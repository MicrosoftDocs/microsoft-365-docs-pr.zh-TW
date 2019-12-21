---
title: 在進階電子文件中的文件的中繼資料欄位
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
description: 本文中的 Microsoft 365 進階 ediscovery 案例中設定檢閱定義文件的中繼資料欄位。
ms.openlocfilehash: 7a5a767d22c6f3a5251a11bd201846135cfcf130
ms.sourcegitcommit: ca4ce9e8c7e4b433608cd059857740ffd5a472c2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2019
ms.locfileid: "40840152"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>在進階電子文件中的文件的中繼資料欄位

下表列出在進階電子文件探索中設定案例中檢閱文件的中繼資料欄位。 表格會提供下列資訊：

- **欄位名稱**和**顯示欄位名稱：** 中繼資料欄位和檢視檔案中繼資料的選取文件中檢閱設定時，會顯示的欄位名稱的名稱。 請注意，有些中繼資料欄位時，不會包含檢視的文件的檔案中繼資料。 這些欄位會醒目提示加有星號 （*）。

- **可搜尋的欄位名稱：** 您可以執行[檢閱設定查詢](review-set-search.md)時搜尋的屬性的名稱。 空白儲存格表示您無法搜尋的檢閱設定查詢中的欄位。

-  **匯出欄位名稱：** 包含時都要匯出的文件的中繼資料欄位的名稱。  空白儲存格表示的欄位並不包含在匯出的中繼資料。

- **描述：** 中繼資料欄位的描述。

