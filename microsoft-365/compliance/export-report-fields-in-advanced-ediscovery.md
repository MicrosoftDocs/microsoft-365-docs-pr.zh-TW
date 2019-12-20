---
title: 在 Office 365 進階電子文件探索中匯出報告欄位
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
description: 說明在進階電子文件的匯出報告中包含的所有欄位。
ms.openlocfilehash: cc585fcabefa9036d91162b6418c3e5e9c752378
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805836"
---
# <a name="export-report-fields-in-office-365-advanced-ediscovery"></a>在 Office 365 進階電子文件探索中匯出報告欄位

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本主題說明標準和所有範本的進階電子文件探索匯出報告欄位。
  
## <a name="export-report-fields"></a>匯出報告欄位

下表列出每個匯出範本的欄位。
  
|**匯出欄位名稱**|**群組**|**說明**|**提供標準範本**|**適用於所有範本**|
|:-----|:-----|:-----|:-----|:-----|
|即  <br/> |一般  <br/> |列號。  <br/> |是  <br/> |是  <br/> |
|File_ID  <br/> |一般  <br/> |檔案識別碼。  <br/> |是  <br/> |是  <br/> |
|File_class  <br/> |處理  <br/> |檔案類別。  <br/> |是  <br/> |是  <br/> |
|Family_ID  <br/> |處理  <br/> |用來群組檔案 （通常是電子郵件執行個體和其附件） 的數值識別碼。  <br/> |是  <br/> |是  <br/> |
|For_review  <br/> |處理  <br/> |表示欄位將會包含在匯出供檢閱的旗標。  <br/> |是  <br/> |是  <br/> |
|Native_file_name  <br/> |處理  <br/> |原生檔案名稱，而不參照資料夾和分機號碼。  <br/> |是  <br/> |是  <br/> |
|Custodians  <br/> |一般  <br/> |Custodian 的檔案。  <br/> |是  <br/> |是  <br/> |
|Set_ID  <br/> |分析  <br/> |「 ND 設定 」 或者 「 電子郵件設定 」 的識別碼。  <br/> |是  <br/> |是  <br/> |
|Inclusive_type  <br/> |電子郵件  <br/> |會指出如果檔案 （含），根據下列值： 0-不含 1-（含)，2-內含減 3-（含） 的複本。  <br/> |是  <br/> |是  <br/> |
|Marked_as_pivot  <br/> |Near 重複項目  <br/> |會指出檔案是否樞紐分析表。  <br/> |是  <br/> |是  <br/> |
|Similarity_percent  <br/> |Near 重複項目  <br/> |相對於樞紐分析表的相似性的百分比。  <br/> |是  <br/> |是  <br/> |
|Duplicate_subset  <br/> |Near 重複項目  <br/> |重複的子集的唯一識別碼。 會指出檔案是否有重複的確切文字項目。  <br/> |是  <br/> |是  <br/> |
|日期  <br/> |一般  <br/> |檔案的日期 (取決於檔案類型的電子郵件： 傳送的日期; 文件： 修改日期)。  <br/> |是  <br/> |是  <br/> |
|Dominant_theme  <br/> |分析  <br/> |主要的佈景主題的檔案。  <br/> |是  <br/> |是  <br/> |
|Themes_list  <br/> |佈景主題  <br/> |佈景主題名稱的清單。  <br/> |是  <br/> |是  <br/> |
|ND_set  <br/> |EquiSet  <br/> |Nearduplicate 集的唯一的數值識別碼。  <br/> |是  <br/> |是  <br/> |
|Email_set  <br/> |電子郵件  <br/> |唯一的電子郵件設定的數值識別碼。  <br/> |是  <br/> |是  <br/> |
|Email_thread  <br/> |電子郵件  <br/> |說明在電子郵件內的電子郵件的位置設定的所有節點識別碼 Consists 從根目前的電子郵件，並以句點分隔。  <br/> |是  <br/> |是  <br/> |
|Email_subject  <br/> |電子郵件  <br/> |電子郵件的主旨。  <br/> |是  <br/> |是  <br/> |
|Email_date_sent  <br/> |電子郵件  <br/> |電子郵件的傳送日期。  <br/> |是  <br/> |是  <br/> |
|Email_participants  <br/> |電子郵件  <br/> |電子郵件地址的電子郵件執行緒，包括缺少連結中的所有參與者。  <br/> |是  <br/> |是  <br/> |
|Email_participant_domains  <br/> |電子郵件  <br/> |網域的電子郵件執行緒，包括缺少連結中的所有參與者。  <br/> |是  <br/> |是  <br/> |
|Email_sender  <br/> |電子郵件  <br/> |電子郵件寄件者名稱及/或地址。  <br/> |是  <br/> |是  <br/> |
|Email_sender_domain  <br/> |電子郵件  <br/> |電子郵件寄件者的網域。  <br/> |是  <br/> |是  <br/> |
|Email_to  <br/> |電子郵件  <br/> |收件者的電子郵件。  <br/> |是  <br/> |是  <br/> |
|Email_cc  <br/> |電子郵件  <br/> |[副本] 收件者的電子郵件。  <br/> |是  <br/> |是  <br/> |
|Email_bcc  <br/> |電子郵件  <br/> |[密件副本收件者的電子郵件。  <br/> |是  <br/> |是  <br/> |
|Email_recipient_domains  <br/> |電子郵件  <br/> |電子郵件收件者 (To、 [副本] 及 [密件副本]） 的網域。  <br/> |是  <br/> |是  <br/> |
|Email_date_received  <br/> |電子郵件  <br/> |在其接收電子郵件的日期。  <br/> |是  <br/> |是  <br/> |
|Email_action  <br/> |電子郵件  <br/> |值： 根據電子郵件主旨: 「 轉寄 」 (的 「 FW: 」)，「 回覆 」 (的"RE: 「) 或 「 其他 」 （其他主體文字）。  <br/> |是  <br/> |是  <br/> |
|Meeting_Start_Date/時間  <br/> ||日期和時間的會議項目開始。  <br/> |是  <br/> |是  <br/> |
|Meeting_End_Date/時間  <br/> ||日期和結束會議項目的時間。  <br/> |是  <br/> |是  <br/> |
|File_relevance_score  <br/> |相關性  <br/> |相關性分數 (0-100)。 每個問題。  <br/> |是  <br/> |是  <br/> |
|Family_relevance_score  <br/> |相關性  <br/> |最大系列相關性分數 (0-100)。 每個問題。  <br/> |是  <br/> |是  <br/> |
|Relevance_tag  <br/> |相關性  <br/> |如果檔案以手動方式標記中相關性，標記檔案。 每個問題。  <br/> |是  <br/> |是  <br/> |
|Relevance_load_group  <br/> |相關性  <br/> |相關性負載群組，指定的檔案，以每此問題:] 欄位。  <br/> |是  <br/> |是  <br/> |
|Normalized_relevance_score  <br/> |相關性  <br/> |正規化的相關性分數 (0-100)，這是相當問題與負載之間。  <br/> |是  <br/> |是  <br/> |
|Marked_as_seed  <br/> |相關性  <br/> |如果它已設為相關性每個問題/類別中的植入檔案是，標記檔案。  <br/> |是  <br/> |是  <br/> |
|Marked_as_pre 標記  <br/> |相關性  <br/> |如果它是設定為預先標記相關性每個問題/類別中，標記的檔案。  <br/> |是  <br/> |是  <br/> |
|Relevance_status_description  <br/> |相關性  <br/> |相關性狀態的描述。  <br/> |是  <br/> |是  <br/> |
|留言  <br/> |一般  <br/> |使用者所輸入的註解。  <br/> |是  <br/> |是  <br/> |
|Export_input_path  <br/> |處理  <br/> |匯出輸入的路徑。  <br/> |是  <br/> |是  <br/> |
|Pivot_ID  <br/> |Near 重複項目  <br/> |樞紐分析表檔案的識別碼。  <br/> |是  <br/> |是  <br/> |
|Family_size  <br/> |處理  <br/> |系列中的檔案數目。  <br/> |是  <br/> |是  <br/> |
|Native_type  <br/> |處理  <br/> |原生檔案類型。 例如，試算表或簡報。  <br/> |是  <br/> |是  <br/> |
|Native_MD5  <br/> |處理  <br/> |原生檔案 MD5 雜湊值。  <br/> |是  <br/> |是  <br/> |
|Native_size  <br/> |處理  <br/> |原生檔案大小。  <br/> |是  <br/> |是  <br/> |
|Native_extension  <br/> |處理  <br/> |原生檔案的副檔名。  <br/> |是  <br/> |是  <br/> |
|Doc_date_modified  <br/> |文件屬性  <br/> |原生檔案的修改，採取從檔案的中繼資料的日期。  <br/> |是  <br/> |是  <br/> |
|Doc_date_created  <br/> |文件屬性  <br/> |日期原生檔案已建立，拍攝從檔案的中繼資料。  <br/> |是  <br/> |是  <br/> |
|Doc_modified_by  <br/> |文件屬性  <br/> |修改原生檔案，從檔案的中繼資料採取的使用者。  <br/> |是  <br/> |是  <br/> |
|O365_date_modified  <br/> |文件屬性  <br/> |修改日期原生檔案，擷取自 SharePoint or Exchange 欄位。  <br/> |是  <br/> |是  <br/> |
|O365_date_created  <br/> |文件屬性  <br/> |建立日期原生檔案，從 SharePoint] 或 [Exchange] 欄位。  <br/> |是  <br/> |是  <br/> |
|O365_modified_by  <br/> |文件屬性  <br/> |上次使用者修改原生檔案，從 SharePoint] 或 [Exchange] 欄位。  <br/> |是  <br/> |是  <br/> |
|Compound_path  <br/> |處理  <br/> |原生檔案路徑，包括其複合的來源。  <br/> |是  <br/> |是  <br/> |
|Input_path  <br/> |處理  <br/> |輸入檔案的路徑。  <br/> |是  <br/> |是  <br/> |
|Input_date_modified  <br/> |處理  <br/> |上次修改日期輸入檔案。  <br/> |是  <br/> |是  <br/> |
|ND_ET_sort_excl_attach  <br/> |分析  <br/> |串連的電子郵件設定並且 ND 設定供檢閱。 有 ' 會新增為 ND 組及 'E' 前置詞會新增至電子郵件 ssets。  <br/> |是  <br/> |是  <br/> |
|ND_ET_sort_incl_attach  <br/> |分析  <br/> |串連的電子郵件設定和設定供檢閱的 ND 會 ' 會新增為 ND 組，並 'E' 前置詞會新增電子郵件設定。 此外，每封電子郵件內 Email_set 之後必須接著其適當的附件。  <br/> |是  <br/> |是  <br/> |
|Deduped_custodians  <br/> |一般  <br/> |取消上當檔案的 custodians  <br/> |是  <br/> |是  <br/> |
|Deduped_file_IDs  <br/> |一般  <br/> |取消上當檔案的識別碼  <br/> |是  <br/> |是  <br/> |
|Deduped_paths  <br/> |一般  <br/> |取消上當檔案路徑  <br/> |是  <br/> |是  <br/> |
|File_key  <br/> |一般  <br/> |供日後使用的內部識別碼。  <br/> |是  <br/> |是  <br/> |
|Export_native_path  <br/> |處理  <br/> |匯出套件中的原生檔案的路徑。  <br/> |是  <br/> |是  <br/> |
|Extracted_text_path  <br/> |處理  <br/> |解壓縮檔案的路徑。  <br/> |是  <br/> |是  <br/> |
|Process_batch  <br/> |處理  <br/> |匯入批次的批次識別碼。  <br/> |是  <br/> |是  <br/> |
|Process_status_ID  <br/> |處理  <br/> |表示程序階段狀態的識別項。  <br/> |是  <br/> |是  <br/> |
|Process_status_description  <br/> |處理  <br/> |處理程序階段狀態描述： 成功或錯誤描述。  <br/> |是  <br/> |是  <br/> |
|Export_status_ID  <br/> |處理  <br/> |匯出狀態的識別碼。  <br/> |是  <br/> |是  <br/> |
|Export_status_description  <br/> |處理  <br/> |匯出狀態; 描述成功或錯誤描述。  <br/> |是  <br/> |是  <br/> |
|Read_percent  <br/> |相關性  <br/> |讀取 %(0-100)。 每個問題。  <br/> |是  <br/> |是  <br/> |
|Doc_author  <br/> |文件屬性  <br/> |文件屬性： 作者。  <br/> |否  <br/> |是  <br/> |
|Doc_comments  <br/> |文件屬性  <br/> |文件屬性： 註解。  <br/> |否  <br/> |是  <br/> |
|Doc_keywords  <br/> |文件屬性  <br/> |文件屬性： 關鍵字。  <br/> |否  <br/> |是  <br/> |
|Doc_last_saved_by  <br/> |文件屬性  <br/> |文件屬性： 上次存檔者。  <br/> |否  <br/> |是  <br/> |
|Doc_revision  <br/> |文件屬性  <br/> |文件屬性： 修訂編號。  <br/> |否  <br/> |是  <br/> |
|Doc_subject  <br/> |文件屬性  <br/> |文件屬性： 主旨。  <br/> |否  <br/> |是  <br/> |
|Doc_template  <br/> |文件屬性  <br/> |文件屬性： 範本。  <br/> |否  <br/> |是  <br/> |
|Doc_title  <br/> |文件屬性  <br/> |文件屬性： 標題。  <br/> |否  <br/> |是  <br/> |
|Email_has_attachment  <br/> |電子郵件  <br/> |指出電子郵件是否具有一或多個附件。  <br/> |否  <br/> |是  <br/> |
|Email_importance  <br/> |電子郵件  <br/> |電子郵件重要性屬性。  <br/> |否  <br/> |是  <br/> |
|Email_level  <br/> |電子郵件  <br/> |會指出在電子郵件執行緒內的電子郵件的層級。 附件，附加的電子郵件的值。  <br/> |否  <br/> |是  <br/> |
|Email_recipients  <br/> |電子郵件  <br/> |名稱及/或 (To、 CC 或 BCC） 地址的電子郵件收件者。  <br/> |否  <br/> |是  <br/> |
|Email_security  <br/> |電子郵件  <br/> |電子郵件安全性屬性。  <br/> |否  <br/> |是  <br/> |
|Email_sensitivity  <br/> |電子郵件  <br/> |Sensitivity 屬性的電子郵件。  <br/> |否  <br/> |是  <br/> |
|Export_batch  <br/> |處理  <br/> |檔案的最後一個匯出批次名稱。  <br/> |否  <br/> |是  <br/> |
|Export_session  <br/> |處理  <br/> |檔案的上次匯出工作階段識別碼包括日期。  <br/> |否  <br/> |是  <br/> |
|Extracted_text_length  <br/> |處理  <br/> |擷取文字檔案的字元長度。  <br/> |否  <br/> |是  <br/> |
|Family_duplicate_set  <br/> |處理  <br/> |另一部的確切文字重複的家庭成員的數值識別碼 （分別-系列中的所有成員都是完全重複的項目）。  <br/> |否  <br/> |是  <br/> |
|Has_Text  <br/> |處理  <br/> |會指出是否有文字檔案中： 0-不;1-[是]。  <br/> |否  <br/> |是  <br/> |
|Input_file_ID  <br/> |處理  <br/> |輸入檔案從從中擷取檔案的識別碼。  <br/> |否  <br/> |是  <br/> |
|Native_SHA_256  <br/> |處理  <br/> |原生檔案 sha-256 雜湊值。  <br/> |否  <br/> |是  <br/> |
|O365_authors  <br/> |文件屬性  <br/> |修改原生檔案，從 SharePoint] 或 [Exchange] 欄位的使用者。  <br/> |否  <br/> |是  <br/> |
|O365_created_by  <br/> |文件屬性  <br/> |建立原生檔案，從 SharePoint] 或 [Exchange] 欄位的使用者。  <br/> |否  <br/> |是  <br/> |
|Parent_node  <br/> |電子郵件  <br/> |與電子郵件執行緒中的節點關聯之最接近的父節點的不是遺失的連結。  <br/> |否  <br/> |是  <br/> |
|Set_order_inclusives_first  <br/> |電子郵件  <br/> |電子郵件和附件： 計數器先後順序 (Inclusives 第一個)。 文件： 會進行第一和 rest 由相似性分數，遞減樞紐分析。  <br/> |否  <br/> |是  <br/> |
|Tagged_By  <br/> |相關性  <br/> |在 [相關性標記檔案的特定問題的使用者。  <br/> |否  <br/> |是  <br/> |
|Word_count  <br/> |分析  <br/> |文件中的字詞數目。  <br/> |否  <br/> |是  <br/> |
|
   
## <a name="related-topics"></a>相關主題

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[使用進階電子文件的匯出案例資料](export-case-data-in-advanced-ediscovery.md)
  
[匯出結果](export-results-in-advanced-ediscovery.md)
  
[檢視批次歷程記錄及匯出過去的結果](view-batch-history-and-export-past-results.md)
  

