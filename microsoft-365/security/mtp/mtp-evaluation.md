---
title: 評估 Microsoft 威脅防護
description: 設定您的 Microsoft 威脅防護試用實驗室環境，以嘗試如何設計用來保護裝置、身分識別、資料和應用程式的協同威脅防護解決方案，可協助您的組織
keywords: Microsoft 威脅防護試用版，請嘗試 Microsoft 威脅防護，評估 Microsoft 威脅防護，Microsoft 威脅防護實驗室，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
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
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049636"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="f1316-104">建立 Microsoft 威脅防護試用實驗室環境</span><span class="sxs-lookup"><span data-stu-id="f1316-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="f1316-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f1316-105">**Applies to:**</span></span>
- <span data-ttu-id="f1316-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="f1316-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f1316-107">建立此試用實驗室環境的目的是為了說明可在組織中使用的偵測、防護、調查和回應中，Microsoft 威脅防護的綜合、整合及智慧功能。</span><span class="sxs-lookup"><span data-stu-id="f1316-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="f1316-108">本指南會逐步引導您逐步開始 Microsoft 威脅防護評估，以建議的部署路徑為基礎。</span><span class="sxs-lookup"><span data-stu-id="f1316-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="f1316-109">其目標是協助您設定實驗室環境中的整合式 Microsoft 威脅防護服務，或在組織中向安全性解決方案決策者展示時，做為概念證明（POC）。</span><span class="sxs-lookup"><span data-stu-id="f1316-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="f1316-110">當您執行攻擊模擬時，會自動調查和回應，並對結果滿意，您可以使用 Microsoft 技術銷售人員或您組織中的專家協助，在實際執行環境中部署它。</span><span class="sxs-lookup"><span data-stu-id="f1316-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="f1316-111">本指南將協助您：</span><span class="sxs-lookup"><span data-stu-id="f1316-111">This guide will help you:</span></span>
- <span data-ttu-id="f1316-112">設定實驗室服務器和電腦</span><span class="sxs-lookup"><span data-stu-id="f1316-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="f1316-113">使用使用者和群組設定 Active Directory</span><span class="sxs-lookup"><span data-stu-id="f1316-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="f1316-114">安裝和設定 Azure ATP、Office ATP、Microsoft Defender ATP 和 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f1316-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f1316-115">設定伺服器和電腦的本機原則</span><span class="sxs-lookup"><span data-stu-id="f1316-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="f1316-116">模仿威脅攻擊，以在 Microsoft 威脅防護中產生測試事件或警示</span><span class="sxs-lookup"><span data-stu-id="f1316-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="f1316-117">為了獲得最佳結果，請盡可能遵循實驗室設定指示。</span><span class="sxs-lookup"><span data-stu-id="f1316-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="f1316-118">部署階段</span><span class="sxs-lookup"><span data-stu-id="f1316-118">Deployment phases</span></span>

