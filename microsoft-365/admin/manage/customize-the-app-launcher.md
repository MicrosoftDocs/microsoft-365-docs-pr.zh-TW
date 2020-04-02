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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: '透過將自訂麻將牌新增至應用程式啟動器，建立電子郵件、檔、應用程式、SharePoint 網站、外部網站及其他資源的快速連結。 '
ms.openlocfilehash: e52bad5cdd1809e8aa0d97c681b69daa5143d3fd
ms.sourcegitcommit: 4b73f070747a66874c03fdf670ffdf16f736585a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2020
ms.locfileid: "43103072"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>新增自訂磚至 App 啟動器

在 Office 365 中使用 Office 365 App 啟動器，可讓您輕鬆快速地存取電子郵件、行事曆、文件和 App ([深入了解](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx))。這些是 Office 365 中提供給您的 App，以及您從 [SharePoint 市集](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx)或 [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher) 新增的自訂 App。
  
您還可以在 App 啟動器上，加入自己的自訂磚，讓它們指向 SharePoint 網站、外部網站、舊版 App 等。 自訂圖格會出現在應用程式啟動器的**所有**應用程式下方，但您可以將其固定至**Home**應用程式，並指示使用者執行相同的作業。 這麼一來，您就可以輕鬆尋找相關的網站、App 和資源來完成您的工作。 在下面這個範例中，名為「Contoso 入口網站」的磚，就是用來存取組織 SharePoint 內部網路網站的自訂磚。 
  
![Office 365 應用程式啟動器](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>在 App 啟動器上新增自訂磚

1. 在系統管理中心中，移至 [**設定** > ]**[設定]，然後選擇**[**組織設定檔**] 索引標籤。
    
2. 在 [**組織設定檔**] 索引標籤上，選擇 [**自訂應用程式啟動器**]。
  
3. 選取 [**新增自訂磚**]。 
  
4. 輸入新磚的**麻將牌名稱**。 磚中就會出現該名稱。 
    
5. 輸入麻將牌**之網站的 URL** 。 當使用者選取應用程式啟動器上的麻將牌時，這是您想要的位置。 在 URL 中使用 HTTPS。<br/>提示：如果您要為 SharePoint 網站建立磚，請流覽至該網站，複製 URL，然後貼到這裡。 預設小組網站的 URL 看起來如下所示：`https://<company_name>.sharepoint.com` 
  
6. 輸入磚的**影像 URL** 。 隨後影像就會出現在 [我的 App] 頁面和 App 啟動器上。<br/>提示：影像應該是60x60 圖元，並可供組織中的所有人使用，而不需要驗證。

7. 輸入磚的**描述**。 當您在 [我的應用程式] 頁面上選取麻將牌並選取 [**應用程式詳細資料**] 時，就會看到 
  
8. 選取 [**儲存變更**] 以建立自訂磚。 
    
您的自訂圖格現在會出現在 [**全部**] 索引標籤上的應用程式啟動器中，以及您的使用者。 
  
## <a name="promote-the-tile-to-app-launcher"></a>將磚提升至應用程式啟動器

1. 選取應用程式啟動器圖示，然後選取 [**所有應用程式**]。 
    
2. 尋找應用程式的新麻將牌，選取省略號，然後選擇 [**固定至啟動器**]。
  
    > [!NOTE]
    > 如果您在之前的步驟看不到已建立的 [自訂磚]，請確認 Exchange Online 信箱已指派給您，且至少登入您的信箱一次。這些是在 Office 365 中自訂磚時的必要步驟。 
  
> [!IMPORTANT]
> 您和您的使用者都必須執行這些步驟，才能將自訂磚從 [我的 App] 頁面升階到 App 啟動器。 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. 在系統管理中心中，移至 [**設定** > **Settings** > ] [<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">組織設定檔</a>] 索引標籤。
    
2. 在 [**組織設定檔**] 頁面上，按一下 [**新增組織的自訂麻將牌**] 旁邊的 [**編輯**]。

3. 更新自訂磚的**麻將牌名稱**、 **URL**、**描述**或**影像 URL** （請參閱[Add a custom 磚 to the app 啟動器](#add-a-custom-tile-to-the-app-launcher)）。
    
4. 選取 [**更新** \> **關閉**]。 
    
若要刪除自訂磚，請從 [**自訂磚**] 視窗中選取拼貼，選取 [**移除磚** > **刪除**]。 
  
## <a name="whats-next"></a>下一步是什麼？

除了在 App 啟動器中新增磚之外，您還可以在 Office 365 導覽列中，新增 App 啟動器磚 ([深入了解](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx))。若要配合貴組織的品牌，自訂 Office 365 的外觀與風格，請參閱[自訂 Office 365 佈景主題](../setup/customize-your-organization-theme.md)。
  

