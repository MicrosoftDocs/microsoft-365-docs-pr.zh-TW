---
title: 設定將協力廠商網路釣魚模擬的傳遞給使用者及未篩選的郵件以 SecOps 信箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 系統管理員可以瞭解如何使用 Exchange Online Protection (EOP) 中的高級傳遞原則，以識別不應該在特定支援案例中篩選的郵件 (協力廠商網路釣魚模擬及傳送至安全性作業的郵件 (SecOps) 信箱。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b989b11739b5418ad14e147f76dde0e0dd7b1b1a
ms.sourcegitcommit: 233989a02a3fc6db33c995ad06b1f820f08f8f0a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383447"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>設定將協力廠商網路釣魚模擬的傳遞給使用者及未篩選的郵件以 SecOps 信箱

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 本文所述的功能都是在預覽中，並非每個人都可以使用，而且可能會變更。

若要讓組織保持[預設安全性](secure-by-default.md)，Exchange Online Protection (EOP) 不允許對識別為惡意程式碼或高可信度網路釣魚的郵件進行安全清單或篩選旁路。 不過，有些特定案例需要傳遞未篩選的郵件。 例如：

- **協力廠商網路釣魚模擬**：模擬的攻擊可協助您在實際攻擊影響組織之前，識別有漏洞的使用者。
- **(SecOps 的安全性作業) 信箱**：安全小組用來收集及分析未篩選郵件 (良好和不良) 的專用信箱。

您可以使用 Microsoft 365 中的 _高級傳遞原則_，以避免篩選這些 _特定案例中_ 的郵件。 <sup>\*</sup>[高級傳遞原則] 可確保這些案例中的郵件達到下列結果：

- EOP 中的篩選器和 Microsoft Defender for Office 365 不會對這些郵件採取任何動作。<sup>\*</sup>
- [零小時清除 (](zero-hour-auto-purge.md) 用於垃圾郵件和網路釣魚的 ZAP) 不會對這些郵件採取任何動作。<sup>\*</sup>
- 在這些情況下，不會觸發[預設系統警示](alerts.md)。
- [Office 365 中的 AIR 和](office-365-air.md)叢集會忽略這些郵件。
- 特別是協力廠商網路釣魚模擬：
  - 系統[管理報送](admin-submission.md)會產生自動回應，表示郵件屬於網路釣魚模擬活動的一部分，而且不是實際威脅。 不會觸發警示和空氣。
  - [保管庫的 Defender 中的連結 Office 365](safe-links.md)不會封鎖或引爆這些郵件中的明確識別 URLs。
  - [保管庫的 Defender 中的附件 Office 365](safe-attachments.md)不會引爆這些郵件中的附件。

<sup>\*</sup> 您無法略過惡意程式碼篩選或 ZAP 惡意程式碼。

由高級傳遞原則識別的郵件不會受到安全性威脅，所以郵件會標示為系統覆寫。 系統管理員可以在下列體驗中篩選和分析這些系統覆寫：

- [Office 365 方案2之 Defender 中的威脅瀏覽器/即時偵測](threat-explorer.md)
- [威脅瀏覽器/即時偵測中的電子郵件實體頁面](mdo-email-entity-page.md)
- [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft Defender for Endpoint 中的高級搜尋](../defender-endpoint/advanced-hunting-overview.md)
- [行銷活動檢視](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。 若要直接移至 [ **高級傳遞** ] 頁面，請開啟] <https://security.microsoft.com/advanceddelivery> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 您必須已獲指派許可權，才能執行本文中的程式：
  - 若要建立、修改或移除 advanced 傳遞原則中已設定的設定，您必須是 **Microsoft 365 Defender 入口網站** 中 **安全性管理員** 角色群組的成員，以及 **Exchange Online** 中 **組織管理** 角色群組的成員。
  - 若要以唯讀方式存取高級傳遞原則，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-microsoft-365-security-center.md)及[Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  > 將使用者新增至對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>使用 Microsoft 365 Defender 入口網站設定高級傳遞原則中的 SecOps 信箱

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則**] 頁面 \> **規則**] 「 \> **高級傳遞**」。

2. 在 [ **高級傳遞** ] 頁面上，確認已選取 [ **SecOps 信箱** ] 索引標籤，然後執行下列其中一個步驟：
   - 按一下 [ ![ 編輯圖示] [ ](../../media/m365-cc-sc-edit-icon.png) **編輯**]。
   - 若未設定網路釣魚模擬，請按一下 [ **新增**]。

