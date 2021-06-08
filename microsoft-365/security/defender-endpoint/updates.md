---
title: 管理 Microsoft Defender 更新的逐步展示過程
description: 深入瞭解逐步更新程式和控制項
keywords: 更新、更新程式、控制項、版本
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f5db08e4eb98dd3fe6f7e8a84fb0c49e889fb73f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809249"
---
#  <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a><span data-ttu-id="430ab-104">管理 Microsoft Defender 更新的逐步展示過程</span><span class="sxs-lookup"><span data-stu-id="430ab-104">Manage the gradual rollout process for Microsoft Defender updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="430ab-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="430ab-105">**Applies to:**</span></span>

- [<span data-ttu-id="430ab-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="430ab-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="430ab-107">務必確保用戶端元件是最新的，以提供重要的保護功能並防止受到攻擊。</span><span class="sxs-lookup"><span data-stu-id="430ab-107">It is important to ensure that client components are up-to-date to deliver critical protection capabilities and prevent attacks.</span></span>

<span data-ttu-id="430ab-108">功能是透過數個元件提供：</span><span class="sxs-lookup"><span data-stu-id="430ab-108">Capabilities are provided through several components:</span></span> 

- [<span data-ttu-id="430ab-109">& 回應的端點偵測</span><span class="sxs-lookup"><span data-stu-id="430ab-109">Endpoint Detection & Response</span></span>](overview-endpoint-detection-response.md) 
- <span data-ttu-id="430ab-110">使用[雲端傳送保護](cloud-protection-microsoft-defender-antivirus.md)的[下一代保護](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection)</span><span class="sxs-lookup"><span data-stu-id="430ab-110">[Next-generation protection](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md)</span></span> 
- [<span data-ttu-id="430ab-111">攻擊面減少</span><span class="sxs-lookup"><span data-stu-id="430ab-111">Attack Surface Reduction</span></span>](overview-attack-surface-reduction.md)

<span data-ttu-id="430ab-112">使用逐步發行處理常式每月發行一次更新。</span><span class="sxs-lookup"><span data-stu-id="430ab-112">Updates are released monthly using a gradual release process.</span></span> <span data-ttu-id="430ab-113">此程式可協助您啟用早期的失敗偵測，以在發生影響時立即取得影響，並在較大的首展之前快速處理。</span><span class="sxs-lookup"><span data-stu-id="430ab-113">This process helps to enable early failure detection to catch impact as it occurs and address it quickly before a larger rollout.</span></span> 

> [!NOTE]
> <span data-ttu-id="430ab-114">如需如何控制每日定義更新的詳細資訊，請參閱[排程 Microsoft Defender 防毒軟體定義更新-Windows 安全性 |Microsoft](manage-protection-update-schedule-microsoft-defender-antivirus.md)檔。定義更新可確保下一代保護可以防禦新的威脅，即使無法使用雲端提供的保護也是一樣。</span><span class="sxs-lookup"><span data-stu-id="430ab-114">For more information on how to control daily definition updates, see [Schedule Microsoft Defender Antivirus definition updates - Windows security | Microsoft Docs](manage-protection-update-schedule-microsoft-defender-antivirus.md). Definition updates ensure that next-generation protection can defend against new threats, even if cloud-delivered protection is not available to the endpoint.</span></span>

## <a name="microsoft-gradual-rollout-model"></a><span data-ttu-id="430ab-115">Microsoft 逐步推廣模型</span><span class="sxs-lookup"><span data-stu-id="430ab-115">Microsoft gradual rollout model</span></span>

<span data-ttu-id="430ab-116">下列逐步展模型遵循下列專案：</span><span class="sxs-lookup"><span data-stu-id="430ab-116">The following gradual rollout model is followed:</span></span>

1. <span data-ttu-id="430ab-117">第一個版本會發佈到 Beta 通道訂閱者。</span><span class="sxs-lookup"><span data-stu-id="430ab-117">The first release goes out to Beta channel subscribers.</span></span>
2. <span data-ttu-id="430ab-118">在驗證、意見反應和修正程式之後，我們會以節流的方式開始逐步展示處理常式，並先預覽通道訂閱者。</span><span class="sxs-lookup"><span data-stu-id="430ab-118">After validation, feedback, and fixes, we start the gradual rollout process in a throttled way and to Preview channel subscribers first.</span></span>
3. <span data-ttu-id="430ab-119">接著，我們會繼續發行更新 ato，以從10-100% 向內擴充。</span><span class="sxs-lookup"><span data-stu-id="430ab-119">We then proceed to release the update ato the rest of the global population, scaling out from 10-100%.</span></span>

<span data-ttu-id="430ab-120">我們的工程師會持續監控影響並上報任何問題，以視需要建立修正。</span><span class="sxs-lookup"><span data-stu-id="430ab-120">Our engineers continuously monitor impact and escalate any issues to create a fix as needed.</span></span>

## <a name="how-to-customize-your-internal-deployment-process"></a><span data-ttu-id="430ab-121">如何自訂您的內部部署程式</span><span class="sxs-lookup"><span data-stu-id="430ab-121">How to customize your internal deployment process</span></span>

<span data-ttu-id="430ab-122">如果您的機器從 Windows 更新接收到 defender 更新，逐步推廣程式可能會導致某些您的電腦以較早的速度接收 defender 更新。</span><span class="sxs-lookup"><span data-stu-id="430ab-122">If your machines are receiving Defender updates from Windows Update, the gradual rollout process may result in some of your machines receiving Defender updates sooner than others.</span></span> <span data-ttu-id="430ab-123">下一節將說明如何透過利用更新通道設定，定義允許自動更新流向不同于特定裝置群組的策略。</span><span class="sxs-lookup"><span data-stu-id="430ab-123">The following section explains how to define a strategy that will allow automatic updates to flow differently to specific groups of devices by leveraging update channel configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="430ab-124">在規劃您自己的逐步發行時，請務必確定已訂閱預覽及分段通道的裝置的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="430ab-124">When planning for your own gradual release, please make sure to always have a selection of devices subscribed to the preview and staged channels.</span></span> <span data-ttu-id="430ab-125">這將為您的組織和 Microsoft 提供機會，以防止或找出並修正您環境特有的問題。</span><span class="sxs-lookup"><span data-stu-id="430ab-125">This will provide your organization as well as Microsoft the opportunity to prevent or find and fix issues specific to your environment.</span></span>

<span data-ttu-id="430ab-126">例如，針對接收更新的電腦，Windows Server Update Services (WSUS) 或 Microsoft Endpoint Configuration Manager (MECM) ，所有 Windows 更新都會提供更多選項，包括 Microsoft Defender for Endpoint 的選項。</span><span class="sxs-lookup"><span data-stu-id="430ab-126">For machines receiving updates through, for example, Windows Server Update Services (WSUS) or Microsoft Endpoint Configuration Manager (MECM), more options are available to all Windows updates, including options  for Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="430ab-127">深入瞭解如何使用 WSUS （如 WSUS） MECM，以管理[管理 Microsoft Defender 防毒軟體更新及套用基準 Windows 安全性 | 的更新的發佈和應用程式。Microsoft](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates)檔。</span><span class="sxs-lookup"><span data-stu-id="430ab-127">Read more about how to use a solution like WSUS, MECM to manage the distribution and application of updates at [Manage Microsoft Defender Antivirus updates and apply baselines - Windows security | Microsoft Docs](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).</span></span>

## <a name="update-channels-for-monthly-updates"></a><span data-ttu-id="430ab-128">更新每月更新的通道</span><span class="sxs-lookup"><span data-stu-id="430ab-128">Update channels for monthly updates</span></span>

<span data-ttu-id="430ab-129">您可以將機器指派至更新通道，以定義機器接收每月引擎和平臺更新的節奏。</span><span class="sxs-lookup"><span data-stu-id="430ab-129">You can assign a machine to an update channel to define the cadence in which a machine receives monthly engine and platform updates.</span></span>

<span data-ttu-id="430ab-130">如需如何設定更新的詳細資訊，請參閱 [建立 Microsoft Defender 更新的自訂逐步展處理](configure-updates.md)程式。</span><span class="sxs-lookup"><span data-stu-id="430ab-130">For more information on how to configure updates, see [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).</span></span>

<span data-ttu-id="430ab-131">下列更新通道可供使用：</span><span class="sxs-lookup"><span data-stu-id="430ab-131">The following update channels are available:</span></span>

| <span data-ttu-id="430ab-132">通道名稱</span><span class="sxs-lookup"><span data-stu-id="430ab-132">Channel name</span></span>  | <span data-ttu-id="430ab-133">描述</span><span class="sxs-lookup"><span data-stu-id="430ab-133">Description</span></span>  | <span data-ttu-id="430ab-134">應用程式</span><span class="sxs-lookup"><span data-stu-id="430ab-134">Application</span></span>  |
|-|-|-|
| <span data-ttu-id="430ab-135">Beta 通道-預發行</span><span class="sxs-lookup"><span data-stu-id="430ab-135">Beta Channel - Prerelease</span></span>  | <span data-ttu-id="430ab-136">測試其他人之前的更新</span><span class="sxs-lookup"><span data-stu-id="430ab-136">Test updates before others</span></span>  | <span data-ttu-id="430ab-137">設定為此通道的裝置將是第一個接收新的每月更新的裝置。</span><span class="sxs-lookup"><span data-stu-id="430ab-137">Devices set to this channel will be the first to receive new monthly updates.</span></span> <span data-ttu-id="430ab-138">選取 [Beta 通道]，以參與識別及報告 Microsoft 的問題。</span><span class="sxs-lookup"><span data-stu-id="430ab-138">Select Beta Channel to participate in identifying and reporting issues to Microsoft.</span></span> <span data-ttu-id="430ab-139">預設會為此通道訂閱 Windows 有問必答方案中的裝置。</span><span class="sxs-lookup"><span data-stu-id="430ab-139">Devices in the Windows Insider Program are subscribed to this channel by default.</span></span> <span data-ttu-id="430ab-140">僅供測試環境使用。</span><span class="sxs-lookup"><span data-stu-id="430ab-140">For use in test environments only.</span></span>  |
| <span data-ttu-id="430ab-141">目前通道 (預覽)</span><span class="sxs-lookup"><span data-stu-id="430ab-141">Current Channel (Preview)</span></span>  | <span data-ttu-id="430ab-142">在逐步發行過程中， **早先** 取得目前的通道更新</span><span class="sxs-lookup"><span data-stu-id="430ab-142">Get Current Channel updates **earlier** during gradual release</span></span>  | <span data-ttu-id="430ab-143">設定為此通道的裝置會在逐步發行週期中儘早提供更新。</span><span class="sxs-lookup"><span data-stu-id="430ab-143">Devices set to this channel will be offered updates earliest during the gradual release cycle.</span></span> <span data-ttu-id="430ab-144">建議用於預先生產/驗證環境。</span><span class="sxs-lookup"><span data-stu-id="430ab-144">Suggested for pre-production/validation environments.</span></span>  |
| <span data-ttu-id="430ab-145"> (分段) 的目前通道</span><span class="sxs-lookup"><span data-stu-id="430ab-145">Current Channel (Staged)</span></span>  | <span data-ttu-id="430ab-146">稍後逐步發行時取得目前的頻道更新</span><span class="sxs-lookup"><span data-stu-id="430ab-146">Get Current Channel updates later during gradual release</span></span>  | <span data-ttu-id="430ab-147">在逐步發行週期中，裝置會在稍後提供更新。</span><span class="sxs-lookup"><span data-stu-id="430ab-147">Devices will be offered updates later during the gradual release cycle.</span></span> <span data-ttu-id="430ab-148">建議套用至您的裝置人口的小型代表性部分 (~ 10% ) 。</span><span class="sxs-lookup"><span data-stu-id="430ab-148">Suggested to apply to a small, representative part of your device population (~10%).</span></span>  |
| <span data-ttu-id="430ab-149">目前通道 (廣泛) </span><span class="sxs-lookup"><span data-stu-id="430ab-149">Current Channel (Broad)</span></span> | <span data-ttu-id="430ab-150">在逐步發行結束時取得更新</span><span class="sxs-lookup"><span data-stu-id="430ab-150">Get updates at the end of gradual release</span></span>  | <span data-ttu-id="430ab-151">只有在逐步發行週期完成之後，才會將更新提供給裝置。</span><span class="sxs-lookup"><span data-stu-id="430ab-151">Devices will be offered updates only after the gradual release cycle completes.</span></span> <span data-ttu-id="430ab-152">建議套用至實際執行填充 (~ 10-100% ) 中的一組廣泛裝置。</span><span class="sxs-lookup"><span data-stu-id="430ab-152">Suggested to apply to a broad set of devices in your production population (~10-100%).</span></span>  |
| <span data-ttu-id="430ab-153"> (預設) </span><span class="sxs-lookup"><span data-stu-id="430ab-153">(default)</span></span>  |   | <span data-ttu-id="430ab-154">如果您停用或未設定此原則，裝置將會保留在目前通道中 (預設) ：在逐步發行週期內，會自動維持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="430ab-154">If you disable or do not configure this policy, the device will remain in Current Channel (Default): Stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="430ab-155">適用于大部分裝置。</span><span class="sxs-lookup"><span data-stu-id="430ab-155">Suitable for most devices.</span></span>  |

### <a name="update-channels-for-daily-definition-updates"></a><span data-ttu-id="430ab-156">更新每日定義更新的通道</span><span class="sxs-lookup"><span data-stu-id="430ab-156">Update channels for daily definition updates</span></span>

<span data-ttu-id="430ab-157">您可以將機器指派至更新通道，以定義機器接收每日定義更新的節奏。</span><span class="sxs-lookup"><span data-stu-id="430ab-157">You can assign a machine to an update channel to define the cadence in which a machine receives daily definition updates.</span></span>
  
| <span data-ttu-id="430ab-158">通道名稱</span><span class="sxs-lookup"><span data-stu-id="430ab-158">Channel name</span></span>  | <span data-ttu-id="430ab-159">描述</span><span class="sxs-lookup"><span data-stu-id="430ab-159">Description</span></span>  | <span data-ttu-id="430ab-160">應用程式</span><span class="sxs-lookup"><span data-stu-id="430ab-160">Application</span></span>  |
|-|-|-|
| <span data-ttu-id="430ab-161"> (分段) 的目前通道</span><span class="sxs-lookup"><span data-stu-id="430ab-161">Current Channel (Staged)</span></span>  | <span data-ttu-id="430ab-162">稍後逐步發行時取得目前的頻道更新</span><span class="sxs-lookup"><span data-stu-id="430ab-162">Get Current Channel updates later during gradual release</span></span>  | <span data-ttu-id="430ab-163">在逐步發行週期中，裝置會在稍後提供更新。</span><span class="sxs-lookup"><span data-stu-id="430ab-163">Devices will be offered updates later during the gradual release cycle.</span></span> <span data-ttu-id="430ab-164">建議套用至您的裝置人口的小型代表性部分 (~ 10% ) 。</span><span class="sxs-lookup"><span data-stu-id="430ab-164">Suggested to apply to a small, representative part of your device population (~10%).</span></span>  |
| <span data-ttu-id="430ab-165">目前通道 (廣泛) </span><span class="sxs-lookup"><span data-stu-id="430ab-165">Current Channel (Broad)</span></span> | <span data-ttu-id="430ab-166">在逐步發行結束時取得更新</span><span class="sxs-lookup"><span data-stu-id="430ab-166">Get updates at the end of gradual release</span></span>  | <span data-ttu-id="430ab-167">在逐步發行週期過後，裝置將會提供更新。</span><span class="sxs-lookup"><span data-stu-id="430ab-167">Devices will be offered updates after the gradual release cycle.</span></span> <span data-ttu-id="430ab-168">適用于僅接收有限更新的資料中心電腦。</span><span class="sxs-lookup"><span data-stu-id="430ab-168">Best for datacenter machines that only receive limited updates.</span></span> <span data-ttu-id="430ab-169">注意：此設定會套用至所有的 Defender 更新。</span><span class="sxs-lookup"><span data-stu-id="430ab-169">Note: this setting applies to all Defender updates.</span></span>  |
| <span data-ttu-id="430ab-170"> (預設) </span><span class="sxs-lookup"><span data-stu-id="430ab-170">(default)</span></span>  |   | <span data-ttu-id="430ab-171">如果您停用或未設定此原則，裝置將會保留在目前通道中 (預設) ：在逐步發行週期內，會自動維持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="430ab-171">If you disable or do not configure this policy, the device will remain in Current Channel (Default): Stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="430ab-172">適用于大部分裝置</span><span class="sxs-lookup"><span data-stu-id="430ab-172">Suitable for most devices</span></span>  |

> [!NOTE]
> <span data-ttu-id="430ab-173">如果您想要強制更新為最新的簽章，而不是利用時間延遲，您必須先移除此原則。</span><span class="sxs-lookup"><span data-stu-id="430ab-173">In case you wish to force an update to the newest signature instead of leveraging the time delay, you will need to remove this policy first.</span></span>

## <a name="update-guidance"></a><span data-ttu-id="430ab-174">更新指導</span><span class="sxs-lookup"><span data-stu-id="430ab-174">Update guidance</span></span>

<span data-ttu-id="430ab-175">在大多數情況下，使用 Windows 更新時，建議的設定是允許端點接收並套用每月的 Defender 更新。</span><span class="sxs-lookup"><span data-stu-id="430ab-175">In most cases, the recommended configuration when using Windows Update is to allow endpoints to receive and apply monthly Defender updates as they arrive.</span></span> <span data-ttu-id="430ab-176">這可讓您在保護與可能會帶來的變更相關聯時，獲得最佳的平衡。</span><span class="sxs-lookup"><span data-stu-id="430ab-176">This provides the best balance between protection and possible impact associated with the changes they can introduce.</span></span>

<span data-ttu-id="430ab-177">針對可能需要更多控制自動 Defender 更新的逐漸推廣的環境，請考慮使用部署群組的方法：</span><span class="sxs-lookup"><span data-stu-id="430ab-177">For environments where there is a need for a more controlled gradual rollout of automatic Defender updates, consider an approach with deployment groups:</span></span>

1. <span data-ttu-id="430ab-178">參與 Windows 的內幕程式，或將裝置的群組指派給 Beta 通道。</span><span class="sxs-lookup"><span data-stu-id="430ab-178">Participate in the Windows Insider program or assign a group of devices to the Beta Channel.</span></span>
2. <span data-ttu-id="430ab-179">指定示範群組以預覽通道（通常是驗證環境），以及早接收新的更新。</span><span class="sxs-lookup"><span data-stu-id="430ab-179">Designate a pilot group that opts-in to Preview Channel, typically validation environments, to receive new updates early.</span></span>
3. <span data-ttu-id="430ab-180">指定一組機器，以從分段通道逐步進行逐步的首次開始時接收更新。</span><span class="sxs-lookup"><span data-stu-id="430ab-180">Designate a group of machines that receive updates later during the gradual rollout from Staged channel.</span></span> <span data-ttu-id="430ab-181">這通常是代表大約10% 的人口。</span><span class="sxs-lookup"><span data-stu-id="430ab-181">Typically, this would be a representative ~10% of the population.</span></span>
4. <span data-ttu-id="430ab-182">指定在逐步發行週期完成後接收更新的機器群組。</span><span class="sxs-lookup"><span data-stu-id="430ab-182">Designate a group of machines that receive updates after the gradual release cycle completes.</span></span> <span data-ttu-id="430ab-183">這通常是非常重要的實際執行系統。</span><span class="sxs-lookup"><span data-stu-id="430ab-183">These are typically important production systems.</span></span>

<span data-ttu-id="430ab-184">在其他裝置中，預設設定是在 Microsoft 逐步推廣過程中收到新的更新，而且不需要進行進一步的設定。</span><span class="sxs-lookup"><span data-stu-id="430ab-184">For the remainder of devices, the default setting is to receive new updates as they arrive during the Microsoft gradual rollout process and no further configuration is required.</span></span> 

<span data-ttu-id="430ab-185">採用此模型：</span><span class="sxs-lookup"><span data-stu-id="430ab-185">Adopting this model:</span></span>
- <span data-ttu-id="430ab-186">可讓您在發佈至實際執行環境之前測試早期版本</span><span class="sxs-lookup"><span data-stu-id="430ab-186">Allows you to test early releases before they reach a production environment</span></span> 
- <span data-ttu-id="430ab-187">確定生產環境仍會收到定期更新，並確保針對重大威脅進行防護。</span><span class="sxs-lookup"><span data-stu-id="430ab-187">Ensure the production environment still receives regular updates and ensure protection against critical threats.</span></span>

## <a name="management-tools"></a><span data-ttu-id="430ab-188">管理工具</span><span class="sxs-lookup"><span data-stu-id="430ab-188">Management tools</span></span>
<span data-ttu-id="430ab-189">若要建立您自己的自訂逐步產生過程以進行每月更新，您可以使用下列工具：</span><span class="sxs-lookup"><span data-stu-id="430ab-189">To create your own custom gradual rollout process for monthly updates, you can use the following tools:</span></span>

- <span data-ttu-id="430ab-190">群組原則</span><span class="sxs-lookup"><span data-stu-id="430ab-190">Group policy</span></span>
- <span data-ttu-id="430ab-191">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="430ab-191">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="430ab-192">PowerShell</span><span class="sxs-lookup"><span data-stu-id="430ab-192">PowerShell</span></span>

<span data-ttu-id="430ab-193">如需如何使用這些工具的詳細資訊，請參閱 [建立 Microsoft Defender 更新的自訂逐步展處理](configure-updates.md)程式。</span><span class="sxs-lookup"><span data-stu-id="430ab-193">For details on how to use these tools, see [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).</span></span>
