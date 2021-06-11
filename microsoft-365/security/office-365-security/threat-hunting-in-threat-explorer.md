---
title: Microsoft Defender for Office 365 威脅瀏覽器中的威脅搜尋
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
description: 使用安全規範中心中的威脅瀏覽器或即時偵測 &amp; ，以有效地調查和回應威脅。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65fe67103d9a380c63a0362594c23290457ea3aa
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52295229"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="43267-103">Microsoft Defender for Office 365 威脅瀏覽器中的威脅搜尋</span><span class="sxs-lookup"><span data-stu-id="43267-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="43267-104">本文內容：</span><span class="sxs-lookup"><span data-stu-id="43267-104">In this article:</span></span>

- [<span data-ttu-id="43267-105">威脅瀏覽器逐步流覽</span><span class="sxs-lookup"><span data-stu-id="43267-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="43267-106">電子郵件調查</span><span class="sxs-lookup"><span data-stu-id="43267-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="43267-107">電子郵件修復</span><span class="sxs-lookup"><span data-stu-id="43267-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="43267-108">威脅搜尋體驗的增強功能</span><span class="sxs-lookup"><span data-stu-id="43267-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="43267-109">這是 **威脅 Explorer (Explorer)**、**電子郵件安全性** 及 **Explorer 和即時** 偵測 (基礎的 **3 篇文章** 中的一部分，例如工具間的差異，以及操作) 所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="43267-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="43267-110">此系列中的其他兩篇文章是 [使用威脅瀏覽器的電子郵件安全性](email-security-in-microsoft-defender.md) 和 [威脅瀏覽器，以及即時的偵測基礎知識](real-time-detections.md)。</span><span class="sxs-lookup"><span data-stu-id="43267-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="43267-111">**適用於**</span><span class="sxs-lookup"><span data-stu-id="43267-111">**Applies to**</span></span>
- [<span data-ttu-id="43267-112">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="43267-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="43267-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43267-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="43267-114">如果您的組織有 [Office 365 的 Microsoft Defender](defender-for-office-365.md)，而且您具有 [許可權](#required-licenses-and-permissions)，您可以使用 **Explorer** 或 **即時** 偵測來偵測和修正威脅。</span><span class="sxs-lookup"><span data-stu-id="43267-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span> 

<span data-ttu-id="43267-115">在 [ **安全性 & 規範中心**] 中，移至 [ **威脅管理**]，然後選擇 [ **Explorer** ] _或_[ **即時** 偵測]。</span><span class="sxs-lookup"><span data-stu-id="43267-115">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="43267-116">使用 Microsoft Defender Office 365 方案2，您會看到：</span><span class="sxs-lookup"><span data-stu-id="43267-116">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="43267-117">使用 Microsoft Defender Office 365 方案1，您會看到：</span><span class="sxs-lookup"><span data-stu-id="43267-117">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="43267-120">使用這些工具，您可以：</span><span class="sxs-lookup"><span data-stu-id="43267-120">With these tools, you can:</span></span>

- <span data-ttu-id="43267-121">查看 Microsoft 365 安全性功能偵測到的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="43267-121">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="43267-122">查看網路釣魚 URL，然後按一下 [已判定資料]</span><span class="sxs-lookup"><span data-stu-id="43267-122">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="43267-123">從瀏覽器中的視圖開始自動調查和回應程式</span><span class="sxs-lookup"><span data-stu-id="43267-123">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="43267-124">調查惡意電子郵件及其他</span><span class="sxs-lookup"><span data-stu-id="43267-124">Investigate malicious email, and more</span></span>

<span data-ttu-id="43267-125">如需詳細資訊，請參閱 [使用威脅瀏覽器的電子郵件安全性](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="43267-125">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span> 

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="43267-126">威脅瀏覽器逐步流覽</span><span class="sxs-lookup"><span data-stu-id="43267-126">Threat Explorer walk-through</span></span>

<span data-ttu-id="43267-127">在 Microsoft Defender for Office 365 中，有兩個訂閱者案（方案1和方案2）。</span><span class="sxs-lookup"><span data-stu-id="43267-127">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="43267-128">手動運作的威脅搜尋工具，都存在於兩個計畫中的不同名稱和不同功能。</span><span class="sxs-lookup"><span data-stu-id="43267-128">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="43267-129">Office 365 方案1的 Defender 使用 *即時* 偵測，也就是 *威脅瀏覽器* 的子集 (也稱為計畫2中的 *Explorer*) 搜尋工具。</span><span class="sxs-lookup"><span data-stu-id="43267-129">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="43267-130">在此系列文章中，大部分的範例是使用完整威脅瀏覽器建立的。</span><span class="sxs-lookup"><span data-stu-id="43267-130">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="43267-131">管理員應該在即時偵測中測試任何步驟，以查看其適用的位置。</span><span class="sxs-lookup"><span data-stu-id="43267-131">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="43267-132">若要開啟 Explorer 工具，請移至 **Security & 合規性中心**  >  **威脅管理**  >  **瀏覽器** (或 **即時** 偵測) 。</span><span class="sxs-lookup"><span data-stu-id="43267-132">To open the Explorer tool, go to **Security & Compliance Center** > **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="43267-133">依預設，您會到達 **惡意軟體** 頁面，但使用 [View] （ **查看** ）下拉式功能表以熟悉您的選項。</span><span class="sxs-lookup"><span data-stu-id="43267-133">By default, you’ll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="43267-134">如果您要搜尋網路釣魚網路，或鑽研至威脅活動，請選擇這些視圖。</span><span class="sxs-lookup"><span data-stu-id="43267-134">If you’re hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-135">![威脅瀏覽器中的 View 下拉式清單](../../media/threat-explorer-view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="43267-135">![View drop down in Threat Explorer](../../media/threat-explorer-view-drop-down.png)</span></span>

<span data-ttu-id="43267-136">一旦安全性作業 (Sec Op) 人員會選取他們想要查看的資料、範圍是否如使用者 **報送** 或更大的查看（如 **所有電子郵件**），他們可以使用 [ **寄件者** ] 按鈕進一步篩選。</span><span class="sxs-lookup"><span data-stu-id="43267-136">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="43267-137">請記得選取 [重新整理]，以完成篩選動作。</span><span class="sxs-lookup"><span data-stu-id="43267-137">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-138">![威脅瀏覽器中的寄件者按鈕](../../media/threat-explorer-sender-button.png)</span><span class="sxs-lookup"><span data-stu-id="43267-138">![Sender button in Threat Explorer](../../media/threat-explorer-sender-button.png)</span></span>

<span data-ttu-id="43267-139">若要在瀏覽器中精煉焦點或即時偵測，您可以在層中想到。</span><span class="sxs-lookup"><span data-stu-id="43267-139">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="43267-140">第一個是 **View**。</span><span class="sxs-lookup"><span data-stu-id="43267-140">The first is **View**.</span></span> <span data-ttu-id="43267-141">第二個可以視為 *篩選的焦點*。</span><span class="sxs-lookup"><span data-stu-id="43267-141">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="43267-142">例如，您可以透過記錄決策來回溯您在尋找威脅時所採取的步驟：若要在瀏覽器中找出問題， **我選擇具有收件者篩選器焦點的惡意程式碼視圖**。</span><span class="sxs-lookup"><span data-stu-id="43267-142">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="43267-143">這可讓您更輕鬆 retracing 步驟。</span><span class="sxs-lookup"><span data-stu-id="43267-143">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="43267-144">如果 Sec Ops 使用標籤來標示其考慮高值 **目標的帳戶** ，他們可以像網路釣魚視圖一樣，進行選擇 *篩選焦點 (包括使用) 的日期範圍*。</span><span class="sxs-lookup"><span data-stu-id="43267-144">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="43267-145">這會在時間範圍 (等時間範圍內，向使用者顯示其高價值的使用者目標，例如，當某些網路釣魚攻擊針對其行業) 所發生的情況。</span><span class="sxs-lookup"><span data-stu-id="43267-145">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span> 

<span data-ttu-id="43267-146">您可以使用日期範圍控制項，對日期範圍進行改進。</span><span class="sxs-lookup"><span data-stu-id="43267-146">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="43267-147">在這裡，您可以在 **惡意** 代碼視圖中查看瀏覽器，並使用 **偵測技術** 篩選焦點。</span><span class="sxs-lookup"><span data-stu-id="43267-147">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="43267-148">但它是可讓 Sec Ops 小組深入瞭解的「 **高級篩選** 」按鈕。</span><span class="sxs-lookup"><span data-stu-id="43267-148">But it’s the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-149">![威脅瀏覽器中的高級篩選](../../media/threat-explorer-advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="43267-149">![Advanced filter in Threat Explorer](../../media/threat-explorer-advanced-filter.png)</span></span>

<span data-ttu-id="43267-150">按一下 [ **高級] 篩選器** 會彈出面板，讓每個 hunters 建立查詢本身，讓它們包含或排除所需查看的資訊。</span><span class="sxs-lookup"><span data-stu-id="43267-150">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="43267-151">瀏覽器頁面上的圖表和表格都會反映其結果。</span><span class="sxs-lookup"><span data-stu-id="43267-151">Both the chart and table on the Explorer page will reflect their results.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-152">![查詢的結果](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="43267-152">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="43267-153">使用 [ **欄選項** ] 按鈕，以取得表格中最有説明的資訊類型：</span><span class="sxs-lookup"><span data-stu-id="43267-153">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-154">![高亮顯示欄選項按鈕](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="43267-154">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-155">![欄中可用的選項](../../media/threat-explorer-column-options-details.png)</span><span class="sxs-lookup"><span data-stu-id="43267-155">![Available options in Columns](../../media/threat-explorer-column-options-details.png)</span></span>

<span data-ttu-id="43267-156">在同一個 mien 中，請務必測試顯示選項。</span><span class="sxs-lookup"><span data-stu-id="43267-156">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="43267-157">不同的物件會對相同資料的不同簡報有很好的反應。</span><span class="sxs-lookup"><span data-stu-id="43267-157">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="43267-158">針對有些檢視器， **電子郵件來源** 地圖可顯示威脅的普及或更快，比其旁邊的 [ **市場活動顯示** ] 選項更快。</span><span class="sxs-lookup"><span data-stu-id="43267-158">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="43267-159">每秒 Op 可以利用這些顯示效果，使底線成為安全性和保護的必要點，或用於進行後續比較，以示範其動作的效能。</span><span class="sxs-lookup"><span data-stu-id="43267-159">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-160">![電子郵件來源地圖](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="43267-160">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-161">![市場活動顯示選項](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="43267-161">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="43267-162">電子郵件調查</span><span class="sxs-lookup"><span data-stu-id="43267-162">Email investigation</span></span>

<span data-ttu-id="43267-163">當您看到可疑的電子郵件時，按一下名稱以展開右側的飛出視窗。</span><span class="sxs-lookup"><span data-stu-id="43267-163">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="43267-164">在這裡，允許 Sec Ops 的橫幅會看到 [ [電子郵件實體] 頁面](mdo-email-entity-page.md) 可供使用。</span><span class="sxs-lookup"><span data-stu-id="43267-164">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="43267-165">[電子郵件實體] 頁面會將可在 [ **詳細** 資料]、[ **附件**]、[ **裝置**] 底下找到的內容，包含更多組織的資料。</span><span class="sxs-lookup"><span data-stu-id="43267-165">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="43267-166">這包括 DMARC 結果、純文字顯示（含副本選項的電子郵件標題）、判定已安全引爆之附件的資訊，以及 detonations 丟棄的檔案， (可以包含已連接的 IP 位址，以及) 的頁面或檔案的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="43267-166">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="43267-167">URLs 及其 verdicts 也會以報告的類似詳細資料列出。</span><span class="sxs-lookup"><span data-stu-id="43267-167">URLs and their verdicts are also listed with similar details reported.</span></span> 

<span data-ttu-id="43267-168">當您到達此階段時，[電子郵件實體] 頁面將對最後一個步驟（*修正*）很重要。</span><span class="sxs-lookup"><span data-stu-id="43267-168">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-169">![電子郵件實體頁面](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="43267-169">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="43267-170">若要深入瞭解 [ **分析** ] 索引標籤上的 [豐富的電子郵件實體) ] 頁面 (，包括引爆附件的結果、包含 URLs 的結果，以及安全的電子郵件預覽，請按一下 [這裡](mdo-email-entity-page.md)。</span><span class="sxs-lookup"><span data-stu-id="43267-170">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-171">![電子郵件實體頁面的 [分析] 索引標籤](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="43267-171">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="43267-172">電子郵件修復</span><span class="sxs-lookup"><span data-stu-id="43267-172">Email remediation</span></span>

<span data-ttu-id="43267-173">當 Sec Op 人員判斷電子郵件成為威脅之後，下一個瀏覽器或即時偵測步驟便會處理威脅並修正該威脅。</span><span class="sxs-lookup"><span data-stu-id="43267-173">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="43267-174">若要執行此動作，可以傳回威脅瀏覽器，選取問題電子郵件的核取方塊，然後使用 [ **動作** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="43267-174">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-175">![威脅瀏覽器中的 [動作] 按鈕](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="43267-175">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="43267-176">在這裡，分析員可以採取類似于垃圾郵件、網路釣魚或惡意程式碼等動作來報告郵件，也就是在您有計劃 2) 的情況下，可以包含觸發自動調查和回應 (或 AIR) 行動手冊 (的其他調查。</span><span class="sxs-lookup"><span data-stu-id="43267-176">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="43267-177">或者，也可以將郵件報告為乾淨。</span><span class="sxs-lookup"><span data-stu-id="43267-177">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-178">![[動作] 下拉式清單](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="43267-178">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="43267-179">威脅搜尋體驗的增強功能</span><span class="sxs-lookup"><span data-stu-id="43267-179">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="43267-180">警示識別碼</span><span class="sxs-lookup"><span data-stu-id="43267-180">Alert ID</span></span>

<span data-ttu-id="43267-181">從警示流覽至威脅瀏覽器時，會依照 **警示識別碼** 篩選該 **視圖**。</span><span class="sxs-lookup"><span data-stu-id="43267-181">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="43267-182">這也適用于即時偵測。</span><span class="sxs-lookup"><span data-stu-id="43267-182">This also applies in Real-time detection.</span></span> <span data-ttu-id="43267-183">會顯示與特定警示相關的郵件，以及 (計數) 的電子郵件總數。</span><span class="sxs-lookup"><span data-stu-id="43267-183">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="43267-184">您將能夠查看郵件是否屬於警示的一部分，以及從該郵件流覽至相關的警示。</span><span class="sxs-lookup"><span data-stu-id="43267-184">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="43267-185">最後，警示識別碼會包含在 URL 中，例如： `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span><span class="sxs-lookup"><span data-stu-id="43267-185">Finally, alert ID is included in the URL, for example: `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-186">![警示識別碼的篩選](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="43267-186">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-187">![詳細資料快顯視窗中的警示識別碼](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="43267-187">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="43267-188">延伸 Explorer (和即時偵測) 資料保留與試用承租人的搜尋限制</span><span class="sxs-lookup"><span data-stu-id="43267-188">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span> 

<span data-ttu-id="43267-189">在此變更中，分析者將可以搜尋並篩選超過30天的電子郵件資料 (會在威脅瀏覽器中增加7天) ，在威脅瀏覽器中增加，針對 Office P1 和 P2 試用租使用者的 Defender 進行即時偵測。</span><span class="sxs-lookup"><span data-stu-id="43267-189">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="43267-190">這不會影響 P1 和 P2 E5 客戶的任何實際執行承租人，保留預設值為已30天。</span><span class="sxs-lookup"><span data-stu-id="43267-190">This doesn’t impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="43267-191">更新的匯出限制</span><span class="sxs-lookup"><span data-stu-id="43267-191">Updated Export limit</span></span> 

<span data-ttu-id="43267-192">可以從威脅瀏覽器匯出的電子郵件記錄數目現在是 200000 (為 9990) 。</span><span class="sxs-lookup"><span data-stu-id="43267-192">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="43267-193">可以匯出的一組資料行不會變更。</span><span class="sxs-lookup"><span data-stu-id="43267-193">The set of columns that can be exported is unchanged.</span></span> 

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="43267-194">威脅瀏覽器中的標記</span><span class="sxs-lookup"><span data-stu-id="43267-194">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="43267-195">[使用者標記] 功能是在預覽中，並非所有人都可以使用。</span><span class="sxs-lookup"><span data-stu-id="43267-195">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="43267-196">此外，預覽可能也會變更。</span><span class="sxs-lookup"><span data-stu-id="43267-196">Also, Previews are subject to change.</span></span> <span data-ttu-id="43267-197">如需發行排程的相關資訊，請參閱 Microsoft 365 藍圖。</span><span class="sxs-lookup"><span data-stu-id="43267-197">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="43267-198">使用者標記識別 Microsoft Defender 中 Office 365 的特定使用者群組。</span><span class="sxs-lookup"><span data-stu-id="43267-198">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="43267-199">如需標記的相關資訊（包括授權和設定），請參閱 [User tags](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="43267-199">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="43267-200">在威脅瀏覽器中，您可以在下列體驗中看到使用者標記的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="43267-200">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="43267-201">電子郵件格線視圖</span><span class="sxs-lookup"><span data-stu-id="43267-201">Email grid view</span></span>

<span data-ttu-id="43267-202">當分析員查看 [ **標記** ] 欄的電子郵件格線時，他們會看到所有已套用到寄件者或收件者信箱的標記。</span><span class="sxs-lookup"><span data-stu-id="43267-202">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="43267-203">依預設，會先顯示「 *優先順序」帳戶* 之類的系統標記。</span><span class="sxs-lookup"><span data-stu-id="43267-203">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-204">![在電子郵件格線視圖中篩選標記](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="43267-204">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="43267-205">篩選</span><span class="sxs-lookup"><span data-stu-id="43267-205">Filtering</span></span>

<span data-ttu-id="43267-206">標記可用作篩選。</span><span class="sxs-lookup"><span data-stu-id="43267-206">Tags can be used as filters.</span></span> <span data-ttu-id="43267-207">以這種方式，只在優先順序帳戶中加以搜尋，或使用特定的使用者標記案例。</span><span class="sxs-lookup"><span data-stu-id="43267-207">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="43267-208">您也可以排除包含某些標記的結果。</span><span class="sxs-lookup"><span data-stu-id="43267-208">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="43267-209">結合標記與其他篩選和日期範圍，以縮小您的調查範圍。</span><span class="sxs-lookup"><span data-stu-id="43267-209">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span> 

<span data-ttu-id="43267-210">[![篩選標記](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="43267-210">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-211">![不篩選標記](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="43267-211">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="43267-212">電子郵件詳細資料快顯視窗</span><span class="sxs-lookup"><span data-stu-id="43267-212">Email detail flyout</span></span>

<span data-ttu-id="43267-213">若要查看寄件者和收件者的個別標記，請選取電子郵件以開啟 [郵件詳細資料] 浮出。</span><span class="sxs-lookup"><span data-stu-id="43267-213">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="43267-214">在 [ **摘要** ] 索引標籤上，會分別顯示寄件者和收件者標記。</span><span class="sxs-lookup"><span data-stu-id="43267-214">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="43267-215">寄件者和收件者個別標記的相關資訊可匯出為 CSV 資料。</span><span class="sxs-lookup"><span data-stu-id="43267-215">The information about individual tags for sender and recipient can be exported as CSV data.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-216">![電子郵件詳細資料標記](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="43267-216">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="43267-217">標記資訊也會顯示在 URL 中按一下 [飛入]。</span><span class="sxs-lookup"><span data-stu-id="43267-217">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="43267-218">若要查看，請移至網路釣魚或所有電子郵件 view > **URLs** 或 **URL 按一下** ] 索引標籤。選取個別的 [URL] 飛出，以查看有關該 URL 之按一下的其他詳細資料，包括任何與該按一下相關聯的標記。</span><span class="sxs-lookup"><span data-stu-id="43267-218">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="43267-219">更新時程表視圖</span><span class="sxs-lookup"><span data-stu-id="43267-219">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-220">![URL 標記](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="43267-220">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="43267-221">觀看[此影片](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="43267-221">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="43267-222">延伸功能</span><span class="sxs-lookup"><span data-stu-id="43267-222">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="43267-223">主要目標使用者</span><span class="sxs-lookup"><span data-stu-id="43267-223">Top targeted users</span></span>

<span data-ttu-id="43267-224">主要惡意程式碼系列會顯示惡意程式碼區段中 **主要的目標使用者** 。</span><span class="sxs-lookup"><span data-stu-id="43267-224">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="43267-225">主要的目標使用者將透過網路釣魚和所有電子郵件視圖延伸。</span><span class="sxs-lookup"><span data-stu-id="43267-225">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="43267-226">分析員將可以查看前5位目標使用者，以及每個視圖中每位使用者的嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="43267-226">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span> 

<span data-ttu-id="43267-227">安全性作業使用者可以匯出目標使用者的清單，最多可匯出3000的限制，以及嘗試的次數，以供每個電子郵件 view 之離線分析使用。</span><span class="sxs-lookup"><span data-stu-id="43267-227">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="43267-228">此外，選取 [嘗試次數] (例如，13在下列的圖像中嘗試) 會在威脅瀏覽器中開啟篩選的視圖，這樣您就能看到有關電子郵件的詳細資料，以及該使用者的威脅。</span><span class="sxs-lookup"><span data-stu-id="43267-228">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-229">![主要目標使用者](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="43267-229">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="43267-230">傳輸規則 Exchange</span><span class="sxs-lookup"><span data-stu-id="43267-230">Exchange transport rules</span></span>

<span data-ttu-id="43267-231">安全性作業小組能夠在電子郵件格線視圖中查看所有 Exchange 的傳輸規則 (或郵件流程規則) 套用至郵件。</span><span class="sxs-lookup"><span data-stu-id="43267-231">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="43267-232">選取格線中的 [**欄選項**]，然後從 [欄] 選項 **新增 Exchange 傳輸規則**。</span><span class="sxs-lookup"><span data-stu-id="43267-232">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="43267-233">在電子郵件中的 [**詳細資料**] 快顯視窗中也會顯示 Exchange 傳輸規則] 選項。</span><span class="sxs-lookup"><span data-stu-id="43267-233">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span> 

<span data-ttu-id="43267-234">會出現套用至郵件的傳輸規則名稱及 Guid。</span><span class="sxs-lookup"><span data-stu-id="43267-234">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="43267-235">分析員將可以使用傳輸規則的名稱來搜尋郵件。</span><span class="sxs-lookup"><span data-stu-id="43267-235">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="43267-236">這是包含搜尋，也就是您也可以進行部分搜尋。</span><span class="sxs-lookup"><span data-stu-id="43267-236">This is a CONTAINS search, which means you can do partial searches as well.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="43267-237">Exchange 傳輸規則搜尋與名稱可用性取決於指派給您的特定角色。</span><span class="sxs-lookup"><span data-stu-id="43267-237">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="43267-238">您必須具有下列其中一個角色或許可權，才能查看傳輸規則名稱和搜尋。</span><span class="sxs-lookup"><span data-stu-id="43267-238">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="43267-239">不過，即使沒有下列角色或許可權，分析員還是可以在電子郵件詳細資料中看到傳輸規則標籤及 GUID 資訊。</span><span class="sxs-lookup"><span data-stu-id="43267-239">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="43267-240">其他記錄流覽的電子郵件格線、電子郵件 flyouts、篩選和匯出不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="43267-240">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="43267-241">Exchange Online僅資料遺失防護：全部</span><span class="sxs-lookup"><span data-stu-id="43267-241">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="43267-242">Exchange Online僅 O365SupportViewConfig： All</span><span class="sxs-lookup"><span data-stu-id="43267-242">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="43267-243">Microsoft Azure Active Directory 或 Exchange Online 安全性管理員： All</span><span class="sxs-lookup"><span data-stu-id="43267-243">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="43267-244">Azure Active Directory 或 Exchange Online 安全性讀者： All</span><span class="sxs-lookup"><span data-stu-id="43267-244">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="43267-245">Exchange Online僅傳輸規則：全部</span><span class="sxs-lookup"><span data-stu-id="43267-245">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="43267-246">Exchange Online僅 View-Only 設定：全部</span><span class="sxs-lookup"><span data-stu-id="43267-246">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="43267-247">在電子郵件格線、詳細資料浮出和匯出的 CSV 中，ETRs 會以如下所示的名稱/GUID 呈現。</span><span class="sxs-lookup"><span data-stu-id="43267-247">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="43267-248">![Exchange傳輸規則](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="43267-248">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="43267-249">輸入連接器</span><span class="sxs-lookup"><span data-stu-id="43267-249">Inbound connectors</span></span>

<span data-ttu-id="43267-250">連接器是一組指示，可自訂您的電子郵件進出 Microsoft 365 或 Office 365 組織的方式。</span><span class="sxs-lookup"><span data-stu-id="43267-250">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="43267-251">它們可讓您套用任何安全性限制或控制項。</span><span class="sxs-lookup"><span data-stu-id="43267-251">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="43267-252">在 [威脅瀏覽器] 中，您可以查看與電子郵件相關的連接器，並搜尋使用連接器名稱的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="43267-252">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span> 

<span data-ttu-id="43267-253">連接器的搜尋是包含查詢，這表示部分關鍵字搜尋可以運作：</span><span class="sxs-lookup"><span data-stu-id="43267-253">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43267-254">![連接器詳細資料](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="43267-254">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="43267-255">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="43267-255">Required licenses and permissions</span></span>

<span data-ttu-id="43267-256">您必須具有[Microsoft Defender Office 365](defender-for-office-365.md) ，才能使用 Explorer 或即時偵測。</span><span class="sxs-lookup"><span data-stu-id="43267-256">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="43267-257">Explorer 會包含在 Office 365 方案2的 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="43267-257">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="43267-258">在 Office 365 方案1的 Defender 中包含即時偵測報告。</span><span class="sxs-lookup"><span data-stu-id="43267-258">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="43267-259">規劃為所有應受 Office 365 Defender 保護的使用者指派授權。</span><span class="sxs-lookup"><span data-stu-id="43267-259">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="43267-260">瀏覽器和即時偵測顯示已授權使用者的偵測資料。</span><span class="sxs-lookup"><span data-stu-id="43267-260">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="43267-261">若要查看和使用 Explorer 或即時偵測，您必須具備下列各項：</span><span class="sxs-lookup"><span data-stu-id="43267-261">To view and use Explorer or Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="43267-262">針對安全性 & 規範中心：</span><span class="sxs-lookup"><span data-stu-id="43267-262">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="43267-263">組織管理</span><span class="sxs-lookup"><span data-stu-id="43267-263">Organization Management</span></span>
  - <span data-ttu-id="43267-264">安全性管理員 (可以在 Azure Active Directory 系統管理中心 (中指派 <https://aad.portal.azure.com>) </span><span class="sxs-lookup"><span data-stu-id="43267-264">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="43267-265">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="43267-265">Security Reader</span></span>

- <span data-ttu-id="43267-266">Exchange Online：</span><span class="sxs-lookup"><span data-stu-id="43267-266">For Exchange Online:</span></span>

  - <span data-ttu-id="43267-267">組織管理</span><span class="sxs-lookup"><span data-stu-id="43267-267">Organization Management</span></span>
  - <span data-ttu-id="43267-268">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="43267-268">View-Only Organization Management</span></span>
  - <span data-ttu-id="43267-269">僅限檢視收件者</span><span class="sxs-lookup"><span data-stu-id="43267-269">View-Only Recipients</span></span>
  - <span data-ttu-id="43267-270">合規性管理</span><span class="sxs-lookup"><span data-stu-id="43267-270">Compliance Management</span></span>

<span data-ttu-id="43267-271">若要深入了解角色和權限，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="43267-271">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="43267-272">安全性與合規性中心的權限</span><span class="sxs-lookup"><span data-stu-id="43267-272">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="43267-273">Exchange Online 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="43267-273">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="43267-274">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="43267-274">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="43267-275">其他資訊</span><span class="sxs-lookup"><span data-stu-id="43267-275">More information</span></span>

- [<span data-ttu-id="43267-276">尋找並調查傳送的惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="43267-276">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md) 
- [<span data-ttu-id="43267-277">檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案</span><span class="sxs-lookup"><span data-stu-id="43267-277">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md) 
- [<span data-ttu-id="43267-278">取得威脅瀏覽器中的視圖 (和即時偵測的概覽) </span><span class="sxs-lookup"><span data-stu-id="43267-278">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md) 
- [<span data-ttu-id="43267-279">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="43267-279">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report) 
- [<span data-ttu-id="43267-280">Microsoft 威脅防護的自動化調查及回應</span><span class="sxs-lookup"><span data-stu-id="43267-280">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md) 
- [<span data-ttu-id="43267-281">使用電子郵件實體頁面調查電子郵件</span><span class="sxs-lookup"><span data-stu-id="43267-281">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)