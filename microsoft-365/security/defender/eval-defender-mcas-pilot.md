---
title: 試驗 Microsoft Cloud App Security，使用 Microsoft 365 Defender，建立試驗群組，設定條件式存取控制，嘗試功能，設定成為 Microsoft 365 Defender 的一部分
description: 設定您的 Microsoft 365 Defender 試用實驗室或試驗環境，以測試及體驗設計用來保護裝置、身分識別、資料及應用程式的安全性解決方案。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457624"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a><span data-ttu-id="3941d-103">使用 Microsoft 365 Defender 的試驗 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3941d-103">Pilot Microsoft Cloud App Security with Microsoft 365 Defender</span></span>


<span data-ttu-id="3941d-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3941d-104">**Applies to:**</span></span>
- <span data-ttu-id="3941d-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3941d-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="3941d-106">本文是設定 Microsoft Cloud App Security 評估環境之程式中的[步驟 3](eval-defender-mcas-overview.md)之3。</span><span class="sxs-lookup"><span data-stu-id="3941d-106">This article is [Step 3 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="3941d-107">如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-mcas-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3941d-107">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="3941d-108">使用下列步驟來設定和設定 Microsoft Cloud App Security 的試驗。</span><span class="sxs-lookup"><span data-stu-id="3941d-108">Use the following steps to setup and configure the pilot for Microsoft Cloud App Security.</span></span>


![試驗 Microsoft Cloud App Security 步驟](../../media/defender/m365-defender-mcas-pilot-steps.png)

