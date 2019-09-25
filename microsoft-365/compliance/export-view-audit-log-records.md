---
title: 导出、配置和查看审核日志记录
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
description: 将 Office 365 审核日志搜索的结果导出并下载到 CSV 文件后，可以使用 Excel 中的 Power 查询编辑器中的 JSON 转换功能将 AuditData 列中的 JSON 对象中的每个属性拆分为自己的列。 这可以帮助您快速找到要查找的特定审核数据。
ms.openlocfilehash: 7dac373e8f25ead38dddbe2663e521b35b3153ef
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077032"
---
# <a name="export-configure-and-view-audit-log-records"></a><span data-ttu-id="0c7fd-104">导出、配置和查看审核日志记录</span><span class="sxs-lookup"><span data-stu-id="0c7fd-104">Export, configure, and view audit log records</span></span>

<span data-ttu-id="0c7fd-105">搜索 Office 365 审核日志并将搜索结果下载到 CSV 文件后，该文件包含一个名为**AuditData**的列，其中包含有关每个事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-105">After you search the Office 365 audit log and download the search results to a CSV file, the file contains a column named **AuditData**, which contains additional information about each event.</span></span> <span data-ttu-id="0c7fd-106">此列中的数据被格式化为 JSON 对象，其中包含配置为*属性的多个属性：* 用逗号分隔的值对。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-106">The data in this column is formatted as a JSON object, which contains multiple properties that are configured as *property:value* pairs separated by commas.</span></span> <span data-ttu-id="0c7fd-107">您可以使用 Excel 中的电源查询编辑器中的 JSON 转换功能将**AuditData**列中 JSON 对象中的每个属性拆分为多个列，以便每个属性都有自己的列。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-107">You can use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into multiple columns so that each property has its own column.</span></span> <span data-ttu-id="0c7fd-108">这使您可以对这些属性中的一个或多个进行排序和筛选，这有助于快速查找要查找的特定审核数据。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-108">This lets you sort and filter on one or more of these properties, which can help you quickly locate the specific auditing data you're looking for.</span></span>

## <a name="step-1-export-audit-log-search-results"></a><span data-ttu-id="0c7fd-109">步骤 1：导出审核日志搜索结果</span><span class="sxs-lookup"><span data-stu-id="0c7fd-109">Step 1: Export audit log search results</span></span>

<span data-ttu-id="0c7fd-110">第一步是搜索审核日志，然后将逗号分隔值 （CSV） 文件中的结果导出到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-110">The first step is to search the audit log and then export the results in a comma-separated value (CSV) file to your local computer.</span></span>
  
1. <span data-ttu-id="0c7fd-111">运行[审核日志搜索](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log)并在必要时修改搜索条件，直到获得所需的结果。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-111">Run an [audit log search](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) and revise the search criteria if necessary until you have the desired results.</span></span>
    
2. <span data-ttu-id="0c7fd-112">**单击"导出结果"** 并**选择"下载所有结果"。**</span><span class="sxs-lookup"><span data-stu-id="0c7fd-112">Click **Export results** and select **Download all results**.</span></span> 
    
   ![单击下载所有结果](media/ExportAuditSearchResults.png)

   <span data-ttu-id="0c7fd-114">此选项用于从步骤 1 中运行的审核日志搜索导出所有审核记录，并将原始数据从审核日志下载到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-114">This option to exports all the audit records from the audit log search you ran in step 1, and downloads the raw data from the audit log to a CSV file.</span></span> 

   <span data-ttu-id="0c7fd-115">窗口底部会显示一条消息，提示您打开或保存 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-115">A message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span> 