<span data-ttu-id="f1316-119">建立 Microsoft 威脅防護試用實驗室環境並部署它時，有三個階段：</span><span class="sxs-lookup"><span data-stu-id="f1316-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="f1316-120">階段</span><span class="sxs-lookup"><span data-stu-id="f1316-120">Phase</span></span> | <span data-ttu-id="f1316-121">描述</span><span class="sxs-lookup"><span data-stu-id="f1316-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="f1316-122">![階段1：準備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="f1316-123">階段1：準備</span><span class="sxs-lookup"><span data-stu-id="f1316-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="f1316-124">深入瞭解在試用實驗室環境中部署 Microsoft 威脅防護時，需要考慮的事項：</span><span class="sxs-lookup"><span data-stu-id="f1316-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="f1316-125">-專案關係人和簽核關</span><span class="sxs-lookup"><span data-stu-id="f1316-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="f1316-126">-環境考慮</span><span class="sxs-lookup"><span data-stu-id="f1316-126">- Environment considerations</span></span> <br><span data-ttu-id="f1316-127">-Access</span><span class="sxs-lookup"><span data-stu-id="f1316-127">- Access</span></span> <br><span data-ttu-id="f1316-128">-Azure Active Directory 安裝程式</span><span class="sxs-lookup"><span data-stu-id="f1316-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="f1316-129">-設定順序</span><span class="sxs-lookup"><span data-stu-id="f1316-129">- Configuration order</span></span>
|  <span data-ttu-id="f1316-130">![階段2：設定](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="f1316-131">階段2：設定</span><span class="sxs-lookup"><span data-stu-id="f1316-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="f1316-132">請先取得存取 Microsoft 365 Security Center 的初始步驟，以設定您的 Microsoft 威脅防護試用實驗室環境。</span><span class="sxs-lookup"><span data-stu-id="f1316-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="f1316-133">您將會得到指導：</span><span class="sxs-lookup"><span data-stu-id="f1316-133">You will be guided to:</span></span><br><br><span data-ttu-id="f1316-134">-註冊 Microsoft 365 E5 試用版</span><span class="sxs-lookup"><span data-stu-id="f1316-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="f1316-135">-設定網域</span><span class="sxs-lookup"><span data-stu-id="f1316-135">- Configure domain</span></span><br><span data-ttu-id="f1316-136">-指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="f1316-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="f1316-137">-完成入口網站中的設定向導</span><span class="sxs-lookup"><span data-stu-id="f1316-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="f1316-138">![階段3：設定板載 &](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="f1316-139">階段3：設定板載 &</span><span class="sxs-lookup"><span data-stu-id="f1316-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="f1316-140">設定每個 Microsoft 威脅防護 pillar 和板載端點。</span><span class="sxs-lookup"><span data-stu-id="f1316-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="f1316-141">您將會得到指導：</span><span class="sxs-lookup"><span data-stu-id="f1316-141">You will be guided to:</span></span><br><br><span data-ttu-id="f1316-142">-設定 Office 365 的高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="f1316-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="f1316-143">-設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f1316-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="f1316-144">-設定 Azure 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="f1316-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="f1316-145">-設定 Microsoft Defender 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="f1316-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="f1316-146">在範圍內</span><span class="sxs-lookup"><span data-stu-id="f1316-146">In scope</span></span>

<span data-ttu-id="f1316-147">此試用實驗室環境指南的範圍如下：</span><span class="sxs-lookup"><span data-stu-id="f1316-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="f1316-148">設定 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f1316-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="f1316-149">設定 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="f1316-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="f1316-150">註冊 Microsoft 365 E5 試用版</span><span class="sxs-lookup"><span data-stu-id="f1316-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="f1316-151">設定網域</span><span class="sxs-lookup"><span data-stu-id="f1316-151">Configure domain</span></span>
    -   <span data-ttu-id="f1316-152">指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="f1316-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="f1316-153">在入口網站中完成安裝精靈</span><span class="sxs-lookup"><span data-stu-id="f1316-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="f1316-154">根據最佳作法設定所有 Microsoft 威脅防護支柱</span><span class="sxs-lookup"><span data-stu-id="f1316-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="f1316-155">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="f1316-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="f1316-156">Azure 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="f1316-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="f1316-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f1316-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="f1316-158">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="f1316-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="f1316-159">超出範圍</span><span class="sxs-lookup"><span data-stu-id="f1316-159">Out of scope</span></span>

<span data-ttu-id="f1316-160">下列專案不在本部署指南的範圍內：</span><span class="sxs-lookup"><span data-stu-id="f1316-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="f1316-161">設定可能會與 Microsoft Defender ATP 整合的協力廠商解決方案</span><span class="sxs-lookup"><span data-stu-id="f1316-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="f1316-162">實際執行環境中的滲透測試</span><span class="sxs-lookup"><span data-stu-id="f1316-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="f1316-163">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f1316-163">Next step</span></span>
|||
|:-------|:-----|
|<span data-ttu-id="f1316-164">![階段1：準備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="f1316-165">階段1：準備</span><span class="sxs-lookup"><span data-stu-id="f1316-165">Phase 1: Prepare</span></span>](prepare-mtpeval.md) | <span data-ttu-id="f1316-166">準備您的 Microsoft 威脅防護評估實驗室環境</span><span class="sxs-lookup"><span data-stu-id="f1316-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
