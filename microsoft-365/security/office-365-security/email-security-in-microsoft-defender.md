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
ms.openlocfilehash: cebe76536c5ed309ca16777e85c5cdf919d0fb5c
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082993"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="a3a34-103">使用 Microsoft Defender 中 Office 365 的威脅瀏覽器的電子郵件安全性</span><span class="sxs-lookup"><span data-stu-id="a3a34-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="a3a34-104">本文內容：</span><span class="sxs-lookup"><span data-stu-id="a3a34-104">In this article:</span></span>

- [<span data-ttu-id="a3a34-105">查看電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="a3a34-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- <span data-ttu-id="a3a34-106">[查看網路釣魚 URL，然後按一下 [已判定資料]](#view-phishing-url-and-click-verdict-data)</span><span class="sxs-lookup"><span data-stu-id="a3a34-106">[View phishing URL and click verdict data](#view-phishing-url-and-click-verdict-data)</span></span>
- [<span data-ttu-id="a3a34-107">啟動自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="a3a34-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="a3a34-108">這是 **威脅 Explorer (Explorer)**、**電子郵件安全性** 及 **Explorer 和即時** 偵測 (基礎的 **3 篇文章** 中的一部分，例如工具間的差異，以及操作) 所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="a3a34-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="a3a34-109">此系列中的其他兩篇文章是威脅瀏覽器及[威脅瀏覽器和即時偵測基礎知識](real-time-detections.md)[中的威脅搜尋](threat-hunting-in-threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="a3a34-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>

<span data-ttu-id="a3a34-110">本文說明如何透過 Microsoft 365 的安全性功能，查看並調查電子郵件中偵測到的惡意程式碼和網路釣魚企圖。</span><span class="sxs-lookup"><span data-stu-id="a3a34-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span>

<span data-ttu-id="a3a34-111">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a3a34-111">**Applies to:**</span></span>

- [<span data-ttu-id="a3a34-112">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="a3a34-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a3a34-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3a34-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="a3a34-114">查看電子郵件中偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="a3a34-114">View malware detected in email</span></span>

<span data-ttu-id="a3a34-115">若要查看以 Microsoft 365 技術排序的電子郵件中偵測到惡意程式碼，請使用 Explorer 的 [**電子郵件 \> 惡意**](threat-explorer-views.md#email--malware)代碼視圖 (或即時偵測) 。</span><span class="sxs-lookup"><span data-stu-id="a3a34-115">To see malware detected in email sorted by Microsoft 365 technology, use the [**Email \> Malware**](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="a3a34-116">惡意程式碼是預設的視圖，所以當您開啟 Explorer 時，可能會立即選取惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="a3a34-116">Malware is the default view, so it might be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="a3a34-117">在 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 中，選擇 [**電子郵件 & 協同** \> **流覽**] (或 **即時** 偵測;本範例會使用 Explorer) 。</span><span class="sxs-lookup"><span data-stu-id="a3a34-117">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**; This example uses Explorer).</span></span>

   <span data-ttu-id="a3a34-118">從這裡開始，在視圖中，選擇必要時要調查 (的特定時間框架) ，並依 [瀏覽器](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)的流覽方式，將篩選的重點放在一起。</span><span class="sxs-lookup"><span data-stu-id="a3a34-118">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="a3a34-119">在 [ **View** ] （查看）下拉式清單中，確認已選取 [ **電子郵件** \> **惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="a3a34-119">In the **View** drop down list, verify that **Email** \> **Malware** is selected.</span></span>

3. <span data-ttu-id="a3a34-120">按一下 [ **寄件者**]，然後在下拉式清單中選擇 [ **基本** \> **偵測技術** ]。</span><span class="sxs-lookup"><span data-stu-id="a3a34-120">Click **Sender**, and then choose **Basic** \> **Detection technology** in the drop down list.</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="惡意程式碼偵測技術":::

   <span data-ttu-id="a3a34-122">您的偵測技術現在可做為報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="a3a34-122">Your detection technologies are now available as filters for the report.</span></span>

4. <span data-ttu-id="a3a34-123">選擇一個選項， **然後按一下 [** 重新整理] 套用該篩選 (不要重新整理瀏覽器視窗) 。</span><span class="sxs-lookup"><span data-stu-id="a3a34-123">Choose an option, and then click **Refresh** to apply that filter (don't refresh your browser window).</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="選取的偵測技術":::

   <span data-ttu-id="a3a34-125">報告會進行重新整理，以顯示惡意程式碼在電子郵件中偵測到的結果，並使用您選取的技術選項。</span><span class="sxs-lookup"><span data-stu-id="a3a34-125">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="a3a34-126">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="a3a34-126">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="a3a34-127">查看網路釣魚 URL，然後按一下 [已判定資料]</span><span class="sxs-lookup"><span data-stu-id="a3a34-127">View phishing URL and click verdict data</span></span>

<span data-ttu-id="a3a34-128">您可以透過電子郵件中的 URLs 來查看網路釣魚嘗試，包括允許、封鎖和覆蓋的 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="a3a34-128">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="a3a34-129">若要識別所按一下的 URLs，必須設定[保管庫連結](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="a3a34-129">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="a3a34-130">請務必設定[保管庫連結原則](set-up-safe-links-policies.md)，以在按保管庫連結的情況時，按一下 [保護] 和 [記錄]。</span><span class="sxs-lookup"><span data-stu-id="a3a34-130">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

1. <span data-ttu-id="a3a34-131">在 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 中，選擇 [**電子郵件 & 協同** \> **流覽**] (或 **即時** 偵測;本範例會使用 Explorer) 。</span><span class="sxs-lookup"><span data-stu-id="a3a34-131">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**; This example uses Explorer).</span></span>

2. <span data-ttu-id="a3a34-132">在 [ **視圖** ] 下拉式清單中，選擇 [ **電子郵件** \> **釣魚網絡**]。</span><span class="sxs-lookup"><span data-stu-id="a3a34-132">In the **View** drop down list, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3a34-133">![網路釣魚內容中瀏覽器的視圖功能表](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="a3a34-133">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="a3a34-134">按一下 [**寄件者**]  ，然後選擇 \> 下拉式清單中的 [URLs **按一下 [判定**]。</span><span class="sxs-lookup"><span data-stu-id="a3a34-134">Click **Sender**, and then choose **URLs** \> **Click verdict** in the drop down list.</span></span>

4. <span data-ttu-id="a3a34-135">在出現的選項中，選取一或多個選項（例如 **封鎖** 和 **封鎖**）， **然後按一下 [** 重新整理 (不要重新整理瀏覽器視窗) 。</span><span class="sxs-lookup"><span data-stu-id="a3a34-135">In options that appear, select one or more options, such as **Blocked** and **Block overridden**, and then click **Refresh** (don't refresh your browser window).</span></span>

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="URL 和按一下結果":::

   <span data-ttu-id="a3a34-137">報表會進行重新整理，以在報表底下的 [ **URLs** ] 索引標籤上顯示兩個不同的 URL 表格：</span><span class="sxs-lookup"><span data-stu-id="a3a34-137">The report refreshes to show two different URL tables on the **URLs** tab under the report:</span></span>

   - <span data-ttu-id="a3a34-138">**Top URLs** 是您篩選的郵件中 URLs，以及每個 URL 的電子郵件傳遞動作計數。</span><span class="sxs-lookup"><span data-stu-id="a3a34-138">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="a3a34-139">在網路釣魚電子郵件視圖中，此清單通常包含合法的 URLs。</span><span class="sxs-lookup"><span data-stu-id="a3a34-139">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="a3a34-140">攻擊者會在其郵件中混合使用良好和不良的 URLs，以嘗試傳遞，但它們會使惡意連結看起來更有趣。</span><span class="sxs-lookup"><span data-stu-id="a3a34-140">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="a3a34-141">URLs 的表格依總的電子郵件總數排序，但是此欄位是隱藏的，以簡化視圖。</span><span class="sxs-lookup"><span data-stu-id="a3a34-141">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="a3a34-142">**上** 指按一下的保管庫連結包裝 URLs，依總按一下計數排序。</span><span class="sxs-lookup"><span data-stu-id="a3a34-142">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="a3a34-143">此欄位也不會顯示，以簡化視圖。</span><span class="sxs-lookup"><span data-stu-id="a3a34-143">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="a3a34-144">依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。</span><span class="sxs-lookup"><span data-stu-id="a3a34-144">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="a3a34-145">在網路釣魚電子郵件視圖中，這些通常是可疑或惡意的 URLs。</span><span class="sxs-lookup"><span data-stu-id="a3a34-145">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="a3a34-146">不過，此視圖可以包含不是威脅的 URLs，但位於網路釣魚郵件中。</span><span class="sxs-lookup"><span data-stu-id="a3a34-146">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="a3a34-147">在這裡未顯示 URL 按一下已開啟的連結。</span><span class="sxs-lookup"><span data-stu-id="a3a34-147">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="a3a34-148">這兩個 URL 表格會依照傳送動作和位置，顯示網路釣魚電子郵件中的最上層 URLs。</span><span class="sxs-lookup"><span data-stu-id="a3a34-148">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="a3a34-149">[！注意] 表格會顯示因警告而封鎖或訪問的 URL 按一下，因此您可以看到向使用者呈現的潛在不良連結，以及使用者所按一下的連結。</span><span class="sxs-lookup"><span data-stu-id="a3a34-149">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="a3a34-150">您可以從這裡進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="a3a34-150">From here, you can conduct further analysis.</span></span> <span data-ttu-id="a3a34-151">例如，在圖表下方，您可以在組織環境中所封鎖的電子郵件訊息中看到最上層 URLs。</span><span class="sxs-lookup"><span data-stu-id="a3a34-151">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3a34-152">![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="a3a34-152">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="a3a34-153">選取 URL 以檢視更多詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a3a34-153">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a3a34-154">在 [URL 飛入] 對話方塊中，會移除電子郵件上的篩選，以顯示您環境中 URL 公開的完整視圖。</span><span class="sxs-lookup"><span data-stu-id="a3a34-154">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="a3a34-155">這可讓您在瀏覽器中篩選您關心的電子郵件訊息，找出潛在威脅的特定 URLs，然後透過 [URL 詳細資料] 對話方塊，展開您環境中的 URL 公開知識 () 而不必將 URL 篩選器新增至瀏覽器視圖本身。</span><span class="sxs-lookup"><span data-stu-id="a3a34-155">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="a3a34-156">按一下 verdicts 的轉譯</span><span class="sxs-lookup"><span data-stu-id="a3a34-156">Interpretation of click verdicts</span></span>

<span data-ttu-id="a3a34-157">在電子郵件或 URL flyouts 中，按一下上方，在篩選體驗中，您會看到不同的按一下判定值：</span><span class="sxs-lookup"><span data-stu-id="a3a34-157">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="a3a34-158">**無：** 無法捕獲 URL 的判定。</span><span class="sxs-lookup"><span data-stu-id="a3a34-158">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="a3a34-159">使用者可能已按一下透過 URL。</span><span class="sxs-lookup"><span data-stu-id="a3a34-159">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="a3a34-160">**允許：** 允許使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="a3a34-160">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="a3a34-161">**封鎖：** 已封鎖使用者流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="a3a34-161">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="a3a34-162">**擱置的判定：** 使用者呈現在引爆擱置的頁面上。</span><span class="sxs-lookup"><span data-stu-id="a3a34-162">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="a3a34-163">**封鎖已被取代：** 封鎖使用者直接流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="a3a34-163">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="a3a34-164">但使用者 overrode 區塊以流覽至 URL。</span><span class="sxs-lookup"><span data-stu-id="a3a34-164">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="a3a34-165">**擱置的判定略過：** 使用者呈現的是 [引爆] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a3a34-165">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="a3a34-166">但使用者 overrode 郵件以存取 URL。</span><span class="sxs-lookup"><span data-stu-id="a3a34-166">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="a3a34-167">**錯誤：** 使用者呈現錯誤頁面，或捕獲判定結果時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="a3a34-167">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="a3a34-168">**失敗：** 捕獲判定時，發生未知的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="a3a34-168">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="a3a34-169">使用者可能已按一下透過 URL。</span><span class="sxs-lookup"><span data-stu-id="a3a34-169">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="a3a34-170">啟動自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="a3a34-170">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="a3a34-171">Microsoft Defender 的「自動化調查和回應」功能可在 *Office 365 方案 2* 和 *Office 365 E5* 中取得。</span><span class="sxs-lookup"><span data-stu-id="a3a34-171">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="a3a34-172">[自動化調查和回應](automated-investigation-response-office.md) 可儲存您的安全性運作小組時間和精力，以調查及緩解 cyberattacks。</span><span class="sxs-lookup"><span data-stu-id="a3a34-172">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="a3a34-173">除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。</span><span class="sxs-lookup"><span data-stu-id="a3a34-173">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="a3a34-174">如需詳細資訊，請參閱 [範例：安全性管理員會從瀏覽器觸發調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="a3a34-174">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="a3a34-175">其他文章</span><span class="sxs-lookup"><span data-stu-id="a3a34-175">Other articles</span></span>

[<span data-ttu-id="a3a34-176">使用電子郵件實體頁面調查電子郵件</span><span class="sxs-lookup"><span data-stu-id="a3a34-176">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
