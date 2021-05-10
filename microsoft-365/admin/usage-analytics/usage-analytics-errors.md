---
title: 疑難排解 Microsoft 365 流量分析
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
ms.openlocfilehash: 74ee32ae015421a2352474daefa0eaa0a53fbbc9
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293732"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="8d2e3-103">疑難排解 Microsoft 365 流量分析</span><span class="sxs-lookup"><span data-stu-id="8d2e3-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="8d2e3-104">探索下列錯誤訊息清單，以取得 Microsoft 365 流量分析最常見的問題。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="8d2e3-105">我們無法處理您的要求。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-105">We are unable to process your request.</span></span> <span data-ttu-id="8d2e3-106">您必須先從 Microsoft 365 系統管理中心訂閱此資料</span><span class="sxs-lookup"><span data-stu-id="8d2e3-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="8d2e3-107">**錯誤碼：** 422</span><span class="sxs-lookup"><span data-stu-id="8d2e3-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="8d2e3-108">**您將在其中看到此訊息的位置：** 當您連線至 Microsoft 365 使用方式分析範本應用程式或直接呼叫 Microsoft 365 報告 APIs 時 Power BI。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="8d2e3-109">**原因：** 您必須先從 Microsoft 365 系統管理中心，訂閱資料，才可連線至應用程式。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="8d2e3-110">如果未先執行此步驟，則即使您提供 Microsoft 365 租使用者識別碼，也無法連線至範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="8d2e3-111">**若要修正此錯誤：** 若要訂閱資料，請移至 admin center \> **報告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用狀況</a>，並在主要儀表板頁面上尋找 Microsoft 365 流量分析磚。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="8d2e3-112">選取 [**開始** 使用] 按鈕，然後在開啟的 [**報告**] 窗格中，開啟和 **儲存** Power BI 設定的 **可用資料 Microsoft 365 流量分析**。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="8d2e3-113">我們正在處理您的資料</span><span class="sxs-lookup"><span data-stu-id="8d2e3-113">We are processing your data</span></span>

 <span data-ttu-id="8d2e3-114">**您將在其中看到此訊息的位置：** 在 Microsoft 365 系統管理中心的 [**使用狀況**] 儀表板上的 [ **Microsoft 365 流量分析**] 磚中。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="8d2e3-115">**原因：** 當您選擇從 Microsoft 365 系統管理中心 [查看範本應用程式中的資料](enable-usage-analytics.md)時，Microsoft 365 系統會開始產生您組織的歷史使用方式資料。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="8d2e3-116">視您的租用戶大小而定，此步驟可能需要 2 到 48 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="8d2e3-117">**若要修正此問題：** 請耐心等候，但如果在3天后，郵件未變更為 **您的資料**，請 [聯繫我們 Microsoft 365 以取得商務支援](../../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="8d2e3-p105">我們目前無法處理您的要求。我們仍在為您的組織準備資料</span><span class="sxs-lookup"><span data-stu-id="8d2e3-p105">We are unable to process your request at this time. We are still preparing the data for your organization</span></span>

 <span data-ttu-id="8d2e3-120">**錯誤碼：** 423</span><span class="sxs-lookup"><span data-stu-id="8d2e3-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="8d2e3-121">**您將在其中看到此訊息的位置：** 在 Power BI 中，當您連線至 Microsoft 365 使用方式分析範本應用程式或直接呼叫 Microsoft 365 報告 APIs 時。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="8d2e3-122">**原因：** 當您選擇從系統管理中心 [查看範本應用程式中的資料](enable-usage-analytics.md)時，Microsoft 365 系統會開始為您的組織產生歷史使用方式資料。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="8d2e3-123">根據租使用者的大小而定，此步驟可能需要兩個小時到48小時之間的任何時間。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="8d2e3-124">**若要修正此問題：** 請耐心等候，但如果從起始開始起，郵件未變更為 [**您的資料已經準備好** 3 天]，[請聯繫 Microsoft 365 以取得商務支援](../../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="8d2e3-125">您提供的租用戶識別碼格式錯誤</span><span class="sxs-lookup"><span data-stu-id="8d2e3-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="8d2e3-126">**錯誤碼：** 400</span><span class="sxs-lookup"><span data-stu-id="8d2e3-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="8d2e3-127">**您將在其中看到此訊息的位置：** 在 Power BI 中，當您連線至 Microsoft 365 使用方式分析範本應用程式或直接呼叫 Microsoft 365 報告 APIs 時。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="8d2e3-128">**原因：** 租使用者識別碼為 guid，且其格式必須為 xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx （xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx）。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="8d2e3-129">如果您在承租人輸入方塊中輸入任何其他字串，就會收到此錯誤。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="8d2e3-130">**若要修正此錯誤：** 移至 [系統管理中心] \> **報告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用狀況</a>，並在主要儀表板頁面上尋找 Microsoft 365 流量分析磚。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="8d2e3-131">租使用者識別碼會列在磚上。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="8d2e3-132">您可以從這裡複製並貼到對話方塊中，以連接至範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="8d2e3-133">我們的系統無法辨識您提供的租用戶識別碼</span><span class="sxs-lookup"><span data-stu-id="8d2e3-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="8d2e3-134">**錯誤碼：** 404</span><span class="sxs-lookup"><span data-stu-id="8d2e3-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="8d2e3-135">**您將在其中看到此訊息的位置：** 當您連線至 Microsoft 365 使用方式分析範本應用程式或直接呼叫 Microsoft 365 報告 APIs 時 Power BI。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="8d2e3-136">**原因：** 您提供的租使用者識別碼無效或不存在。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="8d2e3-137">**若要修正此錯誤：** 移至 [系統管理中心] \> **報告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用狀況</a>，並在主要儀表板頁面上尋找 Microsoft 365 流量分析磚。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="8d2e3-138">租使用者識別碼會列在磚上。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="8d2e3-139">您可以從這裡複製並貼到對話方塊中，以連接至範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="8d2e3-140">請重新輸入您的認證以再次登入 Power BI</span><span class="sxs-lookup"><span data-stu-id="8d2e3-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="8d2e3-141">錯誤碼︰302</span><span class="sxs-lookup"><span data-stu-id="8d2e3-141">Error Code: 302</span></span>
  
 <span data-ttu-id="8d2e3-142">**您將在其中看到此訊息的位置：** 當您連線至 Microsoft 365 使用方式分析範本應用程式或直接呼叫 Microsoft 365 報告 APIs 時 Power BI。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="8d2e3-143">**原因：** 授權碼失敗，可能需要您重新輸入認證。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="8d2e3-144">**若要修正此錯誤：** 登出 Power BI，然後再次登入。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="8d2e3-p110">您沒有存取此資料的正確授權。若要取得本服務資料的存取權，您需具備全域系統管理員或任何產品系統管理員的身分</span><span class="sxs-lookup"><span data-stu-id="8d2e3-p110">You do not have the right authorization to access to this data. To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="8d2e3-147">**錯誤碼：** 403</span><span class="sxs-lookup"><span data-stu-id="8d2e3-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="8d2e3-148">**您將在其中看到此訊息的位置：** 當您連線至 Microsoft 365 使用方式分析範本應用程式或直接呼叫 Microsoft 365 報告 APIs 時 Power BI。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="8d2e3-149">**原因：** 授權碼失敗，因為嘗試連線至範本應用程式的使用者不具備存取此資料的適當驗證層級。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="8d2e3-150">**若要修正此錯誤：** 提供 **全域管理員**、 **Exchange 系統管理員**、**商務用 Skype** 系統管理員、 **SharePoint** 系統管理員、**全域讀取器** 或 **報告讀取器** 的使用者認證，以連線至範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="8d2e3-151">如需詳細資訊，請參閱 [關於系統管理員角色](../add-users/about-admin-roles.md) 。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="8d2e3-152">重新整理失敗</span><span class="sxs-lookup"><span data-stu-id="8d2e3-152">Refresh failed</span></span>

 <span data-ttu-id="8d2e3-153">**您將在其中看到此訊息的位置：** 在重新整理歷程記錄中從 Power BI 或失敗的狀態傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="8d2e3-154">**原因：** 有時候會重設連接至範本應用程式之使用者的認證，而不會在範本應用程式的連接設定中更新，以導致使用者看到重新整理失敗的錯誤。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="8d2e3-155">**若要修正此錯誤：** 在 Power BI 中，尋找對應至 Microsoft 365 使用方式分析範本應用程式的資料集，選取 [**排程** 重新整理]，並提供您的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="8d2e3-156">如果這不起作用，請清除快取，然後重新建立範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="8d2e3-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
