---
title: 在裝置上安裝 Intune 公司入口網站
description: 在 Microsoft 受管理的電腦裝置上安裝公司入口網站應用程式的相關資訊
keywords: Microsoft 受管理的電腦、Microsoft 365、公司入口網站
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086682"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="d4b4d-104">在裝置上安裝 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="d4b4d-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="d4b4d-105">Microsoft 受管理的電腦需要 IT 管理員為其具有 Microsoft 受管理的電腦裝置的使用者安裝 Intune 公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d4b4d-106">以下是貴組織的一些優點：</span><span class="sxs-lookup"><span data-stu-id="d4b4d-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="d4b4d-107">使用者有一個位置可流覽及安裝可用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="d4b4d-108">IT 系統管理員可以依類別組織使用者的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="d4b4d-109">某些應用程式 (例如 Microsoft Project 和 Microsoft Visio) 需要公司入口網站以 Microsoft 受管理的電腦部署。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="d4b4d-110">IT 管理員可以自訂群組織的公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="d4b4d-111">這包括品牌影像、在本機支援連絡人中新增，等等。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="d4b4d-112">如需詳細資訊，請參閱 how [to Configure the Microsoft Intune 公司入口網站應用程式](/intune/company-portal-app)。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span></span>   

<span data-ttu-id="d4b4d-113">本主題說明將 Intune 公司入口網站部署至 Microsoft 受管理的電腦使用者的處理常式。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="d4b4d-114">整體程式看起來如下所示：</span><span class="sxs-lookup"><span data-stu-id="d4b4d-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="d4b4d-115">從商務用 Microsoft Store 購買公司入口網站，並與 Intune 同步</span><span class="sxs-lookup"><span data-stu-id="d4b4d-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="d4b4d-116">將公司入口網站指派給您的使用者</span><span class="sxs-lookup"><span data-stu-id="d4b4d-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="d4b4d-117">向使用者傳達變更</span><span class="sxs-lookup"><span data-stu-id="d4b4d-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="d4b4d-118">步驟 1-從商務用 Microsoft Store 購買公司入口網站，並與 Intune 同步處理</span><span class="sxs-lookup"><span data-stu-id="d4b4d-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="d4b4d-119">如需如何購買應用程式和與 Intune 同步的資訊，請參閱將 *應用程式部署至 Microsoft 受管理的電腦裝置*[商務用 Microsoft Store 應用程式](deploy-apps.md#msfb-apps)。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="d4b4d-120">本主題提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d4b4d-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="d4b4d-121">從商務用 Microsoft Store 購買公司入口網站</span><span class="sxs-lookup"><span data-stu-id="d4b4d-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="d4b4d-122">強制 Intune 與商務用 Microsoft Store 之間的同步處理</span><span class="sxs-lookup"><span data-stu-id="d4b4d-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="d4b4d-123">驗證 Intune 與商務用 Microsoft Store 之間的主動同步處理</span><span class="sxs-lookup"><span data-stu-id="d4b4d-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="d4b4d-124">步驟 2-將公司入口網站指派給您的使用者</span><span class="sxs-lookup"><span data-stu-id="d4b4d-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="d4b4d-125">在 Microsoft 受管理的電腦中進行註冊後，系統會自動將公司入口網站部署至您的租使用者，並在組織中的 Microsoft 受管理的電腦裝置上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-125">Following your enrollment in Microsoft Managed Desktop, we will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="d4b4d-126">步驟 3-向使用者傳達變更</span><span class="sxs-lookup"><span data-stu-id="d4b4d-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="d4b4d-127">做為您組織的 IT 管理員，請務必讓您的使用者瞭解如何在組織中使用公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="d4b4d-128">Microsoft 受管理的電腦建議：</span><span class="sxs-lookup"><span data-stu-id="d4b4d-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="d4b4d-129">從公司入口網站安裝應用程式的步驟。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="d4b4d-130">如需詳細資訊，請參閱 [在您的裝置上安裝和共用應用程式](/intune-user-help/install-apps-cpapp-windows)。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-130">For more information, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="d4b4d-131">如何將要求傳送給 IT 管理員，以取得目前無法使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="d4b4d-132">如需詳細資訊，請參閱 [要求適用于工作或學校的應用程式](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。</span><span class="sxs-lookup"><span data-stu-id="d4b4d-132">For more information, see [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="d4b4d-133">開始使用 Microsoft 受管理電腦的步驟</span><span class="sxs-lookup"><span data-stu-id="d4b4d-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="d4b4d-134">在系統管理入口網站中新增和驗證系統管理員連絡人</span><span class="sxs-lookup"><span data-stu-id="d4b4d-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="d4b4d-135">調整條件式存取</span><span class="sxs-lookup"><span data-stu-id="d4b4d-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="d4b4d-136">指派授權</span><span class="sxs-lookup"><span data-stu-id="d4b4d-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="d4b4d-137">部署 Intune 公司入口網站 (本主題) </span><span class="sxs-lookup"><span data-stu-id="d4b4d-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="d4b4d-138">啟用企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="d4b4d-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="d4b4d-139">設定裝置</span><span class="sxs-lookup"><span data-stu-id="d4b4d-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="d4b4d-140">讓您的使用者準備好使用裝置</span><span class="sxs-lookup"><span data-stu-id="d4b4d-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="d4b4d-141">部署應用程式</span><span class="sxs-lookup"><span data-stu-id="d4b4d-141">Deploy apps</span></span>](deploy-apps.md)
