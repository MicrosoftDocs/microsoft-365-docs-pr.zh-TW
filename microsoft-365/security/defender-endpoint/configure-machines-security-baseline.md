---
title: 將合規性提升至 Microsoft Defender for Endpoint security 基準
description: Microsoft Defender for Endpoint security 基準會設定安全性控制，以提供最佳防護。
keywords: Intune 管理，Microsoft Defender for Endpoint，Microsoft Defender，microsoft defender for Endpoint ASR，安全性基準
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a5f3d2de452a8a1ab201f558b93d45dfa6ded3e6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841543"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="e7dba-104">將合規性提升至 Microsoft Defender for Endpoint security 基準</span><span class="sxs-lookup"><span data-stu-id="e7dba-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e7dba-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e7dba-105">**Applies to:**</span></span>
- [<span data-ttu-id="e7dba-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e7dba-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e7dba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7dba-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e7dba-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e7dba-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e7dba-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e7dba-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="e7dba-110">安全性基準可確保根據安全性專家和專家 Windows 系統管理員的指導，設定安全性功能。</span><span class="sxs-lookup"><span data-stu-id="e7dba-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="e7dba-111">當部署時，用於端點安全性基準的 Defender 會將 Defender 設定為端點安全性控制，以提供最佳防護。</span><span class="sxs-lookup"><span data-stu-id="e7dba-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="e7dba-112">若要瞭解安全性基準，以及如何使用設定檔在 Intune 上指派它們，請 [閱讀此 FAQ](/intune/security-baselines#q--a)。</span><span class="sxs-lookup"><span data-stu-id="e7dba-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="e7dba-113">在您部署及追蹤安全性基準的符合性之前，您可以：</span><span class="sxs-lookup"><span data-stu-id="e7dba-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="e7dba-114">將裝置註冊到 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="e7dba-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="e7dba-115">確定您具備必要的許可權</span><span class="sxs-lookup"><span data-stu-id="e7dba-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a><span data-ttu-id="e7dba-116">比較 Microsoft Defender for Endpoint 和 Windows Intune 安全性基準</span><span class="sxs-lookup"><span data-stu-id="e7dba-116">Compare the Microsoft Defender for Endpoint and the Windows Intune security baselines</span></span>
<span data-ttu-id="e7dba-117">Windows Intune 安全性基準會提供一組完整的建議設定，以安全地設定執行 Windows 的裝置，包括瀏覽器設定、PowerShell 設定，以及某些安全性功能（如 Microsoft Defender 防毒軟體）的設定。</span><span class="sxs-lookup"><span data-stu-id="e7dba-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="e7dba-118">相反地，「終結點」基準會提供設定，以優化所有的 endpoint 堆疊中的安全性控制，包括 Windows Intune 安全性基準中 EDR) 的端點偵測和回應 (的設定，以及也位於 Intune 安全性基準中的設定。</span><span class="sxs-lookup"><span data-stu-id="e7dba-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="e7dba-119">如需每個基準的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="e7dba-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="e7dba-120">Windows Intune 的安全性基準設定</span><span class="sxs-lookup"><span data-stu-id="e7dba-120">Windows security baseline settings for Intune</span></span>](/intune/security-baseline-settings-windows)
- [<span data-ttu-id="e7dba-121">Intune 的 Microsoft Defender 端點基準設定</span><span class="sxs-lookup"><span data-stu-id="e7dba-121">Microsoft Defender for Endpoint baseline settings for Intune</span></span>](/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="e7dba-122">理想狀況下，架 to Defender for endpoint 的裝置會同時部署這兩種基準：「Windows Intune 安全性基準」最初是安全的 Windows，而在最上層的 defender for endpoint security 基準會以最優化方式設定 defender for endpoint security 控制項。</span><span class="sxs-lookup"><span data-stu-id="e7dba-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="e7dba-123">若要受益于風險和威脅的最新資料，並在比較基準演變時盡可能減少衝突，請在發行所有產品時，隨時套用最新的基準版本。</span><span class="sxs-lookup"><span data-stu-id="e7dba-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="e7dba-124">已針對實體裝置優化端點安全性基準，目前不建議用於虛擬機器 (Vm) 或 VDI 端點。</span><span class="sxs-lookup"><span data-stu-id="e7dba-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="e7dba-125">某些基準設定會影響虛擬環境中的遠端互動會話。</span><span class="sxs-lookup"><span data-stu-id="e7dba-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="e7dba-126">監視對 Defender for Endpoint security 基準的合規性</span><span class="sxs-lookup"><span data-stu-id="e7dba-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="e7dba-127">[裝置設定管理](configure-machines.md)上的 **安全性基準** 卡會在已指派 Defender for Endpoint Security 基準的 Windows 10 裝置中，提供相容性的概覽。</span><span class="sxs-lookup"><span data-stu-id="e7dba-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="e7dba-128">![安全性基準卡](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="e7dba-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="e7dba-129">*顯示對 Defender for Endpoint security 基準的合規性的卡片*</span><span class="sxs-lookup"><span data-stu-id="e7dba-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="e7dba-130">每個裝置都具有下列其中一個狀態類型：</span><span class="sxs-lookup"><span data-stu-id="e7dba-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="e7dba-131">**符合基準** 線-裝置設定符合基線中的所有設定</span><span class="sxs-lookup"><span data-stu-id="e7dba-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="e7dba-132">不 **符合比較基準**，至少有一個裝置設定不符合基線</span><span class="sxs-lookup"><span data-stu-id="e7dba-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="e7dba-133">**誤** 設定-裝置上至少有一個基準設定沒有正確設定，且處於衝突、錯誤或擱置狀態。</span><span class="sxs-lookup"><span data-stu-id="e7dba-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="e7dba-134">**不適用**—至少一個基準設定不適用於裝置</span><span class="sxs-lookup"><span data-stu-id="e7dba-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="e7dba-135">若要查看特定裝置，請選取卡片上的 [ **設定安全性基準** ]。</span><span class="sxs-lookup"><span data-stu-id="e7dba-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="e7dba-136">這會帶您前往 Intune 裝置管理。</span><span class="sxs-lookup"><span data-stu-id="e7dba-136">This takes you to Intune device management.</span></span> <span data-ttu-id="e7dba-137">從那裡，選取裝置的名稱和狀態的裝置 **狀態** 。</span><span class="sxs-lookup"><span data-stu-id="e7dba-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="e7dba-138">在 [裝置設定管理] 頁面上顯示的匯總資料和在 Intune 中顯示的概要畫面中，您可能會遇到差異。</span><span class="sxs-lookup"><span data-stu-id="e7dba-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="e7dba-139">檢查並指派 Microsoft Defender for Endpoint security 基準</span><span class="sxs-lookup"><span data-stu-id="e7dba-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="e7dba-140">裝置設定管理會監控僅限明確指派 Microsoft Defender for Endpoint security 基準的 Windows 10 裝置的基準相容性。</span><span class="sxs-lookup"><span data-stu-id="e7dba-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="e7dba-141">您可以在 Intune 裝置管理上輕鬆查看基準，並將其指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="e7dba-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="e7dba-142">選取 [**安全性基準** 卡] 上的 [**設定安全性基準**]，以移至 [Intune 裝置管理]。</span><span class="sxs-lookup"><span data-stu-id="e7dba-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="e7dba-143">會顯示類似的基準相容性綜述。</span><span class="sxs-lookup"><span data-stu-id="e7dba-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="e7dba-144">或者，您可以從所有服務 > Intune 流覽至 Microsoft Azure 入口網站的 Defender for Endpoint security 基準 **> 裝置安全性 > 安全性基準 > Microsoft Defender ATP 基準**。</span><span class="sxs-lookup"><span data-stu-id="e7dba-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="e7dba-145">建立新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="e7dba-145">Create a new profile.</span></span>

   <span data-ttu-id="e7dba-146">![Intune 上的 Microsoft Defender for Endpoint security 基準概述](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="e7dba-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="e7dba-147">*Intune 上的 Microsoft Defender for Endpoint security 基準概述*</span><span class="sxs-lookup"><span data-stu-id="e7dba-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="e7dba-148">在建立設定檔期間，您可以複查和調整基準上的特定設定。</span><span class="sxs-lookup"><span data-stu-id="e7dba-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="e7dba-149">![在 Intune 上建立設定檔期間的安全性基準選項](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="e7dba-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="e7dba-150">*在 Intune 上建立設定檔期間的安全性基準選項*</span><span class="sxs-lookup"><span data-stu-id="e7dba-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="e7dba-151">將設定檔指派給適當的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="e7dba-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="e7dba-152">![Intune 上的安全性基準設定檔](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="e7dba-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="e7dba-153">*在 Intune 上指派安全性基準設定檔*</span><span class="sxs-lookup"><span data-stu-id="e7dba-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="e7dba-154">建立設定檔，並將其部署至指派的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="e7dba-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="e7dba-155">![在 Intune 上指派安全性基準](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="e7dba-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="e7dba-156">*在 Intune 上建立安全性基準設定檔*</span><span class="sxs-lookup"><span data-stu-id="e7dba-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="e7dba-157">Intune 上的安全性基準可讓您輕鬆地保護裝置，並保護您的裝置。</span><span class="sxs-lookup"><span data-stu-id="e7dba-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="e7dba-158">[深入瞭解 Intune 上的安全性基準](/intune/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="e7dba-158">[Learn more about security baselines on Intune](/intune/security-baselines).</span></span>

><span data-ttu-id="e7dba-159">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="e7dba-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e7dba-160">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e7dba-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="e7dba-161">相關主題</span><span class="sxs-lookup"><span data-stu-id="e7dba-161">Related topics</span></span>
- [<span data-ttu-id="e7dba-162">確保您的裝置已正確設定</span><span class="sxs-lookup"><span data-stu-id="e7dba-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="e7dba-163">取得架至 Microsoft Defender for Endpoint 的裝置</span><span class="sxs-lookup"><span data-stu-id="e7dba-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="e7dba-164">優化 ASR 規則的部署和偵測</span><span class="sxs-lookup"><span data-stu-id="e7dba-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
