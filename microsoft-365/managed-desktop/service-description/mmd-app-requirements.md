---
title: Microsoft 受管理的桌面應用程式需求
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5889a4e80f44349b4f149ee4f2a631f12b32251e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637849"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="f5986-103">Microsoft 受管理的桌面應用程式需求</span><span class="sxs-lookup"><span data-stu-id="f5986-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="f5986-104">為了保證 Microsoft 受管理桌面裝置的效能、可靠性及可維護性，客戶的商務線應用程式不一定會嚴重影響使用者的經驗，也不一定會影響安全性的目的。</span><span class="sxs-lookup"><span data-stu-id="f5986-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="f5986-105">因此，您想要部署至 Microsoft 受管理桌面裝置的商務線應用程式，必須符合本主題中的需求。</span><span class="sxs-lookup"><span data-stu-id="f5986-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="f5986-106">應用程式條件</span><span class="sxs-lookup"><span data-stu-id="f5986-106">Application condition</span></span>

<span data-ttu-id="f5986-107">重要的是應用程式不會對 Microsoft 管理的桌面環境造成不良影響。</span><span class="sxs-lookup"><span data-stu-id="f5986-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="f5986-108">以下是應用程式必須符合才能部署應用程式的需求。</span><span class="sxs-lookup"><span data-stu-id="f5986-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="f5986-109">針對任何特定的應用程式或驅動程式，Microsoft 可能會停征任何在此提供的需求。</span><span class="sxs-lookup"><span data-stu-id="f5986-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="f5986-110">Microsoft 可能決定移除任何對 Microsoft 受管理的桌面裝置效能和可靠性產生負面影響的應用程式或驅動程式。</span><span class="sxs-lookup"><span data-stu-id="f5986-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="f5986-111">集中管理的應用程式</span><span class="sxs-lookup"><span data-stu-id="f5986-111">Centrally managed apps</span></span>

<span data-ttu-id="f5986-112">所有安裝在 Microsoft 受管理裝置上的應用程式和驅動程式都必須透過 Microsoft Intune、Microsoft Store 或 Microsoft Store for Business 進行部署;若有可用，也會透過 Windows Update 服務部署驅動程式。</span><span class="sxs-lookup"><span data-stu-id="f5986-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Microsoft Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="f5986-113">禁止的應用程式類別</span><span class="sxs-lookup"><span data-stu-id="f5986-113">Prohibited app classes</span></span>

<span data-ttu-id="f5986-114">Microsoft 受管理的桌面裝置上不允許某些應用程式類型：</span><span class="sxs-lookup"><span data-stu-id="f5986-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="f5986-115">協力廠商的反病毒、安全性或核查軟體</span><span class="sxs-lookup"><span data-stu-id="f5986-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="f5986-116">Microsoft 365 Apps for enterprise 之前的 Microsoft Office 版本</span><span class="sxs-lookup"><span data-stu-id="f5986-116">Versions of Microsoft Office prior to Microsoft 365 Apps for enterprise</span></span>
- <span data-ttu-id="f5986-117">安裝或捆綁其他協力廠商軟體的應用程式</span><span class="sxs-lookup"><span data-stu-id="f5986-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="f5986-118">限制的應用程式行為</span><span class="sxs-lookup"><span data-stu-id="f5986-118">Restricted app behaviors</span></span>

<span data-ttu-id="f5986-119">某些應用程式行為會對使用者經驗造成負面影響，也可能對 Microsoft 受管理的桌面裝置帶來安全性風險。</span><span class="sxs-lookup"><span data-stu-id="f5986-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f5986-120">不允許在未從 Microsoft 管理的桌面環境中執行具有下列行為的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5986-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific  from Microsoft.</span></span>

<span data-ttu-id="f5986-121">使用者體驗：</span><span class="sxs-lookup"><span data-stu-id="f5986-121">User Experience:</span></span>
- <span data-ttu-id="f5986-122">安裝背景服務</span><span class="sxs-lookup"><span data-stu-id="f5986-122">Install background services</span></span>
- <span data-ttu-id="f5986-123">將自身新增至 Windows 啟動路徑</span><span class="sxs-lookup"><span data-stu-id="f5986-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="f5986-124">取決於驅動程式的應用程式</span><span class="sxs-lookup"><span data-stu-id="f5986-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="f5986-125">協力廠商網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="f5986-125">3rd party web browsers</span></span>

<span data-ttu-id="f5986-126">安全性：</span><span class="sxs-lookup"><span data-stu-id="f5986-126">Security:</span></span>
- <span data-ttu-id="f5986-127">提升使用者的許可權</span><span class="sxs-lookup"><span data-stu-id="f5986-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="f5986-128">做為應用程式存放區，或具有內建的延伸管理員</span><span class="sxs-lookup"><span data-stu-id="f5986-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="f5986-129">有已知的安全弱點</span><span class="sxs-lookup"><span data-stu-id="f5986-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="f5986-130">加密或限制存取使用者資料</span><span class="sxs-lookup"><span data-stu-id="f5986-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="f5986-131">未簽署或使用不會總成根信任的憑證進行簽署</span><span class="sxs-lookup"><span data-stu-id="f5986-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="f5986-132">驅動程式部署</span><span class="sxs-lookup"><span data-stu-id="f5986-132">Driver deployment</span></span>

<span data-ttu-id="f5986-133">Microsoft 受管理的桌面只支援透過 Windows Update 或已安裝的 [收件匣] 與 Microsoft Managed 裝置提供的裝置驅動程式。</span><span class="sxs-lookup"><span data-stu-id="f5986-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="f5986-134">若應用程式需要特定的驅動程式來執行它，就會被視為限制的應用程式，並在部署至 Microsoft Managed Desktop 之前需要例外狀況。</span><span class="sxs-lookup"><span data-stu-id="f5986-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an exception before being deployed to Microsoft Managed Desktop.</span></span> 

