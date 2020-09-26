---
title: 查看相關人員的「審計」活動
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
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
description: 您可以在調查中存取和搜尋活動，以使用資料調查 (預覽) 調查中的人員感興趣的管理工具。
ms.openlocfilehash: e5369307894726c37d465fad6c29c1dac0e7391c
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285929"
---
# <a name="view-the-audit-activity-of-people-of-interest"></a><span data-ttu-id="e117d-103">查看相關人員的「審計」活動</span><span class="sxs-lookup"><span data-stu-id="e117d-103">View the audit activity of people of interest</span></span>

<span data-ttu-id="e117d-104">需要了解是否有使用者已檢視特定文件或清除信箱中的項目嗎？</span><span class="sxs-lookup"><span data-stu-id="e117d-104">Need to find if a user viewed a specific document or purged an item from their mailbox?</span></span> <span data-ttu-id="e117d-105">資料調查 (預覽) 現在已與安全性 & 合規性中心內的現有「審核記錄」搜尋工具整合。</span><span class="sxs-lookup"><span data-stu-id="e117d-105">Data Investigations (preview) is now integrated with the existing audit log search tool in the Security & Compliance Center.</span></span> <span data-ttu-id="e117d-106">使用此內嵌經驗，您可以使用「資料調查 (預覽」) 感興趣的管理工具，以協助您進行調查，輕鬆存取和搜尋活動以取得調查中的利益人員。</span><span class="sxs-lookup"><span data-stu-id="e117d-106">Using this embedded experience, you can use the Data Investigations (preview) People of interest Management tool to facilitate your investigation by easily accessing and searching the activity for people of interest within your investigation.</span></span>

## <a name="get-permissions"></a><span data-ttu-id="e117d-107">取得許可權</span><span class="sxs-lookup"><span data-stu-id="e117d-107">Get permissions</span></span>