- <span data-ttu-id="3941d-110">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="3941d-110">Step 1.</span></span> [<span data-ttu-id="3941d-111">建立試驗群組—將試驗部署的範圍設為特定使用者群組</span><span class="sxs-lookup"><span data-stu-id="3941d-111">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [<span data-ttu-id="3941d-112">步驟2。設定保護-條件式存取應用程式控制</span><span class="sxs-lookup"><span data-stu-id="3941d-112">Step 2. Configure protection — Conditional Access App Control</span></span>](#step-2-configure-protection--conditional-access-app-control)
- [<span data-ttu-id="3941d-113">步驟3。嘗試功能-逐步指導您的環境以進行保護</span><span class="sxs-lookup"><span data-stu-id="3941d-113">Step 3. Try out capabilities — Walk through tutorials for protecting your environment</span></span>](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a><span data-ttu-id="3941d-114">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="3941d-114">Step 1.</span></span> <span data-ttu-id="3941d-115">建立試驗群組—將試驗部署的範圍設為特定使用者群組</span><span class="sxs-lookup"><span data-stu-id="3941d-115">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>

<span data-ttu-id="3941d-116">Microsoft Cloud App Security 可讓您進行部署的範圍。</span><span class="sxs-lookup"><span data-stu-id="3941d-116">Microsoft Cloud App Security enables you to scope your deployment.</span></span> <span data-ttu-id="3941d-117">範圍可讓您選取要監視之應用程式的特定使用者群組，或從監控中排除。</span><span class="sxs-lookup"><span data-stu-id="3941d-117">Scoping allows you to select certain user groups to be monitored for apps or excluded from monitoring.</span></span> <span data-ttu-id="3941d-118">您可以包含或排除使用者群組。</span><span class="sxs-lookup"><span data-stu-id="3941d-118">You can include or exclude user groups.</span></span> <span data-ttu-id="3941d-119">若要設定試驗部署的範圍，請參閱設定 [範圍的部署](/cloud-app-security/scoped-deployment)。</span><span class="sxs-lookup"><span data-stu-id="3941d-119">To scope your pilot deployment, see [Scoped Deployment](/cloud-app-security/scoped-deployment).</span></span>


## <a name="step-2-configure-protection--conditional-access-app-control"></a><span data-ttu-id="3941d-120">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="3941d-120">Step 2.</span></span> <span data-ttu-id="3941d-121">設定保護-條件式存取應用程式控制</span><span class="sxs-lookup"><span data-stu-id="3941d-121">Configure protection — Conditional Access App Control</span></span>

<span data-ttu-id="3941d-122">您可以設定的最強大防護之一是條件式存取應用程式控制。</span><span class="sxs-lookup"><span data-stu-id="3941d-122">One of the most powerful protections you can configure is Conditional Access App Control.</span></span> <span data-ttu-id="3941d-123">這需要與 Azure Active Directory (Azure AD) 進行整合。</span><span class="sxs-lookup"><span data-stu-id="3941d-123">This requires integration with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="3941d-124">它可讓您將條件式存取原則（包括 (類似) 裝置）等相關原則套用至您已 sanctioned 的雲端應用程式。</span><span class="sxs-lookup"><span data-stu-id="3941d-124">It allows you to apply Conditional Access policies, including related policies (like requiring healthy devices), to cloud apps you've sanctioned.</span></span> 

<span data-ttu-id="3941d-125">使用 Microsoft Cloud App Security 來管理 SaaS 應用程式的第一步是探索這些應用程式，然後將它們新增至您的 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="3941d-125">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="3941d-126">如果您需要探索協助，請參閱 [探索和管理您網路中的 SaaS 應用程式](/cloud-app-security/tutorial-shadow-it)。</span><span class="sxs-lookup"><span data-stu-id="3941d-126">If you need help with discovery, see [Discover and manage SaaS apps in your network](/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="3941d-127">在您探索應用程式之後， [將它們新增至您的 AZURE AD 租](/azure/active-directory/manage-apps/add-application-portal)使用者。</span><span class="sxs-lookup"><span data-stu-id="3941d-127">After you've discovered apps, [add these to your Azure AD tenant](/azure/active-directory/manage-apps/add-application-portal).</span></span>

<span data-ttu-id="3941d-128">您可以執行下列動作來開始管理：</span><span class="sxs-lookup"><span data-stu-id="3941d-128">You can begin to manage these by doing the following:</span></span>

- <span data-ttu-id="3941d-129">首先，在 Azure AD 中建立新的條件式存取原則，並將其設定為「使用條件式存取應用程式控制」。</span><span class="sxs-lookup"><span data-stu-id="3941d-129">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="3941d-130">這會將要求重新導向至雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="3941d-130">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="3941d-131">您可以建立一個原則，並將所有 SaaS 應用程式新增至此原則。</span><span class="sxs-lookup"><span data-stu-id="3941d-131">You can create one policy and add all SaaS apps to this policy.</span></span>
- <span data-ttu-id="3941d-132">接下來，在雲端 App 安全性中建立會話原則。</span><span class="sxs-lookup"><span data-stu-id="3941d-132">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="3941d-133">針對每個您想要套用的控制項建立一個原則。</span><span class="sxs-lookup"><span data-stu-id="3941d-133">Create one policy for each control you want to apply.</span></span>

<span data-ttu-id="3941d-134">如需詳細資訊，包括支援的應用程式和用戶端，請參閱[使用 Microsoft Cloud App Security 條件式存取應用程式控制保護應用程式](/cloud-app-security/proxy-intro-aad)。</span><span class="sxs-lookup"><span data-stu-id="3941d-134">For more information, including supported apps and clients, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).</span></span> 

<span data-ttu-id="3941d-135">如需原則，請參閱[建議的 SaaS 應用程式 Microsoft Cloud App Security 原則](../office-365-security/mcas-saas-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3941d-135">For example policies, see [Recommended Microsoft Cloud App Security policies for SaaS apps](../office-365-security/mcas-saas-access-policies.md).</span></span> <span data-ttu-id="3941d-136">這些原則建立于一組共同的身分 [識別和裝置存取原則](../office-365-security/microsoft-365-policies-configurations.md) 上，建議作為所有客戶的起點。</span><span class="sxs-lookup"><span data-stu-id="3941d-136">These policies build on a set of [common identity and device access policies](../office-365-security/microsoft-365-policies-configurations.md) that are recommended as a starting point for all customers.</span></span> 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a><span data-ttu-id="3941d-137">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="3941d-137">Step 3.</span></span> <span data-ttu-id="3941d-138">嘗試功能-逐步指導您的環境以進行保護</span><span class="sxs-lookup"><span data-stu-id="3941d-138">Try out capabilities — Walk through tutorials for protecting your environment</span></span> 

<span data-ttu-id="3941d-139">Microsoft Cloud App Security 檔包括一系列的教程，可協助您探索風險及保護您的環境。</span><span class="sxs-lookup"><span data-stu-id="3941d-139">The Microsoft Cloud App Security documentation includes a series of tutorials to help you discover risk and protect your environment.</span></span> 

<span data-ttu-id="3941d-140">嘗試雲端 App 安全性教程：</span><span class="sxs-lookup"><span data-stu-id="3941d-140">Try out Cloud App Security tutorials:</span></span>

- [<span data-ttu-id="3941d-141">偵測到可疑的使用者活動</span><span class="sxs-lookup"><span data-stu-id="3941d-141">Detect suspicious user activity</span></span>](/cloud-app-security/tutorial-suspicious-activity)
- [<span data-ttu-id="3941d-142">調查有風險的使用者</span><span class="sxs-lookup"><span data-stu-id="3941d-142">Investigate risky users</span></span>](/cloud-app-security/tutorial-ueba)
- [<span data-ttu-id="3941d-143">調查危險的 OAuth 應用程式</span><span class="sxs-lookup"><span data-stu-id="3941d-143">Investigate risky OAuth apps</span></span>](/cloud-app-security/investigate-risky-oauth)
- [<span data-ttu-id="3941d-144">探索和保護機密資訊</span><span class="sxs-lookup"><span data-stu-id="3941d-144">Discover and protect sensitive information</span></span>](/cloud-app-security/tutorial-dlp)
- [<span data-ttu-id="3941d-145">保護組織中的任何應用程式即時</span><span class="sxs-lookup"><span data-stu-id="3941d-145">Protect any app in your organization in real time</span></span>](/cloud-app-security/tutorial-proxy)
- [<span data-ttu-id="3941d-146">封鎖敏感資訊的下載</span><span class="sxs-lookup"><span data-stu-id="3941d-146">Block downloads of sensitive information</span></span>](/cloud-app-security/use-case-proxy-block-session-aad)
- [<span data-ttu-id="3941d-147">使用系統管理員隔離來保護您的檔案</span><span class="sxs-lookup"><span data-stu-id="3941d-147">Protect your files with admin quarantine</span></span>](/cloud-app-security/use-case-admin-quarantine)
- [<span data-ttu-id="3941d-148">在危險動作上需要進行逐步驗證</span><span class="sxs-lookup"><span data-stu-id="3941d-148">Require step-up authentication upon risky action</span></span>](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a><span data-ttu-id="3941d-149">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3941d-149">Next steps</span></span>

[<span data-ttu-id="3941d-150">在試驗環境中使用 Microsoft 365 Defender 調查和回應</span><span class="sxs-lookup"><span data-stu-id="3941d-150">Investigate and respond using Microsoft 365 Defender in a pilot environment</span></span>](eval-defender-investigate-respond.md)

<span data-ttu-id="3941d-151">回到 [[評估 Microsoft Cloud App Security](eval-defender-mcas-overview.md)的總覽</span><span class="sxs-lookup"><span data-stu-id="3941d-151">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="3941d-152">回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述</span><span class="sxs-lookup"><span data-stu-id="3941d-152">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>