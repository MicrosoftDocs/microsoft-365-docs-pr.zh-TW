---
title: 威脅總管和即時偵測, 威脅總管新功能, 威脅總管變更, Office 365 新功能, 安全性, 雲端安全性, ATP 安全性新功能, ATP 新功能
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 深入了解安全性與合規性中心的總管和即時偵測。
ms.openlocfilehash: 3ddcaf4dc457ead7a203e00d71d0d18c23ee6557
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082095"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="3bd93-103">威脅總管和即時偵測</span><span class="sxs-lookup"><span data-stu-id="3bd93-103">Threat Explorer and real-time detections</span></span>

<span data-ttu-id="3bd93-104">如果貴組織具有 [Office 365 進階威脅防護](office-365-atp.md) (Office 365 ATP)，而且您具有[必要的權限](#required-licenses-and-permissions)，您具有**總管**或**即時偵測** (先前的*即時報告* — [查看新增功能](#new-features-in-threat-explorer-and-real-time-detections)！)。</span><span class="sxs-lookup"><span data-stu-id="3bd93-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly *real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="3bd93-105">在安全性與合規性中心， 移至**威脅管理**，然後選擇**總管**或**即時偵測**。</span><span class="sxs-lookup"><span data-stu-id="3bd93-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** OR **Real-time detections**.</span></span> 

|<span data-ttu-id="3bd93-106">在 ATP 方案 2，您會看到：</span><span class="sxs-lookup"><span data-stu-id="3bd93-106">With ATP Plan 2, you see:</span></span>  |<span data-ttu-id="3bd93-107">在 ATP 方案 1，您會看到：</span><span class="sxs-lookup"><span data-stu-id="3bd93-107">With ATP Plan 1, you see:</span></span>  |
|---------|---------|
|![威脅總管](../../media/threatmgmt-explorer.png)      |![即時偵測](../../media/threatmgmt-realtimedetections.png)         |

<span data-ttu-id="3bd93-110">總管 (或即時偵測) 提供您強大的報告，讓您的安全性作業小組以有效的方式調查及回應威脅。</span><span class="sxs-lookup"><span data-stu-id="3bd93-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently.</span></span> <span data-ttu-id="3bd93-111">報告類似下列影像：</span><span class="sxs-lookup"><span data-stu-id="3bd93-111">The report resembles the following image:</span></span> 

![移至威脅管理 \> 總管](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="3bd93-113">您可以使用此報告：</span><span class="sxs-lookup"><span data-stu-id="3bd93-113">With this report, you can:</span></span>
- [<span data-ttu-id="3bd93-114">查看 Office 365 安全性功能偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="3bd93-114">See malware detected by Office 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="3bd93-115">檢視網路釣魚 URL 並按一下結果</span><span class="sxs-lookup"><span data-stu-id="3bd93-115">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- <span data-ttu-id="3bd93-116">[從總管中的檢視啟動自動化的調查和回應程序](#start-automated-investigation-and-response) (僅限 ATP 方案 2)</span><span class="sxs-lookup"><span data-stu-id="3bd93-116">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="3bd93-117">... [調查惡意電子郵件等功能](#more-ways-to-use-explorer-or-real-time-detections)！</span><span class="sxs-lookup"><span data-stu-id="3bd93-117">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="3bd93-118">威脅總管和即時偵測的新功能</span><span class="sxs-lookup"><span data-stu-id="3bd93-118">New features in Threat Explorer and real-time detections</span></span>

<span data-ttu-id="3bd93-119">威脅總管和即時偵測新增了三個新功能：</span><span class="sxs-lookup"><span data-stu-id="3bd93-119">Three new features added into Threat Explorer and real-time detections:</span></span>
- [<span data-ttu-id="3bd93-120">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="3bd93-120">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="3bd93-121">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="3bd93-121">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="3bd93-122">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="3bd93-122">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="3bd93-123">新功能如下所列。</span><span class="sxs-lookup"><span data-stu-id="3bd93-123">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="3bd93-124">預覽電子郵件標頭和下載電子郵件內文</span><span class="sxs-lookup"><span data-stu-id="3bd93-124">Preview email header and download email body</span></span>

<span data-ttu-id="3bd93-125">預覽電子郵件標頭和下載電子郵件內文能力為威脅總管提供的新功能。</span><span class="sxs-lookup"><span data-stu-id="3bd93-125">The ability to preview an email header and download the email body are new features available in Threat Explorer.</span></span> <span data-ttu-id="3bd93-126">系統管理員將能分析下載的標頭/電子郵件訊息是否存在威脅。</span><span class="sxs-lookup"><span data-stu-id="3bd93-126">Admins will be able to analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="3bd93-127">由於下載電子郵件訊息可能有資訊暴露的風險，此程序是由角色型存取控制 (RBAC) 來控制。</span><span class="sxs-lookup"><span data-stu-id="3bd93-127">Because downloading email messages can risk the exposure of information, this process is controlled by roles-based access control (RBAC).</span></span> <span data-ttu-id="3bd93-128">必須將新角色*預覽*新增至另一個 Office 365 角色群組 (例如，新增至安全性作業或安全性系統管理員) 以授與能力來下載郵件，並以所有電子郵件檢視來預覽標頭。</span><span class="sxs-lookup"><span data-stu-id="3bd93-128">A new role, *Preview*, must be added to another Office 365 role group (such as Security Operations or Security Administrator) to grant the ability to download mails and preview headers in all-email messages view.</span></span>

<span data-ttu-id="3bd93-129">但總管 (和即時偵測) 也會新增新欄位，設計用於提供您更完整的電子郵件訊息目標位置資訊。</span><span class="sxs-lookup"><span data-stu-id="3bd93-129">But Explorer (and real-time detections) also adds fresh new fields designed to give you a more complete picture of where your email messages land.</span></span> <span data-ttu-id="3bd93-130">這項變更的部分目標是讓安全性作業人員更容易搜捕，但最後的結果在於對問題電子郵件訊息的位置一目了然。</span><span class="sxs-lookup"><span data-stu-id="3bd93-130">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="3bd93-131">這是如何達成？</span><span class="sxs-lookup"><span data-stu-id="3bd93-131">How is this done?</span></span> <span data-ttu-id="3bd93-132">傳遞狀態現在劃分為兩個資料行：</span><span class="sxs-lookup"><span data-stu-id="3bd93-132">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="3bd93-133">**傳遞動作** - 這封電子郵件的狀態為何？</span><span class="sxs-lookup"><span data-stu-id="3bd93-133">**Delivery Action** - What is the status of this email?</span></span>
- <span data-ttu-id="3bd93-134">**傳遞位置** - 結果這封電子郵件是如何路由傳送？</span><span class="sxs-lookup"><span data-stu-id="3bd93-134">**Delivery Location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="3bd93-135">「傳遞動作」是基於現有原則或偵測對電子郵件所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="3bd93-135">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="3bd93-136">以下是電子郵件可能採取的動作：</span><span class="sxs-lookup"><span data-stu-id="3bd93-136">Here are the possible actions an email can take:</span></span>

|<span data-ttu-id="3bd93-137">已傳遞</span><span class="sxs-lookup"><span data-stu-id="3bd93-137">Delivered</span></span>  |<span data-ttu-id="3bd93-138">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="3bd93-138">Junked</span></span>  |<span data-ttu-id="3bd93-139">已封鎖</span><span class="sxs-lookup"><span data-stu-id="3bd93-139">Blocked</span></span>  |<span data-ttu-id="3bd93-140">已取代</span><span class="sxs-lookup"><span data-stu-id="3bd93-140">Replaced</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="3bd93-141">電子郵件已傳遞至使用者的收件匣或其他資料夾，使用者可以直接存取。</span><span class="sxs-lookup"><span data-stu-id="3bd93-141">Email was delivered to the user's inbox or another folder, and the user can directly access it.</span></span>    | <span data-ttu-id="3bd93-142">電子郵件已傳送至使用者的垃圾郵件資料夾或刪除的郵件] 資料夾中，且使用者可以存取電子郵件訊息在這些資料夾中。</span><span class="sxs-lookup"><span data-stu-id="3bd93-142">Email was sent to either user's Junk folder or Deleted folder, and the user has access to email messages in those folders.</span></span>       | <span data-ttu-id="3bd93-143">任何已隔離、傳遞失敗或已捨棄的電子郵件，使用者均無法存取。</span><span class="sxs-lookup"><span data-stu-id="3bd93-143">Any email messages that are quarantined, that failed, or were dropped, and are not accessible by the user.</span></span>     | <span data-ttu-id="3bd93-144">以 .txt 檔案替換為惡意附件的任何電子郵件訊息，均指出附件是惡意的。</span><span class="sxs-lookup"><span data-stu-id="3bd93-144">Any email messages where malicious attachments were replaced by .txt files that state the attachments were malicious.</span></span>     |

<span data-ttu-id="3bd93-145">以下是使用者可以查看及無法查看的內容：</span><span class="sxs-lookup"><span data-stu-id="3bd93-145">And here is what the user can see, and what they can't:</span></span>

|<span data-ttu-id="3bd93-146">使用者可以存取</span><span class="sxs-lookup"><span data-stu-id="3bd93-146">Accessible to end users</span></span>  |<span data-ttu-id="3bd93-147">使用者無法存取 </span><span class="sxs-lookup"><span data-stu-id="3bd93-147">Inaccessible to end users</span></span>  |
|---------|---------|
|<span data-ttu-id="3bd93-148">已傳遞</span><span class="sxs-lookup"><span data-stu-id="3bd93-148">Delivered</span></span>     | <span data-ttu-id="3bd93-149">已封鎖</span><span class="sxs-lookup"><span data-stu-id="3bd93-149">Blocked</span></span>        |
|<span data-ttu-id="3bd93-150">已標示為垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="3bd93-150">Junked</span></span>     | <span data-ttu-id="3bd93-151">已取代</span><span class="sxs-lookup"><span data-stu-id="3bd93-151">Replaced</span></span>        |

<span data-ttu-id="3bd93-152">傳遞位置顯示原則和執行傳遞後偵測的結果。</span><span class="sxs-lookup"><span data-stu-id="3bd93-152">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="3bd93-153">其連結到「傳遞動作」。</span><span class="sxs-lookup"><span data-stu-id="3bd93-153">It's linked to a Delivery Action.</span></span> <span data-ttu-id="3bd93-154">已新增此欄位，以深入了解找到問題電子郵件時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="3bd93-154">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="3bd93-155">以下是傳遞位置可能的值：</span><span class="sxs-lookup"><span data-stu-id="3bd93-155">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="3bd93-156">**收件匣或資料夾**：電子郵件位於收件匣或資料夾中 (根據您的電子郵件規則)。</span><span class="sxs-lookup"><span data-stu-id="3bd93-156">**Inbox or folder**: The email is in inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="3bd93-157">**在內部或外部**： 信箱不存在於雲端上，但會在內部。</span><span class="sxs-lookup"><span data-stu-id="3bd93-157">**On-prem or external**: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="3bd93-158">**垃圾郵件資料夾**：電子郵件位於使用者的 [垃圾郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="3bd93-158">**Junk folder**: The email is in the Junk folder of a user.</span></span>
- <span data-ttu-id="3bd93-159">**刪除的郵件資料夾**：電子郵件位於使用者的 [刪除的郵件] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="3bd93-159">**Deleted items folder**: The email in the Deleted items folder of a user.</span></span>
- <span data-ttu-id="3bd93-160">**隔離**： 隔離中的電子郵件以及不在使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="3bd93-160">**Quarantine**: The email in quarantine, and is not in a user's mailbox.</span></span>
- <span data-ttu-id="3bd93-161">**失敗**；電子郵件無法傳遞至信箱。</span><span class="sxs-lookup"><span data-stu-id="3bd93-161">**Failed**: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="3bd93-162">**已捨棄**：電子郵件在郵件流程的某處遺失。</span><span class="sxs-lookup"><span data-stu-id="3bd93-162">**Dropped**: The email gets lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="3bd93-163">電子郵件時間表</span><span class="sxs-lookup"><span data-stu-id="3bd93-163">Email timeline</span></span>

<span data-ttu-id="3bd93-164">**電子郵件時間表**是總管的另一個新功能，目標是提升系統管理員的搜捕體驗。</span><span class="sxs-lookup"><span data-stu-id="3bd93-164">The **Email Timeline** is another new Explorer feature aimed at making the hunting experience better for admins.</span></span> <span data-ttu-id="3bd93-165">這可減少不規則性，因為花較少的時間檢查不同位置以嘗試了解事件。</span><span class="sxs-lookup"><span data-stu-id="3bd93-165">It cuts down on randomization because there is less time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="3bd93-166">當多個事件同時或接近同時發生在某電子郵件時，這些事件會出現在時刻表檢視。</span><span class="sxs-lookup"><span data-stu-id="3bd93-166">When multiple events happen at, or close to, the same time on an email, those events will show up in a timeline view.</span></span> <span data-ttu-id="3bd93-167">事實上，某些在傳遞郵件後發生的事件會由「特殊動作」欄擷取。</span><span class="sxs-lookup"><span data-stu-id="3bd93-167">In fact, some events that happen post-delivery to your mail will be captured in the 'Special action' column.</span></span> <span data-ttu-id="3bd93-168">透過結合該郵件在時間表的資訊和傳遞郵件後採取的特殊動作，能讓系統管理員深入了解其原則的運作方式、郵件最後路由傳送的位置，以及在某些情況下最終評估的內容。</span><span class="sxs-lookup"><span data-stu-id="3bd93-168">Combining the information from the timeline of that mail with the special action taken on the mail post-delivery will give admins insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="3bd93-169">如需調查惡意電子郵件訊息的詳細討論，請參閱[尋找並調查在 Office 365 傳送的惡意電子郵件](https://docs.microsoft.com/office365/securitycompliance/investigate-malicious-email-that-was-delivered) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="3bd93-169">For more discussion about investigating malicious email messages, see [Find and investigate malicious email that was delivered in Office 365](https://docs.microsoft.com/office365/securitycompliance/investigate-malicious-email-that-was-delivered).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="3bd93-170">匯出 URL 點擊資料</span><span class="sxs-lookup"><span data-stu-id="3bd93-170">Export URL click data</span></span>

<span data-ttu-id="3bd93-171">此外，您現在可以將 URL 點選的報告匯出到 Microsoft Excel 中，以便檢視其 [網路郵件識別碼] 以及 [按一下結果]，從而更容易了解 URL 點擊流量的來源。</span><span class="sxs-lookup"><span data-stu-id="3bd93-171">Also, you will now be able to export reports for URL clicks to Microsoft Excel in order to view both their Network Message ID, and their Click Verdict, making the task of understanding where your URL click traffic originated easier.</span></span> <span data-ttu-id="3bd93-172">以下說明運作方式。</span><span class="sxs-lookup"><span data-stu-id="3bd93-172">Here's how it works.</span></span> <span data-ttu-id="3bd93-173">在 Office 365 的威脅管理快速啟動中開啟，按一下此鏈結：</span><span class="sxs-lookup"><span data-stu-id="3bd93-173">Starting in Threat Management on the Office 365 quick-launch, click through this chain:</span></span>

<span data-ttu-id="3bd93-174">\*\*總管 \*\* > \*\* 檢視網路釣魚 \*\* > **按一下 \*\* > \*\* 熱門 URLs 或熱門 URL 點擊 \*\* > \*\* 按一下任何記錄以開起 URL 飛出視窗**</span><span class="sxs-lookup"><span data-stu-id="3bd93-174">**Explorer** > **View Phish** > **Clicks** > **Top URLs or URL Top Clicks** > **Click on any record to open URL flyout**</span></span>

<span data-ttu-id="3bd93-175">當您按一下清單中的 URL 時，將會在飛出面版上看到新的 [匯出] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3bd93-175">When you click on a URL in the list, you'll see a new Export button on the fly-out panel.</span></span> <span data-ttu-id="3bd93-176">使用此按鈕將資料移至 Excel 試算表，以便更輕鬆地進行報告。</span><span class="sxs-lookup"><span data-stu-id="3bd93-176">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="3bd93-177">您可以在即時偵測報告中取得相同的位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3bd93-177">You can get to the same location in the real-time detections report as follows:</span></span>

<span data-ttu-id="3bd93-178">\*\*總管 \*\* > \*\* 即時偵測 \*\* > \*\* 檢視網路釣魚 \*\* > \*\* URL \*\* > \*\* 熱門 URL 或熱門點選 \*\* > **按一下任何記錄以開啟 URL 飛出視窗 \*\* > \*\* 瀏覽至按一下索引標籤。**</span><span class="sxs-lookup"><span data-stu-id="3bd93-178">**Explorer** > **Real-time Detections** > **View Phish** > **URLs** > **Top URLs or Top Clicks** > **Click on any record to open URL flyout** > **Navigate to the Clicks Tab.**</span></span>

> [!TIP]
> <span data-ttu-id="3bd93-179">當您透過網路郵件識別碼在總管或關聯的協力廠商工具中進行搜尋時，網路郵件識別碼會將點擊返回對應到特定的郵件。</span><span class="sxs-lookup"><span data-stu-id="3bd93-179">Network Message ID maps the click back to specific mails when you search through Explorer or associated 3rd party tools via Network Message ID.</span></span> <span data-ttu-id="3bd93-180">搜尋網路郵件識別碼時，系統會提供系統管理員與點擊結果相關聯的特定電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3bd93-180">Searching through the Network Message ID will give admins the specific email associated with a click result.</span></span> <span data-ttu-id="3bd93-181">匯出時，網路郵件識別碼的關聯識別可提供更快且更強大的分析。</span><span class="sxs-lookup"><span data-stu-id="3bd93-181">On export having, the correlating identification of Network Message ID makes for quicker and more powerful analysis.</span></span>

![tp_ExportClickResultAndNetworkID.png](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="3bd93-183">查看透過技術在電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="3bd93-183">See malware detected in email by technology</span></span>

<span data-ttu-id="3bd93-184">假設您想要查看 Office 365 技術在電子郵件中偵測到的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="3bd93-184">Suppose you want to see malware detected in email, by Office 365 technology.</span></span> <span data-ttu-id="3bd93-185">若要這麼做，請使用總管 (或即時偵測) 的 [[電子郵件] > [惡意程式碼]](threat-explorer-views.md#email--malware) 檢視。</span><span class="sxs-lookup"><span data-stu-id="3bd93-185">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="3bd93-186">在安全性與合規性中心 ([https://protection.office.com](https://protection.office.com)) 選擇 **[威脅管理]** > **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="3bd93-186">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="3bd93-187">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="3bd93-187">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="3bd93-188">在 **[檢視]** 功能表中，選擇 **[電子郵件]** > **[惡意程式碼 ]**。</span><span class="sxs-lookup"><span data-stu-id="3bd93-188">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="3bd93-189">![總管的檢視功能表](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="3bd93-189">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>

3. <span data-ttu-id="3bd93-190">按一下 **[寄件者]**，然後選擇 **[基本]** > **[偵測技術]**。</span><span class="sxs-lookup"><span data-stu-id="3bd93-190">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="3bd93-191">您的偵測技術現在可做為報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="3bd93-191">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="3bd93-192">![惡意程式碼偵測技術](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="3bd93-192">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 

4. <span data-ttu-id="3bd93-193">選取一個選項，然後按一下 **[重新整理]** 按鈕來套用該篩選器。</span><span class="sxs-lookup"><span data-stu-id="3bd93-193">Select an option, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="3bd93-194">![選取的偵測技術](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="3bd93-194">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span><br/> 

<span data-ttu-id="3bd93-195">報告會使用您所選取的技術選項重新整理，以顯示在電子郵件中偵測到的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="3bd93-195">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="3bd93-196">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="3bd93-196">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="3bd93-197">檢視網路釣魚 URL 並按一下結果</span><span class="sxs-lookup"><span data-stu-id="3bd93-197">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="3bd93-198">假設您想要查看透過電子郵件中的 URL 進行的網路釣魚攻擊，包括允許、封鎖及覆寫的 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="3bd93-198">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="3bd93-199">若要識別已按過的 URL，則必須設定 [ATP 安全連結](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="3bd93-199">Identifying URLs that were clicked requires [ATP Safe links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="3bd93-200">請確認您已針對點擊時保護和 ATP 安全連結的按一下結果記錄設定 [ATP 安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3bd93-200">Make sure that you have set up [ATP Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by ATP Safe Links.</span></span> 

<span data-ttu-id="3bd93-201">若要檢閱郵件中的網路釣魚 URL 和網路釣魚郵件中的 URL 點擊，請使用總管 (或即時偵測) 的 [[電子郵件] > [網路釣魚]](threat-explorer-views.md#email--phish) 檢視。</span><span class="sxs-lookup"><span data-stu-id="3bd93-201">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="3bd93-202">在安全性與合規性中心 ([https://protection.office.com](https://protection.office.com)) 選擇 **[威脅管理]** > **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="3bd93-202">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="3bd93-203">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="3bd93-203">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="3bd93-204">在 **[檢視]** 功能表中，選擇 **[電子郵件]** > **[網路釣魚]**。</span><span class="sxs-lookup"><span data-stu-id="3bd93-204">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="3bd93-205">![總管的檢視功能表](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="3bd93-205">![View menu for Explorer](../../media/ExplorerViewEmailPhishMenu.png)</span></span><br/>

3. <span data-ttu-id="3bd93-206">按一下 **[寄件者]**，然後選擇 **[URL]** > **按一下結果**。</span><span class="sxs-lookup"><span data-stu-id="3bd93-206">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="3bd93-207">選取一或多個選項，例如 **[已封鎖]** 和 **[封鎖覆寫]**，然後按一下要套用該篩選器的選項同一行上的 **[重新整理]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3bd93-207">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="3bd93-208">(請勿重新整理瀏覽器視窗。)</span><span class="sxs-lookup"><span data-stu-id="3bd93-208">(Don't refresh your browser window.)</span></span><br/><span data-ttu-id="3bd93-209">![URL 和按一下結果](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="3bd93-209">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

    <span data-ttu-id="3bd93-210">報告會重新整理以在報告下的 [URL] 索引標籤上顯示兩個不同的 URL 表格：</span><span class="sxs-lookup"><span data-stu-id="3bd93-210">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="3bd93-211">**[熱門 URL]** 為已篩選的郵件中的 URL，而電子郵件傳送動作會計算每個 URL。</span><span class="sxs-lookup"><span data-stu-id="3bd93-211">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="3bd93-212">在網路釣魚電子郵件檢視中，此清單通常會包含合法的 URL。</span><span class="sxs-lookup"><span data-stu-id="3bd93-212">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="3bd93-213">攻擊者會在這些郵件中混雜善意和惡意的 URL，以試圖傳遞這些郵件，但他們會讓惡意連結看起來更加有趣，以誘使使用者點擊。</span><span class="sxs-lookup"><span data-stu-id="3bd93-213">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="3bd93-214">URL 表格是依電子郵件總數量排序 (注意：為了簡化檢視，不會顯示此欄)。</span><span class="sxs-lookup"><span data-stu-id="3bd93-214">The table of URLs is sorted by total email count (NOTE: This column is not shown to simplify the view).</span></span>

   - <span data-ttu-id="3bd93-215">**[熱門點擊]** 為點擊過的包含在安全連結中的 URL，並依總點擊數排序 (為了簡化檢視，此欄也不會顯示)。</span><span class="sxs-lookup"><span data-stu-id="3bd93-215">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="3bd93-216">依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。</span><span class="sxs-lookup"><span data-stu-id="3bd93-216">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="3bd93-217">在網路釣魚電子郵件檢視中，這些通常是可疑或惡意的 URL，但可能包含網路釣魚郵件中的無害 URL。</span><span class="sxs-lookup"><span data-stu-id="3bd93-217">In the phish email view, these are more often suspicious or malicious URLs, but could include clean URLs that are in phish messages.</span></span> <span data-ttu-id="3bd93-218">已開啟的連結 URL 點擊不會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="3bd93-218">URL clicks on unwrapped links will not show up here.</span></span>
   
   <span data-ttu-id="3bd93-219">兩個 URL 表格依傳遞動作和位置顯示網路釣魚電子郵件訊息熱門 URL，並顯示已封鎖的 URL 點擊 (或儘管已警告卻仍造訪的 URL)，讓您了解使用者接收到及互動的潛在惡意連結。</span><span class="sxs-lookup"><span data-stu-id="3bd93-219">The two URL tables show top URLs in phishing email messages by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="3bd93-220">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="3bd93-220">From here, you can conduct further analysis.</span></span> <span data-ttu-id="3bd93-221">例如，在圖表的下方，您可以查看貴組織環境中封鎖的電子郵件訊息熱門 URL。</span><span class="sxs-lookup"><span data-stu-id="3bd93-221">For example, below the chart, you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>
   
   ![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)
   
   <span data-ttu-id="3bd93-223">選取 URL 以檢視更多詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3bd93-223">Select a URL to view more detailed information.</span></span> <span data-ttu-id="3bd93-224">**請注意**：URL 飛出對話方塊中，電子郵件篩選已移除，以讓您完整檢視暴露於環境中的 URL。</span><span class="sxs-lookup"><span data-stu-id="3bd93-224">**Note**: In the URL flyout dialog, the filtering on email messages is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="3bd93-225">這能讓您在總管中篩選出擔心的電子郵件訊息，找出具有潛在威脅的特定 URL，然後了解暴露於環境 (經由 URL 詳細資料對話方塊) 中的 URL，而不需要將 URL 篩選新增至總管檢視本身。</span><span class="sxs-lookup"><span data-stu-id="3bd93-225">This lets you filter down email messages in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="3bd93-226">檢閱使用者回報的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="3bd93-226">Review email messages reported by users</span></span>

<span data-ttu-id="3bd93-227">假設您想透過使用 [Outlook 和 Outlook 網頁版的回報郵件增益集](enable-the-report-message-add-in.md)來查看貴組織使用者回報為「垃圾郵件」、「非垃圾郵件」或「網路釣魚」的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="3bd93-227">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="3bd93-228">若要這麼做，請使用總管 (或即時偵測) 的 [[電子郵件] > [提交]](threat-explorer-views.md#email--submissions) 檢視。</span><span class="sxs-lookup"><span data-stu-id="3bd93-228">To do this, use the [Email > Submissions](threat-explorer-views.md#email--submissions) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="3bd93-229">在安全性與合規性中心 ([https://protection.office.com](https://protection.office.com)) 選擇 **[威脅管理]** > **[總管]** (或 **[即時偵測]**)。</span><span class="sxs-lookup"><span data-stu-id="3bd93-229">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="3bd93-230">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="3bd93-230">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="3bd93-231">在 **[檢視]** 功能表中，選擇 **[電子郵件]** > **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="3bd93-231">In the **View** menu, choose **Email** > **Submissions**.</span></span><br/><span data-ttu-id="3bd93-232">![總管的檢視功能表](../../media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="3bd93-232">![View menu for Explorer](../../media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>

3. <span data-ttu-id="3bd93-233">按一下 **[寄件者]**，然後選擇 **[基本]** > **[回報類型]**。</span><span class="sxs-lookup"><span data-stu-id="3bd93-233">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="3bd93-234">選取一個選項，例如 **[網路釣魚]**，然後按一下 **[重新整理]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="3bd93-234">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="3bd93-235">![使用者回報的網路釣魚](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="3bd93-235">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="3bd93-236">報告會重新整理，顯示貴組織中的人員回報為網路釣魚攻擊的電子郵件相關資料。</span><span class="sxs-lookup"><span data-stu-id="3bd93-236">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="3bd93-237">您可以使用此資訊來進行進一步分析，並視需要調整 [ATP 防網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3bd93-237">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="3bd93-238">啟動自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="3bd93-238">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="3bd93-239">**Office 365 ATP 方案 2** 和 **Office 365 E5** 提供自動化調查及回應功能。</span><span class="sxs-lookup"><span data-stu-id="3bd93-239">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="3bd93-240">(新增！) [自動化調查及回應](automated-investigation-response-office.md)能為您的安全性作業小組節省許多時間和精力來調查及降低網路攻擊。</span><span class="sxs-lookup"><span data-stu-id="3bd93-240">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="3bd93-241">除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。</span><span class="sxs-lookup"><span data-stu-id="3bd93-241">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> 

<span data-ttu-id="3bd93-242">如需這方面的詳細資訊，請參閱[範例：安全性系統管理員從總管觸發調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="3bd93-242">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="3bd93-243">更多使用總管 (或即時偵測) 的方法</span><span class="sxs-lookup"><span data-stu-id="3bd93-243">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="3bd93-244">除了這篇文章所述的案例，總管 (或即時偵測) 還有更多回報選項。</span><span class="sxs-lookup"><span data-stu-id="3bd93-244">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span> 
- [<span data-ttu-id="3bd93-245">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="3bd93-245">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="3bd93-246">檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="3bd93-246">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="3bd93-247">取得威脅總管 (和即時偵測) 檢視的概觀</span><span class="sxs-lookup"><span data-stu-id="3bd93-247">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="3bd93-248">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="3bd93-248">Required licenses and permissions</span></span>

<span data-ttu-id="3bd93-249">您必須具備 [Office 365 ATP](office-365-atp.md) 才能取得總管或即時偵測。</span><span class="sxs-lookup"><span data-stu-id="3bd93-249">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>
- <span data-ttu-id="3bd93-250">總管會包含在 Office 365 ATP 方案 2。</span><span class="sxs-lookup"><span data-stu-id="3bd93-250">Explorer is included in Office 365 ATP Plan 2.</span></span> 
- <span data-ttu-id="3bd93-251">即時偵測報告會包含在 Office 365 ATP 方案 1。</span><span class="sxs-lookup"><span data-stu-id="3bd93-251">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>
- <span data-ttu-id="3bd93-252">請計劃指派授權給所有應受 Office 365 ATP 保護的使用者。</span><span class="sxs-lookup"><span data-stu-id="3bd93-252">Plan to assign licenses for all users who should be protected by Office 365 ATP.</span></span> <span data-ttu-id="3bd93-253">(總管或即時偵測會為經過授權的使用者顯示偵測資料。)</span><span class="sxs-lookup"><span data-stu-id="3bd93-253">(Explorer or real-time detections shows detection data for licensed users.)</span></span>

<span data-ttu-id="3bd93-254">若要檢視及使用總管或即時偵測，您必須具有適當的權限，例如授與安全性系統管理員或安全性讀取者的權限。</span><span class="sxs-lookup"><span data-stu-id="3bd93-254">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="3bd93-255">針對「安全性與合規性中心」，您必須受指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="3bd93-255">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="3bd93-256">組織管理</span><span class="sxs-lookup"><span data-stu-id="3bd93-256">Organization Management</span></span>
    - <span data-ttu-id="3bd93-257">安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="3bd93-257">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="3bd93-258">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="3bd93-258">Security Reader</span></span>

- <span data-ttu-id="3bd93-259">針對 Exchange Online，您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) 受指派下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="3bd93-259">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>
    - <span data-ttu-id="3bd93-260">組織管理</span><span class="sxs-lookup"><span data-stu-id="3bd93-260">Organization Management</span></span>
    - <span data-ttu-id="3bd93-261">僅檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="3bd93-261">View-only Organization Management</span></span>
    - <span data-ttu-id="3bd93-262">僅檢視收件者角色</span><span class="sxs-lookup"><span data-stu-id="3bd93-262">View-Only Recipients role</span></span>
    - <span data-ttu-id="3bd93-263">合規性管理</span><span class="sxs-lookup"><span data-stu-id="3bd93-263">Compliance Management</span></span>

<span data-ttu-id="3bd93-264">若要深入了解角色和權限，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="3bd93-264">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="3bd93-265">Office 365 安全性與合規性中心權限</span><span class="sxs-lookup"><span data-stu-id="3bd93-265">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="3bd93-266">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="3bd93-266">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="3bd93-267">某些威脅總管和即時偵測之間的差異</span><span class="sxs-lookup"><span data-stu-id="3bd93-267">Some differences between Threat Explorer and real-time detections</span></span>

 - <span data-ttu-id="3bd93-268">Office 365 ATP 方案 1 提供**即時偵測**報告，而 Office 365 ATP 方案 2 提供**威脅總管**。</span><span class="sxs-lookup"><span data-stu-id="3bd93-268">The **real-time detections** report is available in Office 365 ATP Plan 1, whereas **Threat Explorer** is available in Office 365 ATP Plan 2.</span></span>
 - <span data-ttu-id="3bd93-269">**即時偵測**報告可讓您即時檢視偵測。</span><span class="sxs-lookup"><span data-stu-id="3bd93-269">The **real-time detections** report allows you to view detections in real-time.</span></span> <span data-ttu-id="3bd93-270">**威脅總管**也有這個功能，但也能讓您檢視特定攻擊的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3bd93-270">**Threat Explorer** does this as well, but also allows you to view additional details for a given attack.</span></span>
