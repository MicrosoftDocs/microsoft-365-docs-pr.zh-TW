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
ms.date: 07/13/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 1915a57becb1cba14605f4512ff123c1bca846bb
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415596"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a><span data-ttu-id="d8db9-104">在封鎖模式中) 的端點偵測和回應 (EDR</span><span class="sxs-lookup"><span data-stu-id="d8db9-104">Endpoint detection and response (EDR) in block mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d8db9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d8db9-105">**Applies to:**</span></span>
- [<span data-ttu-id="d8db9-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d8db9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d8db9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8db9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d8db9-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d8db9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d8db9-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d8db9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a><span data-ttu-id="d8db9-110">封鎖模式中的 EDR 為何？</span><span class="sxs-lookup"><span data-stu-id="d8db9-110">What is EDR in block mode?</span></span>

<span data-ttu-id="d8db9-111">[Endpoint 偵測和 response](overview-endpoint-detection-response.md) (EDR) 在封鎖模式中，當 Microsoft Defender 防毒軟體不是主要防病毒產品且以被動模式執行時，可提供對惡意專案的保護。</span><span class="sxs-lookup"><span data-stu-id="d8db9-111">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR) in block mode provides added protection from malicious artifacts when Microsoft Defender Antivirus is not the primary antivirus product and is running in passive mode.</span></span> <span data-ttu-id="d8db9-112">EDR 以封鎖模式 remediates 使用 EDR 偵測到的惡意專案。</span><span class="sxs-lookup"><span data-stu-id="d8db9-112">EDR in block mode remediates malicious artifacts that are detected using EDR.</span></span> <span data-ttu-id="d8db9-113">主要的非 Microsoft 防病毒產品可能已錯過這類專案。</span><span class="sxs-lookup"><span data-stu-id="d8db9-113">Such artifacts might have been missed by the primary, non-Microsoft antivirus product.</span></span> <span data-ttu-id="d8db9-114">block 模式中的 EDR 會在幕後運作，以在裝置上修正偵測到的惡意專案（遭到破壞）。</span><span class="sxs-lookup"><span data-stu-id="d8db9-114">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected, post breach, on a device.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d8db9-115">當 Microsoft Defender 防毒軟體即時保護啟用時，封鎖模式中的 EDR 不會提供所有可用的保護。</span><span class="sxs-lookup"><span data-stu-id="d8db9-115">EDR in block mode does not provide all the protection that is available when Microsoft Defender Antivirus real-time protection is enabled.</span></span> <span data-ttu-id="d8db9-116">所有依賴 Microsoft Defender 防毒軟體成為使用中防病毒方案的功能將無法運作，包括下列主要範例：</span><span class="sxs-lookup"><span data-stu-id="d8db9-116">All features that depend on Microsoft Defender Antivirus to be the active antivirus solution will not work, including the following key examples:</span></span> 
> 
> - <span data-ttu-id="d8db9-117">當 Microsoft Defender 防毒軟體處於被動模式時，就無法使用即時保護（包括存取掃描）。</span><span class="sxs-lookup"><span data-stu-id="d8db9-117">Real-time protection, including on-access scanning, is not available when Microsoft Defender Antivirus is in passive mode.</span></span> <span data-ttu-id="d8db9-118">若要深入瞭解即時保護原則設定，請參閱 **[Enable and configure Microsoft Defender 防毒軟體 always on protection](configure-real-time-protection-microsoft-defender-antivirus.md)**。</span><span class="sxs-lookup"><span data-stu-id="d8db9-118">To learn more about real-time protection policy settings, see **[Enable and configure Microsoft Defender Antivirus always-on protection](configure-real-time-protection-microsoft-defender-antivirus.md)**.</span></span>
> - <span data-ttu-id="d8db9-119">僅當 Microsoft Defender 防毒軟體以主動模式執行時，才可使用 **[網路保護](network-protection.md)** 和 **[攻擊面降規則](attack-surface-reduction.md)** 等功能。</span><span class="sxs-lookup"><span data-stu-id="d8db9-119">Features like **[network protection](network-protection.md)** and **[attack surface reduction rules](attack-surface-reduction.md)** are only available when Microsoft Defender Antivirus is running in active mode.</span></span> 
> 
> <span data-ttu-id="d8db9-120">您的非 Microsoft 防病毒解決方案應該提供這些功能。</span><span class="sxs-lookup"><span data-stu-id="d8db9-120">It is expected that your non-Microsoft antivirus solution provides these capabilities.</span></span> 

