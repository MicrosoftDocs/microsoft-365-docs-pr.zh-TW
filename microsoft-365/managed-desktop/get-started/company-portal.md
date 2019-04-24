---
title: 安裝 Intune 公司入口網站 Microsoft 受管理的電腦裝置
description: Microsoft 受管理的電腦裝置上安裝的公司入口網站應用程式的資訊
keywords: Microsoft 受管理的電腦，Microsoft 365，公司入口網站
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: d533de7b68d9fa55ff0a108373d9621068c8fb1e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289108"
---
# <a name="install-intune-company-portal-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="07e10-104">Microsoft 受管理的電腦裝置上安裝 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="07e10-104">Install Intune Company Portal on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="07e10-105">Microsoft 受管理的電腦需要 IT 系統管理員安裝 Intune 公司入口網站的使用者與 Microsoft 受管理的電腦裝置。</span><span class="sxs-lookup"><span data-stu-id="07e10-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="07e10-106">以下是您組織的一些優點：</span><span class="sxs-lookup"><span data-stu-id="07e10-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="07e10-107">使用者可以瀏覽並安裝可用的應用程式的一個位置。</span><span class="sxs-lookup"><span data-stu-id="07e10-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="07e10-108">IT 系統管理員可以組織應用程式為其使用者的類別。</span><span class="sxs-lookup"><span data-stu-id="07e10-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="07e10-109">某些應用程式 （如 Microsoft Project 和 Microsoft Visio） 需要使用 Microsoft 受管理電腦來部署的公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="07e10-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="07e10-110">IT 系統管理員可以為其組織自訂公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="07e10-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="07e10-111">這包括品牌製作映像，新增在本機的支援連絡人等等。</span><span class="sxs-lookup"><span data-stu-id="07e10-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="07e10-112">如需詳細資訊，請參閱[如何設定 Microsoft Intune 公司入口網站應用程式](https://docs.microsoft.com/intune/company-portal-app)。</span><span class="sxs-lookup"><span data-stu-id="07e10-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).</span></span>   

<span data-ttu-id="07e10-113">本主題記載的程序將 Intune 公司入口網站部署至您 Microsoft 受管理電腦的使用者。</span><span class="sxs-lookup"><span data-stu-id="07e10-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="07e10-114">整體程序看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="07e10-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="07e10-115">購買商務及同步處理使用 Intune 公司入口網站從 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="07e10-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="07e10-116">指派給使用者的公司入口網站</span><span class="sxs-lookup"><span data-stu-id="07e10-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="07e10-117">傳達給使用者的變更</span><span class="sxs-lookup"><span data-stu-id="07e10-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="07e10-118">步驟 1-從 Microsoft Store for Business 和同步處理的購買公司入口網站使用 Intune</span><span class="sxs-lookup"><span data-stu-id="07e10-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="07e10-119">如需如何購買應用程式和使用 Intune 的同步處理的資訊，請參閱*部署應用程式連接至 Microsoft 受管理的電腦裝置*中的[商務應用程式的 Microsoft 網上商店](deploy-apps.md#msfb-apps)。</span><span class="sxs-lookup"><span data-stu-id="07e10-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="07e10-120">本主題提供如何資訊：</span><span class="sxs-lookup"><span data-stu-id="07e10-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="07e10-121">從適用於企業的 Microsoft 網上商店的購買公司入口網站</span><span class="sxs-lookup"><span data-stu-id="07e10-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="07e10-122">強制執行 Intune 和商務用 Microsoft Store 間同步處理</span><span class="sxs-lookup"><span data-stu-id="07e10-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="07e10-123">確認 active Intune 和商務用 Microsoft Store 之間的同步處理</span><span class="sxs-lookup"><span data-stu-id="07e10-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="07e10-124">步驟 2-您的使用者指派公司入口網站</span><span class="sxs-lookup"><span data-stu-id="07e10-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="07e10-125">支援要求提交給 Microsoft 受管理的桌上型電腦 Operations 透過 Microsoft 受管理的桌上型電腦系統管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="07e10-125">Submit a support request to Microsoft Managed Desktop Operations through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="07e10-126">在支援要求，要求公司入口網站指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="07e10-126">In the support request, request that Company Portal be assigned to your users.</span></span> <span data-ttu-id="07e10-127">Microsoft 受管理的電腦會將公司入口網站部署至您的租用戶，並在組織中的 Microsoft 受管理的電腦裝置上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="07e10-127">Microsoft Managed Desktop will deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

<span data-ttu-id="07e10-128">如需有關提交使用 Microsoft 受管理電腦的支援要求的詳細資訊，請參閱 <<c0>支援的 Microsoft 受管理電腦的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="07e10-128">For more information on submitting support requests with Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="07e10-129">步驟 3-傳達給使用者的變更</span><span class="sxs-lookup"><span data-stu-id="07e10-129">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="07e10-130">為貴組織的 IT 系統管理員，請務必讓您了解如何在組織中使用公司入口網站的使用者。</span><span class="sxs-lookup"><span data-stu-id="07e10-130">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="07e10-131">Microsoft 受管理電腦建議：</span><span class="sxs-lookup"><span data-stu-id="07e10-131">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="07e10-132">在 [從公司入口網站安裝的應用程式的步驟。</span><span class="sxs-lookup"><span data-stu-id="07e10-132">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="07e10-133">如需詳細資訊，請參閱[安裝及共用您的裝置上的應用程式](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)。</span><span class="sxs-lookup"><span data-stu-id="07e10-133">For more information, see [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="07e10-134">如何將要求傳送至目前沒有足夠的應用程式的 IT 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="07e10-134">How to send requests to IT administrators for applications that are not currently available.</span></span>