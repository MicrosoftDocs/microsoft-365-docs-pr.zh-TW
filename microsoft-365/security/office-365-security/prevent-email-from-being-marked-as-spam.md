---
title: 如何避免 Office 365 發生誤判
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 了解如何避免發生誤判，並將真實的電子郵件排除在 Office 365、Exchange Online 和獨立版 Exchange Online Protection (EOP) 中的垃圾郵件之外。
ms.openlocfilehash: bf6149d21a5088e4507b65c6474918327faf3510
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598690"
---
# <a name="how-to-prevent-good-email-messages-from-being-marked-as-spam-in-office-365"></a>如何在 Office 365 中防止真正的電子郵件被標示為垃圾郵件

 **您的實際電子郵件將在 Office 365 中被標示為垃圾郵件嗎？請執行此動作。**

如果真正的內送電子郵件訊息在 Office 365、Exchange Online 或獨立版 Exchange Online Protection (EOP) 中被標示為垃圾郵件 (_誤判_)，您應該使用 [使用報告訊息增益集][](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，向 Microsoft 回報郵件。 此外，您可以使用 [提交總管][](admin-submission.md) 來提交郵件。

## <a name="determine-why-the-message-was-marked-as-spam"></a>判斷郵件被標示為垃圾郵件的原因

您可以檢視電子郵件標頭來判斷郵件被標示為垃圾郵件的原因，以解決許多誤判問題。 若要檢視郵件標頭，請參閱[在 Outlook 中查看網際網路郵件標題](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)。

具體來說，您需要尋找名為 **X-Forefront-Antispam-Report** 的標頭欄位。 要尋找的重要值如下：

- **SFV:SPM**：郵件是由反垃圾郵件篩選器 (又稱為_內容篩選器_) 標示為垃圾郵件。 如需詳細資訊，請參閱 [Office 365 電子郵件反垃圾郵件防護機制](anti-spam-protection.md)。

- **SFV:BLK**：郵件被標示為垃圾郵件，因為寄件者的電子郵件地址是在**收件者的** [封鎖的寄件者] 清單上。 如需詳細資訊，請參閱[在 Outlook 網頁版中篩選垃圾郵件](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)和[垃圾郵件篩選概觀](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。

- **SFV:SKS**：郵件在反垃圾郵件篩選器可以檢查**之前**，已被標示為垃圾郵件。 例如，郵件流程規則 (又稱為傳輸規則) 會將郵件的垃圾郵件信賴等級 (SCL) 設定為高值 (9)，表示該郵件是垃圾郵件。 如需有關 SCL 的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。

  執行郵件追蹤來查看郵件流程規則是否是高 SCL 值的原因。 如需詳細資訊，請參閱[安全性與合規性中心內的郵件追蹤](message-trace-scc.md)。

- **SFV:SKB**：郵件符合垃圾郵件篩選原則中的封鎖項目 (例如，封鎖的寄件者或封鎖的寄件者網域) 而被標示為垃圾郵件。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。

- **SFV:BULK**：郵件被反垃圾郵件篩選器識別為大量電子郵件，而不是垃圾郵件。 當郵件的大量相容層級 (BCL) 值**大於**反垃圾郵件原則設定 (BCL 值越低表示郵件越有可能是垃圾郵件) 中所定義的大量閾值時，就會發生這種情況。 您可以在 **X-Microsoft-Antispam** 標頭欄位中查看 BCL 值。

  大量電子郵件 (也稱為_灰色郵件_) 是使用者不希望看到的，卻是使用者有意或無意間要求的非惡意行銷或廣告電子郵件。 不同的使用者對應該如何處理大量電子郵件有不同的期望，因此您可以建立不同的原則或規則，相應地允許或封鎖大量電子郵件。 如需詳細資訊，請參閱下列主題：

  - [垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)

  - [大量相容層級值](bulk-complaint-level-values.md)

- **CAT:SPOOF** 或 **CAT:PHISH**：指出郵件似乎是詐騙郵件，表示無法驗證郵件來源，且可能是可疑的郵件。

  如果訊息來自詐騙的寄件者，對應的合法寄件者將需要驗證其公用 DNS 中電子郵件網域的 SPF 和 DKIM 記錄。 如需詳細資訊，請查看 **Authentication-Results** 標頭欄位。 雖然要讓所有的寄件者都使用正確的電子郵件驗證方法並不容易，但略過這些檢查非常危險，且是造成詐騙和網路釣魚郵件的主要原因。

> [!NOTE]
> • 若要深入了解其他反垃圾郵件訊息標頭和值，請參閱[反垃圾郵件訊息標頭](anti-spam-message-headers.md)。 <br/><br/>• 未特別描述的其他標頭欄位和值專供 Microsoft 反垃圾郵件小組進行診斷之用。 <br/><br/>• 郵件標頭中的 **X-CustomSpam** 標頭欄位會指出郵件已由進階垃圾郵件篩選 (ASF) 標示為垃圾郵件。 我們正在將 ASF 功能移至篩選堆疊的其他部分，因此建議您**關閉**反垃圾郵件原則中目前提供的 ASF 設定。 如需詳細資訊，請參閱[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)。

## <a name="solutions-for-too-much-spam"></a>太多垃圾郵件的解決方案

為了讓反垃圾郵件篩選變成最有效率，系統管理員必須在組織中進行一些設定。 如果您不是系統管理員，可以跳至使用者區段。

### <a name="for-admins"></a>適用於系統管理員

- **將您電子郵件網域的 MX 記錄指向 Office 365**：為了讓 Office 365 提供保護，Office 365 中所有電子郵件網域的 MX 記錄都必須指向 Office 365，且僅限 Office 365 (也就是說，這些網域中的收件者電子郵件一律會先傳送到 Office 365)。 如果 MX 記錄指向另一個位置 (例如，協力廠商反垃圾郵件解決方案或設定)，則 Office 365 無法為您的使用者提供垃圾郵件篩選。 在此情況下，請考慮建立略過所有郵件之垃圾郵件篩選的郵件流程規則 (將所有內送郵件的 SCL 值設定為 -1)。 如果您之後決定要將 MX 記錄先指向 Office 365，請務必移除該規則。

- **開啟使用者的回報郵件增益集**：我們強烈建議您為使用者啟用回報郵件增益集。 如需相關指示，請參閱[啟用回報郵件增益集](enable-the-report-message-add-in.md)。

- **使用提交總管**：系統管理員現在可以提交電子郵件，以供 Microsoft 掃描之用。 身為系統管理員，您也可以檢視使用者傳送的意見反應。 您可以使用誤判報告中的模式來調整垃圾郵件篩選設定。 如需詳細資訊，請參閱[如何將可疑的垃圾郵件、網路釣魚、URL 和檔案提交至 Microsoft for Office 365 掃描](admin-submission.md)。

- **驗證您的使用者在允許的限制範圍內**，如 Exchange Online 服務說明中的[接收及傳送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) 中所述。

- **驗證您反垃圾郵件原則中的 BCL 層級**，如本主題稍早所述。

### <a name="for-users"></a>適用於使用者

- **將寄件者新增到** [Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) 或 [Outlook 網頁版](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)中的 [安全寄件者] 清單。

  Office 365 將會使用您的 [安全寄件者] 清單和 [安全收件者] 清單，但不會使用您的 [安全網域] 清單。 無論您如何將網域新增到清單 (在 Outlook、Outlook 網頁版中，或在 Outlook 中，然後透過目錄同步處理進行同步處理) 中，都是如此。

- **停用 Outlook 中的 SmartScreen 篩選**：在舊版 Outlook 桌面用戶端中，請不要在 [垃圾郵件選項]**** 內啟用 SmartScreen 篩選。 SmartScreen 篩選的更新已在 2016 年 11 月結束。 如果您在 Outlook 中啟用 [低]**** 或 [高]**** 垃圾郵件保護，您將使用 SmartScreen 篩選，而且您可能會收到誤判。 請注意，SmartScreen 篩選不適用於新式 Outlook 桌面用戶端。 如需詳細資訊，請參閱 [Outlook 和 Exchange 中 SmartScreen 的取代支援](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/Deprecating-support-for-SmartScreen-in-Outlook-and-Exchange/ba-p/605332)。

## <a name="troubleshooting-a-message-is-delivered-to-the-junk-email-folder-after-passing-anti-spam-filtering"></a>疑難排解：傳遞反垃圾郵件篩選之後，郵件會傳送到 [垃圾郵件] 資料夾

如果使用者已在其 Outlook 垃圾郵件選項中選取 [僅安全的清單]**** 選項，則所有來自使用者 [安全寄件者] 清單或 [安全收件者] 清單之人員的郵件，無論郵件是否通過貴組織的反垃圾郵件篩選，也無論郵件流程規則是否將郵件標示為非垃圾郵件 (SCL 值為 -1)，都將會移至其 [垃圾郵件]**** 資料夾。

在 Outlook 網頁版中，收件者將會看到一個黃色安全提示，指出郵件位於 [垃圾郵件]**** 資料夾，因為寄件者不在其 [安全寄件者] 清單或 [安全收件者] 清單中。

郵件標頭將包含 **X-Forefront-Antispam-Report** 標頭欄位值 `SFV:SKN` (該郵件在反垃圾郵件篩選器處理之前，已標示為非垃圾郵件) 或 `SFV:NSPM` (反垃圾郵件篩選器認為該郵件不是垃圾郵件)，但郵件仍會傳送到使用者的 [垃圾郵件]**** 資料夾。

郵件標頭中沒有任何內容表示郵件因為使用者的 [僅安全的清單]**** 設定，而被傳送為垃圾郵件。 但是，您可以在 Exchange Online PowerShell 中使用 **Get-MailboxJunkEmailConfiguration** Cmdlet，查看使用者是否只允許將來自受信任寄件者的郵件傳送到 [收件匣]。

使用信箱的名稱、別名或電子郵件地址取代 \<MailboxIdentity\>，然後在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 中執行下列命令：

```PowerShell
Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
```

- 如果 *TrustedListsOnly* 屬性值為 `True`：並非來自受信任寄件者或收件者 (亦即，不在使用者的 [安全寄件者] 清單和 [安全收件者] 清單中的人員) 的郵件將會移至其 [垃圾郵件]**** 資料夾。

- 如果 *ContactsTrusted* 屬性值為 `True`：使用者的連絡人也會被視為受信任的寄件者。 如果 *TrustedListsOnly* 屬性值也為 `True`：來自不在使用者的 [安全寄件者] 清單、[安全收件者] 清單或 [連絡人] 中的人員的郵件將會移至其 [垃圾郵件]**** 資料夾。

- *TrustedSendersAndDomains* 屬性值包含使用者的 [安全寄件者] 清單。

若要在信箱上變更這些設定，請使用信箱的名稱、別名或電子郵件地址取代 \<MailboxIdentity\>，然後執行下列命令：

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" -TrustedListsOnly $false -ContactsTrusted $false
```

如需詳細的語法、參數和所需權限的資訊，請參閱 [Get-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-mailboxjunkemailconfiguration) 和 [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) 主題。

## <a name="directory-synchronization-for-standalone-eop-customers"></a>獨立版 EOP 客戶的目錄同步處理

如果您使用獨立版 EOP 來協助保護內部部署的 Exchange 組織，則應該使用目錄同步處理，將使用者設定與服務同步處理。 這樣做可確保 EOP 信任您使用者的 [安全寄件者] 清單。 如需詳細資訊，請參閱[使用目錄同步處理來管理郵件使用者](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users)。
