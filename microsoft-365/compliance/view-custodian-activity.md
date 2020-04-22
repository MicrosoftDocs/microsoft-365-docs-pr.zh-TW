---
title: 查看保管人審核活動
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: bf4274106ce1724785c3ac38204f753cd7788a63
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626339"
---
# <a name="view-custodian-audit-activity"></a><span data-ttu-id="2b271-102">查看保管人審核活動</span><span class="sxs-lookup"><span data-stu-id="2b271-102">View custodian audit activity</span></span>

<span data-ttu-id="2b271-103">需要了解是否有使用者已檢視特定文件或清除信箱中的項目嗎？</span><span class="sxs-lookup"><span data-stu-id="2b271-103">Need to find if a user viewed a specific document or purged an item from their mailbox?</span></span> <span data-ttu-id="2b271-104">「高級 eDiscovery」現在已與安全性 & 合規性中心內的現有「審核記錄」搜尋工具整合。</span><span class="sxs-lookup"><span data-stu-id="2b271-104">Advanced eDiscovery is now integrated with the existing audit log search tool in the Security & Compliance Center.</span></span> <span data-ttu-id="2b271-105">使用此內嵌經驗，您可以使用「高級 eDiscovery 保管人管理」工具，輕鬆地存取和搜尋您案例中的保管人活動，以協助您進行調查。</span><span class="sxs-lookup"><span data-stu-id="2b271-105">Using this embedded experience, you can use the Advanced eDiscovery Custodian Management tool to facilitate your investigation by easily accessing and searching the activity for custodians within your case.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2b271-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="2b271-106">Before you begin</span></span>

<span data-ttu-id="2b271-107">您必須在 Exchange Online 中指派 View-Only 的「審計記錄」或「審計記錄」角色，才能搜尋審計記錄。</span><span class="sxs-lookup"><span data-stu-id="2b271-107">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="2b271-108">根據預設，這些角色會在 Exchange 系統管理員中心的 [權限] 頁面上，指派給 [法務遵循管理] 和 [組織管理] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="2b271-108">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="2b271-109">若要讓使用者能夠使用最低的許可權層級來搜尋高級 eDiscovery 審核記錄，您可以在 Exchange Online 中建立自訂角色群組、新增 View-Only 的「審核記錄檔」或「審核記錄」角色，然後將該使用者新增為新角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2b271-109">To give a user the ability to search the Advanced eDiscovery audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="2b271-110">如需詳細資訊，請參閱管理 Exchange Online 中的角色群組。</span><span class="sxs-lookup"><span data-stu-id="2b271-110">For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b271-111">如果您在安全性 & 規範中心的 [許可權] 頁面上指派使用者 View-Only 的「審核記錄」或「審核記錄」角色，他們將無法搜尋審核記錄。</span><span class="sxs-lookup"><span data-stu-id="2b271-111">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the audit log.</span></span> <span data-ttu-id="2b271-112">您必須在 Exchange Online 中指派權限。</span><span class="sxs-lookup"><span data-stu-id="2b271-112">You have to assign the permissions in Exchange Online.</span></span> <span data-ttu-id="2b271-113">這是因為用來搜尋稽核記錄的基礎 Cmdlet 是 Exchange Online Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2b271-113">This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a><span data-ttu-id="2b271-114">步驟1：搜尋針對保管人所執行之活動的審計記錄</span><span class="sxs-lookup"><span data-stu-id="2b271-114">Step 1: Search the audit log for activities performed by a custodian</span></span>

