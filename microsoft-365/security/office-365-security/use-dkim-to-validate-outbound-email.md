---
title: 如何將 DKIM 用於自訂網域中的電子郵件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
audience: ITPro
ms.topic: article
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 了解如何搭配 Microsoft 365 中使用網域金鑰識別郵件 (DKIM)，以確保目的地電子郵件系統信任從您自訂網域傳送的郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9aa67d7875bb7f81c6569b56704d221b57378962
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108496"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a>使用 DKIM 驗證從您自訂網域傳送的輸出電子郵件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 本文列出在 Microsoft 365 中使用網域金鑰識別郵件 (DKIM) 的步驟，以確保目的地電子郵件系統會信任從您自訂網域對外傳送的郵件。

本文內容：

- [DKIM 防止惡意詐騙的效用為何優於單獨使用 SPF](#how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing)
- [將 1024 位元金鑰手動升級至 2048 位元 DKIM 加密金鑰的步驟](#steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys)
- [手動設定 DKIM 的步驟](#steps-to-manually-set-up-dkim)
- [為多個自訂網域設定 DKIM 的步驟](#to-configure-dkim-for-more-than-one-custom-domain)
- [停用自訂網域 DKIM 簽署原則](#disabling-the-dkim-signing-policy-for-a-custom-domain)
- [DKIM 和 Microsoft 365 的預設行為](#default-behavior-for-dkim-and-microsoft-365)
- [設定 DKIM，讓第三方服務可代表您的自訂網域傳送 (或偽造) 電子郵件](#set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain)
- [後續步驟：為 Microsoft 365 設定 DKIM 之後](#next-steps-after-you-set-up-dkim-for-microsoft-365)

> [!NOTE]
> Microsoft 365 會自動為其初始 'onmicrosoft.com' 網域設定 DKIM。 這表示您不需要執行任何操作，即可為任何初始網域名稱設定 DKIM (例如：litware.onmicrosoft.com)。 如需網域的詳細資訊，請參閱[網域常見問題集](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain)。

DKIM 是三個驗證方法 (SPF、DKIM 和 DMARC) 的其中一個，可協助防止攻擊者傳送看起來像來自您網域的郵件。

DKIM 可讓您在郵件標頭中將數位簽章新增到外寄電子郵件訊息中。 在設定 DKIM 時，您會授權給網域，使其能夠使用密碼編譯驗證將其名稱簽署至電子郵件訊息，或建立關聯。 電子郵件系統在取得來自您網域的電子郵件時，可以利用此數位簽章來協助驗證內送電子郵件是否合法。

基本而言，私密金鑰會加密網域外寄電子郵件中的標頭。 您可以將公開金鑰發佈至網域的 DNS 記錄，讓接收端伺服器可以用此金鑰來解碼簽章。 DKIM 驗證可協助接收伺服器確認郵件確實來自您的網域，而不是有人對您的網域 *進行詐騙*。

> [!TIP]
>您也可以選擇不為自訂網域進行任何 DKIM 設定。如果您未替自訂網域設定 DKIM，Microsoft 365 將會為您的自訂網域建立私密和公開金鑰組、啟用 DKIM 簽章，然後設定 Microsoft 365 預設原則。

 Microsoft 365 的內建 DKIM 設定對大部分的客戶而言已足夠使用，但在下列情況下，您仍應手動為自訂網域設定 DKIM：

- 您在 Microsoft 365 中有多個自訂網域
- 您也將設定 DMARC (**建議**)
- 您想要控管私密金鑰
- 您想要自訂 CNAME 記錄
- 您想要為來自於第三方網域的電子郵件設定 DKIM，例如，當您使用第三方大量郵件寄件者時。

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a>DKIM 防止惡意詐騙的效用為何優於單獨使用 SPF
<a name="HowDKIMWorks"> </a>

SPF 會在郵件信封中新增資訊，但 DKIM 則會為郵件標頭中的數位簽章 *加密*。 當您轉寄郵件時，轉寄端伺服器可能會將該郵件信封的某些部分移除掉。 由於數位簽章是電子郵件標頭的一部分，會存留在電子郵件訊息內，因此即使郵件已轉寄，DKIM 仍可運作，如下列範例所示。

![流程圖顯示當 SPF 檢查不通過時，轉送的訊息會傳遞 DKIM 驗證](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

在此範例中，如果您只為您的網域發佈 SPF TXT 記錄，收件者的郵件伺服器可能會將您的電子郵件標示為垃圾郵件，並產生誤判的結果。 **在此案例中，加入 DKIM 可減少 *誤判* 垃圾郵件的報告。** 由於 DKIM 也使用公開金鑰密碼編譯進行驗證，而非僅使用 IP 位址，因此我們認為 DKIM 是遠優於 SPF 的驗證形式。 我們建議您在部署中應同時使用 SPF 和 DKIM 以及 DMARC。

> [!TIP]
> DKIM 會使用私密金鑰將加密的簽章插入郵件標頭中。 登入網域 (或輸出網域) 會在標頭中插入作為 **d=** 欄位的值。 驗證網域 (或收件者網域) 隨後會使用 **d=** 欄位來查閱來自 DNS 的公開金鑰，並驗證郵件。 如果訊息通過驗證，即可通過 DKIM 檢查。


## <a name="steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>將 1024 位元金鑰手動升級至 2048 位元 DKIM 加密金鑰的步驟
<a name="1024to2048DKIM"> </a>

> [!NOTE]
> Microsoft 365 會自動為 *onmicrosoft.com* 網域設定 DKIM。 不需要任何步驟，就可以將 DKIM 用於任何初始網域名稱 (例如 litware.*onmicrosoft.com*)。 如需網域的詳細資訊，請參閱 [網域常見問題集](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain)。

由於 DKIM 金鑰同時支援 1024 和 2048 位元，這些指示會告訴您如何在 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 中將您的 1024 位元金鑰升級至 2048。 下列步驟適用於兩個使用案例，請選擇最符合您設定的案例。

- 當您 **已設定 DKIM** 時，您可以執行下列命令來輪轉位元：

  ```powershell
  Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
  ```

  **或**

- 如需 **DKIM 的新實作**，請執行下列命令：

  ```powershell
  New-DkimSigningConfig -DomainName <Domain for which config is to be created> -KeySize 2048 -Enabled $true
  ```

請透過執行下列命令，保持連線至 Exchange Online PowerShell，以 *確認* 設定：

```powershell
Get-DkimSigningConfig -Identity <Domain for which the configuration was set> | Format-List
```

> [!TIP]
> 這個新的 2048 位元金鑰會在 RotateOnDate 時生效，並會在過渡期使用 1024 位元金鑰傳送電子郵件。 4 天後，您可以使用 2048 位元金鑰再次測試 (亦即輪轉對第二個選取器生效的時候)。

如果您想要輪轉至第二個選取器，您的選項為 a) 讓 Microsoft 365 服務輪選取器，並在接下來 6 個月內升級到 2048 位元，或是 b) 在 4 天後並確認 2048 位元使用中時，使用上方所列的適當 Cmdlet，手動輪轉第二個選取器金鑰。

如需詳細的語法和參數資訊，請參閱下列文章：[Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)、[New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig) 和 [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig)。

## <a name="steps-to-manually-set-up-dkim"></a>手動設定 DKIM 的步驟
<a name="SetUpDKIMO365"> </a>

若要設定 DKIM，您應完成下列步驟：

- [將兩個 CNAME 記錄發佈至您在 DNS 中的自訂網域](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
- [為自訂網域啟用 DKIM 簽署](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>將兩個 CNAME 記錄發佈至您在 DNS 中的自訂網域
<a name="Publish2CNAME"> </a>

對於要在 DNS 中新增 DKIM 簽章的每個網域，您必須發佈兩個 CNAME 記錄。

> [!NOTE]
> 如果您還沒有閱讀完整的文章，則可能錯過了這份可節省時間的 PowerShell 連線資訊：[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

在 Exchange Online PowerShell 中執行下列命令，以建立選取器記錄：

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

如果您在 Microsoft 365 中除了初始網域以外也佈建了自訂網域，則必須為每個額外的網域發佈兩個 CNAME 記錄。 因此，如果您有兩個網域，您必須發佈兩個額外的 CNAME 記錄，依此類推。

CNAME 記錄應使用下列格式。

> [!IMPORTANT]
> 如果您是我們的 GCC High 客戶，我們會以不同的方式計算 _domainGuid_！ 我們在計算 _domainGuid_ 時不會查閱您 _initialDomain_ 的 MX 記錄，而是會直接從自訂的網域計算。 例如，如果您的自訂網域是 "contoso.com"，則您的 domainGuid 會變成 "contoso-com"，任何句點都會取代為虛線。 因此，無論您的 initialDomain 指向哪個 MX 記錄，您都將一律使用上述方法來計算在您的 CNAME 記錄中使用的 domainGuid。

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

其中：

- Microsoft 365 的選取器將一律為 "selector1" 或 "selector2"。
- _domainGUID_ 會與您自訂網域的自訂 MX 記錄中顯示於 mail.protection.outlook.com 前面的 _domainGUID_ 相同。 例如，在網域 contoso.com 的下列 MX 記錄中，_domainGUID_ 為 contoso-com：

  > contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com

- _initialDomain_ 是您註冊 Microsoft 365 時所使用的網域。 初始網域的結尾一律為 onmicrosoft.com。 如需如何判斷初始網域的相關資訊，請參閱[網域的常見問題集](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain)。

例如，如果您的初始網域為 cohovineyardandwinery.onmicrosoft.com，並且有兩個自訂網域 cohovineyard.com 和 cohowinery.com，則必須為每個額外的網域各設定兩個 CNAME 記錄，因此共計四個 CNAME 記錄。

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> 建立第二筆記錄很重要，但建立時只能使用其中一個選取器。 基本上，第二個選取器可能會指向尚未建立的位址。 我們還是建議您建立第二筆 CNAME 記錄，因為您的金鑰輪換會較流暢。

### <a name="steps-to-enable-dkim-signing-for-your-custom-domain"></a>為自訂網域啟用 DKIM 簽署的步驟
<a name="EnableDKIMinO365"> </a>

在 DNS 中發佈 CNAME 記錄後，您即可透過 Microsoft 365 啟用 DKIM 簽署。 您可以透過 Microsoft 365 系統管理中心或使用 PowerShell 來執行此作業。

#### <a name="to-enable-dkim-signing-for-your-custom-domain-in-the-microsoft-365-defender-portal"></a>若要在 Microsoft 365 Defender 入口網站中啟用自訂網域的 DKIM 簽署

1. [使用您的公司或學校帳戶](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) 開啟 Microsoft 365 Defender 入口網站。

2. 前往 **電子郵件與共同作業** \> **原則與規則** \> **威脅原則** 頁面 \>**規則** 區段 \> **DKIM**。 或者，若要直接前往 DKIM 頁面，請使用 <https://security.microsoft.com/dkimv2>。

3. 在 **[DKIM]** 頁面上，按一下名稱以選取網域。

4. 在顯示的詳細資料飛出視窗中，將 **[使用 DKIM 簽章簽署此網域的郵件]** 設定為 **[啟用]** (![[切換開啟]](../../media/scc-toggle-on.png))

   完成後，按一下 **[變換 DKIM 金鑰]**。

5. 對每個自訂網域重複此步驟。

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>使用 PowerShell 為自訂網域啟用 DKIM 簽署

> [!IMPORTANT]
> :::image type="content" source="../../media/dkim.png" alt-text="「沒有儲存于這個網域的 DKIM 金鑰。」錯誤。":::
> 如果您是第一次設定 DKIM，並看到螢幕顯示 [沒有儲存此網域的 DKIM 金鑰] 錯誤，請完成下列步驟 2 的命令 (如範例 `Set-DkimSigningConfig -Identity contoso.com -Enabled $true`)，以查看金鑰。

1. [連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 使用下列語法：

   ```powershell
   Set-DkimSigningConfig -Identity <Domain> -Enabled $true
   ```

   \<Domain\> 是要啟用 DKIM 簽署的自訂網域名稱。

   此範例會啟用 contoso.com 網域的 DKIM 簽署：

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a>確認已為 Microsoft 365 正確設定 DKIM 簽章

請稍待幾分鐘，再依照下列步驟來確認您已正確設定 DKIM。 這可讓關於網域的 DKIM 資訊有時間散佈到整個網路。

- 從已啟用 Microsoft 365 DKIM 的網域內包含的帳戶，傳送郵件到另一個電子郵件帳戶，例如 outlook.com 或 Hotmail.com。
- 請勿使用 aol.com 帳戶進行測試。 在通過 SPF 檢查的情況下，AOL 可能會略過 DKIM 檢查。 這將使您的測試失去效用。
- 開啟郵件並查看標頭。 檢視郵件標頭的指示會隨著您的郵件用戶端而不同。 如需在 Outlook 中檢視郵件標題的相關指示，請參閱[在 Outlook 中檢視網路訊息標題](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)。

  DKIM 簽署的郵件會包含您在發佈 CNAME 項目時所定義的主機名稱和網域。郵件會如下列範例所示：

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- 查看 Authentication-Results 標頭。 雖然每個接收服務分別使用稍有不同的格式為內送郵件加上戳記，但結果應會包含類似於 **DKIM=pass** 或 **DKIM=OK** 的項目。

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a>為多個自訂網域設定 DKIM
<a name="DKIMMultiDomain"> </a>

如果您日後決定要新增另一個自訂網域，且您想要為新的網域啟用 DKIM，您必須為每個網域完成本文所述的步驟。 明確而言，請完成[手動設定 DKIM 時需執行哪些作業](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)中的所有步驟。

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a>停用自訂網域 DKIM 簽署原則
<a name="DisableDKIMSigningPolicy"> </a>

停用簽署原則並不會完全停用 DKIM。 一段時間後，Microsoft 365 會自動為您的網域套用預設的原則。 如需詳細資訊，請參閱 [DKIM 與 Microsoft 365 的預設行為](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)。

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>使用 Windows PowerShell 停用 DKIM 簽署原則

1. [連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 為您要停用 DKIM 簽署的每個網域執行下列命令。

   ```powershell
   $p = Get-DkimSigningConfig -Identity <Domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   例如：

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   或

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   其中，_number_ 是原則的索引。 例如：

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a>DKIM 和 Microsoft 365 的預設行為
<a name="DefaultDKIMbehavior"> </a>

若您未啟用 DKIM，Microsoft 365 將為您的預設網域自動建立 1024 位元 DKIM 公開金鑰，我們在資料中心內部儲存的相關私密金鑰。 根據預設，對於未設定原則的網域，Microsoft 365 會使用預設的簽署組態。 這表示，如果您未自行設定 DKIM，Microsoft 365 將會使用預設原則，以及為了替您網域啟用 DKIM 而建立的金鑰。

此外，如果您在啟用 DKIM 簽署後加以停用，在經過一段時間後，Microsoft 365 將會自動為您的網域套用預設原則。

在下列範例中，假設 fabrikam.com 的 DKIM 是由 Microsoft 365 所啟用，而不是網域的系統管理員所啟用的。 這表示必要的 CNAME 不存在於 DNS 中。 在來自此網域的電子郵件中，DKIM 簽章會顯示如下：

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

在此範例中，主機名稱和網域會包含 CNAME 在網域系統管理員已為 fabrikam.com 啟用 DKIM 簽署時所將指向的值。 最後，每一則從 Microsoft 365 傳送的郵件都會由 DKIM 簽署。 如果您自行啟用 DKIM，網域將會與「寄件者:」位址中的網域相同；在此案例中為 fabrikam.com。 若未自行啟用，則網域會不同，且會改用組織的初始網域。 如需如何判斷初始網域的相關資訊，請參閱[網域的常見問題集](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain)。

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>設定 DKIM，讓第三方服務可代表您的自訂網域傳送 (或偽造) 電子郵件
<a name="SetUp3rdPartyspoof"> </a>

某些大量電子郵件服務提供者或軟體即服務提供者，會允許您為來自於其服務的電子郵件設定 DKIM 金鑰。 若要設定所需的 DNS 記錄，您必須與第三方提供者進行協調。 部分第三方伺服器可以擁有不同選取器之自己的 CNAME 記錄。 每個組織的設定方式都不盡相同。 具體程序完全取決於組織。

若已為 contoso.com 和 bulkemailprovider.com 正確設定 DKIM，郵件可能會如下列範例所示：

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

在此範例中，若要達到此結果：

1. 大量電子郵件提供者為 Contoso 提供 DKIM 公開金鑰。

2. Contoso 將 DKIM 金鑰發佈至其 DNS 記錄。

3. 傳送電子郵件時，大量電子郵件提供者以對應的私密金鑰簽署金鑰。 藉由此動作，大量電子郵件提供者將 DKIM 簽署附加至郵件標頭。

4. 接收端電子郵件系統針對郵件的「寄件者:」(5322.From) 位址驗證 DKIM-Signature d=\<domain\> 值，以執行 DKIM 檢查。 在此範例中，這些值符合：

   > sender@**contoso.com**

   > d=**contoso.com**

## <a name="identify-domains-that-do-not-send-email"></a>辨識出無法傳送電子郵件的網域

組織應明確聲明網域是否不會透過這些網域的 DKIM 記錄中指定的 `v=DKIM1; p=` 來傳送電子郵件。 這建議您收受電子郵件伺服器並沒有網域的有效公用金鑰，且所有聲稱來自該網域的電子郵件都會遭到拒絕。 您應使用萬用字元 DKIM 為每個網欲和子網域執行此動作。

例如，DKIM 記錄看起來會像這樣:

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a>後續步驟：為 Microsoft 365 設定 DKIM 之後
<a name="DKIMNextSteps"> </a>

雖然 DKIM 可協助您防範詐騙，但 DKIM 與 SPF 和 DMARC 搭配運作時，效果會更好。 設定 DKIM 之後，如果您尚未設定 SPF，應加以設定。 如需 SPF 的快速簡介並快速設定，請參閱[在 Microsoft 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 如需更深入了解 Microsoft 365 如何使用 SPF 或是進行疑難排解或非標準的部署 (例如混合式部署)，請先參閱 [ 365 如何使用寄件者原則架構 (SPF) 防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)。 接下來，請參閱[使用 DMARC 來驗證電子郵件](use-dmarc-to-validate-email.md)。 [反垃圾郵件訊息標頭](anti-spam-message-headers.md)包含 Microsoft 365 針對 DKIM 檢查所使用的語法及標頭欄位。

## <a name="more-information"></a>其他資訊

透過 PowerShell 輪換金鑰 [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)
