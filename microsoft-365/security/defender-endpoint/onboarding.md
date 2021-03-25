---
title: Microsoft Defender ATP 服務的板載
description: 深入瞭解如何在 Microsoft Defender ATP 服務上架端點
keywords: ''
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
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56645553c43289995012d53d7caf879874e65c8a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186926"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="2f2b4-103">在 Microsoft Defender for Endpoint service 上架</span><span class="sxs-lookup"><span data-stu-id="2f2b4-103">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f2b4-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2f2b4-104">**Applies to:**</span></span>
- [<span data-ttu-id="2f2b4-105">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2f2b4-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2f2b4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f2b4-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="2f2b4-107">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2f2b4-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2f2b4-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2f2b4-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2f2b4-109">瞭解部署 Microsoft Defender for Endpoint 的各個階段，以及如何設定解決方案內的功能。</span><span class="sxs-lookup"><span data-stu-id="2f2b4-109">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="2f2b4-110">為端點部署 Defender 是三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="2f2b4-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="2f2b4-111">[![部署階段-準備](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="2f2b4-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="2f2b4-112">階段1：準備</span><span class="sxs-lookup"><span data-stu-id="2f2b4-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="2f2b4-113">[![部署階段-安裝程式](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="2f2b4-113">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="2f2b4-114">階段2：設定</span><span class="sxs-lookup"><span data-stu-id="2f2b4-114">Phase 2: Setup</span></span>](production-deployment.md) | ![部署階段-板載](images/phase-diagrams/onboard.png)<br><span data-ttu-id="2f2b4-116">階段3：板載</span><span class="sxs-lookup"><span data-stu-id="2f2b4-116">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="2f2b4-117">*您在這裡！*</span><span class="sxs-lookup"><span data-stu-id="2f2b4-117">*You are here!*</span></span>|

<span data-ttu-id="2f2b4-118">您目前位於上架階段。</span><span class="sxs-lookup"><span data-stu-id="2f2b4-118">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="2f2b4-119">您必須採取下列步驟，才能部署用於端點的 Defender：</span><span class="sxs-lookup"><span data-stu-id="2f2b4-119">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="2f2b4-120">步驟1：服務的板載端點</span><span class="sxs-lookup"><span data-stu-id="2f2b4-120">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="2f2b4-121">步驟2：設定功能</span><span class="sxs-lookup"><span data-stu-id="2f2b4-121">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="2f2b4-122">步驟1：使用任何支援的管理工具的板載端點</span><span class="sxs-lookup"><span data-stu-id="2f2b4-122">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="2f2b4-123">「 [計畫部署](deployment-strategy.md) 」主題概要說明部署用於端點的 Defender 所需執行的一般步驟。</span><span class="sxs-lookup"><span data-stu-id="2f2b4-123">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="2f2b4-124">觀賞這段影片，快速流覽上架程式，並瞭解可用的工具和方法。</span><span class="sxs-lookup"><span data-stu-id="2f2b4-124">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="2f2b4-125">在識別您的架構之後，您必須決定要使用的部署方法。</span><span class="sxs-lookup"><span data-stu-id="2f2b4-125">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="2f2b4-126">您選擇的部署工具會影響您板載端點到服務的方式。</span><span class="sxs-lookup"><span data-stu-id="2f2b4-126">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="2f2b4-127">上架工具選項</span><span class="sxs-lookup"><span data-stu-id="2f2b4-127">Onboarding tool options</span></span>

<span data-ttu-id="2f2b4-128">下表根據您在上架所需的端點，列出可用的工具。</span><span class="sxs-lookup"><span data-stu-id="2f2b4-128">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="2f2b4-129">端點</span><span class="sxs-lookup"><span data-stu-id="2f2b4-129">Endpoint</span></span>     | <span data-ttu-id="2f2b4-130">工具選項</span><span class="sxs-lookup"><span data-stu-id="2f2b4-130">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="2f2b4-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="2f2b4-131">**Windows**</span></span>  |  [<span data-ttu-id="2f2b4-132">本機腳本 (最多10個裝置) </span><span class="sxs-lookup"><span data-stu-id="2f2b4-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="2f2b4-133">群組原則</span><span class="sxs-lookup"><span data-stu-id="2f2b4-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="2f2b4-134">Microsoft 端點管理員/行動裝置管理員</span><span class="sxs-lookup"><span data-stu-id="2f2b4-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="2f2b4-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2f2b4-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="2f2b4-136">VDI 腳本</span><span class="sxs-lookup"><span data-stu-id="2f2b4-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="2f2b4-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="2f2b4-137">**macOS**</span></span>    | [<span data-ttu-id="2f2b4-138">本機腳本</span><span class="sxs-lookup"><span data-stu-id="2f2b4-138">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="2f2b4-139">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="2f2b4-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="2f2b4-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="2f2b4-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="2f2b4-141">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="2f2b4-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="2f2b4-142">**Linux 伺服器**</span><span class="sxs-lookup"><span data-stu-id="2f2b4-142">**Linux Server**</span></span> | [<span data-ttu-id="2f2b4-143">本機腳本</span><span class="sxs-lookup"><span data-stu-id="2f2b4-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="2f2b4-144">木偶</span><span class="sxs-lookup"><span data-stu-id="2f2b4-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="2f2b4-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="2f2b4-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="2f2b4-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="2f2b4-146">**iOS**</span></span>      | [<span data-ttu-id="2f2b4-147">以應用程式為基礎</span><span class="sxs-lookup"><span data-stu-id="2f2b4-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="2f2b4-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="2f2b4-148">**Android**</span></span>  | [<span data-ttu-id="2f2b4-149">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="2f2b4-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="2f2b4-150">步驟2：設定功能</span><span class="sxs-lookup"><span data-stu-id="2f2b4-150">Step 2: Configure capabilities</span></span>
<span data-ttu-id="2f2b4-151">在上架端點後，您會設定各種功能，例如端點偵測和回應、下一代保護，以及攻擊面降低。</span><span class="sxs-lookup"><span data-stu-id="2f2b4-151">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="2f2b4-152">部署範例</span><span class="sxs-lookup"><span data-stu-id="2f2b4-152">Example deployments</span></span>
<span data-ttu-id="2f2b4-153">在此部署指南中，我們將引導您瞭解如何對板載端點使用兩個部署工具，以及如何設定功能。</span><span class="sxs-lookup"><span data-stu-id="2f2b4-153">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="2f2b4-154">範例部署中的工具組括：</span><span class="sxs-lookup"><span data-stu-id="2f2b4-154">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="2f2b4-155">使用 Microsoft Endpoint Configuration Manager 上架</span><span class="sxs-lookup"><span data-stu-id="2f2b4-155">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="2f2b4-156">使用 Microsoft 端點管理員上架</span><span class="sxs-lookup"><span data-stu-id="2f2b4-156">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="2f2b4-157">您可以使用上述部署工具，在設定下列的 Defender for Endpoint 功能時進行指導：</span><span class="sxs-lookup"><span data-stu-id="2f2b4-157">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="2f2b4-158">端點偵測和回應設定</span><span class="sxs-lookup"><span data-stu-id="2f2b4-158">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="2f2b4-159">下一代保護設定</span><span class="sxs-lookup"><span data-stu-id="2f2b4-159">Next-generation protection configuration</span></span>
- <span data-ttu-id="2f2b4-160">攻擊面減少設定</span><span class="sxs-lookup"><span data-stu-id="2f2b4-160">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="2f2b4-161">相關主題</span><span class="sxs-lookup"><span data-stu-id="2f2b4-161">Related topics</span></span>
- [<span data-ttu-id="2f2b4-162">使用 Microsoft Endpoint Configuration Manager 上架</span><span class="sxs-lookup"><span data-stu-id="2f2b4-162">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="2f2b4-163">使用 Microsoft 端點管理員上架</span><span class="sxs-lookup"><span data-stu-id="2f2b4-163">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
