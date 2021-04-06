---
title: Symantec to Microsoft Defender for Endpoint-階段3，上架
description: 這是第3階段，將從 Symantec 遷移至 Microsoft Defender for Endpoint
keywords: 遷移、windows defender 高級威脅防護、atp、edr
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
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: cc005c559e0f91f1c5888f8d7e4e7a2a420894db
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218697"
---
# <a name="migrate-from-symantec---phase-3-onboard-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="f8542-104">從 Symantec 遷移-階段3：板載至 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f8542-104">Migrate from Symantec - Phase 3: Onboard to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="f8542-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f8542-105">**Applies to:**</span></span>
- [<span data-ttu-id="f8542-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f8542-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f8542-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8542-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

|<span data-ttu-id="f8542-108">[![階段1：準備](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="f8542-108">[![Phase 1: Prepare](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)</span></span><br/>[<span data-ttu-id="f8542-109">階段1：準備</span><span class="sxs-lookup"><span data-stu-id="f8542-109">Phase 1: Prepare</span></span>](symantec-to-microsoft-defender-atp-prepare.md) |<span data-ttu-id="f8542-110">[![階段2：設定](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)</span><span class="sxs-lookup"><span data-stu-id="f8542-110">[![Phase 2: Set up](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)</span></span><br/>[<span data-ttu-id="f8542-111">階段2：設定</span><span class="sxs-lookup"><span data-stu-id="f8542-111">Phase 2: Set up</span></span>](symantec-to-microsoft-defender-atp-setup.md) |![階段3：板載](images/phase-diagrams/onboard.png)<br/><span data-ttu-id="f8542-113">階段3：板載</span><span class="sxs-lookup"><span data-stu-id="f8542-113">Phase 3: Onboard</span></span> |
|--|--|--|
|| |<span data-ttu-id="f8542-114">*您在這裡！*</span><span class="sxs-lookup"><span data-stu-id="f8542-114">*You are here!*</span></span> |


<span data-ttu-id="f8542-115">**歡迎您 [從 Symantec 遷移至 Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)的階段 3**。</span><span class="sxs-lookup"><span data-stu-id="f8542-115">**Welcome to Phase 3 of [migrating from Symantec to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**.</span></span> <span data-ttu-id="f8542-116">此遷移階段包含下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f8542-116">This migration phase includes the following steps:</span></span>

1. <span data-ttu-id="f8542-117">[板載裝置至 Microsoft Defender For Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="f8542-117">[Onboard devices to Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).</span></span>
2. <span data-ttu-id="f8542-118">[執行偵測測試](#run-a-detection-test)。</span><span class="sxs-lookup"><span data-stu-id="f8542-118">[Run a detection test](#run-a-detection-test).</span></span>
3. <span data-ttu-id="f8542-119">[卸載 Symantec](#uninstall-symantec)。</span><span class="sxs-lookup"><span data-stu-id="f8542-119">[Uninstall Symantec](#uninstall-symantec).</span></span>
4. <span data-ttu-id="f8542-120">[請確定 Microsoft Defender For Endpoint 處於主動模式](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)。</span><span class="sxs-lookup"><span data-stu-id="f8542-120">[Make sure Microsoft Defender for Endpoint is in active mode](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode).</span></span>

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="f8542-121">在 Microsoft Defender for Endpoint 上的板載裝置</span><span class="sxs-lookup"><span data-stu-id="f8542-121">Onboard devices to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="f8542-122">請移至 Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="f8542-122">Go to the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) and sign in.</span></span>
2. <span data-ttu-id="f8542-123">選擇 [**設定**  >  **裝置管理** 上  >  **架**]。</span><span class="sxs-lookup"><span data-stu-id="f8542-123">Choose **Settings** > **Device management** > **Onboarding**.</span></span> 
3. <span data-ttu-id="f8542-124">在 [ **選取作業系統以啟動上架** 程式] 清單中，選取作業系統。</span><span class="sxs-lookup"><span data-stu-id="f8542-124">In the **Select operating system to start onboarding process** list, select an operating system.</span></span> 
4. <span data-ttu-id="f8542-125">在 [ **部署方法**] 底下，選取選項。</span><span class="sxs-lookup"><span data-stu-id="f8542-125">Under **Deployment method**, select an option.</span></span> <span data-ttu-id="f8542-126">遵循連結，並提示您組織的裝置。</span><span class="sxs-lookup"><span data-stu-id="f8542-126">Follow the links and prompts to onboard your organization's devices.</span></span> <span data-ttu-id="f8542-127">需要協助？</span><span class="sxs-lookup"><span data-stu-id="f8542-127">Need help?</span></span> <span data-ttu-id="f8542-128">請參閱本文中 (的內 [架方法](#onboarding-methods)) 。</span><span class="sxs-lookup"><span data-stu-id="f8542-128">See [Onboarding methods](#onboarding-methods) (in this article).</span></span>

### <a name="onboarding-methods"></a><span data-ttu-id="f8542-129">上架方法</span><span class="sxs-lookup"><span data-stu-id="f8542-129">Onboarding methods</span></span>
 
<span data-ttu-id="f8542-130">根據選取的作業系統而定，部署方法會有所不同。</span><span class="sxs-lookup"><span data-stu-id="f8542-130">Deployment methods vary, depending on which operating system is selected.</span></span> <span data-ttu-id="f8542-131">請參閱下表中所列的資源，以取得上架的協助。</span><span class="sxs-lookup"><span data-stu-id="f8542-131">Refer to the resources listed in the table below to get help with onboarding.</span></span>

|<span data-ttu-id="f8542-132">作業系統</span><span class="sxs-lookup"><span data-stu-id="f8542-132">Operating system</span></span>  |<span data-ttu-id="f8542-133">方法</span><span class="sxs-lookup"><span data-stu-id="f8542-133">Method</span></span>  |
|---------|---------|
|<span data-ttu-id="f8542-134">Windows 10</span><span class="sxs-lookup"><span data-stu-id="f8542-134">Windows 10</span></span>     |<span data-ttu-id="f8542-135">- [群組原則](configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="f8542-135">- [Group Policy](configure-endpoints-gp.md)</span></span><br/><span data-ttu-id="f8542-136">- [Configuration Manager](configure-endpoints-sccm.md)</span><span class="sxs-lookup"><span data-stu-id="f8542-136">- [Configuration Manager](configure-endpoints-sccm.md)</span></span><br/><span data-ttu-id="f8542-137">- [Mobile Device Management (Intune) ](configure-endpoints-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="f8542-137">- [Mobile Device Management (Intune)](configure-endpoints-mdm.md)</span></span><br/><span data-ttu-id="f8542-138">- [本機腳本](configure-endpoints-script.md)</span><span class="sxs-lookup"><span data-stu-id="f8542-138">- [Local script](configure-endpoints-script.md)</span></span> <br/><br/><span data-ttu-id="f8542-139">**附注**：本機腳本適用于概念證明，但不適用於實際執行部署。</span><span class="sxs-lookup"><span data-stu-id="f8542-139">**NOTE**: A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="f8542-140">在實際執行部署中，我們建議使用群組原則、Microsoft 端點設定管理員或 Intune。</span><span class="sxs-lookup"><span data-stu-id="f8542-140">For a production deployment, we recommend using Group Policy, Microsoft Endpoint Configuration Manager, or Intune.</span></span>         |
|<span data-ttu-id="f8542-141">-Windows 8.1 企業版</span><span class="sxs-lookup"><span data-stu-id="f8542-141">- Windows 8.1 Enterprise</span></span> <br/><span data-ttu-id="f8542-142">-Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="f8542-142">- Windows 8.1 Pro</span></span> <br/><span data-ttu-id="f8542-143">-Windows 7 SP1 企業版</span><span class="sxs-lookup"><span data-stu-id="f8542-143">- Windows 7 SP1 Enterprise</span></span> <br/><span data-ttu-id="f8542-144">-Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="f8542-144">- Windows 7 SP1 Pro</span></span>     | [<span data-ttu-id="f8542-145">Microsoft Monitoring Agent</span><span class="sxs-lookup"><span data-stu-id="f8542-145">Microsoft Monitoring Agent</span></span>](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)<br/><br/><span data-ttu-id="f8542-146">**附注**： Microsoft Monitoring Agent 現在是 Azure 記錄分析代理程式。</span><span class="sxs-lookup"><span data-stu-id="f8542-146">**NOTE**: Microsoft Monitoring Agent is now Azure Log Analytics agent.</span></span> <span data-ttu-id="f8542-147">若要深入瞭解，請參閱 [Log Analytics agent 一覽](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)。</span><span class="sxs-lookup"><span data-stu-id="f8542-147">To learn more, see [Log Analytics agent overview](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>        |
|<span data-ttu-id="f8542-148">-Windows Server 2019 和更新版本</span><span class="sxs-lookup"><span data-stu-id="f8542-148">- Windows Server 2019 and later</span></span> <br/><span data-ttu-id="f8542-149">-Windows Server 2019 core edition</span><span class="sxs-lookup"><span data-stu-id="f8542-149">- Windows Server 2019 core edition</span></span> <br/><span data-ttu-id="f8542-150">-Windows Server 版本1803和更新版本</span><span class="sxs-lookup"><span data-stu-id="f8542-150">- Windows Server version 1803 and later</span></span> |<span data-ttu-id="f8542-151">- [本機腳本](configure-endpoints-script.md)</span><span class="sxs-lookup"><span data-stu-id="f8542-151">- [Local script](configure-endpoints-script.md)</span></span> <br/><span data-ttu-id="f8542-152">- [群組原則](configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="f8542-152">- [Group Policy](configure-endpoints-gp.md)</span></span> <br/><span data-ttu-id="f8542-153">- [Configuration Manager](/configure-endpoints-sccm.md)</span><span class="sxs-lookup"><span data-stu-id="f8542-153">- [Configuration Manager](/configure-endpoints-sccm.md)</span></span> <br/><span data-ttu-id="f8542-154">- [System Center Configuration Manager](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="f8542-154">- [System Center Configuration Manager](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)</span></span><br/><span data-ttu-id="f8542-155">- [非持久性裝置的 VDI 上架腳本](configure-endpoints-vdi.md)</span><span class="sxs-lookup"><span data-stu-id="f8542-155">- [VDI onboarding scripts for non-persistent devices](configure-endpoints-vdi.md)</span></span> <br/><br/><span data-ttu-id="f8542-156">**附注**：本機腳本適用于概念證明，但不適用於實際執行部署。</span><span class="sxs-lookup"><span data-stu-id="f8542-156">**NOTE**: A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="f8542-157">在實際執行部署中，我們建議使用群組原則、Microsoft 端點設定管理員或 Intune。</span><span class="sxs-lookup"><span data-stu-id="f8542-157">For a production deployment, we recommend using Group Policy, Microsoft Endpoint Configuration Manager, or Intune.</span></span>    |
|<span data-ttu-id="f8542-158">-Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f8542-158">- Windows Server 2016</span></span> <br/><span data-ttu-id="f8542-159">-Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f8542-159">- Windows Server 2012 R2</span></span> <br/><span data-ttu-id="f8542-160">-Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="f8542-160">- Windows Server 2008 R2 SP1</span></span>  |<span data-ttu-id="f8542-161">- [Microsoft Defender 安全中心](configure-server-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="f8542-161">- [Microsoft Defender Security Center](configure-server-endpoints.md)</span></span><br/><span data-ttu-id="f8542-162">- [Azure 安全性中心](https://docs.microsoft.com/azure/security-center/security-center-wdatp)</span><span class="sxs-lookup"><span data-stu-id="f8542-162">- [Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp)</span></span> |
|<span data-ttu-id="f8542-163">macOS</span><span class="sxs-lookup"><span data-stu-id="f8542-163">macOS</span></span><br/><span data-ttu-id="f8542-164">-10.15 (Catalina) </span><span class="sxs-lookup"><span data-stu-id="f8542-164">- 10.15 (Catalina)</span></span><br/><span data-ttu-id="f8542-165">-10.14 (Mojave) </span><span class="sxs-lookup"><span data-stu-id="f8542-165">- 10.14 (Mojave)</span></span><br/><span data-ttu-id="f8542-166">-10.13 (高塞拉里昂) </span><span class="sxs-lookup"><span data-stu-id="f8542-166">- 10.13 (High Sierra)</span></span><br/><br/><span data-ttu-id="f8542-167">iOS</span><span class="sxs-lookup"><span data-stu-id="f8542-167">iOS</span></span><br/><br/><span data-ttu-id="f8542-168">Linux：</span><span class="sxs-lookup"><span data-stu-id="f8542-168">Linux:</span></span><br/><span data-ttu-id="f8542-169">-RHEL 7.2 +</span><span class="sxs-lookup"><span data-stu-id="f8542-169">- RHEL 7.2+</span></span><br/><span data-ttu-id="f8542-170">-CentOS Linux 7.2 +</span><span class="sxs-lookup"><span data-stu-id="f8542-170">- CentOS Linux 7.2+</span></span><br/><span data-ttu-id="f8542-171">-Ubuntu 16 LTS 或更高版本 LTS</span><span class="sxs-lookup"><span data-stu-id="f8542-171">- Ubuntu 16 LTS, or higher LTS</span></span><br/><span data-ttu-id="f8542-172">-SLES 12 +</span><span class="sxs-lookup"><span data-stu-id="f8542-172">- SLES 12+</span></span><br/><span data-ttu-id="f8542-173">-Debian 9 +</span><span class="sxs-lookup"><span data-stu-id="f8542-173">- Debian 9+</span></span><br/><span data-ttu-id="f8542-174">-Oracle Linux 7。2</span><span class="sxs-lookup"><span data-stu-id="f8542-174">- Oracle Linux 7.2</span></span> |[<span data-ttu-id="f8542-175">板載非 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="f8542-175">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a><span data-ttu-id="f8542-176">執行偵測測試</span><span class="sxs-lookup"><span data-stu-id="f8542-176">Run a detection test</span></span>

<span data-ttu-id="f8542-177">若要驗證架裝置是否正確連接至 Microsoft Defender for Endpoint，您可以執行偵測測試。</span><span class="sxs-lookup"><span data-stu-id="f8542-177">To verify that your onboarded devices are properly connected to Microsoft Defender for Endpoint, you can run a detection test.</span></span>

|<span data-ttu-id="f8542-178">作業系統</span><span class="sxs-lookup"><span data-stu-id="f8542-178">Operating system</span></span>  |<span data-ttu-id="f8542-179">指導方針</span><span class="sxs-lookup"><span data-stu-id="f8542-179">Guidance</span></span>  |
|---------|---------|
|<span data-ttu-id="f8542-180">-Windows 10</span><span class="sxs-lookup"><span data-stu-id="f8542-180">- Windows 10</span></span> <br/><span data-ttu-id="f8542-181">-Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f8542-181">- Windows Server 2019</span></span> <br/><span data-ttu-id="f8542-182">-Windows Server，版本1803</span><span class="sxs-lookup"><span data-stu-id="f8542-182">- Windows Server, version 1803</span></span> <br/><span data-ttu-id="f8542-183">-Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f8542-183">- Windows Server 2016</span></span> <br/><span data-ttu-id="f8542-184">-Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f8542-184">- Windows Server 2012 R2</span></span>     |<span data-ttu-id="f8542-185">請參閱 [執行偵測測試](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="f8542-185">See [Run a detection test](run-detection-test.md).</span></span> <br/><br/><span data-ttu-id="f8542-186">流覽 Microsoft Defender for Endpoint 示範案例網站 ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) 並嘗試一或多個案例。</span><span class="sxs-lookup"><span data-stu-id="f8542-186">Visit the Microsoft Defender for Endpoint demo scenarios site ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) and try one or more of the scenarios.</span></span> <span data-ttu-id="f8542-187">例如，嘗試 **雲端提供的保護** 示範案例。</span><span class="sxs-lookup"><span data-stu-id="f8542-187">For example, try the **Cloud-delivered protection** demo scenario.</span></span>         |
|<span data-ttu-id="f8542-188">macOS</span><span class="sxs-lookup"><span data-stu-id="f8542-188">macOS</span></span><br/><span data-ttu-id="f8542-189">-10.15 (Catalina) </span><span class="sxs-lookup"><span data-stu-id="f8542-189">- 10.15 (Catalina)</span></span><br/><span data-ttu-id="f8542-190">-10.14 (Mojave) </span><span class="sxs-lookup"><span data-stu-id="f8542-190">- 10.14 (Mojave)</span></span><br/><span data-ttu-id="f8542-191">-10.13 (高塞拉里昂) </span><span class="sxs-lookup"><span data-stu-id="f8542-191">- 10.13 (High Sierra)</span></span>     |<span data-ttu-id="f8542-192">下載並使用 DIY 應用程式 [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) 。</span><span class="sxs-lookup"><span data-stu-id="f8542-192">Download and use the DIY app at [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy).</span></span> <br/><br/><span data-ttu-id="f8542-193">如需詳細資訊，請參閱 [Microsoft Defender For Mac 的 Endpoint](microsoft-defender-endpoint-mac.md)。</span><span class="sxs-lookup"><span data-stu-id="f8542-193">For more information, see [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md).</span></span>        |
|<span data-ttu-id="f8542-194">Linux：</span><span class="sxs-lookup"><span data-stu-id="f8542-194">Linux:</span></span><br/><span data-ttu-id="f8542-195">-RHEL 7.2 +</span><span class="sxs-lookup"><span data-stu-id="f8542-195">- RHEL 7.2+</span></span><br/><span data-ttu-id="f8542-196">-CentOS Linux 7.2 +</span><span class="sxs-lookup"><span data-stu-id="f8542-196">- CentOS Linux 7.2+</span></span><br/><span data-ttu-id="f8542-197">-Ubuntu 16 LTS 或更高版本 LTS</span><span class="sxs-lookup"><span data-stu-id="f8542-197">- Ubuntu 16 LTS, or higher LTS</span></span><br/><span data-ttu-id="f8542-198">-SLES 12 +</span><span class="sxs-lookup"><span data-stu-id="f8542-198">- SLES 12+</span></span><br/><span data-ttu-id="f8542-199">-Debian 9 +</span><span class="sxs-lookup"><span data-stu-id="f8542-199">- Debian 9+</span></span><br/><span data-ttu-id="f8542-200">-Oracle Linux 7。2</span><span class="sxs-lookup"><span data-stu-id="f8542-200">- Oracle Linux 7.2</span></span> |<span data-ttu-id="f8542-201">1. 執行下列命令，並尋找 **1** 的結果：</span><span class="sxs-lookup"><span data-stu-id="f8542-201">1. Run the following command, and look for a result of **1**:</span></span> <br/><span data-ttu-id="f8542-202">`mdatp health --field real_time_protection_enabled`.</span><span class="sxs-lookup"><span data-stu-id="f8542-202">`mdatp health --field real_time_protection_enabled`.</span></span> <br/><br/><span data-ttu-id="f8542-203">2. 開啟終端視窗，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f8542-203">2. Open a Terminal window, and run the following command:</span></span> <br/><span data-ttu-id="f8542-204">`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`.</span><span class="sxs-lookup"><span data-stu-id="f8542-204">`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`.</span></span> <br/><br/><span data-ttu-id="f8542-205">3. 執行下列命令，列出任何偵測到的威脅：</span><span class="sxs-lookup"><span data-stu-id="f8542-205">3. Run the following command to list any detected threats:</span></span> <br/><span data-ttu-id="f8542-206">`mdatp threat list`.</span><span class="sxs-lookup"><span data-stu-id="f8542-206">`mdatp threat list`.</span></span> <br/><br/><span data-ttu-id="f8542-207">如需詳細資訊，請參閱 [Microsoft Defender For Linux 的 Endpoint](microsoft-defender-endpoint-linux.md)。</span><span class="sxs-lookup"><span data-stu-id="f8542-207">For more information, see [Microsoft Defender for Endpoint for Linux](microsoft-defender-endpoint-linux.md).</span></span> |

## <a name="uninstall-symantec"></a><span data-ttu-id="f8542-208">卸載 Symantec</span><span class="sxs-lookup"><span data-stu-id="f8542-208">Uninstall Symantec</span></span>

<span data-ttu-id="f8542-209">現在，您已將組織的裝置架至 Microsoft Defender for Endpoint，下一步是卸載 Symantec。</span><span class="sxs-lookup"><span data-stu-id="f8542-209">Now that you have onboarded your organization's devices to Microsoft Defender for Endpoint, your next step is to uninstall Symantec.</span></span>

1. <span data-ttu-id="f8542-210">停用 Symantec 中的[篡改保護](https://knowledge.broadcom.com/external/article?legacyId=tech192023)。</span><span class="sxs-lookup"><span data-stu-id="f8542-210">[Disable Tamper Protection](https://knowledge.broadcom.com/external/article?legacyId=tech192023) in Symantec.</span></span>
2. <span data-ttu-id="f8542-211">刪除 Symantec 的卸載密碼：</span><span class="sxs-lookup"><span data-stu-id="f8542-211">Delete the uninstall password for Symantec:</span></span><br/>
   1. <span data-ttu-id="f8542-212">在您的 Windows 裝置上，以系統管理員身分開啟登錄編輯程式。</span><span class="sxs-lookup"><span data-stu-id="f8542-212">On your Windows devices, open Registry Editor as an administrator.</span></span>
   2. <span data-ttu-id="f8542-213">移至`HKEY_LOCAL_MACHINE\SOFTWARE\Symantec\Symantec Endpoint Protection\SMC`。</span><span class="sxs-lookup"><span data-stu-id="f8542-213">Go to `HKEY_LOCAL_MACHINE\SOFTWARE\Symantec\Symantec Endpoint Protection\SMC`.</span></span>
   3. <span data-ttu-id="f8542-214">尋找名為 **SmcInstData** 的專案。</span><span class="sxs-lookup"><span data-stu-id="f8542-214">Look for an entry named **SmcInstData**.</span></span> 
   4. <span data-ttu-id="f8542-215">以滑鼠右鍵按一下專案，然後選擇 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="f8542-215">Right-click the item, and then choose **Delete**.</span></span> 
3. <span data-ttu-id="f8542-216">從您的裝置移除 Symantec。</span><span class="sxs-lookup"><span data-stu-id="f8542-216">Remove Symantec from your devices.</span></span> <span data-ttu-id="f8542-217">如需相關資訊，請參閱 Broadcom 的檔。</span><span class="sxs-lookup"><span data-stu-id="f8542-217">If you need help with this, see Broadcom's documentation.</span></span> <span data-ttu-id="f8542-218">以下是一些 Broadcom 資源：</span><span class="sxs-lookup"><span data-stu-id="f8542-218">Here are a few Broadcom resources:</span></span> 
   - [<span data-ttu-id="f8542-219">卸載 Symantec Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="f8542-219">Uninstall Symantec Endpoint Protection</span></span>](https://knowledge.broadcom.com/external/article/156148/uninstall-symantec-endpoint-protection.html)
   - <span data-ttu-id="f8542-220">Windows 裝置： [手動卸載 windows 上的 Endpoint Protection 14 用戶端](https://knowledge.broadcom.com/external/article?articleId=170040)</span><span class="sxs-lookup"><span data-stu-id="f8542-220">Windows devices: [Manually uninstall Endpoint Protection 14 clients on Windows](https://knowledge.broadcom.com/external/article?articleId=170040)</span></span>
   - <span data-ttu-id="f8542-221">macOS 電腦： [使用 RemoveSymantecMacFiles 移除 Mac 版 Symantec 軟體](https://knowledge.broadcom.com/external/article?articleId=151387)</span><span class="sxs-lookup"><span data-stu-id="f8542-221">macOS computers: [Remove Symantec software for Mac using RemoveSymantecMacFiles](https://knowledge.broadcom.com/external/article?articleId=151387)</span></span>
   - <span data-ttu-id="f8542-222">Linux 裝置： [適用于 linux 的 Endpoint Protection 常見問題](https://knowledge.broadcom.com/external/article?articleId=162054)</span><span class="sxs-lookup"><span data-stu-id="f8542-222">Linux devices: [Frequently Asked Questions for Endpoint Protection for Linux](https://knowledge.broadcom.com/external/article?articleId=162054)</span></span>

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a><span data-ttu-id="f8542-223">確定 Microsoft Defender for Endpoint 處於主動模式</span><span class="sxs-lookup"><span data-stu-id="f8542-223">Make sure Microsoft Defender for Endpoint is in active mode</span></span>

<span data-ttu-id="f8542-224">現在，您已卸載 Symantec 後，下一步是確定已啟用 Microsoft Defender 防病毒和 Microsoft Defender for Endpoint，並以主動模式進行。</span><span class="sxs-lookup"><span data-stu-id="f8542-224">Now that you have uninstalled Symantec, your next step is to make sure that Microsoft Defender Antivirus and Microsoft Defender for Endpoint are enabled and in active mode.</span></span>

<span data-ttu-id="f8542-225">若要這麼做，請造訪 Microsoft Defender for Endpoint 示範案例網站 ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) 。</span><span class="sxs-lookup"><span data-stu-id="f8542-225">To do this, visit the Microsoft Defender for Endpoint demo scenarios site ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)).</span></span> <span data-ttu-id="f8542-226">請在該頁面上嘗試一或多個示範案例，至少包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="f8542-226">Try one or more of the demo scenarios on that page, including at least the following:</span></span>
- <span data-ttu-id="f8542-227">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="f8542-227">Cloud-delivered protection</span></span>
- <span data-ttu-id="f8542-228">PUA (可能有害的應用程式) </span><span class="sxs-lookup"><span data-stu-id="f8542-228">Potentially Unwanted Applications (PUA)</span></span>
- <span data-ttu-id="f8542-229">網路保護 (NP) </span><span class="sxs-lookup"><span data-stu-id="f8542-229">Network Protection (NP)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8542-230">如果您使用的是 Windows Server 2016，您可能需要手動啟動 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="f8542-230">If you are using Windows Server 2016, you might have to start Microsoft Defender Antivirus manually.</span></span> <span data-ttu-id="f8542-231">您可以使用裝置上的 PowerShell Cmdlet 來執行此動作 `mpcmdrun.exe -wdenable` 。</span><span class="sxs-lookup"><span data-stu-id="f8542-231">You can do this by using the PowerShell cmdlet `mpcmdrun.exe -wdenable` on the device.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f8542-232">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f8542-232">Next steps</span></span>

<span data-ttu-id="f8542-233">**恭喜**！</span><span class="sxs-lookup"><span data-stu-id="f8542-233">**Congratulations**!</span></span> <span data-ttu-id="f8542-234">您已完成 [從 Symantec 遷移至 Microsoft Defender For Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)！</span><span class="sxs-lookup"><span data-stu-id="f8542-234">You have completed your [migration from Symantec to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)!</span></span> 
- <span data-ttu-id="f8542-235">請造訪 Microsoft Defender Security Center () 中的[安全性作業儀表板](security-operations-dashboard.md) [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。</span><span class="sxs-lookup"><span data-stu-id="f8542-235">[Visit your security operations dashboard](security-operations-dashboard.md) in the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)).</span></span> 
- <span data-ttu-id="f8542-236">[管理 Microsoft Defender For Endpoint，後期遷移](manage-atp-post-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="f8542-236">[Manage Microsoft Defender for Endpoint, post migration](manage-atp-post-migration.md).</span></span>