<span data-ttu-id="d8db9-121">封鎖模式中 EDR 會與[威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)整合。</span><span class="sxs-lookup"><span data-stu-id="d8db9-121">EDR in block mode is integrated with [threat & vulnerability management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="d8db9-122">組織的安全性小組會取得[安全性建議](tvm-security-recommendation.md)，以在封鎖模式中開啟 EDR （如果尚未啟用）。</span><span class="sxs-lookup"><span data-stu-id="d8db9-122">Your organization's security team will get a [security recommendation](tvm-security-recommendation.md) to turn EDR in block mode on if it isn't already enabled.</span></span> 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="在封鎖模式中開啟 EDR 的建議":::

> [!TIP]
> <span data-ttu-id="d8db9-124">若要取得最佳保護，請務必 **[部署 Microsoft Defender For Endpoint 基準](configure-machines-security-baseline.md)**。</span><span class="sxs-lookup"><span data-stu-id="d8db9-124">To get the best protection, make sure to **[deploy Microsoft Defender for Endpoint baselines](configure-machines-security-baseline.md)**.</span></span>

## <a name="what-happens-when-something-is-detected"></a><span data-ttu-id="d8db9-125">偵測到某項時會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="d8db9-125">What happens when something is detected?</span></span>

<span data-ttu-id="d8db9-126">當以封鎖模式開啟 EDR，且偵測到惡意的專案時，Microsoft Defender 會封鎖和 remediates 該專案。</span><span class="sxs-lookup"><span data-stu-id="d8db9-126">When EDR in block mode is turned on, and a malicious artifact is detected, Microsoft Defender for Endpoint blocks and remediates that artifact.</span></span> <span data-ttu-id="d8db9-127">您的安全性作業小組會在重要訊息 [中心](respond-machine-alerts.md#check-activity-details-in-action-center)看到 **偵測為已** 完成的 **動作的偵測** 狀態。</span><span class="sxs-lookup"><span data-stu-id="d8db9-127">Your security operations team will see detection status as **Blocked** or **Prevented** in the [Action center](respond-machine-alerts.md#check-activity-details-in-action-center), listed as completed actions.</span></span>

<span data-ttu-id="d8db9-128">下圖顯示以封鎖模式 EDR 所偵測到並封鎖的未預期軟體實例：</span><span class="sxs-lookup"><span data-stu-id="d8db9-128">The following image shows an instance of unwanted software that was detected and blocked through EDR in block mode:</span></span>

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="在封鎖模式中 EDR 偵測到某項":::


## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="d8db9-130">在封鎖模式中啟用 EDR</span><span class="sxs-lookup"><span data-stu-id="d8db9-130">Enable EDR in block mode</span></span>

> [!TIP]
> <span data-ttu-id="d8db9-131">在封鎖模式中開啟 EDR 之前，請確定符合[需求](#requirements-for-edr-in-block-mode)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-131">Make sure the [requirements](#requirements-for-edr-in-block-mode) are met before turning on EDR in block mode.</span></span>

1. <span data-ttu-id="d8db9-132">移至 Microsoft 365 Defender 入口網站 ([https://security.microsoft.com/](https://security.microsoft.com/)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="d8db9-132">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com/](https://security.microsoft.com/)) and sign in.</span></span> 

2. <span data-ttu-id="d8db9-133">選擇 [**設定**  >  **端點**  >  **一般**  >  **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="d8db9-133">Choose **Settings** > **Endpoints** > **General** > **Advanced features**.</span></span>

3. <span data-ttu-id="d8db9-134">向下滾動，然後在 **block 模式中啟用 EDR 的** urn。</span><span class="sxs-lookup"><span data-stu-id="d8db9-134">Scroll down, and then urn on **Enable EDR in block mode**.</span></span>

> [!NOTE]
> <span data-ttu-id="d8db9-135">在封鎖模式中 EDR 只能在 Microsoft 365 Defender 入口網站 ([https://security.microsoft.com](https://security.microsoft.com)) 或從前 Microsoft Defender 資訊安全中心 () 中開啟 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="d8db9-135">EDR in block mode can be turned on only in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) or the former Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span> <span data-ttu-id="d8db9-136">您無法使用登錄機碼、Microsoft Intune 或群組原則來啟用或停用封鎖模式中的 EDR。</span><span class="sxs-lookup"><span data-stu-id="d8db9-136">You cannot use registry keys, Microsoft Intune, or Group Policy to enable or disable EDR in block mode.</span></span>

## <a name="requirements-for-edr-in-block-mode"></a><span data-ttu-id="d8db9-137">封鎖模式中 EDR 的需求</span><span class="sxs-lookup"><span data-stu-id="d8db9-137">Requirements for EDR in block mode</span></span>

| <span data-ttu-id="d8db9-138">需求</span><span class="sxs-lookup"><span data-stu-id="d8db9-138">Requirement</span></span>  | <span data-ttu-id="d8db9-139">詳細資料</span><span class="sxs-lookup"><span data-stu-id="d8db9-139">Details</span></span>  |
|---------|---------|
| <span data-ttu-id="d8db9-140">權限</span><span class="sxs-lookup"><span data-stu-id="d8db9-140">Permissions</span></span> | <span data-ttu-id="d8db9-141">您必須在[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)中指派全域管理員或安全性管理員角色。</span><span class="sxs-lookup"><span data-stu-id="d8db9-141">You must have the Global Administrator or Security Administrator role assigned in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span> <span data-ttu-id="d8db9-142">如需詳細資訊，請參閱 [基本許可權](basic-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-142">For more information, see [Basic permissions](basic-permissions.md).</span></span> |
| <span data-ttu-id="d8db9-143">作業系統</span><span class="sxs-lookup"><span data-stu-id="d8db9-143">Operating system</span></span>     | <span data-ttu-id="d8db9-144">裝置必須執行下列其中一個 Windows 版本：</span><span class="sxs-lookup"><span data-stu-id="d8db9-144">Devices must be running one of the following versions of Windows:</span></span> <br/><span data-ttu-id="d8db9-145">-Windows 10 (所有版本) </span><span class="sxs-lookup"><span data-stu-id="d8db9-145">- Windows 10 (all releases)</span></span> <br/><span data-ttu-id="d8db9-146">-Windows Server，版本1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="d8db9-146">- Windows Server, version 1803 or newer</span></span> <br/><span data-ttu-id="d8db9-147">-Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="d8db9-147">- Windows Server 2019</span></span> <br/><span data-ttu-id="d8db9-148">-只有當 Microsoft Defender 防毒軟體處於主動模式時，才 Windows Server 2016 () </span><span class="sxs-lookup"><span data-stu-id="d8db9-148">- Windows Server 2016 (only when Microsoft Defender Antivirus is in active mode)</span></span>     |
| <span data-ttu-id="d8db9-149">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d8db9-149">Microsoft Defender for Endpoint</span></span>     | <span data-ttu-id="d8db9-150">裝置必須架至 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="d8db9-150">Devices must be onboarded to Defender for Endpoint.</span></span> <span data-ttu-id="d8db9-151">請參閱 [Microsoft Defender For Endpoint 的基本需求](minimum-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-151">See [Minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md).</span></span>       |
| <span data-ttu-id="d8db9-152">Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="d8db9-152">Microsoft Defender Antivirus</span></span>  | <span data-ttu-id="d8db9-153">裝置必須以主動模式或被動模式安裝和執行 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="d8db9-153">Devices must have Microsoft Defender Antivirus installed and running in either active mode or passive mode.</span></span> <span data-ttu-id="d8db9-154">[確認 Microsoft Defender 防毒軟體處於主動或被動模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-154">[Confirm Microsoft Defender Antivirus is in active or passive mode](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).</span></span> |
| <span data-ttu-id="d8db9-155">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="d8db9-155">Cloud-delivered protection</span></span> | <span data-ttu-id="d8db9-156">您必須設定 Microsoft Defender 防毒軟體，讓[已啟用雲端傳遞的保護](enable-cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-156">Microsoft Defender Antivirus must be configured such that [cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span> |
| <span data-ttu-id="d8db9-157">Microsoft Defender 防毒軟體平臺</span><span class="sxs-lookup"><span data-stu-id="d8db9-157">Microsoft Defender Antivirus platform</span></span> | <span data-ttu-id="d8db9-158">裝置必須是最新的。</span><span class="sxs-lookup"><span data-stu-id="d8db9-158">Devices must be up to date.</span></span> <span data-ttu-id="d8db9-159">若要確認，使用 PowerShell，請以系統管理員身分執行 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d8db9-159">To confirm, using PowerShell, run the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet as an administrator.</span></span> <span data-ttu-id="d8db9-160">在 **AMProductVersion** 行中，您應該會看到 **4.18.2001.10** 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="d8db9-160">In the **AMProductVersion** line, you should see **4.18.2001.10** or above.</span></span> <p> <span data-ttu-id="d8db9-161">若要深入了解，請參閱[管理Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-161">To learn more, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> |
| <span data-ttu-id="d8db9-162">Microsoft Defender 防毒軟體引擎</span><span class="sxs-lookup"><span data-stu-id="d8db9-162">Microsoft Defender Antivirus engine</span></span> | <span data-ttu-id="d8db9-163">裝置必須是最新的。</span><span class="sxs-lookup"><span data-stu-id="d8db9-163">Devices must be up to date.</span></span> <span data-ttu-id="d8db9-164">若要確認，使用 PowerShell，請以系統管理員身分執行 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d8db9-164">To confirm, using PowerShell, run the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet as an administrator.</span></span> <span data-ttu-id="d8db9-165">在 **AMEngineVersion** 行中，您應該會看到 **1.1.16700.2** 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="d8db9-165">In the **AMEngineVersion** line, you should see **1.1.16700.2** or above.</span></span> <p> <span data-ttu-id="d8db9-166">若要深入了解，請參閱[管理Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-166">To learn more, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="d8db9-167">若要取得最佳保護值，請確定您的防病毒方案已設定為接收定期更新和基本功能，以及您的 [排除已設定](configure-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-167">To get the best protection value, make sure your antivirus solution is configured to receive regular updates and essential features, and that your [exclusions are configured](configure-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="d8db9-168">封鎖模式中 EDR 會考慮針對 Microsoft Defender 防毒軟體定義的排除專案，但不會考慮為 Microsoft Defender for Endpoint 定義的[指示器](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-168">EDR in block mode respects exclusions that are defined for Microsoft Defender Antivirus, but not [indicators](manage-indicators.md) that are defined for Microsoft Defender for Endpoint.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d8db9-169">常見問題集</span><span class="sxs-lookup"><span data-stu-id="d8db9-169">Frequently asked questions</span></span> 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a><span data-ttu-id="d8db9-170">在裝置上執行 Microsoft Defender 防毒軟體時，是否需要在封鎖模式中開啟 EDR？</span><span class="sxs-lookup"><span data-stu-id="d8db9-170">Do I need to turn EDR in block mode on if I have Microsoft Defender Antivirus running on devices?</span></span>

<span data-ttu-id="d8db9-171">封鎖模式中 EDR 的主要目的是修正非 Microsoft 防病毒產品錯過的破壞後偵測。</span><span class="sxs-lookup"><span data-stu-id="d8db9-171">The primary purpose of EDR in block mode is to remediate post-breach detections that were missed by a non-Microsoft antivirus product.</span></span> <span data-ttu-id="d8db9-172">不過，建議您將 EDR 置於封鎖模式，不論 Microsoft Defender 防毒軟體是以被動模式還是以主動模式執行。</span><span class="sxs-lookup"><span data-stu-id="d8db9-172">However, we recommend keeping EDR in block mode turned on, whether Microsoft Defender Antivirus is running in passive mode or in active mode.</span></span> 

- <span data-ttu-id="d8db9-173">當 Microsoft Defender 防毒軟體處於被動模式時，在封鎖模式中 EDR 會提供另一層的防禦，以及 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="d8db9-173">When Microsoft Defender Antivirus is in passive mode, EDR in block mode provides another layer of defense together with Microsoft Defender for Endpoint.</span></span> 
- <span data-ttu-id="d8db9-174">當 Microsoft Defender 防毒軟體處於主動模式時，EDR 以封鎖模式不會提供額外的掃描，但可讓 Defender 在破壞後的行為中自動採取動作 EDR 偵測。</span><span class="sxs-lookup"><span data-stu-id="d8db9-174">When Microsoft Defender Antivirus is in active mode, EDR in block mode does not provide extra scanning, but it does allow Defender for Endpoint to take automatic actions on post-breach, behavioral EDR detections.</span></span>

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a><span data-ttu-id="d8db9-175">會在封鎖模式中 EDR 是否會影響使用者的病毒防護？</span><span class="sxs-lookup"><span data-stu-id="d8db9-175">Will EDR in block mode affect a user's antivirus protection?</span></span> 

<span data-ttu-id="d8db9-176">在封鎖模式中 EDR 不會影響使用者裝置上執行的協力廠商防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="d8db9-176">EDR in block mode does not affect third-party antivirus protection running on users' devices.</span></span> <span data-ttu-id="d8db9-177">如果主要防病毒解決方案未接任何問題，或發生破壞後的情況，則 EDR 以封鎖模式運作。</span><span class="sxs-lookup"><span data-stu-id="d8db9-177">EDR in block mode works if the primary antivirus solution misses something, or if there is a post-breach detection.</span></span> <span data-ttu-id="d8db9-178">在封鎖模式中 EDR 的運作方式，Microsoft Defender 防毒軟體在被動模式中，但在封鎖模式中 EDR 也會封鎖和 remediates 所偵測到的惡意偽像或行為。</span><span class="sxs-lookup"><span data-stu-id="d8db9-178">EDR in block mode works just like Microsoft Defender Antivirus in passive mode, except that EDR in block mode also blocks and remediates malicious artifacts or behaviors that are detected.</span></span>

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a><span data-ttu-id="d8db9-179">為什麼我需要讓 Microsoft Defender 防毒軟體保持最新狀態？</span><span class="sxs-lookup"><span data-stu-id="d8db9-179">Why do I need to keep Microsoft Defender Antivirus up to date?</span></span> 

<span data-ttu-id="d8db9-180">由於 Microsoft Defender 防毒軟體偵測和 remediates 惡意專案，因此務必將其保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="d8db9-180">Because Microsoft Defender Antivirus detects and remediates malicious items, it's important to keep it up to date.</span></span> <span data-ttu-id="d8db9-181">為使封鎖模式中的 EDR 生效，它會使用最新的裝置學習模型、行為偵測和試探法。</span><span class="sxs-lookup"><span data-stu-id="d8db9-181">For EDR in block mode to be effective, it uses the latest device learning models, behavioral detections, and heuristics.</span></span> <span data-ttu-id="d8db9-182">功能 [終結點](microsoft-defender-endpoint.md) 堆疊功能的運作方式是以整合方式運作。</span><span class="sxs-lookup"><span data-stu-id="d8db9-182">The [Defender for Endpoint](microsoft-defender-endpoint.md) stack of capabilities works in an integrated manner.</span></span> <span data-ttu-id="d8db9-183">若要取得最佳防護值，您應該將 Microsoft Defender 防毒軟體保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="d8db9-183">To get best protection value, you should keep Microsoft Defender Antivirus up to date.</span></span> <span data-ttu-id="d8db9-184">請參閱[管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-184">See [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> 

### <a name="why-do-we-need-cloud-protection-maps-on"></a><span data-ttu-id="d8db9-185">為什麼需要 () 的雲端保護？</span><span class="sxs-lookup"><span data-stu-id="d8db9-185">Why do we need cloud protection (MAPS) on?</span></span> 

<span data-ttu-id="d8db9-186">需要 Cloud protection 才能開啟裝置上的功能。</span><span class="sxs-lookup"><span data-stu-id="d8db9-186">Cloud protection is needed to turn on the feature on the device.</span></span> <span data-ttu-id="d8db9-187">雲端防護功能可讓 [Defender For Endpoint](microsoft-defender-endpoint.md) ，根據我們的廣泛和深度安全性情報，以及行為和裝置教學模型，提供最新和最佳的保護。</span><span class="sxs-lookup"><span data-stu-id="d8db9-187">Cloud protection allows [Defender for Endpoint](microsoft-defender-endpoint.md) to deliver the latest and greatest protection based on our breadth and depth of security intelligence, along with behavioral and device learning models.</span></span>

### <a name="what-is-the-difference-between-active-and-passive-mode"></a><span data-ttu-id="d8db9-188">主動與被動模式之間的差異為何？</span><span class="sxs-lookup"><span data-stu-id="d8db9-188">What is the difference between active and passive mode?</span></span>

<span data-ttu-id="d8db9-189">針對執行 Windows 10 的端點、Windows Server、版本1803或更新版本，或 Windows Server 2019，當 Microsoft Defender 防毒軟體處於作用中模式時，會將其當作裝置上的主要防毒軟體使用。</span><span class="sxs-lookup"><span data-stu-id="d8db9-189">For endpoints running Windows 10, Windows Server, version 1803 or later, or Windows Server 2019, when Microsoft Defender Antivirus is in active mode, it is used as the primary antivirus on the device.</span></span> <span data-ttu-id="d8db9-190">在被動模式中執行時，Microsoft Defender 防毒軟體不是主要的防病毒產品。</span><span class="sxs-lookup"><span data-stu-id="d8db9-190">When running in passive mode, Microsoft Defender Antivirus is not the primary antivirus product.</span></span> <span data-ttu-id="d8db9-191">在此情況下，不會 Microsoft Defender 防毒軟體即時修正威脅。</span><span class="sxs-lookup"><span data-stu-id="d8db9-191">In this case, threats are not remediated by Microsoft Defender Antivirus in real time.</span></span>

> [!NOTE]
> <span data-ttu-id="d8db9-192">只有當裝置架至 Microsoft Defender for Endpoint 時，才可以在被動模式下執行 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="d8db9-192">Microsoft Defender Antivirus can run in passive mode only when the device is onboarded to Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="d8db9-193">如需詳細資訊，請參閱[Microsoft Defender 防毒軟體相容性](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-193">For more information, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a><span data-ttu-id="d8db9-194">如何確認 Microsoft Defender 防毒軟體處於主動或被動模式？</span><span class="sxs-lookup"><span data-stu-id="d8db9-194">How do I confirm Microsoft Defender Antivirus is in active or passive mode?</span></span>

<span data-ttu-id="d8db9-195">若要確認 Microsoft Defender 防毒軟體是否以主動或被動模式執行，您可以在執行 Windows 的裝置上使用命令提示字元或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d8db9-195">To confirm whether Microsoft Defender Antivirus is running in active or passive mode, you can use Command Prompt or PowerShell on a device running Windows.</span></span>

|<span data-ttu-id="d8db9-196">方法</span><span class="sxs-lookup"><span data-stu-id="d8db9-196">Method</span></span>  |<span data-ttu-id="d8db9-197">程序</span><span class="sxs-lookup"><span data-stu-id="d8db9-197">Procedure</span></span>  |
|---------|---------|
| <span data-ttu-id="d8db9-198">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8db9-198">PowerShell</span></span>     | <span data-ttu-id="d8db9-199">1. 選取 [[開始] 功能表]，開始輸入 `PowerShell` ，然後在結果中開啟 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d8db9-199">1. Select the Start menu, begin typing `PowerShell`, and then open Windows PowerShell in the results.</span></span> <p><span data-ttu-id="d8db9-200">2. 輸入 `Get-MpComputerStatus` 。</span><span class="sxs-lookup"><span data-stu-id="d8db9-200">2. Type `Get-MpComputerStatus`.</span></span> <p><span data-ttu-id="d8db9-201">3. 在結果清單中的 [ **AMRunningMode** ] 列中，尋找下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="d8db9-201">3. In the list of results, in the **AMRunningMode** row, look for one of the following values:</span></span> <br/>- `Normal` <br/>- `Passive Mode` <p><span data-ttu-id="d8db9-202">若要深入瞭解，請參閱 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-202">To learn more, see [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).</span></span>        |
|<span data-ttu-id="d8db9-203">命令提示字元</span><span class="sxs-lookup"><span data-stu-id="d8db9-203">Command Prompt</span></span>     | <span data-ttu-id="d8db9-204">1. 選取 [開始] 功能表，開始輸入 `Command Prompt` ，然後在結果中開啟 Windows 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="d8db9-204">1. Select the Start menu, begin typing `Command Prompt`, and then open Windows Command Prompt in the results.</span></span> <p><span data-ttu-id="d8db9-205">2. 輸入 `sc query windefend` 。</span><span class="sxs-lookup"><span data-stu-id="d8db9-205">2. Type `sc query windefend`.</span></span> <p><span data-ttu-id="d8db9-206">3. 在結果清單中的 [ **狀態** ] 列中，確認服務正在執行中。</span><span class="sxs-lookup"><span data-stu-id="d8db9-206">3. In the list of results, in the **STATE** row, confirm that the service is running.</span></span>         |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a><span data-ttu-id="d8db9-207">如何確認 EDR 在封鎖模式中以被動模式 Microsoft Defender 防毒軟體開啟？</span><span class="sxs-lookup"><span data-stu-id="d8db9-207">How do I confirm that EDR in block mode is turned on with Microsoft Defender Antivirus in passive mode?</span></span>

<span data-ttu-id="d8db9-208">您可以使用 PowerShell，確認 EDR 在封鎖模式中已開啟，且 Microsoft Defender 防毒軟體以被動模式執行。</span><span class="sxs-lookup"><span data-stu-id="d8db9-208">You can use PowerShell to confirm that EDR in block mode is turned on with Microsoft Defender Antivirus running in passive mode.</span></span>

1. <span data-ttu-id="d8db9-209">選取 [開始] 功能表，開始輸入 `PowerShell` ，然後在結果中開啟 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d8db9-209">Select the Start menu, begin typing `PowerShell`, and then open Windows PowerShell in the results.</span></span> 

2. <span data-ttu-id="d8db9-210">輸入 `Get-MPComputerStatus | select AMRunningMode`。</span><span class="sxs-lookup"><span data-stu-id="d8db9-210">Type `Get-MPComputerStatus | select AMRunningMode`.</span></span>

3. <span data-ttu-id="d8db9-211">確認 `EDR Block Mode` 會顯示結果。</span><span class="sxs-lookup"><span data-stu-id="d8db9-211">Confirm that the result, `EDR Block Mode`, is displayed.</span></span>

   > [!TIP]
   > <span data-ttu-id="d8db9-212">如果 Microsoft Defender 防毒軟體以主動模式顯示，您會看到 `Normal` 而不是 `EDR Block Mode` 。</span><span class="sxs-lookup"><span data-stu-id="d8db9-212">If Microsoft Defender Antivirus is in active mode, you will see `Normal` instead of `EDR Block Mode`.</span></span> <span data-ttu-id="d8db9-213">若要深入瞭解，請參閱 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-213">To learn more, see [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).</span></span>

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a><span data-ttu-id="d8db9-214">在 Windows Server 2016 上支援的封鎖模式中 EDR 嗎？</span><span class="sxs-lookup"><span data-stu-id="d8db9-214">Is EDR in block mode supported on Windows Server 2016?</span></span>

<span data-ttu-id="d8db9-215">如果 Microsoft Defender 防毒軟體以主動模式或被動模式執行，則下列 Windows 版本都支援 EDR in 封鎖模式：</span><span class="sxs-lookup"><span data-stu-id="d8db9-215">If Microsoft Defender Antivirus is running in active mode or passive mode, EDR in block mode is supported of the following versions of Windows:</span></span>

- <span data-ttu-id="d8db9-216">所有版本 Windows 10 () </span><span class="sxs-lookup"><span data-stu-id="d8db9-216">Windows 10 (all releases)</span></span>
- <span data-ttu-id="d8db9-217">Windows伺服器、版本1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="d8db9-217">Windows Server, version 1803 or newer</span></span> 
- <span data-ttu-id="d8db9-218">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="d8db9-218">Windows Server 2019</span></span> 

#### <a name="what-about-windows-server-2016"></a><span data-ttu-id="d8db9-219">Windows Server 2016 的情況為何？</span><span class="sxs-lookup"><span data-stu-id="d8db9-219">What about Windows Server 2016?</span></span> 

<span data-ttu-id="d8db9-220">如果 Windows Server 2016 以主動模式執行 Microsoft Defender 防毒軟體，且端點架至 Defender for endpoint，則會以技術支援的封鎖模式 EDR。</span><span class="sxs-lookup"><span data-stu-id="d8db9-220">If Windows Server 2016 has Microsoft Defender Antivirus running in active mode, and the endpoint is onboarded to Defender for Endpoint, then EDR in block mode is technically supported.</span></span> <span data-ttu-id="d8db9-221">不過，當 Microsoft Defender 防毒軟體不是端點上的主要防病毒方案時，在封鎖模式中 EDR 應是額外的保護。</span><span class="sxs-lookup"><span data-stu-id="d8db9-221">However, EDR in block mode is intended to be extra protection when Microsoft Defender Antivirus is not the primary antivirus solution on an endpoint.</span></span> <span data-ttu-id="d8db9-222">在這種情況下，Microsoft Defender 防毒軟體會以被動模式執行。</span><span class="sxs-lookup"><span data-stu-id="d8db9-222">In those cases, Microsoft Defender Antivirus runs in passive mode.</span></span> 

<span data-ttu-id="d8db9-223">目前，Windows Server 2016 上不支援以被動模式執行 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="d8db9-223">Currently, running Microsoft Defender Antivirus in passive mode is not supported on Windows Server 2016.</span></span> <span data-ttu-id="d8db9-224">若要深入瞭解，請參閱[Microsoft Defender 防毒軟體和非 Microsoft 防毒軟體/反惡意程式碼解決方案](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)。</span><span class="sxs-lookup"><span data-stu-id="d8db9-224">To learn more, see [Microsoft Defender Antivirus and non-Microsoft antivirus/antimalware solutions](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions).</span></span>

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a><span data-ttu-id="d8db9-225">停用封鎖模式中的 EDR 需要多少時間？</span><span class="sxs-lookup"><span data-stu-id="d8db9-225">How much time does it take for EDR in block mode to be disabled?</span></span>

<span data-ttu-id="d8db9-226">如果您選擇以封鎖模式停用 EDR，最多可能需要30分鐘的時間，系統才會停用此功能。</span><span class="sxs-lookup"><span data-stu-id="d8db9-226">If you choose to disable EDR in block mode, it can take up to 30 minutes for the system to disable this capability.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8db9-227">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d8db9-227">See also</span></span>

- [<span data-ttu-id="d8db9-228">技術 Community 博客：在封鎖模式中引入 EDR：在其蹤跡中停止攻擊</span><span class="sxs-lookup"><span data-stu-id="d8db9-228">Tech Community blog: Introducing EDR in block mode: Stopping attacks in their tracks</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [<span data-ttu-id="d8db9-229">行為封鎖和包含專案</span><span class="sxs-lookup"><span data-stu-id="d8db9-229">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

