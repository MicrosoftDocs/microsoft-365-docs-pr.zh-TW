---
title: 設定 SPF 以協助防止詐騙
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何更新網域名稱服務 (DNS) 記錄，以在 Office 365 內的自訂網域中使用寄件者原則架構 (SPF)。
ms.openlocfilehash: a6cd2a0cf60812bb874c1be63fb2d294cda6d6aa
ms.sourcegitcommit: 31be333178b934c519f419656f4c3a53e1beffdc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2021
ms.locfileid: "49881714"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>設定 SPF 以協助防止詐騙

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

- [必要條件<a name="UpdateSPFTXT"></a>](#updating-your-spf-txt-record-for-office-365-a-nameUpdateSPFTXT)
- [為 Office 365 建立/更新 SPF TXT 記錄 <a name="CreateUpdateSPFTXT"></a>](#to-create-or-update-your-spf-txt-record-a-namecreateupdatespftxta)
    - [如何處理子網域？<a name="SPFandSubdomains"></a>](#how-to-handle-subdomains-a-namespfandsubdomainsa)
- [SPF 疑難排解和最佳做法 <a name="TshootingSPF"></a>](#next-steps-after-you-set-up-spf-for-office-365-a-nametshootingspfa)
- [進階 SPF 範例<a name="AdvancedSPFexs"></a>](#more-information-about-spf-a-nameadvancedspfexsa)

本文說明如何更新網域名稱服務 (DNS) 記錄，以便可以在 Office 365 中結合使用寄件者原則架構 (SPF) 電子郵件驗證和自訂網域。

使用 SPF 協助驗證自您自訂網域傳送的輸出電子郵件。 這是設定其他推薦的電子郵件驗證方法 DMARC 和 DKIM (Office 365 還支援另外兩種電子郵件驗證方法) 的第一步。

## <a name="updating-your-spf-txt-record-for-office-365"></a>更新 Office 365 的 SPF TXT 記錄<a name="UpdateSPFTXT"></a>

> [!IMPORTANT]
> 如果您是 **小型企業**，或是不熟悉 IP 位址或 DNS 設定，請致電您的網際網路網域註冊機構 (例如， GoDaddy、Bluehost、web.com) 請求有關 SPF 的 DNS 設定 (以及任何其他電子郵件驗證方法) 的協助。 *另外*，如果您尚未購買或未使用自訂 URL (換言之，您和您的客戶瀏覽至 Office 365 的 URL 以 **onmicrosoft.com** 結尾)，已在 Office 365 服務中為您設定 SPF。 在這種情況下，不需要採取進一步的步驟。 感謝閲讀。

在 DNS 中更新 TXT 記錄之前，需要收集一些製作記錄所需的資訊。 如需進階範例和有關支援的 SPF 語法的更詳細討論，請參閱 [SPF 如何在 Office 365 中運作以防止詐騙和網路釣魚](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。

收集這項資訊：

- 自訂網域的目前 SPF TXT 記錄 (如果存在)。 如需相關指示，請參閱[收集建立 Office 365 DNS 記錄所需的資訊](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)。

- 前往訊息伺服器並尋找外部 IP 位址 (需要來自所有內部部署訊息伺服器)。 例如，**131.107.2.200**。

- 要使用的網域名稱，針對您需要包含在 SPF TXT 記錄中的所有協力廠商網域。某些大量郵件提供者已設定要用於他們的客戶的子網域。例如，公司 MailChimp 已設定 **servers.mcsv.net**。

- 確定您想要對 SPF TXT 記錄使用何種強制執行規則。 建議使用 **-al** l規則。 如需其他語法選項的詳細資訊，請參閱 [Office 365 的 SPF TXT 記錄語法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)。

> [!IMPORTANT]
> 如要使用自訂網域，Office 365 要求您將寄件者原則架構 (SPF) TXT 記錄新增至您的 DNS 記錄以協助防止詐騙。

## <a name="create-or-update-your-spf-txt-record"></a>建立或更新您的 SPF TXT 記錄<a name="CreateUpdateSPFTXT"></a>

1. 請確定您熟悉下表中的 SPF 語法。

   ****

   |元素|如果您正在使用...|對客戶通用？|新增此...|
   |---|---|---|---|
   |1|任何電子郵件系統 (必要項)|通用。以此值開頭的所有 SPF TXT 記錄|`v=spf1`|
   |2|Exchange Online|通用|`include:spf.protection.outlook.com`|
   |3|僅限 Exchange Online 專用|不通用|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |4|僅限 Office 365 德國、Microsoft Cloud 德國|不通用|`include:spf.protection.outlook.de`|
   |5|協力廠商電子郵件系統|不通用|`include:<domain_name>` <p> \<domain_name\> 是協力廠商電子郵件系統的網域。|
   |6|內部部署電子郵件系統。例如，Exchange Online Protection 加上另一個電子郵件系統|不通用|對每個額外郵件系統使用其中一個︰ <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> \<IP_address\> 和 \<domain_name\> 是其他郵件系統的 IP 位址和網域，可代表您的網域傳送電子郵件。|
   |7|任何電子郵件系統 (必要項)|通用。以此值結束的所有 SPF TXT 記錄|`<enforcement rule>` <p> 這可以是數個值其中之一。 我們建議的值是 `-all`。|
   |

2. 如果您還未這樣做，請使用表格中的語法以形成 SPF TXT 記錄。

   例如，如果您已完全裝載於 Office 365，也就是您沒有內部部署郵件伺服器，您的 SPF TXT 記錄會包含 1、2 和 7 的資料列，並且看起來如下：

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   這是最通用的 SPF TXT 記錄。 這筆記錄可供絕大部分人使用，無論您的 Microsoft 資料中心是設於美國、歐洲 (包括德國) 或其他地方。

   不過，如果您已購買 Microsoft Office 365 Germany (為 Microsoft Cloud Germany 德國的一部分)，您應該使用第 4 行所包含的陳述式，而不是第 2 行。 例如，如果您已經完全裝載於 Office 365 Germany，也就是您沒有內部部署郵件伺服器，您的 SPF TXT 記錄會包含 1、4 和 7 的資料列，並且看起來如下：

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   如果您已部署 Office 365，並已為您的自訂網域設定 SPF TXT 記錄，且正在移轉至 Office 365 Germany，您將需要更新 SPF TXT 記錄。 若要這麼做，請將 `include:spf.protection.outlook.com` 變更為 `include:spf.protection.outlook.de`。

3. 一旦您已形成 SPF TXT 記錄，您需要在 DNS 中更新記錄。 您的網域只能有一個 SPF TXT 記錄。 如果存在 SPF TXT 記錄，請不要新增新的記錄，而是必須更新現有的記錄。 移至[建立 Office 365 的 DNS 記錄](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)，然後按一下您的 DNS 主機的連結。

4. 測試您的 SPF TXT 記錄。

## <a name="how-to-handle-subdomains"></a>如何處理子網域？ <a name="SPFandSubdomains"></a>

請注意，*你必須為每個子網域建立個別記錄，因為子網域無法獲取最上層網域的 SPF 記錄*。

每個網域和子網域都需要額外的通配符 SPF 記錄（`*.`），以免攻擊者傳送聲稱為來自不存在之子網域的電子郵件。 例如：

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="next-steps"></a>後續步驟<a name="TshootingSPF"></a>

無法使用您的 SPF TXT 記錄嗎? 請閲讀[疑難排解：Office 365 中 SPF 的最佳做法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。


## <a name="what-does-spf-email-authentication-actually-do"></a>SPF 電子郵件驗證實際上做什麼？

SPF 會識別哪些郵件伺服器可以代表您傳送郵件。 基本上，SPF 以及 DKIM、DMARC 和其他 Office 365 所支援的技術可以協助防止詐騙和網路釣魚。 SPF 會新增為 TXT 記錄，DNS 用來識別哪些郵件伺服器可以代表您的網域傳送郵件。 收件者郵件系統參考 SPF TXT 記錄，以判斷您自訂網域的郵件是否來自授權的郵件伺服器。

例如，假設您的自訂網域 contoso.com 是使用 Office 365。您新增了 SPF TXT 記錄，而該記錄將 Office 365 訊息伺服器列為您的網域的合法郵件伺服器。當接收郵件伺服器是從 joe@contoso.com 取得訊息時，伺服器就會查閱 contoso.com 的 SPF TXT 記錄，並且找出訊息是否有效。如果接收伺服器發現訊息來自 SPF 記錄中所列的 Office 365 訊息伺服器以外的伺服器，接收郵件伺服器可以選擇將訊息當作垃圾郵件拒絕。

此外，如果您的自訂網域沒有 SPF TXT 記錄，某些接收伺服器可能會拒絕徹底訊息。這是因為接收伺服器無法驗證訊息是來自授權的訊息伺服器。

如果您已經設定 Office 365 的郵件，然後您已經在 DNS 中包含 Microsoft 的訊息伺服器作為 SPF TXT 記錄。不過，在某些情況下，您可能需要在 DNS 中更新您的 SPF TXT 記錄。例如：

- 以往，如果您是使用 SharePoint Online，您需要新增不同的 SPF TXT 記錄至您的自訂網域。你不再需要這樣做。此變更會降低 SharePoint Online 通知訊息被置於「垃圾電子郵件」資料夾的機率。如果您達到 10 次查閱限制，且收到錯誤，表示「超出查閱限制」和「太多躍點」，請更新您的 SPF TXT 記錄。

- 如果您有 Office 365 與 Exchange 內部部署的混合式環境。

- 您想要設定 DKIM 和 DMARC (建議選項)。

## <a name="more-information-about-spf"></a>關於 SPF 的詳細資訊<a name="AdvancedSPFexs"></a>

如需進階範例、有關支援的 SPF 語法、詐騙、疑難排解，以及 Office 365 如何支援 SPF 的更詳細討論，請參閱 [SPF 如何運作以防止 Office 365 中的詐騙和網路釣魚](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。

## <a name="links-to-configure-dkim-and-dmarc"></a>用於設定 DKIM 和 DMARC 的連結

 SPF 旨在協助防止詐騙，但是仍有 SPF 無法防護的詐騙技術。 為了防範這些騙術，設定 SPF 之後，應該為 Office 365 設定 DKIM 和 DMARC。

[DKIM](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide) 電子郵件驗證的目標是證明郵件的內容沒有被篡改。

[DMARC](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dmarc-to-validate-email?view=o365-worldwide) 電子郵件驗證的目標是確保 SPF 和 DKIM 資訊與寄件者地址相符。