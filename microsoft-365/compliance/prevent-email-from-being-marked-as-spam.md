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
ms.openlocfilehash: 3c7c2c8b3a66c940612a28d54d847a1c273abe6e
ms.sourcegitcommit: 18b5f6e9913147cea911c0fd347fcd880fb86f17
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2019
ms.locfileid: "37167129"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a><span data-ttu-id="e7398-103">如何在 Office 365 中防止實際電子郵件被標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="e7398-103">How to prevent real email from being marked as spam in Office 365</span></span>

 <span data-ttu-id="e7398-104">**您的實際電子郵件將在 Office 365 中被標示為垃圾郵件嗎？請執行此動作。**</span><span class="sxs-lookup"><span data-stu-id="e7398-104">**Is your real email getting marked as spam in Office 365? Do this.**</span></span>

<span data-ttu-id="e7398-p101">如果發生誤判，您應使用[使用回報郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)向 Microsoft 回報該郵件。此外，您可以使用[提交總管](/security/office-365-security/admin-submission.md)來提交郵件。</span><span class="sxs-lookup"><span data-stu-id="e7398-p101">If you get a false positive, you should report the message to Microsoft by using the [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Additionally, you can forward the message [as an attachment](/security/office-365-security/admin-submission.md) to not_junk@office365.microsoft.com.</span></span>

## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a><span data-ttu-id="e7398-107">判斷郵件被標示為垃圾郵件的原因</span><span class="sxs-lookup"><span data-stu-id="e7398-107">Determine the reason why the message was marked as spam</span></span>

<span data-ttu-id="e7398-p102">您可以[檢視電子郵件訊息標頭](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)並判定發生何種問題，來解決 Office 365 中的許多垃圾郵件問題。您需要尋找名為 X-Forefront-Antispam-Report 的標頭。您可以[深入了解反垃圾郵件標頭](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e7398-p102">Many issues with spam in Office 365 can be resolved by [View e-mail message headers](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) and determining what went wrong. You will need to look for a header named X-Forefront-Antispam-Report. You can [learn more about anti-spam message headers](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="e7398-111">在標頭中，尋找下列標題和值。</span><span class="sxs-lookup"><span data-stu-id="e7398-111">In the header, look for the following headings and values.</span></span>

### <a name="x-forefront-antispam-report"></a><span data-ttu-id="e7398-112">X-Forefront-Antispam-Report</span><span class="sxs-lookup"><span data-stu-id="e7398-112">X-Forefront-Antispam-Report</span></span>

- <span data-ttu-id="e7398-113">**SFV:SPM**：表示郵件已因 EOP 垃圾郵件篩選而標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="e7398-113">**SFV:SPM** Indicates that the message was marked as spam because of the EOP spam filters.</span></span>

- <span data-ttu-id="e7398-114">**SFV:BLK**：表示郵件已標示為垃圾郵件，因為寄件地址是在收件者封鎖的寄件者清單上。</span><span class="sxs-lookup"><span data-stu-id="e7398-114">**SFV:BLK** Indicates that the message was marked as spam because the sending address is on the recipient's Blocked Senders List.</span></span>

- <span data-ttu-id="e7398-115">**SFV:SKS**：表示該郵件在進入內容篩選器之前就已標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="e7398-115">**SFV:SKS**: Indicates that the message was marked as spam prior to the content filter.</span></span> <span data-ttu-id="e7398-116">這可能包括將郵件標示為垃圾郵件的郵件流程規則 (也稱為傳輸規則)。</span><span class="sxs-lookup"><span data-stu-id="e7398-116">This could include a mail flow rule (also known as a transport rule) marking the message as spam.</span></span> <span data-ttu-id="e7398-117">請執行訊息追蹤來查看它是否觸發了設定為高垃圾郵件信賴等級 (SCL) 的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="e7398-117">Run a message trace to see if a mail flow rule triggered which may have set a high spam confidence level (SCL).</span></span>

- <span data-ttu-id="e7398-118">**SFV:SKB**：表示郵件已標示為垃圾郵件，因為它符合垃圾郵件篩選原則中的封鎖清單。</span><span class="sxs-lookup"><span data-stu-id="e7398-118">**SFV:SKB** Indicates that the message was marked as spam because it matched a block list in the spam filter policy.</span></span>

- <span data-ttu-id="e7398-119">**SFV:BULK**：表示 x-microsoft-antispam 標頭中的大量抱怨層級 (BCL) 值超過已針對內容篩選設定的大量閾值。</span><span class="sxs-lookup"><span data-stu-id="e7398-119">**SFV:BULK**: Indicates that the Bulk Complaint Level (BCL) value located in the x-microsoft-antispam header is above the Bulk threshold that has been set for the content filter.</span></span> <span data-ttu-id="e7398-120">大量電子郵件可能是由使用者自己註冊的，但也可能是不想要的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e7398-120">Bulk email is email which users may have signed up for, but may still be undesirable.</span></span> <span data-ttu-id="e7398-121">請在郵件標頭中，尋找 X-Microsoft-Antispam 標頭中的 BCL (大量信賴等級) 屬性。</span><span class="sxs-lookup"><span data-stu-id="e7398-121">In the message header find the BCL (Bulk Confidence Level) property in the X-Microsoft-Antispam header.</span></span> <span data-ttu-id="e7398-122">如果 BCL 值小於 [垃圾郵件篩選] 中設定的閾值，建議您調整閥值，而不要將這類大量郵件標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="e7398-122">If the BCL value is less than the threshold set in the Spam Filter, you may want to adjust the threshold to instead mark these types of bulk messages as spam.</span></span> <span data-ttu-id="e7398-123">不同的使用者在如何處理[大量電子郵件](https://docs.microsoft.com/microsoft-365/security/office-365-security/bulk-complaint-level-values)的方式上會有不同的標準及喜好。</span><span class="sxs-lookup"><span data-stu-id="e7398-123">Different users have different tolerances and preferences for [how bulk email is handled](https://docs.microsoft.com/microsoft-365/security/office-365-security/bulk-complaint-level-values).</span></span> <span data-ttu-id="e7398-124">您可以為不同的使用者偏好建立不同的原則或規則。</span><span class="sxs-lookup"><span data-stu-id="e7398-124">You can create different policies or rules for different user preferences.</span></span>

- <span data-ttu-id="e7398-125">**CAT:SPOOF** 或 **CAT:PHISH**：表示該郵件似乎受到冒名，意即其來源無法受到系統驗證，且可能為可疑來源。</span><span class="sxs-lookup"><span data-stu-id="e7398-125">**CAT:SPOOF** or **CAT:PHISH**: Indicates that the message appears to be spoofed, meaning that the message source cannot be validated and could be suspicious.</span></span> <span data-ttu-id="e7398-126">如果為正確郵件，寄件者將需要確認其 SPF 及 DKIM 設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="e7398-126">If valid, the sender will need to make sure that they have proper SPF and DKIM configuration.</span></span> <span data-ttu-id="e7398-127">如需詳細資訊，請查看 Authentication-Results 標頭。</span><span class="sxs-lookup"><span data-stu-id="e7398-127">Check the Authentication-Results header for more information.</span></span> <span data-ttu-id="e7398-128">雖然要讓所有的寄件者都使用正確的電子郵件驗證方法並不容易，但略過這些檢查非常危險，且是造成風險的主要原因。</span><span class="sxs-lookup"><span data-stu-id="e7398-128">Although it may be difficult to get all senders to use proper email authentication methods, bypassing these checks can be extremely dangerous and is the top cause of compromises.</span></span>

### <a name="x-customspam"></a><span data-ttu-id="e7398-129">x-customspam</span><span class="sxs-lookup"><span data-stu-id="e7398-129">x-customspam</span></span>

- <span data-ttu-id="e7398-p106">若出現此標頭，表示郵件已標示為垃圾郵件，因為已在您的垃圾郵件篩選器中啟用其中一個[進階垃圾郵件選項](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx)。除非您需要這些功能，否則我們建議您使用預設設定。</span><span class="sxs-lookup"><span data-stu-id="e7398-p106">The presence of this header indicates that the message was marked as spam because one of the [advanced spam options is enabled](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) in your spam filter. Unless you need these features, we recommend that you use the default settings.</span></span>

## <a name="solutions-to-additional-causes-of-too-much-spam"></a><span data-ttu-id="e7398-132">造成太多垃圾郵件之其他原因的解決方案</span><span class="sxs-lookup"><span data-stu-id="e7398-132">Solutions to additional causes of too much spam</span></span>

<span data-ttu-id="e7398-p107">若要有效地運作，Exchange Online Protection (EOP) 需要系統管理員完成一些工作。如果您不是 Office 365 租用戶的系統管理員，而且收到太多垃圾郵件，則您可能會想要與您的系統管理員合作處理這些工作。否則，您可以跳至使用者區段。</span><span class="sxs-lookup"><span data-stu-id="e7398-p107">In order to work effectively, Exchange Online Protection (EOP) requires that administrators complete a few tasks. If you are not the administrator for your Office 365 tenant and you are getting too much spam, then you may want to work with your administrator on these tasks. Otherwise, you can skip to the user section.</span></span>

### <a name="for-admins"></a><span data-ttu-id="e7398-136">適用於系統管理員</span><span class="sxs-lookup"><span data-stu-id="e7398-136">For admins</span></span>

- <span data-ttu-id="e7398-137">**將您的 DNS 記錄指向 Office 365**：為了讓 EOP 提供保護，您在所有網域的郵件交換程式 (MX) DNS 記錄都必須指向 (且只能指向) Office 365。</span><span class="sxs-lookup"><span data-stu-id="e7398-137">**Point your DNS records to Office 365** In order for EOP to provide the best protection, your mail exchanger (MX) DNS record(s) for all domains must be pointed to Office 365 -- and only to Office 365. See Create DNS records for Office 365 when you manage your DNS records.</span></span> <span data-ttu-id="e7398-138">如果您的 MX 未指向 Office 365，那麼 EOP 將無法為您的使用者提供垃圾郵件篩選服務。</span><span class="sxs-lookup"><span data-stu-id="e7398-138">If your MX does not point to Office 365, then EOP will not provide spam filtering for your users.</span></span> <span data-ttu-id="e7398-139">當您想要使用另一個服務或設備來提供您的網域垃圾郵件篩選功能時，請考慮停用 EOP 中的垃圾郵件防護機制。</span><span class="sxs-lookup"><span data-stu-id="e7398-139">In the situation where you wish to use another service or appliance to provide spam filtering for your domain, you should consider disabling the spam protection in EOP.</span></span> <span data-ttu-id="e7398-140">若要這麼做，您可以建立郵件流程規則，來將 SCL 值設為 -1。</span><span class="sxs-lookup"><span data-stu-id="e7398-140">You can do this by creating a mail flow rule that sets the SCL value to -1.</span></span> <span data-ttu-id="e7398-141">如果您稍後決定要使用 EOP，請務必移除此郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="e7398-141">If you later decide to use EOP, make sure to remove this mail flow rule.</span></span>

- <span data-ttu-id="e7398-142">**開啟使用者的回報郵件增益集**：我們強烈建議您[為使用者啟用回報郵件增益集](/security/office-365-security/enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="e7398-142">**Turn on the report message add-in for users** We strongly recommend that you [enable the report message add-in for you users](/security/office-365-security/enable-the-report-message-add-in.md). As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.</span></span>

- <span data-ttu-id="e7398-143">**使用[提交總管](/security/office-365-security/admin-submission.md)**：系統管理員現在可以使用檔案或網路訊息 ID、URL 以及 Microsoft Office 365 掃描的檔案來傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e7398-143">**Use [Submissions Explorer](/security/office-365-security/admin-submission.md)**: Admins can now send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span> <span data-ttu-id="e7398-144">身為系統管理員，您也能夠檢視使用者傳送的意見反應，並使用任何模式來調整任何可能造成問題的設定。</span><span class="sxs-lookup"><span data-stu-id="e7398-144">Turn on the report message add-in for users We strongly recommend that you enable the report message add-in for your users. As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.</span></span>

- <span data-ttu-id="e7398-145">**確認您的使用者在傳送及接收電子郵件允許的限制內**，如[這裡](https://docs.microsoft.com/zh-TW/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)所示。</span><span class="sxs-lookup"><span data-stu-id="e7398-145">**Make sure that your users are inside the allowed limits** for sending and receiving emails as showed [here](https://docs.microsoft.com/zh-TW/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

- <span data-ttu-id="e7398-146">**仔細檢查大量層級**，如[這裡](/security/office-365-security/bulk-complaint-level-values.md)所指定。</span><span class="sxs-lookup"><span data-stu-id="e7398-146">**Double-check the bulk levels** as specified [here](/security/office-365-security/bulk-complaint-level-values.md)</span></span>

### <a name="for-users"></a><span data-ttu-id="e7398-147">若為使用者</span><span class="sxs-lookup"><span data-stu-id="e7398-147">For users</span></span>

- <span data-ttu-id="e7398-p110">**建立安全寄件者清單**：使用者可從將他們所信任的寄件者地址新增到 [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) 或 [Outlook 網頁版](https://go.microsoft.com/fwlink/p/?LinkId=294862) (之前稱為 Outlook Web App) 中的安全寄件者清單。若要開始使用 Outlook 網頁版，請選擇 [設定]\*\*\*\*![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \>[選項]\*\*\*\* \> [封鎖或允許]\*\*\*\*。下列圖表顯示新增某項目到安全寄件者清單的範例。</span><span class="sxs-lookup"><span data-stu-id="e7398-p110">**Create a safe sender list** Users can add addresses from senders that they trust to their safe sender list in [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) or [Outlook on the Web](https://go.microsoft.com/fwlink/p/?LinkId=294862). To get started in Outlook on the Web, choose **Settings**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Options** \> **Block or allow**. The following diagram shows an example of adding something to a safe sender list.</span></span>

![在 Outlook 網頁版中新增安全寄件者](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)

<span data-ttu-id="e7398-p111">EOP 將信任使用者的安全寄件者人和收件人，但不會信任安全的網域。不管是透過 Outlook 網頁版新增的網域，或是使用目錄同步處理新增到 Outlook 並進行同步處理的網域，都是如此。</span><span class="sxs-lookup"><span data-stu-id="e7398-p111">EOP will honor your users' Safe Senders and Recipients, but not Safe Domains. This is true regardless of whether the domain is added through the Outlook on the Web, or added in Outlook and synchronized using Directory Sync.</span></span>

- <span data-ttu-id="e7398-p112">**停用 Outlook 中的 SmartScreen 篩選**：如果您使用舊版 Outlook 桌面用戶端，您應該停用已終止的 SmartScreen 篩選功能。啟用將會造成誤判。如果執行已更新的桌面 Outlook 用戶端，並不需要此功能。</span><span class="sxs-lookup"><span data-stu-id="e7398-p112">**Disable SmartScreen filtering in Outlook** If you are using an older Outlook desktop client, you should disable the SmartScreen filtering functionality, which has been discontinued. If enabled, it can cause false positives. This should not be required if running an updated desktop Outlook client.</span></span>

## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a><span data-ttu-id="e7398-157">疑難排解：即使 EOP 將郵件標示為非垃圾郵件，它仍然跑到垃圾郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="e7398-157">Troubleshooting: A message ends up in the Junk folder even though EOP marked the message as non-spam</span></span>

<span data-ttu-id="e7398-p113">如果您的使用者在 Outlook 中啟用了「僅限安全清單：只有來自安全寄件者清單或安全收件者清單上的人員或網域所寄出的郵件才會傳送到您的收件匣」，除非寄件者位於收件者的安全寄件者清單中，否則所有電子郵件將進入垃圾郵件資料夾。無論 EOP 將郵件標示為非垃圾郵件，或是您在EOP 設定規則將郵件標示為非垃圾郵件，這個情況都會發生。</span><span class="sxs-lookup"><span data-stu-id="e7398-p113">If your users have the option in Outlook enabled for "Safe Lists Only: Only mail from people or domains on your Safe Senders list or Safe Recipients List will be delivered to your Inbox", then all email will go to the junk folder for a sender unless the sender is on the recipient's Safe Sender list. This will happen regardless of whether EOP marks a message as non-spam, or if you have set up a rule in EOP to mark a message as non-spam.</span></span>

<span data-ttu-id="e7398-160">您可以遵照 [Outlook：可停用垃圾電子郵件 UI 和篩選機制的原則設定](https://support.microsoft.com/zh-TW/kb/2180568) 中的指示，為您的 Outlook 使用者停用 [僅限安全清單] 選項。</span><span class="sxs-lookup"><span data-stu-id="e7398-160">You can disable the Safe Lists Only option for your Outlook users by following the instructions in [Outlook: Policy setting to disable the Junk E-mail UI and filtering mechanism](https://support.microsoft.com/zh-TW/kb/2180568).</span></span>

<span data-ttu-id="e7398-161">如果您是在 Outlook 網頁版中查看郵件，則會顯示一個黃色安全提示，指出郵件位於垃圾郵件資料夾，因為寄件者不在收件者的安全寄件者清單中。</span><span class="sxs-lookup"><span data-stu-id="e7398-161">If you view the message in Outlook on the Web, there will be a yellow safety tip that indicates that the message is in the Junk folder because the sender is not on the recipient's Safe Senders list.</span></span>

<span data-ttu-id="e7398-p114">當您查看郵件標題，它可能包含 SFV:SKN (IP 允許或 ETR 允許) 或 SFV:NSPM (非垃圾郵件) 戳記，但郵件仍然被放在使用者的垃圾郵件資料夾中。郵件標題中不會有任何資訊顯示使用者已啟用「僅限安全清單」。因為使用者在 Outlook 中設定的「僅限安全清單」選項會覆寫 EOP 設定，所以會發生這個情況。</span><span class="sxs-lookup"><span data-stu-id="e7398-p114">If you look at the header of a message, it may include the stamp SFV:SKN (IP Allow or ETR Allow) or SFV:NSPM (non-spam), but the message is still placed in the user's junk folder. There is nothing in the message header that indicates that the user has "Safe Lists Only" enabled. This happens because the "Safe Lists Only" option set by users in Outlook overrides the EOP setting.</span></span>

### <a name="to-verify-why-a-message-from-a-safe-sender-is-marked-as-non-spam-in-the-message-header-but-still-ends-up-in-the-users-junk-folder"></a><span data-ttu-id="e7398-165">驗證為什麼來自安全寄件者的郵件在郵件標題中被標示為非垃圾郵件，但卻仍進入使用者的垃圾郵件資料夾</span><span class="sxs-lookup"><span data-stu-id="e7398-165">To verify why a message from a safe sender is marked as non-spam in the message header, but still ends up in the user's Junk folder</span></span>

1. <span data-ttu-id="e7398-166">若要了解如何連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="e7398-166">To learn how to connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>

2. <span data-ttu-id="e7398-167">執行下列命令，檢視使用者的垃圾電子郵件組態設定：</span><span class="sxs-lookup"><span data-stu-id="e7398-167">Run the following command to view the user's junk email configuration settings:</span></span>

  ```Powershell
  Get-MailboxJunkEmailConfiguration example@contoso.com | Format-List TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

- <span data-ttu-id="e7398-168">如果 TrustedListsOnly 為 True，表示已啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="e7398-168">If TrustedListsOnly is set to True, it means that this setting is enabled</span></span>

- <span data-ttu-id="e7398-169">如果 ContactsTrusted 為 True，表示使用者信任連絡人和安全寄件者。</span><span class="sxs-lookup"><span data-stu-id="e7398-169">If ContactsTrusted is set to True, it means that the user trusts both Contacts and Safe Senders</span></span>

- <span data-ttu-id="e7398-170">TrustedSendersAndDomains 會列出使用者安全寄件者清單的內容。</span><span class="sxs-lookup"><span data-stu-id="e7398-170">The TrustedSendersAndDomains lists the contents of the user's Safe Senders list</span></span>

## <a name="eop-only-customers-use-directory-synchronization"></a><span data-ttu-id="e7398-171">只使用 EOP 的客戶：使用目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="e7398-171">EOP-only customers: use directory synchronization</span></span>

<span data-ttu-id="e7398-p115">如果您是只使用 EOP 的客戶，即您訂閱 EOP 服務以與內部部署 (Exchange) 電子郵件伺服器搭配使用，則應使用目錄同步處理將使用者設定與服務同步。這樣做可確保 EOP 信任您的安全寄件者清單。如需詳細資訊，請參閱[在 EOP 中管理郵件使用者](https://go.microsoft.com/fwlink/?LinkId=534098)中的「使用目錄同步處理來管理郵件使用者」。</span><span class="sxs-lookup"><span data-stu-id="e7398-p115">If you're an EOP-only customer, that is, you subscribe to the EOP service for use with your on-premises (Exchange) email server, you should sync user settings with the service by using directory synchronization. Doing this ensures that your safe senders lists are respected by EOP. For more information, see "Use directory synchronization to manage mail users" in [Manage Mail Users in EOP](https://go.microsoft.com/fwlink/?LinkId=534098).</span></span>
