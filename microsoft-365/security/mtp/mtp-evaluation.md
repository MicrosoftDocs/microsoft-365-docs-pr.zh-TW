---
title: 評估 Microsoft 365 Defender
description: 設定您的 Microsoft 365 Defender 試用版實驗室或試驗環境，以嘗試並體驗專為保護貴組織中裝置、身分識別、資料和應用程式所設計的安全性解決方案。
keywords: Microsoft 威脅防護試用版，試用 Microsoft 威脅防護，評估 Microsoft 威脅防護，Microsoft 威脅防護評估實驗室，Microsoft 威脅防護試驗，網路安全性，進一步持續性威脅，企業安全性、裝置、裝置、身分識別、使用者、資料、應用程式、事件、自動化調查與補救、進一步搜尋
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930207"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="cfe5b-104">建立 Microsoft 365 Defender 試用版實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="cfe5b-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cfe5b-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="cfe5b-105">**Applies to:**</span></span>
- <span data-ttu-id="cfe5b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cfe5b-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="cfe5b-107">本指南可協助您與使用者和群組一起設定實驗室環境，然後引導您完成 Microsoft 365 Defender 功能設定，以模仿威脅攻擊並取得有意義的試驗結果。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="cfe5b-108">建立此試驗實驗室或試驗環境的目的是說明全面且整合的 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="cfe5b-109">體驗此智慧型安全性解決方案如何偵測、防止、自動調查及回應貴組織的進一步威脅。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="cfe5b-110">系統將會引導您完成這些步驟，以根據建議的部署路徑啟動您的 Microsoft 365 Defender 評估。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="cfe5b-111">目標是要協助您將安全性解決方案設定在有試用版帳戶的實驗室環境中，或在具有完整授權之生產環境的試驗環境中。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="cfe5b-112">準備您的試驗實驗室或試驗環境可協助您將安全性作業使用案例呈現給貴組織的決策者。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="cfe5b-113">當您執行完攻擊模擬並滿意結果之後，您可以在貴組織中利用 Microsoft 技術銷售專業人員或專家的協助，在組織中完全部署和運作。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="cfe5b-114">本指南將可協助您：</span><span class="sxs-lookup"><span data-stu-id="cfe5b-114">This guide will help you:</span></span>
- <span data-ttu-id="cfe5b-115">設定實驗室服務器和電腦</span><span class="sxs-lookup"><span data-stu-id="cfe5b-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="cfe5b-116">設定 Active Directory 與使用者和群組</span><span class="sxs-lookup"><span data-stu-id="cfe5b-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="cfe5b-117">設定 Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint，以及 Microsoft Cloud App 安全性</span><span class="sxs-lookup"><span data-stu-id="cfe5b-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="cfe5b-118">設定伺服器和電腦的本地策略</span><span class="sxs-lookup"><span data-stu-id="cfe5b-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="cfe5b-119">在 Microsoft 365 Defender 中模仿威脅攻擊來產生測試事件或警示</span><span class="sxs-lookup"><span data-stu-id="cfe5b-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="cfe5b-120">為獲得最佳結果，請盡可能遵循實驗室設定指示。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="cfe5b-121">部署階段</span><span class="sxs-lookup"><span data-stu-id="cfe5b-121">Deployment phases</span></span>

