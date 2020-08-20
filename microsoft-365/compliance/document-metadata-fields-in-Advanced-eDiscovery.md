---
title: 在高級 eDiscovery 中記錄元資料欄位
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
description: 本文針對 Microsoft 365 的「高級 eDiscovery」中的案例，定義了審查集內檔的元資料欄位。
ms.openlocfilehash: 69b22155f209f155aa0b311f67f3e69841093003
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814385"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>在高級 eDiscovery 中記錄元資料欄位

下表列出在 [高級 eDiscovery] 中的審閱集中的檔的元資料欄位。 表格提供下列資訊：

- **功能變數名稱和****顯示功能變數名稱：** [中繼資料] 欄位的名稱，以及在審閱集中查看選取檔的檔案中繼資料時所顯示的功能變數名稱。 在查看檔的檔案中繼資料時，不會包含某些元資料欄位。 這些欄位會反白顯示星號 ( * ) 。

- 可搜尋的**功能變數名稱：** 執行[審閱集查詢](review-set-search.md)時可搜尋的屬性名稱。 空白儲存格表示您無法在「審閱集」查詢中搜尋該欄位。

- **匯出的功能變數名稱：** 匯出檔時包含的元資料欄位名稱。  空白儲存格表示欄位不會包含在匯出的中繼資料中。

- **描述：** 元資料欄位的描述。

