---
title: Symantec to Microsoft Defender for Endpoint-階段1，準備
description: 這是第1階段，準備從 Symantec 遷移至 Microsoft Defender for Endpoint。
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 7fe0eb8adc90c259d31f237082effc80c5e8622c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537976"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a><span data-ttu-id="f970e-104">從 Symantec 遷移-階段1：準備遷移</span><span class="sxs-lookup"><span data-stu-id="f970e-104">Migrate from Symantec - Phase 1: Prepare for your migration</span></span>

<span data-ttu-id="f970e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f970e-105">**Applies to:**</span></span>
- [<span data-ttu-id="f970e-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f970e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f970e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f970e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

|![階段 1：準備](images/phase-diagrams/prepare.png)<br/><span data-ttu-id="f970e-109">階段 1：準備</span><span class="sxs-lookup"><span data-stu-id="f970e-109">Phase 1: Prepare</span></span> |<span data-ttu-id="f970e-110">[![階段 2：設定](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)</span><span class="sxs-lookup"><span data-stu-id="f970e-110">[![Phase 2: Set up](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)</span></span><br/>[<span data-ttu-id="f970e-111">階段 2：設定</span><span class="sxs-lookup"><span data-stu-id="f970e-111">Phase 2: Set up</span></span>](symantec-to-microsoft-defender-atp-setup.md) |<span data-ttu-id="f970e-112">[![第 3 階段：導入](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)</span><span class="sxs-lookup"><span data-stu-id="f970e-112">[![Phase 3: Onboard](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)</span></span><br/>[<span data-ttu-id="f970e-113">第 3 階段：導入</span><span class="sxs-lookup"><span data-stu-id="f970e-113">Phase 3: Onboard</span></span>](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|<span data-ttu-id="f970e-114">*您在這裡！*</span><span class="sxs-lookup"><span data-stu-id="f970e-114">*You are here!*</span></span>| | |


<span data-ttu-id="f970e-115">**歡迎使用 [從 Symantec 遷移至 Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)的準備階段**。</span><span class="sxs-lookup"><span data-stu-id="f970e-115">**Welcome to the Prepare phase of [migrating from Symantec to Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**.</span></span> 

<span data-ttu-id="f970e-116">此遷移階段包含下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f970e-116">This migration phase includes the following steps:</span></span>

1. <span data-ttu-id="f970e-117">[更新您組織的裝置](#update-your-organizations-devices)。</span><span class="sxs-lookup"><span data-stu-id="f970e-117">[Update your organization's devices](#update-your-organizations-devices).</span></span>

2. <span data-ttu-id="f970e-118">[取得 Microsoft Defender For Endpoint](#get-microsoft-defender-for-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="f970e-118">[Get Microsoft Defender for Endpoint](#get-microsoft-defender-for-endpoint).</span></span>

3. <span data-ttu-id="f970e-119">[授與 Microsoft Defender 資訊安全中心的存取權](#grant-access-to-the-microsoft-defender-security-center)。</span><span class="sxs-lookup"><span data-stu-id="f970e-119">[Grant access to the Microsoft Defender Security Center](#grant-access-to-the-microsoft-defender-security-center).</span></span>

4. [<span data-ttu-id="f970e-120">設定裝置 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="f970e-120">Configure device proxy and internet connectivity settings</span></span>](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="update-your-organizations-devices"></a><span data-ttu-id="f970e-121">更新您組織的裝置</span><span class="sxs-lookup"><span data-stu-id="f970e-121">Update your organization's devices</span></span>

<span data-ttu-id="f970e-122">最佳作法是將組織的裝置和端點保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="f970e-122">As a best practice, keep your organization's devices and endpoints up to date.</span></span> <span data-ttu-id="f970e-123">請確定現有的 endpoint protection 和防病毒方案是最新的，而且您組織的作業系統和應用程式也會有最新的更新。</span><span class="sxs-lookup"><span data-stu-id="f970e-123">Make sure your existing endpoint protection and antivirus solution is up to date, and that the operating systems and apps your organization is also have the latest updates.</span></span> <span data-ttu-id="f970e-124">現在這樣做可以協助您在遷移至更新至 Defender 時，避免發生問題。</span><span class="sxs-lookup"><span data-stu-id="f970e-124">Doing this now can help prevent problems later as you migrate to Defender for Endpoint.</span></span>

### <a name="make-sure-symantec-is-up-to-date"></a><span data-ttu-id="f970e-125">請確定 Symantec 是最新版本</span><span class="sxs-lookup"><span data-stu-id="f970e-125">Make sure Symantec is up to date</span></span>

<span data-ttu-id="f970e-126">保留現有的 endpoint protection 方案，並確定您組織的裝置具有最新的安全性更新。</span><span class="sxs-lookup"><span data-stu-id="f970e-126">Keep your existing endpoint protection solution up to date, and make sure that your organization's devices have the latest security updates.</span></span>

<span data-ttu-id="f970e-127">需要協助？</span><span class="sxs-lookup"><span data-stu-id="f970e-127">Need help?</span></span> <span data-ttu-id="f970e-128">請參閱 Broadcom 的檔： [Symantec Endpoint Protection 安裝與管理指南](https://techdocs.broadcom.com/us/en/symantec-security-software/endpoint-security-and-management/endpoint-protection/all.html)</span><span class="sxs-lookup"><span data-stu-id="f970e-128">See Broadcom's documentation: [Symantec Endpoint Protection Installation and Administration Guide](https://techdocs.broadcom.com/us/en/symantec-security-software/endpoint-security-and-management/endpoint-protection/all.html)</span></span>

### <a name="make-sure-your-endpoints-are-up-to-date"></a><span data-ttu-id="f970e-129">確定您的端點是最新的</span><span class="sxs-lookup"><span data-stu-id="f970e-129">Make sure your endpoints are up to date</span></span>

<span data-ttu-id="f970e-130">需要協助更新您的組織裝置嗎？</span><span class="sxs-lookup"><span data-stu-id="f970e-130">Need help updating your organization's devices?</span></span> <span data-ttu-id="f970e-131">請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="f970e-131">See the following resources:</span></span>


|<span data-ttu-id="f970e-132">作業系統</span><span class="sxs-lookup"><span data-stu-id="f970e-132">OS</span></span>  |<span data-ttu-id="f970e-133">資源</span><span class="sxs-lookup"><span data-stu-id="f970e-133">Resource</span></span>  |
|---------|---------|
|<span data-ttu-id="f970e-134">Windows</span><span class="sxs-lookup"><span data-stu-id="f970e-134">Windows</span></span>     | [<span data-ttu-id="f970e-135">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="f970e-135">Microsoft Update</span></span>](https://www.update.microsoft.com/)        |
|<span data-ttu-id="f970e-136">macOS</span><span class="sxs-lookup"><span data-stu-id="f970e-136">macOS</span></span>     | [<span data-ttu-id="f970e-137">如何更新 Mac 上的軟體</span><span class="sxs-lookup"><span data-stu-id="f970e-137">How to update the software on your Mac</span></span>](https://support.apple.com/HT201541)         |
|<span data-ttu-id="f970e-138">iOS</span><span class="sxs-lookup"><span data-stu-id="f970e-138">iOS</span></span>     | [<span data-ttu-id="f970e-139">更新 iPhone、iPad 或 iPod 觸控</span><span class="sxs-lookup"><span data-stu-id="f970e-139">Update your iPhone, iPad, or iPod touch</span></span>](https://support.apple.com/HT204204)         |
|<span data-ttu-id="f970e-140">Android</span><span class="sxs-lookup"><span data-stu-id="f970e-140">Android</span></span>     | [<span data-ttu-id="f970e-141">檢查 & 更新您的 Android 版本</span><span class="sxs-lookup"><span data-stu-id="f970e-141">Check & update your Android version</span></span>](https://support.google.com/android/answer/7680439)        |
|<span data-ttu-id="f970e-142">Linux</span><span class="sxs-lookup"><span data-stu-id="f970e-142">Linux</span></span>     | [<span data-ttu-id="f970e-143">Linux 101：更新您的系統</span><span class="sxs-lookup"><span data-stu-id="f970e-143">Linux 101: Updating Your System</span></span>](https://www.linux.com/training-tutorials/linux-101-updating-your-system)        |


## <a name="get-microsoft-defender-for-endpoint"></a><span data-ttu-id="f970e-144">取得 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f970e-144">Get Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="f970e-145">現在，您已更新組織的裝置，下一個步驟是取得 Defender for Endpoint、指派授權，並確定服務已布建。</span><span class="sxs-lookup"><span data-stu-id="f970e-145">Now that you've updated your organization's devices, the next step is to get Defender for Endpoint, assign licenses, and make sure the service is provisioned.</span></span>

1. <span data-ttu-id="f970e-146">立即購買或試用 Endpoint for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f970e-146">Buy or try Defender for Endpoint today.</span></span> <span data-ttu-id="f970e-147">[請造訪用於端點的 Defender，以開始免費試用版或要求報價](https://aka.ms/mdatp)。</span><span class="sxs-lookup"><span data-stu-id="f970e-147">[Visit Defender for Endpoint to start a free trial or request a quote](https://aka.ms/mdatp).</span></span> 

2. <span data-ttu-id="f970e-148">確認已正確布建您的授權。</span><span class="sxs-lookup"><span data-stu-id="f970e-148">Verify that your licenses are properly provisioned.</span></span> <span data-ttu-id="f970e-149">[檢查您的授權狀態](production-deployment.md#check-license-state)。</span><span class="sxs-lookup"><span data-stu-id="f970e-149">[Check your license state](production-deployment.md#check-license-state).</span></span>

3. <span data-ttu-id="f970e-150">以全域管理員或安全性管理員的身分，設定您專用的 Defender for Endpoint 的雲端實例。</span><span class="sxs-lookup"><span data-stu-id="f970e-150">As a global administrator or security administrator, set up your dedicated cloud instance of Defender for Endpoint.</span></span> <span data-ttu-id="f970e-151">請參閱 [適用于 Endpoint 的 Defender 設定：承租人設定](production-deployment.md#tenant-configuration)。</span><span class="sxs-lookup"><span data-stu-id="f970e-151">See [Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).</span></span>

4. <span data-ttu-id="f970e-152">如果您組織中)  (等端點使用 proxy 來存取網際網路，請參閱 [Defender For Endpoint setup： Network configuration](production-deployment.md#network-configuration)。</span><span class="sxs-lookup"><span data-stu-id="f970e-152">If endpoints (such as devices) in your organization use a proxy to access the internet, see [Defender for Endpoint setup: Network configuration](production-deployment.md#network-configuration).</span></span>
 
<span data-ttu-id="f970e-153">此時，您已準備好授與安全性管理員的存取權，以及將使用 Microsoft Defender 資訊安全中心 () 的安全性操作員 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。</span><span class="sxs-lookup"><span data-stu-id="f970e-153">At this point, you are ready to grant access to your security administrators and security operators who will use the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)).</span></span> 

> [!NOTE]
> <span data-ttu-id="f970e-154">Microsoft Defender 資訊安全中心有時也稱為端點入口網站的 Defender。</span><span class="sxs-lookup"><span data-stu-id="f970e-154">The Microsoft Defender Security Center is sometimes referred to as the Defender for Endpoint portal.</span></span> 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a><span data-ttu-id="f970e-155">授與 Microsoft Defender 資訊安全中心的存取權</span><span class="sxs-lookup"><span data-stu-id="f970e-155">Grant access to the Microsoft Defender Security Center</span></span>

<span data-ttu-id="f970e-156">Microsoft Defender 資訊安全中心 ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) 是您用來存取及設定用於端點之 Defender 的功能。</span><span class="sxs-lookup"><span data-stu-id="f970e-156">The Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) is where you access and configure features and capabilities of Defender for Endpoint.</span></span> <span data-ttu-id="f970e-157">若要深入瞭解，請參閱[Microsoft Defender 資訊安全中心的總覽](use.md)。</span><span class="sxs-lookup"><span data-stu-id="f970e-157">To learn more, see [Overview of the Microsoft Defender Security Center](use.md).</span></span>

<span data-ttu-id="f970e-158">您可以使用基本許可權或以角色為基礎的存取控制 (RBAC) 授與 Microsoft Defender 資訊安全中心許可權。</span><span class="sxs-lookup"><span data-stu-id="f970e-158">Permissions to the Microsoft Defender Security Center can be granted by using either basic permissions or role-based access control (RBAC).</span></span> <span data-ttu-id="f970e-159">我們建議使用 RBAC，讓您可以更細微地控制許可權。</span><span class="sxs-lookup"><span data-stu-id="f970e-159">We recommend using RBAC so that you have more granular control over permissions.</span></span>

1. <span data-ttu-id="f970e-160">規劃安全性管理員及安全性操作員的角色和許可權。</span><span class="sxs-lookup"><span data-stu-id="f970e-160">Plan the roles and permissions for your security administrators and security operators.</span></span> <span data-ttu-id="f970e-161">請參閱以 [角色為基礎的存取控制](prepare-deployment.md#role-based-access-control)。</span><span class="sxs-lookup"><span data-stu-id="f970e-161">See [Role-based access control](prepare-deployment.md#role-based-access-control).</span></span>

2. <span data-ttu-id="f970e-162">設定和設定 RBAC。</span><span class="sxs-lookup"><span data-stu-id="f970e-162">Set up and configure RBAC.</span></span> <span data-ttu-id="f970e-163">建議使用[Intune](/mem/intune/fundamentals/what-is-intune)設定 RBAC，尤其是當您的組織使用 Windows 10、macOS、iOS 和 Android 裝置的組合時。</span><span class="sxs-lookup"><span data-stu-id="f970e-163">We recommend using [Intune](/mem/intune/fundamentals/what-is-intune) to configure RBAC, especially if your organization is using a combination of Windows 10, macOS, iOS, and Android devices.</span></span> <span data-ttu-id="f970e-164">請參閱 [使用 Intune 設定 RBAC](/mem/intune/fundamentals/role-based-access-control)。</span><span class="sxs-lookup"><span data-stu-id="f970e-164">See [setting up RBAC using Intune](/mem/intune/fundamentals/role-based-access-control).</span></span>

   <span data-ttu-id="f970e-165">如果您的組織需要 Intune 以外的方法，請選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="f970e-165">If your organization requires a method other than Intune, choose one of the following options:</span></span>

    - [<span data-ttu-id="f970e-166">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f970e-166">Configuration Manager</span></span>](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [<span data-ttu-id="f970e-167">高級群組原則管理</span><span class="sxs-lookup"><span data-stu-id="f970e-167">Advanced Group Policy Management</span></span>](/microsoft-desktop-optimization-pack/agpm)

    - [<span data-ttu-id="f970e-168">Windows系統管理中心</span><span class="sxs-lookup"><span data-stu-id="f970e-168">Windows Admin Center</span></span>](/windows-server/manage/windows-admin-center/overview)

3. <span data-ttu-id="f970e-169">授與 Microsoft Defender 資訊安全中心的存取權。</span><span class="sxs-lookup"><span data-stu-id="f970e-169">Grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="f970e-170"> (需要協助嗎？</span><span class="sxs-lookup"><span data-stu-id="f970e-170">(Need help?</span></span> <span data-ttu-id="f970e-171">請參閱 [使用 RBAC) 管理入口網站存取](rbac.md) 。</span><span class="sxs-lookup"><span data-stu-id="f970e-171">See [Manage portal access using RBAC](rbac.md)).</span></span>

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="f970e-172">設定裝置 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="f970e-172">Configure device proxy and internet connectivity settings</span></span>

<span data-ttu-id="f970e-173">若要啟用裝置和 Defender for Endpoint 之間的通訊，請設定 proxy 和網際網路設定。</span><span class="sxs-lookup"><span data-stu-id="f970e-173">To enable communication between your devices and Defender for Endpoint, configure proxy and internet settings.</span></span> <span data-ttu-id="f970e-174">下表包含可用於設定各種作業系統和功能之 proxy 和網際網路設定的資源連結：</span><span class="sxs-lookup"><span data-stu-id="f970e-174">The following table includes links to resources you can use to configure your proxy and internet settings for various operating systems and capabilities:</span></span>

|<span data-ttu-id="f970e-175">功能</span><span class="sxs-lookup"><span data-stu-id="f970e-175">Capabilities</span></span>  | <span data-ttu-id="f970e-176">作業系統</span><span class="sxs-lookup"><span data-stu-id="f970e-176">Operating System</span></span> | <span data-ttu-id="f970e-177">資源</span><span class="sxs-lookup"><span data-stu-id="f970e-177">Resources</span></span> |
|:----|:----|:---|
|<span data-ttu-id="f970e-178"> (EDR[的端點偵測和回應](overview-endpoint-detection-response.md)) </span><span class="sxs-lookup"><span data-stu-id="f970e-178">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR)</span></span> | [<span data-ttu-id="f970e-179">Windows 10</span><span class="sxs-lookup"><span data-stu-id="f970e-179">Windows 10</span></span>](/windows/release-health/release-information/) <p> [<span data-ttu-id="f970e-180">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f970e-180">Windows Server 2019</span></span>](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[<span data-ttu-id="f970e-181">Windows伺服器1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="f970e-181">Windows Server 1803 or later</span></span>](/windows-server/get-started/whats-new-in-windows-server-1803)  |[<span data-ttu-id="f970e-182">設定電腦 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="f970e-182">Configure machine proxy and internet connectivity settings</span></span>](configure-proxy-internet.md) |
|<span data-ttu-id="f970e-183">EDR</span><span class="sxs-lookup"><span data-stu-id="f970e-183">EDR</span></span> | [<span data-ttu-id="f970e-184">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f970e-184">Windows Server 2016</span></span>](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[<span data-ttu-id="f970e-185">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f970e-185">Windows Server 2012 R2</span></span>](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[<span data-ttu-id="f970e-186">Windows伺服器 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="f970e-186">Windows Server 2008 R2 SP1</span></span>](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[<span data-ttu-id="f970e-187">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="f970e-187">Windows 8.1</span></span>](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[<span data-ttu-id="f970e-188">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="f970e-188">Windows 7 SP1</span></span>](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[<span data-ttu-id="f970e-189">設定 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="f970e-189">Configure proxy and internet connectivity settings</span></span>](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|<span data-ttu-id="f970e-190">EDR</span><span class="sxs-lookup"><span data-stu-id="f970e-190">EDR</span></span>  |<span data-ttu-id="f970e-191">macOS：</span><span class="sxs-lookup"><span data-stu-id="f970e-191">macOS:</span></span> <p><span data-ttu-id="f970e-192">11.3.1 (大型 Sur) </span><span class="sxs-lookup"><span data-stu-id="f970e-192">11.3.1 (Big Sur)</span></span><p><span data-ttu-id="f970e-193">10.15 (Catalina) </span><span class="sxs-lookup"><span data-stu-id="f970e-193">10.15 (Catalina)</span></span><p><span data-ttu-id="f970e-194">10.14 (Mojave) </span><span class="sxs-lookup"><span data-stu-id="f970e-194">10.14 (Mojave)</span></span> |[<span data-ttu-id="f970e-195">MacOS 上的 Defender for Endpoint： Network connections</span><span class="sxs-lookup"><span data-stu-id="f970e-195">Defender for Endpoint on macOS: Network connections</span></span>](microsoft-defender-endpoint-mac.md#network-connections) |
|[<span data-ttu-id="f970e-196">Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="f970e-196">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md) |[<span data-ttu-id="f970e-197">Windows 10</span><span class="sxs-lookup"><span data-stu-id="f970e-197">Windows 10</span></span>](/windows/release-health/release-information/)<p>[<span data-ttu-id="f970e-198">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f970e-198">Windows Server 2019</span></span>](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[<span data-ttu-id="f970e-199">Windows伺服器1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="f970e-199">Windows Server 1803 or later</span></span>](/windows-server/get-started/whats-new-in-windows-server-1803)<p>[<span data-ttu-id="f970e-200">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f970e-200">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016) |[<span data-ttu-id="f970e-201">設定及驗證 Microsoft Defender 防毒軟體網路連線</span><span class="sxs-lookup"><span data-stu-id="f970e-201">Configure and validate Microsoft Defender Antivirus network connections</span></span>](configure-network-connections-microsoft-defender-antivirus.md) |
|<span data-ttu-id="f970e-202">防毒</span><span class="sxs-lookup"><span data-stu-id="f970e-202">Antivirus</span></span> |<span data-ttu-id="f970e-203">macOS：</span><span class="sxs-lookup"><span data-stu-id="f970e-203">macOS:</span></span> <p><span data-ttu-id="f970e-204">11.3.1 (大型 Sur) </span><span class="sxs-lookup"><span data-stu-id="f970e-204">11.3.1 (Big Sur)</span></span><p><span data-ttu-id="f970e-205">10.15 (Catalina) </span><span class="sxs-lookup"><span data-stu-id="f970e-205">10.15 (Catalina)</span></span><p><span data-ttu-id="f970e-206">10.14 (Mojave) </span><span class="sxs-lookup"><span data-stu-id="f970e-206">10.14 (Mojave)</span></span>  |[<span data-ttu-id="f970e-207">Mac 版上端點的 Defender：網路連接</span><span class="sxs-lookup"><span data-stu-id="f970e-207">Defender for Endpoint on Mac: Network connections</span></span>](microsoft-defender-endpoint-mac.md#network-connections) |
|<span data-ttu-id="f970e-208">防毒</span><span class="sxs-lookup"><span data-stu-id="f970e-208">Antivirus</span></span> |<span data-ttu-id="f970e-209">Linux：</span><span class="sxs-lookup"><span data-stu-id="f970e-209">Linux:</span></span> <p><span data-ttu-id="f970e-210">RHEL 7.2 +</span><span class="sxs-lookup"><span data-stu-id="f970e-210">RHEL 7.2+</span></span><p><span data-ttu-id="f970e-211">CentOS Linux 7.2 +</span><span class="sxs-lookup"><span data-stu-id="f970e-211">CentOS Linux 7.2+</span></span><p><span data-ttu-id="f970e-212">Ubuntu 16 LTS 或更高版本 LTS</span><span class="sxs-lookup"><span data-stu-id="f970e-212">Ubuntu 16 LTS, or higher LTS</span></span><p><span data-ttu-id="f970e-213">SLES 12 +</span><span class="sxs-lookup"><span data-stu-id="f970e-213">SLES 12+</span></span><p><span data-ttu-id="f970e-214">Debian 9 +</span><span class="sxs-lookup"><span data-stu-id="f970e-214">Debian 9+</span></span><p><span data-ttu-id="f970e-215">Oracle Linux 7。2</span><span class="sxs-lookup"><span data-stu-id="f970e-215">Oracle Linux 7.2</span></span> |[<span data-ttu-id="f970e-216">Linux 上的 Defender Endpoint：網路連接</span><span class="sxs-lookup"><span data-stu-id="f970e-216">Defender for Endpoint on Linux: Network connections</span></span>](microsoft-defender-endpoint-linux.md#network-connections)  |

## <a name="next-step"></a><span data-ttu-id="f970e-217">下一步</span><span class="sxs-lookup"><span data-stu-id="f970e-217">Next step</span></span>

<span data-ttu-id="f970e-218">**恭喜**！</span><span class="sxs-lookup"><span data-stu-id="f970e-218">**Congratulations**!</span></span> <span data-ttu-id="f970e-219">您已完成 [從 Symantec 遷移至 Defender For Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)的 **準備** 階段！</span><span class="sxs-lookup"><span data-stu-id="f970e-219">You have completed the **Prepare** phase of [migrating from Symantec to Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)!</span></span>
- <span data-ttu-id="f970e-220">[繼續設定端點的 Defender](symantec-to-microsoft-defender-atp-setup.md)。</span><span class="sxs-lookup"><span data-stu-id="f970e-220">[Proceed to set up Defender for Endpoint](symantec-to-microsoft-defender-atp-setup.md).</span></span>
