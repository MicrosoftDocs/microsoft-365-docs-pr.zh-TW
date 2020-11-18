---
title: 評估 Microsoft 365 Defender
description: 設定您的 Microsoft 365 Defender 試用實驗室或試驗環境，以嘗試用來保護組織中裝置、身分識別、資料和應用程式的安全性解決方案。
keywords: Microsoft 威脅防護試用版，請嘗試 Microsoft 威脅防護，評估 Microsoft 威脅防護，Microsoft 威脅防護實驗，Microsoft 威脅防護試驗，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: fe0a06dd104f0f0532363ee046f4bad1c03c5400
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130875"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="5f5ab-104">建立 Microsoft 365 Defender 試用實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="5f5ab-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5f5ab-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="5f5ab-105">**Applies to:**</span></span>
- <span data-ttu-id="5f5ab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f5ab-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5f5ab-107">建立此試用實驗室或試驗環境的目的，是為了示範綜合性和整合的 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="5f5ab-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="5f5ab-108">體驗這種聰明的安全性解決方案如何偵測、避免、自動調查，並回應貴組織的高級威脅。</span><span class="sxs-lookup"><span data-stu-id="5f5ab-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="5f5ab-109">本指南會逐步引導您執行 Microsoft 365 Defender 評估，並以建議的部署路徑為基礎。</span><span class="sxs-lookup"><span data-stu-id="5f5ab-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="5f5ab-110">其目標是協助您在實驗環境中設定安全性解決方案，以試用帳戶，或在實際執行環境中使用完整授權。</span><span class="sxs-lookup"><span data-stu-id="5f5ab-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="5f5ab-111">準備您的試用實驗室或試驗環境可協助您向組織中的決策者展示安全性運作案例。</span><span class="sxs-lookup"><span data-stu-id="5f5ab-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="5f5ab-112">當您執行攻擊模擬並符合結果時，您可以使用 Microsoft 技術銷售人員或組織中的專家的說明，在組織中完整部署及 operationalize。</span><span class="sxs-lookup"><span data-stu-id="5f5ab-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="5f5ab-113">本指南將協助您：</span><span class="sxs-lookup"><span data-stu-id="5f5ab-113">This guide will help you:</span></span>
- <span data-ttu-id="5f5ab-114">設定實驗室服務器和電腦</span><span class="sxs-lookup"><span data-stu-id="5f5ab-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="5f5ab-115">使用使用者和群組設定 Active Directory</span><span class="sxs-lookup"><span data-stu-id="5f5ab-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="5f5ab-116">安裝和設定 Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint 和 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5f5ab-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="5f5ab-117">設定伺服器和電腦的本機原則</span><span class="sxs-lookup"><span data-stu-id="5f5ab-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="5f5ab-118">模仿威脅攻擊，以在 Microsoft 365 Defender 中產生測試事件或警示</span><span class="sxs-lookup"><span data-stu-id="5f5ab-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="5f5ab-119">為了獲得最佳結果，請盡可能遵循實驗室設定指示。</span><span class="sxs-lookup"><span data-stu-id="5f5ab-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="5f5ab-120">部署階段</span><span class="sxs-lookup"><span data-stu-id="5f5ab-120">Deployment phases</span></span>

<span data-ttu-id="5f5ab-121">建立 Microsoft 365 Defender 試用實驗室環境並部署它時，有三個階段：</span><span class="sxs-lookup"><span data-stu-id="5f5ab-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

