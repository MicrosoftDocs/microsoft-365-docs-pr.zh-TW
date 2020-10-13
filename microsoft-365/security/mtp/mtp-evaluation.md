---
title: 評估 Microsoft 威脅防護
description: 設定您的 Microsoft 威脅防護試用實驗室或試驗環境，以嘗試用來保護組織中裝置、身分識別、資料和應用程式的安全性解決方案。
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
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447116"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="a45f7-104">建立 Microsoft 威脅防護試用實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="a45f7-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a45f7-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a45f7-105">**Applies to:**</span></span>
- <span data-ttu-id="a45f7-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="a45f7-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a45f7-107">建立此試用實驗室或試驗環境的目的是為了示範綜合和整合的 Microsoft 威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="a45f7-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="a45f7-108">體驗這種聰明的安全性解決方案如何偵測、避免、自動調查，並回應貴組織的高級威脅。</span><span class="sxs-lookup"><span data-stu-id="a45f7-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="a45f7-109">本指南會逐步引導您逐步開始 Microsoft 威脅防護評估，以建議的部署路徑為基礎。</span><span class="sxs-lookup"><span data-stu-id="a45f7-109">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="a45f7-110">其目標是協助您在實驗環境中設定安全性解決方案，以試用帳戶，或在實際執行環境中使用完整授權。</span><span class="sxs-lookup"><span data-stu-id="a45f7-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="a45f7-111">準備您的試用實驗室或試驗環境可協助您向組織中的決策者展示安全性運作案例。</span><span class="sxs-lookup"><span data-stu-id="a45f7-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="a45f7-112">當您執行攻擊模擬並符合結果時，您可以使用 Microsoft 技術銷售人員或組織中的專家的說明，在組織中完整部署及 operationalize。</span><span class="sxs-lookup"><span data-stu-id="a45f7-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="a45f7-113">本指南將協助您：</span><span class="sxs-lookup"><span data-stu-id="a45f7-113">This guide will help you:</span></span>
- <span data-ttu-id="a45f7-114">設定實驗室服務器和電腦</span><span class="sxs-lookup"><span data-stu-id="a45f7-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="a45f7-115">使用使用者和群組設定 Active Directory</span><span class="sxs-lookup"><span data-stu-id="a45f7-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="a45f7-116">安裝和設定 Azure ATP、Office ATP、Microsoft Defender ATP 和 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a45f7-116">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="a45f7-117">設定伺服器和電腦的本機原則</span><span class="sxs-lookup"><span data-stu-id="a45f7-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="a45f7-118">模仿威脅攻擊，以在 Microsoft 威脅防護中產生測試事件或警示</span><span class="sxs-lookup"><span data-stu-id="a45f7-118">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="a45f7-119">為了獲得最佳結果，請盡可能遵循實驗室設定指示。</span><span class="sxs-lookup"><span data-stu-id="a45f7-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="a45f7-120">部署階段</span><span class="sxs-lookup"><span data-stu-id="a45f7-120">Deployment phases</span></span>