3. <span data-ttu-id="0c7fd-116">**单击"保存>另存为**CSV 文件并将其保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-116">Click **Save > Save as** and save the CSV file to your local computer.</span></span> <span data-ttu-id="0c7fd-117">下载许多搜索结果需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-117">It takes a while to download many search results.</span></span> <span data-ttu-id="0c7fd-118">在搜索所有活动或宽日期范围时，通常会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-118">This is typically the case when searching for all activities or a broad date range.</span></span> <span data-ttu-id="0c7fd-119">CSV 文件完成下载后，窗口底部将显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-119">A message at the bottom of the windows is displayed when the CSV file is finished downloading.</span></span>
 
   ![CSV 文件下载完成后显示的消息](media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > <span data-ttu-id="0c7fd-121">从单个审核日志搜索中最多可以将 50，000 个条目下载到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-121">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="0c7fd-122">如果将 50，000 个条目下载到 CSV 文件，则可以假定有超过 50，000 个事件符合搜索条件。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-122">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="0c7fd-123">要导出超过此限制，请尝试使用日期范围来减少审核日志记录的数量。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-123">To export more than this limit, try using a date range to reduce the number of audit log records.</span></span> <span data-ttu-id="0c7fd-124">您可能需要运行多个日期范围较小的搜索才能导出超过 50，000 个条目。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-124">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a><span data-ttu-id="0c7fd-125">步骤 2：使用电源查询编辑器格式化导出的审核日志</span><span class="sxs-lookup"><span data-stu-id="0c7fd-125">Step 2: Format the exported audit log using the Power Query Editor</span></span>

<span data-ttu-id="0c7fd-126">下一步是使用 Excel 中的电源查询编辑器中的 JSON 转换功能将**AuditData**列中的 JSON 对象中的每个属性拆分为自己的列。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-126">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="0c7fd-127">然后筛选列以根据特定属性的值查看记录。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-127">Then you filter columns to view records based on the values of specific properties.</span></span> <span data-ttu-id="0c7fd-128">这可以帮助您快速找到要查找的特定审核数据。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-128">This can help you quickly locate the specific auditing data you're looking for.</span></span>

1. <span data-ttu-id="0c7fd-129">在 Office 365、Excel 2019 或 Excel 2016 的 Excel 中打开空白工作簿。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-129">Open a blank workbook in Excel for Office 365, Excel 2019, or Excel 2016.</span></span>
    
2.  <span data-ttu-id="0c7fd-130">在"**数据"** 选项卡上，**在"获取&转换数据**功能区"组中，**单击"从文本/CSV**"。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-130">On the **Data** tab, in the **Get & Transform Data** ribbon group, click **From Text/CSV**.</span></span>

    ![在"数据"选项卡上，单击"从文本/CSV"](media/JSONTransformOpenCSVFile.png)

3. <span data-ttu-id="0c7fd-132">打开您在步骤 1 中下载的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-132">Open the CSV file that you downloaded in Step 1.</span></span>
    
4. <span data-ttu-id="0c7fd-133">在显示的窗口中，**单击"转换数据"。**</span><span class="sxs-lookup"><span data-stu-id="0c7fd-133">In the window that's displayed, click **Transform Data**.</span></span>

   ![单击转换数据](media/JSONOpenPowerQuery.png)

<span data-ttu-id="0c7fd-135">CSV 文件在**查询编辑器**中打开。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-135">The CSV file is opened in the **Query Editor**.</span></span> <span data-ttu-id="0c7fd-136">有四列：**创建日期、\*\*\*\*用户Id、\*\*\*\*操作**和**审核数据。**</span><span class="sxs-lookup"><span data-stu-id="0c7fd-136">There are four columns: **CreationDate**, **UserIds**, **Operations**, and **AuditData**.</span></span> <span data-ttu-id="0c7fd-137">**审核数据**列是包含多个属性的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-137">The **AuditData** column is a JSON object that contains multiple properties.</span></span> <span data-ttu-id="0c7fd-138">下一步是为 JSON 对象中的每个属性创建一个列。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-138">The next step is to create a column for each property in the JSON object.</span></span>
    
5. <span data-ttu-id="0c7fd-139">右键**单击"审核数据"** 列中的标题，**单击"转换"，\*\*\*\*然后单击"JSON**"。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-139">Right-click the title in the **AuditData** column, click **Transform**, and then click **JSON**.</span></span> 
 
   ![右键单击"审核数据"列，单击"转换"，然后选择"JSON"](media/JSONTransform.png)

6. <span data-ttu-id="0c7fd-141">**在"审核数据"** 列的右上角，单击展开图标。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-141">In the upper-right corner of the **AuditData** column, click the expand icon.</span></span>
    
   ![在"审核数据"列中，单击展开图标](media/JSONTransformExpandIcon.png)

   <span data-ttu-id="0c7fd-143">将显示**AuditData**列中 JSON 对象中属性的部分列表。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-143">A partial list of the properties in the JSON objects in the **AuditData** column is displayed.</span></span>

7. <span data-ttu-id="0c7fd-144">**单击"加载更多"** 以**在"审核数据"** 列中显示 JSON 对象中的所有属性。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-144">Click **Load more** to display all properties in the JSON objects in the **AuditData** column.</span></span>

   ![单击"加载更多"以显示 JSON 对象中的所有属性](media/JSONTransformLoadJSONProperties.png)

   <span data-ttu-id="0c7fd-146">您可以取消选中不想包含的任何属性旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-146">You can unselect the checkbox next to any property that you don't want to include.</span></span> <span data-ttu-id="0c7fd-147">删除对调查没有用处的列是减少审核日志中显示的数据量的好方法。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-147">Eliminating columns that aren't useful for your investigation is a good way to reduce the amount of data displayed in the audit log.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="0c7fd-148">上一个屏幕截图中显示的 JSON 属性（在**单击"加载更多"** 之后）基于在 CSV 文件中前 1，000 行中的**AuditData**列中找到的属性。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-148">The JSON properties displayed in the previous screenshot (after you click **Load more**) are based on the properties found in the **AuditData** column from the first 1,000 rows in the CSV file.</span></span> <span data-ttu-id="0c7fd-149">如果前 1，000 行之后记录中存在不同的 JSON 属性，则当**AuditData**列拆分为多列时，这些属性（和相应的列）将不会包括在内。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-149">If there are different JSON properties in records after the first 1,000 rows, these properties (and a corresponding column) won't be included when the **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="0c7fd-150">为了帮助防止这种情况，请考虑重新运行审核日志搜索并缩小搜索条件，以便返回更少的记录。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-150">To help prevent this, consider re-running the audit log search and narrow the search criteria so that fewer records are returned.</span></span> <span data-ttu-id="0c7fd-151">另一种解决方法是**筛选"操作"** 列中的项，以减少**在"审核数据"** 列中转换 JSON 对象之前（在执行上述步骤 5 之前）行数。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-151">Another workaround is to filter items in the **Operations** column to reduce the number of rows (before you perform step 5 above) before transforming the JSON object in the **AuditData** column.</span></span>

8. <span data-ttu-id="0c7fd-152">执行以下操作之一，为所选的每个 JSON 属性添加的列的标题设置格式。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-152">Do one of the following things to format the title of the columns that are added for each JSON property that's selected.</span></span>

    - <span data-ttu-id="0c7fd-153">取消选择"**使用原始列名称作为前缀"** 复选框，将 JSON 属性的名称用作列名称;例如，**记录类型**或**源文件名称**。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-153">Unselect the **Use original column name as prefix** checkbox to use the name of the JSON property as the column names; for example, **RecordType** or **SourceFileName**.</span></span>
    
   - <span data-ttu-id="0c7fd-154">保留选中"**使用原始列名称作为前缀"** 复选框，以将 AuditData 前缀添加到列名称中;例如，**审核数据.记录类型**或**审核数据.源文件名称**。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-154">Leave the **Use original column name as prefix** checkbox selected to add the AuditData prefix to the column names; for example, **AuditData.RecordType** or **AuditData.SourceFileName**.</span></span>

9. <span data-ttu-id="0c7fd-155">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-155">Click **OK**.</span></span>
    
    <span data-ttu-id="0c7fd-156">"**审核数据"** 列被拆分为多列。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-156">The **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="0c7fd-157">每个新列对应于 AuditData JSON 对象中的属性。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-157">Each new column corresponds to a property in the AuditData JSON object.</span></span> <span data-ttu-id="0c7fd-158">列中的每一行都包含属性的值。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-158">Each row in the column contains the value for the property.</span></span> <span data-ttu-id="0c7fd-159">如果属性不包含值，则显示*空*值。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-159">If the property doesn't contain a value, the *null* value is displayed.</span></span> <span data-ttu-id="0c7fd-160">在 Excel 中，具有 null 值的单元格为空。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-160">In Excel, cells with null values are empty.</span></span>
  
10. <span data-ttu-id="0c7fd-161">在"**主页"** 选项卡上，**单击"关闭&加载"** 以关闭电源查询编辑器，并在 Excel 工作簿中打开转换后的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-161">On the **Home** tab, click **Close & Load** to close the Power Query Editor and open the transformed CSV file in an Excel workbook.</span></span> 

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a><span data-ttu-id="0c7fd-162">导出和查看审核日志的提示</span><span class="sxs-lookup"><span data-stu-id="0c7fd-162">Tips for exporting and viewing the audit log</span></span>

<span data-ttu-id="0c7fd-163">以下是在使用 JSON 转换功能将**AuditData**列拆分为多个列之前和之后导出和查看审核日志的一些提示和示例。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-163">Here are some tips and examples of exporting and viewing the audit log before and after you use the JSON transform feature to split the **AuditData** column into multiple columns.</span></span>

- <span data-ttu-id="0c7fd-164">筛选"**记录类型"** 列以仅显示来自特定 Office 365 服务或功能区域的记录。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-164">Filter the **RecordType** column to display only the records from a specific Office 365 service or functional area.</span></span> <span data-ttu-id="0c7fd-165">例如，要显示与 SharePoint 共享相关的事件，请选择**14（SharePoint**共享活动触发的记录的枚举值）。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-165">For example, to show events related to SharePoint sharing, you would select **14** (the enum value for records triggered by SharePoint sharing activities).</span></span> <span data-ttu-id="0c7fd-166">有关与**RecordType**列中显示的枚举值对应的 Office 365 服务的列表，请参阅[Office 365 审核日志中的详细信息。](detailed-properties-in-the-office-365-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="0c7fd-166">For a list of the Office 365 services that correspond to the enum values displayed in the **RecordType** column, see [Detailed properties in the Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md).</span></span>

- <span data-ttu-id="0c7fd-167">筛选"**操作"** 列以显示特定活动的记录。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-167">Filter the **Operations** column to display the records for specific activities.</span></span> <span data-ttu-id="0c7fd-168">有关与安全&合规中心中的审核日志搜索工具中的可搜索活动对应的大多数操作的列表，请参阅[在"安全&合规中心"中搜索审核日志中的"](search-the-audit-log-in-security-and-compliance.md#audited-activities)已审核活动"部分。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-168">For a list of most operations that correspond to a searchable activity in the audit log search tool in the Security & Compliance Center, see the "Audited activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>

- <span data-ttu-id="0c7fd-169">您可以使用 Exchange 在线电源外壳中的[搜索统一审核日志](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog)cmdlet 将 Office 365 审核日志搜索的结果导出到 CSV 文件，而不是使用安全&合规性中心的审核日志搜索工具。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-169">Instead of using the audit log search tool in the Security & Compliance Center, you can use the [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) cmdlet in Exchange Online Powershell to export the results of an Office 365 audit log search to a CSV file.</span></span> <span data-ttu-id="0c7fd-170">然后，您可以按照步骤 2 中描述的相同过程，使用 Power 查询编辑器格式化审核日志。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-170">Then you can follow the same procedure described in Step 2 to format the audit log using the Power Query editor.</span></span> <span data-ttu-id="0c7fd-171">使用 PowerShell cmdlet 的一个优点是，您可以使用*RecordType*参数搜索特定 Office 365 服务中的事件。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-171">One advantage of using the PowerShell cmdlet is that you can search for events from a specific Office 365 service by using the *RecordType* parameter.</span></span> <span data-ttu-id="0c7fd-172">下面是使用 PowerShell 将审核记录导出到 CSV 文件的几个示例，因此您可以使用 Power 查询编辑器转换**AuditData**列中的 JSON 对象，如步骤 2 中所述。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-172">Here are few examples of using PowerShell to export audit records to a CSV file so you can use the Power Query editor to transform the JSON object in the **AuditData** column as described in Step 2.</span></span>

   <span data-ttu-id="0c7fd-173">在此示例中，运行以下命令以返回与 SharePoint 共享操作相关的所有记录。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-173">In this example, run the following commands to return all records related to SharePoint sharing operations.</span></span> 
   
   ```
   $auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
   ```

   ```
   $auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
   ```

   - <span data-ttu-id="0c7fd-174">搜索结果将导出到名为*PowerShellAuditlog*的 CSV 文件，该文件包含四列：创建日期、用户 Id、记录类型、审核数据）。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-174">The search results are exported to a CSV file named *PowerShellAuditlog* that contains four columns: CreationDate, UserIds, RecordType, AuditData).</span></span>

   - <span data-ttu-id="0c7fd-175">可以使用记录类型的名称或枚举值作为*RecordType*参数的值。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-175">You can use the name or enum value for the record type as the value for the *RecordType* parameter.</span></span> <span data-ttu-id="0c7fd-176">有关记录类型名称及其相应的枚举值的列表，请参阅[Office 365 管理活动 API 架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)中的*AuditLogRecordType 类型*表。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-176">For a list of record type names and their corresponding enum values, see the *AuditLogRecordType* table in [Office 365 Management Activity API schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32).</span></span>
   
   - <span data-ttu-id="0c7fd-177">只能包含此参数的单个值。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-177">You can only include a single value for this parameter.</span></span> <span data-ttu-id="0c7fd-178">要搜索其他记录类型的审核记录，必须再次运行前两个命令以指定不同的记录类型并将这些结果追加到原始 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-178">To search for audit records for other record types, you have to run the two previous commands again to specify a different record type and append those results to the original CSV file.</span></span> <span data-ttu-id="0c7fd-179">例如，您将运行这两个命令，将同一日期范围内的 SharePoint 文件活动添加到 PowerShellAuditlog.csv 文件中。</span><span class="sxs-lookup"><span data-stu-id="0c7fd-179">For example, you would run these two commands to add SharePoint file activities from the same date range to the PowerShellAuditlog.csv file.</span></span>

       ```
      $auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
      ```

      ```
      $auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
      ```
