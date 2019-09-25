---
title: 在安全規範中心執行內容搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ComplianceSearch
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 61852fd9-fe8a-4880-a339-cb19ed3bff4a
description: '在"安全&合规性中心"中使用内容搜索来搜索邮箱、SharePoint 在线网站和一个业务位置的 OneDrive。 '
ms.openlocfilehash: cebdbf7808534b82085affa16c06ac1929b3fd8d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077583"
---
# <a name="run-a-content-search-in-the-security--compliance-center"></a>在安全規範中心執行內容搜尋

您可以使用安全&合规性中心中的内容搜索电子数据展示工具在 Office 365 组织中搜索电子邮件、文档和即时消息对话等项目。 使用此工具可以搜索这些 Office 365 服务中的项目：
  
- 交换联机邮箱和公用文件夹
    
- 适用于商业网站的共享点在线和 OneDrive
    
- 业务对话的 Skype
    
- Microsoft Teams 
    
- Office 365 群組
    
内容搜索是一种新的电子数据展示搜索工具，具有新的和改进的缩放和性能功能。 使用「內容搜尋」執行極大型的 eDiscovery 搜尋。 您可以在单个内容搜索中搜索所有邮箱、所有 Exchange 公用文件夹以及所有 SharePoint 联机网站和企业帐户的 OneDrive。 可以搜索的内容位置数量没有限制。 同時可以執行的搜尋數目也沒有限制。 运行内容搜索后，内容位置数和预计搜索结果数将显示在**内容搜索**页上的详细信息窗格中。 运行搜索后，您可以预览结果、获取一个或多个搜索的关键字统计信息、批量编辑内容搜索以及将结果导出到本地计算机。 
  
 **Contents**
  
