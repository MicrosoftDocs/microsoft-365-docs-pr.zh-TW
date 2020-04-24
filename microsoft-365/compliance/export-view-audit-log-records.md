---
title: 匯出、 設定及檢視稽核記錄檔的記錄
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: 將審核記錄搜尋的結果匯出並下載到 CSV 檔案之後，您可以在 Excel 的 Power Query 編輯器中使用 JSON 轉換功能，將 AuditData 欄中 JSON 物件的每個屬性都分割成自己的資料行。 這可協助您快速找到您要尋找的特定審核資料。 您也可以使用 PowerShell 來搜尋和匯出審計記錄檔。
ms.openlocfilehash: c06fbe28a62cf04e1ffdd6ecf173d027e89b5074
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/24/2020
ms.locfileid: "43799926"
---
# <a name="export-configure-and-view-audit-log-records"></a><span data-ttu-id="1a5d4-105">匯出、 設定及檢視稽核記錄檔的記錄</span><span class="sxs-lookup"><span data-stu-id="1a5d4-105">Export, configure, and view audit log records</span></span>

<span data-ttu-id="1a5d4-106">在您搜尋審核記錄並將搜尋結果下載至 CSV 檔案之後，該檔案會包含一個名為**AuditData**的欄，其中包含每個事件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-106">After you search the audit log and download the search results to a CSV file, the file contains a column named **AuditData**, which contains additional information about each event.</span></span> <span data-ttu-id="1a5d4-107">此欄中的資料已格式化為 JSON 物件，包含多個屬性設定為*property：值*組合，以逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-107">The data in this column is formatted as a JSON object, which contains multiple properties that are configured as *property:value* pairs separated by commas.</span></span> <span data-ttu-id="1a5d4-108">您可以在 Excel 的 Power Query 編輯器中使用 JSON 轉換功能，將**AuditData**欄中 JSON 物件的每個屬性分割成多個欄，使每個屬性都有自己的資料行。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-108">You can use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into multiple columns so that each property has its own column.</span></span> <span data-ttu-id="1a5d4-109">這可讓您在一個或多個屬性上進行排序和篩選，這可協助您快速找到所要尋找的特定審核資料。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-109">This lets you sort and filter on one or more of these properties, which can help you quickly locate the specific auditing data you're looking for.</span></span>

## <a name="step-1-export-audit-log-search-results"></a><span data-ttu-id="1a5d4-110">步驟1：匯出審計記錄搜尋結果</span><span class="sxs-lookup"><span data-stu-id="1a5d4-110">Step 1: Export audit log search results</span></span>

<span data-ttu-id="1a5d4-111">第一步是搜尋審核記錄檔，然後將結果以逗號分隔值（CSV）檔案匯出到您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-111">The first step is to search the audit log and then export the results in a comma-separated value (CSV) file to your local computer.</span></span>
  
1. <span data-ttu-id="1a5d4-112">如有需要，請執行[審計記錄搜尋](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log)並修正搜尋準則，直到您有需要的結果為止。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-112">Run an [audit log search](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) and revise the search criteria if necessary until you have the desired results.</span></span>

2. <span data-ttu-id="1a5d4-113">按一下 [**匯出結果**]，然後選取 [**下載所有結果**]。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-113">Click **Export results** and select **Download all results**.</span></span> 

   ![按一下 [下載所有結果]](../media/ExportAuditSearchResults.png)

   <span data-ttu-id="1a5d4-115">此選項可從您在步驟1中執行的審計記錄搜尋中匯出所有的審計記錄，並將原始資料從審核記錄檔下載到 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-115">This option to exports all the audit records from the audit log search you ran in step 1, and downloads the raw data from the audit log to a CSV file.</span></span> 

   <span data-ttu-id="1a5d4-116">會在視窗底部顯示一則訊息，提示您開啟或儲存 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-116">A message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span> 

