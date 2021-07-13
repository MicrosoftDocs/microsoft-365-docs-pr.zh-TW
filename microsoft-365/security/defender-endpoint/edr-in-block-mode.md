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
ms.date: 06/11/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 835195f0c35ada409ef632b2dbfa1b6de0291351
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409149"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a><span data-ttu-id="b8997-104">在封鎖模式中) 的端點偵測和回應 (EDR</span><span class="sxs-lookup"><span data-stu-id="b8997-104">Endpoint detection and response (EDR) in block mode</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b8997-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b8997-105">**Applies to:**</span></span>
- [<span data-ttu-id="b8997-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b8997-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b8997-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8997-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b8997-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b8997-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b8997-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b8997-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a><span data-ttu-id="b8997-110">封鎖模式中的 EDR 為何？</span><span class="sxs-lookup"><span data-stu-id="b8997-110">What is EDR in block mode?</span></span>

<span data-ttu-id="b8997-111">[端點偵測和回應](overview-endpoint-detection-response.md) (EDR) 在封鎖模式中時，即使 Microsoft Defender 防毒軟體是以被動模式執行，也可以保護惡意的惡意資料。</span><span class="sxs-lookup"><span data-stu-id="b8997-111">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="b8997-112">開啟時，以封鎖模式 EDR 會封鎖在裝置上偵測到的惡意的偽像或行為。</span><span class="sxs-lookup"><span data-stu-id="b8997-112">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="b8997-113">block 模式中的 EDR 會在幕後運作，以修正偵測到破壞後偵測到的惡意作品。</span><span class="sxs-lookup"><span data-stu-id="b8997-113">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span> 

<span data-ttu-id="b8997-114">組塊模式中的 EDR 也會與[威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)整合。</span><span class="sxs-lookup"><span data-stu-id="b8997-114">EDR in block mode is also integrated with [threat & vulnerability management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="b8997-115">組織的安全性小組會取得[安全性建議](tvm-security-recommendation.md)，以在封鎖模式中開啟 EDR （如果尚未啟用）。</span><span class="sxs-lookup"><span data-stu-id="b8997-115">Your organization's security team will get a [security recommendation](tvm-security-recommendation.md) to turn EDR in block mode on if it isn't already enabled.</span></span> 

:::image type="content" source="images/enable-edr-in-block-mode.png" alt-text="在封鎖模式中開啟 EDR 的建議":::

> [!NOTE]
> <span data-ttu-id="b8997-117">若要取得最佳保護，請務必 **[部署 Microsoft Defender For Endpoint 基準](configure-machines-security-baseline.md)**。</span><span class="sxs-lookup"><span data-stu-id="b8997-117">To get the best protection, make sure to **[deploy Microsoft Defender for Endpoint baselines](configure-machines-security-baseline.md)**.</span></span>

## <a name="what-happens-when-something-is-detected"></a><span data-ttu-id="b8997-118">偵測到某項時會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="b8997-118">What happens when something is detected?</span></span>

<span data-ttu-id="b8997-119">當以封鎖模式開啟 EDR，且偵測到惡意的專案時，Microsoft Defender 會封鎖和 remediates 該專案。</span><span class="sxs-lookup"><span data-stu-id="b8997-119">When EDR in block mode is turned on, and a malicious artifact is detected, Microsoft Defender for Endpoint blocks and remediates that artifact.</span></span> <span data-ttu-id="b8997-120">您的安全性作業小組會在重要訊息 [中心](respond-machine-alerts.md#check-activity-details-in-action-center)看到 **偵測為已** 完成的 **動作的偵測** 狀態。</span><span class="sxs-lookup"><span data-stu-id="b8997-120">Your security operations team will see detection status as **Blocked** or **Prevented** in the [Action center](respond-machine-alerts.md#check-activity-details-in-action-center), listed as completed actions.</span></span>

<span data-ttu-id="b8997-121">下圖顯示以封鎖模式 EDR 所偵測到並封鎖的未預期軟體實例：</span><span class="sxs-lookup"><span data-stu-id="b8997-121">The following image shows an instance of unwanted software that was detected and blocked through EDR in block mode:</span></span>

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="在封鎖模式中 EDR 偵測到某項":::


## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="b8997-123">在封鎖模式中啟用 EDR</span><span class="sxs-lookup"><span data-stu-id="b8997-123">Enable EDR in block mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8997-124">在封鎖模式中開啟 EDR 之前，請確定符合[需求](#requirements-for-edr-in-block-mode)。</span><span class="sxs-lookup"><span data-stu-id="b8997-124">Make sure the [requirements](#requirements-for-edr-in-block-mode) are met before turning on EDR in block mode.</span></span>

1. <span data-ttu-id="b8997-125">移至[Microsoft 365 Defender 入口網站](microsoft-defender-security-center.md)並登入。</span><span class="sxs-lookup"><span data-stu-id="b8997-125">Go to the [Microsoft 365 Defender portal](microsoft-defender-security-center.md) and sign in.</span></span> 

2. <span data-ttu-id="b8997-126">選擇 [**設定**  >  **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="b8997-126">Choose **Settings** > **Advanced features**.</span></span>

3. <span data-ttu-id="b8997-127">**在塊狀模式中開啟 EDR**。</span><span class="sxs-lookup"><span data-stu-id="b8997-127">Turn on **EDR in block mode**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b8997-128">在組塊模式中 EDR 只能在 Microsoft 365 Defender 入口網站中開啟。</span><span class="sxs-lookup"><span data-stu-id="b8997-128">EDR in block mode can be turned on only in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="b8997-129">您無法使用登錄機碼、Intune 或群組原則，在封鎖模式中啟用或停用 EDR。</span><span class="sxs-lookup"><span data-stu-id="b8997-129">You cannot use registry keys, Intune, or group policies to enable or disable EDR in block mode.</span></span>

## <a name="requirements-for-edr-in-block-mode"></a><span data-ttu-id="b8997-130">封鎖模式中 EDR 的需求</span><span class="sxs-lookup"><span data-stu-id="b8997-130">Requirements for EDR in block mode</span></span>

|<span data-ttu-id="b8997-131">需求</span><span class="sxs-lookup"><span data-stu-id="b8997-131">Requirement</span></span>  |<span data-ttu-id="b8997-132">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b8997-132">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="b8997-133">權限</span><span class="sxs-lookup"><span data-stu-id="b8997-133">Permissions</span></span> |<span data-ttu-id="b8997-134">在[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)中指派全域管理員或安全性管理員角色。</span><span class="sxs-lookup"><span data-stu-id="b8997-134">Global Administrator or Security Administrator role assigned in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span> <span data-ttu-id="b8997-135">請參閱 [基本許可權](basic-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="b8997-135">See [Basic permissions](basic-permissions.md).</span></span> |
|<span data-ttu-id="b8997-136">作業系統</span><span class="sxs-lookup"><span data-stu-id="b8997-136">Operating system</span></span>     |<span data-ttu-id="b8997-137">下列其中一個版本：</span><span class="sxs-lookup"><span data-stu-id="b8997-137">One of the following versions:</span></span> <br/><span data-ttu-id="b8997-138">-Windows 10 (所有版本) </span><span class="sxs-lookup"><span data-stu-id="b8997-138">- Windows 10 (all releases)</span></span> <br/><span data-ttu-id="b8997-139">-Windows Server，版本1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="b8997-139">- Windows Server, version 1803 or newer</span></span> <br/><span data-ttu-id="b8997-140">-Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="b8997-140">- Windows Server 2019</span></span> <br/><span data-ttu-id="b8997-141">-只有當 Microsoft Defender 防毒軟體處於主動模式時，才 Windows Server 2016 () </span><span class="sxs-lookup"><span data-stu-id="b8997-141">- Windows Server 2016 (only when Microsoft Defender Antivirus is in active mode)</span></span>     |
|<span data-ttu-id="b8997-142">WindowsE5 登記</span><span class="sxs-lookup"><span data-stu-id="b8997-142">Windows E5 enrollment</span></span>     |<span data-ttu-id="b8997-143">WindowsE5 包含在下列訂閱中：</span><span class="sxs-lookup"><span data-stu-id="b8997-143">Windows E5 is included in the following subscriptions:</span></span> <br/><span data-ttu-id="b8997-144">-Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b8997-144">- Microsoft 365 E5</span></span> <br/><span data-ttu-id="b8997-145">-Microsoft 365 E3 搭配 Microsoft 365 E5 安全性附加元件</span><span class="sxs-lookup"><span data-stu-id="b8997-145">- Microsoft 365 E3 together with the Microsoft 365 E5 Security Add-on</span></span> <br/><br/><span data-ttu-id="b8997-146">請參閱[每個計畫的](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)[元件](/microsoft-365/enterprise/microsoft-365-overview#components)和功能。</span><span class="sxs-lookup"><span data-stu-id="b8997-146">See [Components](/microsoft-365/enterprise/microsoft-365-overview#components) and [features and capabilities for each plan](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>       |
|<span data-ttu-id="b8997-147">Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="b8997-147">Microsoft Defender Antivirus</span></span>  |<span data-ttu-id="b8997-148">必須以主動模式或被動模式安裝和執行 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="b8997-148">Microsoft Defender Antivirus must be installed and running in either active mode or passive mode.</span></span> <span data-ttu-id="b8997-149"> (您可以在非 Microsoft 防病毒方案旁使用 Microsoft Defender 防毒軟體。 ) [確認 Microsoft Defender 防毒軟體為主動或被動模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="b8997-149">(You can use Microsoft Defender Antivirus alongside a non-Microsoft antivirus solution.) [Confirm Microsoft Defender Antivirus is in active or passive mode](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).</span></span> |
|<span data-ttu-id="b8997-150">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="b8997-150">Cloud-delivered protection</span></span> |<span data-ttu-id="b8997-151">請確定已設定 Microsoft Defender 防毒軟體，讓[已啟用雲端傳遞的保護](enable-cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="b8997-151">Make sure Microsoft Defender Antivirus is configured such that [cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span> |
|<span data-ttu-id="b8997-152">Microsoft Defender 防毒軟體反惡意程式碼用戶端</span><span class="sxs-lookup"><span data-stu-id="b8997-152">Microsoft Defender Antivirus antimalware client</span></span> |<span data-ttu-id="b8997-153">請確定您的用戶端是最新版本。</span><span class="sxs-lookup"><span data-stu-id="b8997-153">Make sure your client is up to date.</span></span> <span data-ttu-id="b8997-154">使用 PowerShell，以系統管理員身分執行 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b8997-154">Using PowerShell, run the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet as an administrator.</span></span> <span data-ttu-id="b8997-155">在 **AMProductVersion** 行中，您應該會看到 **4.18.2001.10** 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b8997-155">In the **AMProductVersion** line, you should see **4.18.2001.10** or above.</span></span> |
|<span data-ttu-id="b8997-156">Microsoft Defender 防毒軟體引擎</span><span class="sxs-lookup"><span data-stu-id="b8997-156">Microsoft Defender Antivirus engine</span></span> |<span data-ttu-id="b8997-157">請確定您的引擎是最新版本。</span><span class="sxs-lookup"><span data-stu-id="b8997-157">Make sure your engine is up to date.</span></span> <span data-ttu-id="b8997-158">使用 PowerShell，以系統管理員身分執行 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b8997-158">Using PowerShell, run the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet as an administrator.</span></span> <span data-ttu-id="b8997-159">在 **AMEngineVersion** 行中，您應該會看到 **1.1.16700.2** 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b8997-159">In the **AMEngineVersion** line, you should see **1.1.16700.2** or above.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="b8997-160">若要取得最佳保護值，請確定您的防病毒方案已設定為接收定期更新和基本功能，以及您的 [排除已設定](configure-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="b8997-160">To get the best protection value, make sure your antivirus solution is configured to receive regular updates and essential features, and that your [exclusions are configured](configure-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="b8997-161">在封鎖模式中 EDR 會考慮針對 Microsoft Defender 防毒軟體所定義的排除專案。</span><span class="sxs-lookup"><span data-stu-id="b8997-161">EDR in block mode respects exclusions that are defined for Microsoft Defender Antivirus.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="b8997-162">常見問題集</span><span class="sxs-lookup"><span data-stu-id="b8997-162">Frequently asked questions</span></span> 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a><span data-ttu-id="b8997-163">即使在裝置上執行 Microsoft Defender 防毒軟體，我是否需要在封鎖模式中開啟 EDR？</span><span class="sxs-lookup"><span data-stu-id="b8997-163">Do I need to turn EDR in block mode on even when I have Microsoft Defender Antivirus running on devices?</span></span>

<span data-ttu-id="b8997-164">建議您將 EDR 置於封鎖模式，不論 Microsoft Defender 防毒軟體是以被動模式還是以主動模式執行。</span><span class="sxs-lookup"><span data-stu-id="b8997-164">We recommend keeping EDR in block mode on, whether Microsoft Defender Antivirus is running in passive mode or in active mode.</span></span> <span data-ttu-id="b8997-165">在封鎖模式中 EDR 會提供另一個與 Microsoft Defender for Endpoint 的防禦層。</span><span class="sxs-lookup"><span data-stu-id="b8997-165">EDR in block mode provides another layer of defense with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b8997-166">它可讓 Defender for Endpoint 根據破壞後的行為 EDR 偵測採取動作。</span><span class="sxs-lookup"><span data-stu-id="b8997-166">It allows Defender for Endpoint to take actions based on post-breach behavioral EDR detections.</span></span> 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a><span data-ttu-id="b8997-167">會在封鎖模式中 EDR 是否會影響使用者的病毒防護？</span><span class="sxs-lookup"><span data-stu-id="b8997-167">Will EDR in block mode have any impact on a user's antivirus protection?</span></span> 

<span data-ttu-id="b8997-168">在封鎖模式中 EDR 不會影響使用者裝置上執行的協力廠商防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="b8997-168">EDR in block mode does not affect third-party antivirus protection running on users' devices.</span></span> <span data-ttu-id="b8997-169">如果主要防病毒解決方案未接任何問題，或發生破壞後的情況，則 EDR 以封鎖模式運作。</span><span class="sxs-lookup"><span data-stu-id="b8997-169">EDR in block mode works if the primary antivirus solution misses something, or if there is a post-breach detection.</span></span> <span data-ttu-id="b8997-170">在封鎖模式中 EDR 的運作方式與被動模式 Microsoft Defender 防毒軟體相同，但也會封鎖和 remediates 偵測到的惡意專案或行為。</span><span class="sxs-lookup"><span data-stu-id="b8997-170">EDR in block mode works just like Microsoft Defender Antivirus in passive mode, except it also blocks and remediates malicious artifacts or behaviors that are detected.</span></span>

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a><span data-ttu-id="b8997-171">為什麼我需要讓 Microsoft Defender 防毒軟體保持最新狀態？</span><span class="sxs-lookup"><span data-stu-id="b8997-171">Why do I need to keep Microsoft Defender Antivirus up to date?</span></span> 

<span data-ttu-id="b8997-172">由於 Microsoft Defender 防毒軟體偵測和 remediates 惡意專案，因此務必將其保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="b8997-172">Because Microsoft Defender Antivirus detects and remediates malicious items, it's important to keep it up to date.</span></span> <span data-ttu-id="b8997-173">為使封鎖模式中的 EDR 生效，它會使用最新的裝置學習模型、行為偵測和試探法。</span><span class="sxs-lookup"><span data-stu-id="b8997-173">For EDR in block mode to be effective, it uses the latest device learning models, behavioral detections, and heuristics.</span></span> <span data-ttu-id="b8997-174">功能 [終結點](microsoft-defender-endpoint.md) 堆疊功能的運作方式是以整合方式運作。</span><span class="sxs-lookup"><span data-stu-id="b8997-174">The [Defender for Endpoint](microsoft-defender-endpoint.md) stack of capabilities works in an integrated manner.</span></span> <span data-ttu-id="b8997-175">若要取得最佳防護值，您應該將 Microsoft Defender 防毒軟體保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="b8997-175">To get best protection value, you should keep Microsoft Defender Antivirus up to date.</span></span> <span data-ttu-id="b8997-176">請參閱[管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="b8997-176">See [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> 

### <a name="why-do-we-need-cloud-protection-on"></a><span data-ttu-id="b8997-177">我們為何需要雲端保護開啟？</span><span class="sxs-lookup"><span data-stu-id="b8997-177">Why do we need cloud protection on?</span></span> 

<span data-ttu-id="b8997-178">需要 Cloud protection 才能開啟裝置上的功能。</span><span class="sxs-lookup"><span data-stu-id="b8997-178">Cloud protection is needed to turn on the feature on the device.</span></span> <span data-ttu-id="b8997-179">雲端防護功能可讓 [Defender For Endpoint](microsoft-defender-endpoint.md) ，根據我們的廣泛和深度安全性情報，以及行為和裝置教學模型，提供最新和最佳的保護。</span><span class="sxs-lookup"><span data-stu-id="b8997-179">Cloud protection allows [Defender for Endpoint](microsoft-defender-endpoint.md) to deliver the latest and greatest protection based on our breadth and depth of security intelligence, along with behavioral and device learning models.</span></span>

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="b8997-180">如何將 Microsoft Defender 防毒軟體設定為被動模式？</span><span class="sxs-lookup"><span data-stu-id="b8997-180">How do I set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="b8997-181">根據作業系統，當執行非 Microsoft 防毒軟體/反惡意程式碼的裝置架至 Defender for Endpoint 時，Microsoft Defender 防毒軟體可以自動進入被動模式。</span><span class="sxs-lookup"><span data-stu-id="b8997-181">Depending on operating systems, when devices that are running a non-Microsoft antivirus/antimalware solution are onboarded to Defender for Endpoint, Microsoft Defender Antivirus can go into passive mode automatically.</span></span> <span data-ttu-id="b8997-182">如需詳細資訊，請參閱 how [Microsoft Defender 防毒軟體如何影響 Defender for Endpoint 功能](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality)。</span><span class="sxs-lookup"><span data-stu-id="b8997-182">For more information, see [How Microsoft Defender Antivirus affects Defender for Endpoint functionality](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality).</span></span> 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a><span data-ttu-id="b8997-183">如何確認 Microsoft Defender 防毒軟體處於主動或被動模式？</span><span class="sxs-lookup"><span data-stu-id="b8997-183">How do I confirm Microsoft Defender Antivirus is in active or passive mode?</span></span>

<span data-ttu-id="b8997-184">若要確認 Microsoft Defender 防毒軟體是否以主動或被動模式執行，您可以在執行 Windows 的裝置上使用命令提示字元或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b8997-184">To confirm whether Microsoft Defender Antivirus is running in active or passive mode, you can use Command Prompt or PowerShell on a device running Windows.</span></span>


|<span data-ttu-id="b8997-185">方法</span><span class="sxs-lookup"><span data-stu-id="b8997-185">Method</span></span>  |<span data-ttu-id="b8997-186">程序</span><span class="sxs-lookup"><span data-stu-id="b8997-186">Procedure</span></span>  |
|---------|---------|
| <span data-ttu-id="b8997-187">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8997-187">PowerShell</span></span>     | <span data-ttu-id="b8997-188">1. 選取 [[開始] 功能表]，開始輸入 `PowerShell` ，然後在結果中開啟 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b8997-188">1. Select the Start menu, begin typing `PowerShell`, and then open Windows PowerShell in the results.</span></span> <p><span data-ttu-id="b8997-189">2. 輸入 `Get-MpComputerStatus` 。</span><span class="sxs-lookup"><span data-stu-id="b8997-189">2. Type `Get-MpComputerStatus`.</span></span> <p><span data-ttu-id="b8997-190">3. 在結果清單中的 [ **AMRunningMode** ] 列中，尋找下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="b8997-190">3. In the list of results, in the **AMRunningMode** row, look for one of the following values:</span></span> <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p><span data-ttu-id="b8997-191">若要深入瞭解，請參閱 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。</span><span class="sxs-lookup"><span data-stu-id="b8997-191">To learn more, see [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).</span></span>        |
|<span data-ttu-id="b8997-192">命令提示字元</span><span class="sxs-lookup"><span data-stu-id="b8997-192">Command Prompt</span></span>     | <span data-ttu-id="b8997-193">1. 選取 [開始] 功能表，開始輸入 `Command Prompt` ，然後在結果中開啟 Windows 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="b8997-193">1. Select the Start menu, begin typing `Command Prompt`, and then open Windows Command Prompt in the results.</span></span> <p><span data-ttu-id="b8997-194">2. 輸入 `sc query windefend` 。</span><span class="sxs-lookup"><span data-stu-id="b8997-194">2. Type `sc query windefend`.</span></span> <p><span data-ttu-id="b8997-195">3. 在結果清單中的 [ **狀態** ] 列中，確認服務正在執行中。</span><span class="sxs-lookup"><span data-stu-id="b8997-195">3. In the list of results, in the **STATE** row, confirm that the service is running.</span></span>         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a><span data-ttu-id="b8997-196">停用封鎖模式中的 EDR 需要多少時間？</span><span class="sxs-lookup"><span data-stu-id="b8997-196">How much time does it take for EDR in block mode to be disabled?</span></span>

<span data-ttu-id="b8997-197">如果您選擇以封鎖模式停用 EDR，最多可能需要30分鐘的時間，系統才會停用此功能。</span><span class="sxs-lookup"><span data-stu-id="b8997-197">If you chose to disable EDR in block mode, it can take up to 30 minutes for the system to disable this capability.</span></span>

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a><span data-ttu-id="b8997-198">在 Windows Server 2016 上支援的封鎖模式中 EDR 嗎？</span><span class="sxs-lookup"><span data-stu-id="b8997-198">Is EDR in block mode supported on Windows Server 2016?</span></span>

<span data-ttu-id="b8997-199">如果 Microsoft Defender 防毒軟體以主動模式或被動模式執行，則下列 Windows 版本都支援 EDR in 封鎖模式：</span><span class="sxs-lookup"><span data-stu-id="b8997-199">If Microsoft Defender Antivirus is running in active mode or passive mode, EDR in block mode is supported of the following versions of Windows:</span></span>

- <span data-ttu-id="b8997-200">所有版本 Windows 10 () </span><span class="sxs-lookup"><span data-stu-id="b8997-200">Windows 10 (all releases)</span></span>
- <span data-ttu-id="b8997-201">Windows伺服器、版本1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="b8997-201">Windows Server, version 1803 or newer</span></span> 
- <span data-ttu-id="b8997-202">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="b8997-202">Windows Server 2019</span></span> 

<span data-ttu-id="b8997-203">如果 Windows Server 2016 以主動模式執行 Microsoft Defender 防毒軟體，且端點架至 Defender for endpoint，則會以技術支援的封鎖模式 EDR。</span><span class="sxs-lookup"><span data-stu-id="b8997-203">If Windows Server 2016 has Microsoft Defender Antivirus running in active mode, and the endpoint is onboarded to Defender for Endpoint, then EDR in block mode is technically supported.</span></span> <span data-ttu-id="b8997-204">不過，當 Microsoft Defender 防毒軟體不是端點上的主要防病毒方案時，在封鎖模式中 EDR 應是額外的保護。</span><span class="sxs-lookup"><span data-stu-id="b8997-204">However, EDR in block mode is intended to be extra protection when Microsoft Defender Antivirus is not the primary antivirus solution on an endpoint.</span></span> <span data-ttu-id="b8997-205">在這種情況下，Microsoft Defender 防毒軟體會以被動模式執行。</span><span class="sxs-lookup"><span data-stu-id="b8997-205">In those cases, Microsoft Defender Antivirus runs in passive mode.</span></span> <span data-ttu-id="b8997-206">目前，Windows Server 2016 上不支援以被動模式執行 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="b8997-206">Currently, running Microsoft Defender Antivirus in passive mode is not supported on Windows Server 2016.</span></span> <span data-ttu-id="b8997-207">若要深入瞭解，請參閱[Microsoft Defender 防毒軟體和非 Microsoft 防毒軟體/反惡意程式碼解決方案](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)。</span><span class="sxs-lookup"><span data-stu-id="b8997-207">To learn more, see [Microsoft Defender Antivirus and non-Microsoft antivirus/antimalware solutions](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8997-208">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b8997-208">See also</span></span>

- [<span data-ttu-id="b8997-209">技術 Community 博客：在封鎖模式中引入 EDR：在其蹤跡中停止攻擊</span><span class="sxs-lookup"><span data-stu-id="b8997-209">Tech Community blog: Introducing EDR in block mode: Stopping attacks in their tracks</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [<span data-ttu-id="b8997-210">行為封鎖和包含專案</span><span class="sxs-lookup"><span data-stu-id="b8997-210">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

