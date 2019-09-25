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
# <a name="export-configure-and-view-audit-log-records"></a>导出、配置和查看审核日志记录

搜索 Office 365 审核日志并将搜索结果下载到 CSV 文件后，该文件包含一个名为**AuditData**的列，其中包含有关每个事件的其他信息。 此列中的数据被格式化为 JSON 对象，其中包含配置为*属性的多个属性：* 用逗号分隔的值对。 您可以使用 Excel 中的电源查询编辑器中的 JSON 转换功能将**AuditData**列中 JSON 对象中的每个属性拆分为多个列，以便每个属性都有自己的列。 这使您可以对这些属性中的一个或多个进行排序和筛选，这有助于快速查找要查找的特定审核数据。

## <a name="step-1-export-audit-log-search-results"></a>步骤 1：导出审核日志搜索结果

第一步是搜索审核日志，然后将逗号分隔值 （CSV） 文件中的结果导出到本地计算机。
  
1. 运行[审核日志搜索](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log)并在必要时修改搜索条件，直到获得所需的结果。
    
2. **单击"导出结果"** 并**选择"下载所有结果"。** 
    
   ![单击下载所有结果](media/ExportAuditSearchResults.png)

   此选项用于从步骤 1 中运行的审核日志搜索导出所有审核记录，并将原始数据从审核日志下载到 CSV 文件。 

   窗口底部会显示一条消息，提示您打开或保存 CSV 文件。 

