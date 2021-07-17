---
title: 評估 Microsoft 365 Defender
description: 設定您的 Microsoft 365 Defender 試用實驗室或試驗環境，以嘗試用來保護組織中裝置、身分識別、資料和應用程式的安全性解決方案。
keywords: Microsoft 365 Defender 試用版，請嘗試 Microsoft 365 Defender，評估 Microsoft 365 Defender，Microsoft 365 Defender 評估實驗室，Microsoft 365 Defender 試驗，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53457949"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="19d48-104">建立 Microsoft 365 Defender 試用實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="19d48-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="19d48-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="19d48-105">**Applies to:**</span></span>
- <span data-ttu-id="19d48-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19d48-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="19d48-107">本指南可協助您使用使用者和群組設定實驗室環境，然後逐步指導您設定 Microsoft 365 Defender 中的功能，讓您可以模仿威脅攻擊，並取得有意義的試用結果。</span><span class="sxs-lookup"><span data-stu-id="19d48-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="19d48-108">建立此試用實驗室或試驗環境的目的是為了示範綜合和整合式的 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="19d48-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="19d48-109">體驗這種聰明的安全性解決方案如何偵測、避免、自動調查，並回應貴組織的高級威脅。</span><span class="sxs-lookup"><span data-stu-id="19d48-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="19d48-110">您將會逐步引導您根據建議的部署路徑開始 Microsoft 365 Defender 評估。</span><span class="sxs-lookup"><span data-stu-id="19d48-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="19d48-111">其目標是協助您在實驗環境中設定安全性解決方案，以試用帳戶，或在實際執行環境中使用完整授權。</span><span class="sxs-lookup"><span data-stu-id="19d48-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="19d48-112">準備您的試用實驗室或試驗環境可協助您向組織中的決策者展示安全性運作案例。</span><span class="sxs-lookup"><span data-stu-id="19d48-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="19d48-113">當您執行攻擊模擬並符合結果時，您可以使用 Microsoft 技術銷售人員或組織中的專家的說明，在組織中完整部署及 operationalize。</span><span class="sxs-lookup"><span data-stu-id="19d48-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="19d48-114">本指南將協助您：</span><span class="sxs-lookup"><span data-stu-id="19d48-114">This guide will help you:</span></span>
- <span data-ttu-id="19d48-115">設定實驗室服務器和電腦</span><span class="sxs-lookup"><span data-stu-id="19d48-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="19d48-116">使用使用者和群組設定 Active Directory</span><span class="sxs-lookup"><span data-stu-id="19d48-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="19d48-117">為身分識別設定及設定 microsoft defender 身分識別、microsoft defender for Office 365、microsoft defender for Endpoint 及 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="19d48-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="19d48-118">設定伺服器和電腦的本機原則</span><span class="sxs-lookup"><span data-stu-id="19d48-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="19d48-119">模仿威脅攻擊，以在 Microsoft 365 Defender 產生測試事件或警示</span><span class="sxs-lookup"><span data-stu-id="19d48-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="19d48-120">為了獲得最佳結果，請盡可能遵循實驗室設定指示。</span><span class="sxs-lookup"><span data-stu-id="19d48-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="19d48-121">部署階段</span><span class="sxs-lookup"><span data-stu-id="19d48-121">Deployment phases</span></span>

