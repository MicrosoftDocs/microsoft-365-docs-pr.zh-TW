---
title: 如何避免 Office 365 發生誤判
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
description: 了解如何避免 Office 365 誤判，並篩選出真正的電子郵件與垃圾郵件。
ms.openlocfilehash: f1c83ee08c38a5456a44c8c73c55a7b456b93589
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2019
ms.locfileid: "39233496"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a>如何在 Office 365 中防止實際電子郵件被標示為垃圾郵件

 **您的實際電子郵件將在 Office 365 中被標示為垃圾郵件嗎？請執行此動作。**

如果發生誤判，您應使用[使用回報郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)向 Microsoft 回報該郵件。此外，您可以使用[提交總管](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)來提交郵件。

> [!NOTE]
> 標頭中未在以下提及的任何其他欄位，專門由 Microsoft 反垃圾郵件團隊用於進行診斷。

## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a>判斷郵件被標示為垃圾郵件的原因

您可以[檢視電子郵件訊息標頭](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)並判定發生何種問題，來解決 Office 365 中的許多垃圾郵件問題。您需要尋找名為 X-Forefront-Antispam-Report 的標頭。您可以[深入了解反垃圾郵件標頭](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-message-headers)。

在標頭中，尋找下列標題和值。

### <a name="x-forefront-antispam-report"></a>X-Forefront-Antispam-Report

- **SFV:SPM**：表示郵件已因 EOP 垃圾郵件篩選而標示為垃圾郵件。

- **SFV:BLK**：指出已將郵件標示為垃圾郵件，因為寄件地址是在收件者封鎖的寄件者清單上。

- **SFV:SKS**：指出在篩選內容之前已將郵件標示為垃圾郵件。這可能包括將郵件標示為垃圾郵件的郵件流程規則 (也稱為傳輸規則)。請執行郵件追蹤，來查看是否已觸發可能設定高垃圾郵件信賴等級 (SCL) 的郵件流程規則。

- **SFV:SKB**：指出已將郵件標示為垃圾郵件，因為它符合垃圾郵件篩選原則中的封鎖清單。

