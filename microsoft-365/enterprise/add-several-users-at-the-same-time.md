---
title: 同時將多個使用者新增至 Microsoft 365-系統管理說明
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
ms.assetid: 1f5767ed-e717-4f24-969c-6ea9d412ca88
description: '瞭解如何從試算表或其他 CSV 格式的檔案中的清單，將多個使用者新增至 Microsoft 365 for business。 在說明如何將帳戶新增至 Microsoft 365 的 YouTube 觀看影片。 在此程式結束時，具有帳戶的每位使用者都會有 Microsoft 365 信箱。 '
ms.openlocfilehash: c75f16233a85f48be44082ba3ec9ffb82ef18ff9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688874"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a>同時將多個使用者新增至 Microsoft 365-系統管理說明

小組中的每位人員必須先使用使用者帳戶，才能登入並存取 Microsoft 365 服務，例如電子郵件和 Office。如果您有許多人員，您可以從 Excel 試算表或以 CSV 格式儲存的其他檔案，一次新增他們的帳戶。 [不確定 CSV 格式是什麼？](add-several-users-at-the-same-time.md#__toc316652088)
  
> [!NOTE] 
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心] **開關將它開啟。

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心新增多個使用者

1. 請使用工作或學校帳戶登入 Microsoft 365。 
    
2. 在系統管理中心，選擇 **[使用者]**\> > **[作用中使用者]**。

3. 選取 [ **新增多個使用者**]。

4. 在 **[匯入多個使用者]** 面板中，您可以選擇下載包含或不含範例資料的範例 CSV 檔。 
    
    您的試算表必須包含和範例試算表**完全相同的欄位標題** (使用者名稱、名字等)。如果您使用範本，請在記事本這類的文字編輯工具中開啟範本，然後考慮將列 1 的所有資料維持原狀，只在列 2 以下輸入資料。 
    
    您的試算表也必須包含使用者名稱 (例如 bob@contoso.com) 與每個使用者的顯示名稱 (例如「柯百勝」) 這兩個值。 
    
  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-9821,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-9822,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-9823,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-9824,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-9825,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. 在方塊中輸入檔案路徑，或選擇 **[瀏覽]** 以瀏覽至 CSV 檔案的位置，然後選擇 **[驗證]**。
  
    如果檔案有任何問題，問題會顯示在面板中。您也可以下載記錄檔。
    
5. 在 **[設定使用者選項]** 對話方塊中，您可以設定登入狀態，並選擇要指派給所有使用者的產品授權。 
    
6. 在 **[檢視結果]** 對話方塊中，您可以選擇將結果傳送給自己或其他使用者 (密碼會以純文字顯示)，並且可以看到已建立多少使用者，以及是否需要購買更多授權以指派給某些新使用者。 

## <a name="next-steps"></a>後續步驟
<a name="bk_preview"> </a>

- 現在，這些人具有帳戶，他們必須 [在電腦或 Mac 上下載並安裝或重新安裝 Microsoft 365 或 Office 2016](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)。 您的小組中的每位人員最多可以在5部 Pc 或 Mac 上安裝 Microsoft 365。 
    
- 每位人員也可以[在行動裝置上安裝 Office 應用程式和電子郵件](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) (最多 5 部平板電腦和 5 支手機)，例如 iPhone、iPad 和 Android 電話及平板電腦。 這樣一來，他們就能隨時隨地編輯 Office 檔案。 
    
    如需安裝步驟的端對端清單，請參閱 [設定 Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) 。 
    
## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a>如何將使用者新增至 Microsoft 365 的詳細資訊
<a name="bk_preview"> </a>

### <a name="not-sure-what-csv-format-is"></a>不確定 CSV 格式是什麼嗎？
<a name="__toc316652088"> </a>

CSV 檔案是以逗號區分值的檔案。您可以用任何文字編輯器或試算表程式 (例如 Excel) 來建立或編輯這樣的檔案。
  