<span data-ttu-id="e117d-108">您必須在 Exchange Online 中獲派為 [僅限檢視稽核記錄] 或 [稽核記錄] 角色，才能搜尋稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="e117d-108">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="e117d-109">根據預設，這些角色會在 Exchange 系統管理員中心的 [權限] 頁面上，指派給 [法務遵循管理] 和 [組織管理] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="e117d-109">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="e117d-110">若要讓使用者能夠搜尋資料調查 (預覽) 具有最低許可權等級的審計記錄，您可以在 Exchange Online 中建立自訂角色群組、新增 [View-Only 審核記錄] 或 [審核記錄] 角色，然後將該使用者新增為新角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e117d-110">To give a user the ability to search the Data Investigations (preview) audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="e117d-111">如需詳細資訊，請參閱管理 Exchange Online 中的角色群組。</span><span class="sxs-lookup"><span data-stu-id="e117d-111">For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e117d-112">如果您在安全性 & 規範中心的 [許可權] 頁面上指派使用者 View-Only 的「審核記錄」或「審核記錄」角色，他們將無法搜尋審核記錄。</span><span class="sxs-lookup"><span data-stu-id="e117d-112">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the audit log.</span></span> <span data-ttu-id="e117d-113">您必須在 Exchange Online 中指派權限。</span><span class="sxs-lookup"><span data-stu-id="e117d-113">You have to assign the permissions in Exchange Online.</span></span> <span data-ttu-id="e117d-114">這是因為用來搜尋稽核記錄的基礎 Cmdlet 是 Exchange Online Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e117d-114">This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-create-an-data-investigations-preview-audit-log-search"></a><span data-ttu-id="e117d-115">步驟1：建立資料調查 (預覽) 審核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="e117d-115">Step 1: Create an Data Investigations (preview) audit log search</span></span>

   1. <span data-ttu-id="e117d-116">從 \*\*安全性 & 規範中心 > 「資料調查」 (預覽) \*\*中，選取現有的調查。</span><span class="sxs-lookup"><span data-stu-id="e117d-116">Select an existing investigation from the **Security & Compliance Center > Data Investigations (preview)**.</span></span>

   2. <span data-ttu-id="e117d-117">流覽至 [ **興趣人員** ] 索引標籤，然後選取人員。</span><span class="sxs-lookup"><span data-stu-id="e117d-117">Navigate to the **People of interest** tab and select a person.</span></span>

   3. <span data-ttu-id="e117d-118">選取人員後，按一下 [詳細資料] 窗格中的 [ **查看活動** ]。</span><span class="sxs-lookup"><span data-stu-id="e117d-118">Once you have selected a person, click **View Activity** from the details panel.</span></span>

   4. <span data-ttu-id="e117d-119">設定下列搜尋準則：</span><span class="sxs-lookup"><span data-stu-id="e117d-119">Configure the following search criteria:</span></span>

      <span data-ttu-id="e117d-120">a.</span><span class="sxs-lookup"><span data-stu-id="e117d-120">a.</span></span> <span data-ttu-id="e117d-121">**活動** -按一下下拉式清單，以顯示您可以搜尋的活動。</span><span class="sxs-lookup"><span data-stu-id="e117d-121">**Activities** - Click the drop-down list to display the activities that you can search for.</span></span> <span data-ttu-id="e117d-122">執行搜尋後，只會顯示所選活動的審計記錄。</span><span class="sxs-lookup"><span data-stu-id="e117d-122">After you run the search, only the audit records for the selected activities are displayed.</span></span> <span data-ttu-id="e117d-123">選取 [ **顯示所有活動的結果** ]，會顯示符合其他搜尋準則之所有活動的結果。</span><span class="sxs-lookup"><span data-stu-id="e117d-123">Selecting **Show results for all activities** will display results for all activities that meet the other search criteria.</span></span>

      <span data-ttu-id="e117d-124">b.</span><span class="sxs-lookup"><span data-stu-id="e117d-124">b.</span></span> <span data-ttu-id="e117d-125">**開始日期和結束日期** -選取日期和時間範圍，以顯示在該期間內發生的事件。</span><span class="sxs-lookup"><span data-stu-id="e117d-125">**Start date and End date** - Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="e117d-126">預設會選取最後七天。</span><span class="sxs-lookup"><span data-stu-id="e117d-126">The last seven days are selected by default.</span></span> <span data-ttu-id="e117d-127">日期和時間以國際標準時間 (UTC) 格式表示。</span><span class="sxs-lookup"><span data-stu-id="e117d-127">The date and time are presented in Coordinated Universal Time (UTC) format.</span></span> <span data-ttu-id="e117d-128">您可以指定的最大日期範圍是一年。</span><span class="sxs-lookup"><span data-stu-id="e117d-128">The maximum date range that you can specify is one year.</span></span>

      <span data-ttu-id="e117d-129">c.</span><span class="sxs-lookup"><span data-stu-id="e117d-129">c.</span></span> <span data-ttu-id="e117d-130">**感興趣的人員** -按一下此方塊，然後選取要顯示搜尋結果的特定保管人。</span><span class="sxs-lookup"><span data-stu-id="e117d-130">**People of interest** - Click in this box and then select a specific custodian to display search results for.</span></span> <span data-ttu-id="e117d-131">您在此方塊中選取之使用者所執行之選取活動的審計記錄會顯示在結果清單中。</span><span class="sxs-lookup"><span data-stu-id="e117d-131">Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>

   5. <span data-ttu-id="e117d-132">按一下 [搜尋]\*\*\*\* 以使用您的搜尋準則執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="e117d-132">Click **Search** to run the search using your search criteria.</span></span> <span data-ttu-id="e117d-133">搜尋結果會載入，並在一段時間之後，顯示「興趣活動人員搜尋」頁面上的 [結果] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e117d-133">The search results are loaded, and after a few moments they are displayed under Results on the People of interest Activities search page.</span></span>

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="e117d-134">步驟2：查看審核記錄搜尋結果</span><span class="sxs-lookup"><span data-stu-id="e117d-134">Step 2: View the audit log search results</span></span>

<span data-ttu-id="e117d-135">審核記錄搜尋的結果會顯示在 [感興趣之人員的審計記錄檔] 頁面的 [結果] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="e117d-135">The results of an audit log search are displayed under Results on the People of interest Audit log page.</span></span> <span data-ttu-id="e117d-136">最多 5000 (最新的) 事件會以150事件的增量顯示。</span><span class="sxs-lookup"><span data-stu-id="e117d-136">A maximum of 5,000 (newest) events are displayed in increments of 150 events.</span></span> <span data-ttu-id="e117d-137">若要顯示更多事件，您可以在 [結果] 窗格中使用捲軸列，或按 Shift + End 顯示後續 150 個事件。</span><span class="sxs-lookup"><span data-stu-id="e117d-137">To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="e117d-138">結果包含搜尋傳回之每個事件的下列相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e117d-138">The results contain the following information about each event returned by the search.</span></span>

