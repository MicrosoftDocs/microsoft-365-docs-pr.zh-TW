---
title: 評估 Microsoft 威脅防護
description: 設定您的 Microsoft 威脅防護試用實驗室或試驗環境，以嘗試如何設計用來保護裝置、身分識別、資料和應用程式的協同威脅防護解決方案，可協助您的組織
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 62852dfe75794d5d0e33453f978967fff40813e1
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816934"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="a7ae9-104">建立 Microsoft 威脅防護試用實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="a7ae9-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

<span data-ttu-id="a7ae9-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a7ae9-105">**Applies to:**</span></span>
- <span data-ttu-id="a7ae9-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="a7ae9-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a7ae9-107">建立此試用實驗室或試驗環境的目的，是為了示範 Microsoft 威脅防護的綜合、整合及智慧功能，可在組織中使用偵測、防護、調查和回應。</span><span class="sxs-lookup"><span data-stu-id="a7ae9-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="a7ae9-108">本指南會逐步引導您逐步開始 Microsoft 威脅防護評估，以建議的部署路徑為基礎。</span><span class="sxs-lookup"><span data-stu-id="a7ae9-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="a7ae9-109">目標是在使用試用帳戶時，或在使用完整授權時在實際執行環境中，協助您設定實驗室環境中的整合式 Microsoft 威脅防護服務。</span><span class="sxs-lookup"><span data-stu-id="a7ae9-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment when using a trial account, or in a pilot environment in production when using a full license.</span></span> <span data-ttu-id="a7ae9-110">在您的組織中提供安全性作業使用案例給安全性解決方案決策者時，其結果將十分有用。</span><span class="sxs-lookup"><span data-stu-id="a7ae9-110">The results of which will be useful in presenting security operation use cases to security solution decision makers in your organization.</span></span> <span data-ttu-id="a7ae9-111">當您執行攻擊模擬後，如果結果符合，您可以使用 Microsoft 技術銷售人員或組織中的專家的協助，在組織中完整部署及 operationalize。</span><span class="sxs-lookup"><span data-stu-id="a7ae9-111">When you’re done running your attack simulations, and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="a7ae9-112">本指南將協助您：</span><span class="sxs-lookup"><span data-stu-id="a7ae9-112">This guide will help you:</span></span>
- <span data-ttu-id="a7ae9-113">設定實驗室服務器和電腦</span><span class="sxs-lookup"><span data-stu-id="a7ae9-113">Set up your lab server and computers</span></span>
- <span data-ttu-id="a7ae9-114">使用使用者和群組設定 Active Directory</span><span class="sxs-lookup"><span data-stu-id="a7ae9-114">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="a7ae9-115">安裝和設定 Azure ATP、Office ATP、Microsoft Defender ATP 和 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a7ae9-115">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="a7ae9-116">設定伺服器和電腦的本機原則</span><span class="sxs-lookup"><span data-stu-id="a7ae9-116">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="a7ae9-117">模仿威脅攻擊，以在 Microsoft 威脅防護中產生測試事件或警示</span><span class="sxs-lookup"><span data-stu-id="a7ae9-117">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="a7ae9-118">為了獲得最佳結果，請盡可能遵循實驗室設定指示。</span><span class="sxs-lookup"><span data-stu-id="a7ae9-118">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="a7ae9-119">部署階段</span><span class="sxs-lookup"><span data-stu-id="a7ae9-119">Deployment phases</span></span>

