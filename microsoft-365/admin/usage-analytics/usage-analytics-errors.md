---
title: Microsoft 365 流量分析疑難排解
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: 瞭解如何疑難排解 Microsoft 365 使用方式分析範本應用程式的問題。
ms.openlocfilehash: bf8e4ece7b1e310d91f418f5388cae9aa27f2aa7
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841432"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Microsoft 365 流量分析疑難排解

探索下列錯誤訊息清單，以取得 Microsoft 365 流量分析最常見的問題。
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>我們無法處理您的要求。 您必須先從 Microsoft 365 系統管理中心訂閱此資料

 **錯誤碼：** 422 
  
 **您將在其中看到此訊息的位置：** 當您連線至 Microsoft 365 使用方式分析範本應用程式或直接呼叫 Microsoft 365 報告 APIs 時，在 Power BI 中。 
  
 **原因：** 在您可以連線至應用程式之前，您必須訂閱 Microsoft 365 系統管理中心中的資料。 若未執行此步驟，則即使您提供 Microsoft 365 租使用者識別碼，也無法連線至範本應用程式。 
  
 **若要修正此錯誤：** 若要訂閱資料，請移至 [系統管理中心] \> **報告** 的 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用狀況</a> ，並在主要儀表板頁面上找到 [Microsoft 365 流量分析] 磚。 選取 [ **開始** 使用] 按鈕，然後在所開啟的 [ **報告** ] 窗格中，開啟 [ **讓資料可365用於 Power BI 的流量分析** ] 設定及 [ **儲存** ]。
  
## <a name="we-are-processing-your-data"></a>我們正在處理您的資料

 **您將在其中看到此訊息的位置：** 在 Microsoft 365 系統管理中心的 [ **使用狀況** ] 儀表板上的 [ **microsoft 365 流量分析** ] 磚中。 
  
 **原因：** 當您選擇從 Microsoft 365 系統管理中心 [查看範本應用程式中的資料](enable-usage-analytics.md) 時，Microsoft 365 系統會開始為您的組織產生歷史使用方式資料。 視您的租用戶大小而定，此步驟可能需要 2 到 48 個小時才能完成。 
  
 **若要修正此問題：** 請耐心等候，但如果在3天后，郵件未變更為 **您的資料** ，請 [與 Microsoft 365 聯繫以取得商務支援](../contact-support-for-business-products.md)。
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>我們目前無法處理您的要求。 我們仍在為您的組織準備資料

 **錯誤碼：** 423 
  
 **您將在其中看到此訊息的位置：** 在 Power BI 中，當您連接至 Microsoft 365 使用方式分析範本應用程式或直接呼叫 Microsoft 365 報告 APIs。 
  
 **原因：** 當您選擇從系統管理中心 [查看範本應用程式中的資料](enable-usage-analytics.md) 時，Microsoft 365 系統就會開始產生您組織的歷史使用方式資料。 根據租使用者的大小而定，此步驟可能需要兩個小時到48小時之間的任何時間。 
  
 **若要修正此問題：** 請耐心等候，但如果自啟動以來，郵件未變更為 **您的資料已準備好** ，請 [與 Microsoft 365 聯繫以取得商務服務支援](../contact-support-for-business-products.md)。
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>您提供的租用戶識別碼格式錯誤

 **錯誤碼：** 400 
  
 **您將在其中看到此訊息的位置：** 在 Power BI 中，當您連接至 Microsoft 365 使用方式分析範本應用程式或直接呼叫 Microsoft 365 報告 APIs。 
  
 **原因：** 租使用者識別碼為 guid，且其格式必須為 xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx （xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx）。 如果您在承租人輸入方塊中輸入任何其他字串，就會收到此錯誤。 
  
 **若要修正此錯誤：** 移至 [系統管理中心] \> **報告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用狀況</a> ，並在主要儀表板頁面上找到 [Microsoft 365 流量分析] 磚。 租使用者識別碼會列在磚上。 您可以從這裡複製並貼到對話方塊中，以連接至範本應用程式。 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>我們的系統無法辨識您提供的租用戶識別碼

 **錯誤碼：** 404 
  
 **您將在其中看到此訊息的位置：** 當您連線至 Microsoft 365 使用方式分析範本應用程式或直接呼叫 Microsoft 365 報告 APIs 時，在 Power BI 中。 
  
 **原因：** 您提供的租使用者識別碼無效或不存在。 
  
 **若要修正此錯誤：** 移至 [系統管理中心] \> **報告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用狀況</a> ，並在主要儀表板頁面上找到 [Microsoft 365 流量分析] 磚。 租使用者識別碼會列在磚上。 您可以從這裡複製並貼到對話方塊中，以連接至範本應用程式。 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>請重新輸入您的認證以再次登入 Power BI

錯誤碼︰302
  
 **您將在其中看到此訊息的位置：** 當您連線至 Microsoft 365 使用方式分析範本應用程式或直接呼叫 Microsoft 365 報告 APIs 時，在 Power BI 中。 
  
 **原因：** 授權碼失敗，可能需要您重新輸入認證。 
  
 **若要修正此錯誤：** 登出 Power BI，然後再次登入。 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>您沒有存取此資料的正確授權。 若要取得本服務資料的存取權，您需具備全域系統管理員或任何產品系統管理員的身分

 **錯誤碼：** 403 
  
 **您將在其中看到此訊息的位置：** 當您連線至 Microsoft 365 使用方式分析範本應用程式或直接呼叫 Microsoft 365 報告 APIs 時，在 Power BI 中。 
  
 **原因：** 授權碼失敗，因為嘗試連線至範本應用程式的使用者不具備存取此資料的適當驗證層級。 
  
 **若要修正此錯誤：** 提供 **全域系統管理員** 、 **Exchange 系統管理員** 、商務用 **Skype** 系統管理員、SharePoint 系統 **管理員** 、 **全域讀取器** 或 **報告讀取器** 的使用者認證，以連接至範本應用程式。 如需詳細資訊，請參閱 [關於系統管理員角色](../add-users/about-admin-roles.md) 。 
  
## <a name="refresh-failed"></a>重新整理失敗

 **您將在其中看到此訊息的位置：** 在重新整理歷程記錄中從 Power BI 或 failed 狀態傳送電子郵件。 
  
 **原因：** 有時候會重設連接至範本應用程式之使用者的認證，而不會在範本應用程式的連接設定中更新，以導致使用者看到重新整理失敗的錯誤。 
  
 **若要修正此錯誤：** 在 [Power BI] 中，找到對應至 Microsoft 365 使用方式分析範本應用程式的資料集，選取 [ **排程** 重新整理]，並提供您的系統管理員認證。 
  
如果這不起作用，請清除快取，然後重新建立範本應用程式。
  
  
