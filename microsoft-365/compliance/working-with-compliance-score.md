---
title: 使用 Microsoft 合規性分數
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在 Microsoft 合規性分數中使用的工作流程工具可協助您管理組織的合規性。
ms.openlocfilehash: 9c3871db720666319eb8a0523ff8150efd753f91
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802130"
---
# <a name="working-with-microsoft-compliance-score-preview"></a><span data-ttu-id="f8e9f-103">使用 Microsoft 合規性分數 （預覽）</span><span class="sxs-lookup"><span data-stu-id="f8e9f-103">Working with Microsoft Compliance Score (Preview)</span></span>

## <a name="managing-your-workflow-with-improvement-actions"></a><span data-ttu-id="f8e9f-104">管理您的工作流程與改進動作</span><span class="sxs-lookup"><span data-stu-id="f8e9f-104">Managing your workflow with improvement actions</span></span>

<span data-ttu-id="f8e9f-105">使用合規性分數改進動作可以集中您合規性工作流程。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-105">Using improvement actions in Compliance Score centralizes your compliance workflows.</span></span> <span data-ttu-id="f8e9f-106">改進動作建議對齊資料保護規定與標準，建議的動作，並提供詳細的實作指南。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-106">Improvement actions suggest recommended actions to align with data protection regulations and standards, and provide detailed implementation guidance.</span></span> <span data-ttu-id="f8e9f-107">您可以將它們指派給使用者執行必要的實作和測試的工作。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-107">You can assign them to users to perform the necessary implementation and testing work.</span></span> <span data-ttu-id="f8e9f-108">您也可以儲存文件與備忘稿並記錄狀態更新本身的改進巨集指令中的權限。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-108">You can also store documentation and notes, and record status updates right in the improvement action itself.</span></span>

## <a name="view-your-improvement-actions"></a><span data-ttu-id="f8e9f-109">檢視您改進的動作</span><span class="sxs-lookup"><span data-stu-id="f8e9f-109">View your improvement actions</span></span>

<span data-ttu-id="f8e9f-110">合規性分數儀表板會顯示您的**關鍵的改進動作**-閱讀有最高資料點的最重要的問題。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-110">The Compliance Score dashboard shows your **key improvement actions**—the ones with the most available points which address the most important issues.</span></span>

