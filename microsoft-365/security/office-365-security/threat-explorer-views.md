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
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 瞭解如何使用威脅瀏覽器和即時偵測報告，調查和回應安全性 & 規範中心內的威脅。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78c03b45063f4bc34b47ab003bcf00d2befab886
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204604"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="8a37a-103">威脅瀏覽器和即時偵測中的視圖</span><span class="sxs-lookup"><span data-stu-id="8a37a-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8a37a-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="8a37a-104">**Applies to**</span></span>
- [<span data-ttu-id="8a37a-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="8a37a-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8a37a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a37a-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


![威脅總管](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="8a37a-108">[威脅瀏覽器](threat-explorer.md) (和即時偵測報告) 是強大的近即時工具，可協助安全性運作小組調查和回應安全性 & 合規性中心內的威脅。</span><span class="sxs-lookup"><span data-stu-id="8a37a-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="8a37a-109">Explorer (和即時偵測報告) 會以 Office 365 中的電子郵件和檔案顯示可疑惡意程式碼和網路釣魚程式的相關資訊，以及組織的其他安全性威脅和風險。</span><span class="sxs-lookup"><span data-stu-id="8a37a-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="8a37a-110">如果您有[Microsoft Defender for Office 365](defender-for-office-365.md) Plan 2，則會有 Explorer。</span><span class="sxs-lookup"><span data-stu-id="8a37a-110">If you have [Microsoft Defender for Office 365](defender-for-office-365.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="8a37a-111">如果您有 Microsoft Defender for Office 365 Plan 1，則會進行即時偵測。</span><span class="sxs-lookup"><span data-stu-id="8a37a-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="8a37a-112">當您第一次開啟 Explorer (或即時偵測報告) 時，預設視圖會顯示過去7天的電子郵件惡意程式碼偵測。</span><span class="sxs-lookup"><span data-stu-id="8a37a-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="8a37a-113">這份報告也可顯示 Microsoft Defender 的 Office 365 偵測，例如由[安全連結](safe-links.md)偵測到的惡意 URLs，以及由[安全附件](safe-attachments.md)偵測到的惡意檔。</span><span class="sxs-lookup"><span data-stu-id="8a37a-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](safe-links.md), and malicious files detected by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="8a37a-114">您可以修改此報告以顯示過去30天的資料 (與 Microsoft Defender for Office 365 P2 付費訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="8a37a-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="8a37a-115">試用訂閱只會包含過去7天的資料。</span><span class="sxs-lookup"><span data-stu-id="8a37a-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="8a37a-116">訂閱</span><span class="sxs-lookup"><span data-stu-id="8a37a-116">Subscription</span></span>|<span data-ttu-id="8a37a-117">實用</span><span class="sxs-lookup"><span data-stu-id="8a37a-117">Utility</span></span>|<span data-ttu-id="8a37a-118">資料天數</span><span class="sxs-lookup"><span data-stu-id="8a37a-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="8a37a-119">用於 Office 365 P1 試用版的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8a37a-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="8a37a-120">即時偵測</span><span class="sxs-lookup"><span data-stu-id="8a37a-120">Real-time detections</span></span>|<span data-ttu-id="8a37a-121">7 </span><span class="sxs-lookup"><span data-stu-id="8a37a-121">7</span></span>|
|<span data-ttu-id="8a37a-122">已支付 Office 365 P1 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8a37a-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="8a37a-123">即時偵測</span><span class="sxs-lookup"><span data-stu-id="8a37a-123">Real-time detections</span></span>|<span data-ttu-id="8a37a-124">大約</span><span class="sxs-lookup"><span data-stu-id="8a37a-124">30</span></span>|
|<span data-ttu-id="8a37a-125">適用于 Office 365 P2 試用版的 Office 365 P1 付費測試 Defender 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8a37a-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="8a37a-126">威脅總管</span><span class="sxs-lookup"><span data-stu-id="8a37a-126">Threat Explorer</span></span>|<span data-ttu-id="8a37a-127">7 </span><span class="sxs-lookup"><span data-stu-id="8a37a-127">7</span></span>|
|<span data-ttu-id="8a37a-128">適用于 Office 365 P2 試用版的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8a37a-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="8a37a-129">威脅總管</span><span class="sxs-lookup"><span data-stu-id="8a37a-129">Threat Explorer</span></span>|<span data-ttu-id="8a37a-130">7 </span><span class="sxs-lookup"><span data-stu-id="8a37a-130">7</span></span>|
|<span data-ttu-id="8a37a-131">用於 Office 365 P2 已支付的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8a37a-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="8a37a-132">威脅總管</span><span class="sxs-lookup"><span data-stu-id="8a37a-132">Threat Explorer</span></span>|<span data-ttu-id="8a37a-133">大約</span><span class="sxs-lookup"><span data-stu-id="8a37a-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="8a37a-134">我們即將開始展開瀏覽器的 (和即時偵測) 從7天到30天的試用承租人的資料保留和搜尋限制。</span><span class="sxs-lookup"><span data-stu-id="8a37a-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="8a37a-135">這項變更是在藍圖專案的一部分中追蹤的，而不是70544，而且目前在滾出階段。</span><span class="sxs-lookup"><span data-stu-id="8a37a-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="8a37a-136">使用 [ **View** ] （查看）功能表來變更顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="8a37a-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="8a37a-137">工具提示可協助您決定要使用的視圖。</span><span class="sxs-lookup"><span data-stu-id="8a37a-137">Tooltips help you determine which view to use.</span></span>

![威脅瀏覽器視圖功能表](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="8a37a-139">選取視圖後，您就可以套用篩選器，並設定查詢進行進一步的分析。</span><span class="sxs-lookup"><span data-stu-id="8a37a-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="8a37a-140">下列各節提供 Explorer (或即時偵測) 中所提供的各種視圖的簡短概述。</span><span class="sxs-lookup"><span data-stu-id="8a37a-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="8a37a-141">電子郵件 > 惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="8a37a-141">Email > Malware</span></span>

<span data-ttu-id="8a37a-142">若要查看此報告，請在 Explorer (或即時偵測) 中，選擇 [ **view** \> **Email** \> **Malware**]。</span><span class="sxs-lookup"><span data-stu-id="8a37a-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="8a37a-143">此視圖顯示識別為包含惡意程式碼之電子郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8a37a-143">This view shows information about email messages that were identified as containing malware.</span></span>

![查看識別為惡意程式碼的電子郵件資料](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="8a37a-145">按一下 [ **寄件者** ] 開啟您的查看選項清單。</span><span class="sxs-lookup"><span data-stu-id="8a37a-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="8a37a-146">使用此清單，透過寄件者、收件者、寄件者網域、主旨、偵測技術、保護狀態等方式來查看資料。</span><span class="sxs-lookup"><span data-stu-id="8a37a-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="8a37a-147">例如，若要查看對偵測到的電子郵件所採取的動作，請挑選清單中的 [ **保護狀態** ]。</span><span class="sxs-lookup"><span data-stu-id="8a37a-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="8a37a-148">選取一個選項，然後按一下 [重新整理] 按鈕，將該篩選套用至您的報表。</span><span class="sxs-lookup"><span data-stu-id="8a37a-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![威脅瀏覽器的威脅防護狀態選項](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="8a37a-150">在圖表下方，查看特定郵件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8a37a-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="8a37a-151">當您選取清單中的專案時，會開啟一個彈出窗格，您可以在其中深入瞭解您所選取的專案。</span><span class="sxs-lookup"><span data-stu-id="8a37a-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![已開啟快顯視窗的威脅瀏覽器](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="8a37a-153">電子郵件 > 網路釣魚</span><span class="sxs-lookup"><span data-stu-id="8a37a-153">Email > Phish</span></span>

<span data-ttu-id="8a37a-154">若要查看此報告，請在 Explorer (或即時偵測) 中，選擇 [ **view** \> **Email** \> **釣魚網絡**]。</span><span class="sxs-lookup"><span data-stu-id="8a37a-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="8a37a-155">此視圖顯示視為網路釣魚企圖的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8a37a-155">This view shows email messages identified as phishing attempts.</span></span>

![查看識別為網路釣魚企圖的電子郵件資料](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="8a37a-157">按一下 [ **寄件者** ] 開啟您的查看選項清單。</span><span class="sxs-lookup"><span data-stu-id="8a37a-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="8a37a-158">使用此清單，依寄件者、收件者、寄件者網域、寄件者 IP、URL 網域、判定結果等方式來查看資料。</span><span class="sxs-lookup"><span data-stu-id="8a37a-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="8a37a-159">例如，若要查看在已識別為網路釣魚企圖的 URLs 上按一下人員時採取的動作，請挑選清單中 **的 [依** 序顯示]，然後選取一或多個選項，然後按一下 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="8a37a-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![按一下網路釣魚報告的 [已判定選項]](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="8a37a-161">在圖表下方，查看特定訊息、URL 按一下、URLs 及電子郵件原始的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8a37a-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![在電子郵件訊息中偵測到網路釣魚網路的 URLs](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="8a37a-163">當您選取清單中的專案（例如已偵測到的 URL）時，就會開啟彈出窗格，您可以在其中深入瞭解您所選取的專案。</span><span class="sxs-lookup"><span data-stu-id="8a37a-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![偵測到之 URL 的詳細資料](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="8a37a-165">電子郵件 > 提交</span><span class="sxs-lookup"><span data-stu-id="8a37a-165">Email > Submissions</span></span>

<span data-ttu-id="8a37a-166">若要查看此報告，請在 Explorer (或即時偵測) 中，選擇 [ **view** \> **Email** \> **報送**]。</span><span class="sxs-lookup"><span data-stu-id="8a37a-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="8a37a-167">此視圖顯示使用者已舉報為垃圾郵件、非垃圾郵件或網路釣魚電子郵件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8a37a-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![使用者所報告的電子郵件](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="8a37a-169">按一下 [ **寄件者** ] 開啟您的查看選項清單。</span><span class="sxs-lookup"><span data-stu-id="8a37a-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="8a37a-170">使用此清單，以 [寄件者]、[收件者]、[報告] 類型 (使用者判斷電子郵件為垃圾郵件、非垃圾郵件或網路釣魚) 等等的方式來查看資訊。</span><span class="sxs-lookup"><span data-stu-id="8a37a-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="8a37a-171">例如，若要查看報告為網路釣魚企圖的電子郵件資訊，請按一下 [ **寄件者** \> **報告類型**]，選取 [ **網路釣魚**]，然後按一下 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="8a37a-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![針對報表類型篩選選取的網路釣魚](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="8a37a-173">在圖表下方，查看特定電子郵件訊息的詳細資訊，例如主題行、寄件者的 IP 位址、將郵件報告為垃圾郵件的使用者，而非垃圾郵件或網路釣魚網路等等。</span><span class="sxs-lookup"><span data-stu-id="8a37a-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![報告為網路釣魚嘗試的郵件](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="8a37a-175">選取清單中的專案，以查看其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8a37a-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="8a37a-176">電子郵件 > 所有電子郵件</span><span class="sxs-lookup"><span data-stu-id="8a37a-176">Email > All email</span></span>

<span data-ttu-id="8a37a-177">若要在瀏覽器中查看此報告 ，請選擇 [在 \>  \> **所有郵件** 中查看電子郵件]。</span><span class="sxs-lookup"><span data-stu-id="8a37a-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="8a37a-178">這種方式會顯示電子郵件活動的完整視圖，包括因網路釣魚或惡意程式碼而識別為惡意的電子郵件，而且所有非惡意郵件 (一般電子郵件、垃圾郵件和大宗郵件) 。</span><span class="sxs-lookup"><span data-stu-id="8a37a-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="8a37a-179">如果您收到的錯誤是 **要顯示太多資料**，請新增篩選器，並視需要縮小您正在查看的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="8a37a-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="8a37a-180">若要套用篩選，請選擇 [ **寄件者**]，選取清單中的專案，然後按一下 [重新整理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="8a37a-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="8a37a-181">在我們的範例中，我們使用 **偵測技術** 做為篩選 (有許多選項可供使用) 。</span><span class="sxs-lookup"><span data-stu-id="8a37a-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="8a37a-182">以寄件者、寄件者的網域、收件者、主旨、附件檔案名、惡意程式碼系列、保護狀態 (動作來查看資訊。 Office 365) 中的威脅防護功能和原則，偵測技術 (偵測惡意程式碼) 的方式等等。</span><span class="sxs-lookup"><span data-stu-id="8a37a-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![透過偵測技術查看偵測到的電子郵件相關資料](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="8a37a-184">在圖表下方，查看特定電子郵件的詳細資料，例如主旨行、收件者、寄件者、狀態等等。</span><span class="sxs-lookup"><span data-stu-id="8a37a-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="8a37a-185">內容 > 惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="8a37a-185">Content > Malware</span></span>

<span data-ttu-id="8a37a-186">若要查看此報告，請在 Explorer (或即時偵測) 中，選擇 [ **view** \> **Content** \> **Malware**]。</span><span class="sxs-lookup"><span data-stu-id="8a37a-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="8a37a-187">此視圖會顯示[在 SharePoint Online、商務用 OneDrive 和 Microsoft Teams 中，以 Microsoft Defender for Office 365](mdo-for-spo-odb-and-teams.md)識別為惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="8a37a-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="8a37a-188">透過惡意程式碼系列來查看資訊，偵測技術 (偵測惡意軟體的方式) ，以及工作量 (OneDrive、SharePoint 或 Teams) 。</span><span class="sxs-lookup"><span data-stu-id="8a37a-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![查看偵測到之惡意程式碼的資料](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="8a37a-190">在圖表下方，查看特定檔案的詳細資訊，例如附件檔案名、工作量、檔案大小、最後修改檔案的使用者等等。</span><span class="sxs-lookup"><span data-stu-id="8a37a-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="8a37a-191">按一下以篩選功能</span><span class="sxs-lookup"><span data-stu-id="8a37a-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="8a37a-192">透過 Explorer (和即時偵測) ，您可以在按一下時套用篩選。</span><span class="sxs-lookup"><span data-stu-id="8a37a-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="8a37a-193">按一下圖例中的專案，該專案就會變成報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="8a37a-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="8a37a-194">例如，假設我們在瀏覽器中查看惡意程式碼視圖：</span><span class="sxs-lookup"><span data-stu-id="8a37a-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![移至威脅管理 \> 總管](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="8a37a-196">按一下此圖表中的 **ATP 引爆** ，會產生如下的視圖：</span><span class="sxs-lookup"><span data-stu-id="8a37a-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![瀏覽器篩選為只顯示 Office 365 引爆結果的 Defender](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="8a37a-198">在此視圖中，我們現在查看以 [安全附件](safe-attachments.md)引爆之檔案的資料。</span><span class="sxs-lookup"><span data-stu-id="8a37a-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="8a37a-199">在圖表下方，我們可以看到具有安全附件所偵測到之附件的特定電子郵件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8a37a-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![包含偵測到的附件之電子郵件的特定詳細資料](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="8a37a-201">選取一個或多個專案時，會啟動 [ **動作** ] 功能表，提供數個選項供您選擇 (s) 的選取專案。</span><span class="sxs-lookup"><span data-stu-id="8a37a-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![選取專案會啟用動作功能表](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="8a37a-203">您可以在按一下並流覽至特定詳細資料的情況中進行篩選，以在調查威脅時節省很多時間。</span><span class="sxs-lookup"><span data-stu-id="8a37a-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="8a37a-204">查詢和篩選</span><span class="sxs-lookup"><span data-stu-id="8a37a-204">Queries and filters</span></span>

<span data-ttu-id="8a37a-205">Explorer (和即時偵測報告) 具有多種強大的篩選和查詢功能，可讓您深入瞭解詳細資料，例如主要目標使用者、主要惡意程式碼系列、偵測技術等等。</span><span class="sxs-lookup"><span data-stu-id="8a37a-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="8a37a-206">每種類型的報表都提供不同的方式來查看及流覽資料。</span><span class="sxs-lookup"><span data-stu-id="8a37a-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a37a-207">在 Explorer (或即時偵測) 的查詢列中，請勿使用萬用字元（如星號或問號）。</span><span class="sxs-lookup"><span data-stu-id="8a37a-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="8a37a-208">當您在電子郵件訊息的 [主旨] **欄位** 上進行搜尋時，Explorer (或即時偵測) 會執行部分比對，類似于萬用字元搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="8a37a-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