- <span data-ttu-id="e117d-139">**日期：** 事件發生時的日期和時間 (以 UTC 格式顯示)。</span><span class="sxs-lookup"><span data-stu-id="e117d-139">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="e117d-140">**IP 位址：** 記錄活動時所使用的裝置之 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e117d-140">**IP address**: The IP address of the device that was used when the activity was logged.</span></span> <span data-ttu-id="e117d-141">IP 位址會以 IPv4 或 IPv6 位址格式顯示。</span><span class="sxs-lookup"><span data-stu-id="e117d-141">The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="e117d-142">**使用者**：執行動作並觸發事件的使用者 (或服務帳戶)。</span><span class="sxs-lookup"><span data-stu-id="e117d-142">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="e117d-143">**活動**：使用者執行的活動。</span><span class="sxs-lookup"><span data-stu-id="e117d-143">**Activity**: The activity performed by the user.</span></span> <span data-ttu-id="e117d-144">這個值對應您在 [活動] 下拉式清單中選取的活動。</span><span class="sxs-lookup"><span data-stu-id="e117d-144">This value corresponds to the activities that you selected in the Activities drop down list.</span></span> <span data-ttu-id="e117d-145">若是來自 Exchange 系統管理員稽核記錄的事件，此欄中的這個值則是 Exchange Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e117d-145">For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="e117d-146">**項目**：已建立或修改為對應活動結果的物件。</span><span class="sxs-lookup"><span data-stu-id="e117d-146">**Item**: The object that was created or modified as a result of the corresponding activity.</span></span> <span data-ttu-id="e117d-147">例如，已檢視或修改的檔案或已更新的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e117d-147">For example, the file that was viewed or modified or the user account that was updated.</span></span> <span data-ttu-id="e117d-148">並非所有活動在此資料行中都具有值。</span><span class="sxs-lookup"><span data-stu-id="e117d-148">Not all activities have a value in this column.</span></span>

- <span data-ttu-id="e117d-149">**詳細**資訊：有關活動的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e117d-149">**Detail**: Additional detail about an activity.</span></span> <span data-ttu-id="e117d-150">同樣地，並非所有活動都具有值。</span><span class="sxs-lookup"><span data-stu-id="e117d-150">Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="e117d-151">步驟 3：篩選搜尋結果</span><span class="sxs-lookup"><span data-stu-id="e117d-151">Step 3: Filter the search results</span></span>

<span data-ttu-id="e117d-152">除了排序，您也可以篩選稽核記錄搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="e117d-152">In addition to sorting, you can also filter the results of an audit log search.</span></span> <span data-ttu-id="e117d-153">這可協助您快速篩選特定使用者或活動的結果。</span><span class="sxs-lookup"><span data-stu-id="e117d-153">This can help you quickly filter the results for a specific user or activity.</span></span>

<span data-ttu-id="e117d-154">若要篩選結果：</span><span class="sxs-lookup"><span data-stu-id="e117d-154">To filter the results:</span></span>

1. <span data-ttu-id="e117d-155">建立並執行審核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="e117d-155">Create and run an audit log search.</span></span>

2. <span data-ttu-id="e117d-156">當顯示結果時，按一下 [篩選結果]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e117d-156">When the results are displayed, click **Filter results**.</span></span>

3. <span data-ttu-id="e117d-157">關鍵字方塊隨即顯示在每個欄標頭底下。</span><span class="sxs-lookup"><span data-stu-id="e117d-157">Keyword boxes are displayed under each column header.</span></span>

4. <span data-ttu-id="e117d-158">按一下欄標頭底下的其中一個方塊，然後輸入字詞或片語 (視您正在篩選的欄而定)。</span><span class="sxs-lookup"><span data-stu-id="e117d-158">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on.</span></span> <span data-ttu-id="e117d-159">結果將動態重新調整為顯示與您的篩選相符之事件。</span><span class="sxs-lookup"><span data-stu-id="e117d-159">The results will dynamically readjust to display the events that match your filter.</span></span>

5. <span data-ttu-id="e117d-160">若要清除篩選，請按一下 [篩選] 方塊中的 **X** 或只按一下 [ **隱藏篩選**]。</span><span class="sxs-lookup"><span data-stu-id="e117d-160">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="e117d-161">將搜尋結果匯出至檔案</span><span class="sxs-lookup"><span data-stu-id="e117d-161">Export the search results to a file</span></span>

