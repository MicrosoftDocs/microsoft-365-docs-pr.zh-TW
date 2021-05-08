---
title: 封鎖模式中的端點偵測和回應
description: 深入瞭解封鎖模式中的端點偵測和回應
keywords: Microsoft Defender for Endpoint，mde，EDR 以封鎖模式，被動模式封鎖
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 05/05/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: d7ab8afd1d643933dc71a5bef1385b9ab95b553f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245801"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a><span data-ttu-id="fb388-104">在封鎖模式中) 的端點偵測和回應 (EDR</span><span class="sxs-lookup"><span data-stu-id="fb388-104">Endpoint detection and response (EDR) in block mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fb388-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="fb388-105">**Applies to:**</span></span>
- [<span data-ttu-id="fb388-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fb388-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fb388-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fb388-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="fb388-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="fb388-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fb388-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="fb388-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a><span data-ttu-id="fb388-110">封鎖模式中的 EDR 為何？</span><span class="sxs-lookup"><span data-stu-id="fb388-110">What is EDR in block mode?</span></span>

<span data-ttu-id="fb388-111">[端點偵測和回應](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) 在封鎖模式中時，即使 Microsoft Defender 防毒軟體是以被動模式執行，也可以保護惡意的惡意資料。</span><span class="sxs-lookup"><span data-stu-id="fb388-111">[Endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="fb388-112">開啟時，以封鎖模式 EDR 會封鎖在裝置上偵測到的惡意的偽像或行為。</span><span class="sxs-lookup"><span data-stu-id="fb388-112">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="fb388-113">block 模式中的 EDR 會在幕後運作，以修正偵測到破壞後偵測到的惡意作品。</span><span class="sxs-lookup"><span data-stu-id="fb388-113">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span> 

<span data-ttu-id="fb388-114">組塊模式中的 EDR 也會與[威脅 & 弱點管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)整合。</span><span class="sxs-lookup"><span data-stu-id="fb388-114">EDR in block mode is also integrated with [threat & vulnerability management](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="fb388-115">組織的安全性小組會取得[安全性建議](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)，以在封鎖模式中開啟 EDR （如果尚未啟用）。</span><span class="sxs-lookup"><span data-stu-id="fb388-115">Your organization's security team will get a [security recommendation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) to turn EDR in block mode on if it isn't already enabled.</span></span> 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="在封鎖模式中開啟 EDR 的建議":::

> [!NOTE]
> <span data-ttu-id="fb388-117">若要取得最佳保護，請務必 **[部署 Microsoft Defender For Endpoint 基準](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**。</span><span class="sxs-lookup"><span data-stu-id="fb388-117">To get the best protection, make sure to **[deploy Microsoft Defender for Endpoint baselines](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**.</span></span>

## <a name="what-happens-when-something-is-detected"></a><span data-ttu-id="fb388-118">偵測到某項時會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="fb388-118">What happens when something is detected?</span></span>

<span data-ttu-id="fb388-119">當以封鎖模式開啟 EDR，且偵測到惡意的專案時，Microsoft Defender 會封鎖和 remediates 該專案。</span><span class="sxs-lookup"><span data-stu-id="fb388-119">When EDR in block mode is turned on, and a malicious artifact is detected, Microsoft Defender for Endpoint blocks and remediates that artifact.</span></span> <span data-ttu-id="fb388-120">您會在重要訊息 [中心](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center)看到偵測 **狀態為「** 已 **封鎖**」或「已完成」動作。</span><span class="sxs-lookup"><span data-stu-id="fb388-120">You'll see detection status as **Blocked** or **Prevented** as completed actions in the [Action center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center).</span></span>

<span data-ttu-id="fb388-121">下圖顯示以封鎖模式 EDR 所偵測到並封鎖的未預期軟體實例：</span><span class="sxs-lookup"><span data-stu-id="fb388-121">The following image shows an instance of unwanted software that was detected and blocked through EDR in block mode:</span></span>

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="在封鎖模式中 EDR 偵測到某項":::


## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="fb388-123">在封鎖模式中啟用 EDR</span><span class="sxs-lookup"><span data-stu-id="fb388-123">Enable EDR in block mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb388-124">在封鎖模式中開啟 EDR 之前，請確定符合[需求](#requirements-for-edr-in-block-mode)。</span><span class="sxs-lookup"><span data-stu-id="fb388-124">Make sure the [requirements](#requirements-for-edr-in-block-mode) are met before turning on EDR in block mode.</span></span>

1. <span data-ttu-id="fb388-125">移至 Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="fb388-125">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span> 

2. <span data-ttu-id="fb388-126">選擇 [**設定**  >  **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="fb388-126">Choose **Settings** > **Advanced features**.</span></span>

3. <span data-ttu-id="fb388-127">**在塊狀模式中開啟 EDR**。</span><span class="sxs-lookup"><span data-stu-id="fb388-127">Turn on **EDR in block mode**.</span></span>

> [!NOTE]
> <span data-ttu-id="fb388-128">在組塊模式中 EDR 只能在 Microsoft Defender 資訊安全中心中開啟。</span><span class="sxs-lookup"><span data-stu-id="fb388-128">EDR in block mode can be turned on only in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="fb388-129">您無法使用登錄機碼、Intune 或群組原則，在封鎖模式中啟用或停用 EDR。</span><span class="sxs-lookup"><span data-stu-id="fb388-129">You cannot use registry keys, Intune, or group policies to enable or disable EDR in block mode.</span></span>

## <a name="requirements-for-edr-in-block-mode"></a><span data-ttu-id="fb388-130">封鎖模式中 EDR 的需求</span><span class="sxs-lookup"><span data-stu-id="fb388-130">Requirements for EDR in block mode</span></span>

|<span data-ttu-id="fb388-131">需求</span><span class="sxs-lookup"><span data-stu-id="fb388-131">Requirement</span></span>  |<span data-ttu-id="fb388-132">詳細資料</span><span class="sxs-lookup"><span data-stu-id="fb388-132">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="fb388-133">權限</span><span class="sxs-lookup"><span data-stu-id="fb388-133">Permissions</span></span> |<span data-ttu-id="fb388-134">在[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)中指派全域管理員或安全性管理員角色。</span><span class="sxs-lookup"><span data-stu-id="fb388-134">Global Administrator or Security Administrator role assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span> <span data-ttu-id="fb388-135">請參閱 [基本許可權](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions)。</span><span class="sxs-lookup"><span data-stu-id="fb388-135">See [Basic permissions](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions).</span></span> |
|<span data-ttu-id="fb388-136">作業系統</span><span class="sxs-lookup"><span data-stu-id="fb388-136">Operating system</span></span>     |<span data-ttu-id="fb388-137">下列其中一個版本：</span><span class="sxs-lookup"><span data-stu-id="fb388-137">One of the following versions:</span></span> <br/><span data-ttu-id="fb388-138">-Windows 10 (所有版本) </span><span class="sxs-lookup"><span data-stu-id="fb388-138">- Windows 10 (all releases)</span></span> <br/><span data-ttu-id="fb388-139">-Windows Server，版本1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="fb388-139">- Windows Server, version 1803 or newer</span></span> <br/><span data-ttu-id="fb388-140">-Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="fb388-140">- Windows Server 2019</span></span>  <p><span data-ttu-id="fb388-141">**附注**： Windows Server 2016 上不支援封鎖模式中的 EDR。</span><span class="sxs-lookup"><span data-stu-id="fb388-141">**NOTE**: EDR in block mode is not supported on Windows Server 2016.</span></span>       |
|<span data-ttu-id="fb388-142">WindowsE5 登記</span><span class="sxs-lookup"><span data-stu-id="fb388-142">Windows E5 enrollment</span></span>     |<span data-ttu-id="fb388-143">WindowsE5 包含在下列訂閱中：</span><span class="sxs-lookup"><span data-stu-id="fb388-143">Windows E5 is included in the following subscriptions:</span></span> <br/><span data-ttu-id="fb388-144">-Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="fb388-144">- Microsoft 365 E5</span></span> <br/><span data-ttu-id="fb388-145">-Microsoft 365 E3 搭配身分識別 & 威脅防護服務</span><span class="sxs-lookup"><span data-stu-id="fb388-145">- Microsoft 365 E3 together with the Identity & Threat Protection offering</span></span> <br/><br/><span data-ttu-id="fb388-146">請參閱[每個計畫的](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)[元件](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components)和功能。</span><span class="sxs-lookup"><span data-stu-id="fb388-146">See [Components](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) and [features and capabilities for each plan](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>       |
|<span data-ttu-id="fb388-147">Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="fb388-147">Microsoft Defender Antivirus</span></span>  |<span data-ttu-id="fb388-148">必須以主動模式或被動模式安裝和執行 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="fb388-148">Microsoft Defender Antivirus must be installed and running in either active mode or passive mode.</span></span> <span data-ttu-id="fb388-149"> (您可以在非 Microsoft 防病毒方案旁使用 Microsoft Defender 防毒軟體。 ) [確認 Microsoft Defender 防毒軟體為主動或被動模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="fb388-149">(You can use Microsoft Defender Antivirus alongside a non-Microsoft antivirus solution.) [Confirm Microsoft Defender Antivirus is in active or passive mode](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).</span></span> |
|<span data-ttu-id="fb388-150">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="fb388-150">Cloud-delivered protection</span></span> |<span data-ttu-id="fb388-151">請確定已設定 Microsoft Defender 防毒軟體，讓[已啟用雲端傳遞的保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="fb388-151">Make sure Microsoft Defender Antivirus is configured such that [cloud-delivered protection is enabled](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus).</span></span> |
|<span data-ttu-id="fb388-152">Microsoft Defender 防毒軟體反惡意程式碼用戶端</span><span class="sxs-lookup"><span data-stu-id="fb388-152">Microsoft Defender Antivirus antimalware client</span></span> |<span data-ttu-id="fb388-153">請確定您的用戶端是最新版本。</span><span class="sxs-lookup"><span data-stu-id="fb388-153">Make sure your client is up to date.</span></span> <span data-ttu-id="fb388-154">使用 PowerShell，以系統管理員身分執行 [MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fb388-154">Using PowerShell, run the [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet as an administrator.</span></span> <span data-ttu-id="fb388-155">在 **AMProductVersion** 行中，您應該會看到 **4.18.2001.10** 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="fb388-155">In the **AMProductVersion** line, you should see **4.18.2001.10** or above.</span></span> |
|<span data-ttu-id="fb388-156">Microsoft Defender 防毒軟體引擎</span><span class="sxs-lookup"><span data-stu-id="fb388-156">Microsoft Defender Antivirus engine</span></span> |<span data-ttu-id="fb388-157">請確定您的引擎是最新版本。</span><span class="sxs-lookup"><span data-stu-id="fb388-157">Make sure your engine is up to date.</span></span> <span data-ttu-id="fb388-158">使用 PowerShell，以系統管理員身分執行 [MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fb388-158">Using PowerShell, run the [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) cmdlet as an administrator.</span></span> <span data-ttu-id="fb388-159">在 **AMEngineVersion** 行中，您應該會看到 **1.1.16700.2** 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="fb388-159">In the **AMEngineVersion** line, you should see **1.1.16700.2** or above.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="fb388-160">若要取得最佳保護值，請確定您的防病毒方案已設定為接收定期更新和基本功能，以及您的 [排除已設定](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="fb388-160">To get the best protection value, make sure your antivirus solution is configured to receive regular updates and essential features, and that your [exclusions are configured](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="fb388-161">在封鎖模式中 EDR 會考慮針對 Microsoft Defender 防毒軟體所定義的排除專案。</span><span class="sxs-lookup"><span data-stu-id="fb388-161">EDR in block mode respects exclusions that are defined for Microsoft Defender Antivirus.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="fb388-162">常見問題集</span><span class="sxs-lookup"><span data-stu-id="fb388-162">Frequently asked questions</span></span> 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a><span data-ttu-id="fb388-163">即使在裝置上執行 Microsoft Defender 防毒軟體，我是否需要在封鎖模式中開啟 EDR？</span><span class="sxs-lookup"><span data-stu-id="fb388-163">Do I need to turn EDR in block mode on even when I have Microsoft Defender Antivirus running on devices?</span></span>

<span data-ttu-id="fb388-164">建議您將 EDR 置於封鎖模式，不論 Microsoft Defender 防毒軟體是以被動模式還是以主動模式執行。</span><span class="sxs-lookup"><span data-stu-id="fb388-164">We recommend keeping EDR in block mode on, whether Microsoft Defender Antivirus is running in passive mode or in active mode.</span></span> <span data-ttu-id="fb388-165">在封鎖模式中 EDR 會提供另一個與 Microsoft Defender for Endpoint 的防禦層。</span><span class="sxs-lookup"><span data-stu-id="fb388-165">EDR in block mode provides another layer of defense with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="fb388-166">它可讓 Defender for Endpoint 根據破壞後的行為 EDR 偵測採取動作。</span><span class="sxs-lookup"><span data-stu-id="fb388-166">It allows Defender for Endpoint to take actions based on post-breach behavioral EDR detections.</span></span> 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a><span data-ttu-id="fb388-167">會在封鎖模式中 EDR 是否會影響使用者的病毒防護？</span><span class="sxs-lookup"><span data-stu-id="fb388-167">Will EDR in block mode have any impact on a user's antivirus protection?</span></span> 

<span data-ttu-id="fb388-168">在封鎖模式中 EDR 不會影響使用者裝置上執行的協力廠商防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="fb388-168">EDR in block mode does not affect third-party antivirus protection running on users' devices.</span></span> <span data-ttu-id="fb388-169">如果主要防病毒解決方案未接任何問題，或發生破壞後的情況，則 EDR 以封鎖模式運作。</span><span class="sxs-lookup"><span data-stu-id="fb388-169">EDR in block mode works if the primary antivirus solution misses something, or if there is a post-breach detection.</span></span> <span data-ttu-id="fb388-170">在封鎖模式中 EDR 的運作方式與[被動模式 Microsoft Defender 防毒軟體](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)相同，但也會封鎖和 remediates 偵測到的惡意專案或行為。</span><span class="sxs-lookup"><span data-stu-id="fb388-170">EDR in block mode works just like [Microsoft Defender Antivirus in passive mode](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state), except it also blocks and remediates malicious artifacts or behaviors that are detected.</span></span> 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a><span data-ttu-id="fb388-171">為什麼我需要讓 Microsoft Defender 防毒軟體保持最新狀態？</span><span class="sxs-lookup"><span data-stu-id="fb388-171">Why do I need to keep Microsoft Defender Antivirus up to date?</span></span> 

<span data-ttu-id="fb388-172">由於 Microsoft Defender 防毒軟體偵測和 remediates 惡意專案，因此務必將其保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="fb388-172">Because Microsoft Defender Antivirus detects and remediates malicious items, it's important to keep it up to date.</span></span> <span data-ttu-id="fb388-173">為使封鎖模式中的 EDR 生效，它會使用最新的裝置學習模型、行為偵測和試探法。</span><span class="sxs-lookup"><span data-stu-id="fb388-173">For EDR in block mode to be effective, it uses the latest device learning models, behavioral detections, and heuristics.</span></span> <span data-ttu-id="fb388-174">功能 [終結點](https://docs.microsoft.com/windows/security/threat-protection) 堆疊功能的運作方式是以整合方式運作。</span><span class="sxs-lookup"><span data-stu-id="fb388-174">The [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) stack of capabilities works in an integrated manner.</span></span> <span data-ttu-id="fb388-175">若要取得最佳防護值，您應該將 Microsoft Defender 防毒軟體保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="fb388-175">To get best protection value, you should keep Microsoft Defender Antivirus up to date.</span></span>  

### <a name="why-do-we-need-cloud-protection-on"></a><span data-ttu-id="fb388-176">我們為何需要雲端保護開啟？</span><span class="sxs-lookup"><span data-stu-id="fb388-176">Why do we need cloud protection on?</span></span> 

<span data-ttu-id="fb388-177">需要 Cloud protection 才能開啟裝置上的功能。</span><span class="sxs-lookup"><span data-stu-id="fb388-177">Cloud protection is needed to turn on the feature on the device.</span></span> <span data-ttu-id="fb388-178">雲端防護功能可讓 [Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection) ，根據我們的廣泛和深度安全性情報，以及行為和裝置教學模型，提供最新和最佳的保護。</span><span class="sxs-lookup"><span data-stu-id="fb388-178">Cloud protection allows [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) to deliver the latest and greatest protection based on our breadth and depth of security intelligence, along with behavioral and device learning models.</span></span>

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="fb388-179">如何將 Microsoft Defender 防毒軟體設定為被動模式？</span><span class="sxs-lookup"><span data-stu-id="fb388-179">How do I set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="fb388-180">請參閱[Enable Microsoft Defender 防毒軟體，並確認它是以被動模式](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="fb388-180">See [Enable Microsoft Defender Antivirus and confirm it's in passive mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode).</span></span>

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a><span data-ttu-id="fb388-181">如何確認 Microsoft Defender 防毒軟體處於主動或被動模式？</span><span class="sxs-lookup"><span data-stu-id="fb388-181">How do I confirm Microsoft Defender Antivirus is in active or passive mode?</span></span>

<span data-ttu-id="fb388-182">若要確認 Microsoft Defender 防毒軟體是否以主動或被動模式執行，您可以在執行 Windows 的裝置上使用命令提示字元或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="fb388-182">To confirm whether Microsoft Defender Antivirus is running in active or passive mode, you can use Command Prompt or PowerShell on a device running Windows.</span></span>

#### <a name="use-powershell"></a><span data-ttu-id="fb388-183">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb388-183">Use PowerShell</span></span>

1. <span data-ttu-id="fb388-184">選取 [開始] 功能表，開始輸入 `PowerShell` ，然後在結果中開啟 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="fb388-184">Select the Start menu, begin typing `PowerShell`, and then open Windows PowerShell in the results.</span></span>

2. <span data-ttu-id="fb388-185">類型 `Get-MpComputerStatus`。</span><span class="sxs-lookup"><span data-stu-id="fb388-185">Type `Get-MpComputerStatus`.</span></span>

3. <span data-ttu-id="fb388-186">在結果清單中的 [ **AMRunningMode** ] 列中，尋找下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="fb388-186">In the list of results, in the **AMRunningMode** row, look for one of the following values:</span></span>   
   - `Normal`
   - `Passive Mode`  
   - `SxS Passive Mode`

<span data-ttu-id="fb388-187">若要深入瞭解，請參閱 [MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)。</span><span class="sxs-lookup"><span data-stu-id="fb388-187">To learn more, see [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus).</span></span>

#### <a name="use-command-prompt"></a><span data-ttu-id="fb388-188">使用命令提示字元</span><span class="sxs-lookup"><span data-stu-id="fb388-188">Use Command Prompt</span></span>

1. <span data-ttu-id="fb388-189">選取 [開始] 功能表，開始輸入 `Command Prompt` ，然後在結果中開啟 Windows 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="fb388-189">Select the Start menu, begin typing `Command Prompt`, and then open Windows Command Prompt in the results.</span></span>

2. <span data-ttu-id="fb388-190">類型 `sc query windefend`。</span><span class="sxs-lookup"><span data-stu-id="fb388-190">Type `sc query windefend`.</span></span>

3. <span data-ttu-id="fb388-191">在結果清單中的 [ **狀態** ] 列中，確認服務正在執行中。</span><span class="sxs-lookup"><span data-stu-id="fb388-191">In the list of results, in the **STATE** row, confirm that the service is running.</span></span>

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a><span data-ttu-id="fb388-192">停用封鎖模式中的 EDR 需要多少時間？</span><span class="sxs-lookup"><span data-stu-id="fb388-192">How much time does it take for EDR in block mode to be disabled?</span></span>

<span data-ttu-id="fb388-193">如果您選擇在封鎖模式中停用 EDR 可能需要30分鐘的時間，系統才會停用此功能。</span><span class="sxs-lookup"><span data-stu-id="fb388-193">If you chose to disable EDR in block mode it can take up to 30 minutes for the system to disable this capability.</span></span>

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a><span data-ttu-id="fb388-194">在 Windows Server 2016 上支援的封鎖模式中 EDR 嗎？</span><span class="sxs-lookup"><span data-stu-id="fb388-194">Is EDR in block mode supported on Windows Server 2016?</span></span>

<span data-ttu-id="fb388-195">錯誤。</span><span class="sxs-lookup"><span data-stu-id="fb388-195">No.</span></span> <span data-ttu-id="fb388-196">在封鎖模式中 EDR 為下列 Windows 版本支援的版本：</span><span class="sxs-lookup"><span data-stu-id="fb388-196">EDR in block mode is supported of the following versions of Windows:</span></span>

- <span data-ttu-id="fb388-197">所有版本 Windows 10 () </span><span class="sxs-lookup"><span data-stu-id="fb388-197">Windows 10 (all releases)</span></span>
- <span data-ttu-id="fb388-198">Windows伺服器、版本1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="fb388-198">Windows Server, version 1803 or newer</span></span> 
- <span data-ttu-id="fb388-199">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="fb388-199">Windows Server 2019</span></span> 

## <a name="see-also"></a><span data-ttu-id="fb388-200">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fb388-200">See also</span></span>

- [<span data-ttu-id="fb388-201">技術 Community 博客：在封鎖模式中引入 EDR：在其蹤跡中停止攻擊</span><span class="sxs-lookup"><span data-stu-id="fb388-201">Tech Community blog: Introducing EDR in block mode: Stopping attacks in their tracks</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [<span data-ttu-id="fb388-202">行為封鎖和包含專案</span><span class="sxs-lookup"><span data-stu-id="fb388-202">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)
- [<span data-ttu-id="fb388-203">相得益彰：Microsoft Defender 防毒軟體與適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fb388-203">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

