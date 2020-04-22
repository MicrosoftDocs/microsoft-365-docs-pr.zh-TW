---
title: 在高級電子檔探索中匯出報告欄位
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 840a5aff-ecd0-4e56-ad22-fe99bc143687
description: 說明所有納入高級 eDiscovery 之匯出報告中的欄位。
ms.openlocfilehash: a7ee8e3971ab2fc921085ca63f7a8451a1597be2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637805"
---
# <a name="export-report-fields-in-advanced-ediscovery-classic"></a>在高級 eDiscovery （古典）中匯出報告欄位

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本主題說明 Standard 和 All 範本的「高級 eDiscovery 匯出報告」欄位。
  
## <a name="export-report-fields"></a>匯出報告欄位

下表列出每個匯出範本的欄位。
  
|**匯出功能變數名稱**|**群組**|**說明**|**可用於標準範本**|**可用於所有範本**|
|:-----|:-----|:-----|:-----|:-----|
|Row_number  <br/> |一般  <br/> |列號。  <br/> |是  <br/> |是  <br/> |
|File_ID  <br/> |一般  <br/> |檔識別碼。  <br/> |是  <br/> |是  <br/> |
|File_class  <br/> |處理  <br/> |檔類別。  <br/> |是  <br/> |是  <br/> |
|Family_ID  <br/> |處理  <br/> |用以群組檔案（通常是電子郵件實例及其附件）的數值識別碼。  <br/> |是  <br/> |是  <br/> |
|For_review  <br/> |處理  <br/> |旗標，指出將會包含在 [匯出以供審閱] 欄位。  <br/> |是  <br/> |是  <br/> |
|Native_file_name  <br/> |處理  <br/> |原生檔案名，未參照資料夾及副檔名。  <br/> |是  <br/> |是  <br/> |
|保管員  <br/> |一般  <br/> |檔案的管理員。  <br/> |是  <br/> |是  <br/> |
|Set_ID  <br/> |分析  <br/> |"ND set" 或「電子郵件組」識別碼。  <br/> |是  <br/> |是  <br/> |
|Inclusive_type  <br/> |電子郵件  <br/> |會指出是否包含檔，根據下列值：0（非包含）、包含1個包含專案、包含2個包含的副本。  <br/> |是  <br/> |是  <br/> |
|Marked_as_pivot  <br/> |接近重複專案  <br/> |會指出檔是否為 pivot。  <br/> |是  <br/> |是  <br/> |
|Similarity_percent  <br/> |接近重複專案  <br/> |相對於 pivot 的相似性百分比。  <br/> |是  <br/> |是  <br/> |
|Duplicate_subset  <br/> |接近重複專案  <br/> |重複子集的唯一識別碼。 會指出檔案是否有完全相同的文字重複。  <br/> |是  <br/> |是  <br/> |
|日期  <br/> |一般  <br/> |檔日期（取決於檔案類型-電子郵件：傳送日期; 檔：修改日期）。  <br/> |是  <br/> |是  <br/> |
|Dominant_theme  <br/> |分析  <br/> |檔案的主要主題。  <br/> |是  <br/> |是  <br/> |
|Themes_list  <br/> |佈景主題  <br/> |主題名稱的清單。  <br/> |是  <br/> |是  <br/> |
|ND_set  <br/> |EquiSet  <br/> |Nearduplicate 集的唯一數位識別碼。  <br/> |是  <br/> |是  <br/> |
|Email_set  <br/> |電子郵件  <br/> |電子郵件組的唯一數位識別碼。  <br/> |是  <br/> |是  <br/> |
|Email_thread  <br/> |電子郵件  <br/> |描述電子郵件內電子郵件的位置，此電子郵件是由從根目錄到目前電子郵件的所有節點 IDs 所組成，以句點分隔。  <br/> |是  <br/> |是  <br/> |
|Email_subject  <br/> |電子郵件  <br/> |電子郵件的主旨。  <br/> |是  <br/> |是  <br/> |
|Email_date_sent  <br/> |電子郵件  <br/> |電子郵件的傳送日期。  <br/> |是  <br/> |是  <br/> |
|Email_participants  <br/> |電子郵件  <br/> |電子郵件線索中所有參與者的電子郵件地址，包含缺失的連結。  <br/> |是  <br/> |是  <br/> |
|Email_participant_domains  <br/> |電子郵件  <br/> |電子郵件執行緒中所有參與者的網域，包含缺失的連結。  <br/> |是  <br/> |是  <br/> |
|Email_sender  <br/> |電子郵件  <br/> |電子郵件寄件者名稱及（或）位址。  <br/> |是  <br/> |是  <br/> |
|Email_sender_domain  <br/> |電子郵件  <br/> |電子郵件寄件者的網域。  <br/> |是  <br/> |是  <br/> |
|Email_to  <br/> |電子郵件  <br/> |電子郵件的收件者。  <br/> |是  <br/> |是  <br/> |
|Email_cc  <br/> |電子郵件  <br/> |電子郵件的抄送收件者。  <br/> |是  <br/> |是  <br/> |
|Email_bcc  <br/> |電子郵件  <br/> |電子郵件的密件副本收件者。  <br/> |是  <br/> |是  <br/> |
|Email_recipient_domains  <br/> |電子郵件  <br/> |電子郵件收件者網域（收件者、抄送及密送）。  <br/> |是  <br/> |是  <br/> |
|Email_date_received  <br/> |電子郵件  <br/> |接收電子郵件的日期。  <br/> |是  <br/> |是  <br/> |
|Email_action  <br/> |電子郵件  <br/> |值：根據電子郵件主旨：「轉寄」（適用于 "FW:"）、「回復」（適用于 "RE:"）或 "Other" （其他主題文字）。  <br/> |是  <br/> |是  <br/> |
|Meeting_Start_Date/Time  <br/> ||會議專案開始的日期和時間。  <br/> |是  <br/> |是  <br/> |
|Meeting_End_Date/Time  <br/> ||會議專案結束的日期和時間。  <br/> |是  <br/> |是  <br/> |
|File_relevance_score  <br/> |相關性  <br/> |相關性分數（0-100）。 每個問題。  <br/> |是  <br/> |是  <br/> |
|Family_relevance_score  <br/> |相關性  <br/> |最大系列相關性分數（0-100）。 每個問題。  <br/> |是  <br/> |是  <br/> |
|Relevance_tag  <br/> |相關性  <br/> |檔的標記（如果檔案已手動標示為相關性）。 每個問題。  <br/> |是  <br/> |是  <br/> |
|Relevance_load_group  <br/> |相關性  <br/> |指定檔案的相關性載入群組，每個問題的欄位。  <br/> |是  <br/> |是  <br/> |
|Normalized_relevance_score  <br/> |相關性  <br/> |標準化相關性分數（0-100），其適用于問題與負載之間的比較。  <br/> |是  <br/> |是  <br/> |
|Marked_as_seed  <br/> |相關性  <br/> |檔的標記（如果它已設定為每個問題的相關性檔案）/類別。  <br/> |是  <br/> |是  <br/> |
|Marked_as_pre 標記  <br/> |相關性  <br/> |檔的標記（如果它已設定為 [每個問題的相關性）]。  <br/> |是  <br/> |是  <br/> |
|Relevance_status_description  <br/> |相關性  <br/> |相關性狀態的描述。  <br/> |是  <br/> |是  <br/> |
|留言  <br/> |一般  <br/> |使用者輸入的批註。  <br/> |是  <br/> |是  <br/> |
|Export_input_path  <br/> |處理  <br/> |匯出輸入路徑。  <br/> |是  <br/> |是  <br/> |
|Pivot_ID  <br/> |接近重複專案  <br/> |檔的樞紐分析表識別碼。  <br/> |是  <br/> |是  <br/> |
|Family_size  <br/> |處理  <br/> |系列中的檔案數目。  <br/> |是  <br/> |是  <br/> |
|Native_type  <br/> |處理  <br/> |原生檔案類型。 例如，試算表或簡報。  <br/> |是  <br/> |是  <br/> |
|Native_MD5  <br/> |處理  <br/> |原生檔案 MD5 雜湊值。  <br/> |是  <br/> |是  <br/> |
|Native_size  <br/> |處理  <br/> |原生檔案大小。  <br/> |是  <br/> |是  <br/> |
|Native_extension  <br/> |處理  <br/> |原生副檔名。  <br/> |是  <br/> |是  <br/> |
|Doc_date_modified  <br/> |檔案屬性  <br/> |修改原生檔案的日期（從檔案的中繼資料中取得）。  <br/> |是  <br/> |是  <br/> |
|Doc_date_created  <br/> |檔案屬性  <br/> |從檔案的中繼資料中所建立的原生檔案的建立日期。  <br/> |是  <br/> |是  <br/> |
|Doc_modified_by  <br/> |檔案屬性  <br/> |修改原生檔案的使用者，來自檔案的中繼資料。  <br/> |是  <br/> |是  <br/> |
|O365_date_modified  <br/> |檔案屬性  <br/> |修改原生檔案的日期（從 SharePoint 或 Exchange 欄位取得）。  <br/> |是  <br/> |是  <br/> |
|O365_date_created  <br/> |檔案屬性  <br/> |從 SharePoint 或 Exchange 欄位建立的原生檔案。  <br/> |是  <br/> |是  <br/> |
|O365_modified_by  <br/> |檔案屬性  <br/> |從 SharePoint 或 Exchange 欄位取得的上次修改原生檔案的使用者。  <br/> |是  <br/> |是  <br/> |
|Compound_path  <br/> |處理  <br/> |包含其複合來源的原生檔路徑。  <br/> |是  <br/> |是  <br/> |
|Input_path  <br/> |處理  <br/> |輸入檔案的路徑。  <br/> |是  <br/> |是  <br/> |
|Input_date_modified  <br/> |處理  <br/> |上次修改日期輸入檔案。  <br/> |是  <br/> |是  <br/> |
|ND_ET_sort_excl_attach  <br/> |分析  <br/> |電子郵件組和 ND 的串連已設定為供複查。 ' D ' 會新增為 ND 集的前置詞，而且 ' E ' 已新增至電子郵件 ssets。  <br/> |是  <br/> |是  <br/> |
|ND_ET_sort_incl_attach  <br/> |分析  <br/> |將電子郵件集和 ND 設定成「送出」組的連接，會新增為 ND 集的前置詞，而 ' E ' 已新增至電子郵件組。 此外，Email_set 內的每封電子郵件都會跟隨其適當的附件。  <br/> |是  <br/> |是  <br/> |
|Deduped_custodians  <br/> |一般  <br/> |Duped 檔案的保管人  <br/> |是  <br/> |是  <br/> |
|Deduped_file_IDs  <br/> |一般  <br/> |Duped 檔的 IDs  <br/> |是  <br/> |是  <br/> |
|Deduped_paths  <br/> |一般  <br/> |解除 duped 檔案的路徑  <br/> |是  <br/> |是  <br/> |
|File_key  <br/> |一般  <br/> |供未來使用的內部識別碼。  <br/> |是  <br/> |是  <br/> |
|Export_native_path  <br/> |處理  <br/> |匯出套件中原生檔案的路徑。  <br/> |是  <br/> |是  <br/> |
|Extracted_text_path  <br/> |處理  <br/> |解壓縮檔的路徑。  <br/> |是  <br/> |是  <br/> |
|Process_batch  <br/> |處理  <br/> |匯入批次的批次識別碼。  <br/> |是  <br/> |是  <br/> |
|Process_status_ID  <br/> |處理  <br/> |代表處理階段狀態的識別碼。  <br/> |是  <br/> |是  <br/> |
|Process_status_description  <br/> |處理  <br/> |處理階段狀態原因：成功或錯誤描述。  <br/> |是  <br/> |是  <br/> |
|Export_status_ID  <br/> |處理  <br/> |匯出狀態的識別碼。  <br/> |是  <br/> |是  <br/> |
|Export_status_description  <br/> |處理  <br/> |匯出狀態的描述;成功或錯誤描述。  <br/> |是  <br/> |是  <br/> |
|Read_percent  <br/> |相關性  <br/> |讀取% （0-100）。 每個問題。  <br/> |是  <br/> |是  <br/> |
|Doc_author  <br/> |文件屬性  <br/> |檔案屬性： author。  <br/> |否  <br/> |是  <br/> |
|Doc_comments  <br/> |文件屬性  <br/> |檔案屬性：批註。  <br/> |否  <br/> |是  <br/> |
|Doc_keywords  <br/> |文件屬性  <br/> |檔案屬性：關鍵字。  <br/> |否  <br/> |是  <br/> |
|Doc_last_saved_by  <br/> |文件屬性  <br/> |檔案屬性：上次儲存者。  <br/> |否  <br/> |是  <br/> |
|Doc_revision  <br/> |文件屬性  <br/> |檔案屬性：修訂編號。  <br/> |否  <br/> |是  <br/> |
|Doc_subject  <br/> |文件屬性  <br/> |檔案屬性： subject。  <br/> |否  <br/> |是  <br/> |
|Doc_template  <br/> |文件屬性  <br/> |檔案屬性：範本。  <br/> |否  <br/> |是  <br/> |
|Doc_title  <br/> |文件屬性  <br/> |檔案屬性： title。  <br/> |否  <br/> |是  <br/> |
|Email_has_attachment  <br/> |電子郵件  <br/> |會指出電子郵件是否有一個或多個附件。  <br/> |否  <br/> |是  <br/> |
|Email_importance  <br/> |電子郵件  <br/> |電子郵件重要性屬性。  <br/> |否  <br/> |是  <br/> |
|Email_level  <br/> |電子郵件  <br/> |會指出電子郵件在電子郵件線索中的層級。 附件的附件，附加的電子郵件的值。  <br/> |否  <br/> |是  <br/> |
|Email_recipients  <br/> |電子郵件  <br/> |電子郵件收件者的名稱和/或位址（收件者、抄送及密送）。  <br/> |否  <br/> |是  <br/> |
|Email_security  <br/> |電子郵件  <br/> |Email security 屬性。  <br/> |否  <br/> |是  <br/> |
|Email_sensitivity  <br/> |電子郵件  <br/> |電子郵件敏感度屬性。  <br/> |否  <br/> |是  <br/> |
|Export_batch  <br/> |處理  <br/> |檔案的最後一個匯出批次名稱。  <br/> |否  <br/> |是  <br/> |
|Export_session  <br/> |處理  <br/> |檔案的最後一個匯出會話識別碼（包含日期）。  <br/> |否  <br/> |是  <br/> |
|Extracted_text_length  <br/> |處理  <br/> |解壓縮的文字檔的字元長度。  <br/> |否  <br/> |是  <br/> |
|Family_duplicate_set  <br/> |處理  <br/> |完全文字重複的系列的數值識別碼（分別為所有的系列成員是完全重複的）。  <br/> |否  <br/> |是  <br/> |
|Has_Text  <br/> |處理  <br/> |會指出檔案中是否有文字： 0-否;1-是。  <br/> |否  <br/> |是  <br/> |
|Input_file_ID  <br/> |處理  <br/> |從中解壓縮檔案之來源輸入檔案的識別碼。  <br/> |否  <br/> |是  <br/> |
|Native_SHA_256  <br/> |處理  <br/> |原生檔案 SHA-256 雜湊值。  <br/> |否  <br/> |是  <br/> |
|O365_authors  <br/> |文件屬性  <br/> |修改原生檔案的使用者，可從 SharePoint 或 Exchange 欄位取得。  <br/> |否  <br/> |是  <br/> |
|O365_created_by  <br/> |文件屬性  <br/> |從 [SharePoint] 或 [Exchange] 欄位取得的原生檔案建立的使用者。  <br/> |否  <br/> |是  <br/> |
|Parent_node  <br/> |電子郵件  <br/> |將電子郵件執行緒中的節點與最接近的父節點（不是遺失的連結）相關聯。  <br/> |否  <br/> |是  <br/> |
|Set_order_inclusives_first  <br/> |電子郵件  <br/> |電子郵件和附件：依序順序（Inclusives）。 檔：先依相似性分數（降冪）旋轉。  <br/> |否  <br/> |是  <br/> |
|Tagged_By  <br/> |相關性  <br/> |針對特定問題標示檔相關的使用者。  <br/> |否  <br/> |是  <br/> |
|Word_count  <br/> |分析  <br/> |檔中的字數。  <br/> |否  <br/> |是  <br/> |
|
   
## <a name="related-topics"></a>相關主題

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[使用高級 eDiscovery 匯出案例資料](export-case-data-in-advanced-ediscovery.md)
  
[匯出結果](export-results-in-advanced-ediscovery.md)
  
[查看批次歷史記錄及匯出過去的結果](view-batch-history-and-export-past-results.md)
  