您可以從下載[這份樣本試算表](https://www.microsoft.com/download/details.aspx?id=45485)開始著手。 請注意，Microsoft 365 需要在第一列中欄標題，否則請勿將其取代為其他內容。 
  
接著請以新名稱儲存檔案，然後指定 CSV 格式。
  
![說明如何在 Excel 中將檔案儲存為 CSV 格式的影像](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
儲存檔案時，系統會提示您若儲存為 CSV 格式，將遺失部分活頁簿中的功能。 這沒有關係。 按一下 **[是]** 以繼續。 
  
![Excel 可能會向您顯示的提示圖片，Excel 會詢問您是否真的要將檔案儲存為 CSV 格式](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a>設定試算表格式的祕訣
<a name="__toc314595848"> </a>

- **我需要使用和範例試算表中相同的欄標題嗎？** 是。 樣本試算表的第一列是欄標題。 這些標題不能省略。 針對您要新增至 Microsoft 365 的每一位使用者，在標題底下建立一列。 如果您新增、變更或刪除任何欄標題，Microsoft 365 可能無法從檔案中的資訊建立使用者。 
    
- **如果我沒有每位使用者所需的所有資訊，該怎麼辦？** 使用者名稱和顯示名稱是必要資訊，缺少的話無法新增新使用者。 若您缺少部分其他資訊 (例如傳真)，可使用空格加上逗號表示此欄位應保留空白。 
    
- **試算表大小的上下限為何？** 試算表至少要有兩列。 一列是欄標題 (使用者資料欄標籤)，另一列是使用者。 列數不得超過 251 列。 如果您必須匯入超過 250 位使用者，可以建立多份試算表。 
    
- **我可以使用什麼語言？** 建立試算表時，您可以使用任何語言或字元輸入使用者資料欄標籤，但不得變更範例所顯示的標籤順序。 然後您可以使用任何語言或字元將項目輸入到欄位中，並將檔案儲存為 Unicode 或 UTF-8 格式。 
    
- **如果我要新增不同國家或地區的使用者該怎麼辦？** 請為每一個地區分別建立一個試算表。 每一個試算表都要執行 [大量新增使用者精靈] 的所有步驟，讓您所用的檔案中，所有的使用者都具備單一位置。 
    
- **是否有字元數的使用上限？** 下表所列的是範例試算表中各使用者資料欄標籤及其字元數長度上限。 
    
|**使用者資料欄標籤**|**最大字元長度**|
|:-----|:-----|
|使用者 名稱 (必填)  <br/> |79，其中包含 name@domain 格式的 at 符號 ( @ \<extension\> ) 。 使用者的別名不得超過50個字元，功能變數名稱不得超過48個字元。  <br/> |
|名字  <br/> |64  <br/> |
|姓氏  <br/> |64  <br/> |
|顯示 名稱 (必填)  <br/> |256  <br/> |
|職稱  <br/> |64  <br/> |
|部門  <br/> |64  <br/> |
|辦公室號碼  <br/> |128  <br/> |
|辦公室電話  <br/> |64  <br/> |
|行動電話  <br/> |64  <br/> |
|傳真  <br/> |64  <br/> |
|地址  <br/> |1023  <br/> |
|城市  <br/> |128  <br/> |
|省/市  <br/> |128  <br/> |
|郵遞區號  <br/> |40  <br/> |
|國家/地區  <br/> |128  <br/> |
   
### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a>將使用者新增至 Microsoft 365 時仍然有問題嗎？

- **請仔細檢查試算表的格式是否正確。** 檢查欄標題，確認與樣本檔案中的標題相符。 務必遵循字元長度的規則，各欄位均以逗號隔開。 
    
- **如果您在 Microsoft 365 中看不到新的使用者，請稍候幾分鐘。** 您可能需要一點時間，才能讓變更移至 Microsoft 365 中的所有服務。 
    
## <a name="related-articles"></a>相關文章

[個別或大量將使用者新增至 Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/add-users)