- **SFV:BULK**：指出位於 x-microsoft-antispam 標頭中的大量抱怨層級 (BCL) 值高於已對內容篩選器設定的大量閾值。大量電子郵件是使用者可能已註冊，但仍有可能不想要的電子郵件。在郵件標頭中，於 X-Microsoft-Antispam 標頭中尋找 BCL (大量信賴等級) 屬性。如果 BCL 值小於垃圾郵件篩選器中設定的閾值，您可能想要調整閾值，而不是將這些類型的大量郵件標示為垃圾郵件。不同的使用者對於[大量電子郵件的處理方式](https://docs.microsoft.com/microsoft-365/security/office-365-security/bulk-complaint-level-values)各有不同的容錯和喜好設定。您可以針對不同的使用者喜好設定建立不同的原則或規則。

- **CAT:SPOOF** 或 **CAT:PHISH**：指出郵件似乎是詐騙郵件，表示無法驗證郵件來源，且可能是可疑的郵件。如果有效，寄件者將需要確定它們具有適當的 SPF 及 DKIM 設定。如需詳細資訊，請檢查 Authentication-Results 標頭。雖然可能很難讓所有寄件者都使用適當的電子郵件驗證方法，但略過這些檢查可能風險極大，而且是造成危害的首要原因。

### <a name="x-customspam"></a>x-customspam

- 若出現此標頭，表示郵件已標示為垃圾郵件，因為已在您的垃圾郵件篩選器中啟用其中一個[進階垃圾郵件選項](https://docs.microsoft.com/microsoft-365/security/office-365-security/advanced-spam-filtering-asf-options)。除非您需要這些功能，否則我們建議您使用預設設定。

## <a name="solutions-to-additional-causes-of-too-much-spam"></a>造成太多垃圾郵件之其他原因的解決方案

若要有效地運作，Exchange Online Protection (EOP) 需要系統管理員完成一些工作。如果您不是 Office 365 租用戶的系統管理員，而且收到太多垃圾郵件，則您可能會想要與您的系統管理員合作處理這些工作。否則，您可以跳至使用者區段。

### <a name="for-admins"></a>適用於系統管理員

- **將您的 DNS 記錄指向 Office 365**：為了讓 EOP 提供防護，所有網域的郵件交換程式 (MX) DNS 記錄都必須指向 Office 365，而且只能指向 Office 365。如果您的 MX 未指向 Office 365，則 EOP 不會為您的使用者提供垃圾郵件篩選功能。在您想要使用其他服務或應用裝置為您的網域提供垃圾郵件篩選功能的情況下，您應該考慮在 EOP 中停用垃圾郵件保護。做法為建立一個郵件流程規則，將 SCL 值設為 -1。如果您稍後決定要使用 EOP，請務必移除此郵件流程規則。

- **開啟使用者的回報郵件增益集**：我們強烈建議您[為使用者啟用回報郵件增益集](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)。

- **使用[提交總管](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)**：系統管理員現在可以使用檔案或網路訊息 ID、URL 以及 Microsoft Office 365 掃描的檔案來傳送電子郵件。 身為系統管理員，您也能夠檢視使用者傳送的意見反應，並使用任何模式來調整任何可能造成問題的設定。

- **確認您的使用者在傳送及接收電子郵件允許的限制內**，如[這裡](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)所示。

- **仔細檢查大量層級**，如[這裡](https://docs.microsoft.com/microsoft-365/security/office-365-security/bulk-complaint-level-values)所指定。

### <a name="for-users"></a>適用於使用者

- **建立安全寄件者清單**：使用者可以在 [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065)，或 [Outlook 網頁版](https://go.microsoft.com/fwlink/p/?LinkId=294862) (之前稱為 Outlook Web App) 中，將來自他們信任的寄件者位址新增到其安全寄件者清單。 若要開始使用 Outlook 網頁版，請選擇 [設定]**** ![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> [選項]**** \> [封鎖或允許]****。 下圖顯示新增一些項目至安全寄件者清單的範例。

![在 Outlook 網頁版中新增安全寄件者](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)

EOP 將信任使用者的安全寄件者和收件者，但不會信任安全網域。 不管是透過 Outlook 網頁版新增的網域，或是使用目錄同步處理新增到 Outlook 並進行同步處理的網域，都是如此。

- **停用 Outlook 中的 SmartScreen 篩選**：如果您使用舊版 Outlook 電腦版用戶端，您應該要停用已中止的 SmartScreen 篩選功能。 如果啟用該功能，可能會造成誤判。 如果執行的是更新的 Outlook 電腦版用戶端，則不需要此程序。

## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a>疑難排解：即使 EOP 將郵件標示為非垃圾郵件，它仍然跑到垃圾郵件資料夾。

如果您的使用者在 Outlook 中啟用了「僅限安全清單：只有來自安全寄件者清單或安全收件者清單上的人員或網域所寄出的郵件才會傳送到您的收件匣」，除非寄件者位於收件者的安全寄件者清單中，否則所有電子郵件將進入垃圾郵件資料夾。無論 EOP 將郵件標示為非垃圾郵件，或是您在EOP 設定規則將郵件標示為非垃圾郵件，這個情況都會發生。

如果您是在 Outlook 網頁版中檢視郵件，則會顯示一個黃色安全提示，指出郵件位於垃圾郵件資料夾，因為寄件者不在收件者的安全寄件者清單中。

當您查看郵件標題，它可能包含 SFV:SKN (IP 允許或 ETR 允許) 或 SFV:NSPM (非垃圾郵件) 戳記，但郵件仍然被放在使用者的垃圾郵件資料夾中。郵件標題中不會有任何資訊顯示使用者已啟用「僅限安全清單」。因為使用者在 Outlook 中設定的「僅限安全清單」選項會覆寫 EOP 設定，所以會發生這個情況。

### <a name="to-verify-why-a-message-from-a-safe-sender-is-marked-as-non-spam-in-the-message-header-but-still-ends-up-in-the-users-junk-folder"></a>驗證為什麼來自安全寄件者的郵件在郵件標題中被標示為非垃圾郵件，但卻仍進入使用者的垃圾郵件資料夾

1. 若要了解如何連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。

2. 執行下列命令，檢視使用者的垃圾電子郵件組態設定：

  ```Powershell
  Get-MailboxJunkEmailConfiguration example@contoso.com | Format-List TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

- 如果 TrustedListsOnly 為 True，表示已啟用此設定。

- 如果 ContactsTrusted 為 True，表示使用者信任連絡人和安全寄件者。

- TrustedSendersAndDomains 會列出使用者安全寄件者清單的內容。

## <a name="eop-only-customers-use-directory-synchronization"></a>只使用 EOP 的客戶：使用目錄同步處理

如果您是只使用 EOP 的客戶，即您訂閱 EOP 服務以與內部部署 (Exchange) 電子郵件伺服器搭配使用，則應使用目錄同步處理將使用者設定與服務同步。這樣做可確保 EOP 信任您的安全寄件者清單。如需詳細資訊，請參閱[在 EOP 中管理郵件使用者](https://go.microsoft.com/fwlink/?LinkId=534098)中的「使用目錄同步處理來管理郵件使用者」。