3. 在開啟的 [**編輯 SecOps 信箱**] 浮出控制項上，執行下列其中一個步驟，輸入您要指定為 SecOps 信箱的現有 Exchange Online 信箱：
   - 在方塊中按一下，讓信箱清單得以解析，然後選取信箱。
   - 按一下方塊中的 [開始輸入信箱識別碼] (名稱、顯示名稱、別名、電子郵件地址、帳戶名稱等 ) ，然後從結果中選取信箱 (顯示名稱) 。

     視需要重複此步驟多次。 不允許通訊群組。

     若要移除現有的值，請按一下 ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) 值旁邊的 [移除]。

4. 完成後，按一下 **[儲存]**。

您設定的 SecOps 信箱專案會顯示在 [ **SecOps 信箱** ] 索引標籤上。若要進行變更，請按一下索引標籤 ![ ](../../media/m365-cc-sc-edit-icon.png) 上的 [編輯圖示 **編輯** ]。

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>使用 Microsoft 365 Defender 入口網站設定高級傳遞原則中的協力廠商網路釣魚模擬

1. 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則**] 頁面 \> **規則**] 「 \> **高級傳遞**」。

2. 在 [ **高級傳遞** ] 頁面上，選取 [ **網路釣魚類比** ] 索引標籤，然後執行下列其中一個步驟：
   - 按一下 [ ![ 編輯圖示] [ ](../../media/m365-cc-sc-edit-icon.png) **編輯**]。
   - 若未設定網路釣魚模擬，請按一下 [ **新增**]。