![部署階段：準備、安裝、板載](../../media/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="5f5ab-123">階段</span><span class="sxs-lookup"><span data-stu-id="5f5ab-123">Phase</span></span> | <span data-ttu-id="5f5ab-124">描述</span><span class="sxs-lookup"><span data-stu-id="5f5ab-124">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="5f5ab-125">階段1：準備</span><span class="sxs-lookup"><span data-stu-id="5f5ab-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="5f5ab-126">深入瞭解在試用實驗室或試驗環境中部署 Microsoft 365 Defender 時，需要考慮的事項：</span><span class="sxs-lookup"><span data-stu-id="5f5ab-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="5f5ab-127">-專案關係人和簽核關</span><span class="sxs-lookup"><span data-stu-id="5f5ab-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="5f5ab-128">-環境考慮</span><span class="sxs-lookup"><span data-stu-id="5f5ab-128">- Environment considerations</span></span> <br><span data-ttu-id="5f5ab-129">-Access</span><span class="sxs-lookup"><span data-stu-id="5f5ab-129">- Access</span></span> <br><span data-ttu-id="5f5ab-130">-Azure Active Directory 安裝程式</span><span class="sxs-lookup"><span data-stu-id="5f5ab-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="5f5ab-131">-設定順序</span><span class="sxs-lookup"><span data-stu-id="5f5ab-131">- Configuration order</span></span>
|[<span data-ttu-id="5f5ab-132">階段2：設定</span><span class="sxs-lookup"><span data-stu-id="5f5ab-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="5f5ab-133">請先取得存取 Microsoft 365 安全中心的初始步驟，以設定您的 Microsoft 365 Defender 試用實驗室或試驗環境。</span><span class="sxs-lookup"><span data-stu-id="5f5ab-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="5f5ab-134">您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="5f5ab-134">You'll be guided to:</span></span><br><br><span data-ttu-id="5f5ab-135">-註冊 Microsoft 365 E5 試用版</span><span class="sxs-lookup"><span data-stu-id="5f5ab-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="5f5ab-136">-設定網域</span><span class="sxs-lookup"><span data-stu-id="5f5ab-136">- Configure domain</span></span><br><span data-ttu-id="5f5ab-137">-指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="5f5ab-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="5f5ab-138">-完成入口網站中的設定向導</span><span class="sxs-lookup"><span data-stu-id="5f5ab-138">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="5f5ab-139">階段3：設定板載 &</span><span class="sxs-lookup"><span data-stu-id="5f5ab-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="5f5ab-140">設定每個 Microsoft 365 Defender pillar 和板載端點。</span><span class="sxs-lookup"><span data-stu-id="5f5ab-140">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="5f5ab-141">您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="5f5ab-141">You'll be guided to:</span></span><br><br><span data-ttu-id="5f5ab-142">-針對 Office 365 設定 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5f5ab-142">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="5f5ab-143">-設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5f5ab-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="5f5ab-144">-設定 Microsoft Defender 身分識別</span><span class="sxs-lookup"><span data-stu-id="5f5ab-144">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="5f5ab-145">-設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5f5ab-145">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="5f5ab-146">在範圍內</span><span class="sxs-lookup"><span data-stu-id="5f5ab-146">In scope</span></span>

<span data-ttu-id="5f5ab-147">下列工作位於此指南的範圍內：</span><span class="sxs-lookup"><span data-stu-id="5f5ab-147">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="5f5ab-148">設定 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5f5ab-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="5f5ab-149">設定 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f5ab-149">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="5f5ab-150">註冊 Microsoft 365 E5 試用版，如果您正在執行試驗，請使用您的完整授權</span><span class="sxs-lookup"><span data-stu-id="5f5ab-150">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="5f5ab-151">設定網域</span><span class="sxs-lookup"><span data-stu-id="5f5ab-151">Configure domain</span></span>
    -   <span data-ttu-id="5f5ab-152">指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="5f5ab-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="5f5ab-153">在入口網站中完成安裝精靈</span><span class="sxs-lookup"><span data-stu-id="5f5ab-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="5f5ab-154">根據最佳作法設定所有 Microsoft 365 Defender 支柱</span><span class="sxs-lookup"><span data-stu-id="5f5ab-154">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="5f5ab-155">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5f5ab-155">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="5f5ab-156">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5f5ab-156">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="5f5ab-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5f5ab-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="5f5ab-158">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5f5ab-158">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="5f5ab-159">超出範圍</span><span class="sxs-lookup"><span data-stu-id="5f5ab-159">Out of scope</span></span>

<span data-ttu-id="5f5ab-160">下列專案不在本部署指南的範圍內：</span><span class="sxs-lookup"><span data-stu-id="5f5ab-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="5f5ab-161">設定可能會與 Microsoft 365 Defender 整合的協力廠商解決方案</span><span class="sxs-lookup"><span data-stu-id="5f5ab-161">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="5f5ab-162">實際執行環境中的滲透測試</span><span class="sxs-lookup"><span data-stu-id="5f5ab-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="5f5ab-163">後續步驟</span><span class="sxs-lookup"><span data-stu-id="5f5ab-163">Next step</span></span>
<span data-ttu-id="5f5ab-164">[階段1：準備](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="5f5ab-164">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="5f5ab-165">準備您的 Microsoft 365 Defender 試用實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="5f5ab-165">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