<span data-ttu-id="a7ae9-120">建立 Microsoft 威脅防護試用實驗室環境並部署它時，有三個階段：</span><span class="sxs-lookup"><span data-stu-id="a7ae9-120">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="a7ae9-121">階段</span><span class="sxs-lookup"><span data-stu-id="a7ae9-121">Phase</span></span> | <span data-ttu-id="a7ae9-122">說明</span><span class="sxs-lookup"><span data-stu-id="a7ae9-122">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="a7ae9-123">![階段1：準備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="a7ae9-123">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="a7ae9-124">階段1：準備</span><span class="sxs-lookup"><span data-stu-id="a7ae9-124">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="a7ae9-125">深入瞭解在試用實驗室或試驗環境中部署 Microsoft 威脅防護時，需要考慮的事項：</span><span class="sxs-lookup"><span data-stu-id="a7ae9-125">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="a7ae9-126">-專案關係人和簽核關</span><span class="sxs-lookup"><span data-stu-id="a7ae9-126">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="a7ae9-127">-環境考慮</span><span class="sxs-lookup"><span data-stu-id="a7ae9-127">- Environment considerations</span></span> <br><span data-ttu-id="a7ae9-128">-Access</span><span class="sxs-lookup"><span data-stu-id="a7ae9-128">- Access</span></span> <br><span data-ttu-id="a7ae9-129">-Azure Active Directory 安裝程式</span><span class="sxs-lookup"><span data-stu-id="a7ae9-129">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="a7ae9-130">-設定順序</span><span class="sxs-lookup"><span data-stu-id="a7ae9-130">- Configuration order</span></span>
|  <span data-ttu-id="a7ae9-131">![階段2：設定](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="a7ae9-131">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="a7ae9-132">階段2：設定</span><span class="sxs-lookup"><span data-stu-id="a7ae9-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="a7ae9-133">請先取得存取 Microsoft 365 安全中心的初始步驟，以設定您的 Microsoft 威脅防護試用實驗室或試驗環境。</span><span class="sxs-lookup"><span data-stu-id="a7ae9-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="a7ae9-134">您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="a7ae9-134">You'll be guided to:</span></span><br><br><span data-ttu-id="a7ae9-135">-註冊 Microsoft 365 E5 試用版</span><span class="sxs-lookup"><span data-stu-id="a7ae9-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="a7ae9-136">-設定網域</span><span class="sxs-lookup"><span data-stu-id="a7ae9-136">- Configure domain</span></span><br><span data-ttu-id="a7ae9-137">-指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="a7ae9-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="a7ae9-138">-完成入口網站中的設定向導</span><span class="sxs-lookup"><span data-stu-id="a7ae9-138">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="a7ae9-139">![階段3：設定板載 &](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="a7ae9-139">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="a7ae9-140">階段3：設定板載 &</span><span class="sxs-lookup"><span data-stu-id="a7ae9-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="a7ae9-141">設定每個 Microsoft 威脅防護 pillar 和板載端點。</span><span class="sxs-lookup"><span data-stu-id="a7ae9-141">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="a7ae9-142">您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="a7ae9-142">You'll be guided to:</span></span><br><br><span data-ttu-id="a7ae9-143">-設定 Office 365 的高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="a7ae9-143">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="a7ae9-144">-設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a7ae9-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="a7ae9-145">-設定 Azure 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="a7ae9-145">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="a7ae9-146">-設定 Microsoft Defender 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="a7ae9-146">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="a7ae9-147">在範圍內</span><span class="sxs-lookup"><span data-stu-id="a7ae9-147">In scope</span></span>

<span data-ttu-id="a7ae9-148">下列工作位於此指南的範圍內：</span><span class="sxs-lookup"><span data-stu-id="a7ae9-148">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="a7ae9-149">設定 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a7ae9-149">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="a7ae9-150">設定 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="a7ae9-150">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="a7ae9-151">註冊 Microsoft 365 E5 試用版，如果您正在執行試驗，請使用您的完整授權</span><span class="sxs-lookup"><span data-stu-id="a7ae9-151">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="a7ae9-152">設定網域</span><span class="sxs-lookup"><span data-stu-id="a7ae9-152">Configure domain</span></span>
    -   <span data-ttu-id="a7ae9-153">指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="a7ae9-153">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="a7ae9-154">在入口網站中完成安裝精靈</span><span class="sxs-lookup"><span data-stu-id="a7ae9-154">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="a7ae9-155">根據最佳作法設定所有 Microsoft 威脅防護支柱</span><span class="sxs-lookup"><span data-stu-id="a7ae9-155">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="a7ae9-156">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="a7ae9-156">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="a7ae9-157">Azure 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="a7ae9-157">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="a7ae9-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a7ae9-158">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="a7ae9-159">Microsoft Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="a7ae9-159">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="a7ae9-160">超出範圍</span><span class="sxs-lookup"><span data-stu-id="a7ae9-160">Out of scope</span></span>

<span data-ttu-id="a7ae9-161">下列專案不在本部署指南的範圍內：</span><span class="sxs-lookup"><span data-stu-id="a7ae9-161">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="a7ae9-162">設定可能會與 Microsoft 威脅防護整合的協力廠商解決方案</span><span class="sxs-lookup"><span data-stu-id="a7ae9-162">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="a7ae9-163">實際執行環境中的滲透測試</span><span class="sxs-lookup"><span data-stu-id="a7ae9-163">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="a7ae9-164">後續步驟</span><span class="sxs-lookup"><span data-stu-id="a7ae9-164">Next step</span></span>
<span data-ttu-id="a7ae9-165">![階段1：準備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="a7ae9-165">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="a7ae9-166">[階段1：準備](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="a7ae9-166">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="a7ae9-167">準備您的 Microsoft 威脅防護試用實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="a7ae9-167">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
