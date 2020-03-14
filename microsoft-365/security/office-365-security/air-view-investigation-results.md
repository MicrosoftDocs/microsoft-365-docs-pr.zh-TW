---
title: 在 Office 365 中查看自動調查的結果
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
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
ms.collection: M365-security-compliance
description: 在 Office 365 的自動調查期間和之後，您可以查看結果和重要結果。
ms.openlocfilehash: 638559efe5f7028a647b466c030a339c677601ce
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633841"
---
# <a name="details-and-results-of-an-automated-investigation-in-office-365"></a><span data-ttu-id="11d2b-104">Office 365 中自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="11d2b-104">Details and results of an automated investigation in Office 365</span></span>

<span data-ttu-id="11d2b-105">當[Office 365 的「高級威脅防護](office-365-atp.md)」會進行[自動調查](office-365-air.md)時，系統會在自動化調查程式期間和之後使用該調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="11d2b-105">When an [automated investigation](office-365-air.md) occurs in [Office 365 Advanced Threat Protection](office-365-atp.md), details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="11d2b-106">如果您擁有必要權限，您可以在調查詳細資料檢視中查看這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="11d2b-106">If you have the necessary permissions, you can view those details in an investigation details view.</span></span> <span data-ttu-id="11d2b-107">調查詳細資料檢視可提供您最新的狀態，以及核准任何待核准動作的能力。</span><span class="sxs-lookup"><span data-stu-id="11d2b-107">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="11d2b-108">檢視調查的詳細資料</span><span class="sxs-lookup"><span data-stu-id="11d2b-108">View details of an investigation</span></span>

