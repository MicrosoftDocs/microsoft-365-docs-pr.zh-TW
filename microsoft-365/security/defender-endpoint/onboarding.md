---
title: 在 Microsoft Defender for Endpoint service 上架
description: 深入瞭解如何在 Microsoft Defender for Endpoint service 上進行板載端點服務
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
ms.openlocfilehash: cc538c887397d5bbea78f63c8a8acd318ec7fe9f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689530"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="8dfbc-103">在 Microsoft Defender for Endpoint service 上架</span><span class="sxs-lookup"><span data-stu-id="8dfbc-103">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8dfbc-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8dfbc-104">**Applies to:**</span></span>
- [<span data-ttu-id="8dfbc-105">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8dfbc-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8dfbc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8dfbc-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="8dfbc-107">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8dfbc-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8dfbc-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="8dfbc-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="8dfbc-109">瞭解部署 Microsoft Defender for Endpoint 的各個階段，以及如何設定解決方案內的功能。</span><span class="sxs-lookup"><span data-stu-id="8dfbc-109">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="8dfbc-110">為端點部署 Defender 是三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="8dfbc-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="8dfbc-111">[![部署階段-準備](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="8dfbc-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="8dfbc-112">階段 1：準備</span><span class="sxs-lookup"><span data-stu-id="8dfbc-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="8dfbc-113">[![部署階段-安裝程式](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="8dfbc-113">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="8dfbc-114">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="8dfbc-114">Phase 2: Setup</span></span>](production-deployment.md) | ![部署階段-板載](images/phase-diagrams/onboard.png)<br><span data-ttu-id="8dfbc-116">第 3 階段：導入</span><span class="sxs-lookup"><span data-stu-id="8dfbc-116">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="8dfbc-117">*您在這裡！*</span><span class="sxs-lookup"><span data-stu-id="8dfbc-117">*You are here!*</span></span>|

<span data-ttu-id="8dfbc-118">您目前位於上架階段。</span><span class="sxs-lookup"><span data-stu-id="8dfbc-118">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="8dfbc-119">您必須採取下列步驟，才能部署用於端點的 Defender：</span><span class="sxs-lookup"><span data-stu-id="8dfbc-119">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="8dfbc-120">步驟1：服務的板載端點</span><span class="sxs-lookup"><span data-stu-id="8dfbc-120">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="8dfbc-121">步驟2：設定功能</span><span class="sxs-lookup"><span data-stu-id="8dfbc-121">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="8dfbc-122">步驟1：使用任何支援的管理工具的板載端點</span><span class="sxs-lookup"><span data-stu-id="8dfbc-122">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="8dfbc-123">「 [計畫部署](deployment-strategy.md) 」主題概要說明部署用於端點的 Defender 所需執行的一般步驟。</span><span class="sxs-lookup"><span data-stu-id="8dfbc-123">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="8dfbc-124">觀賞這段影片，快速流覽上架程式，並瞭解可用的工具和方法。</span><span class="sxs-lookup"><span data-stu-id="8dfbc-124">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="8dfbc-125">在識別您的架構之後，您必須決定要使用的部署方法。</span><span class="sxs-lookup"><span data-stu-id="8dfbc-125">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="8dfbc-126">您選擇的部署工具會影響您板載端點到服務的方式。</span><span class="sxs-lookup"><span data-stu-id="8dfbc-126">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="8dfbc-127">上架工具選項</span><span class="sxs-lookup"><span data-stu-id="8dfbc-127">Onboarding tool options</span></span>

<span data-ttu-id="8dfbc-128">下表根據您在上架所需的端點，列出可用的工具。</span><span class="sxs-lookup"><span data-stu-id="8dfbc-128">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="8dfbc-129">端點</span><span class="sxs-lookup"><span data-stu-id="8dfbc-129">Endpoint</span></span>     | <span data-ttu-id="8dfbc-130">工具選項</span><span class="sxs-lookup"><span data-stu-id="8dfbc-130">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="8dfbc-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="8dfbc-131">**Windows**</span></span>  |  [<span data-ttu-id="8dfbc-132">本機腳本 (最多10個裝置) </span><span class="sxs-lookup"><span data-stu-id="8dfbc-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="8dfbc-133">群組原則</span><span class="sxs-lookup"><span data-stu-id="8dfbc-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="8dfbc-134">Microsoft 端點管理員/行動裝置管理員</span><span class="sxs-lookup"><span data-stu-id="8dfbc-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="8dfbc-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8dfbc-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="8dfbc-136">VDI 腳本</span><span class="sxs-lookup"><span data-stu-id="8dfbc-136">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="8dfbc-137">Azure 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="8dfbc-137">Azure Security Center</span></span>](configure-server-endpoints.md#integration-with-azure-security-center) |
| <span data-ttu-id="8dfbc-138">**macOS**</span><span class="sxs-lookup"><span data-stu-id="8dfbc-138">**macOS**</span></span>    | [<span data-ttu-id="8dfbc-139">本機腳本</span><span class="sxs-lookup"><span data-stu-id="8dfbc-139">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="8dfbc-140">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="8dfbc-140">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="8dfbc-141">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="8dfbc-141">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="8dfbc-142">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="8dfbc-142">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="8dfbc-143">**Linux 伺服器**</span><span class="sxs-lookup"><span data-stu-id="8dfbc-143">**Linux Server**</span></span> | [<span data-ttu-id="8dfbc-144">本機腳本</span><span class="sxs-lookup"><span data-stu-id="8dfbc-144">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="8dfbc-145">木偶</span><span class="sxs-lookup"><span data-stu-id="8dfbc-145">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="8dfbc-146">Ansible</span><span class="sxs-lookup"><span data-stu-id="8dfbc-146">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="8dfbc-147">**iOS**</span><span class="sxs-lookup"><span data-stu-id="8dfbc-147">**iOS**</span></span>      | [<span data-ttu-id="8dfbc-148">以應用程式為基礎</span><span class="sxs-lookup"><span data-stu-id="8dfbc-148">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="8dfbc-149">**Android**</span><span class="sxs-lookup"><span data-stu-id="8dfbc-149">**Android**</span></span>  | [<span data-ttu-id="8dfbc-150">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="8dfbc-150">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="8dfbc-151">步驟2：設定功能</span><span class="sxs-lookup"><span data-stu-id="8dfbc-151">Step 2: Configure capabilities</span></span>
<span data-ttu-id="8dfbc-152">在上架端點後，您會設定各種功能，例如端點偵測和回應、下一代保護，以及攻擊面降低。</span><span class="sxs-lookup"><span data-stu-id="8dfbc-152">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="8dfbc-153">部署範例</span><span class="sxs-lookup"><span data-stu-id="8dfbc-153">Example deployments</span></span>
<span data-ttu-id="8dfbc-154">在此部署指南中，我們將引導您瞭解如何對板載端點使用兩個部署工具，以及如何設定功能。</span><span class="sxs-lookup"><span data-stu-id="8dfbc-154">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="8dfbc-155">範例部署中的工具組括：</span><span class="sxs-lookup"><span data-stu-id="8dfbc-155">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="8dfbc-156">使用 Microsoft Endpoint Configuration Manager 上線</span><span class="sxs-lookup"><span data-stu-id="8dfbc-156">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="8dfbc-157">使用 Microsoft 端點管理員上線</span><span class="sxs-lookup"><span data-stu-id="8dfbc-157">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="8dfbc-158">您可以使用上述部署工具，在設定下列的 Defender for Endpoint 功能時進行指導：</span><span class="sxs-lookup"><span data-stu-id="8dfbc-158">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="8dfbc-159">端點偵測和回應設定</span><span class="sxs-lookup"><span data-stu-id="8dfbc-159">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="8dfbc-160">下一代保護設定</span><span class="sxs-lookup"><span data-stu-id="8dfbc-160">Next-generation protection configuration</span></span>
- <span data-ttu-id="8dfbc-161">攻擊面減少設定</span><span class="sxs-lookup"><span data-stu-id="8dfbc-161">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="8dfbc-162">相關主題</span><span class="sxs-lookup"><span data-stu-id="8dfbc-162">Related topics</span></span>
- [<span data-ttu-id="8dfbc-163">使用 Microsoft Endpoint Configuration Manager 上線</span><span class="sxs-lookup"><span data-stu-id="8dfbc-163">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="8dfbc-164">使用 Microsoft 端點管理員上線</span><span class="sxs-lookup"><span data-stu-id="8dfbc-164">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="8dfbc-165">Microsoft 365 E5 中的安全文件</span><span class="sxs-lookup"><span data-stu-id="8dfbc-165">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
