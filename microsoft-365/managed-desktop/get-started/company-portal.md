---
title: 在裝置上安裝 Intune 公司入口網站
description: 在 Microsoft 受管理的桌面裝置上安裝公司入口網站應用程式的相關資訊
keywords: Microsoft 受管理的桌面、Microsoft 365、公司入口網站
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 371656168f32db86ff32f187736d59dbd5dbe749
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529692"
---
# <a name="install-intune-company-portal-on-on-devices"></a><span data-ttu-id="22022-104">在裝置上安裝 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="22022-104">Install Intune Company Portal on on devices</span></span>

<span data-ttu-id="22022-105">Microsoft 受管理的桌面要求 IT 管理員為其使用者安裝 Intune 公司入口網站與 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="22022-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="22022-106">以下是貴組織的一些優點：</span><span class="sxs-lookup"><span data-stu-id="22022-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="22022-107">使用者有一個位置可流覽及安裝可用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="22022-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="22022-108">IT 系統管理員可以依類別組織使用者的應用程式。</span><span class="sxs-lookup"><span data-stu-id="22022-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="22022-109">部分應用程式（如 Microsoft Project 和 Microsoft Visio）需要公司入口網站才能使用 Microsoft 受管理的桌面進行部署。</span><span class="sxs-lookup"><span data-stu-id="22022-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="22022-110">IT 系統管理員可以自訂群組織的公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="22022-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="22022-111">這包括品牌影像、在本機支援連絡人中新增，等等。</span><span class="sxs-lookup"><span data-stu-id="22022-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="22022-112">如需詳細資訊，請參閱 how [To Configure The Microsoft Intune 公司入口網站應用程式](https://docs.microsoft.com/intune/company-portal-app)。</span><span class="sxs-lookup"><span data-stu-id="22022-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).</span></span>   

<span data-ttu-id="22022-113">本主題說明將 Intune 公司入口網站部署至 Microsoft 受管理的桌面使用者的程式。</span><span class="sxs-lookup"><span data-stu-id="22022-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="22022-114">整體程式看起來如下所示：</span><span class="sxs-lookup"><span data-stu-id="22022-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="22022-115">從商務用 Microsoft Store 購買公司入口網站，並與 Intune 同步處理</span><span class="sxs-lookup"><span data-stu-id="22022-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="22022-116">將公司入口網站指派給您的使用者</span><span class="sxs-lookup"><span data-stu-id="22022-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="22022-117">向使用者傳達變更</span><span class="sxs-lookup"><span data-stu-id="22022-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="22022-118">步驟 1-購買來自 Microsoft Store for Business 的公司入口網站，並與 Intune 同步處理</span><span class="sxs-lookup"><span data-stu-id="22022-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="22022-119">如需如何購買應用程式和與 Intune 同步的資訊，請參閱將*應用程式部署至 Microsoft 受管理的桌面裝置*中的[Microsoft Store for Business app](deploy-apps.md#msfb-apps) 。</span><span class="sxs-lookup"><span data-stu-id="22022-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="22022-120">本主題提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="22022-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="22022-121">從商務用 Microsoft Store 購買公司入口網站</span><span class="sxs-lookup"><span data-stu-id="22022-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="22022-122">強制 Intune 與 Microsoft Store for Business 之間的同步處理</span><span class="sxs-lookup"><span data-stu-id="22022-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="22022-123">在 Intune 和 Microsoft Store for Business 上驗證主動同步處理</span><span class="sxs-lookup"><span data-stu-id="22022-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="22022-124">步驟 2-將公司入口網站指派給您的使用者</span><span class="sxs-lookup"><span data-stu-id="22022-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="22022-125">透過 Microsoft Managed Desktop Admin 入口網站，將支援要求提交至 Microsoft Managed Desktop Operations。</span><span class="sxs-lookup"><span data-stu-id="22022-125">Submit a support request to Microsoft Managed Desktop Operations through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="22022-126">在支援要求中，要求將公司入口網站指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="22022-126">In the support request, request that Company Portal be assigned to your users.</span></span> <span data-ttu-id="22022-127">Microsoft 受管理的桌面會將公司入口網站部署至您的租使用者，並在組織中的 Microsoft 受管理桌面裝置上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="22022-127">Microsoft Managed Desktop will deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

<span data-ttu-id="22022-128">如需使用 Microsoft 受管理的電腦提交支援要求的詳細資訊，請參閱[Microsoft Managed desktop 的系統管理支援](../working-with-managed-desktop/admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="22022-128">For more information on submitting support requests with Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="22022-129">步驟 3-向使用者傳達變更</span><span class="sxs-lookup"><span data-stu-id="22022-129">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="22022-130">做為您組織的 IT 管理員，請務必讓您的使用者瞭解如何在組織中使用公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="22022-130">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="22022-131">Microsoft 受管理的桌面建議：</span><span class="sxs-lookup"><span data-stu-id="22022-131">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="22022-132">從公司入口網站安裝應用程式的步驟。</span><span class="sxs-lookup"><span data-stu-id="22022-132">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="22022-133">如需詳細資訊，請參閱[在您的裝置上安裝和共用應用程式](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)。</span><span class="sxs-lookup"><span data-stu-id="22022-133">For more information, see [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="22022-134">如何將要求傳送給 IT 管理員，以取得目前無法使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="22022-134">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="22022-135">如需詳細資訊，請參閱[要求適用于工作或學校的應用程式](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。</span><span class="sxs-lookup"><span data-stu-id="22022-135">For more information, see [Request an app for work or school](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="22022-136">開始使用 Microsoft 受管理電腦的步驟</span><span class="sxs-lookup"><span data-stu-id="22022-136">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="22022-137">在系統管理入口網站中新增和驗證系統管理員連絡人</span><span class="sxs-lookup"><span data-stu-id="22022-137">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="22022-138">調整條件式存取</span><span class="sxs-lookup"><span data-stu-id="22022-138">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="22022-139">指派授權</span><span class="sxs-lookup"><span data-stu-id="22022-139">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="22022-140">部署 Intune 公司入口網站（本主題）</span><span class="sxs-lookup"><span data-stu-id="22022-140">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="22022-141">啟用企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="22022-141">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="22022-142">設定裝置</span><span class="sxs-lookup"><span data-stu-id="22022-142">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="22022-143">讓您的使用者準備好使用裝置</span><span class="sxs-lookup"><span data-stu-id="22022-143">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="22022-144">部署應用程式</span><span class="sxs-lookup"><span data-stu-id="22022-144">Deploy apps</span></span>](deploy-apps.md)
