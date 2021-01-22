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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: '新增自訂磚至應用程式啟動器，以建立電子郵件、檔、App、SharePoint 網站、外部網站及其他資源的快速連結。 '
ms.openlocfilehash: 2bbcf64b807754aed199c441f6df028d5fe20a97
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926231"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>新增自訂磚至 App 啟動器

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end

在 Microsoft 365 中，您可以使用應用程式啟動器快速且輕鬆地取得您的電子郵件、月曆、檔和應用程式， ([深入瞭解) 。](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) 這些是您從 Microsoft 365 取得的應用程式，以及您從 [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) 或 [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)新增的自訂應用程式。
  
您可以新增自己的自訂磚至應用程式啟動器，用來指向 SharePoint 網站、外部網站、舊版應用程式及其他項目。 自訂磚會出現在應用程式啟動器的所有 App下，但您可以將它釘釘到家用App，並指示使用者執行相同的操作。 這麼一來，您就可以輕鬆尋找相關的網站、App 和資源來完成您的工作。 在下面這個範例中，名為「Contoso 入口網站」的磚，就是用來存取組織 SharePoint 內部網路網站的自訂磚。 
  
![應用程式啟動器](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>在 App 啟動器上新增自訂磚

1. 以全域管理員的名列號到系統管理中心，前往設定  >  **組織設定**，然後選擇組織 **設定檔的 Tab。**
    
2. 在組織 **設定檔的 Tab** 上，選擇 **自訂應用程式啟動器磚**。
  
3. 選取 **新增自訂磚**。 
  
4. 輸入新 **磚** 的磚名稱。 磚中就會出現該名稱。 
    
5. 輸入 **磚的網站** URL。 這是當使用者選取 App 啟動器上的磚時，您希望使用者前往的位置。 在 URL 使用 HTTPS。<br/>提示：如果您要為 SharePoint 網站建立磚，請流覽至該網站、複製 URL，然後貼到這裡。 預設小組網站的 URL 看起來像這樣： `https://<company_name>.sharepoint.com` 
  
6. 輸入 **磚影像** 的 URL。 隨後影像就會出現在 [我的 App] 頁面和 App 啟動器上。<br/>提示：影像大小應為 60x60 圖元，且可供貴組織中所有人使用，而不需要驗證。

7. 輸入 **磚** 的描述。 當您選取我的應用程式頁面上的磚，然後選取應用程式詳細資料時，會看到 **這一點**。 
  
8. 選取 **儲存變更** 以建立自訂磚。 
    
您的自訂磚現在會顯示在 App 啟動器中的您和使用者。 
  
## <a name="promote-the-tile-to-app-launcher"></a>將磚升上應用程式啟動器

1. 選取應用程式啟動器圖示，然後選取所有 **應用程式**。 
    
2. 找出應用程式的新磚，選取省略號，然後選擇釘 **選到啟動器**。
  
    > [!NOTE]
    > 如果您在之前的步驟看不到已建立的 [自訂磚]，請確認 Exchange Online 信箱已指派給您，且至少登入您的信箱一次。 這些步驟是 Microsoft 365 中自訂磚的必填步驟。 
  
> [!IMPORTANT]
> 您和您的使用者都必須執行這些步驟，才能將自訂磚從 [我的 App] 頁面升階到 App 啟動器。 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. 在系統管理中心中，前往設定  >  **組織設定**  >  **組織設定檔的 Tab。** </a>
    
2. 在組織 **設定檔頁面面上**，選取貴組織自訂 **磚** 旁 **的編輯。**

3. 更新自訂 **磚** 的磚名稱 **、URL、** 描述或影像 **URL** [ (請參閱在](#add-a-custom-tile-to-the-app-launcher)應用程式啟動器中新增自訂磚) 。 
    
4. 選取 **更新** \> **關閉**。 
    
若要刪除自訂磚，請從自訂磚視窗中選取該磚，然後選取移除 **磚**  >  **Delete。** 
  
## <a name="whats-next"></a>下一步是什麼？

除了在應用程式啟動器中新增磚，您還可以在流覽工具列中新增應用程式啟動器磚， ([進](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985) 一) 。 若要配合貴組織的品牌來自訂 Microsoft 365 的外觀與感覺，請參閱自訂 [Microsoft 365 主題](../setup/customize-your-organization-theme.md)。
  