[Create a search](run-a-content-search-in-the-security-and-compliance-center.md#create)
  
[匯出搜尋結果](run-a-content-search-in-the-security-and-compliance-center.md#export)
  
[Preview search results](run-a-content-search-in-the-security-and-compliance-center.md#preview)
  
[Update search results](run-a-content-search-in-the-security-and-compliance-center.md#restart)
  
[Edit a search](run-a-content-search-in-the-security-and-compliance-center.md#edit)
  
[Retry a search](run-a-content-search-in-the-security-and-compliance-center.md#retry)
  

  
## <a name="before-you-begin"></a>開始之前

- 有关生成搜索查询和使用布尔搜索运算符的信息和指南，请参阅[关键字查询和内容搜索搜索条件。](keyword-queries-and-search-conditions.md) 本文还包含有关搜索敏感信息类型和搜索与组织内外人员共享的内容的信息。
    
- 要访问**内容搜索**页以执行搜索、预览和导出搜索结果，管理员、合规官或电子数据展示经理必须是安全&合规中心中的电子数据展示经理角色组的成员。 您不必在 Exchange 联机、共享点联机或针对商业网站的 OneDrive 中分配其他搜索权限。 有关详细信息，请参阅在[Office 365 安全&合规性中心中分配电子数据展示权限](assign-ediscovery-permissions.md)。
    
- 对内容搜索应用了限制，以保持提供给 Office 365 组织的服务的运行状况和质量。 在大部分情況下，您無法修改這些限制，但您應注意這些限制以在進行規劃、執行和疑難排解搜尋時將這些限制納入考量。 有关详细信息，请参阅[安全&合规性中心中的搜索限制](limits-for-content-search.md)。
    
- 根据单个内容搜索中搜索的邮箱数，请参阅该部分，了解估计搜索时间。 
    
- 如前所述，您可以使用内容搜索在 Office 365 组和 Microsoft 团队中搜索内容。 这意味着您可以搜索与 Office 365 组和 Microsoft 团队关联的组邮箱、共享日历和 SharePoint 网站。 此外，您还可以在 Microsoft 团队中搜索频道对话。 有关 Office 365 组和 Microsoft 团队的信息，请参阅：
    
  - [了解 Office 365 组](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
    
  - [微软团队帮助](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
    有关在 Office 365 组和 Microsoft 团队中搜索内容的提示，请参阅部分。 
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="create-a-search"></a>Create a search
<a name="create"> </a>

1. 移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用公司或學校帳戶登入 Office 365。
    
3. 在"安全&合规性中心"的左侧窗格中，****\>单击"**搜索内容搜索"。**
    
4. **单击"新建"**![图标](media/O365-MDM-CreatePolicy-AddIcon.gif)。
    
5. 在 [新增搜尋]**** 頁面上，輸入內容搜尋的名稱。 此名稱在您的組織中必須是唯一的。 
    
6. 选择要搜索的内容位置。 您可以在同一搜索中搜索邮箱、网站和公用文件夹。
    
    ![选择要搜索的内容位置](media/da32e3f9-6cd6-4a26-8217-e97a5a7071e4.png)
  
1. **随处搜索**选择此选项可搜索组织中的所有内容位置。 选择此选项时，您可以选择搜索所有邮箱（包括非活动邮箱和所有 Office 365 组和 Microsoft 团队的邮箱）、所有 SharePoint 和一个业务站点的 OneDrive（包括所有 Office 365 组和微软团队），以及所有公用文件夹。
    
    ![单击"搜索所有位置"选项可搜索所有内容位置](media/86f132f1-0a2a-4048-900c-9f219d909ef2.png)
  
2. **自定义位置选择**选择此选项可选择要搜索的邮箱和网站。 如果选择此选项，则可以灵活地搜索特定服务的所有内容位置（如搜索所有 Exchange 邮箱），也可以搜索 Office 365 服务的特定内容位置。
    
    在添加要搜索的内容位置时，请记住以下事项：
    
    **信箱**
    
  - 当您**单击"添加**![图标"](media/ITPro-EAC-AddIcon.gif)以指定要搜索的邮箱时，显示的邮箱选取器为空。 這項設計的目的是提升效能。 要将收件人添加到此列表，请在搜索框中键入名称（至少 3 个字符），然后单击"**搜索**![搜索"图标](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)。
    
  - 您可以将非活动邮箱和通讯组添加到要搜索的邮箱列表中。 对于通讯组，将搜索组成员的邮箱。 请注意，不支持动态通讯组。
    
  - 要获取组织中非活动邮箱的列表，请运行 Exchange 联机 PowerShell`Get-Mailbox -InactiveMailboxOnly`中的命令。 或者，您可以转到安全&合规性中心**中的数据治理**\>**保留，****然后单击"更多**![导航](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)\>**栏"省略号非活动邮箱**。
    
  - 您还可以添加与 Office 365 组或 Microsoft 团队关联的邮箱。 在这种情况下，仅搜索组或团队邮箱;否则，将搜索组或团队邮箱。不搜索组或团队成员的邮箱。 要搜索它们，您必须专门将它们添加到搜索中。
    
  - 如果不想将任何邮箱包含在搜索中，请选择**选择要搜索的特定邮箱，** 但不要将邮箱添加到列表中。
    
    **網站**
    
  - **单击"添加**![图标"](media/ITPro-EAC-AddIcon.gif)将网站添加到搜索中。 键入要搜索的每个网站的 URL。 内容搜索工具将验证 URL，然后将其添加到要搜索的网站列表中。 
    
  - 您可以添加与 Office 365 组或 Microsoft 团队关联的 SharePoint。 有关如何查找组或团队的 URL 的指南，请参阅部分。 
    
  - 如果不想在搜索中包含任何网站，**请选择"选择要搜索的特定网站"，** 但不要将网站添加到列表中。
    
    **公用資料夾**
    
    对于公用文件夹，您可以选择搜索 Exchange Online 组织中的所有公用文件夹，也可以不搜索任何公用文件夹。
    
7. 按 [下一步]****。
    
8. 在 [新搜尋]**** 頁面上，您可以新增關鍵字和條件來建立搜尋查詢。 
    
    ![使用關鍵字和條件建立搜尋查詢](media/1b7cf7b5-f1e1-471a-ad5c-48aad8435b00.png)
  
1. 在 [您希望我們尋找什麼?]**** 下方的方塊，在方塊中輸入搜尋查詢。 您可以指定關鍵字、例如傳送和接收日期的郵件屬性，或者例如檔案名稱或文件上次變更的日期的文件屬性。 您可以使用使用布尔运算符的更复杂的**** 查询，例如**** AND、OR、NEAR 或**ONEAR** ****。 **** 您还可以在文档中搜索敏感信息（如社会保险号），或搜索外部共享的文档。 如果关键字框为空，则位于指定内容位置的所有内容都将包含在搜索结果中。 
    
2. 您可以**单击"显示关键字列表"** 复选框，并在每行中键入关键字。 如果这样做，则每行上的关键字由所创建的搜索查询中的**OR**运算符连接。 
    
    ![您可以在关键字列表中的行中键入关键字或关键字阶段](media/aea1a361-639d-4a82-8c3c-48645ef3fc05.png)
  
    为什么要使用关键字列表？ 您可以获取显示每个关键字匹配的项目数的统计信息。 这可以帮助您快速确定哪些关键字最有效（也是最不有效）。 您还可以在一行中使用关键字短语（用括号括起来）。 有关搜索统计信息的详细信息，请参阅[查看内容搜索结果的关键字统计信息。](view-keyword-statistics-for-content-search.md)
    
    有关使用关键字列表的指南，请参阅部分。 
    
3. **单击"检查错误拼写错误查询"** 以检查查询是否不支持的字符以及可能未大写布尔运算符的查询。 不支持的字符通常被隐藏，并且通常会导致搜索错误或返回意外的结果。 有关选中的不支持的字符的详细信息，请参阅[检查内容搜索查询是否存在错误。](check-your-content-search-query-for-errors.md)
    
4. **在"条件"** 下，向搜索查询添加条件以缩小搜索范围并返回更精细的结果集。 每個條件會將一個子句新增至 KQL 搜尋查詢，當您啟動搜尋時便會建立並執行。 條件會以 **AND** 運算子的邏輯方式連接至關鍵字查詢 (在關鍵字方塊中指定)。 這表示結果中包含的項目必須同時滿足關鍵字查詢與條件。 這就是條件如何協助您縮小搜尋結果。 
    
||
|:-----|
|有关创建搜索查询和使用条件的详细信息，请参阅[关键字查询和内容搜索的搜索条件。 ](keyword-queries-and-search-conditions.md) |
   
9. 按一下 [搜尋]**** 以儲存搜尋設定並開始搜尋。 
    
    已啟動搜尋。 搜索完成后，详细信息窗格中将显示以下信息。
    
    ![搜索统计信息显示在所选内容搜索的详细信息窗格中](media/2046bb5e-f4cb-4ba7-b7fc-8e5e53dae567.png)
  
1. 上次运行搜索的日期和时间。
    
2. 找到与搜索查询匹配的项目的数量（和总大小）。 项目类型的示例包括电子邮件、日历项目和文档。 如果项目包含正在搜索的关键字的多个实例，则仅在项目总数中计数一次。 例如，如果您搜索单词"股票"或"提示"，并且电子邮件包含单词"stock"的三个实例，则**在"项目"** 字段中只计算一次。 
    
3. 搜索的内容位置中未编制索引的项目的数量和总大小。 不符合搜尋準則的未建立索引的項目數會包含在詳細資料窗格中顯示的搜尋統計資料。 如果未编制索引的项目与搜索查询匹配（因为其他消息或文档属性满足搜索条件），则该项将不会包含在未编制索引的项目的估计数量中。 但是，如果搜索条件排除了未编制索引的项目，则该项将不会包含在未编制索引的项目的估计值中。
    
4. 搜索的每种内容位置类型的编号。 对于邮箱，请注意，存档邮箱包含在搜索的邮箱总数中。 在前面的示例中，搜索了四个用户邮箱，并启用了每个用户的存档邮箱。 这就是为什么搜索统计信息中引用了八个邮箱的原因。
    
5. 用于预览搜索结果或再次运行搜索以更新搜索统计信息的链接。
    
    如有必要，**单击"刷新**![刷新"](media/O365-MDM-Policy-RefreshIcon.gif)图标以更新所选搜索的详细信息窗格中的信息。 
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="export-search-results"></a>匯出搜尋結果
<a name="export"> </a>

成功运行搜索后，可以将搜索结果导出到本地计算机。 當您匯出電子郵件結果時，其會以 PST 檔案下載到您的電腦。 当您从 SharePoint 和 OneDrive 导出业务网站的内容时，将导出本机 Office 文档的副本。 匯出的搜尋結果中另外還有其他文件和報告。 有关详细信息，请参阅[从安全&合规性中心导出搜索结果。](export-search-results.md)
  
## <a name="preview-search-results"></a>預覽搜尋結果
<a name="preview"> </a>

成功完成搜尋之後，您可以預覽搜尋結果。 關於預覽內容搜尋結果有一些限制。 有关详细信息，请参阅[安全&合规性中心中的搜索限制](limits-for-content-search.md)。 请注意，未编制索引的项目无法预览。
  
1. 在"**内容"搜索**页上，选择搜索。 
    
2. 在詳細資料窗格中的 [結果]**** 底下，按一下 [預覽搜尋結果]****。[預覽搜尋結果]**** 頁面隨即開啟，並且包含搜尋結果項目的清單。 
    
    可以单击列标题，根据主题、类型、发件人或项目在源邮箱中收到日期对结果进行排序。
    
3. 单击要预览的项目。
    
    项目在预览窗格中打开。
    
4. 如果预览或下载文档副本不支持文件类型，则可以**单击"下载原始文件"** 将其下载到本地计算机。 对于 .aspx 网页，包含该页的 URL，尽管您可能没有访问该页面的权限。 
    
> [!NOTE]
> 如果您預覽 7 天之前所執行之搜尋的搜尋結果，系統會提示您更新搜尋結果。 重新运行搜索以获取满足搜索查询的最新版本。 
  
### <a name="file-types-that-can-be-previewed"></a>可预览的文件类型

您可以在预览窗格中预览支持的文件类型。 如果文件类型不受支持，您必须将文件的副本下载到本地计算机才能查看。 支持以下文件类型，**可在"预览搜索结果"** 页上预览。 
  
- .txt， .html， .mhtml
    
- .eml
    
- .doc， .docx， .docm
    
- .pptm， .pptx
    
- .pdf
    
此外，还支持以下文件容器类型。 您可以在预览窗格中查看容器中的文件列表。
  
- .zip
    
- .gzip
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="update-search-results"></a>更新搜尋結果
<a name="restart"> </a>

更新现有内容搜索的结果时，搜索查询将在所有指定内容位置重新运行。 更新搜索结果的明显原因是获取最新数据。
  
1. 在**內容搜尋**頁面上，選取您想要更新結果的搜尋。 
    
2. 在詳細資料窗格中的 [結果]**** 底下，按一下 [**更新搜尋結果**]。
    
    狀態訊息隨即顯示，表示正在擷取結果。 搜尋完成時，更新的資訊會顯示在詳細資料窗格中的 [結果]**** 底下。 請注意，在詳細資料窗格中的 [搜尋]**** 欄位的日期會更新為目前日期和時間。 要刷新内容搜索列表中的信息，请单击"**刷新**![刷新"图标](media/O365-MDM-Policy-RefreshIcon.gif)。
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="edit-a-search"></a>編輯搜尋
<a name="edit"> </a>

您可以更改现有内容搜索的源邮箱和搜索查询。
  
1. 在"**内容"搜索**页上，选择搜索。 
    
2. 在詳細資料窗格中的 [查詢]**** 底下，按一下 [編輯搜尋]****。
    
3. 在"**位置"** 页上，您可以更改要搜索的邮箱、组、SharePoint 网站或一个企业网站。 您也可以選取 (或取消選取) 來搜尋 Exchange 中的所有公用資料夾。 
    
4. 在"**查询"** 页上，您可以编辑搜索查询。 
    
5. 要开始修订的搜索，请单击"**来源"** 或"**位置"** 页上**的"搜索"。** 
    
    便會啟動修訂的搜尋。 搜尋完成時，修訂的搜尋的估計結果會顯示在詳細資料窗格中。
    
## <a name="retry-a-search"></a>重試搜尋
<a name="retry"> </a>

如果搜索返回任何错误，则不必重新搜索所有内容位置。 您可以重新运行搜索，以便只有失败的内容位置才能再次搜索。 要重新搜索所有内容位置，可以更新搜索结果。
  
1. 在"**内容"搜索**页上，选择包含要重新搜索的内容位置的搜索。 
    
2. 在詳細資料窗格中的 [錯誤]**** 底下，按一下 [重試搜尋]****。
    
    狀態訊息隨即顯示，表示正在擷取結果。 搜尋完成時，更新的資訊會顯示在詳細資料窗格中的 [結果]**** 底下。 請注意，在詳細資料窗格中的 [搜尋]**** 欄位的日期會更新為目前日期和時間。 要刷新搜索列表中的信息，请单击"**刷新**![刷新"图标](media/O365-MDM-Policy-RefreshIcon.gif)。
    
[回到頁首](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="more-information"></a>其他資訊
<a name="moreinfo"> </a>

以下是有关内容搜索的详细信息。
  
[限制和性能](#limits-and-performance)
  
[未编制索引的项目](#unindexed-items) 
 
[微软团队和 Office 365 组](#microsoft-teams-and-office-365-groups)
  
[商務用 OneDrive](#onedrive-for-business)
  
[搜索查询](#search-queries)
  
[搜索非活动邮箱](#searching-inactive-mailboxes)
  
[其他工作](#miscellaneous)
  
[回到頁首](#before-you-begin)
  
### <a name="limits-and-performance"></a>限制和性能
  
- 有关应用于内容搜索功能的限制的说明，请参阅[安全&合规性中心中的搜索限制](limits-for-content-search.md)。
    
- Microsoft 收集所有 Office 365 组织运行的内容搜索的性能信息。 虽然搜索查询的复杂性可能会影响搜索时间，但影响搜索时间的最大因素是搜索的邮箱数。 尽管 Microsoft 不提供搜索时间的服务级别协议，但下表根据搜索中包含的邮箱数列出内容搜索的平均搜索时间。
    
|**信箱數量**|**平均搜索时间**|
|:-----|:-----|
|100  <br/> |30 秒  <br/> |
|1,000  <br/> |45 秒  <br/> |
|10,000  <br/> |4分钟  <br/> |
|25,000  <br/> |10 分鐘  <br/> |
|50,000  <br/> |20 分鐘  <br/> |
|100,000  <br/> |25 分鐘  <br/> |
   
  
### <a name="unindexed-items"></a>未编制索引的项目
  
- 如前所述，在内容位置中搜索的未编制索引的项目将包含在估计搜索结果中。 如果未编制索引的项目与搜索查询匹配（因为其他消息或文档属性满足搜索条件），则该项将不会包含在未编制索引的项目的估计数量中。 如果搜索条件排除了未编制索引的项目，则该项也不会包含在未编制索引的项目的估计数量中。 有关详细信息，请参阅[内容搜索 中的未编制索引的项目。](https://go.microsoft.com/fwlink/p/?LinkId=780739)
    

  
### <a name="microsoft-teams-and-office-365-groups"></a>微软团队和 Office 365 组
  
- 微软团队基于 Office 365 组构建。 因此，搜索它们非常相似。 在 Microsoft 团队和 Office 365 组中搜索内容时，请记住以下事项。
    
  - 要搜索位于 Microsoft 团队和 Office 365 组中的内容，必须指定与团队或组关联的邮箱和 SharePoint 网站。
    
  - 在联机交换中运行**Get-Unified 组**cmdlet 以查看 Microsoft 团队或 Office 365 组的属性。 这是获取与团队或组关联的网站的 URL 的好方法。 例如，以下命令显示名为高级领导团队的 Office 365 组选定的属性： 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > 要运行**Get-UnifiedGroup** cmdlet，您必须在 Exchange 联机中分配仅查看收件人角色，或者成为分配了"仅查看收件人"角色的角色组的成员。 
  
  - 搜索用户的邮箱时，将不会搜索用户是其成员的任何 Microsoft 团队或 Office 365 组。 同样，当您搜索 Microsoft 团队或 Office 365 组时，仅搜索您指定的组邮箱和组网站;否则，将搜索您指定的组邮箱和组网站。除非将组成员的邮箱和 OneDrive 业务帐户显式添加到搜索中，否则不会搜索这些邮箱和 OneDrive。
    
  - 要获取 Microsoft 团队或 Office 365 组成员的列表，可以在 Microsoft 365**管理中心\>的"主页组"** 页上查看属性。 或者，您可以在 Exchange 在线电源外壳中运行以下命令： 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > 要运行**Get-UnifiedGroupLinks** cmdlet，您必须在 Exchange 联机中分配仅查看收件人角色，或者成为分配了"仅查看收件人"角色的角色组的成员。 
  
  - 属于 Microsoft Teams 频道的对话存储在与 Microsoft 团队关联的邮箱中。 同样，团队成员在通道中共享的文件存储在团队的 SharePoint 网站上。 因此，您必须添加 Microsoft Team 邮箱和 SharePoint 网站作为内容位置，以搜索通道中的对话和文件。
    
  - 
    
    或者，作为 Microsoft Teams 中聊天列表一部分的对话存储在参与聊天的用户的 Exchange 联机邮箱中。 用户在聊天对话中共享的文件存储在共享该文件的用户的 OneDrive 业务帐户中。 因此，您必须将单个用户邮箱和一个企业帐户的 OneDrive 添加为内容位置，以搜索聊天列表中的对话和文件。
    
    > [!NOTE]
    > 参与 Microsoft Teams 中"聊天"列表中的对话的用户必须具有联机交换（基于云的）邮箱，以便搜索聊天对话。 这是因为作为聊天列表一部分的对话存储在聊天参与者的基于云的邮箱中。 如果聊天参与者没有 Exchange Online 邮箱，您将无法搜索聊天对话。 例如，在 Exchange 混合部署中，具有本地邮箱的用户可能能够参与 Microsoft Teams 中"聊天"列表的一部分的对话。 但是，在这种情况下，这些对话中的内容不可搜索，因为用户没有基于云的邮箱。 
  
  - 每个 Microsoft 团队或团队渠道都包含一个用于记笔记和协作的 Wiki。 Wiki 内容会自动保存到具有 .mht 格式的文件。 此文件存储在团队 SharePoint 网站上的团队 Wiki 数据文档库中。 您可以通过将团队的 SharePoint 网站指定为要搜索的内容位置来使用内容搜索工具搜索 Wiki。 
    
    > [!NOTE]
    > 2017 年 6 月 22 日发布了在 Wiki 中搜索 Microsoft 团队或渠道的功能（当您搜索团队的 SharePoint 网站时）。 可搜索在该日期或之后保存或更新的 Wiki 页面。 上次保存或更新的 Wiki 页面在此日期之前无法搜索。 
  
### <a name="onedrive-for-business"></a>商務用 OneDrive
  
- 要收集组织中一个企业站点的一个业务站点的 URL 列表，请参阅[创建组织中所有 OneDrive 位置的列表。](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a) 本文中的脚本创建一个文本文件，其中包含所有适用于业务站点的 OneDrive 的列表。 要运行此脚本，您必须安装和使用 SharePoint 联机管理命令行程序。 请务必将组织的 MySite 域的 URL 追加到要搜索的每个一个企业网站。 这是包含所有 OneDrive 业务域的域;例如， `https://contoso-my.sharepoint.com`. 下面是用户 OneDrive 商业网站 URL 的示例： `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。
    

### <a name="search-queries"></a>搜索查询
  
- 使用关键字列表创建搜索查询时，请记住以下事项。
    
  - 您必须**选择"显示关键字列表"** 复选框，然后在单独的行中键入每个关键字，以创建搜索查询，其中每行中的关键字（或关键字短语）由**OR**运算符连接。 如果您只是在关键字框中粘贴关键字列表，或在键入关键字后按**Enter**键，则**OR**运算符不会连接这些关键字。 下面是添加关键字列表的错误和正确示例。 
    
    **错误**
    
    ![设置关键字列表格式的错误方法（通过将列表粘贴到关键字框中）](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **正确**
    
    ![设置关键字列表格式的正确方法（通过选中复选框然后粘贴列表）](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
  - 您还可以在 Excel 文件或纯文本文件中准备关键字或关键字短语的列表，然后将列表复制并粘贴到关键字列表中。 为此，您必须**选择"显示关键字列表"** 复选框。 然后，单击关键字列表中的第一行并粘贴列表。 Excel 或文本文件中的每行都将粘贴到关键字列表中的单独行中。 
    
  - 使用 关键字列表创建查询后，最好验证搜索查询语法（在所选搜索的详细信息窗格中），以使搜索查询达到预期目标。 在详细信息窗格中"**查询"** 下显示的搜索查询中，关键字由文本 **（c：s）** 分隔。 这表示关键字由**OR**运算符连接。 同样，如果您的搜索查询包含条件，关键字和条件由文本 **（c：c）** 分隔。 这表示关键字已通过**AND**运算符连接到条件。 下面是使用关键字列表和条件时产生的搜索查询（显示在"详细信息"窗格中）的示例。 
    
    ![使用关键字列表和条件时创建的查询示例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
  - 如果您的搜索查询包含非英语字符（如中文字符）的关键字，则可能必须**使用"设置合规性搜索**cmdlet"来配置内容搜索的语言属性。 当您在安全&合规性中心中使用 GUI 创建内容搜索时，默认语言为中性语言。 
    
    如何判断是否需要更改内容搜索的语言设置？ 如果您的某些内容位置包含您要搜索的非英语字符，但搜索不返回任何结果，则语言设置可能是原因。
    
    要更改现有内容搜索的语言设置，在"安全&合规性中心 PowerShell 中运行以下命令：
    
  ```
  Set-ComplianceSearch <name of content search> -Language <culture code value>
  ```

    例如，要将语言设置更改为中文，可以使用`zh-CN`区域性代码值。 更改语言设置后，必须重新运行搜索。 有关可能区域性代码值的列表，请参阅[文化信息类](https://go.microsoft.com/fwlink/p/?LinkID=184859)。 对于内容搜索，我们建议您使用两部分区域性代码来表示语言设置的值;对于语言设置，请使用两部分区域性代码。例如，`ja-JP`而不是`ja`。
    

### <a name="searching-inactive-mailboxes"></a>搜索非活动邮箱
  
如前所述，您可以在内容搜索中搜索非活动邮箱。 在搜索非活动邮箱时，需要记住一些事项。
  
- 如果内容搜索包含用户邮箱，然后该邮箱处于非活动状态，则当您在非活动后重新运行搜索时，内容搜索将继续搜索该非活动邮箱。
    
- 在某些情况下，用户可能具有活动邮箱和非活动邮箱具有相同的 SMTP 地址。 在这种情况下，将仅搜索您选择作为内容搜索位置的特定邮箱。 换句话说，如果将用户的邮箱添加到搜索中，则不能假定将搜索其活动邮箱和非活动邮箱;如果将用户的邮箱添加到搜索中，则不能假定用户邮箱的邮箱和非活动邮箱都将被搜索。只会搜索您显式添加到搜索中的邮箱。
    
- 我们强烈建议您避免使用具有相同 SMTP 地址的活动邮箱和非活动邮箱。 如果需要重用当前分配给非活动邮箱的 SMTP 地址，我们建议您恢复非活动邮箱或将非活动邮箱的内容还原到活动邮箱（或活动邮箱的存档），然后删除非活动邮箱。 有关详细信息，请参阅以下主题之一：
    
  - [在 Office 365 中恢复非活动邮箱](recover-an-inactive-mailbox.md)
    
  - [在 Office 365 中还原非活动邮箱](restore-an-inactive-mailbox.md)
    
  - [删除 Office 365 中的非活动邮箱](delete-an-inactive-mailbox.md)
    
### <a name="miscellaneous"></a>雜項
  
- 在"安全&合规**中心"的内容搜索**页面上创建的内容搜索不会显示在 Exchange 管理中心的**就地电子数据展示&amp;保留**页上。 这是因为内容搜索体系结构和在安全&合规性中心创建的搜索对象与 Exchange 在线中的就地电子数据展示功能完全不同。 
    
    出于同样的原因，在**内容搜索**页上创建的搜索不会显示在安全&合规中心电子数据展示案例**的"搜索"** 页上。 
    
- 重新啟動與重試搜尋之間有何差異？ 重新启动搜索时，将在新的预览搜索中再次搜索搜索中指定的所有内容位置。 但是，当您重试搜索时，只会再次搜索上次运行搜索时失败的内容位置。
   

