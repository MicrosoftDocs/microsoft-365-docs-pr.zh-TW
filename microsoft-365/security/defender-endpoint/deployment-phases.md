---
title: 部署階段
description: 瞭解如何在服務中準備、設定和上架端點來部署 Microsoft Defender for Endpoint
keywords: deploy，prepare，setup，板載，階段，部署，部署，採用，設定
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165162"
---
# <a name="deployment-phases"></a><span data-ttu-id="2f571-104">部署階段</span><span class="sxs-lookup"><span data-stu-id="2f571-104">Deployment phases</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f571-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2f571-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f571-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2f571-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2f571-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f571-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2f571-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2f571-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2f571-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2f571-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="2f571-110">瞭解如何部署 Microsoft Defender for Endpoint，使您的企業能夠利用預防性防護、入侵後偵測、自動調查和回應。</span><span class="sxs-lookup"><span data-stu-id="2f571-110">Learn how to deploy Microsoft Defender for Endpoint so that your enterprise can take advantage of preventative protection, post-breach detection, automated investigation, and response.</span></span> 


<span data-ttu-id="2f571-111">本指南可協助您在不同的專案關係人上運作，以系統方式準備您的環境，然後以系統方式從評估移至有意義的試驗，以進行完整部署。</span><span class="sxs-lookup"><span data-stu-id="2f571-111">This guide helps you work across stakeholders to prepare your environment and then onboard devices in a methodical way, moving from evaluation, to a meaningful pilot, to full deployment.</span></span>

<span data-ttu-id="2f571-112">每一節都對應此方案中的個別文章。</span><span class="sxs-lookup"><span data-stu-id="2f571-112">Each section corresponds to a separate article in this solution.</span></span>

![包含資料表詳細資料的部署階段映射](images/deployment-guide-phases.png)


![部署階段摘要： prepare、setup、板載](images/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="2f571-115">階段</span><span class="sxs-lookup"><span data-stu-id="2f571-115">Phase</span></span> | <span data-ttu-id="2f571-116">描述</span><span class="sxs-lookup"><span data-stu-id="2f571-116">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="2f571-117">階段 1：準備</span><span class="sxs-lookup"><span data-stu-id="2f571-117">Phase 1: Prepare</span></span>](prepare-deployment.md)| <span data-ttu-id="2f571-118">深入瞭解部署 Defender （如專案關係人核准、環境考慮、存取權及功能採用順序）時，您需要考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="2f571-118">Learn about what you need to consider when deploying Defender for Endpoint such as stakeholder approvals, environment considerations, access permissions, and adoption order of capabilities.</span></span> 
| [<span data-ttu-id="2f571-119">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="2f571-119">Phase 2: Setup</span></span>](production-deployment.md)|  <span data-ttu-id="2f571-120">取得您必須採取之初始步驟的指導方針，讓您可以存取入口網站，例如驗證授權、完成安裝精靈及網路設定。</span><span class="sxs-lookup"><span data-stu-id="2f571-120">Get guidance on the initial steps you need to take so that you can access the portal such as validating licensing, completing the setup wizard, and network configuration.</span></span> 
| [<span data-ttu-id="2f571-121">第 3 階段：導入</span><span class="sxs-lookup"><span data-stu-id="2f571-121">Phase 3: Onboard</span></span>](onboarding.md) | <span data-ttu-id="2f571-122">瞭解如何使用部署環、根據端點類型所支援的內架工具，以及設定可用的功能。</span><span class="sxs-lookup"><span data-stu-id="2f571-122">Learn how to make use of deployment rings, supported onboarding tools based on the type of endpoint, and configuring available capabilities.</span></span> 


<span data-ttu-id="2f571-123">當您完成本指南後，您將會使用正確的存取權限進行安裝，而您的端點將會架並報告感應器資料給服務，而下一代保護和攻擊面降低等功能將會就地實施。</span><span class="sxs-lookup"><span data-stu-id="2f571-123">After you've completed this guide, you'll be setup with the right access permissions, your endpoints will be onboarded and reporting sensor data to the service, and capabilities such as next-generation protection and attack surface reduction will be in place.</span></span>



<span data-ttu-id="2f571-124">不論 [規劃部署](deployment-strategy.md) 指導中所選擇的環境架構和部署方法為何，本指南都將為您提供上架端點的支援。</span><span class="sxs-lookup"><span data-stu-id="2f571-124">Regardless of the environment architecture and method of deployment you choose outlined in the [Plan deployment](deployment-strategy.md) guidance, this guide is going to support you in onboarding endpoints.</span></span> 








## <a name="key-capabilities"></a><span data-ttu-id="2f571-125">主要功能</span><span class="sxs-lookup"><span data-stu-id="2f571-125">Key capabilities</span></span>

<span data-ttu-id="2f571-126">雖然 Microsoft Defender for Endpoint 提供許多功能，但此部署指南的主要目的是讓您開始使用上架裝置。</span><span class="sxs-lookup"><span data-stu-id="2f571-126">While Microsoft Defender for Endpoint provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="2f571-127">除了上架之外，本指南也可讓您開始使用下列功能。</span><span class="sxs-lookup"><span data-stu-id="2f571-127">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>



