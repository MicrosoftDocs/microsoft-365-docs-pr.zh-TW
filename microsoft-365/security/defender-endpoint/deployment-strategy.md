---
title: 規劃用於端點部署的 Microsoft Defender
description: 為您的環境選取最佳的 Microsoft Defender for Endpoint 部署策略
keywords: 部署、規劃、部署策略、雲端原生、管理、部署、評估、上架、本機、群組原則、gp、端點管理員、mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163572"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="d1301-104">規劃用於端點部署的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d1301-104">Plan your Microsoft Defender for Endpoint deployment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d1301-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d1301-105">**Applies to:**</span></span>
- [<span data-ttu-id="d1301-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d1301-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d1301-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d1301-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d1301-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d1301-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d1301-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d1301-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


<span data-ttu-id="d1301-110">規劃 Microsoft Defender for Endpoint deployment，使您可以最大化套件中的安全性功能，並更好地保護您的企業免受網路威脅。</span><span class="sxs-lookup"><span data-stu-id="d1301-110">Plan your Microsoft Defender for Endpoint deployment so that you can maximize the security capabilities within the suite and better protect your enterprise from cyber threats.</span></span>


<span data-ttu-id="d1301-111">此方案提供有關如何識別環境架構的指導方針、選取最符合您需求的部署工具類型，以及如何設定功能的指導方針。</span><span class="sxs-lookup"><span data-stu-id="d1301-111">This solution provides guidance on how to identify your environment architecture, select the type of deployment tool that best fits your needs, and guidance on how to configure capabilities.</span></span>


![部署流程的映射](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a><span data-ttu-id="d1301-113">步驟1：識別架構</span><span class="sxs-lookup"><span data-stu-id="d1301-113">Step 1: Identify architecture</span></span>
<span data-ttu-id="d1301-114">我們知道每個企業環境都是唯一的，因此我們提供了數個選項，讓您在選擇部署服務的方式上具有彈性。</span><span class="sxs-lookup"><span data-stu-id="d1301-114">We understand that every enterprise environment is unique, so we've provided several options to give you the flexibility in choosing how to deploy the service.</span></span>

<span data-ttu-id="d1301-115">根據您的環境而定，有些工具更適合特定架構。</span><span class="sxs-lookup"><span data-stu-id="d1301-115">Depending on your environment, some tools are better suited for certain architectures.</span></span> 

<span data-ttu-id="d1301-116">使用下列材料，選取最適合您組織的端點架構的適當 Defender。</span><span class="sxs-lookup"><span data-stu-id="d1301-116">Use the following material to select the appropriate Defender for Endpoint architecture that best suites your organization.</span></span>

| <span data-ttu-id="d1301-117">項目</span><span class="sxs-lookup"><span data-stu-id="d1301-117">Item</span></span> | <span data-ttu-id="d1301-118">描述</span><span class="sxs-lookup"><span data-stu-id="d1301-118">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="d1301-119">[![適用于 Defender 的 Endpoint 部署策略的縮圖影像](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="d1301-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="d1301-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="d1301-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="d1301-121">架構材料可協助您規劃下列架構的部署：</span><span class="sxs-lookup"><span data-stu-id="d1301-121">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="d1301-122">雲端-原生</span><span class="sxs-lookup"><span data-stu-id="d1301-122">Cloud-native</span></span> </li><li> <span data-ttu-id="d1301-123">共同管理</span><span class="sxs-lookup"><span data-stu-id="d1301-123">Co-management</span></span> </li><li> <span data-ttu-id="d1301-124">內部部署</span><span class="sxs-lookup"><span data-stu-id="d1301-124">On-premise</span></span></li><li><span data-ttu-id="d1301-125">評估與本機上架</span><span class="sxs-lookup"><span data-stu-id="d1301-125">Evaluation and local onboarding</span></span></li>



## <a name="step-2-select-deployment-method"></a><span data-ttu-id="d1301-126">步驟2：選取部署方法</span><span class="sxs-lookup"><span data-stu-id="d1301-126">Step 2: Select deployment method</span></span>
<span data-ttu-id="d1301-127">Defender for Endpoint 支援您可以在服務上架的各種端點。</span><span class="sxs-lookup"><span data-stu-id="d1301-127">Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> 

<span data-ttu-id="d1301-128">下表列出支援的端點和對應的部署工具，您可以使用這些端點和對應的部署工具，以適當地規劃部署。</span><span class="sxs-lookup"><span data-stu-id="d1301-128">The following table lists the supported endpoints and the corresponding deployment tool that you can use so that you can plan the deployment appropriately.</span></span>

| <span data-ttu-id="d1301-129">端點</span><span class="sxs-lookup"><span data-stu-id="d1301-129">Endpoint</span></span>     | <span data-ttu-id="d1301-130">部署工具</span><span class="sxs-lookup"><span data-stu-id="d1301-130">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="d1301-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="d1301-131">**Windows**</span></span>  |  [<span data-ttu-id="d1301-132">本機腳本 (最多10個裝置) </span><span class="sxs-lookup"><span data-stu-id="d1301-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="d1301-133">群組原則</span><span class="sxs-lookup"><span data-stu-id="d1301-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="d1301-134">Microsoft 端點管理員/行動裝置管理員</span><span class="sxs-lookup"><span data-stu-id="d1301-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="d1301-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d1301-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="d1301-136">VDI 腳本</span><span class="sxs-lookup"><span data-stu-id="d1301-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="d1301-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="d1301-137">**macOS**</span></span>    | [<span data-ttu-id="d1301-138">本機腳本</span><span class="sxs-lookup"><span data-stu-id="d1301-138">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="d1301-139">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="d1301-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="d1301-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="d1301-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="d1301-141">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="d1301-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="d1301-142">**Linux 伺服器**</span><span class="sxs-lookup"><span data-stu-id="d1301-142">**Linux Server**</span></span> | [<span data-ttu-id="d1301-143">本機腳本</span><span class="sxs-lookup"><span data-stu-id="d1301-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="d1301-144">木偶</span><span class="sxs-lookup"><span data-stu-id="d1301-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="d1301-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="d1301-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="d1301-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="d1301-146">**iOS**</span></span>      | [<span data-ttu-id="d1301-147">以應用程式為基礎</span><span class="sxs-lookup"><span data-stu-id="d1301-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="d1301-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="d1301-148">**Android**</span></span>  | [<span data-ttu-id="d1301-149">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="d1301-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a><span data-ttu-id="d1301-150">步驟3：設定功能</span><span class="sxs-lookup"><span data-stu-id="d1301-150">Step 3: Configure capabilities</span></span>
<span data-ttu-id="d1301-151">在上架端點之後，在 Defender for Endpoint 中設定安全性功能，讓您可以最大化套件中可用的穩健安全性保護。</span><span class="sxs-lookup"><span data-stu-id="d1301-151">After onboarding endpoints, configure the security capabilities in Defender for Endpoint so that you can maximize the robust security protection available in the suite.</span></span> <span data-ttu-id="d1301-152">功能包括：</span><span class="sxs-lookup"><span data-stu-id="d1301-152">Capabilities include:</span></span>

- <span data-ttu-id="d1301-153">端點偵測及回應</span><span class="sxs-lookup"><span data-stu-id="d1301-153">Endpoint detection and response</span></span>
- <span data-ttu-id="d1301-154">新一代保護</span><span class="sxs-lookup"><span data-stu-id="d1301-154">Next-generation protection</span></span>
- <span data-ttu-id="d1301-155">攻擊面縮小</span><span class="sxs-lookup"><span data-stu-id="d1301-155">Attack surface reduction</span></span>


  
## <a name="related-topics"></a><span data-ttu-id="d1301-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="d1301-156">Related topics</span></span>
- [<span data-ttu-id="d1301-157">部署階段</span><span class="sxs-lookup"><span data-stu-id="d1301-157">Deployment phases</span></span>](deployment-phases.md)