|**欄位名稱**和**顯示欄位名稱**|**可搜尋的欄位名稱**|**匯出的欄位名稱**|**描述**|
|:-----|:-----|:-----|:-----|
|附件內容識別碼|AttachmentContentId||附件的內容識別碼的項目。|
|附件名稱|AttachmentNames|Attachment_Names|附件的名稱清單。|
|Attorney-client 用戶端權限分數|AttorneyClientPrivilegeScore||設定律師-委託人權限模型內容分數。|
|作者|作者|Doc_authors|從文件中繼資料的作者。|
|密件副本|密件副本|Email_bcc|郵件類型的 [密件副本] 欄位。 格式為**DisplayName \<SMTPAddress>**。|
|副本|副本|Email_cc|郵件類型的 [副本] 欄位。 格式為**DisplayName \<SMTPAddress>**。|
|合規性標籤|ComplianceLabels|Compliance_labels|[保留標籤](labels.md)套用至 Office 365 中的內容。|
|複合路徑|CompoundPath|Compound_path|描述項目的來源的人力可讀取路徑。|
|內容 *|內容||擷取的項目的文字。|
|交談內文|交談內文||交談項目的本文。|
|交談主旨|交談主旨||交談主旨的項目。|
|交談識別碼|ConversationId|Conversation_ID|從郵件的交談 Id。|
|交談的索引||Conversation_index|從郵件的交談索引。|
|交談 Pdf 時間|ConversationPdfTime||PDF 版本交談的建立日期。|
|交談 Redaction 燒錄時間|ConversationRedactionBurnTime||PDF 版本的交談建立聊天室的日期。|
|建立的文件日期|CreatedTime|Doc_date_created|從文件中繼資料建立日期。|
|監管人|監管人|監管人|Custodian 項目名稱已與相關聯。|
|日期|日期|日期|日期是取決於該檔案類型的計算的欄位。<br /><br />傳送日期的電子郵件：<br />電子郵件附件： 上次修改日期的文件; 如果無法使用，父項的傳送日期<br />內嵌文件： 上次修改日期的文件;若未提供，父項的上次修改日期<br />SPO 文件 （包含最新附件）： SharePoint 上次修改日期;如果沒有可用的文件上次修改日期<br />非 Office 365 文件： 上次修改日期<br />會議： 會議開始日期<br />語音信箱： 傳送日期<br />IM： 傳送日期|
|其他路徑|Dedupedcompoundpath|Deduped_compound_path|複合完全重複的文件的路徑清單 (電子郵件： 根據文件的內容： 根據雜湊)。|
|其他 custodians|DedupedCustodians|Deduped_custodians|Custodians 文件索引 （適用於電子郵件，基礎內容; 為基礎的文件，雜湊） 完全重複的清單。|
|其他檔案識別碼|DedupedFileIds|Deduped_file_IDs|文件索引 （適用於電子郵件，基礎內容; 為基礎的文件，雜湊） 完全重複的檔案識別碼的清單。|
|文件的註解|DocComments|Doc_comments|文件中繼資料的註解。|
|文件公司||Doc_company|從文件中繼資料的公司。|
|DocIndex *|||系列中的索引。 **-1**或**0**就是根。|
|文件的關鍵字||Doc_keywords|從文件中繼資料的關鍵字。|
|修改過的文件||Doc_modified_by|上次修改的日期藉由從文件中繼資料。|
|文件修訂||Doc_revision|文件中繼資料從修訂。|
|文件主旨||Doc_subject|主旨中的文件中繼資料。|
|文件範本||Doc_template|文件中繼資料中的範本。|
|主控項的佈景主題|DominantTheme|Dominant_theme|主控項主題做為分析計算。|
|重複的子集||Duplicate_subset|完全重複群組識別碼。|
|EmailAction *||Email_action|值為**None**、**回覆**或**轉寄**;根據郵件的主旨行。|
|電子郵件送達回條||Email_delivery_receipt|在 [網際網路標頭中提供給送達回條的電子郵件地址。|
|Importance|EmailImportance|Email_importance|郵件重要性： **0** -低;**1** -正常;**2** -高|
|EmailLevel *||Email_level|會指出它屬於; 在電子郵件執行緒內的郵件層級附件繼承其父訊息的值。|
|電子郵件訊息識別碼||Email_message_ID|郵件從網際網路郵件識別碼。|
|EmailReadReceipt *||Email_read_receipt|在 [網際網路標頭中提供給讀信回條的電子郵件地址。|
|電子郵件安全性|EmailSecurity|Email_security|郵件的安全性設定： **0** -無]。**1** -簽署;**2** -加密;**3** -加密和簽署。|
|電子郵件的敏感度|EmailSensitivity|email_sensitivity|郵件的敏感度設定： **0** -無]。**1**個人;**2** -私人;**3** -CompanyConfidential。|
|電子郵件設定|EmailSet|Email_set|設定相同的電子郵件中的所有郵件的群組識別碼。|
|EmailThread *||Email_thread|集內的電子郵件訊息中的位置;包含的節點識別碼根目錄從目前的訊息;以句點分隔。|
|擷取內容類型||Extracted_content_type|Mime 類型; 的表單中擷取的內容類型例如， **image/jpeg**|
|ExtractedTextLength *||Extracted_text_length|中擷取文字的字元數。|
|家庭相關性分數案例問題 1 *||Family_relevance_score_case_issue_1|家庭相關性分數案例從相關性發行 1。|
|FamilyDuplicateSet *||Family_duplicate_set|另一部 （相同的內容和相同的所有附件） 完全重複的家庭成員的數值識別碼。|
|家庭識別碼|Id|Family_ID|家庭識別碼分組的所有項目;電子郵件，這包括郵件，並將所有附件。對於文件，包括文件和任何內嵌的項目。|
|家庭大小||Family_size|系列中的文件數。|
|檔案相關性分數案例問題 1 *||File_relevance_score_case_issue_1|檔案相關性分數案例問題 1 相關性。|
|檔案類別|FileClass|File_class|來自 SharePoint 和 OneDrive 的內容：**文件**;從 Exchange 內容：**電子郵件**或**附件**。|
|檔案識別碼|FileId|File_ID|文件內案例的唯一識別碼。|
|建立的檔案系統日期||File_system_date_created|從檔案系統中建立日期 （僅適用於非 Office 365 資料）。|
|修改的檔案系統日期||File_system_date_modified|修改日期從檔案系統 （僅適用於非 Office 365 資料）。|
|檔案類型|FileType||根據檔案副檔名項目的檔案類型。|
|具有附件|HasAttachment|Email_has_attachment|會指出郵件具有附件。|
|具有律師|HasAttorney||**，則為 true**時，至少下列其中一個參與者是清單中找到律師;否則，此值為**False**。|
|HasText *||Has_text|指出項目含有文字;可能的值為**True**及**False**。|
|固定 ID|ImmutableId|Immutable_ID|為 Office 365 中儲存的固定識別碼。|
|內含類型|InclusiveType|Inclusive_type|針對分析計算 （含） 的類型： **0** -不含;**1** -（含);**2** -內含減;**3** -（含） 的複本。|
|In Reply To 識別碼||In_reply_to_ID|In reply to 從郵件的識別碼。|
|為代表性|IsRepresentative|Is_representative|每一組圖形完全重複的項目中的一份文件會標示為具有代表性。|
|項目類別|ItemClass|Item_class|由 exchange 伺服器; 所提供的項目類別例如， **IPM。附註**|
|上次修改的日期|LastModifiedDate|Doc_date_modified|從文件中繼資料的上次修改的日期。|
|負載識別碼|LoadId|Load_ID|在中新增項目設定負載的識別碼來檢閱設定。|
|位置|位置|位置|字串，表示文件所源自的位置的類型。<br /><br />**匯入資料**的非 Office 365 資料<br />**Teams** -Microsoft Teams<br />**Exchange** -Exchange 信箱<br />**SharePoint** -SharePoint 網站<br />**OneDrive** OneDrive 帳戶|
|位置名稱|LocationName|Location_name|識別項目的來源的字串。 對於 exchange，這是信箱; 的 SMTP 位址SharePoint 和 OneDrive 網站集合的 URL。|
|標示為代表性|MarkAsRepresentative||從完全重複的每一組一份文件會標示為代表。|
|標示為預先標記案例問題 1 *||Marked_as_pre_tagged_Case_issue_1|標示為預先標記的情況下從相關性發行 1。|
|標示為植入案例問題 1 *||Marked_as_seed_Case_issue_1|標示為植入案例從相關性發行 1。|
|會議結束日期|MeetingEndDate|Meeting_end_date|會議的會議結束日期。|
|會議開始日期|MeetingStartDate|Meeting_start_date|會議的會議開始日期。|
|訊息類型|MessageKind|Message_kind|若要搜尋的訊息類型。 可能的值： ** <br /><br />連絡人<br />docs<br />電子郵件<br />externaldata<br />傳真<br />im<br />日誌<br />會議<br />microsoftteams** （從聊天室、 會議中，傳回的項目和 Microsoft Teams 中的通話）**<br />備忘稿<br />張貼<br />rssfeeds<br />工作<br />voicemail**| 
|原生副檔名|NativeExtension|Native_extension|項目的的原生擴充。|
|原生檔案名稱|NativeFileName|Native_file_name|原生檔案名稱的項目。|
|NativeMD5||Native_MD5|檔案資料流 MD5 雜湊。|
|ND/ET 排序： 不含附件|NdEtSortExclAttach|ND_ET_sort_excl_attach|電子郵件設定和 ND 有效率排序在檢閱階段; 設定串連而成**D**新增為前置詞 ND 設定和**E**新增至電子郵件設定。|
|ND/ET 排序： 包括附件|NdEtSortInclAttach|ND_ET_sort_incl_attach|電子郵件設定和 ND 有效率排序在檢閱階段; 設定串連而成**D**新增為前置詞 ND 設定和**E**新增至電子郵件設定。 電子郵件組內的每封電子郵件之後必須接著其適當的附件。|
|正規化相關性分數案例問題 1||Normalized_relevance_score_case_issue_1|正規化相關性分數案例問題 1 相關性。|
|O365 作者||O365_authors|從 SharePoint 的作者。|
|所建立的 O365||O365_created_by|從 SharePoint 所建立。|
|建立的 O365 日期||O365_date_created|從 SharePoint 的建立的日期。|
|修改的 O365 日期||O365_date_modified|從 SharePoint 的上次修改的日期。|
|修改的 O365||O365_modified_by|修改從 SharePoint。|
|父項識別碼|ParentId|Parent_ID|父項目識別碼。|
|ParentNode||Parent_node|最接近上述電子郵件訊息的電子郵件執行緒中。|
|父路徑|ParentPath|Parent_path|複合的直接上層項目的路徑。|
|參與者的網域|ParticipantDomains|Email_participant_domains|清單中的所有網域的郵件的參與者。|
|參與者|參與者|Email_participants|清單中的所有參與者的郵件。例如，寄件者、 To、 Cc [密件副本]。|
|樞紐分析表識別碼|PivotId|Pivot_ID|樞紐分析表的識別碼。|
|可能特殊權限|PotentiallyPrivileged|Potentially_privileged|True 是表示如果律師-委託人權限偵測模型考量可能特殊權限的文件|
|處理狀態|ProcessingStatus|錯誤碼|處理狀態之後的項目已新增至檢閱設定。|
|讀取的 %案例問題 1||Read_percent_Case_issue_1|讀取的 %案例問題 1 從相關性。|
|讀取百分位數|ReadPercentile||閱讀相關性為基礎的文件的百分位數。|
|收件者計數||Recipient_count|收件者的郵件數目。|
|收件者網域|RecipientDomains|Email_recipient_domains|所有網域的郵件收件者的清單。|
|收件者|收件者|Email_recipients|所有的收件者 (To、 Cc 密件副本) 的郵件清單。|
|相關性負載群組案例問題 1||Relevance_load_group_case_issue_1|相關性負載群組案例問題 1 從相關性。|
|相關性狀態描述案例問題 1||Relevance_status_description_Case_issue_1|相關性狀態描述案例問題 1 從相關性。|
|相關性標記案例問題 1||Relevance_tag_case_issue_1|相關性標記案例問題 1 從相關性。|
|相關性註解||Relevance_comment|從相關性的註解] 欄位。|
|相關性分數|RelevanceScore||相關性為基礎的文件的相關性分數。|
|相關性標記|RelevanceTag||相關性為基礎的文件的相關性分數。|
|具有代表性的識別碼|RepresentativeId||每一組完全重複的數值識別碼。|
|寄件者|寄件者|Email_sender|寄件者的郵件類型的欄位 （中）。 格式為**DisplayName \<SmtpAddress>**。|
|寄件者/作者|SenderAuthor||寄件者或項目的作者所組成的計算的欄位。|
|寄件者網域|SenderDomain|Email_sender_domain|寄件者的網域。|
|寄件日期|寄件日期|Email_date_sent|傳送的郵件的日期。|
|內含第一組順序：|SetOrderInclusivesFirst|Set_order_inclusives_first|排序欄位-電子郵件和附件： 逆時針先後;文件： 樞紐分析第一次然後依據遞減相似性分數。|
|SimilarityPercent||Similarity_percent|表示文件給 near 重複集的樞紐分析表的相似程度。|
|原生檔案大小|大小|Native_size|原生項目的的位元組數目。|
|主旨|主旨|Email_subject|郵件的主旨。|
|主旨/標題|SubjectTitle||在主旨或項目的標題所組成的計算的欄位。|
|標記的大小寫發出 1||Tagged_by_Case_issue_1|案例標記這份文件的使用者發出 1 中的相關性。|
|標記|標記|標記|在檢閱套用標記設定。|
|佈景主題清單|ThemesList|Themes_list|計算中分析的佈景主題清單。|
|職稱|職稱|Doc_title|從文件中繼資料的標題。|
|收件者|收件者|Email_to|若要針對郵件類型] 欄位。 格式為**DisplayName\<SmtpAddress>**|
|唯一的電子郵件設定|UniqueInEmailSet||**False**表示沒有在其電子郵件附件的複本設定。|
|已修復|WasRemediated|Was_Remediated|**True 是表示**如果項目已修復，否則為**False**。|
|字數統計|WordCount|Word_count|項目中的字詞數目。|
|||||

> [!NOTE]
> 如需可搜尋內容時搜尋 Office 365 內容的位置，當您正在收集資料的進階的 eDiscovery 案例的詳細資訊，請參閱[關鍵字查詢和搜尋條件的內容搜尋](keyword-queries-and-search-conditions.md)。