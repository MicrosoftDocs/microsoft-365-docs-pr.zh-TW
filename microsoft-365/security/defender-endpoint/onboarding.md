---
title: 在 Microsoft Defender for Endpoint service 上架
description: 深入瞭解如何在 Microsoft Defender for Endpoint service 上進行板載端點服務
keywords: microsoft defender for endpoint，板載，deploy
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
ms.openlocfilehash: f63b4f81f454fec60a26c7cb063d66bed4a2bead
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933538"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="6afd3-104">在 Microsoft Defender for Endpoint service 上架</span><span class="sxs-lookup"><span data-stu-id="6afd3-104">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6afd3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="6afd3-105">**Applies to:**</span></span>
- [<span data-ttu-id="6afd3-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6afd3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6afd3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6afd3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="6afd3-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="6afd3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6afd3-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="6afd3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6afd3-110">瞭解部署 Microsoft Defender for Endpoint 的各個階段，以及如何設定解決方案內的功能。</span><span class="sxs-lookup"><span data-stu-id="6afd3-110">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="6afd3-111">為端點部署 Defender 是三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="6afd3-111">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="6afd3-112">[![部署階段-準備](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="6afd3-112">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="6afd3-113">階段 1：準備</span><span class="sxs-lookup"><span data-stu-id="6afd3-113">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="6afd3-114">[![部署階段-安裝程式](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="6afd3-114">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="6afd3-115">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="6afd3-115">Phase 2: Setup</span></span>](production-deployment.md) | ![部署階段-板載](images/phase-diagrams/onboard.png)<br><span data-ttu-id="6afd3-117">第 3 階段：導入</span><span class="sxs-lookup"><span data-stu-id="6afd3-117">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="6afd3-118">*您在這裡！*</span><span class="sxs-lookup"><span data-stu-id="6afd3-118">*You are here!*</span></span>|

<span data-ttu-id="6afd3-119">您目前位於上架階段。</span><span class="sxs-lookup"><span data-stu-id="6afd3-119">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="6afd3-120">您必須採取下列步驟，才能部署用於端點的 Defender：</span><span class="sxs-lookup"><span data-stu-id="6afd3-120">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="6afd3-121">步驟1：服務的板載端點</span><span class="sxs-lookup"><span data-stu-id="6afd3-121">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="6afd3-122">步驟2：設定功能</span><span class="sxs-lookup"><span data-stu-id="6afd3-122">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="6afd3-123">步驟1：使用任何支援的管理工具的板載端點</span><span class="sxs-lookup"><span data-stu-id="6afd3-123">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="6afd3-124">「 [計畫部署](deployment-strategy.md) 」主題概要說明部署用於端點的 Defender 所需執行的一般步驟。</span><span class="sxs-lookup"><span data-stu-id="6afd3-124">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="6afd3-125">觀賞這段影片，快速流覽上架程式，並瞭解可用的工具和方法。</span><span class="sxs-lookup"><span data-stu-id="6afd3-125">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="6afd3-126">在識別您的架構之後，您必須決定要使用的部署方法。</span><span class="sxs-lookup"><span data-stu-id="6afd3-126">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="6afd3-127">您選擇的部署工具會影響您板載端點到服務的方式。</span><span class="sxs-lookup"><span data-stu-id="6afd3-127">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="6afd3-128">上架工具選項</span><span class="sxs-lookup"><span data-stu-id="6afd3-128">Onboarding tool options</span></span>

<span data-ttu-id="6afd3-129">下表根據您在上架所需的端點，列出可用的工具。</span><span class="sxs-lookup"><span data-stu-id="6afd3-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="6afd3-130">端點</span><span class="sxs-lookup"><span data-stu-id="6afd3-130">Endpoint</span></span>     | <span data-ttu-id="6afd3-131">工具選項</span><span class="sxs-lookup"><span data-stu-id="6afd3-131">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="6afd3-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="6afd3-132">**Windows**</span></span>  |  [<span data-ttu-id="6afd3-133">本機腳本 (最多10個裝置) </span><span class="sxs-lookup"><span data-stu-id="6afd3-133">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="6afd3-134">群組原則</span><span class="sxs-lookup"><span data-stu-id="6afd3-134">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="6afd3-135">Microsoft 端點管理員/行動裝置管理員</span><span class="sxs-lookup"><span data-stu-id="6afd3-135">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="6afd3-136">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6afd3-136">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="6afd3-137">VDI 腳本</span><span class="sxs-lookup"><span data-stu-id="6afd3-137">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="6afd3-138">與 Azure Defender 整合</span><span class="sxs-lookup"><span data-stu-id="6afd3-138">Integration with Azure Defender</span></span>](configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="6afd3-139">**macOS**</span><span class="sxs-lookup"><span data-stu-id="6afd3-139">**macOS**</span></span>    | [<span data-ttu-id="6afd3-140">本機腳本</span><span class="sxs-lookup"><span data-stu-id="6afd3-140">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="6afd3-141">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="6afd3-141">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="6afd3-142">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="6afd3-142">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="6afd3-143">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="6afd3-143">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="6afd3-144">**Linux 伺服器**</span><span class="sxs-lookup"><span data-stu-id="6afd3-144">**Linux Server**</span></span> | [<span data-ttu-id="6afd3-145">本機腳本</span><span class="sxs-lookup"><span data-stu-id="6afd3-145">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="6afd3-146">木偶</span><span class="sxs-lookup"><span data-stu-id="6afd3-146">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="6afd3-147">Ansible</span><span class="sxs-lookup"><span data-stu-id="6afd3-147">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="6afd3-148">**iOS**</span><span class="sxs-lookup"><span data-stu-id="6afd3-148">**iOS**</span></span>      | [<span data-ttu-id="6afd3-149">以應用程式為基礎</span><span class="sxs-lookup"><span data-stu-id="6afd3-149">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="6afd3-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="6afd3-150">**Android**</span></span>  | [<span data-ttu-id="6afd3-151">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="6afd3-151">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="6afd3-152">步驟2：設定功能</span><span class="sxs-lookup"><span data-stu-id="6afd3-152">Step 2: Configure capabilities</span></span>
<span data-ttu-id="6afd3-153">在上架端點後，您會設定各種功能，例如端點偵測和回應、下一代保護，以及攻擊面降低。</span><span class="sxs-lookup"><span data-stu-id="6afd3-153">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="6afd3-154">部署範例</span><span class="sxs-lookup"><span data-stu-id="6afd3-154">Example deployments</span></span>
<span data-ttu-id="6afd3-155">在此部署指南中，我們將引導您瞭解如何對板載端點使用兩個部署工具，以及如何設定功能。</span><span class="sxs-lookup"><span data-stu-id="6afd3-155">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="6afd3-156">範例部署中的工具組括：</span><span class="sxs-lookup"><span data-stu-id="6afd3-156">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="6afd3-157">使用 Microsoft Endpoint Configuration Manager 上線</span><span class="sxs-lookup"><span data-stu-id="6afd3-157">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="6afd3-158">使用 Microsoft 端點管理員上線</span><span class="sxs-lookup"><span data-stu-id="6afd3-158">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="6afd3-159">您可以使用上述部署工具，在設定下列的 Defender for Endpoint 功能時進行指導：</span><span class="sxs-lookup"><span data-stu-id="6afd3-159">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="6afd3-160">端點偵測和回應設定</span><span class="sxs-lookup"><span data-stu-id="6afd3-160">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="6afd3-161">下一代保護設定</span><span class="sxs-lookup"><span data-stu-id="6afd3-161">Next-generation protection configuration</span></span>
- <span data-ttu-id="6afd3-162">攻擊面減少設定</span><span class="sxs-lookup"><span data-stu-id="6afd3-162">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="6afd3-163">相關主題</span><span class="sxs-lookup"><span data-stu-id="6afd3-163">Related topics</span></span>
- [<span data-ttu-id="6afd3-164">使用 Microsoft Endpoint Configuration Manager 上線</span><span class="sxs-lookup"><span data-stu-id="6afd3-164">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="6afd3-165">使用 Microsoft 端點管理員上線</span><span class="sxs-lookup"><span data-stu-id="6afd3-165">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="6afd3-166">Microsoft 365 E5 中的安全文件</span><span class="sxs-lookup"><span data-stu-id="6afd3-166">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
