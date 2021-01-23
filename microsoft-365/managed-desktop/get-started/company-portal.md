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
ms.openlocfilehash: bddf46e451408e4f17e58cc62186b7cd6cefb382
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939281"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="db96a-104">在裝置上安裝 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="db96a-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="db96a-105">Microsoft 受管理的桌面要求 IT 管理員為其使用者安裝 Intune 公司入口網站與 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="db96a-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="db96a-106">以下是貴組織的一些優點：</span><span class="sxs-lookup"><span data-stu-id="db96a-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="db96a-107">使用者有一個位置可流覽及安裝可用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="db96a-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="db96a-108">IT 系統管理員可以依類別組織使用者的應用程式。</span><span class="sxs-lookup"><span data-stu-id="db96a-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="db96a-109">某些應用程式 (如 Microsoft Project 和 Microsoft Visio) 需要公司入口網站才能使用 Microsoft 受管理的桌面進行部署。</span><span class="sxs-lookup"><span data-stu-id="db96a-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="db96a-110">IT 系統管理員可以自訂群組織的公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="db96a-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="db96a-111">這包括品牌影像、在本機支援連絡人中新增，等等。</span><span class="sxs-lookup"><span data-stu-id="db96a-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="db96a-112">如需詳細資訊，請參閱 how [To Configure The Microsoft Intune 公司入口網站應用程式](https://docs.microsoft.com/intune/company-portal-app)。</span><span class="sxs-lookup"><span data-stu-id="db96a-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).</span></span>   

<span data-ttu-id="db96a-113">本主題說明將 Intune 公司入口網站部署至 Microsoft 受管理的桌面使用者的程式。</span><span class="sxs-lookup"><span data-stu-id="db96a-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="db96a-114">整體程式看起來如下所示：</span><span class="sxs-lookup"><span data-stu-id="db96a-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="db96a-115">從商務用 Microsoft Store 購買公司入口網站，並與 Intune 同步處理</span><span class="sxs-lookup"><span data-stu-id="db96a-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="db96a-116">將公司入口網站指派給您的使用者</span><span class="sxs-lookup"><span data-stu-id="db96a-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="db96a-117">向使用者傳達變更</span><span class="sxs-lookup"><span data-stu-id="db96a-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="db96a-118">步驟 1-購買來自 Microsoft Store for Business 的公司入口網站，並與 Intune 同步處理</span><span class="sxs-lookup"><span data-stu-id="db96a-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="db96a-119">如需如何購買應用程式和與 Intune 同步的資訊，請參閱將 *應用程式部署至 Microsoft 受管理的桌面裝置* 中的 [Microsoft Store for Business app](deploy-apps.md#msfb-apps) 。</span><span class="sxs-lookup"><span data-stu-id="db96a-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="db96a-120">本主題提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="db96a-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="db96a-121">從商務用 Microsoft Store 購買公司入口網站</span><span class="sxs-lookup"><span data-stu-id="db96a-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="db96a-122">強制 Intune 與 Microsoft Store for Business 之間的同步處理</span><span class="sxs-lookup"><span data-stu-id="db96a-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="db96a-123">在 Intune 和 Microsoft Store for Business 上驗證主動同步處理</span><span class="sxs-lookup"><span data-stu-id="db96a-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="db96a-124">步驟 2-將公司入口網站指派給您的使用者</span><span class="sxs-lookup"><span data-stu-id="db96a-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="db96a-125">在 Microsoft Managed Desktop 中進行註冊後，Microsoft 受管理的桌面作業將會自動將公司入口網站部署至您的租使用者，並在組織中的 Microsoft 受管理桌面裝置上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="db96a-125">Following your enrollment in Microsoft Managed Desktop, Microsoft Managed Desktop Operations will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="db96a-126">步驟 3-向使用者傳達變更</span><span class="sxs-lookup"><span data-stu-id="db96a-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="db96a-127">做為您組織的 IT 管理員，請務必讓您的使用者瞭解如何在組織中使用公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="db96a-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="db96a-128">Microsoft 受管理的桌面建議：</span><span class="sxs-lookup"><span data-stu-id="db96a-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="db96a-129">從公司入口網站安裝應用程式的步驟。</span><span class="sxs-lookup"><span data-stu-id="db96a-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="db96a-130">如需詳細資訊，請參閱 [在您的裝置上安裝和共用應用程式](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)。</span><span class="sxs-lookup"><span data-stu-id="db96a-130">For more information, see [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="db96a-131">如何將要求傳送給 IT 管理員，以取得目前無法使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="db96a-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="db96a-132">如需詳細資訊，請參閱 [要求適用于工作或學校的應用程式](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。</span><span class="sxs-lookup"><span data-stu-id="db96a-132">For more information, see [Request an app for work or school](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="db96a-133">開始使用 Microsoft 受管理電腦的步驟</span><span class="sxs-lookup"><span data-stu-id="db96a-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="db96a-134">在系統管理入口網站中新增和驗證系統管理員連絡人</span><span class="sxs-lookup"><span data-stu-id="db96a-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="db96a-135">調整條件式存取</span><span class="sxs-lookup"><span data-stu-id="db96a-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="db96a-136">指派授權</span><span class="sxs-lookup"><span data-stu-id="db96a-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="db96a-137">部署 Intune 公司入口網站 (本主題) </span><span class="sxs-lookup"><span data-stu-id="db96a-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="db96a-138">啟用企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="db96a-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="db96a-139">設定裝置</span><span class="sxs-lookup"><span data-stu-id="db96a-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="db96a-140">讓您的使用者準備好使用裝置</span><span class="sxs-lookup"><span data-stu-id="db96a-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="db96a-141">部署應用程式</span><span class="sxs-lookup"><span data-stu-id="db96a-141">Deploy apps</span></span>](deploy-apps.md)