3. 在開啟的 [ **編輯協力廠商網路釣魚類比** ] 浮出控制項上，設定下列設定：

   - 傳送 **網域**：展開此設定，然後輸入至少一個電子郵件地址網域 (例如，contoso.com) 按一下方塊中的方塊，輸入值，然後按 enter 或選取方塊下方所顯示的值。 視需要重複此步驟多次。 您最多可以新增10個專案。
   - 傳送 **IP**：展開此設定，並輸入至少一個有效的 IPv4 位址是在方塊中按一下，輸入值，然後按 enter 或選取方塊下方所顯示的值。 視需要重複此步驟多次。 您最多可以新增10個專案。 有效值為：
     - 單一 IP：例如，192.168.1.1。
     - IP 範圍：例如，192.168.0.1-192.168.0.254。
     - CIDR IP：例如 192.168.0.1/25。
   - **類比 URLs 允許**：展開此設定，並選擇性地 URLs 輸入您的網路釣魚類比活動的一部分，而不應該封鎖或引爆，方法是按一下 [方塊]，輸入值，然後按 enter 或選取方塊下方所顯示的值。 您最多可以新增10個專案。 如需 URL 語法格式，請參閱 [承租人 Allow/封鎖清單的 URL 語法](/microsoft-365/security/office-365-security/tenant-allow-block-list#url-syntax-for-the-tenant-allowblock-list)。

   若要移除現有的值，請按一下 ![[移除] 圖示](../../media/m365-cc-sc-remove-selection-icon.png) 值旁邊的 [移除]。

4. 完成作業後，請執行下列其中一個步驟：
   - **第一次**：按一下 [ **新增**]，然後按一下 [ **關閉**]。
   - **編輯現有**：按一下 [ **儲存** ]，然後按一下 [ **關閉**]。

您設定的協力廠商網路釣魚模擬專案會顯示在 [ **網路釣魚類比** ] 索引標籤上。若要進行變更，請按一下索引標籤 ![ ](../../media/m365-cc-sc-edit-icon.png) 上的 [編輯圖示 **編輯** ]。

## <a name="additional-scenarios-that-require-filtering-bypass"></a>需要篩選略過的其他案例

除了高級傳遞原則可以協助您使用的兩種情形之外，還有其他情況可能需要您略過篩選：

- **協力廠商篩選**：如果您的網域的 MX 記錄 *沒有* 指向 Office 365 (郵件會先在其他地方傳送) ，否則 *無法使用* [secure](secure-by-default.md) 。 如果您想要新增保護，必須啟用連接器的增強篩選 (也稱為 *skip 清單*) 。 如需詳細資訊，請參閱[使用具有 Exchange Online 的協力廠商雲端服務管理郵件流程](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)。 如果您不想要增強的連接器篩選功能，請使用郵件流程規則 (也稱為傳輸規則) ，以略過協力廠商篩選已評估之郵件的 Microsoft 篩選功能。 如需詳細資訊，請參閱 [使用郵件流程規則設定郵件中的 SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)。

- **審核** 中的誤報：您可能想要暫時允許 Microsoft 透過系統 [管理員提交](admin-submission.md) 進行的某些郵件仍要進行分析，以報告未正確標記為壞于 microsoft (誤報) 的已知良好郵件。 就像所有覆寫一樣， **_強烈建議_** 這些余量是暫時的。

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>Exchange OnlineSecOps 高級傳遞原則中的信箱的 PowerShell 程式

在 Exchange Online PowerShell 中，高級傳遞原則中 SecOps 信箱的基本元素為：

- **SecOps 覆寫原則**：由 **\* -SecOpsOverridePolicy** Cmdlet 控制。
- **SecOps 覆寫規則**：由 **\* -SecOpsOverrideRule** Cmdlet 控制。

這種行為具有下列結果：

- 您必須先建立原則，然後建立規則來識別套用規則的原則。
- 當您從 PowerShell 中移除原則時，也會移除對應的規則。
- 當您從 PowerShell 中移除規則時，並不會移除對應的原則。 您必須手動移除對應的原則。

### <a name="use-powershell-to-configure-secops-mailboxes"></a>使用 PowerShell 設定 SecOps 信箱

在 PowerShell 的高級傳遞原則中設定 SecOps 信箱是兩個步驟的程式：

1. 建立 SecOps 覆寫原則。
2. 建立 SecOps 覆寫規則，以指定套用規則的原則。

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>步驟1：使用 PowerShell 來建立 SecOps 覆寫原則

若要建立 SecOps 覆寫原則，請使用下列語法：

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

**附注**：不管您指定的名稱值為何，原則名稱都會是 SecOpsOverridePolicy，因此您也可以使用該值。

此範例會建立 SecOps 信箱原則。

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

如需詳細的語法及參數資訊，請參閱 [SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy)。

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>步驟2：使用 PowerShell 建立 SecOps 覆寫規則

本範例會建立具有指定設定的 SecOps 信箱規則。

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

**附注**： * * 不論您指定的名稱值為何，規則名稱都會是 SecOpsOverrideRule \<GUID\> ，其中 \<GUID\> 是唯一的 GUID 值 (例如，6fed4b63-3563-495d-a481-b24a311f8329) 。

如需詳細的語法及參數資訊，請參閱 [SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule)。

### <a name="use-powershell-to-view-the-secops-override-policy"></a>使用 PowerShell 來查看 SecOps 覆寫原則

此範例會傳回單一 SecOps 信箱原則的詳細資訊。

```powershell
Get-SecOpsOverridePolicy
```

如需詳細的語法及參數資訊，請參閱 [SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy)。

### <a name="use-powershell-to-view-secops-override-rules"></a>使用 PowerShell 來查看 SecOps 覆寫規則

本範例會傳回 SecOps 覆寫規則的詳細資訊。

```powershell
Get-SecOpsOverrideRule
```

雖然上一個命令只會傳回一個規則，但結果中也可能會包含任何擱置刪除的規則。

這個範例會識別 (一) 和任何無效規則的有效規則。

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

在您識別不正確規則之後，您可以使用 **SecOpsOverrideRule** 指令程式（如 [本文稍後](#use-powershell-to-remove-secops-override-rules)所述）移除這些規則。

如需詳細的語法及參數資訊，請參閱 [SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>使用 PowerShell 修改 SecOps 覆寫原則

若要修改 SecOps 覆寫原則，請使用下列語法：

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

本範例會將 secops2@contoso.com 新增至 SecOps 覆寫原則。

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

**附注**：如果存在相關聯且有效的 SecOps 覆寫規則，則也會更新該規則中的電子郵件地址。

如需詳細的語法及參數資訊，請參閱 [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy)。

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>使用 PowerShell 修改 SecOps 覆寫規則

**SecOpsOverrideRule** Cmdlet 不會修改 SecOps 覆寫規則中的電子郵件地址。 若要修改 SecOps 覆寫規則中的電子郵件地址，請使用 **SecOpsOverridePolicy** Cmdlet。

如需詳細的語法及參數資訊，請參閱 [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule)。

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>使用 PowerShell 移除 SecOps 覆寫原則

此範例會移除 SecOps 信箱原則和對應的規則。

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

如需詳細的語法及參數資訊，請參閱 [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy)。

### <a name="use-powershell-to-remove-secops-override-rules"></a>使用 PowerShell 移除 SecOps 覆寫規則

若要移除 SecOps 覆寫規則，請使用下列語法：

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

本範例會移除指定的 SecOps 覆寫規則。

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

如需詳細的語法及參數資訊，請參閱 [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule)。

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Exchange Online在高級傳遞原則中 PowerShell 協力廠商網路釣魚模擬的程式

在 Exchange Online PowerShell 中，高級傳遞原則中的協力廠商網路釣魚模擬基本元素為：

- **網路釣魚類比覆寫原則**：由 **\* -PhishSimOverridePolicy** Cmdlet 控制。
- **網路釣魚類比覆寫規則**：由 **\* -PhishSimOverrideRule** Cmdlet 控制。

這種行為具有下列結果：

- 您必須先建立原則，然後建立規則來識別套用規則的原則。
- 您可以修改原則和規則中的設定。
- 當您從 PowerShell 中移除原則時，也會移除對應的規則。
- 當您從 PowerShell 中移除規則時，並不會移除對應的原則。 您必須手動移除對應的原則。

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>使用 PowerShell 設定協力廠商網路釣魚模擬

在 PowerShell 中的高級傳遞原則中設定協力廠商網路釣魚模擬的程式分為兩個步驟：

1. 建立網路釣魚類比覆寫原則。
2. 建立網路釣魚類比覆寫規則，以指定套用規則的原則。

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>步驟1：使用 PowerShell 建立網路釣魚類比覆寫原則

此範例會建立網路釣魚類比覆寫原則。

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**附注**：不管您指定的名稱值為何，原則名稱都會是 PhishSimOverridePolicy，因此您也可以使用該值。

如需詳細的語法及參數資訊，請參閱 [PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy)。

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>步驟2：使用 PowerShell 建立網路釣魚類比覆寫規則

使用下列語法：

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

不論您指定的名稱值為何，規則名稱都會是 PhishSimOverrideRule \<GUID\> ，其中 \<GUID\> 是唯一的 GUID 值 (例如，a0eae53e-d755-4a42-9320-b9c6b55c5011) 。

有效的 IP 位址專案為下列其中一個值：

- 單一 IP：例如，192.168.1.1。
- IP 範圍：例如，192.168.0.1-192.168.0.254。
- CIDR IP：例如 192.168.0.1/25。

此範例會建立具有指定設定的網路釣魚類比覆寫規則。

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

如需詳細的語法及參數資訊，請參閱 [PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule)。

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>使用 PowerShell 來查看網路釣魚類比覆寫原則

此範例會傳回單一網路釣魚類比覆寫原則的詳細資訊。

```powershell
Get-PhishSimOverridePolicy
```

如需詳細的語法及參數資訊，請參閱 [PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy)。

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>使用 PowerShell 來查看網路釣魚類比覆寫規則

此範例會傳回網路釣魚類比覆寫規則的詳細資訊。

```powershell
Get-PhishSimOverrideRule
```

雖然上一個命令只會傳回一個規則，但結果中也可能會包含任何擱置刪除的規則。

這個範例會識別 (一) 和任何無效規則的有效規則。

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

在您識別不正確規則之後，您可以使用 **PhisSimOverrideRule** 指令程式（如 [本文稍後](#use-powershell-to-remove-phishing-simulation-override-rules)所述）移除這些規則。

如需詳細的語法及參數資訊，請參閱 [PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule)。

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>使用 PowerShell 修改網路釣魚類比覆寫原則

若要修改網路釣魚類比覆寫原則，請使用下列語法：

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

此範例會停用網路釣魚類比覆寫原則。

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

如需詳細的語法及參數資訊，請參閱 [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy)。

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a>使用 PowerShell 修改網路釣魚類比覆寫規則

若要修改網路釣魚類比覆寫規則，請使用下列語法：

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

此範例會使用下列設定修改指定的網路釣魚類比覆寫規則：

- 新增網域專案 blueyonderairlines.com。
- 移除 IP 位址專案192.168.1.55。

請注意，這些變更不會影響現有專案。

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

如需詳細的語法及參數資訊，請參閱 [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule)。

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>使用 PowerShell 移除網路釣魚類比覆寫原則

此範例會移除網路釣魚類比覆寫原則和對應的規則。

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

如需詳細的語法及參數資訊，請參閱 [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy)。

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>使用 PowerShell 移除網路釣魚類比覆寫規則

若要移除網路釣魚類比覆寫規則，請使用下列語法：

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

此範例會移除指定的網路釣魚類比覆寫規則。

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

如需詳細的語法及參數資訊，請參閱 [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule)。
