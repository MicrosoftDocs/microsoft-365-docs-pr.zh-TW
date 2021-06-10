---
title: 使用 Microsoft Defender 中 Office 365 的威脅瀏覽器的電子郵件安全性
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 查看並調查惡意程式碼釣魚企圖。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0326a51f14b402b9a579e8668ef2c026f9de789
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877893"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="08732-103">使用 Microsoft Defender 中 Office 365 的威脅瀏覽器的電子郵件安全性</span><span class="sxs-lookup"><span data-stu-id="08732-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="08732-104">本文內容：</span><span class="sxs-lookup"><span data-stu-id="08732-104">In this article:</span></span>

- [<span data-ttu-id="08732-105">查看電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="08732-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- <span data-ttu-id="08732-106">[查看網路釣魚 URL，然後按一下 [已判定資料]](#view-phishing-url-and-click-verdict-data)</span><span class="sxs-lookup"><span data-stu-id="08732-106">[View phishing URL and click verdict data](#view-phishing-url-and-click-verdict-data)</span></span>
- [<span data-ttu-id="08732-107">啟動自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="08732-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="08732-108">這是 **威脅 Explorer (Explorer)**、**電子郵件安全性** 及 **Explorer 和即時** 偵測 (基礎的 **3 篇文章** 中的一部分，例如工具間的差異，以及操作) 所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="08732-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="08732-109">此系列中的其他兩篇文章是威脅瀏覽器及[威脅瀏覽器和即時偵測基礎知識](real-time-detections.md)[中的威脅搜尋](threat-hunting-in-threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="08732-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span> 

<span data-ttu-id="08732-110">本文說明如何透過 Microsoft 365 的安全性功能，查看並調查電子郵件中偵測到的惡意程式碼和網路釣魚企圖。</span><span class="sxs-lookup"><span data-stu-id="08732-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span> 

<span data-ttu-id="08732-111">**適用於**</span><span class="sxs-lookup"><span data-stu-id="08732-111">**Applies to**</span></span>

- [<span data-ttu-id="08732-112">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="08732-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="08732-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08732-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="08732-114">查看電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="08732-114">View malware detected in email</span></span>

<span data-ttu-id="08732-115">若要查看以 Microsoft 365 技術排序的電子郵件中偵測到惡意程式碼，請使用 Explorer 的[電子郵件 > 惡意](threat-explorer-views.md#email--malware)代碼視圖 (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="08732-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="08732-116">惡意程式碼是預設的視圖，所以當您開啟 Explorer 時，可能會立即選取它。</span><span class="sxs-lookup"><span data-stu-id="08732-116">Malware is the default view, so it may be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="08732-117">在 [安全性 & 規範中心] (<https://protection.office.com>) 中，選擇 [ **威脅管理** \> **瀏覽器** (] 或 [ **即時** 偵測]) 。</span><span class="sxs-lookup"><span data-stu-id="08732-117">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="08732-118">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="08732-118">(This example uses Explorer.)</span></span>

   <span data-ttu-id="08732-119">如果您正在集中 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 滾動至 **電子郵件 & 協同**  >  **瀏覽器**。</span><span class="sxs-lookup"><span data-stu-id="08732-119">If you're in the converged Microsoft 365 Defender portal (<https://security.microsoft.com>) scroll to **Email & collaboration** > **Explorer**.</span></span>

   <span data-ttu-id="08732-120">從這裡開始，在視圖中，選擇必要時要調查 (的特定時間框架) ，並依 [瀏覽器](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)的流覽方式，將篩選的重點放在一起。</span><span class="sxs-lookup"><span data-stu-id="08732-120">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="08732-121">在 [ **視圖** ] 功能表中，選擇 [ **電子郵件** \> **惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="08732-121">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08732-122">![總管的檢視功能表](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="08732-122">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="08732-123">按一下 [ **寄件者**]，然後選擇 [ **基本** \> **偵測技術**]。</span><span class="sxs-lookup"><span data-stu-id="08732-123">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="08732-124">您的偵測技術現在可做為報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="08732-124">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08732-125">![惡意程式碼偵測技術](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="08732-125">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="08732-126">選擇 [選項]。</span><span class="sxs-lookup"><span data-stu-id="08732-126">Choose an option.</span></span> <span data-ttu-id="08732-127">然後選取 [重新整理] **按鈕，套用** 該篩選。</span><span class="sxs-lookup"><span data-stu-id="08732-127">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08732-128">![選取的偵測技術](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="08732-128">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

   <span data-ttu-id="08732-129">報告會進行重新整理，以顯示惡意程式碼在電子郵件中偵測到的結果，並使用您選取的技術選項。</span><span class="sxs-lookup"><span data-stu-id="08732-129">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="08732-130">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="08732-130">From here, you can conduct further analysis.</span></span> 

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="08732-131">查看網路釣魚 URL，然後按一下 [已判定資料]</span><span class="sxs-lookup"><span data-stu-id="08732-131">View phishing URL and click verdict data</span></span>

<span data-ttu-id="08732-132">您可以透過電子郵件中的 URLs 來查看網路釣魚嘗試，包括允許、封鎖和覆蓋的 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="08732-132">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="08732-133">若要識別所按一下的 URLs，必須設定 [安全連結](safe-links.md) 。</span><span class="sxs-lookup"><span data-stu-id="08732-133">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="08732-134">請確定您已設定 [安全連結原則](set-up-safe-links-policies.md) 的 [保護] 和 [記錄] 按一下 [安全連結] 中的 [verdicts]。</span><span class="sxs-lookup"><span data-stu-id="08732-134">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="08732-135">若要查看郵件中的網路釣魚 URLs，並按一下網路釣魚郵件中 URLs，請使用瀏覽器或即時偵測的 [**電子郵件**  >  **網路釣魚**](threat-explorer-views.md#email--phish)視圖。</span><span class="sxs-lookup"><span data-stu-id="08732-135">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="08732-136">在 [安全性 & 規範中心] (<https://protection.office.com>) 中，選擇 [ **威脅管理** \> **瀏覽器** (] 或 [ **即時** 偵測]) 。</span><span class="sxs-lookup"><span data-stu-id="08732-136">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="08732-137">(此範例使用總管。)</span><span class="sxs-lookup"><span data-stu-id="08732-137">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="08732-138">在 [ **視圖** ] 功能表中，選擇 [ **電子郵件** \> **釣魚網絡**]。</span><span class="sxs-lookup"><span data-stu-id="08732-138">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08732-139">![網路釣魚內容中瀏覽器的視圖功能表](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="08732-139">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="08732-140">按一下 [ **寄件者**]，然後選擇 **URLs** \> **按一下 [判定**]。</span><span class="sxs-lookup"><span data-stu-id="08732-140">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="08732-141">選取一個或多個選項（例如 **封鎖** 和 **封鎖**），然後在與套用該篩選的選項相同的列上選取 [重新整理 **] 按鈕。**</span><span class="sxs-lookup"><span data-stu-id="08732-141">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="08732-142">(請勿重新整理瀏覽器視窗。)</span><span class="sxs-lookup"><span data-stu-id="08732-142">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08732-143">![URL 和按一下結果](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="08732-143">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="08732-144">報告會重新整理以在報告下的 [URL] 索引標籤上顯示兩個不同的 URL 表格：</span><span class="sxs-lookup"><span data-stu-id="08732-144">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="08732-145">**Top URLs** 是您篩選的郵件中 URLs，以及每個 URL 的電子郵件傳遞動作計數。</span><span class="sxs-lookup"><span data-stu-id="08732-145">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="08732-146">在網路釣魚電子郵件視圖中，此清單通常包含合法的 URLs。</span><span class="sxs-lookup"><span data-stu-id="08732-146">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="08732-147">攻擊者會在其郵件中混合使用良好和不良的 URLs，以嘗試傳遞，但它們會使惡意連結看起來更有趣。</span><span class="sxs-lookup"><span data-stu-id="08732-147">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="08732-148">URLs 的表格依總的電子郵件總數排序，但是此欄位是隱藏的，以簡化視圖。</span><span class="sxs-lookup"><span data-stu-id="08732-148">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="08732-149">**上** 指按一下的安全連結-包裝 URLs，依總按一下計數排序。</span><span class="sxs-lookup"><span data-stu-id="08732-149">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="08732-150">此欄位也不會顯示，以簡化視圖。</span><span class="sxs-lookup"><span data-stu-id="08732-150">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="08732-151">依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。</span><span class="sxs-lookup"><span data-stu-id="08732-151">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="08732-152">在網路釣魚電子郵件視圖中，這些通常是可疑或惡意的 URLs。</span><span class="sxs-lookup"><span data-stu-id="08732-152">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="08732-153">不過，此視圖可以包含不是威脅的 URLs，但位於網路釣魚郵件中。</span><span class="sxs-lookup"><span data-stu-id="08732-153">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="08732-154">在這裡未顯示 URL 按一下已開啟的連結。</span><span class="sxs-lookup"><span data-stu-id="08732-154">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="08732-155">這兩個 URL 表格會依照傳送動作和位置，顯示網路釣魚電子郵件中的最上層 URLs。</span><span class="sxs-lookup"><span data-stu-id="08732-155">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="08732-156">[！注意] 表格會顯示因警告而封鎖或訪問的 URL 按一下，因此您可以看到向使用者呈現的潛在不良連結，以及使用者所按一下的連結。</span><span class="sxs-lookup"><span data-stu-id="08732-156">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="08732-157">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="08732-157">From here, you can conduct further analysis.</span></span> <span data-ttu-id="08732-158">例如，在圖表下方，您可以在組織環境中所封鎖的電子郵件訊息中看到最上層 URLs。</span><span class="sxs-lookup"><span data-stu-id="08732-158">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08732-159">![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="08732-159">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="08732-160">選取 URL 以檢視更多詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="08732-160">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="08732-161">在 [URL 飛入] 對話方塊中，會移除電子郵件上的篩選，以顯示您環境中 URL 公開的完整視圖。</span><span class="sxs-lookup"><span data-stu-id="08732-161">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="08732-162">這可讓您在瀏覽器中篩選您關心的電子郵件訊息，找出潛在威脅的特定 URLs，然後透過 [URL 詳細資料] 對話方塊，展開您環境中的 URL 公開知識 () 而不必將 URL 篩選器新增至瀏覽器視圖本身。</span><span class="sxs-lookup"><span data-stu-id="08732-162">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="08732-163">按一下 verdicts 的轉譯</span><span class="sxs-lookup"><span data-stu-id="08732-163">Interpretation of click verdicts</span></span>

<span data-ttu-id="08732-164">在電子郵件或 URL flyouts 中，按一下上方，在篩選體驗中，您會看到不同的按一下判定值：</span><span class="sxs-lookup"><span data-stu-id="08732-164">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="08732-165">**無：** 無法捕獲 URL 的判定。</span><span class="sxs-lookup"><span data-stu-id="08732-165">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="08732-166">使用者可能已按一下透過 URL。</span><span class="sxs-lookup"><span data-stu-id="08732-166">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="08732-167">**允許：** 允許使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="08732-167">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="08732-168">**封鎖：** 已封鎖使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="08732-168">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="08732-169">**擱置的判定：** 使用者呈現在引爆擱置的頁面上。</span><span class="sxs-lookup"><span data-stu-id="08732-169">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="08732-170">**封鎖已被取代：** 封鎖使用者直接流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="08732-170">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="08732-171">但使用者 overrode 區塊以流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="08732-171">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="08732-172">**擱置的判定略過：** 使用者呈現的是 [引爆] 頁面。</span><span class="sxs-lookup"><span data-stu-id="08732-172">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="08732-173">但使用者 overrode 郵件以存取 URL。</span><span class="sxs-lookup"><span data-stu-id="08732-173">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="08732-174">**錯誤：** 使用者呈現錯誤頁面，或捕獲判定結果時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="08732-174">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="08732-175">**失敗：** 捕獲判定時，發生未知的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="08732-175">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="08732-176">使用者可能已按一下透過 URL。</span><span class="sxs-lookup"><span data-stu-id="08732-176">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="08732-177">啟動自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="08732-177">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="08732-178">您可以在 *Microsoft Defender Office 365 方案 2* 和 *Office 365 E5* 中取得自動化調查和回應功能。</span><span class="sxs-lookup"><span data-stu-id="08732-178">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="08732-179">[自動化調查和回應](automated-investigation-response-office.md) 可儲存您的安全性運作小組時間和精力，以調查及緩解 cyberattacks。</span><span class="sxs-lookup"><span data-stu-id="08732-179">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="08732-180">除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。</span><span class="sxs-lookup"><span data-stu-id="08732-180">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="08732-181">如需詳細資訊，請參閱 [範例：安全性管理員會從瀏覽器觸發調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="08732-181">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="08732-182">其他文章</span><span class="sxs-lookup"><span data-stu-id="08732-182">Other articles</span></span>

[<span data-ttu-id="08732-183">使用電子郵件實體頁面調查電子郵件</span><span class="sxs-lookup"><span data-stu-id="08732-183">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