<span data-ttu-id="2f571-128">功能</span><span class="sxs-lookup"><span data-stu-id="2f571-128">Capability</span></span> | <span data-ttu-id="2f571-129">描述</span><span class="sxs-lookup"><span data-stu-id="2f571-129">Description</span></span> 
:---|:---
<span data-ttu-id="2f571-130">端點偵測及回應</span><span class="sxs-lookup"><span data-stu-id="2f571-130">Endpoint detection and response</span></span> | <span data-ttu-id="2f571-131">端點偵測和回應功能可就地偵測、調查和回應入侵嘗試和主動違例。</span><span class="sxs-lookup"><span data-stu-id="2f571-131">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span>
<span data-ttu-id="2f571-132">新一代保護</span><span class="sxs-lookup"><span data-stu-id="2f571-132">Next-generation protection</span></span> | <span data-ttu-id="2f571-133">若要進一步鞏固網路的安全性周邊，Microsoft Defender for Endpoint 會使用下一代保護，以捕捉所有類型的新威脅。</span><span class="sxs-lookup"><span data-stu-id="2f571-133">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>
<span data-ttu-id="2f571-134">攻擊面縮小</span><span class="sxs-lookup"><span data-stu-id="2f571-134">Attack surface reduction</span></span> |  <span data-ttu-id="2f571-135">在堆疊中提供第一項防護。</span><span class="sxs-lookup"><span data-stu-id="2f571-135">Provide the first line of defense in the stack.</span></span> <span data-ttu-id="2f571-136">透過確定設定設定正確，並套用利用緩解技術，這些功能可讓攻擊和利用。</span><span class="sxs-lookup"><span data-stu-id="2f571-136">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

<span data-ttu-id="2f571-137">所有這些功能均可供 Microsoft Defender for Endpoint 授權擁有者使用。</span><span class="sxs-lookup"><span data-stu-id="2f571-137">All these capabilities are available for Microsoft Defender for Endpoint license holders.</span></span> <span data-ttu-id="2f571-138">如需詳細資訊，請參閱 [授權要求](minimum-requirements.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="2f571-138">For more information, see [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>

## <a name="scope"></a><span data-ttu-id="2f571-139">範圍</span><span class="sxs-lookup"><span data-stu-id="2f571-139">Scope</span></span>

### <a name="in-scope"></a><span data-ttu-id="2f571-140">在範圍內</span><span class="sxs-lookup"><span data-stu-id="2f571-140">In scope</span></span>

-   <span data-ttu-id="2f571-141">使用 Microsoft 端點管理員和 Microsoft 端點管理員上架端點至服務和設定功能</span><span class="sxs-lookup"><span data-stu-id="2f571-141">Use of Microsoft Endpoint Manager and Microsoft Endpoint Manager to onboard endpoints into the service and configure capabilities</span></span>

-   <span data-ttu-id="2f571-142">啟用 (EDR) 功能的 Defender endpoint endpoint 偵測和回應</span><span class="sxs-lookup"><span data-stu-id="2f571-142">Enabling Defender for Endpoint endpoint detection and response (EDR)  capabilities</span></span>

-   <span data-ttu-id="2f571-143">啟用適用于 Endpoint endpoint protection 平臺的 Defender (EPP) 功能</span><span class="sxs-lookup"><span data-stu-id="2f571-143">Enabling Defender for Endpoint endpoint protection platform (EPP) capabilities</span></span>

    -   <span data-ttu-id="2f571-144">新一代保護</span><span class="sxs-lookup"><span data-stu-id="2f571-144">Next-generation protection</span></span>

    -   <span data-ttu-id="2f571-145">攻擊面縮小</span><span class="sxs-lookup"><span data-stu-id="2f571-145">Attack surface reduction</span></span>


### <a name="out-of-scope"></a><span data-ttu-id="2f571-146">超出範圍</span><span class="sxs-lookup"><span data-stu-id="2f571-146">Out of scope</span></span>

<span data-ttu-id="2f571-147">下列專案不在本部署指南的範圍內：</span><span class="sxs-lookup"><span data-stu-id="2f571-147">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="2f571-148">設定可能與 Defender for Endpoint 整合的協力廠商解決方案</span><span class="sxs-lookup"><span data-stu-id="2f571-148">Configuration of third-party solutions that might integrate with Defender for Endpoint</span></span>

-   <span data-ttu-id="2f571-149">實際執行環境中的滲透測試</span><span class="sxs-lookup"><span data-stu-id="2f571-149">Penetration testing in production environment</span></span>




## <a name="see-also"></a><span data-ttu-id="2f571-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2f571-150">See also</span></span>
- [<span data-ttu-id="2f571-151">階段 1：準備</span><span class="sxs-lookup"><span data-stu-id="2f571-151">Phase 1: Prepare</span></span>](prepare-deployment.md)
- [<span data-ttu-id="2f571-152">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="2f571-152">Phase 2: Set up</span></span>](production-deployment.md)
- [<span data-ttu-id="2f571-153">第 3 階段：導入</span><span class="sxs-lookup"><span data-stu-id="2f571-153">Phase 3: Onboard</span></span>](onboarding.md)
- [<span data-ttu-id="2f571-154">規劃部署</span><span class="sxs-lookup"><span data-stu-id="2f571-154">Plan deployment</span></span>](deployment-strategy.md)