3. <span data-ttu-id="1a5d4-117">按一下 [**儲存 > 另存**新檔]，然後將 CSV 檔案儲存至本機電腦。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-117">Click **Save > Save as** and save the CSV file to your local computer.</span></span> <span data-ttu-id="1a5d4-118">下載許多搜尋結果需要一段時間。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-118">It takes a while to download many search results.</span></span> <span data-ttu-id="1a5d4-119">這通常是搜尋所有活動或廣泛的日期範圍時的情況。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-119">This is typically the case when searching for all activities or a broad date range.</span></span> <span data-ttu-id="1a5d4-120">當 CSV 檔案下載完畢後，就會顯示視窗底部的訊息。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-120">A message at the bottom of the windows is displayed when the CSV file is finished downloading.</span></span>

   ![當 CSV 檔案下載完成時所顯示的訊息](../media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > <span data-ttu-id="1a5d4-122">您可以從單一稽核記錄搜尋下載最多 50,000 個項目至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-122">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="1a5d4-123">如果已下載 50,000 個項目至 CSV 檔案，您可能可以假設有超過 50,000 個符合搜尋準則的事件。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-123">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="1a5d4-124">若要匯出超過此限制，請嘗試使用日期範圍來減少審計記錄檔的數量。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-124">To export more than this limit, try using a date range to reduce the number of audit log records.</span></span> <span data-ttu-id="1a5d4-125">您可能需要使用較小的日期範圍執行多次搜尋，以匯出 50,000 個以上的項目。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-125">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a><span data-ttu-id="1a5d4-126">步驟2：使用 Power Query 編輯器格式化匯出的審計記錄檔</span><span class="sxs-lookup"><span data-stu-id="1a5d4-126">Step 2: Format the exported audit log using the Power Query Editor</span></span>

<span data-ttu-id="1a5d4-127">下一步是在 Excel 的 Power Query 編輯器中使用 JSON 轉換功能，將**AuditData**欄中 JSON 物件中的每個屬性分割成自己的資料行。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-127">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="1a5d4-128">然後，根據特定屬性的值，篩選欄以查看記錄。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-128">Then you filter columns to view records based on the values of specific properties.</span></span> <span data-ttu-id="1a5d4-129">這可協助您快速找到您要尋找的特定審核資料。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-129">This can help you quickly locate the specific auditing data you're looking for.</span></span>

1. <span data-ttu-id="1a5d4-130">在 Excel 中開啟空白活頁簿，以供 Office 365、Excel 2019 或 Excel 2016 使用。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-130">Open a blank workbook in Excel for Office 365, Excel 2019, or Excel 2016.</span></span>

2. <span data-ttu-id="1a5d4-131">在 [**資料**] 索引標籤的 [**取得 & 轉換資料**] 功能區群組中，按一下 [**從文字/CSV**]。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-131">On the **Data** tab, in the **Get & Transform Data** ribbon group, click **From Text/CSV**.</span></span>

    ![在 [資料] 索引標籤上，按一下 [從文字/CSV]](../media/JSONTransformOpenCSVFile.png)

3. <span data-ttu-id="1a5d4-133">開啟您在步驟1中下載的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-133">Open the CSV file that you downloaded in Step 1.</span></span>

4. <span data-ttu-id="1a5d4-134">在顯示的視窗中，按一下 [**轉換資料**]。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-134">In the window that's displayed, click **Transform Data**.</span></span>

   ![按一下 [轉換資料]](../media/JSONOpenPowerQuery.png)

   <span data-ttu-id="1a5d4-136">CSV 檔案會在**查詢編輯器**中開啟。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-136">The CSV file is opened in the **Query Editor**.</span></span> <span data-ttu-id="1a5d4-137">有四個欄： **CreationDate**、 **UserIds**、**作業**及**AuditData**。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-137">There are four columns: **CreationDate**, **UserIds**, **Operations**, and **AuditData**.</span></span> <span data-ttu-id="1a5d4-138">**AuditData**欄是包含多個屬性的 JSON 物件。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-138">The **AuditData** column is a JSON object that contains multiple properties.</span></span> <span data-ttu-id="1a5d4-139">下一步是為 JSON 物件中的每個屬性建立欄。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-139">The next step is to create a column for each property in the JSON object.</span></span>

5. <span data-ttu-id="1a5d4-140">以滑鼠右鍵按一下 [ **AuditData** ] 欄中的標題，按一下 [**轉換**]，然後按一下 [ **JSON**]。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-140">Right-click the title in the **AuditData** column, click **Transform**, and then click **JSON**.</span></span> 

   ![以滑鼠右鍵按一下 [AuditData] 欄，按一下 [轉換]，然後選取 [JSON]。](../media/JSONTransform.png)

6. <span data-ttu-id="1a5d4-142">在 [ **AuditData** ] 欄的右上角，按一下展開圖示。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-142">In the upper-right corner of the **AuditData** column, click the expand icon.</span></span>

   ![在 [AuditData] 欄中，按一下展開圖示](../media/JSONTransformExpandIcon.png)

   <span data-ttu-id="1a5d4-144">隨即會顯示 [ **AuditData** ] 欄中 JSON 物件的屬性部分清單。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-144">A partial list of the properties in the JSON objects in the **AuditData** column is displayed.</span></span>

7. <span data-ttu-id="1a5d4-145">按一下 [**載入更多**]，以在 [ **AuditData** ] 欄中顯示 JSON 物件中的所有屬性。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-145">Click **Load more** to display all properties in the JSON objects in the **AuditData** column.</span></span>

   ![按一下 [載入更多] 以顯示 JSON 物件中的所有屬性](../media/JSONTransformLoadJSONProperties.png)

   <span data-ttu-id="1a5d4-147">您可以取消選取不想要包含的任何屬性旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-147">You can unselect the checkbox next to any property that you don't want to include.</span></span> <span data-ttu-id="1a5d4-148">消除對調查沒有用的資料行，是減少審核記錄中所顯示之資料量的好方法。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-148">Eliminating columns that aren't useful for your investigation is a good way to reduce the amount of data displayed in the audit log.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="1a5d4-149">先前的螢幕擷取畫面所顯示的 JSON 屬性（按一下 [**載入更多**]）是以 CSV 檔案中前1000列的**AuditData** ] 欄中找到的屬性為基礎。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-149">The JSON properties displayed in the previous screenshot (after you click **Load more**) are based on the properties found in the **AuditData** column from the first 1,000 rows in the CSV file.</span></span> <span data-ttu-id="1a5d4-150">如果在第一個1000列之後的記錄中有不同的 JSON 屬性，當**AuditData**欄分割成多個欄時，將不會包含這些屬性（和對應的資料行）。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-150">If there are different JSON properties in records after the first 1,000 rows, these properties (and a corresponding column) won't be included when the **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="1a5d4-151">為了協助避免這種情況，請考慮重新執行審核記錄搜尋並縮小搜尋準則，以減少傳回的記錄。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-151">To help prevent this, consider re-running the audit log search and narrow the search criteria so that fewer records are returned.</span></span> <span data-ttu-id="1a5d4-152">另一個解決方法是在 [**作業**] 欄中篩選項目，以減少列數（先執行上述步驟5之前），再轉換**AuditData** ] 欄中的 JSON 物件。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-152">Another workaround is to filter items in the **Operations** column to reduce the number of rows (before you perform step 5 above) before transforming the JSON object in the **AuditData** column.</span></span>

8. <span data-ttu-id="1a5d4-153">請執行下列其中一項動作，以格式化所選取的每個 JSON 屬性所新增的欄標題。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-153">Do one of the following things to format the title of the columns that are added for each JSON property that's selected.</span></span>

    - <span data-ttu-id="1a5d4-154">取消選取 [**使用原始欄名稱做為前置**詞] 核取方塊，以使用 JSON 屬性的名稱做為欄名稱;例如， **RecordType**或**SourceFileName**。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-154">Unselect the **Use original column name as prefix** checkbox to use the name of the JSON property as the column names; for example, **RecordType** or **SourceFileName**.</span></span>

    - <span data-ttu-id="1a5d4-155">選取 [**使用原始欄名稱做為前置**詞] 核取方塊，以將 AuditData 前置詞加入欄名稱中;例如， **AuditData。 RecordType**或**AuditData SourceFileName**。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-155">Leave the **Use original column name as prefix** checkbox selected to add the AuditData prefix to the column names; for example, **AuditData.RecordType** or **AuditData.SourceFileName**.</span></span>

9. <span data-ttu-id="1a5d4-156">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-156">Click **OK**.</span></span>

    <span data-ttu-id="1a5d4-157">**AuditData**欄會分割成多個欄。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-157">The **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="1a5d4-158">每個新欄會對應至 AuditData JSON 物件中的屬性。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-158">Each new column corresponds to a property in the AuditData JSON object.</span></span> <span data-ttu-id="1a5d4-159">資料行中的每一列都包含屬性的值。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-159">Each row in the column contains the value for the property.</span></span> <span data-ttu-id="1a5d4-160">如果此屬性不包含值，則會顯示*null*值。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-160">If the property doesn't contain a value, the *null* value is displayed.</span></span> <span data-ttu-id="1a5d4-161">在 Excel 中，具有 null 值的儲存格是空白的。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-161">In Excel, cells with null values are empty.</span></span>
  
10. <span data-ttu-id="1a5d4-162">在 [**常用**] 索引標籤上，按一下 [**關閉 & 載入**]，關閉 Power Query 編輯器，並在 Excel 活頁簿中開啟轉換後的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-162">On the **Home** tab, click **Close & Load** to close the Power Query Editor and open the transformed CSV file in an Excel workbook.</span></span>

## <a name="use-powershell-to-search-and-export-audit-log-records"></a><span data-ttu-id="1a5d4-163">使用 PowerShell 來搜尋和匯出審計記錄記錄</span><span class="sxs-lookup"><span data-stu-id="1a5d4-163">Use PowerShell to search and export audit log records</span></span>

<span data-ttu-id="1a5d4-164">您可以使用 Exchange Online PowerShell 中的[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) Cmdlet，將審核記錄搜尋的結果匯出至 CSV 檔案，而不是在安全性 & 合規性中心使用「審核記錄搜尋」工具。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-164">Instead of using the audit log search tool in the Security & Compliance Center, you can use the [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) cmdlet in Exchange Online PowerShell to export the results of an audit log search to a CSV file.</span></span> <span data-ttu-id="1a5d4-165">接著，您可以遵循步驟2所述的相同程式，以使用 Power Query 編輯器來格式化審核記錄檔。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-165">Then you can follow the same procedure described in Step 2 to format the audit log using the Power Query editor.</span></span> <span data-ttu-id="1a5d4-166">使用 PowerShell Cmdlet 的其中一個優點是，您可以使用*RecordType*參數，從特定服務搜尋事件。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-166">One advantage of using the PowerShell cmdlet is that you can search for events from a specific service by using the *RecordType* parameter.</span></span> <span data-ttu-id="1a5d4-167">以下是一些使用 PowerShell 將審核記錄匯出至 CSV 檔案的範例，因此您可以使用 Power Query 編輯器，依步驟2所述，在**AuditData**欄中轉換 JSON 物件。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-167">Here are few examples of using PowerShell to export audit records to a CSV file so you can use the Power Query editor to transform the JSON object in the **AuditData** column as described in Step 2.</span></span>

<span data-ttu-id="1a5d4-168">在此範例中，執行下列命令以傳回與 SharePoint 共用作業相關的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-168">In this example, run the following commands to return all records related to SharePoint sharing operations.</span></span>

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

<span data-ttu-id="1a5d4-169">搜尋結果會匯出至名為*PowerShellAuditlog*的 CSV 檔案，該檔案包含四個欄： CreationDate、UserIds、RecordType、AuditData）。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-169">The search results are exported to a CSV file named *PowerShellAuditlog* that contains four columns: CreationDate, UserIds, RecordType, AuditData).</span></span>

<span data-ttu-id="1a5d4-170">您也可以使用 record 類型的 name 或 enum 值做為*RecordType*參數的值。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-170">You can also use the name or enum value for the record type as the value for the *RecordType* parameter.</span></span> <span data-ttu-id="1a5d4-171">如需記錄類型名稱及其對應列舉值的清單，請參閱[Office 365 管理活動 API 架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)中的*AuditLogRecordType*表格。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-171">For a list of record type names and their corresponding enum values, see the *AuditLogRecordType* table in [Office 365 Management Activity API schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32).</span></span>

<span data-ttu-id="1a5d4-172">*RecordType*參數只能包含單一值。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-172">You can only include a single value for the *RecordType* parameter.</span></span> <span data-ttu-id="1a5d4-173">若要搜尋其他記錄類型的審計記錄，您必須再次執行這兩個先前的命令，以指定不同的記錄類型，並將這些結果附加至原始 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-173">To search for audit records for other record types, you have to run the two previous commands again to specify a different record type and append those results to the original CSV file.</span></span> <span data-ttu-id="1a5d4-174">例如，您可以執行下列兩個命令，將相同日期範圍的 SharePoint 檔案活動新增至 PowerShellAuditlog 檔案名。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-174">For example, you would run the following two commands to add SharePoint file activities from the same date range to the PowerShellAuditlog.csv file.</span></span>

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a><span data-ttu-id="1a5d4-175">匯出及查看審核記錄的秘訣</span><span class="sxs-lookup"><span data-stu-id="1a5d4-175">Tips for exporting and viewing the audit log</span></span>

<span data-ttu-id="1a5d4-176">以下是在您使用 JSON 轉換功能將**AuditData**欄分割成多個欄之前和之後，匯出及查看審核記錄的一些秘訣和範例。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-176">Here are some tips and examples of exporting and viewing the audit log before and after you use the JSON transform feature to split the **AuditData** column into multiple columns.</span></span>

- <span data-ttu-id="1a5d4-177">篩選**RecordType**欄，只顯示特定服務或功能區域中的記錄。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-177">Filter the **RecordType** column to display only the records from a specific service or functional area.</span></span> <span data-ttu-id="1a5d4-178">例如，若要顯示與 SharePoint 共用相關的事件，您可以選取 [ **14** ] （由 SharePoint 共用活動所觸發之記錄的列舉值）。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-178">For example, to show events related to SharePoint sharing, you would select **14** (the enum value for records triggered by SharePoint sharing activities).</span></span> <span data-ttu-id="1a5d4-179">如需與**RecordType** ] 欄中所顯示之列舉值相對應的服務清單，請參閱[audit Log 中的詳細](detailed-properties-in-the-office-365-audit-log.md)內容。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-179">For a list of the services that correspond to the enum values displayed in the **RecordType** column, see [Detailed properties in the audit log](detailed-properties-in-the-office-365-audit-log.md).</span></span>

- <span data-ttu-id="1a5d4-180">篩選 [**作業**] 欄，以顯示特定活動的記錄。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-180">Filter the **Operations** column to display the records for specific activities.</span></span> <span data-ttu-id="1a5d4-181">如需與安全性 & 規範中心的「審核記錄」搜尋工具中的可搜尋活動相對應的大部分作業清單，請參閱[安全性 & 規範中心的「搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md#audited-activities)」一節中的「審核的活動」一節。</span><span class="sxs-lookup"><span data-stu-id="1a5d4-181">For a list of most operations that correspond to a searchable activity in the audit log search tool in the Security & Compliance Center, see the "Audited activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>
