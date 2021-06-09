---
title: 建立 Microsoft Defender 更新的自訂逐步展示過程
description: 瞭解如何使用支援的工具來建立自訂的漸進式產生過程以進行更新
keywords: 更新工具、gpo、intune、mdm、microsoft 端點管理員、原則、powershell
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
ms.openlocfilehash: 26695df0e34c0e06adc4f58acf3fea83122c1982
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844475"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a><span data-ttu-id="8efc6-104">建立 Microsoft Defender 更新的自訂逐步展示過程</span><span class="sxs-lookup"><span data-stu-id="8efc6-104">Create a custom gradual rollout process for Microsoft Defender updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8efc6-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8efc6-105">**Applies to:**</span></span>

- [<span data-ttu-id="8efc6-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8efc6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="8efc6-107">這種功能需要 Microsoft Defender 防毒軟體版本4.18.2105 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="8efc6-107">This functionality requires Microsoft Defender Antivirus version 4.18.2105.X or newer.</span></span>

<span data-ttu-id="8efc6-108">若要建立您自己的用於 Defender 更新的自訂逐步推廣過程，您可以使用群組原則、Microsoft 端點管理員和 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8efc6-108">To create your own custom gradual rollout process for Defender updates, you can use Group Policy, Microsoft Endpoint Manager, and PowerShell.</span></span>

<span data-ttu-id="8efc6-109">下表列出可用來設定更新通道的群組原則設定：</span><span class="sxs-lookup"><span data-stu-id="8efc6-109">The following table lists the available group policy settings for configuring update channels:</span></span>

| <span data-ttu-id="8efc6-110">設定標題</span><span class="sxs-lookup"><span data-stu-id="8efc6-110">Setting title</span></span>  | <span data-ttu-id="8efc6-111">描述</span><span class="sxs-lookup"><span data-stu-id="8efc6-111">Description</span></span>  | <span data-ttu-id="8efc6-112">位置</span><span class="sxs-lookup"><span data-stu-id="8efc6-112">Location</span></span>  |
|-|-|-|
| <span data-ttu-id="8efc6-113">選取逐步 Microsoft Defender 每月平臺更新部署通道</span><span class="sxs-lookup"><span data-stu-id="8efc6-113">Select gradual Microsoft Defender monthly platform update rollout channel</span></span>  | <span data-ttu-id="8efc6-114">啟用此原則，以指定裝置每月逐步部署期間何時接收 Microsoft Defender 平臺更新。</span><span class="sxs-lookup"><span data-stu-id="8efc6-114">Enable this policy to specify when devices receive Microsoft Defender platform updates during the monthly gradual rollout.</span></span> <span data-ttu-id="8efc6-115">Beta 通道：設定成此通道的裝置會是第一個接收新更新的裝置。</span><span class="sxs-lookup"><span data-stu-id="8efc6-115">Beta Channel: Devices set to this channel will be the first to receive new updates.</span></span> <span data-ttu-id="8efc6-116">選取 [Beta 通道]，以參與識別及報告 Microsoft 的問題。</span><span class="sxs-lookup"><span data-stu-id="8efc6-116">Select Beta Channel to participate in identifying and reporting issues to Microsoft.</span></span> <span data-ttu-id="8efc6-117">預設會為此通道訂閱 Windows 有問必答方案中的裝置。</span><span class="sxs-lookup"><span data-stu-id="8efc6-117">Devices in the Windows Insider Program are subscribed to this channel by default.</span></span> <span data-ttu-id="8efc6-118">僅供 (手動) 測試環境和有限數目的裝置使用。</span><span class="sxs-lookup"><span data-stu-id="8efc6-118">For use in (manual) test environments only and a limited number of devices.</span></span>  <br><br>  <span data-ttu-id="8efc6-119">目前通道 (預覽) ：設定成此通道的裝置會在每月逐步發佈週期中，儘早提供更新。</span><span class="sxs-lookup"><span data-stu-id="8efc6-119">Current Channel (Preview): Devices set to this channel will be offered updates earliest during the monthly gradual release cycle.</span></span> <span data-ttu-id="8efc6-120">建議用於預先生產/驗證環境。</span><span class="sxs-lookup"><span data-stu-id="8efc6-120">Suggested for pre-production/validation environments.</span></span>  <br><br>  <span data-ttu-id="8efc6-121">目前通道 (分段) ：在每月逐步發行週期後，將會提供裝置更新。</span><span class="sxs-lookup"><span data-stu-id="8efc6-121">Current Channel (Staged): Devices will be offered updates after the monthly gradual release cycle.</span></span> <span data-ttu-id="8efc6-122">建議套用至實際生產環境中的小型、代表性部分 (~ 10% ) 。</span><span class="sxs-lookup"><span data-stu-id="8efc6-122">Suggested to apply to a small, representative part of your production population (~10%).</span></span>  <br><br>  <span data-ttu-id="8efc6-123">目前通道 (多種) ：只有逐步發行週期完成之後，才會提供裝置更新。</span><span class="sxs-lookup"><span data-stu-id="8efc6-123">Current Channel (Broad): Devices will be offered updates only after the gradual release cycle completes.</span></span> <span data-ttu-id="8efc6-124">建議套用至實際執行填充 (~ 10-100% ) 中的一組廣泛裝置。</span><span class="sxs-lookup"><span data-stu-id="8efc6-124">Suggested to apply to a broad set of devices in your production population (~10-100%).</span></span>  <br><br>   <span data-ttu-id="8efc6-125">如果您停用或未設定此原則，裝置會在逐步發行週期中自動維持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="8efc6-125">If you disable or do not configure this policy, the device will stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="8efc6-126">適用于大部分裝置。</span><span class="sxs-lookup"><span data-stu-id="8efc6-126">Suitable for most devices.</span></span>  | <span data-ttu-id="8efc6-127">Windows元件 \ Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="8efc6-127">Windows Components\Microsoft Defender Antivirus</span></span>  |
| <span data-ttu-id="8efc6-128">選取逐步 Microsoft Defender 每月引擎更新部署通道</span><span class="sxs-lookup"><span data-stu-id="8efc6-128">Select gradual Microsoft Defender monthly engine update rollout channel</span></span>  | <span data-ttu-id="8efc6-129">啟用此原則，以指定裝置每月逐步部署期間何時接收 Microsoft Defender 引擎更新。</span><span class="sxs-lookup"><span data-stu-id="8efc6-129">Enable this policy to specify when devices receive Microsoft Defender engine updates during the monthly gradual rollout.</span></span>  <br><br>  <span data-ttu-id="8efc6-130">Beta 通道：設定成此通道的裝置會是第一個接收新更新的裝置。</span><span class="sxs-lookup"><span data-stu-id="8efc6-130">Beta Channel: Devices set to this channel will be the first to receive new updates.</span></span> <span data-ttu-id="8efc6-131">選取 [Beta 通道]，以參與識別及報告 Microsoft 的問題。</span><span class="sxs-lookup"><span data-stu-id="8efc6-131">Select Beta Channel to participate in identifying and reporting issues to Microsoft.</span></span> <span data-ttu-id="8efc6-132">預設會為此通道訂閱 Windows 有問必答方案中的裝置。</span><span class="sxs-lookup"><span data-stu-id="8efc6-132">Devices in the Windows Insider Program are subscribed to this channel by default.</span></span> <span data-ttu-id="8efc6-133">僅供 (手動) 測試環境和有限數目的裝置使用。</span><span class="sxs-lookup"><span data-stu-id="8efc6-133">For use in (manual) test environments only and a limited number of devices.</span></span>  <br><br>  <span data-ttu-id="8efc6-134">目前通道 (預覽) ：設定成此通道的裝置會在每月逐步發佈週期中，儘早提供更新。</span><span class="sxs-lookup"><span data-stu-id="8efc6-134">Current Channel (Preview): Devices set to this channel will be offered updates earliest during the monthly gradual release cycle.</span></span> <span data-ttu-id="8efc6-135">建議用於預先生產/驗證環境。</span><span class="sxs-lookup"><span data-stu-id="8efc6-135">Suggested for pre-production/validation environments.</span></span>  <br><br>  <span data-ttu-id="8efc6-136">目前通道 (分段) ：在每月逐步發行週期後，將會提供裝置更新。</span><span class="sxs-lookup"><span data-stu-id="8efc6-136">Current Channel (Staged): Devices will be offered updates after the monthly gradual release cycle.</span></span> <span data-ttu-id="8efc6-137">建議套用至實際生產環境中的小型、代表性部分 (~ 10% ) 。</span><span class="sxs-lookup"><span data-stu-id="8efc6-137">Suggested to apply to a small, representative part of your production population (~10%).</span></span>  <br><br>  <span data-ttu-id="8efc6-138">目前通道 (多種) ：只有逐步發行週期完成之後，才會提供裝置更新。</span><span class="sxs-lookup"><span data-stu-id="8efc6-138">Current Channel (Broad): Devices will be offered updates only after the gradual release cycle completes.</span></span> <span data-ttu-id="8efc6-139">建議套用至實際執行填充 (~ 10-100% ) 中的一組廣泛裝置。</span><span class="sxs-lookup"><span data-stu-id="8efc6-139">Suggested to apply to a broad set of devices in your production population (~10-100%).</span></span>  <br><br>  <span data-ttu-id="8efc6-140">如果您停用或未設定此原則，裝置會在逐步發行週期中自動維持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="8efc6-140">If you disable or do not configure this policy, the device will stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="8efc6-141">適用于大部分裝置。</span><span class="sxs-lookup"><span data-stu-id="8efc6-141">Suitable for most devices.</span></span>  | <span data-ttu-id="8efc6-142">Windows元件 \ Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="8efc6-142">Windows Components\Microsoft Defender Antivirus</span></span>  |
| <span data-ttu-id="8efc6-143">選取逐步式 Microsoft Defender 每日定義更新試部署通道</span><span class="sxs-lookup"><span data-stu-id="8efc6-143">Select gradual Microsoft Defender daily definition updates rollout channel</span></span>  | <span data-ttu-id="8efc6-144">啟用此原則，以指定裝置每日逐步部署期間何時接收 Microsoft Defender 定義更新。</span><span class="sxs-lookup"><span data-stu-id="8efc6-144">Enable this policy to specify when devices receive Microsoft Defender definition updates during the daily gradual rollout.</span></span> <br><br> <span data-ttu-id="8efc6-145">目前通道 (分段) ：裝置會在發行週期後提供更新。</span><span class="sxs-lookup"><span data-stu-id="8efc6-145">Current Channel (Staged): Devices will be offered updates after the release cycle.</span></span> <span data-ttu-id="8efc6-146">建議套用至實際生產環境 (~ 10% ) 中的小型代表性部分。</span><span class="sxs-lookup"><span data-stu-id="8efc6-146">Suggested to apply to a small, representative part of production population (~10%).</span></span> <br><br>   <span data-ttu-id="8efc6-147">目前通道 (多種) ：只有逐步發行週期完成之後，才會提供裝置更新。</span><span class="sxs-lookup"><span data-stu-id="8efc6-147">Current Channel (Broad): Devices will be offered updates only after the gradual release cycle completes.</span></span> <span data-ttu-id="8efc6-148">建議套用至實際執行填充 (~ 10-100% ) 中的一組廣泛裝置。</span><span class="sxs-lookup"><span data-stu-id="8efc6-148">Suggested to apply to a broad set of devices in your production population (~10-100%).</span></span> <br><br>   <span data-ttu-id="8efc6-149">如果您停用或未設定此原則，裝置會在每日發行週期期間自動維持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="8efc6-149">If you disable or do not configure this policy, the device will stay up to date automatically during the daily release cycle.</span></span> <span data-ttu-id="8efc6-150">適用于大部分裝置。</span><span class="sxs-lookup"><span data-stu-id="8efc6-150">Suitable for most devices.</span></span>  | <span data-ttu-id="8efc6-151">Windows元件 \ Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="8efc6-151">Windows Components\Microsoft Defender Antivirus</span></span>  |
| <span data-ttu-id="8efc6-152">停用 Microsoft Defender 更新逐步展入</span><span class="sxs-lookup"><span data-stu-id="8efc6-152">Disable gradual rollout of Microsoft Defender updates</span></span>  | <span data-ttu-id="8efc6-153">啟用這個原則，以停用 Defender 更新的逐步展入。</span><span class="sxs-lookup"><span data-stu-id="8efc6-153">Enable this policy to disable gradual rollout of Defender updates.</span></span> <br><br> <span data-ttu-id="8efc6-154">目前通道 (廣泛) ：設定成此通道的裝置會在逐步發行週期中最後提供更新。</span><span class="sxs-lookup"><span data-stu-id="8efc6-154">Current Channel (Broad): Devices set to this channel will be offered updates last during the gradual release cycle.</span></span> <span data-ttu-id="8efc6-155">適用于僅接收有限更新的資料中心電腦。</span><span class="sxs-lookup"><span data-stu-id="8efc6-155">Best for datacenter machines that only receive limited updates.</span></span> <br><br> <span data-ttu-id="8efc6-156">注意：此設定會同時套用至每月和每日的 Defender 更新，並將覆寫先前設定平臺及引擎更新的任何先前設定的頻道選擇。</span><span class="sxs-lookup"><span data-stu-id="8efc6-156">Note: This setting applies to both monthly as well as daily Defender updates and will override any previously configured channel selections for platform and engine updates.</span></span> <br><br> <span data-ttu-id="8efc6-157">如果您停用或未設定此原則，裝置會維持在目前通道 (預設) ，除非另有指定的平臺及引擎更新的特定通道。</span><span class="sxs-lookup"><span data-stu-id="8efc6-157">If you disable or do not configure this policy, the device will remain in Current Channel (Default) unless specified otherwise in specific channels for platform and engine updates.</span></span> <span data-ttu-id="8efc6-158">在逐步發佈週期內自動保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="8efc6-158">Stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="8efc6-159">適用于大部分裝置。</span><span class="sxs-lookup"><span data-stu-id="8efc6-159">Suitable for most devices.</span></span>  | <span data-ttu-id="8efc6-160">Windows元件 \ Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="8efc6-160">Windows Components\Microsoft Defender Antivirus</span></span>  |

## <a name="group-policy"></a><span data-ttu-id="8efc6-161">群組原則</span><span class="sxs-lookup"><span data-stu-id="8efc6-161">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="8efc6-162">更新的 Defender ADMX 範本會一起發佈，與 Windows 10 的21H2 版本一起發行。</span><span class="sxs-lookup"><span data-stu-id="8efc6-162">An updated Defender ADMX template will be published together with the 21H2 release of Windows 10.</span></span>

<span data-ttu-id="8efc6-163">您可以使用 [群組原則](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)   來設定及管理端點上的 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="8efc6-163">You can use [Group Policy](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN) to configure and manage Microsoft Defender Antivirus on your endpoints.</span></span>

<span data-ttu-id="8efc6-164">一般來講，您可以使用下列程式設定或變更 Microsoft Defender 防毒軟體群組原則設定：</span><span class="sxs-lookup"><span data-stu-id="8efc6-164">In general, you can use the following procedure to configure or change Microsoft Defender Antivirus group policy settings:</span></span>

1. <span data-ttu-id="8efc6-165">在您的群組原則管理電腦上，開啟 [ **群組原則管理主控台**]，以滑鼠右鍵按一下要設定 (GPO) 的 **群組原則物件** ，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="8efc6-165">On your Group Policy management machine, open the  **Group Policy Management Console**, right-click the **Group Policy Object** (GPO) you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="8efc6-166">使用群組原則管理編輯器移至 [ **電腦** 設定]。</span><span class="sxs-lookup"><span data-stu-id="8efc6-166">Using the Group Policy Management Editor go to **Computer configuration**.</span></span>

3. <span data-ttu-id="8efc6-167">按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="8efc6-167">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="8efc6-168">展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體**。</span><span class="sxs-lookup"><span data-stu-id="8efc6-168">Expand the tree to **Windows components > Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="8efc6-169"> \*\*\*\*   在本主題中，展開包含您要設定之設定的此區段中 (參照為 Location 的位置) ，按兩下此設定以開啟它，然後進行設定變更。</span><span class="sxs-lookup"><span data-stu-id="8efc6-169">Expand the section (referred to as **Location** in the table in this topic) that contains the setting you want to configure, double-click the setting to open it, and make configuration changes.</span></span>

6. <span data-ttu-id="8efc6-170">照常[部署更新的 GPO](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="8efc6-170">[Deploy the updated GPO as you normally do](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx).</span></span>

## <a name="intune"></a><span data-ttu-id="8efc6-171">Intune</span><span class="sxs-lookup"><span data-stu-id="8efc6-171">Intune</span></span>

<span data-ttu-id="8efc6-172">遵循下列連結中的指示，在 Intune 中建立自訂原則：</span><span class="sxs-lookup"><span data-stu-id="8efc6-172">Follow the instructions in below link to create a custom policy in Intune:</span></span>

[<span data-ttu-id="8efc6-173">Microsoft Intune Azure Microsoft 檔中的 Windows 10 裝置新增自訂設定 \|</span><span class="sxs-lookup"><span data-stu-id="8efc6-173">Add custom settings for Windows 10 devices in Microsoft Intune - Azure \| Microsoft Docs</span></span>](/mem/intune/configuration/custom-settings-windows-10)

## <a name="powershell"></a><span data-ttu-id="8efc6-174">PowerShell</span><span class="sxs-lookup"><span data-stu-id="8efc6-174">PowerShell</span></span>

<span data-ttu-id="8efc6-175">使用 `Set-MpPreference` Cmdlet 來設定逐步更新的推出。</span><span class="sxs-lookup"><span data-stu-id="8efc6-175">Use the `Set-MpPreference` cmdlet to configure roll out of the gradual updates.</span></span>

<span data-ttu-id="8efc6-176">使用下列參數：</span><span class="sxs-lookup"><span data-stu-id="8efc6-176">Use the following parameters:</span></span>

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

<span data-ttu-id="8efc6-177">範例：</span><span class="sxs-lookup"><span data-stu-id="8efc6-177">Example:</span></span>

<span data-ttu-id="8efc6-178">用於 `Set-MpPreference -PlatformUpdatesChannel Beta` 設定平臺更新，以從 Beta 通道抵達。</span><span class="sxs-lookup"><span data-stu-id="8efc6-178">Use `Set-MpPreference -PlatformUpdatesChannel Beta` to configure platform updates to arrive from the Beta Channel.</span></span>

<span data-ttu-id="8efc6-179">如需參數及其設定方式的詳細資訊，請參閱 [MpPreference (Defender) |Microsoft](/powershell/module/defender/set-mppreference?view=windowsserver2019-ps)檔。</span><span class="sxs-lookup"><span data-stu-id="8efc6-179">For more information on the parameters and how to configure them, see [Set-MpPreference (Defender) | Microsoft Docs](/powershell/module/defender/set-mppreference?view=windowsserver2019-ps).</span></span>