---
title: McAfee 至 Microsoft Defender 的端點-準備
description: 這是第1階段，準備從 McAfee 遷移至 Microsoft Defender for Endpoint。
keywords: 遷移，Microsoft Defender for Endpoint，edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 171c9b4ff02e7f6ddb6918e430af772f44b1777a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538780"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a><span data-ttu-id="e3d64-104">從 McAfee 遷移-階段1：準備遷移</span><span class="sxs-lookup"><span data-stu-id="e3d64-104">Migrate from McAfee - Phase 1: Prepare for your migration</span></span>

<span data-ttu-id="e3d64-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e3d64-105">**Applies to:**</span></span>
- [<span data-ttu-id="e3d64-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e3d64-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e3d64-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3d64-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

|![階段 1：準備](images/phase-diagrams/prepare.png)<br/><span data-ttu-id="e3d64-109">階段 1：準備</span><span class="sxs-lookup"><span data-stu-id="e3d64-109">Phase 1: Prepare</span></span> |<span data-ttu-id="e3d64-110">[![階段 2：設定](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)</span><span class="sxs-lookup"><span data-stu-id="e3d64-110">[![Phase 2: Set up](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)</span></span><br/>[<span data-ttu-id="e3d64-111">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="e3d64-111">Phase 2: Set up</span></span>](mcafee-to-microsoft-defender-setup.md) |<span data-ttu-id="e3d64-112">[![第 3 階段：導入](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)</span><span class="sxs-lookup"><span data-stu-id="e3d64-112">[![Phase 3: Onboard](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)</span></span><br/>[<span data-ttu-id="e3d64-113">第 3 階段：導入</span><span class="sxs-lookup"><span data-stu-id="e3d64-113">Phase 3: Onboard</span></span>](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|<span data-ttu-id="e3d64-114">*您在這裡！*</span><span class="sxs-lookup"><span data-stu-id="e3d64-114">*You are here!*</span></span>| | |


<span data-ttu-id="e3d64-115">**歡迎使用 [從 Mcafee 端點安全性遷移 (mcafee) 至 Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)的準備階段**。</span><span class="sxs-lookup"><span data-stu-id="e3d64-115">**Welcome to the Prepare phase of [migrating from McAfee Endpoint Security (McAfee) to Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)**.</span></span> 

<span data-ttu-id="e3d64-116">此遷移階段包含下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e3d64-116">This migration phase includes the following steps:</span></span>
1. [<span data-ttu-id="e3d64-117">在組織裝置中取得及部署更新</span><span class="sxs-lookup"><span data-stu-id="e3d64-117">Get and deploy updates across your organization's devices</span></span>](#get-and-deploy-updates-across-your-organizations-devices)

2. <span data-ttu-id="e3d64-118">[取得 Defender For Endpoint](#get-microsoft-defender-for-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="e3d64-118">[Get Defender for Endpoint](#get-microsoft-defender-for-endpoint).</span></span>

3. <span data-ttu-id="e3d64-119">[授與 Microsoft Defender 資訊安全中心的存取權](#grant-access-to-the-microsoft-defender-security-center)。</span><span class="sxs-lookup"><span data-stu-id="e3d64-119">[Grant access to the Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).</span></span>

4. <span data-ttu-id="e3d64-120">[設定裝置 proxy 和網際網路連線設定](#configure-device-proxy-and-internet-connectivity-settings)。</span><span class="sxs-lookup"><span data-stu-id="e3d64-120">[Configure device proxy and internet connectivity settings](#configure-device-proxy-and-internet-connectivity-settings).</span></span>

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a><span data-ttu-id="e3d64-121">在組織裝置中取得及部署更新</span><span class="sxs-lookup"><span data-stu-id="e3d64-121">Get and deploy updates across your organization's devices</span></span>

<span data-ttu-id="e3d64-122">最佳作法是將組織的裝置和端點保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="e3d64-122">As a best practice, keep your organization's devices and endpoints up to date.</span></span> <span data-ttu-id="e3d64-123">請確定您的 McAfee 端點安全性 (McAfee) 解決方案是最新版本，而且您組織的作業系統和應用程式也會有最新的更新。</span><span class="sxs-lookup"><span data-stu-id="e3d64-123">Make sure your McAfee Endpoint Security (McAfee) solution is up to date, and that the operating systems and apps your organization is also have the latest updates.</span></span> <span data-ttu-id="e3d64-124">現在這樣做可以協助您在遷移至更新至 Defender 時，避免發生問題。</span><span class="sxs-lookup"><span data-stu-id="e3d64-124">Doing this now can help prevent problems later as you migrate to Defender for Endpoint.</span></span>

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a><span data-ttu-id="e3d64-125">確定您的 McAfee 解決方案是最新版本</span><span class="sxs-lookup"><span data-stu-id="e3d64-125">Make sure your McAfee solution is up to date</span></span>

<span data-ttu-id="e3d64-126">將 McAfee 保持在最新狀態，並確定您的組織裝置具有最新的安全性更新。</span><span class="sxs-lookup"><span data-stu-id="e3d64-126">Keep McAfee up to date, and make sure that your organization's devices have the latest security updates.</span></span> <span data-ttu-id="e3d64-127">需要協助？</span><span class="sxs-lookup"><span data-stu-id="e3d64-127">Need help?</span></span> <span data-ttu-id="e3d64-128">以下是一些 McAfee 資源：</span><span class="sxs-lookup"><span data-stu-id="e3d64-128">Here are some McAfee resources:</span></span>

- [<span data-ttu-id="e3d64-129">McAfee Enterprise 產品檔：端點安全性的運作方式</span><span class="sxs-lookup"><span data-stu-id="e3d64-129">McAfee Enterprise Product Documentation: How Endpoint Security Works</span></span>](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [<span data-ttu-id="e3d64-130">McAfee 知識中心技術文章： Windows 安全性 Center 在 Windows 10 上執行時，錯誤地報告端點安全性已停用</span><span class="sxs-lookup"><span data-stu-id="e3d64-130">McAfee Knowledge Center Technical Article: Windows Security Center intermittently incorrectly reports that Endpoint Security is disabled when running on Windows 10</span></span>](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [<span data-ttu-id="e3d64-131">McAfee 知識中心技術文章： Windows 安全性 Center 報表在執行端點安全性時，已停用端點安全性</span><span class="sxs-lookup"><span data-stu-id="e3d64-131">McAfee Knowledge Center Technical Article: Windows Security Center reports Endpoint Security is disabled when Endpoint Security is running</span></span>](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- <span data-ttu-id="e3d64-132">您的 McAfee 支援 ServicePortal ([http://mysupport.mcafee.com](http://mysupport.mcafee.com)) </span><span class="sxs-lookup"><span data-stu-id="e3d64-132">Your McAfee support ServicePortal ([http://mysupport.mcafee.com](http://mysupport.mcafee.com))</span></span>

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a><span data-ttu-id="e3d64-133">確定貴組織的裝置是最新版本</span><span class="sxs-lookup"><span data-stu-id="e3d64-133">Make sure your organization's devices are up to date</span></span>

<span data-ttu-id="e3d64-134">需要協助更新您的組織裝置嗎？</span><span class="sxs-lookup"><span data-stu-id="e3d64-134">Need help updating your organization's devices?</span></span> <span data-ttu-id="e3d64-135">請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="e3d64-135">See the following resources:</span></span>

|<span data-ttu-id="e3d64-136">作業系統</span><span class="sxs-lookup"><span data-stu-id="e3d64-136">OS</span></span> | <span data-ttu-id="e3d64-137">資源</span><span class="sxs-lookup"><span data-stu-id="e3d64-137">Resource</span></span> |
|:--|:--|
|<span data-ttu-id="e3d64-138">Windows</span><span class="sxs-lookup"><span data-stu-id="e3d64-138">Windows</span></span> |[<span data-ttu-id="e3d64-139">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="e3d64-139">Microsoft Update</span></span>](https://www.update.microsoft.com) |
|<span data-ttu-id="e3d64-140">macOS</span><span class="sxs-lookup"><span data-stu-id="e3d64-140">macOS</span></span> | [<span data-ttu-id="e3d64-141">如何更新 Mac 上的軟體</span><span class="sxs-lookup"><span data-stu-id="e3d64-141">How to update the software on your Mac</span></span>](https://support.apple.com/HT201541)|
|<span data-ttu-id="e3d64-142">iOS</span><span class="sxs-lookup"><span data-stu-id="e3d64-142">iOS</span></span> |[<span data-ttu-id="e3d64-143">更新 iPhone、iPad 或 iPod 觸控</span><span class="sxs-lookup"><span data-stu-id="e3d64-143">Update your iPhone, iPad, or iPod touch</span></span>](https://support.apple.com/HT204204)|
|<span data-ttu-id="e3d64-144">Android</span><span class="sxs-lookup"><span data-stu-id="e3d64-144">Android</span></span> |[<span data-ttu-id="e3d64-145">檢查 & 更新您的 Android 版本</span><span class="sxs-lookup"><span data-stu-id="e3d64-145">Check & update your Android version</span></span>](https://support.google.com/android/answer/7680439) |
|<span data-ttu-id="e3d64-146">Linux</span><span class="sxs-lookup"><span data-stu-id="e3d64-146">Linux</span></span> | [<span data-ttu-id="e3d64-147">Linux 101：更新您的系統</span><span class="sxs-lookup"><span data-stu-id="e3d64-147">Linux 101: Updating Your System</span></span>](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a><span data-ttu-id="e3d64-148">取得 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e3d64-148">Get Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="e3d64-149">現在，您已更新組織的裝置，下一個步驟是取得 Defender for Endpoint、指派授權，並確定服務已布建。</span><span class="sxs-lookup"><span data-stu-id="e3d64-149">Now that you've updated your organization's devices, the next step is to get Defender for Endpoint, assign licenses, and make sure the service is provisioned.</span></span>

1. <span data-ttu-id="e3d64-150">立即購買或試用 Endpoint for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="e3d64-150">Buy or try Defender for Endpoint today.</span></span> <span data-ttu-id="e3d64-151">[開始免費試用或要求報價](https://aka.ms/mdatp)。</span><span class="sxs-lookup"><span data-stu-id="e3d64-151">[Start a free trial or request a quote](https://aka.ms/mdatp).</span></span> 

2. <span data-ttu-id="e3d64-152">確認已正確布建您的授權。</span><span class="sxs-lookup"><span data-stu-id="e3d64-152">Verify that your licenses are properly provisioned.</span></span> <span data-ttu-id="e3d64-153">[檢查您的授權狀態](production-deployment.md#check-license-state)。</span><span class="sxs-lookup"><span data-stu-id="e3d64-153">[Check your license state](production-deployment.md#check-license-state).</span></span>

3. <span data-ttu-id="e3d64-154">以全域管理員或安全性管理員的身分，設定您專用的 Defender for Endpoint 的雲端實例。</span><span class="sxs-lookup"><span data-stu-id="e3d64-154">As a global administrator or security administrator, set up your dedicated cloud instance of Defender for Endpoint.</span></span> <span data-ttu-id="e3d64-155">請參閱 [適用于 Endpoint 的 Defender 設定：承租人設定](production-deployment.md#tenant-configuration)。</span><span class="sxs-lookup"><span data-stu-id="e3d64-155">See [Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).</span></span>

4. <span data-ttu-id="e3d64-156">如果您組織中)  (等端點使用 proxy 來存取網際網路，請參閱 [Defender For Endpoint setup： Network configuration](production-deployment.md#network-configuration)。</span><span class="sxs-lookup"><span data-stu-id="e3d64-156">If endpoints (such as devices) in your organization use a proxy to access the internet, see [Defender for Endpoint setup: Network configuration](production-deployment.md#network-configuration).</span></span>
 
<span data-ttu-id="e3d64-157">此時，您已準備好授與安全性管理員的存取權，以及將使用 Microsoft Defender 資訊安全中心 () 的安全性操作員 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。</span><span class="sxs-lookup"><span data-stu-id="e3d64-157">At this point, you are ready to grant access to your security administrators and security operators who will use the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)).</span></span> 

> [!NOTE]
> <span data-ttu-id="e3d64-158">Microsoft Defender 資訊安全中心有時也稱為端點入口網站的 Defender。</span><span class="sxs-lookup"><span data-stu-id="e3d64-158">The Microsoft Defender Security Center is sometimes referred to as the Defender for Endpoint portal.</span></span> 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a><span data-ttu-id="e3d64-159">授與 Microsoft Defender 資訊安全中心的存取權</span><span class="sxs-lookup"><span data-stu-id="e3d64-159">Grant access to the Microsoft Defender Security Center</span></span>

<span data-ttu-id="e3d64-160">Microsoft Defender 資訊安全中心 ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) 是您用來存取及設定用於端點之 Defender 的功能。</span><span class="sxs-lookup"><span data-stu-id="e3d64-160">The Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) is where you access and configure features and capabilities of Defender for Endpoint.</span></span> <span data-ttu-id="e3d64-161">若要深入瞭解，請參閱[Microsoft Defender 資訊安全中心的總覽](use.md)。</span><span class="sxs-lookup"><span data-stu-id="e3d64-161">To learn more, see [Overview of the Microsoft Defender Security Center](use.md).</span></span>

<span data-ttu-id="e3d64-162">您可以使用基本許可權或以角色為基礎的存取控制 (RBAC) 授與 Microsoft Defender 資訊安全中心許可權。</span><span class="sxs-lookup"><span data-stu-id="e3d64-162">Permissions to the Microsoft Defender Security Center can be granted by using either basic permissions or role-based access control (RBAC).</span></span> <span data-ttu-id="e3d64-163">我們建議使用 RBAC，讓您可以更細微地控制許可權。</span><span class="sxs-lookup"><span data-stu-id="e3d64-163">We recommend using RBAC so that you have more granular control over permissions.</span></span>

1. <span data-ttu-id="e3d64-164">規劃安全性管理員及安全性操作員的角色和許可權。</span><span class="sxs-lookup"><span data-stu-id="e3d64-164">Plan the roles and permissions for your security administrators and security operators.</span></span> <span data-ttu-id="e3d64-165">請參閱以 [角色為基礎的存取控制](prepare-deployment.md#role-based-access-control)。</span><span class="sxs-lookup"><span data-stu-id="e3d64-165">See [Role-based access control](prepare-deployment.md#role-based-access-control).</span></span>

2. <span data-ttu-id="e3d64-166">設定和設定 RBAC。</span><span class="sxs-lookup"><span data-stu-id="e3d64-166">Set up and configure RBAC.</span></span> <span data-ttu-id="e3d64-167">建議使用[Intune](/mem/intune/fundamentals/what-is-intune)設定 RBAC，尤其是當您的組織使用 Windows 10、macOS、iOS 和 Android 裝置的組合時。</span><span class="sxs-lookup"><span data-stu-id="e3d64-167">We recommend using [Intune](/mem/intune/fundamentals/what-is-intune) to configure RBAC, especially if your organization is using a combination of Windows 10, macOS, iOS, and Android devices.</span></span> <span data-ttu-id="e3d64-168">請參閱 [使用 Intune 設定 RBAC](/mem/intune/fundamentals/role-based-access-control)。</span><span class="sxs-lookup"><span data-stu-id="e3d64-168">See [setting up RBAC using Intune](/mem/intune/fundamentals/role-based-access-control).</span></span>

    <span data-ttu-id="e3d64-169">如果您的組織需要 Intune 以外的方法，請選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="e3d64-169">If your organization requires a method other than Intune, choose one of the following options:</span></span>

    - [<span data-ttu-id="e3d64-170">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e3d64-170">Configuration Manager</span></span>](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [<span data-ttu-id="e3d64-171">高級群組原則管理</span><span class="sxs-lookup"><span data-stu-id="e3d64-171">Advanced Group Policy Management</span></span>](/microsoft-desktop-optimization-pack/agpm)

    - [<span data-ttu-id="e3d64-172">Windows系統管理中心</span><span class="sxs-lookup"><span data-stu-id="e3d64-172">Windows Admin Center</span></span>](/windows-server/manage/windows-admin-center/overview)

3. <span data-ttu-id="e3d64-173">授與 Microsoft Defender 資訊安全中心的存取權。</span><span class="sxs-lookup"><span data-stu-id="e3d64-173">Grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="e3d64-174"> (需要協助嗎？</span><span class="sxs-lookup"><span data-stu-id="e3d64-174">(Need help?</span></span> <span data-ttu-id="e3d64-175">請參閱 [使用 RBAC) 管理入口網站存取](rbac.md) 。</span><span class="sxs-lookup"><span data-stu-id="e3d64-175">See [Manage portal access using RBAC](rbac.md)).</span></span>

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="e3d64-176">設定裝置 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="e3d64-176">Configure device proxy and internet connectivity settings</span></span>

<span data-ttu-id="e3d64-177">若要啟用裝置和 Defender for Endpoint 之間的通訊，請設定 proxy 和網際網路設定。</span><span class="sxs-lookup"><span data-stu-id="e3d64-177">To enable communication between your devices and Defender for Endpoint, configure proxy and internet settings.</span></span> <span data-ttu-id="e3d64-178">下表包含可用於設定各種作業系統和功能之 proxy 和網際網路設定的資源連結：</span><span class="sxs-lookup"><span data-stu-id="e3d64-178">The following table includes links to resources you can use to configure your proxy and internet settings for various operating systems and capabilities:</span></span>

|<span data-ttu-id="e3d64-179">功能</span><span class="sxs-lookup"><span data-stu-id="e3d64-179">Capabilities</span></span>  | <span data-ttu-id="e3d64-180">作業系統</span><span class="sxs-lookup"><span data-stu-id="e3d64-180">Operating System</span></span> | <span data-ttu-id="e3d64-181">資源</span><span class="sxs-lookup"><span data-stu-id="e3d64-181">Resources</span></span> |
|--|--|--|
| <span data-ttu-id="e3d64-182"> (EDR[的端點偵測和回應](overview-endpoint-detection-response.md)) </span><span class="sxs-lookup"><span data-stu-id="e3d64-182">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR)</span></span> | [<span data-ttu-id="e3d64-183">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e3d64-183">Windows 10</span></span>](/windows/release-health/release-information) <p> [<span data-ttu-id="e3d64-184">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e3d64-184">Windows Server 2019</span></span>](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[<span data-ttu-id="e3d64-185">Windows伺服器1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="e3d64-185">Windows Server 1803 or later</span></span>](/windows-server/get-started/whats-new-in-windows-server-1803)  | [<span data-ttu-id="e3d64-186">設定電腦 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="e3d64-186">Configure machine proxy and internet connectivity settings</span></span>](configure-proxy-internet.md) |
|<span data-ttu-id="e3d64-187">EDR</span><span class="sxs-lookup"><span data-stu-id="e3d64-187">EDR</span></span> | [<span data-ttu-id="e3d64-188">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="e3d64-188">Windows Server 2016</span></span>](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[<span data-ttu-id="e3d64-189">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="e3d64-189">Windows Server 2012 R2</span></span>](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[<span data-ttu-id="e3d64-190">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="e3d64-190">Windows Server 2008 R2 SP1</span></span>](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[<span data-ttu-id="e3d64-191">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="e3d64-191">Windows 8.1</span></span>](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[<span data-ttu-id="e3d64-192">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="e3d64-192">Windows 7 SP1</span></span>](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) | [<span data-ttu-id="e3d64-193">設定 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="e3d64-193">Configure proxy and internet connectivity settings</span></span>](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|<span data-ttu-id="e3d64-194">EDR</span><span class="sxs-lookup"><span data-stu-id="e3d64-194">EDR</span></span>  |<span data-ttu-id="e3d64-195">macOS：</span><span class="sxs-lookup"><span data-stu-id="e3d64-195">macOS:</span></span> <p><span data-ttu-id="e3d64-196">11.3.1 (大型 Sur) </span><span class="sxs-lookup"><span data-stu-id="e3d64-196">11.3.1 (Big Sur)</span></span><p><span data-ttu-id="e3d64-197">10.15 (Catalina) </span><span class="sxs-lookup"><span data-stu-id="e3d64-197">10.15 (Catalina)</span></span><p><span data-ttu-id="e3d64-198">10.14 (Mojave) </span><span class="sxs-lookup"><span data-stu-id="e3d64-198">10.14 (Mojave)</span></span>  | [<span data-ttu-id="e3d64-199">MacOS 上的 Defender for Endpoint： Network connections</span><span class="sxs-lookup"><span data-stu-id="e3d64-199">Defender for Endpoint on macOS: Network connections</span></span>](microsoft-defender-endpoint-mac.md#network-connections) |
|[<span data-ttu-id="e3d64-200">Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="e3d64-200">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md) | [<span data-ttu-id="e3d64-201">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e3d64-201">Windows 10</span></span>](/windows/release-health/release-information) <p> [<span data-ttu-id="e3d64-202">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e3d64-202">Windows Server 2019</span></span>](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[<span data-ttu-id="e3d64-203">Windows伺服器1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="e3d64-203">Windows Server 1803 or later</span></span>](/windows-server/get-started/whats-new-in-windows-server-1803) <p>[<span data-ttu-id="e3d64-204">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="e3d64-204">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016) |[<span data-ttu-id="e3d64-205">設定及驗證 Microsoft Defender 防毒軟體網路連線</span><span class="sxs-lookup"><span data-stu-id="e3d64-205">Configure and validate Microsoft Defender Antivirus network connections</span></span>](configure-network-connections-microsoft-defender-antivirus.md) |
|<span data-ttu-id="e3d64-206">防毒</span><span class="sxs-lookup"><span data-stu-id="e3d64-206">Antivirus</span></span> |<span data-ttu-id="e3d64-207">macOS：</span><span class="sxs-lookup"><span data-stu-id="e3d64-207">macOS:</span></span> <p><span data-ttu-id="e3d64-208">11.3.1 (大型 Sur) </span><span class="sxs-lookup"><span data-stu-id="e3d64-208">11.3.1 (Big Sur)</span></span><p><span data-ttu-id="e3d64-209">10.15 (Catalina) </span><span class="sxs-lookup"><span data-stu-id="e3d64-209">10.15 (Catalina)</span></span><p><span data-ttu-id="e3d64-210">10.14 (Mojave) </span><span class="sxs-lookup"><span data-stu-id="e3d64-210">10.14 (Mojave)</span></span> |[<span data-ttu-id="e3d64-211">MacOS 上的 Defender for Endpoint： Network connections</span><span class="sxs-lookup"><span data-stu-id="e3d64-211">Defender for Endpoint on macOS: Network connections</span></span>](microsoft-defender-endpoint-mac.md#network-connections) |
|<span data-ttu-id="e3d64-212">防毒</span><span class="sxs-lookup"><span data-stu-id="e3d64-212">Antivirus</span></span> |<span data-ttu-id="e3d64-213">Linux：</span><span class="sxs-lookup"><span data-stu-id="e3d64-213">Linux:</span></span> <p><span data-ttu-id="e3d64-214">RHEL 7.2 +</span><span class="sxs-lookup"><span data-stu-id="e3d64-214">RHEL 7.2+</span></span><p><span data-ttu-id="e3d64-215">CentOS Linux 7.2 +</span><span class="sxs-lookup"><span data-stu-id="e3d64-215">CentOS Linux 7.2+</span></span><p><span data-ttu-id="e3d64-216">Ubuntu 16 LTS 或更高版本 LTS</span><span class="sxs-lookup"><span data-stu-id="e3d64-216">Ubuntu 16 LTS, or higher LTS</span></span><p><span data-ttu-id="e3d64-217">SLES 12 +</span><span class="sxs-lookup"><span data-stu-id="e3d64-217">SLES 12+</span></span><p><span data-ttu-id="e3d64-218">Debian 9 +</span><span class="sxs-lookup"><span data-stu-id="e3d64-218">Debian 9+</span></span><p><span data-ttu-id="e3d64-219">Oracle Linux 7。2</span><span class="sxs-lookup"><span data-stu-id="e3d64-219">Oracle Linux 7.2</span></span> |[<span data-ttu-id="e3d64-220">Linux 上的 Defender Endpoint：網路連接</span><span class="sxs-lookup"><span data-stu-id="e3d64-220">Defender for Endpoint on Linux: Network connections</span></span>](microsoft-defender-endpoint-linux.md#network-connections) 

## <a name="next-step"></a><span data-ttu-id="e3d64-221">下一步</span><span class="sxs-lookup"><span data-stu-id="e3d64-221">Next step</span></span>

<span data-ttu-id="e3d64-222">**恭喜**！</span><span class="sxs-lookup"><span data-stu-id="e3d64-222">**Congratulations**!</span></span> <span data-ttu-id="e3d64-223">您已完成 [從 McAfee 向 Defender For Endpoint 進行遷移](mcafee-to-microsoft-defender-migration.md#the-migration-process)的 **準備** 階段！</span><span class="sxs-lookup"><span data-stu-id="e3d64-223">You have completed the **Prepare** phase of [migrating from McAfee to Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)!</span></span>

- <span data-ttu-id="e3d64-224">[繼續設定端點的 Defender](mcafee-to-microsoft-defender-setup.md)。</span><span class="sxs-lookup"><span data-stu-id="e3d64-224">[Proceed to set up Defender for Endpoint](mcafee-to-microsoft-defender-setup.md).</span></span>