<span data-ttu-id="e117d-162">您可以將審核記錄搜尋的結果匯出為以逗號分隔的值 (本機電腦上的 CSV) 檔案。</span><span class="sxs-lookup"><span data-stu-id="e117d-162">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer.</span></span> <span data-ttu-id="e117d-163">您可以在 Microsoft Excel 中開啟此檔案，並使用諸如搜尋、排序、篩選和分割包含多值儲存格的單一欄 () 多個欄中的功能。</span><span class="sxs-lookup"><span data-stu-id="e117d-163">You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="e117d-164">執行稽核記錄搜尋，然後修改搜尋準則，直到您獲得想要的結果為止。</span><span class="sxs-lookup"><span data-stu-id="e117d-164">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>

2. <span data-ttu-id="e117d-165">按一下 [匯出結果]，然後選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="e117d-165">Click Export results and select one of the following options:</span></span>

   - <span data-ttu-id="e117d-166">**儲存載入的結果：** 選擇此選項，只會匯出「**關注的人員審計記錄搜尋**」頁面的 [**結果**] 底下顯示的專案。</span><span class="sxs-lookup"><span data-stu-id="e117d-166">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **People of interest Audit log search** page.</span></span> <span data-ttu-id="e117d-167">下載的 CSV 檔案會包含與頁面上顯示相同的欄 (及資料) (日期、使用者、活動、項目及詳細資料)。</span><span class="sxs-lookup"><span data-stu-id="e117d-167">The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details).</span></span> <span data-ttu-id="e117d-168">包含更 **多**)  (的其他欄包含來自審計記錄專案的詳細資訊，包含在 CSV 檔案中。</span><span class="sxs-lookup"><span data-stu-id="e117d-168">An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry.</span></span> <span data-ttu-id="e117d-169">因為您正在匯出 [稽核記錄搜尋] 頁面上所載入的相同結果 (且可檢視)，因此最多可匯出 5,000 個項目。</span><span class="sxs-lookup"><span data-stu-id="e117d-169">Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>

   - <span data-ttu-id="e117d-170">**下載所有結果：** 選擇此選項可從符合搜尋準則的審計記錄中匯出所有專案。</span><span class="sxs-lookup"><span data-stu-id="e117d-170">**Download all results:** Choose this option to export all entries from the audit log that meet the search criteria.</span></span> <span data-ttu-id="e117d-171">針對大型搜尋結果集，請選擇此選項，從審核記錄中下載所有專案，除了可能顯示在「 **關注的人員」審計記錄** 檔搜尋頁面上的5000結果。</span><span class="sxs-lookup"><span data-stu-id="e117d-171">For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **People of interest Audit log** search page.</span></span> <span data-ttu-id="e117d-172">此選項會從審核記錄檔下載原始資料到 CSV 檔案，並包含來自名為 AuditData 的欄中的審計記錄專案的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="e117d-172">This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData.</span></span> <span data-ttu-id="e117d-173">如果您選擇此匯出選項，下載檔案可能需要較久的時間。這是因為如果您選擇其他選項，檔案可能會遠大於下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="e117d-173">It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="e117d-174">您可以從單一稽核記錄搜尋下載最多 50,000 個項目至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="e117d-174">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="e117d-175">如果已下載 50,000 個項目至 CSV 檔案，您可能可以假設有超過 50,000 個符合搜尋準則的事件。</span><span class="sxs-lookup"><span data-stu-id="e117d-175">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="e117d-176">若要匯出的內容超過此限制，請嘗試使用日期範圍來縮小稽核記錄項目的數量。</span><span class="sxs-lookup"><span data-stu-id="e117d-176">To export more than this limit, try using a date range to reduce the number of audit log entries.</span></span> <span data-ttu-id="e117d-177">您可能需要使用較小的日期範圍執行多次搜尋，以匯出 50,000 個以上的項目。</span><span class="sxs-lookup"><span data-stu-id="e117d-177">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>

3. <span data-ttu-id="e117d-178">選取匯出選項之後，會在視窗底部顯示一則訊息，提示您開啟 CSV 檔、將其儲存至 [下載] 資料夾，或將其儲存至特定資料夾。</span><span class="sxs-lookup"><span data-stu-id="e117d-178">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="e117d-179">如需查看、篩選或匯出審計記錄搜尋結果的詳細資訊，請參閱 [搜尋 Office 365 中的「審核記錄](search-the-audit-log-in-security-and-compliance.md)」。</span><span class="sxs-lookup"><span data-stu-id="e117d-179">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Office 365](search-the-audit-log-in-security-and-compliance.md).</span></span>
