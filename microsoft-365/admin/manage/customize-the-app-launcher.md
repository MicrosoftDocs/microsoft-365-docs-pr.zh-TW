---
title: 新增自訂磚至 App 啟動器
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 透過將自訂麻將牌新增至應用程式啟動器，建立電子郵件、檔、應用程式、SharePoint 網站、外部網站及其他資源的快速連結。
ms.openlocfilehash: 0f4141d08811847e8e27cf35975cfa6c6b1b1192
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393676"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>新增自訂磚至 App 啟動器

在 Microsoft 365 中，您可以使用 App 啟動器快速且輕鬆取得您的電子郵件、行事曆、檔及應用程式 ([深入瞭解](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)) 。 這些是您取得 Microsoft 365 的應用程式，以及您從[SharePoint 存放區](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43)或[Azure AD](/previous-versions/office/office-365-api/)新增的自訂應用程式。
  
您可以新增自己的自訂磚至應用程式啟動器，用來指向 SharePoint 網站、外部網站、舊版應用程式及其他項目。 自訂圖格會出現在應用程式啟動器的 **所有** 應用程式下方，但您可以將其固定至 **Home** 應用程式，並指示使用者執行相同的作業。 這麼一來，您就可以輕鬆尋找相關的網站、App 和資源來完成您的工作。 在下面這個範例中，名為「Contoso 入口網站」的磚，就是用來存取組織 SharePoint 內部網路網站的自訂磚。 
  
![應用程式啟動器](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>在 App 啟動器上新增自訂磚

1. 以全域系統管理員身分登入系統管理中心，移至 **設定**  >  的 **Org 設定**，然後選擇 [**組織設定檔**] 索引標籤。
    
2. 在 [ **組織設定檔** ] 索引標籤上，選擇 [ **自訂應用程式啟動器**]。
  
3. 選取 [ **新增自訂磚**]。 
  
4. 輸入新磚的 **麻將牌名稱** 。 磚中就會出現該名稱。 
    
5. 輸入麻將牌 **之網站的 URL** 。 當使用者選取應用程式啟動器上的麻將牌時，這是您想要的位置。 在 URL 中使用 HTTPS。

    > [!TIP]
    > 如果您要為 SharePoint 網站建立一個磚，請瀏覽至該網站、複製 URL，然後貼到這裡。 預設小組網站的 URL 看起來如下所示： `https://<company_name>.sharepoint.com` 
  
6. 輸入磚的 **影像 URL** 。 隨後影像就會出現在 [我的 App] 頁面和 App 啟動器上。

    > [!TIP]
    > 圖像應該是60x60 圖元，並可供組織中的每個人使用，而不需要驗證。

7. 輸入磚的 **描述** 。 當您在 [我的應用程式] 頁面上選取麻將牌並選取 [ **應用程式詳細資料**] 時，就會看到 
  
8. 選取 [ **儲存變更** ] 以建立自訂磚。 
    
    您的自訂圖格現在會出現在 [ **全部** ] 索引標籤上的應用程式啟動器中，以及您的使用者。 

    > [!NOTE]
    > 如果您在之前的步驟看不到已建立的 [自訂磚]，請確認 Exchange Online 信箱已指派給您，且至少登入您的信箱一次。 Microsoft 365 中的自訂圖格必須執行這些步驟。 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. 在系統管理中心中，移至 [**設定**  >  **Org 設定**  >  **組織設定檔**] 索引標籤。
    
2. 在 [ **組織設定檔** ] 頁面上，按一下 [   **新增組織的自訂麻將牌**] 旁邊的 [ **編輯**]。

3. 更新自訂磚的 **麻將牌名稱**、 **URL**、 **描述** 或 **影像 URL** (請參閱 [將自訂磚新增至應用程式啟動器](#add-a-custom-tile-to-the-app-launcher)) 。
    
4. 選取 [ **更新** \> **關閉**]。 
    
若要刪除自訂磚，請從 [**自訂磚**] 視窗中選取拼貼，選取 [**移除磚**  >  **刪除**]。 
  
## <a name="next-steps"></a>後續步驟

除了將磚新增至應用程式啟動器之外，您還可以將應用程式啟動器磚新增至導覽列 ([深入瞭解](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)) 。 若要自訂 Microsoft 365 的外觀與風格，以符合組織的品牌，請參閱[自訂 Microsoft 365 主題](../setup/customize-your-organization-theme.md)。

## <a name="related-content"></a>相關內容

[將應用程式固定至使用者的應用程式啟動器](pin-apps-to-app-launcher.md) (文章) \
[將您的商務使用者 Microsoft 365 升級至最新的 Office 用戶端](../setup/upgrade-users-to-latest-office-client.md) (文章) \
[在系統管理中心管理增益集](../manage/manage-addins-in-the-admin-center.md) (文章) 