<span data-ttu-id="cfe5b-122">建立 Microsoft 365 Defender 試用版實驗室環境有三個階段。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![部署階段：準備、設定、上機](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="cfe5b-124">階段</span><span class="sxs-lookup"><span data-stu-id="cfe5b-124">Phase</span></span> | <span data-ttu-id="cfe5b-125">說明</span><span class="sxs-lookup"><span data-stu-id="cfe5b-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="cfe5b-126">階段 1：準備</span><span class="sxs-lookup"><span data-stu-id="cfe5b-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="cfe5b-127">瞭解在試驗室或試驗環境中部署 Microsoft 365 Defender 時需考慮哪些專案：</span><span class="sxs-lookup"><span data-stu-id="cfe5b-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="cfe5b-128">- 專案關係人與簽簽</span><span class="sxs-lookup"><span data-stu-id="cfe5b-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="cfe5b-129">- 環境考慮</span><span class="sxs-lookup"><span data-stu-id="cfe5b-129">- Environment considerations</span></span> <br><span data-ttu-id="cfe5b-130">- Access</span><span class="sxs-lookup"><span data-stu-id="cfe5b-130">- Access</span></span> <br><span data-ttu-id="cfe5b-131">- Azure Active Directory 設定</span><span class="sxs-lookup"><span data-stu-id="cfe5b-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="cfe5b-132">- 組組順序</span><span class="sxs-lookup"><span data-stu-id="cfe5b-132">- Configuration order</span></span>
|[<span data-ttu-id="cfe5b-133">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="cfe5b-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="cfe5b-134">採取初始步驟來存取 Microsoft 365 資訊安全中心，以設定您的 Microsoft 365 Defender 試用版實驗室或試驗環境。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="cfe5b-135">系統將會引導您進行：</span><span class="sxs-lookup"><span data-stu-id="cfe5b-135">You'll be guided to:</span></span><br><br><span data-ttu-id="cfe5b-136">- 註冊 Microsoft 365 E5 試用版</span><span class="sxs-lookup"><span data-stu-id="cfe5b-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="cfe5b-137">- 設定網域</span><span class="sxs-lookup"><span data-stu-id="cfe5b-137">- Configure domain</span></span><br><span data-ttu-id="cfe5b-138">- 指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="cfe5b-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="cfe5b-139">- 完成入口網站中的設定精靈</span><span class="sxs-lookup"><span data-stu-id="cfe5b-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="cfe5b-140">階段 3：設定&上</span><span class="sxs-lookup"><span data-stu-id="cfe5b-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="cfe5b-141">設定每個 Microsoft 365 Defender 基礎和上線端點。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="cfe5b-142">系統將會引導您進行：</span><span class="sxs-lookup"><span data-stu-id="cfe5b-142">You'll be guided to:</span></span><br><br><span data-ttu-id="cfe5b-143">- 設定 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cfe5b-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="cfe5b-144">- 設定 Microsoft Cloud App 安全性</span><span class="sxs-lookup"><span data-stu-id="cfe5b-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="cfe5b-145">- 設定 Microsoft Defender 的身分識別</span><span class="sxs-lookup"><span data-stu-id="cfe5b-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="cfe5b-146">- 設定 Microsoft Defender 端點</span><span class="sxs-lookup"><span data-stu-id="cfe5b-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="cfe5b-147">完成本指南之後，您將識別出涉及的關係人並取得所需的核准、擁有正確的存取權限、已註冊試用版、已設好網域和每個 Microsoft 365 Defender 基礎，您的端點就會上線至服務。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="cfe5b-148">主要功能</span><span class="sxs-lookup"><span data-stu-id="cfe5b-148">Key capabilities</span></span>

<span data-ttu-id="cfe5b-149">雖然 Microsoft 365 Defender 提供許多功能，但本部署指南的主要用途是引導您上線裝置。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="cfe5b-150">除了上手之外，此指引還可引導您開始使用下列功能。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="cfe5b-151">功能</span><span class="sxs-lookup"><span data-stu-id="cfe5b-151">Capability</span></span> | <span data-ttu-id="cfe5b-152">描述</span><span class="sxs-lookup"><span data-stu-id="cfe5b-152">Description</span></span> 
:---|:---
<span data-ttu-id="cfe5b-153">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cfe5b-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="cfe5b-154">協助保護您的整個 Office 365 服務不受現今的威脅</span><span class="sxs-lookup"><span data-stu-id="cfe5b-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="cfe5b-155">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cfe5b-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="cfe5b-156">識別並偵測身分識別遭到入侵和惡意測試人員動作的威脅。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="cfe5b-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cfe5b-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="cfe5b-158">提供豐富的可見度、控制資料旅行，以及偵測雲端服務中的網路威脅。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="cfe5b-159">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cfe5b-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="cfe5b-160">以完整的端點安全性防止、偵測進一步威脅並提供回應功能。</span><span class="sxs-lookup"><span data-stu-id="cfe5b-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="cfe5b-161">範圍中</span><span class="sxs-lookup"><span data-stu-id="cfe5b-161">In scope</span></span>

<span data-ttu-id="cfe5b-162">本指南將說明下列工作：</span><span class="sxs-lookup"><span data-stu-id="cfe5b-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="cfe5b-163">設定 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cfe5b-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="cfe5b-164">設定 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cfe5b-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="cfe5b-165">註冊 Microsoft 365 E5 試用版，或如果您執行試驗，請使用您的完整授權</span><span class="sxs-lookup"><span data-stu-id="cfe5b-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="cfe5b-166">設定網域</span><span class="sxs-lookup"><span data-stu-id="cfe5b-166">Configure domain</span></span>
    -   <span data-ttu-id="cfe5b-167">指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="cfe5b-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="cfe5b-168">完成入口網站中的設定精靈</span><span class="sxs-lookup"><span data-stu-id="cfe5b-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="cfe5b-169">根據最佳做法設定所有 Microsoft 365 Defender 基礎</span><span class="sxs-lookup"><span data-stu-id="cfe5b-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="cfe5b-170">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cfe5b-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="cfe5b-171">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cfe5b-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="cfe5b-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cfe5b-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="cfe5b-173">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cfe5b-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="cfe5b-174">超出範圍</span><span class="sxs-lookup"><span data-stu-id="cfe5b-174">Out of scope</span></span>

<span data-ttu-id="cfe5b-175">以下是本部署指南的範圍外：</span><span class="sxs-lookup"><span data-stu-id="cfe5b-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="cfe5b-176">可能與 Microsoft 365 Defender 整合的協力廠商解決方案組配置</span><span class="sxs-lookup"><span data-stu-id="cfe5b-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="cfe5b-177">生產環境中的測試測試</span><span class="sxs-lookup"><span data-stu-id="cfe5b-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="cfe5b-178">下一步</span><span class="sxs-lookup"><span data-stu-id="cfe5b-178">Next step</span></span>
<span data-ttu-id="cfe5b-179">[階段 1：準備](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="cfe5b-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="cfe5b-180">準備您的 Microsoft 365 Defender 試用版實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="cfe5b-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