1. <span data-ttu-id="2b271-115">請移至**eDiscovery > Advanced ediscovery** ，然後開啟案例。</span><span class="sxs-lookup"><span data-stu-id="2b271-115">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="2b271-116">按一下 [**保管人**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2b271-116">Click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="2b271-117">從清單中選取管理員，然後按一下彈出頁面上的 [**查看保管人活動**]。</span><span class="sxs-lookup"><span data-stu-id="2b271-117">Select a custodian from the list, and then click **View custodian activity** on the flyout page.</span></span>

    <span data-ttu-id="2b271-118">[保管人活動搜尋] 頁面隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="2b271-118">The Custodian activities search page is displayed.</span></span> <span data-ttu-id="2b271-119">附注您在上一個步驟中選取的系統管理員會顯示在 [**保管人**] 下拉式方塊中。</span><span class="sxs-lookup"><span data-stu-id="2b271-119">Note the custodian you selected in the previous step is displayed in the **Custodian** drop-down box.</span></span> <span data-ttu-id="2b271-120">您可以在下拉式方塊中選取不同的保管人，但是一次只能搜尋一個保管人的活動。</span><span class="sxs-lookup"><span data-stu-id="2b271-120">You can select different custodians in the drop-down box, but you can only search for activities for one custodian at a time.</span></span>

    ![管理員活動搜尋頁面](../media/AeDCustodianActivities1.png)
   
4. <span data-ttu-id="2b271-122">設定下列搜尋準則：</span><span class="sxs-lookup"><span data-stu-id="2b271-122">Configure the following search criteria:</span></span>
      
   <span data-ttu-id="2b271-123">a.</span><span class="sxs-lookup"><span data-stu-id="2b271-123">a.</span></span> <span data-ttu-id="2b271-124">**活動**-按一下下拉式清單，以顯示您可以搜尋的活動。</span><span class="sxs-lookup"><span data-stu-id="2b271-124">**Activities** - Click the drop-down list to display the activities that you can search for.</span></span> <span data-ttu-id="2b271-125">執行搜尋後，只會顯示所選活動的審計記錄。</span><span class="sxs-lookup"><span data-stu-id="2b271-125">After you run the search, only the audit records for the selected activities are displayed.</span></span> <span data-ttu-id="2b271-126">選取 [**顯示所有活動的結果**]，會顯示由系統管理員執行且符合其他搜尋準則之所有活動的結果。</span><span class="sxs-lookup"><span data-stu-id="2b271-126">Selecting **Show results for all activities** will display results for all activities performed by the custodian that match the other search criteria.</span></span>

      ![活動清單](../media/CustodianActivityAudit.PNG)
      
      <span data-ttu-id="2b271-128">b.</span><span class="sxs-lookup"><span data-stu-id="2b271-128">b.</span></span> <span data-ttu-id="2b271-129">**開始日期和結束日期**-選取日期和時間範圍，以顯示在該期間內發生的事件。</span><span class="sxs-lookup"><span data-stu-id="2b271-129">**Start date and End date** - Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="2b271-130">預設會選取最後七天。</span><span class="sxs-lookup"><span data-stu-id="2b271-130">The last seven days are selected by default.</span></span> <span data-ttu-id="2b271-131">日期和時間以國際標準時間 (UTC) 格式表示。</span><span class="sxs-lookup"><span data-stu-id="2b271-131">The date and time are presented in Coordinated Universal Time (UTC) format.</span></span> <span data-ttu-id="2b271-132">您可以指定的最大日期範圍是一年。</span><span class="sxs-lookup"><span data-stu-id="2b271-132">The maximum date range that you can specify is one year.</span></span>
      
      <span data-ttu-id="2b271-133">c.</span><span class="sxs-lookup"><span data-stu-id="2b271-133">c.</span></span> <span data-ttu-id="2b271-134">**保管人**-按一下此方塊，然後選取特定保管人以顯示搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="2b271-134">**Custodians** - Click in this box and then select a specific custodian to display search results for.</span></span> <span data-ttu-id="2b271-135">您在此方塊中選取之使用者所執行之選取活動的審計記錄會顯示在結果清單中。</span><span class="sxs-lookup"><span data-stu-id="2b271-135">Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
      
   5. <span data-ttu-id="2b271-136">按一下</span><span class="sxs-lookup"><span data-stu-id="2b271-136">Click</span></span>   ![搜尋按鈕](../media/SearchButton.PNG)  <span data-ttu-id="2b271-138">使用您的搜尋準則執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="2b271-138">to run the search using your search criteria.</span></span> <span data-ttu-id="2b271-139">搜尋結果會在載入之後，然後在 [保管人活動搜尋] 頁面的 [結果] 底下出現片刻。</span><span class="sxs-lookup"><span data-stu-id="2b271-139">The search results are loaded, and after a few moments they are displayed under Results on the Custodian Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="2b271-140">步驟2：查看審核記錄搜尋結果</span><span class="sxs-lookup"><span data-stu-id="2b271-140">Step 2: View the audit log search results</span></span>

<span data-ttu-id="2b271-141">審核記錄搜尋的結果會顯示在 [保管人審核記錄] 頁面的 [結果] 底下。</span><span class="sxs-lookup"><span data-stu-id="2b271-141">The results of an audit log search are displayed under Results on the Custodian Audit log page.</span></span> <span data-ttu-id="2b271-142">最多5000（最新）事件會以150事件的倍數顯示。</span><span class="sxs-lookup"><span data-stu-id="2b271-142">A maximum of 5,000 (newest) events are displayed in increments of 150 events.</span></span> <span data-ttu-id="2b271-143">若要顯示更多事件，您可以在 [結果] 窗格中使用捲軸列，或按 Shift + End 顯示後續 150 個事件。</span><span class="sxs-lookup"><span data-stu-id="2b271-143">To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="2b271-144">結果包含搜尋傳回之每個事件的下列相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2b271-144">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="2b271-145">**日期：** 事件發生時的日期和時間 (以 UTC 格式顯示)。</span><span class="sxs-lookup"><span data-stu-id="2b271-145">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="2b271-146">**IP 位址：** 記錄活動時所使用的裝置之 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="2b271-146">**IP address**: The IP address of the device that was used when the activity was logged.</span></span> <span data-ttu-id="2b271-147">IP 位址會以 IPv4 或 IPv6 位址格式顯示。</span><span class="sxs-lookup"><span data-stu-id="2b271-147">The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="2b271-148">**使用者**：執行動作並觸發事件的使用者 (或服務帳戶)。</span><span class="sxs-lookup"><span data-stu-id="2b271-148">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="2b271-149">**活動**：使用者執行的活動。</span><span class="sxs-lookup"><span data-stu-id="2b271-149">**Activity**: The activity performed by the user.</span></span> <span data-ttu-id="2b271-150">這個值對應您在 [活動] 下拉式清單中選取的活動。</span><span class="sxs-lookup"><span data-stu-id="2b271-150">This value corresponds to the activities that you selected in the Activities drop down list.</span></span> <span data-ttu-id="2b271-151">若是來自 Exchange 系統管理員稽核記錄的事件，此欄中的這個值則是 Exchange Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2b271-151">For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="2b271-152">**項目**：已建立或修改為對應活動結果的物件。</span><span class="sxs-lookup"><span data-stu-id="2b271-152">**Item**: The object that was created or modified as a result of the corresponding activity.</span></span> <span data-ttu-id="2b271-153">例如，已檢視或修改的檔案或已更新的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="2b271-153">For example, the file that was viewed or modified or the user account that was updated.</span></span> <span data-ttu-id="2b271-154">並非所有活動在此資料行中都具有值。</span><span class="sxs-lookup"><span data-stu-id="2b271-154">Not all activities have a value in this column.</span></span>

- <span data-ttu-id="2b271-155">**詳細**資訊：有關活動的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2b271-155">**Detail**: Additional detail about an activity.</span></span> <span data-ttu-id="2b271-156">同樣地，並非所有活動都具有值。</span><span class="sxs-lookup"><span data-stu-id="2b271-156">Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="2b271-157">步驟 3：篩選搜尋結果</span><span class="sxs-lookup"><span data-stu-id="2b271-157">Step 3: Filter the search results</span></span>

<span data-ttu-id="2b271-158">除了排序，您也可以篩選稽核記錄搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="2b271-158">In addition to sorting, you can also filter the results of an audit log search.</span></span> <span data-ttu-id="2b271-159">這可協助您快速篩選特定使用者或活動的結果。</span><span class="sxs-lookup"><span data-stu-id="2b271-159">This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="2b271-160">若要篩選結果：</span><span class="sxs-lookup"><span data-stu-id="2b271-160">To filter the results:</span></span>

 1. <span data-ttu-id="2b271-161">建立並執行審核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="2b271-161">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="2b271-162">當顯示結果時，按一下 [篩選結果]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b271-162">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="2b271-163">關鍵字方塊隨即顯示在每個欄標頭底下。</span><span class="sxs-lookup"><span data-stu-id="2b271-163">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="2b271-164">按一下欄標頭底下的其中一個方塊，然後輸入字詞或片語 (視您正在篩選的欄而定)。</span><span class="sxs-lookup"><span data-stu-id="2b271-164">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on.</span></span> <span data-ttu-id="2b271-165">結果將動態重新調整為顯示與您的篩選相符之事件。</span><span class="sxs-lookup"><span data-stu-id="2b271-165">The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="2b271-166">若要清除篩選，請按一下 [篩選] 方塊中的**X**或只按一下 [**隱藏篩選**]。</span><span class="sxs-lookup"><span data-stu-id="2b271-166">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="2b271-167">將搜尋結果匯出至檔案</span><span class="sxs-lookup"><span data-stu-id="2b271-167">Export the search results to a file</span></span>

<span data-ttu-id="2b271-168">您可以將審核記錄搜尋的結果匯出至本機電腦上的逗點分隔值（CSV）檔案。</span><span class="sxs-lookup"><span data-stu-id="2b271-168">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer.</span></span> <span data-ttu-id="2b271-169">您可以在 Microsoft Excel 中開啟此檔案，並使用諸如搜尋、排序、篩選和分割單一欄（包含多值儲存格）的功能分為多個欄。</span><span class="sxs-lookup"><span data-stu-id="2b271-169">You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="2b271-170">執行稽核記錄搜尋，然後修改搜尋準則，直到您獲得想要的結果為止。</span><span class="sxs-lookup"><span data-stu-id="2b271-170">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="2b271-171">按一下 [匯出結果]，然後選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="2b271-171">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="2b271-172">**儲存載入的結果：** 選擇此選項，只會匯出在「**保管人審核記錄搜尋**」頁面的 [**結果**] 下顯示的專案。</span><span class="sxs-lookup"><span data-stu-id="2b271-172">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **Custodian Audit log search** page.</span></span> <span data-ttu-id="2b271-173">下載的 CSV 檔案會包含與頁面上顯示相同的欄 (及資料) (日期、使用者、活動、項目及詳細資料)。</span><span class="sxs-lookup"><span data-stu-id="2b271-173">The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details).</span></span> <span data-ttu-id="2b271-174">包含來自審計記錄專案的詳細資訊的 CSV 檔案中包含其他欄（名為**More**）。</span><span class="sxs-lookup"><span data-stu-id="2b271-174">An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry.</span></span> <span data-ttu-id="2b271-175">因為您正在匯出 [稽核記錄搜尋] 頁面上所載入的相同結果 (且可檢視)，因此最多可匯出 5,000 個項目。</span><span class="sxs-lookup"><span data-stu-id="2b271-175">Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="2b271-176">**下載所有結果：** 選擇此選項可從符合搜尋準則的審計記錄中匯出所有專案。</span><span class="sxs-lookup"><span data-stu-id="2b271-176">**Download all results:** Choose this option to export all entries from the audit log that meet the search criteria.</span></span> <span data-ttu-id="2b271-177">針對大型搜尋結果集，請選擇此選項，從審核記錄中下載所有專案，除了可顯示在 [**保管人審核記錄**搜尋] 頁面上的5000結果。</span><span class="sxs-lookup"><span data-stu-id="2b271-177">For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **Custodian Audit log** search page.</span></span> <span data-ttu-id="2b271-178">此選項會從審核記錄檔下載原始資料到 CSV 檔案，並包含來自名為 AuditData 的欄中的審計記錄專案的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="2b271-178">This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData.</span></span> <span data-ttu-id="2b271-179">如果您選擇此匯出選項，下載檔案可能需要較久的時間。這是因為如果您選擇其他選項，檔案可能會遠大於下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="2b271-179">It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="2b271-180">您可以從單一稽核記錄搜尋下載最多 50,000 個項目至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="2b271-180">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="2b271-181">如果已下載 50,000 個項目至 CSV 檔案，您可能可以假設有超過 50,000 個符合搜尋準則的事件。</span><span class="sxs-lookup"><span data-stu-id="2b271-181">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="2b271-182">若要匯出的內容超過此限制，請嘗試使用日期範圍來縮小稽核記錄項目的數量。</span><span class="sxs-lookup"><span data-stu-id="2b271-182">To export more than this limit, try using a date range to reduce the number of audit log entries.</span></span> <span data-ttu-id="2b271-183">您可能需要使用較小的日期範圍執行多次搜尋，以匯出 50,000 個以上的項目。</span><span class="sxs-lookup"><span data-stu-id="2b271-183">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="2b271-184">選取匯出選項之後，會在視窗底部顯示一則訊息，提示您開啟 CSV 檔、將其儲存至 [下載] 資料夾，或將其儲存至特定資料夾。</span><span class="sxs-lookup"><span data-stu-id="2b271-184">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="2b271-185">如需查看、篩選或匯出審計記錄搜尋結果的詳細資訊，請參閱在[安全性 & 規範中心搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。</span><span class="sxs-lookup"><span data-stu-id="2b271-185">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
