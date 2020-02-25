---
title: 疑難排解 Microsoft 365 使用情況分析
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
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
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: 了解如何透過 Microsoft 365 使用情況分析範本應用程式的問題進行疑難排解。
ms.openlocfilehash: a9da79a6d7760f7876de7a6321554545d411f6be
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240402"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>疑難排解 Microsoft 365 使用情況分析

探索下列錯誤訊息，以取得協助 Microsoft 365 使用情況分析最常見的問題清單。
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>我們無法處理您的要求。 您必須先從 Microsoft 365 系統管理中心訂閱此資料

 **錯誤的程式碼：** 422 
  
 **您將在其中看到這個訊息：** 當您連線至 Microsoft 365 使用情況分析範本應用程式，或直接呼叫 Microsoft 365 報告 Api 時，出現 Power bi。 
  
 **原因：** 您可以連線至應用程式之前您必須從 Microsoft 365 系統管理中心訂閱此資料。 如果未先完成此步驟，您無法連線至範本應用程式，即使您提供您的 Microsoft 365 租用戶識別碼。 
  
 **若要修正此錯誤：** 若要訂閱的資料，請前往 [系統管理中心\>**報告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">流量</a>並找出分析並排顯示在主儀表板] 頁面上的 Microsoft 365 使用情況。 選取 [**開始**] 按鈕，然後在開啟 [**報告**] 窗格中，開啟 [**使資料可用來 Power bi 的 Microsoft 365 使用情況分析**設定並**儲存**。
  
## <a name="we-are-processing-your-data"></a>我們正在處理您的資料

 **您將在其中看到這個訊息：** 在 Microsoft 365 系統管理中心中的**使用狀況**儀表板上的 [ **Microsoft 365 使用情況分析**] 磚。 
  
 **原因：** 當您從 Microsoft 365 系統管理員的 [[選擇範本應用程式中的文件都看到資料](enable-usage-analytics.md)中心時，Microsoft 365 系統就會開始產生歷來使用狀況資料，為您的組織。 視您的租用戶大小而定，此步驟可能需要 2 到 48 個小時才能完成。 
  
 **若要修正此問題：** 只耐心等候，但如果郵件不會變更至**您的資料已經準備好**3 天後，[請連絡 Microsoft 365 商務版支援人員](../contact-support-for-business-products.md)。
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>我們目前無法處理您的要求。 我們仍在為您的組織準備資料

 **錯誤的程式碼：** 423 
  
 **您將在其中看到這個訊息：** 當您連線至 Microsoft 365 使用情況分析範本應用程式，或直接呼叫 Microsoft 365 報告 Api 時，出現 Power bi。 
  
 **原因：** 當您從系統管理員的 [[選擇範本應用程式中的文件都看到資料](enable-usage-analytics.md)中心時，Microsoft 365 系統就會開始產生歷來使用狀況資料，為您的組織。 視您的租用戶大小而定，此步驟可能需要 2 到 48 個小時才能完成。 
  
 **若要修正此問題：** 只耐心等候，但如果郵件不會變更至**您的資料已經準備好**即使後 3 天，[請連絡 Microsoft 365 商務版支援人員](../contact-support-for-business-products.md)。
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>您提供的租用戶識別碼格式錯誤

 **錯誤的程式碼：** 400 
  
 **您將在其中看到這個訊息：** 當您連線至 Microsoft 365 使用情況分析範本應用程式，或直接呼叫 Microsoft 365 報告 Api 時，出現 Power bi。 
  
 **原因：** 租用戶識別碼是 guid，且位於 xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx 的格式。 如果您在租用戶輸入方塊中輸入任何其他字串，就會收到這則錯誤訊息。 
  
 **若要修正此錯誤：** 移至系統管理中心 [ \> **報告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">流量</a>並找出分析並排顯示在主儀表板] 頁面上的 Microsoft 365 使用情況。 租用戶識別碼會列在磚當中。 您可以從這裡複製並將它貼在連接到該範本應用程式] 對話方塊。 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>我們的系統無法辨識您提供的租用戶識別碼

 **錯誤的程式碼：** 404 
  
 **您將在其中看到這個訊息：** 當您連線至 Microsoft 365 使用情況分析範本應用程式，或直接呼叫 Microsoft 365 報告 Api 時，出現 Power bi。 
  
 **原因：** 您所提供的租用戶識別碼不正確或不存在。 
  
 **若要修正此錯誤：** 移至系統管理中心 [ \> **報告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">流量</a>並找出分析並排顯示在主儀表板] 頁面上的 Microsoft 365 使用情況。 租用戶識別碼會列在磚當中。 您可以從這裡複製並將它貼在連接到該範本應用程式] 對話方塊。 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>請重新輸入您的認證以再次登入 Power BI

錯誤碼︰302
  
 **您將在其中看到這個訊息：** 當您連線至 Microsoft 365 使用情況分析範本應用程式，或直接呼叫 Microsoft 365 報告 Api 時，出現 Power bi。 
  
 **原因：** 授權程式碼失敗，且可能需要您再次輸入認證。 
  
 **若要修正此錯誤：** 登出 Power BI，然後再次登入。 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>您沒有存取此資料的正確授權。 若要取得本服務資料的存取權，您需具備全域系統管理員或任何產品系統管理員的身分

 **錯誤的程式碼：** 403 
  
 **您將在其中看到這個訊息：** 當您連線至 Microsoft 365 使用情況分析範本應用程式，或直接呼叫 Microsoft 365 報告 Api 時，出現 Power bi。 
  
 **原因：** 授權程式碼失敗，因為嘗試連線至範本應用程式的使用者沒有授權，才能存取此資料的權限層級。 
  
 **若要修正此錯誤：** 提供是**全域系統管理員**、 **Exchange 系統管理員**、**商務系統的商務用 Skype**、 **SharePoint 系統管理員**、**全域讀者**或**報告讀取者**連線至範本應用程式的使用者的認證。 如需詳細資訊，請參閱[關於系統管理員角色](../add-users/about-admin-roles.md)。 
  
## <a name="refresh-failed"></a>重新整理失敗

 **您將在其中看到這個訊息：** 電子郵件從 Power BI 或重新整理歷程記錄中的失敗的狀態。 
  
 **原因：** 有時連接至範本應用程式之使用者的認證重設，且不會導致使用者看到的範本應用程式的連線設定中更新重新整理失敗錯誤。 
  
 **若要修正此錯誤：** Power BI 中尋找對應至 Microsoft 365 使用情況分析範本應用程式的資料集、 選取**排程重新整理**並提供您的系統管理員認證。 
  
如果還是沒有用，清除快取，然後重新建立該範本應用程式。
  
  