<span data-ttu-id="f8e9f-111">若要檢視所有的改進動作，請選取**改進動作**] 索引標籤上 [儀表板，或移至 [儀表板上的關鍵的改進動作清單中選取 [**檢視所有改進動作**。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-111">To view all of your improvement actions, select the **Improvement actions** tab on your dashboard, or select **View all improvement actions** underneath the list of key improvement actions on your dashboard.</span></span> <span data-ttu-id="f8e9f-112">這將帶您前往**改進動作**] 頁面，其中您可以在此處看到所有您組織的改進的動作。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-112">This brings you to the the **Improvement actions** page, where you can see all of your organization’s improvement actions.</span></span>

<span data-ttu-id="f8e9f-113">如果您有動作的詳細清單，可能很有幫助篩選檢視。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-113">If you have a long list of actions, it may be helpful to filter your view.</span></span> <span data-ttu-id="f8e9f-114">若要這麼做，請選取 [右上角的 [動作] 清單的**篩選器**。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-114">To do this, select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="f8e9f-115">[**篩選**] 彈出式視窗窗格出現時，然後選取您想要的準則基於法規和標準、 解決方案和群組。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-115">When the **Filters** flyout pane appears, then select your desired criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="f8e9f-116">您可以也自訂您檢視在右上角中選取**群組**，從下拉式功能表中，選取 [檢視群組、 解決方案、 類別、 的動作類型或狀態。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-116">You can also customize your view by selecting **Group** in the upper-right corner and, from the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="f8e9f-117">此頁面上的預設檢視不會顯示**通過**測試狀態改進動作。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-117">The default view for this page does not show improvement actions with a test status of **Passed**.</span></span> <span data-ttu-id="f8e9f-118">若要檢視已通過測試的動作，檢查 [**篩選**] 彈出式視窗窗格中的 [ **Passed** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-118">To view actions that have passed testing, check the **Passed** box in the **Filters** flyout pane.</span></span> <span data-ttu-id="f8e9f-119">僅限動作與測試狀態的**Passed**會計入您的分數。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-119">Only actions with a test status of **Passed** count toward your score.</span></span>

<span data-ttu-id="f8e9f-120">改進動作] 頁面會顯示下列資料點的每個改進動作：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-120">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="f8e9f-121">**分數影響**： 依據完成動作時，將會增加整體的分數的點</span><span class="sxs-lookup"><span data-stu-id="f8e9f-121">**Score impact**: the points by which your overall score will increase when completing the action</span></span>
- <span data-ttu-id="f8e9f-122">**法規**： 規定或標準相關巨集指令</span><span class="sxs-lookup"><span data-stu-id="f8e9f-122">**Regulations**: the regulation or standard pertaining to the action</span></span>
- <span data-ttu-id="f8e9f-123">**群組**： 群組對其指派巨集指令</span><span class="sxs-lookup"><span data-stu-id="f8e9f-123">**Group**: the group to which you assigned the action</span></span>
- <span data-ttu-id="f8e9f-124">**解決方案**： 您可以移至執行動作的解決方案</span><span class="sxs-lookup"><span data-stu-id="f8e9f-124">**Solutions**: the solution where you can go to perform the action</span></span>
- <span data-ttu-id="f8e9f-125">**「 評估 」**: 評估 （這會將組織以符合特定的合規性目標控制項） 中位於巨集指令</span><span class="sxs-lookup"><span data-stu-id="f8e9f-125">**Assessments**: the assessment  (which organizes controls to meet a certain compliance objective) in which the action resides</span></span>
- <span data-ttu-id="f8e9f-126">**類別**： 相關的資料保護類別 （亦即，保護資訊、 管理裝置等）。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-126">**Categories**: the related data protection category (i.e., protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="f8e9f-127">**測試狀態**：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-127">**Test status**:</span></span>
    - <span data-ttu-id="f8e9f-128">**無**-記錄沒有狀態更新</span><span class="sxs-lookup"><span data-stu-id="f8e9f-128">**None** - no status update recorded</span></span>
    - <span data-ttu-id="f8e9f-129">**不評估**-測試尚未啟動</span><span class="sxs-lookup"><span data-stu-id="f8e9f-129">**Not assessed** - testing has not started</span></span>
    - <span data-ttu-id="f8e9f-130">**不在範圍**-合規性分數計算列印會排除，不會增加您的分數</span><span class="sxs-lookup"><span data-stu-id="f8e9f-130">**Not in scope** - is excluded from Compliance Score calculation and does not increase your score</span></span>
    - <span data-ttu-id="f8e9f-131">**部分測試**-測試尚未完成</span><span class="sxs-lookup"><span data-stu-id="f8e9f-131">**Partially tested** - testing is not yet complete</span></span>
    - <span data-ttu-id="f8e9f-132">**失敗高風險**-實作的測試失敗，且具有適用的標準的非規範的風險較高</span><span class="sxs-lookup"><span data-stu-id="f8e9f-132">**Failed high risk** - testing of implementation has failed, and the risk of non-compliance with the applicable standard is high</span></span>
    - <span data-ttu-id="f8e9f-133">**Passed**實作順利測試</span><span class="sxs-lookup"><span data-stu-id="f8e9f-133">**Passed** - implementation successfully tested</span></span>
- <span data-ttu-id="f8e9f-134">**Pointed 達到**： 顯示點達到不足無法盈餘分析的最大值</span><span class="sxs-lookup"><span data-stu-id="f8e9f-134">**Pointed achieved**: shows points achieved out of the maximum that could be earned</span></span>

### <a name="improvement-actions-details"></a><span data-ttu-id="f8e9f-135">改進的動作詳細資料</span><span class="sxs-lookup"><span data-stu-id="f8e9f-135">Improvement actions details</span></span>

<span data-ttu-id="f8e9f-136">每個改進巨集指令具有詳細資料] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-136">Each improvement action has a details page.</span></span> <span data-ttu-id="f8e9f-137">此頁面包含詳細的實作指示，說明如何採取建議的動作，以解決相關的標準與法規**一眼**標頭下所列的需求。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-137">This page contains detailed implementation instructions, which explain how to take the recommended actions to address the related standards and regulatory requirements listed under the **At a glance** header.</span></span>

<span data-ttu-id="f8e9f-138">詳細資料頁面是其中啟動建議的動作或將工作指派給另一位使用者，更新狀態，並附加註解及文件。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-138">The details page is where you can launch the recommended action or assign the work to another user, update status, and attach notes and documentation.</span></span>

<span data-ttu-id="f8e9f-139">若要檢視改進動作的詳細資料] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-139">To view an improvement action's details page:</span></span>

1. <span data-ttu-id="f8e9f-140">移至您改進動作頁面。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-140">Go to your improvement actions page.</span></span>
2. <span data-ttu-id="f8e9f-141">按一下或點選您預定的改進的動作，這會開啟其詳細資料] 頁面上的資料列中的任何地方。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-141">Click or tap anywhere in the row of your intended improvement action, which opens its details page.</span></span>

<span data-ttu-id="f8e9f-142">藉由選取向上或向下畫面右上角的箭號，可以輕鬆在清單檢視的下一頁或上一頁改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-142">You can easily view the next or previous improvement action in the list by selecting the up or down arrow in the upper-right corner of the screen.</span></span> <span data-ttu-id="f8e9f-143">如果您在改進動作] 頁面上的清單，篩選向上或向下移動將帶您前往該篩選清單內的下一個項目。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-143">If you filtered your list on the improvement actions page, moving up or down will take you to the next item within that filtered list.</span></span>