1. <span data-ttu-id="11d2b-109">移至 [https://protection.office.com](https://protection.office.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="11d2b-109">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="11d2b-110">這樣會帶您前往安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="11d2b-110">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="11d2b-111">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="11d2b-111">Do one of the following:</span></span>

    - <span data-ttu-id="11d2b-112">移至 [威脅管理]\*\*\*\*  >  [儀表板]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="11d2b-112">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="11d2b-113">這樣會帶您前往[安全性儀表板](security-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="11d2b-113">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="11d2b-114">您的 AIR 小工具會顯示在[安全性儀表板](security-dashboard.md)上方。</span><span class="sxs-lookup"><span data-stu-id="11d2b-114">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="11d2b-115">選取小工具，例如**調查摘要**。</span><span class="sxs-lookup"><span data-stu-id="11d2b-115">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="11d2b-116">移至 [威脅管理]\*\*\*\*  >  [調查]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11d2b-116">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="11d2b-117">這兩種方法都會帶您前往調查清單。</span><span class="sxs-lookup"><span data-stu-id="11d2b-117">Either method takes you to a list of investigations.</span></span>

    ![AIR 的主要調查頁面](../../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="11d2b-119">在調查清單中，選取 [識別碼]\*\*\*\* 欄中的項目。</span><span class="sxs-lookup"><span data-stu-id="11d2b-119">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="11d2b-120">這樣會開啟調查詳細資料頁面，從檢視中的調查圖形開始。</span><span class="sxs-lookup"><span data-stu-id="11d2b-120">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![AIR 調查圖形頁面](../../media/air-investigationgraphpage.png)

   <span data-ttu-id="11d2b-122">使用各個索引標籤深入了解調查。</span><span class="sxs-lookup"><span data-stu-id="11d2b-122">Use the various tabs to learn more about the investigation.</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="11d2b-123">檢視與調查相關警示的詳細資料</span><span class="sxs-lookup"><span data-stu-id="11d2b-123">View details about an alert related to an investigation</span></span>

<span data-ttu-id="11d2b-124">某些類型的警示會在 Office 365 中觸發自動化調查。</span><span class="sxs-lookup"><span data-stu-id="11d2b-124">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="11d2b-125">若要深入了解，請參閱[警示](automated-investigation-response-office.md#alerts)。</span><span class="sxs-lookup"><span data-stu-id="11d2b-125">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="11d2b-126">使用下列程序來檢視與自動化調查相關聯警示的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="11d2b-126">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="11d2b-127">移至 [https://protection.office.com](https://protection.office.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="11d2b-127">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="11d2b-128">這樣會帶您前往安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="11d2b-128">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="11d2b-129">移至 [威脅管理]\*\*\*\*  >  [調查]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11d2b-129">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="11d2b-130">在調查清單中，選取 [識別碼]\*\*\*\* 欄中的項目。</span><span class="sxs-lookup"><span data-stu-id="11d2b-130">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="11d2b-131">開啟調查詳細資料時，選取 [警示]\*\*\*\* 索引標籤。觸發調查的任何警示都會列在此處。</span><span class="sxs-lookup"><span data-stu-id="11d2b-131">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="11d2b-132">選取清單中的項目。</span><span class="sxs-lookup"><span data-stu-id="11d2b-132">Select an item in the list.</span></span> <span data-ttu-id="11d2b-133">隨即開啟一個飛出視窗，其中包含警示的詳細資料以及其他資訊和動作的連結。</span><span class="sxs-lookup"><span data-stu-id="11d2b-133">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="11d2b-134">檢閱飛出視窗中的資訊，並視特定警示採取動作，例如**解決**、**隱藏**，或**通知使用者**。</span><span class="sxs-lookup"><span data-stu-id="11d2b-134">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="11d2b-135">**解決**等同於關閉警示</span><span class="sxs-lookup"><span data-stu-id="11d2b-135">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="11d2b-136">**隱藏**會導致原則在指定時段不觸發警示</span><span class="sxs-lookup"><span data-stu-id="11d2b-136">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="11d2b-137">**通知使用者**會啟動電子郵件，並且已輸入使用者的電子郵件地址，讓您的安全性操作小組輸入要給這些使用者的訊息。</span><span class="sxs-lookup"><span data-stu-id="11d2b-137">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="11d2b-138">(這類似於使用[威脅總管](threat-explorer.md)將訊息傳送給收件者。)</span><span class="sxs-lookup"><span data-stu-id="11d2b-138">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="how-to-use-the-various-tabs"></a><span data-ttu-id="11d2b-139">如何使用各種選項卡</span><span class="sxs-lookup"><span data-stu-id="11d2b-139">How to use the various tabs</span></span>

<span data-ttu-id="11d2b-140">下列各節會逐步引導您完成「自動化調查」頁面上的各項索引標籤，以及如何使用此資訊。</span><span class="sxs-lookup"><span data-stu-id="11d2b-140">The following sections walk you through the various tabs on the automated investigations page and how you can use the information.</span></span>

### <a name="automated-investigations-page"></a><span data-ttu-id="11d2b-141">自動調查頁面</span><span class="sxs-lookup"><span data-stu-id="11d2b-141">Automated investigations page</span></span>

<span data-ttu-id="11d2b-142">「自動調查」頁面會顯示您組織的調查及其目前狀態。</span><span class="sxs-lookup"><span data-stu-id="11d2b-142">The automated investigations page shows your organization's investigations and their current states.</span></span>

![AIR 的主要調查頁面](../../media/air-maininvestigationpage.png) 
  
<span data-ttu-id="11d2b-144">您可以：</span><span class="sxs-lookup"><span data-stu-id="11d2b-144">You can:</span></span>
- <span data-ttu-id="11d2b-145">直接流覽至調查（選取**調查識別碼**）。</span><span class="sxs-lookup"><span data-stu-id="11d2b-145">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="11d2b-146">套用篩選器。</span><span class="sxs-lookup"><span data-stu-id="11d2b-146">Apply filters.</span></span> <span data-ttu-id="11d2b-147">您可以選擇**調查類型**、**時間範圍**、**狀態**或兩者的組合。</span><span class="sxs-lookup"><span data-stu-id="11d2b-147">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="11d2b-148">將資料匯出至 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="11d2b-148">Export the data to a .csv file.</span></span>

<span data-ttu-id="11d2b-149">調查狀態會指出分析和動作的進度。</span><span class="sxs-lookup"><span data-stu-id="11d2b-149">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="11d2b-150">調查執行時，會變更狀態，以指出是否發現威脅，以及是否已核准動作。</span><span class="sxs-lookup"><span data-stu-id="11d2b-150">As the investigation runs, status changes to indicate whether threats were found, and whether actions have been approved.</span></span> 

|<span data-ttu-id="11d2b-151">狀態</span><span class="sxs-lookup"><span data-stu-id="11d2b-151">Status</span></span>  |<span data-ttu-id="11d2b-152">含義</span><span class="sxs-lookup"><span data-stu-id="11d2b-152">What it means</span></span>  |
|---------|---------|
|<span data-ttu-id="11d2b-153">啟動中</span><span class="sxs-lookup"><span data-stu-id="11d2b-153">Starting</span></span> | <span data-ttu-id="11d2b-154">調查已排入佇列，即將開始</span><span class="sxs-lookup"><span data-stu-id="11d2b-154">The investigation is queued to begin soon</span></span> |
|<span data-ttu-id="11d2b-155">正在執行</span><span class="sxs-lookup"><span data-stu-id="11d2b-155">Running</span></span> | <span data-ttu-id="11d2b-156">調查已開始，正在進行分析</span><span class="sxs-lookup"><span data-stu-id="11d2b-156">The investigation has started and is conducting its analysis</span></span> |
|<span data-ttu-id="11d2b-157">找不到威脅</span><span class="sxs-lookup"><span data-stu-id="11d2b-157">No Threats Found</span></span> | <span data-ttu-id="11d2b-158">調查已完成分析，但找不到威脅</span><span class="sxs-lookup"><span data-stu-id="11d2b-158">The investigation has completed its analysis and no threats were found</span></span> |
|<span data-ttu-id="11d2b-159">由系統終止</span><span class="sxs-lookup"><span data-stu-id="11d2b-159">Terminated By System</span></span> | <span data-ttu-id="11d2b-160">調查未關閉，7天后到期</span><span class="sxs-lookup"><span data-stu-id="11d2b-160">The investigation was not closed and expired after 7 days</span></span> |
|<span data-ttu-id="11d2b-161">擱置的動作</span><span class="sxs-lookup"><span data-stu-id="11d2b-161">Pending Action</span></span> | <span data-ttu-id="11d2b-162">調查會發現威脅，並建議採取的動作。</span><span class="sxs-lookup"><span data-stu-id="11d2b-162">The investigation found threats with actions recommended.</span></span>  <span data-ttu-id="11d2b-163">調查在找到初始威脅及建議的動作後會繼續執行，所以您應該先檢查記錄，再核准動作，以查看分析器是否仍在進行中。</span><span class="sxs-lookup"><span data-stu-id="11d2b-163">The investigation continues running after it's found initial threats and recommended actions, so you should check the log before approving actions to see if analyzers are still in-progress.</span></span> |
|<span data-ttu-id="11d2b-164">發現威脅</span><span class="sxs-lookup"><span data-stu-id="11d2b-164">Threats Found</span></span> | <span data-ttu-id="11d2b-165">調查發現威脅，但是威脅沒有在空中內可用的動作。</span><span class="sxs-lookup"><span data-stu-id="11d2b-165">The investigation found threats, but the threats do not have actions available within AIR.</span></span>  <span data-ttu-id="11d2b-166">這些是沒有任何方向 AIR 動作的使用者動作。</span><span class="sxs-lookup"><span data-stu-id="11d2b-166">These are user actions where there is no direction AIR action yet.</span></span> |
|<span data-ttu-id="11d2b-167">修復</span><span class="sxs-lookup"><span data-stu-id="11d2b-167">Remediated</span></span> | <span data-ttu-id="11d2b-168">調查已完成且已完全修正（已核准所有動作）</span><span class="sxs-lookup"><span data-stu-id="11d2b-168">The investigation finished and was fully remediated (all actions were approved)</span></span> |
|<span data-ttu-id="11d2b-169">部分修正</span><span class="sxs-lookup"><span data-stu-id="11d2b-169">Partially Remediated</span></span> | <span data-ttu-id="11d2b-170">調查已完成，且已核准某些建議的動作</span><span class="sxs-lookup"><span data-stu-id="11d2b-170">The investigation finished and some of the recommended actions were approved</span></span> |
|<span data-ttu-id="11d2b-171">由使用者終止</span><span class="sxs-lookup"><span data-stu-id="11d2b-171">Terminated By User</span></span> | <span data-ttu-id="11d2b-172">管理員已終止調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-172">An admin terminated the investigation</span></span> |
|<span data-ttu-id="11d2b-173">失敗</span><span class="sxs-lookup"><span data-stu-id="11d2b-173">Failed</span></span> | <span data-ttu-id="11d2b-174">調查過程中發生錯誤，導致其無法達到威脅的「結論」</span><span class="sxs-lookup"><span data-stu-id="11d2b-174">An error occurred during the investigation that prevented it from reaching a conclusion on threats</span></span> |
|<span data-ttu-id="11d2b-175">依節流佇列</span><span class="sxs-lookup"><span data-stu-id="11d2b-175">Queued By Throttling</span></span> | <span data-ttu-id="11d2b-176">調查因系統處理限制而等候分析（為了保護服務效能）</span><span class="sxs-lookup"><span data-stu-id="11d2b-176">The investigation is waiting for analysis due to system processing limitations (to protect service performance)</span></span> |
|<span data-ttu-id="11d2b-177">由節流終止</span><span class="sxs-lookup"><span data-stu-id="11d2b-177">Terminated By Throttling</span></span> | <span data-ttu-id="11d2b-178">由於調查量和系統處理限制，無法在充足的時間內完成調查。</span><span class="sxs-lookup"><span data-stu-id="11d2b-178">The investigation could not be completed in sufficient time due to investigation volume and system processing limitations.</span></span> <span data-ttu-id="11d2b-179">您可以在瀏覽器中選取電子郵件，並選取 [調查] 動作，以 retrigger 調查。</span><span class="sxs-lookup"><span data-stu-id="11d2b-179">You can retrigger the investigation by selecting the email in Explorer and selecting the Investigate action.</span></span> |

### <a name="investigation-graph"></a><span data-ttu-id="11d2b-180">調查圖表</span><span class="sxs-lookup"><span data-stu-id="11d2b-180">Investigation graph</span></span>

<span data-ttu-id="11d2b-181">當您開啟特定調查時，您會看到 [調查圖形] 頁面。</span><span class="sxs-lookup"><span data-stu-id="11d2b-181">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="11d2b-182">此頁面會顯示所有不同的實體：電子郵件訊息、使用者（及其活動），以及在觸發之警示中自動調查的裝置。</span><span class="sxs-lookup"><span data-stu-id="11d2b-182">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![AIR 調查圖形頁面](../../media/air-investigationgraphpage.png)

<span data-ttu-id="11d2b-184">您可以：</span><span class="sxs-lookup"><span data-stu-id="11d2b-184">You can:</span></span>
- <span data-ttu-id="11d2b-185">取得目前調查的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="11d2b-185">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="11d2b-186">查看調查週期的摘要。</span><span class="sxs-lookup"><span data-stu-id="11d2b-186">View a summary of the investigation duration.</span></span>
- <span data-ttu-id="11d2b-187">選取視覺化效果中的節點，以查看該節點的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="11d2b-187">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="11d2b-188">選取頂端的索引標籤，以查看該索引標籤的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="11d2b-188">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="11d2b-189">警示調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-189">Alert investigation</span></span>

<span data-ttu-id="11d2b-190">在調查的 [**提醒**] 索引標籤上，您可以看到與調查相關的警示。</span><span class="sxs-lookup"><span data-stu-id="11d2b-190">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="11d2b-191">詳細資料包括觸發調查的警示，以及與調查相關的其他相關警示（如危險登入、DLP 原則違規等等）。</span><span class="sxs-lookup"><span data-stu-id="11d2b-191">Details include the alert that triggered the investigation and other correlated alerts, such as risky sign-in, DLP policy violations, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="11d2b-192">在此頁面中，安全性分析員也可以查看個別警示的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="11d2b-192">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![空氣提醒頁面](../../media/air-investigationalertspage.png)

<span data-ttu-id="11d2b-194">您可以：</span><span class="sxs-lookup"><span data-stu-id="11d2b-194">You can:</span></span>
- <span data-ttu-id="11d2b-195">取得目前觸發警示及任何相關警示的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="11d2b-195">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="11d2b-196">在清單中選取警示，以開啟顯示完整警示詳細資料的飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="11d2b-196">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="11d2b-197">電子郵件調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-197">Email investigation</span></span>

<span data-ttu-id="11d2b-198">在調查的 [**電子郵件**] 索引標籤上，您可以看到原始的電子郵件，以及視為調查之一部分之類似電子郵件的聚簇。</span><span class="sxs-lookup"><span data-stu-id="11d2b-198">On the **Email** tab for an investigation, you can see the original emails and the clusters of similar email identified as part of the investigation.</span></span> 

<span data-ttu-id="11d2b-199">考慮到組織中的使用者傳送和接收的大量電子郵件，以及電子郵件通訊和攻擊的多使用者性質，您的處理常式</span><span class="sxs-lookup"><span data-stu-id="11d2b-199">Given the sheer volume of email that users in an organization send and receive, plus the multi-user nature of email communications and attacks, the process of</span></span> 
- <span data-ttu-id="11d2b-200">根據來自郵件頭、內文、URL 和附件的類似屬性來聚簇電子郵件訊息;</span><span class="sxs-lookup"><span data-stu-id="11d2b-200">clustering email messages based on similar attributes from a message header, body, URL, and attachments;</span></span> 
- <span data-ttu-id="11d2b-201">將惡意電子郵件與良好的電子郵件分開;和</span><span class="sxs-lookup"><span data-stu-id="11d2b-201">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="11d2b-202">對惡意電子郵件採取動作</span><span class="sxs-lookup"><span data-stu-id="11d2b-202">taking action on malicious email messages</span></span> 

<span data-ttu-id="11d2b-203">會花很長的時間。</span><span class="sxs-lookup"><span data-stu-id="11d2b-203">can take significant time.</span></span> <span data-ttu-id="11d2b-204">現在，AIR 可自動化此程式，儲存組織的安全性小組時間和精力。</span><span class="sxs-lookup"><span data-stu-id="11d2b-204">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="11d2b-205">電子郵件分析步驟期間可識別兩種不同類型的電子郵件簇：相似性聚簇和指示器叢集。</span><span class="sxs-lookup"><span data-stu-id="11d2b-205">Two different types of email clusters may be identified during the email analysis step: similarity clusters and indicator clusters.</span></span> 
- <span data-ttu-id="11d2b-206">相似性聚簇是透過搜尋與類似寄件者和內容屬性的電子郵件所識別的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="11d2b-206">Similarity clusters are email messages identified by hunting for emails with similar sender and content attributes.</span></span> <span data-ttu-id="11d2b-207">根據原始的偵測結果，這些聚簇會針對惡意內容進行評估。</span><span class="sxs-lookup"><span data-stu-id="11d2b-207">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="11d2b-208">包含足夠惡意電子郵件偵測的電子郵件群集被視為惡意電子郵件。</span><span class="sxs-lookup"><span data-stu-id="11d2b-208">Email clusters that contain enough malicious email detections are considered malicious.</span></span>
- <span data-ttu-id="11d2b-209">指標聚簇是透過搜尋來自原始電子郵件的相同指示器實體（檔案雜湊或 URL）所識別的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="11d2b-209">Indicator clusters are email messages that are identified by hunting for the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="11d2b-210">當原始檔案/URL 實體識別為惡意時，AIR 會將指示器結論套用到包含該實體的完整電子郵件。</span><span class="sxs-lookup"><span data-stu-id="11d2b-210">When the original file/URL entity is identified as malicious, AIR applies the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="11d2b-211">識別為惡意程式碼的檔案，表示包含該檔案的電子郵件叢集會被視為惡意程式碼電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="11d2b-211">A file identified as malware means that the cluster of email messages containing that file are treated as malware email messages.</span></span>

<span data-ttu-id="11d2b-212">聚簇的目標是尋找及尋找其他相關的電子郵件訊息，這些郵件是由同一個寄件者在攻擊或活動中所傳送。</span><span class="sxs-lookup"><span data-stu-id="11d2b-212">The goal of clustering is to hunt and find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>  <span data-ttu-id="11d2b-213">在某些情況下，合法的電子郵件可能會觸發調查（例如，使用者報告行銷電子郵件）。</span><span class="sxs-lookup"><span data-stu-id="11d2b-213">In some cases, legitimate email may trigger an investigation (e.g. a user reports a marketing email).</span></span>  <span data-ttu-id="11d2b-214">在這些案例中，電子郵件叢集應識別電子郵件群集是否不是惡意的-當有適當的情況時，它不會指出威脅，也**不**會建議刪除電子郵件。</span><span class="sxs-lookup"><span data-stu-id="11d2b-214">In these scenarios, the email clustering should identify that email clusters are not malicious – when it appropriately does so, it will **not** indicate a threat nor will it recommend email removal.</span></span>

<span data-ttu-id="11d2b-215">[**電子郵件**] 索引標籤也會顯示與調查相關的電子郵件專案，例如使用者報告的電子郵件詳細資料、報告的原始電子郵件、zapped 由於惡意程式碼/網路釣魚等的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="11d2b-215">The **Email** tab also shows email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

<span data-ttu-id="11d2b-216">[電子郵件] 索引標籤上所識別的電子郵件計數目前代表 [**電子**郵件] 索引標籤上所顯示之所有電子郵件的總數。由於電子郵件訊息存在於多個聚簇中，因此所識別的實際電子郵件總數（並受修正動作影響）是在所有的聚簇和原始收件者的電子郵件中顯示的唯一電子郵件計數。</span><span class="sxs-lookup"><span data-stu-id="11d2b-216">The email count identified on the email tab currently represents the sum total of all email messages shown on the **Email** tab. Because email messages are present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) is the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span> 

<span data-ttu-id="11d2b-217">根據每個收件者，Explorer 和 AIR 的電子郵件都會以每個收件者為基礎，因為每個收件者的安全性 verdicts、動作和傳遞位置各不相同。</span><span class="sxs-lookup"><span data-stu-id="11d2b-217">Both Explorer and AIR count email messages on a per recipient basis, since the security verdicts, actions, and delivery locations vary on a per recipient basis.</span></span> <span data-ttu-id="11d2b-218">因此，傳送給三位使用者的原始電子郵件會算作三個電子郵件的總數，而不是一封電子郵件。</span><span class="sxs-lookup"><span data-stu-id="11d2b-218">Thus an original email sent to three users count as a total of three email messages instead of one email.</span></span> <span data-ttu-id="11d2b-219">附注可能是電子郵件會被計算兩次以上的情況，因為電子郵件可能會有多個動作，而且在所有動作都會發生時，可能會有多個電子郵件副本。</span><span class="sxs-lookup"><span data-stu-id="11d2b-219">Note there may be cases where an email gets counted two or more times, since the email may have multiple actions on it and there may be multiple copies of the email once all actions occur.</span></span> <span data-ttu-id="11d2b-220">例如，在傳遞時偵測到惡意程式碼的電子郵件，可能會導致封鎖（隔離）電子郵件和取代的電子郵件（威脅檔案會以警告檔取代，然後傳遞至使用者的信箱）。</span><span class="sxs-lookup"><span data-stu-id="11d2b-220">For example, a malware email that is detected at delivery may result in both a blocked (quarantined) email and a replaced email (threat file replaced with a warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="11d2b-221">由於系統中的電子郵件有逐字的兩個複本，所以兩者都可能會計入簇計數。</span><span class="sxs-lookup"><span data-stu-id="11d2b-221">Since there are literally two copies of the email in the system, both might be counted in cluster counts.</span></span> 

<span data-ttu-id="11d2b-222">電子郵件計數會在調查時進行計算，當您開啟調查 flyouts 時，會重新計算某些計數（根據基礎查詢）。</span><span class="sxs-lookup"><span data-stu-id="11d2b-222">Email counts are calculated at the time of the investigation and some counts are recalculated when you open investigation flyouts (based on an underlying query).</span></span> <span data-ttu-id="11d2b-223">[電子郵件] 索引標籤上的電子郵件聚簇及 [叢集] 浮出控制項上顯示的電子郵件數量詞的電子郵件數目會在調查時進行計算，而且不會變更。</span><span class="sxs-lookup"><span data-stu-id="11d2b-223">The email counts shown for the email clusters on the email tab and the email quantity value shown on cluster flyout are calculated at the time of investigation and do not change.</span></span> <span data-ttu-id="11d2b-224">電子郵件的 [電子郵件] 索引標籤底部顯示的電子郵件計數，以及 Explorer 中所顯示之電子郵件的計數，會反映在調查的初始分析之後所收到的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="11d2b-224">The email count shown at the bottom of the email tab of the email cluster flyout and the count of email messages shown in Explorer reflect email messages received after the investigation's initial analysis.</span></span> <span data-ttu-id="11d2b-225">因此，顯示原始數量10封電子郵件的電子郵件，會顯示在調查分析階段和系統管理員檢查調查時，會有5封以上的電子郵件訊息到貨的電子郵件清單總額15。</span><span class="sxs-lookup"><span data-stu-id="11d2b-225">Thus an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when five more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span>  <span data-ttu-id="11d2b-226">同樣的「調查」的計數可能會比 Explorer 查詢所顯示的計數大，因為 ATP P2 會在30天內的30天后到期資料，以及已收費授權的30天。</span><span class="sxs-lookup"><span data-stu-id="11d2b-226">Likewise old investigations may start having bigger counts than Explorer queries show, since ATP P2 expires data after 7 days for trials and 30 days for paid licenses.</span></span>  <span data-ttu-id="11d2b-227">在不同的視圖中顯示計數歷史和目前的計數，都是為了指出調查時的電子郵件影響，以及目前的影響，直到執行補救的時間為止。</span><span class="sxs-lookup"><span data-stu-id="11d2b-227">Showing both count historical and current counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

<span data-ttu-id="11d2b-228">舉例來說，請考慮下列案例。</span><span class="sxs-lookup"><span data-stu-id="11d2b-228">As an example, consider the following scenario.</span></span> <span data-ttu-id="11d2b-229">第三個電子郵件的第一個叢集已被視為網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="11d2b-229">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="11d2b-230">會找到另一個具有相同 IP 和主體的類似郵件，並將其視為惡意網路，因為在初始偵測時，已將其中一部分識別為網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="11d2b-230">Another cluster of similar messages with the same IP and subject was found and considered malicious, as some of them were identified as phish during initial detection.</span></span> 

![航空電子郵件調查頁面](../../media/air-investigationemailpage.png)

<span data-ttu-id="11d2b-232">您可以：</span><span class="sxs-lookup"><span data-stu-id="11d2b-232">You can:</span></span>
- <span data-ttu-id="11d2b-233">取得目前的聚簇結果及發現威脅的視覺概況。</span><span class="sxs-lookup"><span data-stu-id="11d2b-233">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="11d2b-234">按一下 [叢集] 實體或威脅清單，開啟顯示完整警示詳細資料的飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="11d2b-234">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>
- <span data-ttu-id="11d2b-235">按一下 [電子郵件叢集詳細資料] 索引標籤頂端的「在 Explorer 中開啟」連結進一步調查電子郵件叢集</span><span class="sxs-lookup"><span data-stu-id="11d2b-235">Further investigate the email cluster by clicking the 'Open in Explorer' link at the top of the 'Email cluster details' tab</span></span>

![使用飛出詳細資料的航空調查電子郵件](../../media/air-investigationemailpageflyoutdetails.png)

> [!NOTE]
> <span data-ttu-id="11d2b-237">在電子郵件的內容中，您可能會在調查過程中看到大量的反常威脅曲面。</span><span class="sxs-lookup"><span data-stu-id="11d2b-237">In the context of email, you may see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="11d2b-238">大量的事件會指出調查事件時間與較舊的時程表之間的類似電子郵件訊息中的波峰。</span><span class="sxs-lookup"><span data-stu-id="11d2b-238">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="11d2b-239">這種具有類似特性的電子郵件流量（例如，主旨和寄件者網域、內文相似性和寄件者 IP）通常是電子郵件宣傳活動或攻擊的開始。</span><span class="sxs-lookup"><span data-stu-id="11d2b-239">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span> <span data-ttu-id="11d2b-240">不過，大量、垃圾郵件和合法的電子郵件活動通常會共用這些特性。</span><span class="sxs-lookup"><span data-stu-id="11d2b-240">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span> <span data-ttu-id="11d2b-241">大量的情況代表潛在威脅，而且與使用防病毒引擎、引爆或惡意信譽所識別的惡意程式碼或網路釣魚威脅相比，其可能會較低的危險。</span><span class="sxs-lookup"><span data-stu-id="11d2b-241">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="11d2b-242">使用者調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-242">User investigation</span></span>

<span data-ttu-id="11d2b-243">在 [**使用者**] 索引標籤上，您可以看到所有識別為調查之一部分的使用者。</span><span class="sxs-lookup"><span data-stu-id="11d2b-243">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="11d2b-244">當發生事件時，使用者帳戶會出現在調查中，或指出這些使用者帳戶可能受到影響或遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="11d2b-244">User accounts appear in the investigation when there is an event or indication that those user accounts might be affected or compromised.</span></span>

<span data-ttu-id="11d2b-245">例如，在下圖中，AIR 會根據所建立的新收件匣規則，識別出損等損等現象。</span><span class="sxs-lookup"><span data-stu-id="11d2b-245">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="11d2b-246">調查的其他詳細資料（證據）可透過此索引標籤內的詳細資料。受損的跡象和反常也包括來自[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)的反常偵測。</span><span class="sxs-lookup"><span data-stu-id="11d2b-246">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies may also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![AIR 調查使用者頁面](../../media/air-investigationuserspage.png)

<span data-ttu-id="11d2b-248">您可以：</span><span class="sxs-lookup"><span data-stu-id="11d2b-248">You can:</span></span>
- <span data-ttu-id="11d2b-249">深入瞭解已識別的使用者結果和找到的風險。</span><span class="sxs-lookup"><span data-stu-id="11d2b-249">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="11d2b-250">選取使用者開啟彈出頁面，顯示完整的提醒詳細資料。</span><span class="sxs-lookup"><span data-stu-id="11d2b-250">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="11d2b-251">機器調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-251">Machine investigation</span></span>

<span data-ttu-id="11d2b-252">在 [**機器**] 索引標籤上，您可以看到識別為調查一部分的所有機器。</span><span class="sxs-lookup"><span data-stu-id="11d2b-252">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![AIR 調查電腦頁面](../../media/air-investigationmachinepage.png)

<span data-ttu-id="11d2b-254">在某些行動行動中，AIR 會將電子郵件威脅與裝置相關聯（例如，Zapped 惡意程式碼）。</span><span class="sxs-lookup"><span data-stu-id="11d2b-254">As part of some playbooks, AIR correlates email threats to devices (e.g. Zapped malware).</span></span> <span data-ttu-id="11d2b-255">例如，調查會將惡意檔雜湊傳遞至[Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
)以進行調查。</span><span class="sxs-lookup"><span data-stu-id="11d2b-255">For example, an investigation passes a malicious file hash across to [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) to investigate.</span></span> <span data-ttu-id="11d2b-256">這可讓您針對使用者自動調查相關的機器，以協助確保雲端和您的端點都有解決威脅。</span><span class="sxs-lookup"><span data-stu-id="11d2b-256">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span> 

<span data-ttu-id="11d2b-257">您可以：</span><span class="sxs-lookup"><span data-stu-id="11d2b-257">You can:</span></span>
- <span data-ttu-id="11d2b-258">取得目前的電腦及發現威脅的視覺概況。</span><span class="sxs-lookup"><span data-stu-id="11d2b-258">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="11d2b-259">選取機器，以開啟 Microsoft Defender Security Center 中相關[Microsoft DEFENDER ATP 調查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)中的視圖。</span><span class="sxs-lookup"><span data-stu-id="11d2b-259">Select a machine to open a view that into the related [Microsoft Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in the Microsoft Defender Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="11d2b-260">實體調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-260">Entity investigation</span></span>

<span data-ttu-id="11d2b-261">在 [**實體**] 索引標籤上，您可以看到在調查中識別及分析的實體。</span><span class="sxs-lookup"><span data-stu-id="11d2b-261">On the **Entities** tab, you can see the entities identified and analyzed as part of the investigation.</span></span> 

<span data-ttu-id="11d2b-262">在這裡，您可以查看已調查的實體和實體類型的詳細資料，例如電子郵件訊息、叢集、IP 位址、使用者等等。</span><span class="sxs-lookup"><span data-stu-id="11d2b-262">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="11d2b-263">您也可以查看已分析的實體數量，以及與每個實體相關聯的威脅。</span><span class="sxs-lookup"><span data-stu-id="11d2b-263">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

![AIR 調查實體頁面](../../media/air-investigationentitiespage.png)

<span data-ttu-id="11d2b-265">您可以：</span><span class="sxs-lookup"><span data-stu-id="11d2b-265">You can:</span></span>
- <span data-ttu-id="11d2b-266">取得所找到之調查實體和威脅的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="11d2b-266">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="11d2b-267">選取實體以開啟顯示相關實體詳細資料的飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="11d2b-267">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![空中調查實體詳細資料](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="11d2b-269">行動手冊記錄</span><span class="sxs-lookup"><span data-stu-id="11d2b-269">Playbook log</span></span>

<span data-ttu-id="11d2b-270">在 [**記錄**] 索引標籤上，您可以看到在調查過程中所發生的所有操作手冊步驟。</span><span class="sxs-lookup"><span data-stu-id="11d2b-270">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="11d2b-271">記錄檔會捕獲 Office 365 自動調查功能所完成之所有 analyzer 和動作的完整清查，做為空氣的一部分。</span><span class="sxs-lookup"><span data-stu-id="11d2b-271">The log captures a complete inventory of all analyzers and actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="11d2b-272">它提供所有採取步驟的清晰視圖，包括動作本身、描述，以及實際從開始到完成的持續時間。</span><span class="sxs-lookup"><span data-stu-id="11d2b-272">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span> 

![航空調查記錄頁面](../../media/air-investigationlogpage.png)

<span data-ttu-id="11d2b-274">您可以：</span><span class="sxs-lookup"><span data-stu-id="11d2b-274">You can:</span></span>
- <span data-ttu-id="11d2b-275">請參閱行動手冊步驟的視覺概況。</span><span class="sxs-lookup"><span data-stu-id="11d2b-275">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="11d2b-276">將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="11d2b-276">Export the results to a CSV file.</span></span>
- <span data-ttu-id="11d2b-277">篩選視圖。</span><span class="sxs-lookup"><span data-stu-id="11d2b-277">Filter the view.</span></span>

|<span data-ttu-id="11d2b-278">分析儀</span><span class="sxs-lookup"><span data-stu-id="11d2b-278">Analyzer</span></span> | <span data-ttu-id="11d2b-279">描述</span><span class="sxs-lookup"><span data-stu-id="11d2b-279">Description</span></span> |
|-----|-----|
|<span data-ttu-id="11d2b-280">DLP 違規調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-280">DLP violations investigation</span></span> |<span data-ttu-id="11d2b-281">調查[Office 365 資料遺失防護](../../compliance/data-loss-prevention-policies.md)（DLP）偵測到的任何衝突</span><span class="sxs-lookup"><span data-stu-id="11d2b-281">Investigate any violations detected by [Office 365 Data Loss Prevention](../../compliance/data-loss-prevention-policies.md) (DLP)</span></span> |
|<span data-ttu-id="11d2b-282">電子郵件指示器解壓縮</span><span class="sxs-lookup"><span data-stu-id="11d2b-282">Email indicators extraction</span></span> |<span data-ttu-id="11d2b-283">從電子郵件的標頭、本文和內容提取指示器，以進行調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-283">Extract indicators from the header, body, and content of an email message for investigation</span></span> |
|<span data-ttu-id="11d2b-284">檔案雜湊信譽</span><span class="sxs-lookup"><span data-stu-id="11d2b-284">File Hash Reputation</span></span> |<span data-ttu-id="11d2b-285">根據組織中使用者和機器的檔案雜湊，偵測不好的異常</span><span class="sxs-lookup"><span data-stu-id="11d2b-285">Detect anomalies based on file hashes for users and machines in your organization</span></span> |
|<span data-ttu-id="11d2b-286">郵件叢集識別</span><span class="sxs-lookup"><span data-stu-id="11d2b-286">Mail cluster identification</span></span> |<span data-ttu-id="11d2b-287">以標頭、內文、內容及 URLs 為基礎的電子郵件聚簇分析</span><span class="sxs-lookup"><span data-stu-id="11d2b-287">Email cluster analysis based on header, body, content, and URLs</span></span> |
|<span data-ttu-id="11d2b-288">郵件聚簇磁片區分析</span><span class="sxs-lookup"><span data-stu-id="11d2b-288">Mail cluster volume analysis</span></span> |<span data-ttu-id="11d2b-289">根據輸出郵件流程大量模式進行的電子郵件叢集分析</span><span class="sxs-lookup"><span data-stu-id="11d2b-289">Email cluster analysis based on outbound mail flow volume patterns</span></span> |
|<span data-ttu-id="11d2b-290">郵件委派調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-290">Mail delegation investigation</span></span> |<span data-ttu-id="11d2b-291">調查與此次調查相關之使用者信箱的郵件委派存取權</span><span class="sxs-lookup"><span data-stu-id="11d2b-291">Investigate mail delegation access for user mailboxes related to this investigation</span></span> |
|<span data-ttu-id="11d2b-292">郵件轉發規則調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-292">Mail forwarding rules investigation</span></span> |<span data-ttu-id="11d2b-293">調查與此次調查相關之使用者信箱的任何郵件轉送規則</span><span class="sxs-lookup"><span data-stu-id="11d2b-293">Investigate any mail forwarding rules for user mailboxes related to this investigation</span></span> |
|<span data-ttu-id="11d2b-294">偵測到未接惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="11d2b-294">Missed malware detected</span></span> |<span data-ttu-id="11d2b-295">偵測未接的惡意程式碼已傳遞至組織中的使用者信箱</span><span class="sxs-lookup"><span data-stu-id="11d2b-295">Detect missed malware delivered to user's mailbox in your organization</span></span> |
|<span data-ttu-id="11d2b-296">隨選引爆</span><span class="sxs-lookup"><span data-stu-id="11d2b-296">On-demand detonation</span></span> |<span data-ttu-id="11d2b-297">觸發電子郵件訊息、附件及 URLs 的隨選引爆</span><span class="sxs-lookup"><span data-stu-id="11d2b-297">On-demand detonation triggered for email messages, attachments, and URLs</span></span> |
|<span data-ttu-id="11d2b-298">輸出郵件反常狀況調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-298">Outbound mail anomaly investigation</span></span> |<span data-ttu-id="11d2b-299">根據歷史郵件流程針對組織中的使用者傳送模式來偵測異常</span><span class="sxs-lookup"><span data-stu-id="11d2b-299">Detect anomalies based on historical mail flow sending patterns for users in your organization</span></span> |
|<span data-ttu-id="11d2b-300">輸出惡意程式碼和垃圾郵件反常情況調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-300">Outbound malware and spam anomaly investigation</span></span> |<span data-ttu-id="11d2b-301">偵測來自組織中使用者的組織內和輸出惡意程式碼、網路釣魚詐騙或垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="11d2b-301">Detect intra-org and outbound malware, phish, or spam originating from users in your organization</span></span> |
|<span data-ttu-id="11d2b-302">寄件者網域調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-302">Sender domain investigation</span></span> |<span data-ttu-id="11d2b-303">從[Microsoft 智慧型 Security Graph](https://www.microsoft.com/security/operations/intelligence)和外部威脅情報來源對網域信譽的要求檢查</span><span class="sxs-lookup"><span data-stu-id="11d2b-303">On-demand check of domain reputation from the [Microsoft Intelligent Security Graph](https://www.microsoft.com/security/operations/intelligence) and external threat intelligence sources</span></span> |
|<span data-ttu-id="11d2b-304">寄件者 IP 調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-304">Sender IP investigation</span></span> | <span data-ttu-id="11d2b-305">從[Microsoft 智慧型 Security Graph](https://www.microsoft.com/security/operations/intelligence)和外部威脅情報來源對 IP 信譽的要求檢查</span><span class="sxs-lookup"><span data-stu-id="11d2b-305">On-demand check of IP reputation from the [Microsoft Intelligent Security Graph](https://www.microsoft.com/security/operations/intelligence) and external threat intelligence sources</span></span> |
|<span data-ttu-id="11d2b-306">URL 按一下調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-306">URL clicks investigation</span></span> | <span data-ttu-id="11d2b-307">調查組織中的[Office 365 ATP 安全連結](atp-safe-links.md)所保護的使用者按一下</span><span class="sxs-lookup"><span data-stu-id="11d2b-307">Investigate clicks  from users protected by [Office 365 ATP Safe Links](atp-safe-links.md) in your organization</span></span> |
|<span data-ttu-id="11d2b-308">URL 信譽調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-308">URL reputation investigation</span></span> |<span data-ttu-id="11d2b-309">對來自[Microsoft 智慧型 Security Graph](https://www.microsoft.com/security/operations/intelligence)和外部威脅情報來源之 URL 信譽的要求檢查</span><span class="sxs-lookup"><span data-stu-id="11d2b-309">On-demand check on URL reputation from the [Microsoft Intelligent Security Graph](https://www.microsoft.com/security/operations/intelligence) and external threat intelligence sources</span></span> |
|<span data-ttu-id="11d2b-310">使用者活動調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-310">User activity investigation</span></span> |<span data-ttu-id="11d2b-311">分析[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)中的使用者活動異常</span><span class="sxs-lookup"><span data-stu-id="11d2b-311">Analyze user activity anomalies in [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)</span></span> |
|<span data-ttu-id="11d2b-312">使用者報告的電子郵件指示器解壓縮</span><span class="sxs-lookup"><span data-stu-id="11d2b-312">User-reported emails indicators extraction</span></span> |<span data-ttu-id="11d2b-313">從[使用者報告的郵件](enable-the-report-message-add-in.md)頭、內文和內容提取指示器，以進行調查</span><span class="sxs-lookup"><span data-stu-id="11d2b-313">Extract indicators from the header, body, and content of [user-reported email](enable-the-report-message-add-in.md) for investigation</span></span> |

### <a name="recommended-actions"></a><span data-ttu-id="11d2b-314">建議的動作</span><span class="sxs-lookup"><span data-stu-id="11d2b-314">Recommended actions</span></span>

<span data-ttu-id="11d2b-315">在 [**動作**] 索引標籤上，您可以看到在調查完成之後，修正建議的所有行動手冊動作。</span><span class="sxs-lookup"><span data-stu-id="11d2b-315">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="11d2b-316">動作會捕獲 Microsoft 建議您在調查結束時採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="11d2b-316">Actions capture the steps Microsoft recommends you take at the end of an investigation.</span></span> <span data-ttu-id="11d2b-317">您可以選取一或多個動作來採取補救措施。</span><span class="sxs-lookup"><span data-stu-id="11d2b-317">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="11d2b-318">按一下 [**核准**]，即可開始修復。</span><span class="sxs-lookup"><span data-stu-id="11d2b-318">Clicking **Approve** allows remediation to begin.</span></span> <span data-ttu-id="11d2b-319">（需要適當的許可權-需要「搜尋和清除」角色才能從 Explorer 和 AIR 執行動作）。</span><span class="sxs-lookup"><span data-stu-id="11d2b-319">(Appropriate permissions are needed - the 'Search And Purge' role is required to run actions from Explorer and AIR).</span></span> <span data-ttu-id="11d2b-320">例如，安全性讀者可以查看動作但不能核准。</span><span class="sxs-lookup"><span data-stu-id="11d2b-320">For example, a Security Reader can view actions but not approve them.</span></span> <span data-ttu-id="11d2b-321">附注：您不需要核准每個動作。</span><span class="sxs-lookup"><span data-stu-id="11d2b-321">Note: You do not have to approve every action.</span></span> <span data-ttu-id="11d2b-322">如果您不同意建議的動作，或您的組織未選擇某些類型的動作，您可以選擇**拒絕**動作或完全忽略動作，不採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="11d2b-322">If you do not agree with the recommended action or your organization does not choose certain types of actions, then you can choose to **Reject** the actions or simply ignore them and take no action.</span></span> <span data-ttu-id="11d2b-323">核准和/或拒絕所有動作可讓調查完全關閉（狀態會變成「已修正」），而保留某些動作會導致調查狀態變更為部分修正狀態。</span><span class="sxs-lookup"><span data-stu-id="11d2b-323">Approving and/or rejecting all actions lets the investigation fully close (status becomes remediated), while leaving some actions incomplete results in the investigation status changing to a partially remediated state.</span></span>

![AIR 調查動作頁面](../../media/air-investigationactionspage.png)

<span data-ttu-id="11d2b-325">您可以：</span><span class="sxs-lookup"><span data-stu-id="11d2b-325">You can:</span></span>
- <span data-ttu-id="11d2b-326">取得行動手冊-建議動作的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="11d2b-326">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="11d2b-327">選取一個或多個動作。</span><span class="sxs-lookup"><span data-stu-id="11d2b-327">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="11d2b-328">使用批註核准或拒絕建議的動作。</span><span class="sxs-lookup"><span data-stu-id="11d2b-328">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="11d2b-329">將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="11d2b-329">Export the results to a CSV file.</span></span>
- <span data-ttu-id="11d2b-330">篩選視圖。</span><span class="sxs-lookup"><span data-stu-id="11d2b-330">Filter the view.</span></span>

## <a name="next-steps"></a><span data-ttu-id="11d2b-331">後續步驟</span><span class="sxs-lookup"><span data-stu-id="11d2b-331">Next steps</span></span>

- [<span data-ttu-id="11d2b-332">審閱及核准擱置的動作</span><span class="sxs-lookup"><span data-stu-id="11d2b-332">Review and approve pending actions</span></span>](air-remediation-actions.md)

- [<span data-ttu-id="11d2b-333">深入瞭解 Microsoft 威脅防護中的自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="11d2b-333">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)