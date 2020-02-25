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
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="5fcb0-103">疑難排解 Microsoft 365 使用情況分析</span><span class="sxs-lookup"><span data-stu-id="5fcb0-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="5fcb0-104">探索下列錯誤訊息，以取得協助 Microsoft 365 使用情況分析最常見的問題清單。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="5fcb0-105">我們無法處理您的要求。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-105">We are unable to process your request.</span></span> <span data-ttu-id="5fcb0-106">您必須先從 Microsoft 365 系統管理中心訂閱此資料</span><span class="sxs-lookup"><span data-stu-id="5fcb0-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="5fcb0-107">**錯誤的程式碼：** 422</span><span class="sxs-lookup"><span data-stu-id="5fcb0-107">**Error Code :** 422</span></span> 
  
 <span data-ttu-id="5fcb0-108">**您將在其中看到這個訊息：** 當您連線至 Microsoft 365 使用情況分析範本應用程式，或直接呼叫 Microsoft 365 報告 Api 時，出現 Power bi。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="5fcb0-109">**原因：** 您可以連線至應用程式之前您必須從 Microsoft 365 系統管理中心訂閱此資料。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-109">**Cause:** Before you can connect to the app you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="5fcb0-110">如果未先完成此步驟，您無法連線至範本應用程式，即使您提供您的 Microsoft 365 租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant id.</span></span> 
  
 <span data-ttu-id="5fcb0-111">**若要修正此錯誤：** 若要訂閱的資料，請前往 [系統管理中心\>**報告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">流量</a>並找出分析並排顯示在主儀表板] 頁面上的 Microsoft 365 使用情況。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="5fcb0-112">選取 [**開始**] 按鈕，然後在開啟 [**報告**] 窗格中，開啟 [**使資料可用來 Power bi 的 Microsoft 365 使用情況分析**設定並**儲存**。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="5fcb0-113">我們正在處理您的資料</span><span class="sxs-lookup"><span data-stu-id="5fcb0-113">We are processing your data</span></span>

 <span data-ttu-id="5fcb0-114">**您將在其中看到這個訊息：** 在 Microsoft 365 系統管理中心中的**使用狀況**儀表板上的 [ **Microsoft 365 使用情況分析**] 磚。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="5fcb0-115">**原因：** 當您從 Microsoft 365 系統管理員的 [[選擇範本應用程式中的文件都看到資料](enable-usage-analytics.md)中心時，Microsoft 365 系統就會開始產生歷來使用狀況資料，為您的組織。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="5fcb0-116">視您的租用戶大小而定，此步驟可能需要 2 到 48 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="5fcb0-117">**若要修正此問題：** 只耐心等候，但如果郵件不會變更至**您的資料已經準備好**3 天後，[請連絡 Microsoft 365 商務版支援人員](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="5fcb0-118">我們目前無法處理您的要求。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="5fcb0-119">我們仍在為您的組織準備資料</span><span class="sxs-lookup"><span data-stu-id="5fcb0-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="5fcb0-120">**錯誤的程式碼：** 423</span><span class="sxs-lookup"><span data-stu-id="5fcb0-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="5fcb0-121">**您將在其中看到這個訊息：** 當您連線至 Microsoft 365 使用情況分析範本應用程式，或直接呼叫 Microsoft 365 報告 Api 時，出現 Power bi。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-121">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="5fcb0-122">**原因：** 當您從系統管理員的 [[選擇範本應用程式中的文件都看到資料](enable-usage-analytics.md)中心時，Microsoft 365 系統就會開始產生歷來使用狀況資料，為您的組織。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="5fcb0-123">視您的租用戶大小而定，此步驟可能需要 2 到 48 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-123">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="5fcb0-124">**若要修正此問題：** 只耐心等候，但如果郵件不會變更至**您的資料已經準備好**即使後 3 天，[請連絡 Microsoft 365 商務版支援人員](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="5fcb0-125">您提供的租用戶識別碼格式錯誤</span><span class="sxs-lookup"><span data-stu-id="5fcb0-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="5fcb0-126">**錯誤的程式碼：** 400</span><span class="sxs-lookup"><span data-stu-id="5fcb0-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="5fcb0-127">**您將在其中看到這個訊息：** 當您連線至 Microsoft 365 使用情況分析範本應用程式，或直接呼叫 Microsoft 365 報告 Api 時，出現 Power bi。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-127">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="5fcb0-128">**原因：** 租用戶識別碼是 guid，且位於 xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx 的格式。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-128">**Cause:** The tenant id is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="5fcb0-129">如果您在租用戶輸入方塊中輸入任何其他字串，就會收到這則錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-129">If you enter any other string in the tenant input box you will get this error.</span></span> 
  
 <span data-ttu-id="5fcb0-130">**若要修正此錯誤：** 移至系統管理中心 [ \> **報告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">流量</a>並找出分析並排顯示在主儀表板] 頁面上的 Microsoft 365 使用情況。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="5fcb0-131">租用戶識別碼會列在磚當中。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-131">The tenant id is listed on the tile.</span></span> <span data-ttu-id="5fcb0-132">您可以從這裡複製並將它貼在連接到該範本應用程式] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="5fcb0-133">我們的系統無法辨識您提供的租用戶識別碼</span><span class="sxs-lookup"><span data-stu-id="5fcb0-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="5fcb0-134">**錯誤的程式碼：** 404</span><span class="sxs-lookup"><span data-stu-id="5fcb0-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="5fcb0-135">**您將在其中看到這個訊息：** 當您連線至 Microsoft 365 使用情況分析範本應用程式，或直接呼叫 Microsoft 365 報告 Api 時，出現 Power bi。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="5fcb0-136">**原因：** 您所提供的租用戶識別碼不正確或不存在。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-136">**Cause:** The tenant id you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="5fcb0-137">**若要修正此錯誤：** 移至系統管理中心 [ \> **報告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">流量</a>並找出分析並排顯示在主儀表板] 頁面上的 Microsoft 365 使用情況。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="5fcb0-138">租用戶識別碼會列在磚當中。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-138">The tenant id is listed on the tile.</span></span> <span data-ttu-id="5fcb0-139">您可以從這裡複製並將它貼在連接到該範本應用程式] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="5fcb0-140">請重新輸入您的認證以再次登入 Power BI</span><span class="sxs-lookup"><span data-stu-id="5fcb0-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="5fcb0-141">錯誤碼︰302</span><span class="sxs-lookup"><span data-stu-id="5fcb0-141">Error Code: 302</span></span>
  
 <span data-ttu-id="5fcb0-142">**您將在其中看到這個訊息：** 當您連線至 Microsoft 365 使用情況分析範本應用程式，或直接呼叫 Microsoft 365 報告 Api 時，出現 Power bi。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="5fcb0-143">**原因：** 授權程式碼失敗，且可能需要您再次輸入認證。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="5fcb0-144">**若要修正此錯誤：** 登出 Power BI，然後再次登入。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="5fcb0-145">您沒有存取此資料的正確授權。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="5fcb0-146">若要取得本服務資料的存取權，您需具備全域系統管理員或任何產品系統管理員的身分</span><span class="sxs-lookup"><span data-stu-id="5fcb0-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="5fcb0-147">**錯誤的程式碼：** 403</span><span class="sxs-lookup"><span data-stu-id="5fcb0-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="5fcb0-148">**您將在其中看到這個訊息：** 當您連線至 Microsoft 365 使用情況分析範本應用程式，或直接呼叫 Microsoft 365 報告 Api 時，出現 Power bi。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="5fcb0-149">**原因：** 授權程式碼失敗，因為嘗試連線至範本應用程式的使用者沒有授權，才能存取此資料的權限層級。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="5fcb0-150">**若要修正此錯誤：** 提供是**全域系統管理員**、 **Exchange 系統管理員**、**商務系統的商務用 Skype**、 **SharePoint 系統管理員**、**全域讀者**或**報告讀取者**連線至範本應用程式的使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="5fcb0-151">如需詳細資訊，請參閱[關於系統管理員角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="5fcb0-152">重新整理失敗</span><span class="sxs-lookup"><span data-stu-id="5fcb0-152">Refresh failed</span></span>

 <span data-ttu-id="5fcb0-153">**您將在其中看到這個訊息：** 電子郵件從 Power BI 或重新整理歷程記錄中的失敗的狀態。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="5fcb0-154">**原因：** 有時連接至範本應用程式之使用者的認證重設，且不會導致使用者看到的範本應用程式的連線設定中更新重新整理失敗錯誤。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="5fcb0-155">**若要修正此錯誤：** Power BI 中尋找對應至 Microsoft 365 使用情況分析範本應用程式的資料集、 選取**排程重新整理**並提供您的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="5fcb0-156">如果還是沒有用，清除快取，然後重新建立該範本應用程式。</span><span class="sxs-lookup"><span data-stu-id="5fcb0-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