## <a name="assign-improvement-actions"></a><span data-ttu-id="f8e9f-144">指派改進動作</span><span class="sxs-lookup"><span data-stu-id="f8e9f-144">Assign improvement actions</span></span>

<span data-ttu-id="f8e9f-145">若要開始實作工時改進巨集指令，您可以自行執行工作，或將其指派給另一位使用者。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-145">To begin implementation work on an improvement action, you can do the work yourself or assign it to another user.</span></span> <span data-ttu-id="f8e9f-146">指派的人員可能是：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-146">The assigned person could be:</span></span>

- <span data-ttu-id="f8e9f-147">企業原則擁有者</span><span class="sxs-lookup"><span data-stu-id="f8e9f-147">A business policy owner</span></span>
- <span data-ttu-id="f8e9f-148">IT 實施者</span><span class="sxs-lookup"><span data-stu-id="f8e9f-148">An IT implementer</span></span>
- <span data-ttu-id="f8e9f-149">若要執行的工作與責任另一位員工</span><span class="sxs-lookup"><span data-stu-id="f8e9f-149">Another employee with responsibility to perform the task</span></span> 

<span data-ttu-id="f8e9f-150">一旦識別適當的人員，請務必他們在合規性分數 」 （合規性系統管理員、 規範資料管理員、 安全性系統管理員或全域系統管理員） 來執行工作，然後執行下列步驟中保留足夠的[角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-150">Once the proper person is identified, be sure they hold a sufficient [role](compliance-score-setup.md#set-user-permissions-and-assign-roles) in Compliance Score (compliance administrator, compliance data administrator, security administrator, or global administrator) to perform the work, then take the following steps:</span></span> 

1. <span data-ttu-id="f8e9f-151">從改進的動作詳細資料] 頁面上，選取 [靠近螢幕的左上方] 區段的 [**編輯狀態**]。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-151">From the improvement actions details page, select **Edit status** near the upper-left section of the screen.</span></span> 