> [!NOTE]
> 「[複查設定搜尋](https://docs.microsoft.com/microsoft-365/compliance/review-set-search)使用關鍵字查詢語言 (KQL) 中的**關鍵字**] 欄位。 「可搜尋 **欄位名稱** 」欄中所列的欄位可用於審閱集搜尋中的 [ **關鍵字** ] 欄位，以形成複雜的查詢，而不需要使用「查詢建立器」。 如需 KQL 的詳細資訊，請參閱 [關鍵字查詢語言語法參考](https://go.microsoft.com/fwlink/?LinkId=269603)。

|**功能變數名稱和****顯示欄位名稱**|**可搜尋的功能變數名稱**|**匯出的功能變數名稱**|**描述**|
|:-----|:-----|:-----|:-----|
|附件內容識別碼|AttachmentContentId||專案的附件內容識別碼。|
|附件名稱|AttachmentNames|Attachment_Names|附件的名稱清單。|
|律師用戶端許可權分數|AttorneyClientPrivilegeScore||律師-用戶端許可權模型內容分數。|
|作者|作者|Doc_authors|從檔中繼資料製作作者。|
|密件副本|密件副本|Email_bcc|郵件類型的 [密件副本] 欄位。 Format 為**DisplayName \<SMTPAddress> **。|
|副本|副本|Email_cc|郵件類型的 [副本] 欄位。 Format 為**DisplayName \<SMTPAddress> **。|
|符合性標籤|ComplianceLabels|Compliance_labels|套用至 Office 365 內容的[保留標籤](retention.md)。|
|複合路徑|CompoundPath|Compound_path|描述專案來源的人可讀取路徑。|
|內容|內容||專案的解壓縮文字。|
|交談主體|交談主體||專案的交談主體。|
|交談主題|交談主題||專案的交談主題。|
|交談識別碼|ConversationId|Conversation_ID|郵件中的交談識別碼。|
|交談索引||Conversation_index|郵件中的交談索引。|
|交談 Pdf 時間|ConversationPdfTime||建立交談的 PDF 版本的日期。|
|交談密文燒錄時間|ConversationRedactionBurnTime||為聊天建立交談的 PDF 版本的日期。|
|檔建立日期|CreatedTime|Doc_date_created|從檔中繼資料建立日期。|
|監管人|監管人|監管人|與專案相關聯之保管人的名稱。|
|日期|日期|日期|Date 是取決於檔案類型的計算欄位。<br /><br />電子郵件：傳送日期<br />電子郵件附件：檔的上次修改日期; 如果無法使用，則為父項的傳送日期<br />內嵌檔：檔的上次修改日期;如果無法使用，則為父項的上次修改日期<br />SPO 檔 (包含新式附件) ： SharePoint 的上次修改日期;如果無法使用，檔會以上次修改日期<br />非 Office 365 檔：上次修改日期<br />會議：會議開始日期<br />VoiceMail：傳送日期<br />IM：傳送日期|
|其他路徑|Dedupedcompoundpath|Deduped_compound_path|完全重複的檔複合路徑清單 (電子郵件：根據內容，檔：根據雜湊) 。|
|其他保管人|DedupedCustodians|Deduped_custodians|根據內容，對電子郵件 (完全重複的檔的保管人清單;針對檔，根據雜湊) 。|
|其他檔案 IDs|DedupedFileIds|Deduped_file_IDs|根據內容，對電子郵件而言 IDs 完全重複 (檔的檔案清單;針對檔，根據雜湊) 。|
|檔批註|DocComments|Doc_comments|檔中繼資料中的批註。|
|檔公司||Doc_company|檔中繼資料中的公司。|
|DocIndex*|||系列中的索引。 **-1** 或 **0** 表示它是根項目。|
|檔關鍵字||Doc_keywords|檔中繼資料中的關鍵字。|
|修改的檔||Doc_modified_by|自檔中繼資料的上次修改日期。|
|檔修訂||Doc_revision|檔中繼資料中的修訂。|
|檔主題||Doc_subject|使用檔中繼資料的主旨。|
|文件範本||Doc_template|檔中繼資料中的範本。|
|主要主題|DominantTheme|Dominant_theme|針對分析進行計算的主要主題。|
|重複子集||Duplicate_subset|完全重複的群組識別碼。|
|EmailAction*||Email_action|值為 **無**、 **回復**或 **轉寄**;根據郵件的主旨行。|
|電子郵件送達回執||Email_delivery_receipt|Internet 標頭中提供的傳遞回執的電子郵件地址。|
|Importance|EmailImportance|Email_importance|郵件的重要性： **0** -低; **1** -Normal; **2** -高|
|EmailLevel*||Email_level|會指出郵件在其所屬的電子郵件執行緒中的層級;附件繼承其上層郵件的值。|
|電子郵件訊息識別碼||Email_message_ID|郵件中的網際網路郵件識別碼。|
|EmailReadReceipt*||Email_read_receipt|Internet 標頭中提供的電子郵件地址，供讀取接收。|
|電子郵件安全性|EmailSecurity|Email_security|郵件的安全性設定： **0** -無; **1** -已簽署; **2** -已加密; **3** -加密及簽署。|
|電子郵件敏感度|EmailSensitivity|email_sensitivity|郵件的敏感度設定： **0** -無; **1** 個人; **2** -私人; **3** -CompanyConfidential。|
|電子郵件集|EmailSet|Email_set|相同電子郵件集中所有郵件的群組識別碼。|
|EmailThread*||Email_thread|郵件在電子郵件集中的位置;會包含從根目錄 IDs 到目前的郵件，並以句點 ( ) 分隔的節點。。|
|已解壓縮內容類型||Extracted_content_type|已解壓縮內容類型，格式為 mime 類型;例如， **image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|解壓縮文字中的字元數。|
|系列相關性分數案例問題 1 *||Family_relevance_score_case_issue_1|與相關性的系列相關性分數案例問題1。|
|FamilyDuplicateSet*||Family_duplicate_set|每個其他 (相同內容和所有相同附件) 的不同的系列的數值識別碼。|
|系列識別碼|FamilyId|Family_ID|系列 Id 群組所有專案;電子郵件，這包括郵件和所有附件;對於檔，這包含檔和任何內嵌專案。|
|系列大小||Family_size|系列中的檔數目。|
|檔相關性分數案例問題 1 *||File_relevance_score_case_issue_1|從相關性的檔案相關性分數案例問題1。|
|檔類別|FileClass|File_class|SharePoint 與 OneDrive 的內容： **檔**;若為 Exchange 的內容： **電子郵件** 或 **附件**。|
|檔識別碼|FileId|File_ID|在案例內唯一的檔識別碼。|
|已建立檔案系統日期||File_system_date_created|從檔案系統建立日期 (僅適用于非 Office 365 資料) 。|
|修改檔案系統日期||File_system_date_modified|從檔案系統修改的日期 (只適用于非 Office 365 資料) 。|
|檔案類型|FileType||以副檔名為基礎之專案的檔案類型。|
|群組識別碼| GroupID|  |群組內容的群組識別碼。|
|具有附件|HasAttachment|Email_has_attachment|會指出郵件是否有附件。|
|擁有律師|HasAttorney||當在律師清單中至少找到一個參與者時，**為 True** ，否則為 True。否則，此值為**False**。|
|HasText *||Has_text|會指出專案是否有文字;可能的值為 **True** 和 **False**。|
|不彈性識別碼||Immutable_ID|這個識別碼可用來唯一識別審閱集內的檔。 此欄位無法用於複查集搜尋中，且無法使用識別碼來存取原生位置中的檔。|
|包含類型|InclusiveType|Inclusive_type|針對分析計算的非獨佔類型： **0** -無包含; **1** -包含; **2** 個包含減去; **3** 個包含的副本。|
|回復識別碼中||In_reply_to_ID|從郵件回復識別碼。|
|是新式附件| IsModernAttachment|  |這個檔案是現代的附件或連結的檔案。|
|來自檔版本 | IsFromDocumentVersion |  |目前的檔來自其他版本的另一個檔。|
|電子郵件附件 | IsEmailAttachment|  |此專案是從顯示為郵件附加專案的電子郵件附件。|
|內嵌附件| IsInlineAttachment|  |這是內嵌的，並顯示在郵件的本文中。|
|代表|IsRepresentative|Is_representative|每一組確切的重複專案中的一個檔會標示為代表。|
|專案類別|ItemClass|Item_class|Exchange server 所提供的專案類別;例如， **IPM。記事**|
|上次修改日期|LastModifiedDate|Doc_date_modified|檔中繼資料的上次修改日期。|
|載入識別碼|LoadId|Load_ID|專案已新增至審閱集的載入集識別碼。|
|位置|位置|位置|指出檔來源的位置類型的字串。<br /><br />匯**入的資料**-非 Office 365 資料<br />**團隊** -Microsoft 團隊<br />**Exchange** -exchange 信箱<br />**SharePoint** SharePoint 網站<br />**OneDrive** OneDrive 帳戶|
|位置名稱|LocationName|Location_name|識別專案來源的字串。 若為 exchange，這將是信箱的 SMTP 位址。針對 SharePoint 和 OneDrive，為網站集合的 URL。|
|標示為代表|MarkAsRepresentative||每一組確切的重複專案的一個檔會標示為代表。|
|標示為前置標記案例問題 1 *||Marked_as_pre_tagged_Case_issue_1|標示為相關性的預先標記案例問題1。|
|標示為植入案例問題 1 *||Marked_as_seed_Case_issue_1|標示為來源相關的種子案例問題1。|
|會議結束日期|MeetingEndDate|Meeting_end_date|會議的會議結束日期。|
|會議開始日期|MeetingStartDate|Meeting_start_date|會議的會議開始日期。|
|郵件類型|MessageKind|Message_kind|要搜尋的郵件類型。 可能的值：連絡人檔： ** <br /> <br /> <br /> <br /> 電子郵件 <br /> externaldata <br /> 傳真 <br /> im 記錄 <br /> <br /> 會議 <br /> microsoftteams** (會傳回來自交談、會議和 Microsoft 團隊通話的專案) ** <br /> 記事 <br /> 文章 <br /> rssfeeds 工作 <br /> <br /> 語音信箱**| 
|原生分機|NativeExtension|Native_extension|專案的原生分機。|
|原生檔案名|NativeFileName|Native_file_name|專案的原生檔案名。|
|NativeMD5||Native_MD5|) 檔資料流程的 MD5 雜湊 (128 位雜湊值。|
|NativeSHA256||Native_SHA_256|) 檔資料流程的 SHA256 雜湊 (256 位雜湊值。|
|ND/ET 排序：排除附件|NdEtSortExclAttach|ND_ET_sort_excl_attach|電子郵件執行緒的串聯 (ET) set 和 Near-重複 (ND) set。 此欄位可用於審閱時間的有效排序。 A **D** 的首碼為 ND 集，而 **E** 的首碼為 ET 集。|
|ND/ET 排序：包括附件|NdEtSortInclAttach|ND_ET_sort_incl_attach|電子郵件執行緒的串聯 (ET) set 和 near-重複 (ND) set。 此欄位可用於審閱時間的有效排序。 A **D** 的首碼為 ND 集，而 **E** 的首碼為 ET 集。 ET 集內的每一個電子郵件專案後面都會加上其適當的附件。|
|標準化相關性分數案例問題1||Normalized_relevance_score_case_issue_1|從相關性的標準化相關性分數案例問題1。|
|O365 作者||O365_authors|SharePoint 中的作者。|
|O365 建立者||O365_created_by|從 SharePoint 建立。|
|O365 建立日期||O365_date_created|從 SharePoint 建立日期。|
|O365 修改日期||O365_date_modified|從 SharePoint 的上次修改日期。|
|O365 修改者||O365_modified_by|從 SharePoint 修改。|
|父識別碼|ParentId|Parent_ID|專案的父代識別碼。|
|ParentNode||Parent_node|電子郵件線索中的最近一封電子郵件。|
|父項路徑|ParentPath|Parent_path|專案之直屬父級的複合路徑。|
|參與者網域|ParticipantDomains|Email_participant_domains|郵件參與者的所有網域清單。|
|參與者|參與者|Email_participants|郵件的所有參與者清單;例如，寄件者、收件者、抄送、Bcc。|
|樞紐分析表識別碼|PivotId|Pivot_ID|Pivot 的識別碼。|
|可能的許可權|PotentiallyPrivileged|Potentially_privileged|True 是表示如果律師-用戶端許可權偵測模型認為檔可能具有特權|
|處理狀態|ProcessingStatus|Error_code|專案新增至審閱集之後的處理狀態。|
|已讀% 案例問題1||Read_percent_Case_issue_1|從相關性中讀取問題1的案例。|
|讀取百分位數|ReadPercentile||根據相關性，針對檔讀取百分點。|
|收件者計數||Recipient_count|郵件中的收件者數目。|
|收件者網域|RecipientDomains|Email_recipient_domains|郵件收件者的所有網域清單。|
|收件者|收件者|Email_recipients|郵件的所有收件者清單 (收件者、抄送、Bcc) 。|
|相關性載入群組案例問題1||Relevance_load_group_case_issue_1|相關性載入群組的情況問題1。|
|關聯狀態原因案例問題1||Relevance_status_description_Case_issue_1|相關性狀態原因與相關性的問題1。|
|相關性標記案例問題1||Relevance_tag_case_issue_1|相關性標記案例相關性的問題1。|
|關聯性批註||Relevance_comment|相關性的批註欄位。|
|相關性分數|RelevanceScore||以相關性為基礎的檔相關性分數。|
|相關性標記|RelevanceTag||以相關性為基礎的檔相關性分數。|
|代表識別碼|RepresentativeId||每一組確切重複專案的數值識別碼。|
|寄件者|寄件者|Email_sender|寄件者 (來自郵件類型) 欄位。 Format 為**DisplayName \<SmtpAddress> **。|
|寄件者/作者|SenderAuthor||由專案的寄件者或作者所組成的計算欄位。|
|寄件者網域|SenderDomain|Email_sender_domain|寄件者的網域。|
|寄件日期|寄件日期|Email_date_sent|郵件的傳送日期。|
|設定訂單：先包含|SetOrderInclusivesFirst|Set_order_inclusives_first|排序欄位-電子郵件和附件：計數器-按時間順序;檔：先進行資料透視，再按降冪的相似性分數。|
|SimilarityPercent||Similarity_percent|會指出檔與接近的重複集的 pivot 的類似程度。|
|原生檔案大小|大小|Native_size|原生專案的位元組數。|
|主旨|主旨|Email_subject|郵件的主旨。|
|主旨/職稱|SubjectTitle||由專案主旨或標題組成的計算欄位。|
|標記案例問題1||Tagged_by_Case_issue_1|為相關問題1標記此檔的使用者。|
|標記|標記|標記|套用於審閱集中的標記。|
|主題清單|ThemesList|Themes_list|針對分析所計算的主題清單。|
|職稱|職稱|Doc_title|檔中繼資料中的標題。|
|收件者|收件者|Email_to|郵件類型的 [至] 欄位。 Format 為**DisplayName \<SmtpAddress> **|
|電子郵件集中的唯一|UniqueInEmailSet||**False** 表示電子郵件組中的附件重複。|
|已修正|WasRemediated|Was_Remediated|**True** 是表示如果專案已修正，否則 **為 False**。|
|字數統計|WordCount|Word_count|專案中的字數。|
|||||

> [!NOTE]
> 如需在您為高級 eDiscovery 案例收集資料時搜尋 Office 365 內容位置時，可搜尋屬性的詳細資訊，請參閱 [內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。
