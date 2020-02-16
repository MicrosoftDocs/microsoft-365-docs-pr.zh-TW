---
title: 檢視稽核活動的感興趣的人員
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
ms.openlocfilehash: 59616247f284b76a4e180f315067f694ff861007
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068810"
---
# <a name="view-the-audit-activity-of-people-of-interest"></a><span data-ttu-id="c21e4-102">檢視稽核活動的感興趣的人員</span><span class="sxs-lookup"><span data-stu-id="c21e4-102">View the audit activity of people of interest</span></span>

<span data-ttu-id="c21e4-103">需要了解是否有使用者已檢視特定文件或清除信箱中的項目嗎？</span><span class="sxs-lookup"><span data-stu-id="c21e4-103">Need to find if a user viewed a specific document or purged an item from their mailbox?</span></span> <span data-ttu-id="c21e4-104">資料調查 （預覽） 現在已與現有的安全性 & 規範中心的稽核記錄搜尋工具整合。</span><span class="sxs-lookup"><span data-stu-id="c21e4-104">Data Investigations (Preview) is now integrated with the existing audit log search tool in the Security & Compliance Center.</span></span> <span data-ttu-id="c21e4-105">使用此內嵌的體驗，您可以使用感興趣管理工具的 [資料調查 （預覽） 的人員來協助您調查輕鬆地存取，以及您調查內感興趣的人員搜尋活動。</span><span class="sxs-lookup"><span data-stu-id="c21e4-105">Using this embedded experience, you can use the Data Investigations (Preview) People of interest Management tool to facilitate your investigation by easily accessing and searching the activity for people of interest within your investigation.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c21e4-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="c21e4-106">Before you begin</span></span>

<span data-ttu-id="c21e4-107">您必須在 Exchange Online 中獲派為 [僅限檢視稽核記錄] 或 [稽核記錄] 角色，才能搜尋 Office 365 稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="c21e4-107">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log.</span></span> <span data-ttu-id="c21e4-108">根據預設，這些角色會在 Exchange 系統管理員中心的 [權限] 頁面上，指派給 [法務遵循管理] 和 [組織管理] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="c21e4-108">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="c21e4-109">若要讓使用者能夠搜尋資料調查 （預覽） 稽核記錄的最低權限，您可以自訂角色群組 Exchange Online 中建立、 新增 「 僅檢視稽核記錄檔] 或 [稽核記錄 」 角色，以及再將使用者新增為新的角色 /gr 成員oup。</span><span class="sxs-lookup"><span data-stu-id="c21e4-109">To give a user the ability to search the Data Investigations (Preview) audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="c21e4-110">如需詳細資訊，請參閱管理 Exchange Online 中的角色群組。</span><span class="sxs-lookup"><span data-stu-id="c21e4-110">For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c21e4-111">如果您將 Security & 合規性中心的權限] 頁面上僅檢視稽核記錄檔] 或 [稽核記錄檔角色指派使用者，他們將無法搜尋 Office 365 稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="c21e4-111">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the Office 365 audit log.</span></span> <span data-ttu-id="c21e4-112">您必須在 Exchange Online 中指派權限。</span><span class="sxs-lookup"><span data-stu-id="c21e4-112">You have to assign the permissions in Exchange Online.</span></span> <span data-ttu-id="c21e4-113">這是因為用來搜尋稽核記錄的基礎 Cmdlet 是 Exchange Online Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c21e4-113">This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-create-an-data-investigations-preview-audit-log-search"></a><span data-ttu-id="c21e4-114">步驟 1： 建立資料調查 （預覽） 的稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="c21e4-114">Step 1: Create an Data Investigations (Preview) audit log search</span></span>

   1. <span data-ttu-id="c21e4-115">從**安全性 & 合規性中心 > 資料調查 （預覽）** 中選取現有的調查。</span><span class="sxs-lookup"><span data-stu-id="c21e4-115">Select an existing investigation from the **Security & Compliance Center > Data Investigations (Preview)**.</span></span>
   
   2. <span data-ttu-id="c21e4-116">瀏覽至 [**感興趣的人員**] 索引標籤，然後選取人員。</span><span class="sxs-lookup"><span data-stu-id="c21e4-116">Navigate to the **People of interest** tab and select a person.</span></span>
   
   3. <span data-ttu-id="c21e4-117">選取人員後，從 [詳細資料] 面板中按一下 [**檢視活動**。</span><span class="sxs-lookup"><span data-stu-id="c21e4-117">Once you have selected a person, click **View Activity** from the details panel.</span></span>
   
   4. <span data-ttu-id="c21e4-118">設定下列搜尋準則：</span><span class="sxs-lookup"><span data-stu-id="c21e4-118">Configure the following search criteria:</span></span>
      
      <span data-ttu-id="c21e4-119">a.</span><span class="sxs-lookup"><span data-stu-id="c21e4-119">a.</span></span> <span data-ttu-id="c21e4-120">**活動**-按一下下拉式清單，顯示您可以搜尋的活動。</span><span class="sxs-lookup"><span data-stu-id="c21e4-120">**Activities** - Click the drop-down list to display the activities that you can search for.</span></span> <span data-ttu-id="c21e4-121">執行搜尋之後，會顯示只有選取活動的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="c21e4-121">After you run the search, only the audit records for the selected activities are displayed.</span></span> <span data-ttu-id="c21e4-122">選取 [**顯示所有活動的結果**會顯示結果符合其他搜尋準則的所有活動。</span><span class="sxs-lookup"><span data-stu-id="c21e4-122">Selecting **Show results for all activities** will display results for all activities that meet the other search criteria.</span></span>
      
      <span data-ttu-id="c21e4-123">b.</span><span class="sxs-lookup"><span data-stu-id="c21e4-123">b.</span></span> <span data-ttu-id="c21e4-124">**開始日期和結束日期**-選取日期與時間範圍，以顯示該期間內發生的事件。</span><span class="sxs-lookup"><span data-stu-id="c21e4-124">**Start date and End date** - Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="c21e4-125">預設會選取過去 7 天。</span><span class="sxs-lookup"><span data-stu-id="c21e4-125">The last seven days are selected by default.</span></span> <span data-ttu-id="c21e4-126">日期和時間以國際標準時間 (UTC) 格式表示。</span><span class="sxs-lookup"><span data-stu-id="c21e4-126">The date and time are presented in Coordinated Universal Time (UTC) format.</span></span> <span data-ttu-id="c21e4-127">您可以指定的最大的日期範圍是一年。</span><span class="sxs-lookup"><span data-stu-id="c21e4-127">The maximum date range that you can specify is one year.</span></span>
      
      <span data-ttu-id="c21e4-128">c.</span><span class="sxs-lookup"><span data-stu-id="c21e4-128">c.</span></span> <span data-ttu-id="c21e4-129">**感興趣的人員**-按一下 [在這個方塊，然後選取 [顯示搜尋結果提供給特定 custodian。</span><span class="sxs-lookup"><span data-stu-id="c21e4-129">**People of interest** - Click in this box and then select a specific custodian to display search results for.</span></span> <span data-ttu-id="c21e4-130">選取您在此方塊中選取的使用者所執行的活動的稽核記錄會顯示在結果清單中。</span><span class="sxs-lookup"><span data-stu-id="c21e4-130">Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
    
    1. <span data-ttu-id="c21e4-131">按一下 [搜尋]\*\*\*\* 以使用您的搜尋準則執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="c21e4-131">Click **Search** to run the search using your search criteria.</span></span> <span data-ttu-id="c21e4-132">搜尋結果會載入，而且它們顯示在人員感興趣的結果下的一段時間後的活動搜尋] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c21e4-132">The search results are loaded, and after a few moments they are displayed under Results on the People of interest Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="c21e4-133">步驟 2： 檢視稽核記錄搜尋結果</span><span class="sxs-lookup"><span data-stu-id="c21e4-133">Step 2: View the audit log search results</span></span>

<span data-ttu-id="c21e4-134">稽核記錄搜尋結果會顯示在 [對象的利息稽核記錄 」 頁面上的結果下。</span><span class="sxs-lookup"><span data-stu-id="c21e4-134">The results of an audit log search are displayed under Results on the People of interest Audit log page.</span></span> <span data-ttu-id="c21e4-135">最大值為 5000 個 （最新） 的事件都會顯示在 150 事件以遞增。</span><span class="sxs-lookup"><span data-stu-id="c21e4-135">A maximum of 5,000 (newest) events are displayed in increments of 150 events.</span></span> <span data-ttu-id="c21e4-136">若要顯示更多事件，您可以在 [結果] 窗格中使用捲軸列，或按 Shift + End 顯示後續 150 個事件。</span><span class="sxs-lookup"><span data-stu-id="c21e4-136">To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="c21e4-137">結果包含下列搜尋傳回的每個事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c21e4-137">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="c21e4-138">**日期：** 事件發生時的日期和時間 (以 UTC 格式顯示)。</span><span class="sxs-lookup"><span data-stu-id="c21e4-138">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="c21e4-139">**IP 位址：** 記錄活動時所使用的裝置之 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c21e4-139">**IP address**: The IP address of the device that was used when the activity was logged.</span></span> <span data-ttu-id="c21e4-140">IP 位址會以 IPv4 或 IPv6 位址格式顯示。</span><span class="sxs-lookup"><span data-stu-id="c21e4-140">The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="c21e4-141">**使用者**：執行動作並觸發事件的使用者 (或服務帳戶)。</span><span class="sxs-lookup"><span data-stu-id="c21e4-141">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="c21e4-142">**活動**：使用者執行的活動。</span><span class="sxs-lookup"><span data-stu-id="c21e4-142">**Activity**: The activity performed by the user.</span></span> <span data-ttu-id="c21e4-143">這個值對應您在 [活動] 下拉式清單中選取的活動。</span><span class="sxs-lookup"><span data-stu-id="c21e4-143">This value corresponds to the activities that you selected in the Activities drop down list.</span></span> <span data-ttu-id="c21e4-144">若是來自 Exchange 系統管理員稽核記錄的事件，此欄中的這個值則是 Exchange Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c21e4-144">For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="c21e4-145">**項目**：已建立或修改為對應活動結果的物件。</span><span class="sxs-lookup"><span data-stu-id="c21e4-145">**Item**: The object that was created or modified as a result of the corresponding activity.</span></span> <span data-ttu-id="c21e4-146">例如，已檢視或修改的檔案或已更新的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c21e4-146">For example, the file that was viewed or modified or the user account that was updated.</span></span> <span data-ttu-id="c21e4-147">並非所有活動在此資料行中都具有值。</span><span class="sxs-lookup"><span data-stu-id="c21e4-147">Not all activities have a value in this column.</span></span>

- <span data-ttu-id="c21e4-148">**詳細資料**： 活動相關的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c21e4-148">**Detail**: Additional detail about an activity.</span></span> <span data-ttu-id="c21e4-149">同樣地，並非所有活動會都有一個值。</span><span class="sxs-lookup"><span data-stu-id="c21e4-149">Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="c21e4-150">步驟 3：篩選搜尋結果</span><span class="sxs-lookup"><span data-stu-id="c21e4-150">Step 3: Filter the search results</span></span>

<span data-ttu-id="c21e4-151">除了排序，您也可以篩選稽核記錄搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="c21e4-151">In addition to sorting, you can also filter the results of an audit log search.</span></span> <span data-ttu-id="c21e4-152">這可協助您快速篩選特定使用者或活動的結果。</span><span class="sxs-lookup"><span data-stu-id="c21e4-152">This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="c21e4-153">若要篩選結果：</span><span class="sxs-lookup"><span data-stu-id="c21e4-153">To filter the results:</span></span>

 1. <span data-ttu-id="c21e4-154">建立並執行稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="c21e4-154">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="c21e4-155">當顯示結果時，按一下 [篩選結果]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c21e4-155">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="c21e4-156">關鍵字方塊隨即顯示在每個欄標頭底下。</span><span class="sxs-lookup"><span data-stu-id="c21e4-156">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="c21e4-157">按一下欄標頭底下的其中一個方塊，然後輸入字詞或片語 (視您正在篩選的欄而定)。</span><span class="sxs-lookup"><span data-stu-id="c21e4-157">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on.</span></span> <span data-ttu-id="c21e4-158">結果將動態重新調整為顯示與您的篩選相符之事件。</span><span class="sxs-lookup"><span data-stu-id="c21e4-158">The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="c21e4-159">若要清除篩選，請按一下 [篩選] 方塊中的**X**或只要按一下 [**隱藏篩選**。</span><span class="sxs-lookup"><span data-stu-id="c21e4-159">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="c21e4-160">將搜尋結果匯出至檔案</span><span class="sxs-lookup"><span data-stu-id="c21e4-160">Export the search results to a file</span></span>

<span data-ttu-id="c21e4-161">您可以將稽核記錄搜尋結果匯出至本機電腦上的逗點分隔的值 (CSV) 檔案。</span><span class="sxs-lookup"><span data-stu-id="c21e4-161">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer.</span></span> <span data-ttu-id="c21e4-162">您可以在 Microsoft Excel 中開啟此檔案，並使用多個資料行到功能，例如搜尋，排序、 篩選及分割的單一資料行 （包含多重值的儲存格）。</span><span class="sxs-lookup"><span data-stu-id="c21e4-162">You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="c21e4-163">執行稽核記錄搜尋，然後修改搜尋準則，直到您獲得想要的結果為止。</span><span class="sxs-lookup"><span data-stu-id="c21e4-163">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="c21e4-164">按一下 [匯出結果]，然後選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="c21e4-164">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="c21e4-165">**儲存載入結果：** 選擇此選項以匯出**結果**底下會顯示在**人員感興趣稽核記錄搜尋**] 頁面上的項目。</span><span class="sxs-lookup"><span data-stu-id="c21e4-165">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **People of interest Audit log search** page.</span></span> <span data-ttu-id="c21e4-166">下載的 CSV 檔案會包含與頁面上顯示相同的欄 (及資料) (日期、使用者、活動、項目及詳細資料)。</span><span class="sxs-lookup"><span data-stu-id="c21e4-166">The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details).</span></span> <span data-ttu-id="c21e4-167">（標題為**多個**） 額外一欄隨附於 CSV 檔案包含稽核記錄項目從的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c21e4-167">An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry.</span></span> <span data-ttu-id="c21e4-168">因為您正在匯出 [稽核記錄搜尋] 頁面上所載入的相同結果 (且可檢視)，因此最多可匯出 5,000 個項目。</span><span class="sxs-lookup"><span data-stu-id="c21e4-168">Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="c21e4-169">**下載所有的結果：** 選擇此選項以從符合搜尋準則的 Office 365 稽核記錄檔匯出所有的項目。</span><span class="sxs-lookup"><span data-stu-id="c21e4-169">**Download all results:** Choose this option to export all entries from the Office 365 audit log that meet the search criteria.</span></span> <span data-ttu-id="c21e4-170">一組大型的搜尋結果，選擇此選項以下載此外在可顯示**人員的利息稽核記錄**搜尋] 頁面 5000 筆結果到稽核記錄中的所有項目。</span><span class="sxs-lookup"><span data-stu-id="c21e4-170">For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **People of interest Audit log** search page.</span></span> <span data-ttu-id="c21e4-171">此選項將稽核記錄檔從下載的未經處理資料至 CSV 檔案，並包含名為 AuditData] 欄中的稽核記錄項目中的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="c21e4-171">This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData.</span></span> <span data-ttu-id="c21e4-172">如果您選擇此匯出選項，下載檔案可能需要較久的時間。這是因為如果您選擇其他選項，檔案可能會遠大於下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="c21e4-172">It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="c21e4-173">您可以從單一稽核記錄搜尋下載最多 50,000 個項目至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="c21e4-173">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="c21e4-174">如果已下載 50,000 個項目至 CSV 檔案，您可能可以假設有超過 50,000 個符合搜尋準則的事件。</span><span class="sxs-lookup"><span data-stu-id="c21e4-174">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="c21e4-175">若要匯出的內容超過此限制，請嘗試使用日期範圍來縮小稽核記錄項目的數量。</span><span class="sxs-lookup"><span data-stu-id="c21e4-175">To export more than this limit, try using a date range to reduce the number of audit log entries.</span></span> <span data-ttu-id="c21e4-176">您可能需要使用較小的日期範圍執行多次搜尋，以匯出 50,000 個以上的項目。</span><span class="sxs-lookup"><span data-stu-id="c21e4-176">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="c21e4-177">選取 [匯出] 選項後，會提示您開啟 CSV 檔案，將它儲存到 [下載項目] 資料夾中，或將其儲存至特定資料夾視窗底部顯示訊息</span><span class="sxs-lookup"><span data-stu-id="c21e4-177">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="c21e4-178">如需檢視的詳細資訊，篩選，或匯出稽核記錄搜尋結果，請參閱[的搜尋稽核記錄在 Office 365](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="c21e4-178">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Office 365](search-the-audit-log-in-security-and-compliance.md).</span></span>