<span data-ttu-id="19d48-122">建立 Microsoft 365 Defender 試用實驗室環境有三個階段。</span><span class="sxs-lookup"><span data-stu-id="19d48-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![部署階段：準備、安裝、板載](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="19d48-124">階段</span><span class="sxs-lookup"><span data-stu-id="19d48-124">Phase</span></span> | <span data-ttu-id="19d48-125">描述</span><span class="sxs-lookup"><span data-stu-id="19d48-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="19d48-126">階段 1：準備</span><span class="sxs-lookup"><span data-stu-id="19d48-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="19d48-127">深入瞭解在試用實驗室或試驗環境中部署 Microsoft 365 Defender 時，需要考慮的事項：</span><span class="sxs-lookup"><span data-stu-id="19d48-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="19d48-128">-專案關係人和簽核關</span><span class="sxs-lookup"><span data-stu-id="19d48-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="19d48-129">-環境考慮</span><span class="sxs-lookup"><span data-stu-id="19d48-129">- Environment considerations</span></span> <br><span data-ttu-id="19d48-130">-Access</span><span class="sxs-lookup"><span data-stu-id="19d48-130">- Access</span></span> <br><span data-ttu-id="19d48-131">-Azure Active Directory 安裝程式</span><span class="sxs-lookup"><span data-stu-id="19d48-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="19d48-132">-設定順序</span><span class="sxs-lookup"><span data-stu-id="19d48-132">- Configuration order</span></span>
|[<span data-ttu-id="19d48-133">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="19d48-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="19d48-134">採取初始步驟，存取 Microsoft 365 的安全性中心以設定 Microsoft 365 Defender 試用實驗室或試驗環境。</span><span class="sxs-lookup"><span data-stu-id="19d48-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="19d48-135">您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="19d48-135">You'll be guided to:</span></span><br><br><span data-ttu-id="19d48-136">-註冊 Microsoft 365 E5 試用版</span><span class="sxs-lookup"><span data-stu-id="19d48-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="19d48-137">-設定網域</span><span class="sxs-lookup"><span data-stu-id="19d48-137">- Configure domain</span></span><br><span data-ttu-id="19d48-138">-指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="19d48-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="19d48-139">-完成入口網站中的設定向導</span><span class="sxs-lookup"><span data-stu-id="19d48-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="19d48-140">階段3：設定板載 &</span><span class="sxs-lookup"><span data-stu-id="19d48-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="19d48-141">設定每個 Microsoft 365 Defender pillar 和板載端點。</span><span class="sxs-lookup"><span data-stu-id="19d48-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="19d48-142">您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="19d48-142">You'll be guided to:</span></span><br><br><span data-ttu-id="19d48-143">-針對 Office 365 設定 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="19d48-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="19d48-144">-設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="19d48-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="19d48-145">-設定 Microsoft Defender 身分識別</span><span class="sxs-lookup"><span data-stu-id="19d48-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="19d48-146">-設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="19d48-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="19d48-147">當您完成本指南之後，您將會發現相關的專案關係人和所需核准，具有正確的存取權限，已註冊試用、已設定的網域，以及每個 Microsoft 365 Defender 的支柱，而且您的端點會架至服務。</span><span class="sxs-lookup"><span data-stu-id="19d48-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="19d48-148">主要功能</span><span class="sxs-lookup"><span data-stu-id="19d48-148">Key capabilities</span></span>

<span data-ttu-id="19d48-149">雖然 Microsoft 365 Defender 提供許多功能，但此部署指南的主要目的是讓您開始使用上架裝置。</span><span class="sxs-lookup"><span data-stu-id="19d48-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="19d48-150">除了上架之外，本指南也可讓您開始使用下列功能。</span><span class="sxs-lookup"><span data-stu-id="19d48-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="19d48-151">功能</span><span class="sxs-lookup"><span data-stu-id="19d48-151">Capability</span></span> | <span data-ttu-id="19d48-152">描述</span><span class="sxs-lookup"><span data-stu-id="19d48-152">Description</span></span> 
:---|:---
<span data-ttu-id="19d48-153">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="19d48-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="19d48-154">協助保護整個 Office 365 從當今的威脅環境</span><span class="sxs-lookup"><span data-stu-id="19d48-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="19d48-155">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="19d48-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="19d48-156">識別並偵測遭到損害的身分識別和惡意的內幕人員動作威脅。</span><span class="sxs-lookup"><span data-stu-id="19d48-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="19d48-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="19d48-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="19d48-158">提供豐富的可見度、控制資料旅行，以及偵測不同雲端服務的 cyberthreats。</span><span class="sxs-lookup"><span data-stu-id="19d48-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="19d48-159">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="19d48-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="19d48-160">利用全面的端點安全性，防止、偵測及提供對高級威脅的回應功能。</span><span class="sxs-lookup"><span data-stu-id="19d48-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="19d48-161">在範圍內</span><span class="sxs-lookup"><span data-stu-id="19d48-161">In scope</span></span>

<span data-ttu-id="19d48-162">下列工作位於此指南的範圍內：</span><span class="sxs-lookup"><span data-stu-id="19d48-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="19d48-163">設定 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="19d48-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="19d48-164">設定 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19d48-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="19d48-165">在執行試驗時，註冊 Microsoft 365 E5 試用版或使用您的完整授權</span><span class="sxs-lookup"><span data-stu-id="19d48-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="19d48-166">設定網域</span><span class="sxs-lookup"><span data-stu-id="19d48-166">Configure domain</span></span>
    -   <span data-ttu-id="19d48-167">指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="19d48-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="19d48-168">在入口網站中完成安裝精靈</span><span class="sxs-lookup"><span data-stu-id="19d48-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="19d48-169">根據最佳作法設定所有 Microsoft 365 Defender 的支柱</span><span class="sxs-lookup"><span data-stu-id="19d48-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="19d48-170">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="19d48-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="19d48-171">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="19d48-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="19d48-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="19d48-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="19d48-173">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="19d48-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="19d48-174">超出範圍</span><span class="sxs-lookup"><span data-stu-id="19d48-174">Out of scope</span></span>

<span data-ttu-id="19d48-175">下列專案不在本部署指南的範圍內：</span><span class="sxs-lookup"><span data-stu-id="19d48-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="19d48-176">設定可能與 Microsoft 365 Defender 整合的協力廠商解決方案</span><span class="sxs-lookup"><span data-stu-id="19d48-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="19d48-177">實際執行環境中的滲透測試</span><span class="sxs-lookup"><span data-stu-id="19d48-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="19d48-178">後續步驟</span><span class="sxs-lookup"><span data-stu-id="19d48-178">Next step</span></span>
<span data-ttu-id="19d48-179">[階段1：準備](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="19d48-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="19d48-180">準備您的 Microsoft 365 Defender 試用實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="19d48-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