2. <span data-ttu-id="f8e9f-152">在 [編輯狀態彈出式視窗窗格中，按一下或點選 [在**指定至]** 方塊中，填入使用者的**建議追蹤的人員**清單。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-152">In the edit status flyout pane, click or tap in the **Assigned to** box, which populates a **Suggested people** list of users.</span></span> <span data-ttu-id="f8e9f-153">您可以從清單中，選取的使用者，或輸入您要指派動作之人員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-153">You can select the user from the list, or type the email address of the person to whom you want to assign the action.</span></span>

3. <span data-ttu-id="f8e9f-154">選取 [**儲存並關閉**以完成工作分派。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-154">Select **Save and close** to complete the assignment.</span></span> <span data-ttu-id="f8e9f-155">指派的使用者會收到一封電子郵件的改進巨集指令具有已指派給他們，並從其儀表板可以再開啟的改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-155">The assigned user will receive an email that the improvement action has been assigned to them, and they can then open the improvement action from their dashboard.</span></span>

<span data-ttu-id="f8e9f-156">指派的使用者可以執行的實作指示中所述的建議的動作。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-156">The assigned user can then perform the recommended actions outlined in the implementation instructions.</span></span>

## <a name="perform-work-and-store-documentation"></a><span data-ttu-id="f8e9f-157">執行工作，並儲存文件</span><span class="sxs-lookup"><span data-stu-id="f8e9f-157">Perform work and store documentation</span></span>

<span data-ttu-id="f8e9f-158">當您執行實作工作時，您可以上傳的檔案及備忘稿直接至**備忘稿與文件**] 區段中的改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-158">When you perform implementation work, you can upload files and notes directly to the improvement action in the **Notes and documentation** section.</span></span> <span data-ttu-id="f8e9f-159">這會提供安全的集中式的存放庫，可協助您示範滿意度的控制項，以符合規範標準與法規。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-159">This provides a secure, centralized repository to help you demonstrate satisfaction of controls to meet compliance standards and regulations.</span></span> <span data-ttu-id="f8e9f-160">任何具有唯讀權限的使用者可以閱讀本節內容。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-160">Any user with read-only access can read content in this section.</span></span> <span data-ttu-id="f8e9f-161">若要上傳、 下載，或刪除欄位，或輸入或編輯備忘稿很限制為具有編輯權限的角色。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-161">The ability to upload, download, or delete fields, or to enter or edit notes, is restricted to roles with editing rights.</span></span>

<span data-ttu-id="f8e9f-162">在 [**備忘稿與文件**] 區段中的欄位包含：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-162">Fields in the **Notes and documentation** section include:</span></span>

<span data-ttu-id="f8e9f-163">**上傳的文件**</span><span class="sxs-lookup"><span data-stu-id="f8e9f-163">**Uploaded documents**</span></span>

- <span data-ttu-id="f8e9f-164">選取 [**管理文件**上傳相關的任何檔案。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-164">Select **Manage documents** to upload any relevant files.</span></span>
- <span data-ttu-id="f8e9f-165">管理文件彈出式視窗窗格開啟時，選取 [**新增文件**，然後選取您的檔案從您的系統。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-165">When the manage documents flyout pane opens, select **Add document**, then select your file from your system.</span></span> <span data-ttu-id="f8e9f-166">公認的檔案類型：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-166">Accepted file types:</span></span> 
  - <span data-ttu-id="f8e9f-167">文件 （.doc、.xls、.ppt、.txt、.pdf）</span><span class="sxs-lookup"><span data-stu-id="f8e9f-167">Documents (.doc, .xls, .ppt, .txt, .pdf)</span></span>
  - <span data-ttu-id="f8e9f-168">影像 （.jpg、.png）</span><span class="sxs-lookup"><span data-stu-id="f8e9f-168">Images (.jpg, .png)</span></span>
  - <span data-ttu-id="f8e9f-169">視訊 (.mkv)</span><span class="sxs-lookup"><span data-stu-id="f8e9f-169">Video (.mkv)</span></span>
  - <span data-ttu-id="f8e9f-170">壓縮的檔案 （.zip、.rar）</span><span class="sxs-lookup"><span data-stu-id="f8e9f-170">Compressed files (.zip, .rar)</span></span>
- <span data-ttu-id="f8e9f-171">一旦您檔案中若解析窗格中，選取 [**關閉]** 會自動儲存的檔案附件。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-171">Once your file resolves in the pane, select **Close,** which automatically saves the file attachment.</span></span> <span data-ttu-id="f8e9f-172">接著，您會看到下方所列的檔案**上傳文件。**</span><span class="sxs-lookup"><span data-stu-id="f8e9f-172">You will then see the file listed underneath **Uploaded documents.**</span></span> 
- <span data-ttu-id="f8e9f-173">若要下載或刪除文件時，選取 [**管理文件**從下方清單中的文件。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-173">To download or delete the document, select **Manage documents** from  underneath the list of documents.</span></span> <span data-ttu-id="f8e9f-174">在彈出式視窗] 窗格中，按一下或點選 [以反白顯示，然後選取 [**下載**的文件資料列或**刪除。**</span><span class="sxs-lookup"><span data-stu-id="f8e9f-174">On the flyout pane, click or tap on the document row to highlight it, then select **Download** or **Delete.**</span></span>

<span data-ttu-id="f8e9f-175">**實作、 測試和其他附註**</span><span class="sxs-lookup"><span data-stu-id="f8e9f-175">**Implementation, Test, and Additional notes**</span></span>

- <span data-ttu-id="f8e9f-176">若要將備忘稿新增任何這三個欄位中，選取 [任何以下欄位下方的 [**編輯實作備忘稿**。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-176">To add notes in any of these three fields, select **Edit implementation notes** underneath any of thse fields.</span></span>
- <span data-ttu-id="f8e9f-177">彈出式視窗窗格開啟時，附註在欄位中輸入文字，然後選取 [**儲存並關閉**。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-177">When the flyout pane opens, enter notes in the text field, then select **Save and close**.</span></span>
- <span data-ttu-id="f8e9f-178">若要編輯備忘稿，選取 [**編輯實作備忘稿**、 進行編輯，然後選取 [**儲存並關閉**。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-178">To edit notes, select **Edit implementation notes**, make your edits, then select **Save and close**.</span></span>

<span data-ttu-id="f8e9f-179">附註] 欄位中沒有任何字元的限制。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-179">There is no character limit in the notes fields.</span></span> <span data-ttu-id="f8e9f-180">我們建議您保持備忘稿簡短，讓您輕鬆地檢視和編輯它們從 [改進的動作詳細資料] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-180">We recommend keeping notes brief so that you can easily view and edit them from the improvement actions details page.</span></span>

## <a name="change-improvement-action-status"></a><span data-ttu-id="f8e9f-181">變更改進巨集指令狀態</span><span class="sxs-lookup"><span data-stu-id="f8e9f-181">Change improvement action status</span></span>

<span data-ttu-id="f8e9f-182">您可以將記錄的實作狀態日期，並測試狀態與日期，每個改進巨集指令。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-182">You can record the implementation status and date, and the test status and date, for each improvement action.</span></span> <span data-ttu-id="f8e9f-183">以下是可用的欄位及狀態選項：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-183">Below are the available fields and status options:</span></span>

- <span data-ttu-id="f8e9f-184">**實作狀態**： 選取 [從下列狀態的選項：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-184">**Implementation status**: select from these status options:</span></span>
    - <span data-ttu-id="f8e9f-185">**尚未實作**-尚未實作巨集指令</span><span class="sxs-lookup"><span data-stu-id="f8e9f-185">**Not implemented** - action not yet implemented</span></span>
    - <span data-ttu-id="f8e9f-186">**Implemented**實作巨集指令</span><span class="sxs-lookup"><span data-stu-id="f8e9f-186">**Implemented** - action implemented</span></span>
    - <span data-ttu-id="f8e9f-187">**替代實作**-選取此選項如果您使用其他協力廠商工具，或是不採取其他動作中包含 Microsoft 建議</span><span class="sxs-lookup"><span data-stu-id="f8e9f-187">**Alternative implementation** - select this option if you used other third-party tools or took other actions not included in Microsoft recommendations</span></span>
    - <span data-ttu-id="f8e9f-188">實作計劃**計劃**巨集指令</span><span class="sxs-lookup"><span data-stu-id="f8e9f-188">**Planned** - action is planned for implementation</span></span>
    - <span data-ttu-id="f8e9f-189">**不在範圍**-貴組織; 不相關的動作的選項。選取此狀態會從計分; 排除巨集指令取消選取它將會在計分包含巨集指令</span><span class="sxs-lookup"><span data-stu-id="f8e9f-189">**Not in scope** - an option for actions not relevant to your organization; selecting this status excludes the action from scoring; unselecting it will include the action in scoring</span></span>
- <span data-ttu-id="f8e9f-190">**實作日期**： 可用的欄位，當實作狀態設為**Implemented**或**替代實作**;切換到快顯選取日期的行事曆</span><span class="sxs-lookup"><span data-stu-id="f8e9f-190">**Implementation date**: available field when implementation status is set to **Implemented** or **Alternative implementation**; toggle through the calendar pop-up to select the date</span></span>
- <span data-ttu-id="f8e9f-191">**測試狀態**： 選取 [從下列選項：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-191">**Test status**: select from these options:</span></span>
    - <span data-ttu-id="f8e9f-192">**不評估**-測試尚未啟動</span><span class="sxs-lookup"><span data-stu-id="f8e9f-192">**Not assessed** - testing has not started</span></span>
    - <span data-ttu-id="f8e9f-193">**Passed**實作順利測試</span><span class="sxs-lookup"><span data-stu-id="f8e9f-193">**Passed**- implementation successfully tested</span></span>
    - <span data-ttu-id="f8e9f-194">**失敗低風險**-測試失敗、 低風險</span><span class="sxs-lookup"><span data-stu-id="f8e9f-194">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="f8e9f-195">**失敗中度風險**-測試失敗中, 度風險</span><span class="sxs-lookup"><span data-stu-id="f8e9f-195">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="f8e9f-196">**失敗高風險**-測試失敗]、 [高風險</span><span class="sxs-lookup"><span data-stu-id="f8e9f-196">**Failed high risk** - testing failed, high risk</span></span>
- <span data-ttu-id="f8e9f-197">**測試日期**： 切換到快顯選取日期的行事曆</span><span class="sxs-lookup"><span data-stu-id="f8e9f-197">**Test date**: toggle through the calendar pop-up to select the date</span></span>

> [!NOTE]
> <span data-ttu-id="f8e9f-198">實作和測試狀態欄位都可以編輯的任何使用者具有編輯權限，而不只是**指派給**使用者。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-198">Implementation and test status fields can be edited by any user with editing permissions, not just the **Assigned to** user.</span></span>

## <a name="assign-improvement-action-to-assessor-for-completion"></a><span data-ttu-id="f8e9f-199">將改進動作指派給待完成評估者</span><span class="sxs-lookup"><span data-stu-id="f8e9f-199">Assign improvement action to assessor for completion</span></span>

<span data-ttu-id="f8e9f-200">在完成工作並上傳的辨識項之後下, 一步是設定 [實作狀態] 和 [日期，並將改進動作指派給評估者進行驗證。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-200">After you complete the work and upload evidence, the next step is to set the implementation status and date, and assign the improvement action to an assessor for validation.</span></span>

<span data-ttu-id="f8e9f-201">評估的類型包括：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-201">Types of assessors include:</span></span>

- <span data-ttu-id="f8e9f-202">內部評估者執行驗證的組織內的控制項</span><span class="sxs-lookup"><span data-stu-id="f8e9f-202">Internal assessors who perform validation of controls within your organization</span></span>
- <span data-ttu-id="f8e9f-203">外部評估者檢查、 驗證及證實合規性 — 例如協力廠商獨立組織的稽核 Microsoft 雲端服務</span><span class="sxs-lookup"><span data-stu-id="f8e9f-203">External assessors who examine, verify, and certify compliance—such as third-party independent organizations that audit Microsoft cloud services</span></span>

<span data-ttu-id="f8e9f-204">評估者會驗證工作會檢查文件中，並選取適當的測試狀態。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-204">The assessor validates the work and examines the documentation, and selects the appropriate test status.</span></span>

<span data-ttu-id="f8e9f-205">**如果測試狀態 」 傳遞 」**: 巨集指令已完成，而且**點達到**顯示可能點達成並計算至整體合規性分數的完整數目。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-205">**If the test status is "Passed"**: the action is complete, and the **points achieved** shows the full number of possible points achieved and counted toward your overall compliance score.</span></span>

<span data-ttu-id="f8e9f-206">**如果測試狀態為 「 失敗 」 的任何程度**： 巨集指令不符合需求，並評估者可以將其指派回適當的使用者用於其他工作。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-206">**If the test status is any degree of "Failed"**: the action does not meet the requirements, and the assessor can assign it back to the appropriate user for additional work.</span></span>

## <a name="solutions-page"></a><span data-ttu-id="f8e9f-207">解決方案頁面</span><span class="sxs-lookup"><span data-stu-id="f8e9f-207">Solutions page</span></span>

<span data-ttu-id="f8e9f-208">**解決方案] 頁面上**是另一個起始點處理改進動作，以增加您的分數。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-208">The **Solutions page** is another starting point for working on improvement actions to increase your score.</span></span> 

<span data-ttu-id="f8e9f-209">若要取得您的方案] 頁面上，選取您的儀表板 [**解決方案**] 索引標籤或在儀表板右上方區段中選取 [**的解決方案，會影響您的分數**下方的 [**檢視所有解決方案**。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-209">To get to your solutions page, select the **Solutions** tab on your dashboard, or select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

<span data-ttu-id="f8e9f-210">[解決方案] 頁面上顯示為組織由解決方案的盈餘分析及潛在點的共用。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-210">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="f8e9f-211">檢視您剩餘點與此檢視中的改進動作可協助您了解哪些解決方案需要更多立即處理。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-211">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="f8e9f-212">篩選解決方案檢視</span><span class="sxs-lookup"><span data-stu-id="f8e9f-212">Filtering your solutions view</span></span>

<span data-ttu-id="f8e9f-213">若要篩選檢視的解決方案：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-213">To filter you view of solutions:</span></span> 

1. <span data-ttu-id="f8e9f-214">選取 [在評估] 清單的左上角的 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-214">Select **Filter** at the top left corner of your assessments list.</span></span>
2. <span data-ttu-id="f8e9f-215">在彈出式**篩選器**] 窗格中，勾選 [旁邊 （標準與法規，解決方案的動作類型、 合規性管理員群組、 類別） 所需的準則。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-215">On the flyout **Filters** pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="f8e9f-216">選取 [**套用**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-216">Select the **Apply** button.</span></span> <span data-ttu-id="f8e9f-217">篩選窗格會關閉，您會看到您篩選的檢視。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-217">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="f8e9f-218">您也可以修改檢視以顯示從您評估] 清單上方**群組**下拉功能表中選取 [群組類型，請參閱 「 評估 」 的群組、 產品或規定。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-218">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-actions-from-the-solutions-page"></a><span data-ttu-id="f8e9f-219">採取動作，從 [解決方案] 頁面</span><span class="sxs-lookup"><span data-stu-id="f8e9f-219">Taking actions from the solutions page</span></span>

<span data-ttu-id="f8e9f-220">[解決方案] 頁面上會顯示已連線至改進動作的貴組織的解決方案。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-220">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="f8e9f-221">下表列出每個方案的比重整體的分數，分數提升達成的點以及可能該方案中的，可以增加您的分數該解決方案中分組的改進動作的剩餘數目。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-221">The table lists each solution's contribution to your overall score, the score-enhancing points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span> 

<span data-ttu-id="f8e9f-222">有兩種方式，您可以採取從這個畫面的動作：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-222">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="f8e9f-223">在您預定的解決方案，**剩餘動作**] 欄下方的列上按一下或點選 [超連結數目。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-223">On the row of your intended solution, under the **Remaining actions** column, click or tap on the hyperlinked number.</span></span> <span data-ttu-id="f8e9f-224">這會帶您前往改進動作畫面中顯示該解決方案的未經測試的改進動作篩選檢視。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-224">This takes you to a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="f8e9f-225">在您預定的解決方案，**開啟方案**] 欄下方的列上選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-225">On the row of your intended solution, under the **Open solution** column, select **Open**.</span></span> <span data-ttu-id="f8e9f-226">這會帶您前往解決方案或在其中您可以採取建議的動作 Microsoft 365 和 Office 365 的安全性與合規性中心中的位置。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-226">This takes you to the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="f8e9f-227">「 評估 」 頁面</span><span class="sxs-lookup"><span data-stu-id="f8e9f-227">Assessments page</span></span>

<span data-ttu-id="f8e9f-228">[評估] 頁面上列出您選取追蹤貴組織的評估。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-228">The assessments page lists the assessments you select to track for your organization.</span></span> <span data-ttu-id="f8e9f-229">您合規性分數的分母取決於您追蹤的評估。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-229">Your Compliance Score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="f8e9f-230">您新增更多的評估、 更多的改進動作您會看到您改進動作在頁面上，且愈您分數的分母。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-230">The more assessments you add, the more improvement actions you see on your improvement actions page, and the higher your score denominator is.</span></span>

<span data-ttu-id="f8e9f-231">若要取得您評估] 頁面上，選取您的儀表板上的 [**評估**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-231">To get to your assessments page, select the **Assessments** tab on your dashboard.</span></span>

<span data-ttu-id="f8e9f-232">在此頁面上，您可以快速檢視每個評估的重要資訊：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-232">On this page you can quickly view important information about each assessment:</span></span>

- <span data-ttu-id="f8e9f-233">**狀態**： 朝評估中的所有改進動作完成的狀態會被列為下列一項：</span><span class="sxs-lookup"><span data-stu-id="f8e9f-233">**Status**: the status toward completion of all the improvement actions in the assessment will be listed as either:</span></span>
    - <span data-ttu-id="f8e9f-234">**非相容**： 評估的改進動作不已實作並順利測試;工作尚未開始</span><span class="sxs-lookup"><span data-stu-id="f8e9f-234">**Non-compliant**: the improvement actions in the assessment have not been implemented and successfully tested; work has not yet begun</span></span>
    - <span data-ttu-id="f8e9f-235">**進行中**： 工作正在進行中實作或測試的改進動作;這表示，例如，評定改進巨集指令已指派工作、 正在正在實作和測試</span><span class="sxs-lookup"><span data-stu-id="f8e9f-235">**In progress**: work is underway in implementing or testing the improvement actions; this could mean, for example, that an improvement action in the assessment has been assigned for work, is in the process of being implemented and tested</span></span>
- <span data-ttu-id="f8e9f-236">**評估進度**： 測試是成功透過控制項數目所衡量往最終完成評估，完成工時百分比。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-236">**Assessment progress**: the percentage of the work done towards final completion of the assessment, as measured by the number of controls successfully tested.</span></span>
- <span data-ttu-id="f8e9f-237">**客戶管理動作**： 已完成的動作，以滿足您客戶管理控制措施的實作數目</span><span class="sxs-lookup"><span data-stu-id="f8e9f-237">**Customer-managed actions**: the number of completed actions to satisfy implementation of  your customer-managed controls</span></span>
- <span data-ttu-id="f8e9f-238">**Microsoft 受管理的動作**： 已完成動作來滿足 Microsoft 管理控制措施的實作數目</span><span class="sxs-lookup"><span data-stu-id="f8e9f-238">**Microsoft-managed actions**: the number of completed actions to satisfy implementation of Microsoft-managed controls</span></span>
- <span data-ttu-id="f8e9f-239">**評估群組**： 您建立的群組，在評估所在的名稱</span><span class="sxs-lookup"><span data-stu-id="f8e9f-239">**Assessment group**: name of the group you created, in which the assessment resides</span></span>
- <span data-ttu-id="f8e9f-240">**相關的服務**： Microsoft 365 服務相關聯</span><span class="sxs-lookup"><span data-stu-id="f8e9f-240">**Related services**: associated Microsoft 365 service</span></span>
- <span data-ttu-id="f8e9f-241">**相關的規定**： 法規標準]、 [原則] 中或 [法律它會評估尋找滿足</span><span class="sxs-lookup"><span data-stu-id="f8e9f-241">**Related regulations**: the regulatory standard, policy, or law which the assessment seeks to satisfy</span></span>

### <a name="default-assessments"></a><span data-ttu-id="f8e9f-242">預設 「 評估 」</span><span class="sxs-lookup"><span data-stu-id="f8e9f-242">Default assessments</span></span>

<span data-ttu-id="f8e9f-243">根據預設，您會看到 「 評估 」 頁面上的 Microsoft 365 的資料保護基準評估。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-243">By default, you will see the Microsoft 365 data protection baseline assessment on the assessments page.</span></span> <span data-ttu-id="f8e9f-244">合規性分數也會提供數個現成可用的評估 （[檢視的完整清單](compliance-score.md#templates)）。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-244">Compliance Score also provides several out-of-box assessments ([view the full list](compliance-score.md#templates)).</span></span> <span data-ttu-id="f8e9f-245">如果您想要新增更多評估涵蓋其他法規和標準，您可以這麼做合規性管理員中。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-245">If you want to add more assessments to cover additional regulations and standards, you can do this in Compliance Manager.</span></span>

### <a name="managing-assessments"></a><span data-ttu-id="f8e9f-246">管理評估</span><span class="sxs-lookup"><span data-stu-id="f8e9f-246">Managing assessments</span></span>

<span data-ttu-id="f8e9f-247">公開預覽期間用於檢視、 建立、 匯出及封存評估功能仍會保留在合規性管理員 」。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-247">During public preview, functionality for viewing, creating, exporting, and archiving assessments remains in the Compliance Manager tool.</span></span> 

<span data-ttu-id="f8e9f-248">若要管理您評估，請選取 [**管理評估合規性管理員中**的 「 評估 」 清單頂端。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-248">To manage your assessments, select **Manage Assessments in Compliance Manager** at the top of the assessments list.</span></span>

<span data-ttu-id="f8e9f-249">頂端的評估] 清單中， **Microsoft 動作合規性管理員中**，[其他] 連結會帶您前往參與您的合規性分數的合規性管理員中顯示 Microsoft 控制項中的頁面。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-249">The other link at the top of the assessments list, **Microsoft actions in Compliance Manager**, takes you to the page in Compliance Manager showing Microsoft controls that contribute to your compliance score.</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="f8e9f-250">篩選 「 評估 」 檢視</span><span class="sxs-lookup"><span data-stu-id="f8e9f-250">Filtering your assessments view</span></span>

<span data-ttu-id="f8e9f-251">若要篩選檢視的 「 評估 」:</span><span class="sxs-lookup"><span data-stu-id="f8e9f-251">To filter you view of assessments:</span></span>

1. <span data-ttu-id="f8e9f-252">選取 [在評估] 清單的左上角的 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-252">Select **Filter** at the top left corner of your assessments list.</span></span>
2. <span data-ttu-id="f8e9f-253">在彈出式**篩選器**] 窗格中，勾選 [旁邊所需的準則 （標準與法規、 合規性管理員群組）。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-253">On the flyout **Filters** pane, place a check next to the desired criteria (standards and regulations, Compliance Manager group).</span></span>
3. <span data-ttu-id="f8e9f-254">選取 [**套用**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-254">Select the **Apply** button.</span></span> <span data-ttu-id="f8e9f-255">篩選窗格會關閉，您會看到您篩選的檢視。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-255">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="f8e9f-256">您也可以修改檢視以顯示從您評估] 清單上方**群組**下拉功能表中選取 [群組類型，請參閱 「 評估 」 的群組、 產品或規定。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-256">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="managing-improvement-actions-within-an-assessment"></a><span data-ttu-id="f8e9f-257">管理評估內的改進動作</span><span class="sxs-lookup"><span data-stu-id="f8e9f-257">Managing improvement actions within an assessment</span></span>

<span data-ttu-id="f8e9f-258">從評估] 清單中，[**客戶管理動作**] 欄中，選取 [預定評估的資料列上的連結的文字。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-258">From the assessment list, under the **Customer-managed actions** column, select the linked text on the row of the intended assessment.</span></span> <span data-ttu-id="f8e9f-259">這將帶您篩選的檢視改進動作畫面，顯示在該評定的動作。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-259">This takes you a filtered view of the improvement actions page showing the actions within that assessment.</span></span>

## <a name="reporting"></a><span data-ttu-id="f8e9f-260">Reporting</span><span class="sxs-lookup"><span data-stu-id="f8e9f-260">Reporting</span></span>

<span data-ttu-id="f8e9f-261">您可以匯出您所有合規性分數的改進動作的報告。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-261">You can export a report of all your improvement actions in Compliance Score.</span></span> <span data-ttu-id="f8e9f-262">從 [**改進動作**] 頁面上，選取 [**匯出**畫面，您的動作] 清單上方的左上角。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-262">From the **Improvement actions** page, select **Export** in the upper-left corner of your screen, above your list of actions.</span></span> <span data-ttu-id="f8e9f-263">這將會產生您所有的改進動作與**改進動作**] 頁面上，您可以檢視並儲存到本機電腦上所顯示的篩選類別 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-263">This will produce an Excel worksheet with all your improvement actions and the filter categories shown on the **Improvement actions** page, which you can view and save to your local machine.</span></span>

<span data-ttu-id="f8e9f-264">您也可以匯出報告從合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-264">You can also export a report from Compliance Manager.</span></span> <span data-ttu-id="f8e9f-265">在合規性管理員中，移至**控制項資訊**] 索引標籤，然後選取畫面右上方區段中的 [**匯出**。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-265">In Compliance Manager, go to the **Controls Info** tab and select **Export** in the upper-right section of the screen.</span></span> <span data-ttu-id="f8e9f-266">這會產生您可以檢視及儲存的 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="f8e9f-266">This produces an Excel worksheet you can view and save.</span></span>
