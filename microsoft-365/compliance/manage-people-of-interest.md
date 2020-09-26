---
title: '管理資料調查中感興趣的人員 (預覽) '
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
description: 瞭解如何管理關注搜尋範圍或查看其資訊的人員，例如連絡人、位置及活動記錄。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 58c590b2d72d7eb265dd4f90679effb7cdf68f79
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285579"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a>管理資料調查中感興趣的人員 (預覽) 

資料調查常常會包含感興趣的人員。 通常，他們是擁有您正在調查或想要補救之誤寫、機密或惡意資料的人員。 在 [ **資料調查 (預覽) **] 中，您可以新增它們，以探索用於限定搜尋範圍的資料來源或查看其他資訊，例如連絡人、位置及活動記錄。 


## <a name="add-people-of-interest"></a>新增感興趣的人員

在 [ **興趣人** ] 索引標籤中，您可以新增感興趣的人員，並探索其資料來源，例如可用於限定搜尋範圍的 Exchange 信箱或商務網站 OneDrive。 依興趣的人員劃分範圍時，搜尋會變得更高的性能及準確性，因為此工具會 reprocesses 任何未編制索引的資料，例如影像或不受支援的檔案類型。 您也可以查看其連絡人資訊、位置資訊和活動記錄，您可以用來發起通訊或進一步調查其活動。 

若要新增調查的興趣人員：

1. 從 [ **資料調查 (預覽) ** ] 頁面上，移至您的調查。
 
2. 選取調查後，請移至 [ **興趣人員** ] 索引標籤，然後按一下 [ **新增感興趣的人員**]。 
 
3. 選擇您想要新增至調查的人員。 您可以從輸入搜尋並選取您組織的 Azure Active Directory 中的使用者。
 
4. 完成感興趣的人員清單後，請按 **[下一步]** 以對應其資料來源。 

5. 選針對每位人員，選取 [ **Exchange** ] 以新增人員的主要 Exchange 信箱，並 **OneDrive** 新增人員的主要 OneDrive 的商務網站。

6. 選按 **[下一步]** ，新增您要與感興趣的人員產生關聯的任何其他資料來源。

7. 選選取 [ **更新** ]，將內容位置（例如信箱、網站及小組）指派給人員。 

8. 選在浮出控制項中：
   
    -  **Exchange 信箱** -按一下 **[選擇使用者、群組或小組** ]，然後再按一下 **[選擇使用者、群組或小組** ]。 若要新增更多信箱，請使用搜尋方塊尋找使用者信箱和通訊群組。 您也可以新增用來儲存 Microsoft 365 群組或 Microsoft 小組資訊的信箱。 選取 [使用者、群組、小組] 核取方塊，按一下 **[選擇**]，然後按一下 [ **完成**]。

        > [!NOTE]
        > 當您按一下 [選擇使用者、群組或小組以指定信箱] 時，顯示的信箱選擇器會是空的。 這項設計的目的是提升效能。 若要將人員新增至此清單，請在搜尋方塊中輸入 (至少3個字元) 名稱。
     
     - **SharePoint 網站** -按一下 **[選擇網站** ]，然後按一下 **[選擇網站** ]，以指定您要新增至人員的商務網站的其他 SharePoint 和 OneDrive。 您也可以為 Microsoft 365 群組或 Microsoft 團隊新增 SharePoint 網站的 URL。 輸入每個要指派之網站的 URL。 按一下 **[選擇**]，然後按一下 [ **完成**]。
     - **Microsoft 小組** –按一下 **[選擇小組** ]，然後按一下 **[選擇小組** ]，以查看人員目前隸屬的 Microsoft 小組群組清單。 選取您要新增至人員的團隊。 選取之後，系統會自動識別 & 選取相關聯的 SharePoint 網站與該 Microsoft 團隊相關聯的群組信箱。 按一下 **[選擇**]，然後按一下 [ **完成**]。
        
      > [!NOTE]
      > 若要新增其他 Microsoft 團隊，您必須以上述方式個別新增信箱和 SharePoint 網站。

完成將資料來源對應給感興趣的人員之後，您可以看到您剛新增的信箱、網站和團隊總數摘要。 如果您將任何其他資料來源對應到感興趣的人員，並將您的搜尋範圍限定在調查中，請將檔對應到其關注的利益人，這樣就能更輕鬆地組織證據或產生報表的相關人員。 

## <a name="view-additional-people-of-interest-information"></a>查看其他感興趣資訊的人員

在 [ **興趣人** ] 索引標籤中，按一下您新增的人員。 在飛入的視窗中，您將會看到：

- 連絡人資訊

  - **顯示名稱**：顯示在通訊錄中的人員名稱。 這通常是名字、中間名首字母和姓氏的組合。
  - **Mail/SMTP**：人員的 SMTP 位址，例如，jeff@contoso.onmicrosoft.com。  
  - **職稱**：職稱。
  - **部門**：人員在其中運作之部門的名稱。
  - **管理員**：人員的主管。 管理員接收此人員的任何升級通訊。
  
- 位置資訊

  - **City**：人員所在的城市。
  - **州**：人員所在的省或市。
  - **國家/地區**：人員所在的國家/地區;例如 "US" 或 "UK"。
  - **Office**：人員的辦公室地點。

- 處理狀態

  - **索引狀態**：深入索引資料來源的狀態
  - **索引上次更新時間**：上次觸發深層索引工作的時間戳記。
  - **資料來源**：顯示對應至人員的信箱、網站及小組計數

- 更新索引
    - 您可以將此人的資料來源重新編制索引。 

- View activity 

    - 您可以查看和搜尋使用者的活動記錄。 如需詳細資訊，請參閱 [View 計息人員活動](view-people-of-interest-activity.md) 
