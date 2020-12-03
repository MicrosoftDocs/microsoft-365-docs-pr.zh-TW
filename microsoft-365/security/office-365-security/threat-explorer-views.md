---
title: 威脅瀏覽器和即時偵測中的視圖
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 瞭解如何使用威脅瀏覽器和即時偵測報告，調查和回應安全性 & 規範中心內的威脅。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 551425bf3e6b2c4fbb429dd6698b4f85e30d1ebe
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561228"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="5efb2-103">威脅瀏覽器和即時偵測中的視圖</span><span class="sxs-lookup"><span data-stu-id="5efb2-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


![威脅總管](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="5efb2-105">[威脅瀏覽器](threat-explorer.md) (和即時偵測報告) 是強大的近即時工具，可協助安全性運作小組調查和回應安全性 & 合規性中心內的威脅。</span><span class="sxs-lookup"><span data-stu-id="5efb2-105">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="5efb2-106">Explorer (和即時偵測報告) 會顯示可疑惡意程式碼和網路釣魚詐騙在 Office 365 中的電子郵件和檔案中的相關資訊，以及組織的其他安全性威脅和風險。</span><span class="sxs-lookup"><span data-stu-id="5efb2-106">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="5efb2-107">如果您有 [Microsoft Defender For Office 365](office-365-atp.md) 方案2，則會有 Explorer。</span><span class="sxs-lookup"><span data-stu-id="5efb2-107">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="5efb2-108">如果您有 Microsoft Defender for Office 365 方案1，則會進行即時偵測。</span><span class="sxs-lookup"><span data-stu-id="5efb2-108">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="5efb2-109">當您第一次開啟 Explorer (或即時偵測報告) 時，預設視圖會顯示過去7天的電子郵件惡意程式碼偵測。</span><span class="sxs-lookup"><span data-stu-id="5efb2-109">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="5efb2-110">此報告也可顯示 Microsoft Defender for Office 365 偵測，例如由 [安全連結](atp-safe-links.md)偵測到的惡意 URLs，以及 [安全附件](atp-safe-attachments.md)偵測到的惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="5efb2-110">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="5efb2-111">您可以修改此報告以顯示過去30天的資料 (與 Microsoft Defender for Office 365 P2 付費訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="5efb2-111">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="5efb2-112">試用訂閱只會包含過去7天的資料。</span><span class="sxs-lookup"><span data-stu-id="5efb2-112">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="5efb2-113">訂閱</span><span class="sxs-lookup"><span data-stu-id="5efb2-113">Subscription</span></span>|<span data-ttu-id="5efb2-114">實用</span><span class="sxs-lookup"><span data-stu-id="5efb2-114">Utility</span></span>|<span data-ttu-id="5efb2-115">資料天數</span><span class="sxs-lookup"><span data-stu-id="5efb2-115">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="5efb2-116">Microsoft Defender for Office 365 P1 試用版</span><span class="sxs-lookup"><span data-stu-id="5efb2-116">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="5efb2-117">即時偵測</span><span class="sxs-lookup"><span data-stu-id="5efb2-117">Real-time detections</span></span>|<span data-ttu-id="5efb2-118">7 </span><span class="sxs-lookup"><span data-stu-id="5efb2-118">7</span></span>|
|<span data-ttu-id="5efb2-119">Microsoft Defender for Office 365 P1 已付費</span><span class="sxs-lookup"><span data-stu-id="5efb2-119">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="5efb2-120">即時偵測</span><span class="sxs-lookup"><span data-stu-id="5efb2-120">Real-time detections</span></span>|<span data-ttu-id="5efb2-121">大約</span><span class="sxs-lookup"><span data-stu-id="5efb2-121">30</span></span>|
|<span data-ttu-id="5efb2-122">適用于 office 的 Microsoft Defender 365 P1 已付費測試 Defender for Office 365 P2 試用版</span><span class="sxs-lookup"><span data-stu-id="5efb2-122">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="5efb2-123">威脅總管</span><span class="sxs-lookup"><span data-stu-id="5efb2-123">Threat Explorer</span></span>|<span data-ttu-id="5efb2-124">7 </span><span class="sxs-lookup"><span data-stu-id="5efb2-124">7</span></span>|
|<span data-ttu-id="5efb2-125">Microsoft Defender for Office 365 P2 試用版</span><span class="sxs-lookup"><span data-stu-id="5efb2-125">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="5efb2-126">威脅總管</span><span class="sxs-lookup"><span data-stu-id="5efb2-126">Threat Explorer</span></span>|<span data-ttu-id="5efb2-127">7 </span><span class="sxs-lookup"><span data-stu-id="5efb2-127">7</span></span>|
|<span data-ttu-id="5efb2-128">Microsoft Defender for Office 365 P2 已支付</span><span class="sxs-lookup"><span data-stu-id="5efb2-128">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="5efb2-129">威脅總管</span><span class="sxs-lookup"><span data-stu-id="5efb2-129">Threat Explorer</span></span>|<span data-ttu-id="5efb2-130">大約</span><span class="sxs-lookup"><span data-stu-id="5efb2-130">30</span></span>|
|

<span data-ttu-id="5efb2-131">使用 [ **View** ] （查看）功能表來變更顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="5efb2-131">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="5efb2-132">工具提示可協助您決定要使用的視圖。</span><span class="sxs-lookup"><span data-stu-id="5efb2-132">Tooltips help you determine which view to use.</span></span>

![威脅瀏覽器視圖功能表](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="5efb2-134">選取視圖後，您就可以套用篩選器，並設定查詢進行進一步的分析。</span><span class="sxs-lookup"><span data-stu-id="5efb2-134">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="5efb2-135">下列各節提供 Explorer (或即時偵測) 中所提供的各種視圖的簡短概述。</span><span class="sxs-lookup"><span data-stu-id="5efb2-135">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="5efb2-136">電子郵件 > 惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="5efb2-136">Email > Malware</span></span>

<span data-ttu-id="5efb2-137">若要查看此報告，請在 Explorer (或即時偵測) 中，選擇 [ **view**  >  **Email**  >  **Malware**]。</span><span class="sxs-lookup"><span data-stu-id="5efb2-137">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Malware**.</span></span> <span data-ttu-id="5efb2-138">此視圖顯示識別為包含惡意程式碼之電子郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5efb2-138">This view shows information about email messages that were identified as containing malware.</span></span>

![查看識別為惡意程式碼的電子郵件資料](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="5efb2-140">按一下 [ **寄件者** ] 開啟您的查看選項清單。</span><span class="sxs-lookup"><span data-stu-id="5efb2-140">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="5efb2-141">使用此清單，透過寄件者、收件者、寄件者網域、主旨、偵測技術、保護狀態等方式來查看資料。</span><span class="sxs-lookup"><span data-stu-id="5efb2-141">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="5efb2-142">例如，若要查看對偵測到的電子郵件所採取的動作，請挑選清單中的 [ **保護狀態** ]。</span><span class="sxs-lookup"><span data-stu-id="5efb2-142">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="5efb2-143">選取一個選項，然後按一下 [重新整理] 按鈕，將該篩選套用至您的報表。</span><span class="sxs-lookup"><span data-stu-id="5efb2-143">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![威脅瀏覽器的威脅防護狀態選項](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="5efb2-145">在圖表下方，查看特定郵件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5efb2-145">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="5efb2-146">當您選取清單中的專案時，會開啟一個彈出窗格，您可以在其中深入瞭解您所選取的專案。</span><span class="sxs-lookup"><span data-stu-id="5efb2-146">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![已開啟快顯視窗的威脅瀏覽器](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="5efb2-148">電子郵件 > 網路釣魚</span><span class="sxs-lookup"><span data-stu-id="5efb2-148">Email > Phish</span></span>

<span data-ttu-id="5efb2-149">若要查看此報告，請在 Explorer (或即時偵測) 中，選擇 [ **view**  >  **Email**  >  **釣魚網絡**]。</span><span class="sxs-lookup"><span data-stu-id="5efb2-149">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Phish**.</span></span> <span data-ttu-id="5efb2-150">此視圖顯示視為網路釣魚企圖的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5efb2-150">This view shows email messages identified as phishing attempts.</span></span>

![查看識別為網路釣魚企圖的電子郵件資料](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="5efb2-152">按一下 [ **寄件者** ] 開啟您的查看選項清單。</span><span class="sxs-lookup"><span data-stu-id="5efb2-152">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="5efb2-153">使用此清單，依寄件者、收件者、寄件者網域、寄件者 IP、URL 網域、判定結果等方式來查看資料。</span><span class="sxs-lookup"><span data-stu-id="5efb2-153">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="5efb2-154">例如，若要查看在已識別為網路釣魚企圖的 URLs 上按一下人員時採取的動作，請挑選清單中 **的 [依** 序顯示]，然後選取一或多個選項，然後按一下 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5efb2-154">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![按一下網路釣魚報告的 [已判定選項]](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="5efb2-156">在圖表下方，查看特定訊息、URL 按一下、URLs 及電子郵件原始的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5efb2-156">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![在電子郵件訊息中偵測到網路釣魚網路的 URLs](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="5efb2-158">當您選取清單中的專案（例如已偵測到的 URL）時，就會開啟彈出窗格，您可以在其中深入瞭解您所選取的專案。</span><span class="sxs-lookup"><span data-stu-id="5efb2-158">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![偵測到之 URL 的詳細資料](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="5efb2-160">電子郵件 > 提交</span><span class="sxs-lookup"><span data-stu-id="5efb2-160">Email > Submissions</span></span>

<span data-ttu-id="5efb2-161">若要查看此報告，請在 Explorer (或即時偵測) 中，選擇 [ **view**  >  **Email**  >  **報送**]。</span><span class="sxs-lookup"><span data-stu-id="5efb2-161">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Submissions**.</span></span> <span data-ttu-id="5efb2-162">此視圖顯示使用者已舉報為垃圾郵件、非垃圾郵件或網路釣魚電子郵件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5efb2-162">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![使用者所報告的電子郵件](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="5efb2-164">按一下 [ **寄件者** ] 開啟您的查看選項清單。</span><span class="sxs-lookup"><span data-stu-id="5efb2-164">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="5efb2-165">使用此清單，以 [寄件者]、[收件者]、[報告] 類型 (使用者判斷電子郵件為垃圾郵件、非垃圾郵件或網路釣魚) 等等的方式來查看資訊。</span><span class="sxs-lookup"><span data-stu-id="5efb2-165">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="5efb2-166">例如，若要查看報告為網路釣魚企圖的電子郵件資訊，請按一下 [**寄件者**  >  **報告類型**]，選取 [**網路釣魚**]，然後按一下 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5efb2-166">For example, to view information about email messages that were reported as phishing attempts, click **Sender** > **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![針對報表類型篩選選取的網路釣魚](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="5efb2-168">在圖表下方，查看特定電子郵件訊息的詳細資訊，例如主題行、寄件者的 IP 位址、將郵件報告為垃圾郵件的使用者，而非垃圾郵件或網路釣魚網路等等。</span><span class="sxs-lookup"><span data-stu-id="5efb2-168">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![報告為網路釣魚嘗試的郵件](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="5efb2-170">選取清單中的專案，以查看其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5efb2-170">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="5efb2-171">電子郵件 > 所有電子郵件</span><span class="sxs-lookup"><span data-stu-id="5efb2-171">Email > All email</span></span>

<span data-ttu-id="5efb2-172">若要在瀏覽器中查看此報告 **View**，請選擇 [在  >  **Email**  >  **所有郵件** 中查看電子郵件]。</span><span class="sxs-lookup"><span data-stu-id="5efb2-172">To view this report, in Explorer, choose **View** > **Email** > **All mail**.</span></span> <span data-ttu-id="5efb2-173">這種方式會顯示電子郵件活動的完整視圖，包括因網路釣魚或惡意程式碼而識別為惡意的電子郵件，而且所有非惡意郵件 (一般電子郵件、垃圾郵件和大宗郵件) 。</span><span class="sxs-lookup"><span data-stu-id="5efb2-173">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="5efb2-174">如果您收到的錯誤是 **要顯示太多資料**，請新增篩選器，並視需要縮小您正在查看的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="5efb2-174">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="5efb2-175">若要套用篩選，請選擇 [ **寄件者**]，選取清單中的專案，然後按一下 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5efb2-175">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="5efb2-176">在我們的範例中，我們使用 **偵測技術** 做為篩選 (有許多選項可供使用) 。</span><span class="sxs-lookup"><span data-stu-id="5efb2-176">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="5efb2-177">依寄件者、寄件者的網域、收件者、主旨、附件檔案名、惡意程式碼系列、保護狀態 (動作來查看資訊。) 、偵測技術365中的威脅防護功能和原則， (偵測到惡意程式碼的方式) 等等。</span><span class="sxs-lookup"><span data-stu-id="5efb2-177">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![透過偵測技術查看偵測到的電子郵件相關資料](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="5efb2-179">在圖表下方，查看特定電子郵件的詳細資料，例如主旨行、收件者、寄件者、狀態等等。</span><span class="sxs-lookup"><span data-stu-id="5efb2-179">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="5efb2-180">內容 > 惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="5efb2-180">Content > Malware</span></span>

<span data-ttu-id="5efb2-181">若要查看此報告，請在 Explorer (或即時偵測) 中，選擇 [ **view**  >  **Content**  >  **Malware**]。</span><span class="sxs-lookup"><span data-stu-id="5efb2-181">To view this report, in Explorer (or real-time detections), choose **View** > **Content** > **Malware**.</span></span> <span data-ttu-id="5efb2-182">此視圖會顯示 [Microsoft Defender For Office 365 在 SharePoint Online、商務 OneDrive For Business 及 Microsoft 小組中](atp-for-spo-odb-and-teams.md)識別為惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="5efb2-182">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="5efb2-183">透過惡意程式碼系列來查看資訊，偵測技術 (偵測到惡意軟體的方式) ，以及工作量 (OneDrive、SharePoint 或小組) 。</span><span class="sxs-lookup"><span data-stu-id="5efb2-183">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![查看偵測到之惡意程式碼的資料](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="5efb2-185">在圖表下方，查看特定檔案的詳細資訊，例如附件檔案名、工作量、檔案大小、最後修改檔案的使用者等等。</span><span class="sxs-lookup"><span data-stu-id="5efb2-185">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="5efb2-186">按一下以篩選功能</span><span class="sxs-lookup"><span data-stu-id="5efb2-186">Click-to-filter capabilities</span></span>

<span data-ttu-id="5efb2-187">透過 Explorer (和即時偵測) ，您可以在按一下時套用篩選。</span><span class="sxs-lookup"><span data-stu-id="5efb2-187">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="5efb2-188">按一下圖例中的專案，該專案就會變成報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="5efb2-188">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="5efb2-189">例如，假設我們在瀏覽器中查看惡意程式碼視圖：</span><span class="sxs-lookup"><span data-stu-id="5efb2-189">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![移至威脅管理 \> 總管](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="5efb2-191">按一下此圖表中的 **ATP 引爆** ，會產生如下的視圖：</span><span class="sxs-lookup"><span data-stu-id="5efb2-191">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![瀏覽器篩選為只顯示 Office 365 的 Defender 引爆結果](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="5efb2-193">在此視圖中，我們現在查看以 [安全附件](atp-safe-attachments.md)引爆之檔案的資料。</span><span class="sxs-lookup"><span data-stu-id="5efb2-193">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="5efb2-194">在圖表下方，我們可以看到具有安全附件所偵測到之附件的特定電子郵件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5efb2-194">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![包含偵測到的附件之電子郵件的特定詳細資料](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="5efb2-196">選取一個或多個專案時，會啟動 [ **動作** ] 功能表，提供數個選項供您選擇 (s) 的選取專案。</span><span class="sxs-lookup"><span data-stu-id="5efb2-196">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![選取專案會啟用動作功能表](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="5efb2-198">您可以在按一下並流覽至特定詳細資料的情況中進行篩選，以在調查威脅時節省很多時間。</span><span class="sxs-lookup"><span data-stu-id="5efb2-198">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="5efb2-199">查詢和篩選</span><span class="sxs-lookup"><span data-stu-id="5efb2-199">Queries and filters</span></span>

<span data-ttu-id="5efb2-200">Explorer (和即時偵測報告) 具有多種強大的篩選和查詢功能，可讓您深入瞭解詳細資料，例如主要目標使用者、主要惡意程式碼系列、偵測技術等等。</span><span class="sxs-lookup"><span data-stu-id="5efb2-200">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="5efb2-201">每種類型的報表都提供不同的方式來查看及流覽資料。</span><span class="sxs-lookup"><span data-stu-id="5efb2-201">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5efb2-202">在 Explorer (或即時偵測) 的查詢列中，請勿使用萬用字元（如星號或問號）。</span><span class="sxs-lookup"><span data-stu-id="5efb2-202">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="5efb2-203">當您在電子郵件訊息的 [主旨] **欄位** 上進行搜尋時，Explorer (或即時偵測) 會執行部分比對，類似于萬用字元搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="5efb2-203">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