3. **单击"保存>另存为**CSV 文件并将其保存到本地计算机。 下载许多搜索结果需要一段时间。 在搜索所有活动或宽日期范围时，通常会出现这种情况。 CSV 文件完成下载后，窗口底部将显示一条消息。
 
   ![CSV 文件下载完成后显示的消息](media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > 从单个审核日志搜索中最多可以将 50，000 个条目下载到 CSV 文件。 如果将 50，000 个条目下载到 CSV 文件，则可以假定有超过 50，000 个事件符合搜索条件。 要导出超过此限制，请尝试使用日期范围来减少审核日志记录的数量。 您可能需要运行多个日期范围较小的搜索才能导出超过 50，000 个条目。

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a>步骤 2：使用电源查询编辑器格式化导出的审核日志

下一步是使用 Excel 中的电源查询编辑器中的 JSON 转换功能将**AuditData**列中的 JSON 对象中的每个属性拆分为自己的列。 然后筛选列以根据特定属性的值查看记录。 这可以帮助您快速找到要查找的特定审核数据。

1. 在 Office 365、Excel 2019 或 Excel 2016 的 Excel 中打开空白工作簿。
    
2.  在"**数据"** 选项卡上，**在"获取&转换数据**功能区"组中，**单击"从文本/CSV**"。

    ![在"数据"选项卡上，单击"从文本/CSV"](media/JSONTransformOpenCSVFile.png)

3. 打开您在步骤 1 中下载的 CSV 文件。
    
4. 在显示的窗口中，**单击"转换数据"。**

   ![单击转换数据](media/JSONOpenPowerQuery.png)

CSV 文件在**查询编辑器**中打开。 有四列：**创建日期、****用户Id、****操作**和**审核数据。** **审核数据**列是包含多个属性的 JSON 对象。 下一步是为 JSON 对象中的每个属性创建一个列。
    
5. 右键**单击"审核数据"** 列中的标题，**单击"转换"，****然后单击"JSON**"。 
 
   ![右键单击"审核数据"列，单击"转换"，然后选择"JSON"](media/JSONTransform.png)

6. **在"审核数据"** 列的右上角，单击展开图标。
    
   ![在"审核数据"列中，单击展开图标](media/JSONTransformExpandIcon.png)

   将显示**AuditData**列中 JSON 对象中属性的部分列表。

7. **单击"加载更多"** 以**在"审核数据"** 列中显示 JSON 对象中的所有属性。

   ![单击"加载更多"以显示 JSON 对象中的所有属性](media/JSONTransformLoadJSONProperties.png)

   您可以取消选中不想包含的任何属性旁边的复选框。 删除对调查没有用处的列是减少审核日志中显示的数据量的好方法。 

   > [!NOTE]
   > 上一个屏幕截图中显示的 JSON 属性（在**单击"加载更多"** 之后）基于在 CSV 文件中前 1，000 行中的**AuditData**列中找到的属性。 如果前 1，000 行之后记录中存在不同的 JSON 属性，则当**AuditData**列拆分为多列时，这些属性（和相应的列）将不会包括在内。 为了帮助防止这种情况，请考虑重新运行审核日志搜索并缩小搜索条件，以便返回更少的记录。 另一种解决方法是**筛选"操作"** 列中的项，以减少**在"审核数据"** 列中转换 JSON 对象之前（在执行上述步骤 5 之前）行数。

8. 执行以下操作之一，为所选的每个 JSON 属性添加的列的标题设置格式。

    - 取消选择"**使用原始列名称作为前缀"** 复选框，将 JSON 属性的名称用作列名称;例如，**记录类型**或**源文件名称**。
    
   - 保留选中"**使用原始列名称作为前缀"** 复选框，以将 AuditData 前缀添加到列名称中;例如，**审核数据.记录类型**或**审核数据.源文件名称**。

9. 按一下 [確定]****。
    
    "**审核数据"** 列被拆分为多列。 每个新列对应于 AuditData JSON 对象中的属性。 列中的每一行都包含属性的值。 如果属性不包含值，则显示*空*值。 在 Excel 中，具有 null 值的单元格为空。
  
10. 在"**主页"** 选项卡上，**单击"关闭&加载"** 以关闭电源查询编辑器，并在 Excel 工作簿中打开转换后的 CSV 文件。 

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a>导出和查看审核日志的提示

以下是在使用 JSON 转换功能将**AuditData**列拆分为多个列之前和之后导出和查看审核日志的一些提示和示例。

- 筛选"**记录类型"** 列以仅显示来自特定 Office 365 服务或功能区域的记录。 例如，要显示与 SharePoint 共享相关的事件，请选择**14（SharePoint**共享活动触发的记录的枚举值）。 有关与**RecordType**列中显示的枚举值对应的 Office 365 服务的列表，请参阅[Office 365 审核日志中的详细信息。](detailed-properties-in-the-office-365-audit-log.md)

- 筛选"**操作"** 列以显示特定活动的记录。 有关与安全&合规中心中的审核日志搜索工具中的可搜索活动对应的大多数操作的列表，请参阅[在"安全&合规中心"中搜索审核日志中的"](search-the-audit-log-in-security-and-compliance.md#audited-activities)已审核活动"部分。

- 您可以使用 Exchange 在线电源外壳中的[搜索统一审核日志](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog)cmdlet 将 Office 365 审核日志搜索的结果导出到 CSV 文件，而不是使用安全&合规性中心的审核日志搜索工具。 然后，您可以按照步骤 2 中描述的相同过程，使用 Power 查询编辑器格式化审核日志。 使用 PowerShell cmdlet 的一个优点是，您可以使用*RecordType*参数搜索特定 Office 365 服务中的事件。 下面是使用 PowerShell 将审核记录导出到 CSV 文件的几个示例，因此您可以使用 Power 查询编辑器转换**AuditData**列中的 JSON 对象，如步骤 2 中所述。

   在此示例中，运行以下命令以返回与 SharePoint 共享操作相关的所有记录。 
   
   ```
   $auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
   ```

   ```
   $auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
   ```

   - 搜索结果将导出到名为*PowerShellAuditlog*的 CSV 文件，该文件包含四列：创建日期、用户 Id、记录类型、审核数据）。

   - 可以使用记录类型的名称或枚举值作为*RecordType*参数的值。 有关记录类型名称及其相应的枚举值的列表，请参阅[Office 365 管理活动 API 架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)中的*AuditLogRecordType 类型*表。
   
   - 只能包含此参数的单个值。 要搜索其他记录类型的审核记录，必须再次运行前两个命令以指定不同的记录类型并将这些结果追加到原始 CSV 文件中。 例如，您将运行这两个命令，将同一日期范围内的 SharePoint 文件活动添加到 PowerShellAuditlog.csv 文件中。

       ```
      $auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
      ```

      ```
      $auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
      ```