<span data-ttu-id="a45f7-121">建立 Microsoft 威脅防護試用實驗室環境並部署它時，有三個階段：</span><span class="sxs-lookup"><span data-stu-id="a45f7-121">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="a45f7-122">階段</span><span class="sxs-lookup"><span data-stu-id="a45f7-122">Phase</span></span> | <span data-ttu-id="a45f7-123">描述</span><span class="sxs-lookup"><span data-stu-id="a45f7-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="a45f7-124">![階段1：準備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="a45f7-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="a45f7-125">階段1：準備</span><span class="sxs-lookup"><span data-stu-id="a45f7-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="a45f7-126">深入瞭解在試用實驗室或試驗環境中部署 Microsoft 威脅防護時，需要考慮的事項：</span><span class="sxs-lookup"><span data-stu-id="a45f7-126">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="a45f7-127">-專案關係人和簽核關</span><span class="sxs-lookup"><span data-stu-id="a45f7-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="a45f7-128">-環境考慮</span><span class="sxs-lookup"><span data-stu-id="a45f7-128">- Environment considerations</span></span> <br><span data-ttu-id="a45f7-129">-Access</span><span class="sxs-lookup"><span data-stu-id="a45f7-129">- Access</span></span> <br><span data-ttu-id="a45f7-130">-Azure Active Directory 安裝程式</span><span class="sxs-lookup"><span data-stu-id="a45f7-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="a45f7-131">-設定順序</span><span class="sxs-lookup"><span data-stu-id="a45f7-131">- Configuration order</span></span>
|  <span data-ttu-id="a45f7-132">![階段2：設定](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="a45f7-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="a45f7-133">階段2：設定</span><span class="sxs-lookup"><span data-stu-id="a45f7-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="a45f7-134">請先取得存取 Microsoft 365 安全中心的初始步驟，以設定您的 Microsoft 威脅防護試用實驗室或試驗環境。</span><span class="sxs-lookup"><span data-stu-id="a45f7-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="a45f7-135">您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="a45f7-135">You'll be guided to:</span></span><br><br><span data-ttu-id="a45f7-136">-註冊 Microsoft 365 E5 試用版</span><span class="sxs-lookup"><span data-stu-id="a45f7-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="a45f7-137">-設定網域</span><span class="sxs-lookup"><span data-stu-id="a45f7-137">- Configure domain</span></span><br><span data-ttu-id="a45f7-138">-指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="a45f7-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="a45f7-139">-完成入口網站中的設定向導</span><span class="sxs-lookup"><span data-stu-id="a45f7-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="a45f7-140">![階段3：設定板載 &](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="a45f7-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="a45f7-141">階段3：設定板載 &</span><span class="sxs-lookup"><span data-stu-id="a45f7-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="a45f7-142">設定每個 Microsoft 威脅防護 pillar 和板載端點。</span><span class="sxs-lookup"><span data-stu-id="a45f7-142">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="a45f7-143">您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="a45f7-143">You'll be guided to:</span></span><br><br><span data-ttu-id="a45f7-144">-設定 Office 365 的高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="a45f7-144">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="a45f7-145">-設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a45f7-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="a45f7-146">-設定 Azure 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="a45f7-146">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="a45f7-147">-設定 Microsoft Defender 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="a45f7-147">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="a45f7-148">在範圍內</span><span class="sxs-lookup"><span data-stu-id="a45f7-148">In scope</span></span>

<span data-ttu-id="a45f7-149">下列工作位於此指南的範圍內：</span><span class="sxs-lookup"><span data-stu-id="a45f7-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="a45f7-150">設定 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a45f7-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="a45f7-151">設定 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="a45f7-151">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="a45f7-152">註冊 Microsoft 365 E5 試用版，如果您正在執行試驗，請使用您的完整授權</span><span class="sxs-lookup"><span data-stu-id="a45f7-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="a45f7-153">設定網域</span><span class="sxs-lookup"><span data-stu-id="a45f7-153">Configure domain</span></span>
    -   <span data-ttu-id="a45f7-154">指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="a45f7-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="a45f7-155">在入口網站中完成安裝精靈</span><span class="sxs-lookup"><span data-stu-id="a45f7-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="a45f7-156">根據最佳作法設定所有 Microsoft 威脅防護支柱</span><span class="sxs-lookup"><span data-stu-id="a45f7-156">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="a45f7-157">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="a45f7-157">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="a45f7-158">Azure 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="a45f7-158">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="a45f7-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a45f7-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="a45f7-160">Microsoft Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="a45f7-160">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="a45f7-161">超出範圍</span><span class="sxs-lookup"><span data-stu-id="a45f7-161">Out of scope</span></span>

<span data-ttu-id="a45f7-162">下列專案不在本部署指南的範圍內：</span><span class="sxs-lookup"><span data-stu-id="a45f7-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="a45f7-163">設定可能會與 Microsoft 威脅防護整合的協力廠商解決方案</span><span class="sxs-lookup"><span data-stu-id="a45f7-163">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="a45f7-164">實際執行環境中的滲透測試</span><span class="sxs-lookup"><span data-stu-id="a45f7-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="a45f7-165">下一步</span><span class="sxs-lookup"><span data-stu-id="a45f7-165">Next step</span></span>
<span data-ttu-id="a45f7-166">![階段1：準備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="a45f7-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="a45f7-167">[階段1：準備](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="a45f7-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="a45f7-168">準備您的 Microsoft 威脅防護試用實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="a45f7-168">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
