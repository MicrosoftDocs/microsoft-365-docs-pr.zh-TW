---
title: 適用于 Microsoft Defender for Endpoint service 的板載裝置
description: 板載 Windows 10 裝置、伺服器、非 Windows 裝置，並瞭解如何執行偵測測試。
keywords: 上架，Microsoft Defender for Endpoint 上架，sccm，群組原則，mdm，local script，偵測測試
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 05cc5770df5bb05687bb8be69ad89a7abd6875ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933550"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="873fa-104">適用于 Microsoft Defender for Endpoint service 的板載裝置</span><span class="sxs-lookup"><span data-stu-id="873fa-104">Onboard devices to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="873fa-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="873fa-105">**Applies to:**</span></span>
- [<span data-ttu-id="873fa-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="873fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="873fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="873fa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="873fa-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="873fa-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="873fa-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="873fa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="873fa-110">您必須前往端點入口網站的上架區段，以上架任何支援的裝置。</span><span class="sxs-lookup"><span data-stu-id="873fa-110">You'll need to go the onboarding section of the Defender for Endpoint portal to onboard any of the supported devices.</span></span> <span data-ttu-id="873fa-111">視裝置而定，您將會以適當的步驟進行指導，並提供適用于裝置的管理和部署工具選項。</span><span class="sxs-lookup"><span data-stu-id="873fa-111">Depending on the device, you'll be guided with appropriate steps and provided management and deployment tool options suitable for the device.</span></span> 

<span data-ttu-id="873fa-112">一般而言，對服務的板載裝置：</span><span class="sxs-lookup"><span data-stu-id="873fa-112">In general, to onboard devices to the service:</span></span>

- <span data-ttu-id="873fa-113">確認裝置滿足 [最低需求](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="873fa-113">Verify that the device fulfills the [minimum requirements](minimum-requirements.md)</span></span>
- <span data-ttu-id="873fa-114">視裝置而定，請遵循用於端點入口網站之 Defender 的上架區段中所提供的設定步驟</span><span class="sxs-lookup"><span data-stu-id="873fa-114">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal</span></span>
- <span data-ttu-id="873fa-115">針對您的裝置使用適當的管理工具和部署方法</span><span class="sxs-lookup"><span data-stu-id="873fa-115">Use the appropriate management tool and deployment method for your devices</span></span>
- <span data-ttu-id="873fa-116">執行偵測測試以驗證裝置是否已正確架及報告給服務</span><span class="sxs-lookup"><span data-stu-id="873fa-116">Run a detection test to verify that the devices are properly onboarded and reporting to the service</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a><span data-ttu-id="873fa-117">上架工具選項</span><span class="sxs-lookup"><span data-stu-id="873fa-117">Onboarding tool options</span></span>
<span data-ttu-id="873fa-118">下表根據您在上架所需的端點，列出可用的工具。</span><span class="sxs-lookup"><span data-stu-id="873fa-118">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="873fa-119">端點</span><span class="sxs-lookup"><span data-stu-id="873fa-119">Endpoint</span></span>     | <span data-ttu-id="873fa-120">工具選項</span><span class="sxs-lookup"><span data-stu-id="873fa-120">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="873fa-121">**Windows**</span><span class="sxs-lookup"><span data-stu-id="873fa-121">**Windows**</span></span>  |  [<span data-ttu-id="873fa-122">本機腳本 (最多10個裝置) </span><span class="sxs-lookup"><span data-stu-id="873fa-122">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="873fa-123">群組原則</span><span class="sxs-lookup"><span data-stu-id="873fa-123">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="873fa-124">Microsoft 端點管理員/行動裝置管理員</span><span class="sxs-lookup"><span data-stu-id="873fa-124">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="873fa-125">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="873fa-125">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="873fa-126">VDI 腳本</span><span class="sxs-lookup"><span data-stu-id="873fa-126">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="873fa-127">**macOS**</span><span class="sxs-lookup"><span data-stu-id="873fa-127">**macOS**</span></span>    | [<span data-ttu-id="873fa-128">本機腳本</span><span class="sxs-lookup"><span data-stu-id="873fa-128">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="873fa-129">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="873fa-129">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="873fa-130">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="873fa-130">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="873fa-131">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="873fa-131">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="873fa-132">**Linux 伺服器**</span><span class="sxs-lookup"><span data-stu-id="873fa-132">**Linux Server**</span></span> | [<span data-ttu-id="873fa-133">本機腳本</span><span class="sxs-lookup"><span data-stu-id="873fa-133">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="873fa-134">木偶</span><span class="sxs-lookup"><span data-stu-id="873fa-134">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="873fa-135">Ansible</span><span class="sxs-lookup"><span data-stu-id="873fa-135">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="873fa-136">**iOS**</span><span class="sxs-lookup"><span data-stu-id="873fa-136">**iOS**</span></span>      | [<span data-ttu-id="873fa-137">以應用程式為基礎</span><span class="sxs-lookup"><span data-stu-id="873fa-137">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="873fa-138">**Android**</span><span class="sxs-lookup"><span data-stu-id="873fa-138">**Android**</span></span>  | [<span data-ttu-id="873fa-139">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="873fa-139">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




## <a name="in-this-section"></a><span data-ttu-id="873fa-140">本節內容</span><span class="sxs-lookup"><span data-stu-id="873fa-140">In this section</span></span>
<span data-ttu-id="873fa-141">主題</span><span class="sxs-lookup"><span data-stu-id="873fa-141">Topic</span></span> | <span data-ttu-id="873fa-142">描述</span><span class="sxs-lookup"><span data-stu-id="873fa-142">Description</span></span>
:---|:---
[<span data-ttu-id="873fa-143">將上一版 Windows 上線</span><span class="sxs-lookup"><span data-stu-id="873fa-143">Onboard previous versions of Windows</span></span>](onboard-downlevel.md)| <span data-ttu-id="873fa-144">板載 Windows 7 和 Windows 8.1 裝置的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="873fa-144">Onboard Windows 7 and Windows 8.1 devices to Defender for Endpoint.</span></span> 
[<span data-ttu-id="873fa-145">將 Windows 10 裝置上線</span><span class="sxs-lookup"><span data-stu-id="873fa-145">Onboard Windows 10 devices</span></span>](configure-endpoints.md) | <span data-ttu-id="873fa-146">您需要有板載裝置，才能向其報告「Defender for Endpoint service」。</span><span class="sxs-lookup"><span data-stu-id="873fa-146">You'll need to onboard devices for it to report to the Defender for Endpoint service.</span></span> <span data-ttu-id="873fa-147">深入瞭解您可以用來設定企業中裝置的工具和方法。</span><span class="sxs-lookup"><span data-stu-id="873fa-147">Learn about the tools and methods you can use to configure devices in your enterprise.</span></span>
[<span data-ttu-id="873fa-148">上架伺服器</span><span class="sxs-lookup"><span data-stu-id="873fa-148">Onboard servers</span></span>](configure-server-endpoints.md) |  <span data-ttu-id="873fa-149">板載 Windows Server 2008 R2 SP1，Windows Server 2012 R2，Windows Server 2016，Windows server (SAC) 版本1803及更新版本，Windows server 2019 和更新版本，以及 Windows 伺服器2019核心版到 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="873fa-149">Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) version 1803 and later, Windows Server 2019 and later, and Windows Server 2019 core edition to Defender for Endpoint.</span></span>
[<span data-ttu-id="873fa-150">將非 Windows 裝置上線</span><span class="sxs-lookup"><span data-stu-id="873fa-150">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md) | <span data-ttu-id="873fa-151">Defender for Endpoint 可提供 Windows 和非 Windows 平臺的集中式安全性作業體驗。</span><span class="sxs-lookup"><span data-stu-id="873fa-151">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="873fa-152">您可以在 Microsoft Defender 資訊安全中心中查看不同支援作業系統 (OS) 中的警示，也能更好地保護組織的網路。</span><span class="sxs-lookup"><span data-stu-id="873fa-152">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> <span data-ttu-id="873fa-153">這種經驗利用於協力廠商的安全性產品的感應器資料。</span><span class="sxs-lookup"><span data-stu-id="873fa-153">This experience leverages on a third-party security products' sensor data.</span></span> 
[<span data-ttu-id="873fa-154">在新上線的裝置上執行偵測測試</span><span class="sxs-lookup"><span data-stu-id="873fa-154">Run a detection test on a newly onboarded device</span></span>](run-detection-test.md) | <span data-ttu-id="873fa-155">在新的架裝置上執行腳本，以驗證它是否已正確報告至端點服務的 Defender。</span><span class="sxs-lookup"><span data-stu-id="873fa-155">Run a script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>
[<span data-ttu-id="873fa-156">設定 proxy 和網際網路設定</span><span class="sxs-lookup"><span data-stu-id="873fa-156">Configure proxy and Internet settings</span></span>](configure-proxy-internet.md)| <span data-ttu-id="873fa-157">設定 proxy 和網際網路連線設定，以啟用與 Defender for Endpoint cloud service 的通訊。</span><span class="sxs-lookup"><span data-stu-id="873fa-157">Enable communication with the Defender for Endpoint cloud service by configuring the proxy and Internet connectivity settings.</span></span>
[<span data-ttu-id="873fa-158">為上線問題疑難排解</span><span class="sxs-lookup"><span data-stu-id="873fa-158">Troubleshoot onboarding issues</span></span>](troubleshoot-onboarding.md) | <span data-ttu-id="873fa-159">深入瞭解如何解決上架期間可能發生的問題。</span><span class="sxs-lookup"><span data-stu-id="873fa-159">Learn about resolving issues that might arise during onboarding.</span></span>

><span data-ttu-id="873fa-160">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="873fa-160">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="873fa-161">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="873fa-161">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
