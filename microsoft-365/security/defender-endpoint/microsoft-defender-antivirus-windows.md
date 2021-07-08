---
title: Microsoft Defender 防毒軟體
description: 了解如何管理、設定和使用 Microsoft Defender 防毒軟體、內建防毒軟體和防毒保護。
keywords: Microsoft Defender 防毒軟體、Windows Defender、防毒軟體、SCEP、System Center Endpoint Protection、System Center Configuration Manager、病毒、惡意軟體、威脅、偵測、保護、安全性
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322587"
---
# <a name="microsoft-defender-antivirus-in-windows"></a><span data-ttu-id="9968e-104">Windows 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="9968e-104">Microsoft Defender Antivirus in Windows</span></span>

<span data-ttu-id="9968e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9968e-105">**Applies to:**</span></span>

- [<span data-ttu-id="9968e-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9968e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9968e-107">Microsoft Defender 防毒軟體是新一代適用於端點的 Microsoft Defender 的主要保護元件。</span><span class="sxs-lookup"><span data-stu-id="9968e-107">Microsoft Defender Antivirus is a major component of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9968e-108">此保護結合機器學習、巨量資料分析、深度威脅抵禦研究和 Microsoft 雲端基礎結構來保護貴組織中的裝置 (或端點)。</span><span class="sxs-lookup"><span data-stu-id="9968e-108">This protection brings together machine learning, big-data analysis, in-depth threat resistance research, and the Microsoft cloud infrastructure to protect devices (or endpoints) in your organization.</span></span> <span data-ttu-id="9968e-109">Microsoft Defender 防毒軟體內建於 Windows，且可與適用於端點的 Microsoft Defender 一起運作，以在裝置和雲端提供保護。</span><span class="sxs-lookup"><span data-stu-id="9968e-109">Microsoft Defender Antivirus is built into Windows, and it works with Microsoft Defender for Endpoint to provide protection on your device and in the cloud.</span></span> 

## <a name="compatibility-with-other-antivirus-products"></a><span data-ttu-id="9968e-110">與其他防毒軟體產品的相容性</span><span class="sxs-lookup"><span data-stu-id="9968e-110">Compatibility with other antivirus products</span></span>

<span data-ttu-id="9968e-111">如果您在裝置上使用非 Microsoft 防毒軟體/反惡意程式碼軟體產品，您或許可以在被動模式中執行 Microsoft Defender 防毒軟體，以及非 Microsoft 防毒軟體解決方案。</span><span class="sxs-lookup"><span data-stu-id="9968e-111">If you're using a non-Microsoft antivirus/antimalware product on your device, you might be able to run Microsoft Defender Antivirus in passive mode alongside the non-Microsoft antivirus solution.</span></span> <span data-ttu-id="9968e-112">這取決於您所使用的作業系統，以及您的裝置是否已加入適用於端點的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="9968e-112">It depends on the operating system used and whether your device is onboarded to Defender for Endpoint.</span></span> <span data-ttu-id="9968e-113">如需深入了解，請參閱 [Microsoft Defender 防毒軟體相容性](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="9968e-113">To learn more, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a><span data-ttu-id="9968e-114">比較主動模式、被動模式和停用模式</span><span class="sxs-lookup"><span data-stu-id="9968e-114">Comparing active mode, passive mode, and disabled mode</span></span>

<span data-ttu-id="9968e-115">下表說明 Microsoft Defender 防毒軟體處於主動模式、被動模式或停用模式時預期的情況。</span><span class="sxs-lookup"><span data-stu-id="9968e-115">The following table describes what to expect when Microsoft Defender Antivirus is in active mode, passive mode, or disabled.</span></span>

| <span data-ttu-id="9968e-116">模式</span><span class="sxs-lookup"><span data-stu-id="9968e-116">Mode</span></span>  | <span data-ttu-id="9968e-117">發生的情況</span><span class="sxs-lookup"><span data-stu-id="9968e-117">What happens</span></span>  |
|---------|---------|
| <span data-ttu-id="9968e-118">主動模式</span><span class="sxs-lookup"><span data-stu-id="9968e-118">Active mode</span></span> | <span data-ttu-id="9968e-119">在主動模式中，Microsoft Defender 防毒軟體會做為裝置上的主要防毒軟體應用程式。</span><span class="sxs-lookup"><span data-stu-id="9968e-119">In active mode, Microsoft Defender Antivirus is used as the primary antivirus app on the device.</span></span> <span data-ttu-id="9968e-120">系統會掃描檔案、補救威脅，並將偵測到的威脅列在貴組織的安全性報告和 Windows 安全性應用程式中。</span><span class="sxs-lookup"><span data-stu-id="9968e-120">Files are scanned, threats are remediated, and detected threats are listed in your organization's security reports and in your Windows Security app.</span></span> |
| <span data-ttu-id="9968e-121">被動模式</span><span class="sxs-lookup"><span data-stu-id="9968e-121">Passive mode</span></span> | <span data-ttu-id="9968e-122">在被動模式中，Microsoft Defender 防毒軟體不會做為裝置上的主要防毒軟體應用程式。</span><span class="sxs-lookup"><span data-stu-id="9968e-122">In passive mode, Microsoft Defender Antivirus is not used as the primary antivirus app on the device.</span></span> <span data-ttu-id="9968e-123">系統會掃描檔案並報告偵測到的威脅，但 Microsoft Defender 防毒軟體不會補救威脅。</span><span class="sxs-lookup"><span data-stu-id="9968e-123">Files are scanned, and detected threats are reported, but threats are not remediated by Microsoft Defender Antivirus.</span></span>   |
| <span data-ttu-id="9968e-124">已停用或已解除安裝</span><span class="sxs-lookup"><span data-stu-id="9968e-124">Disabled or uninstalled</span></span>  | <span data-ttu-id="9968e-125">已停用或已解除安裝時，系統不會使用 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="9968e-125">When disabled or uninstalled, Microsoft Defender Antivirus is not used.</span></span> <span data-ttu-id="9968e-126">系統不會掃描檔案，而且不會補救威脅。</span><span class="sxs-lookup"><span data-stu-id="9968e-126">Files are not scanned, and threats are not remediated.</span></span> <span data-ttu-id="9968e-127">一般而言，我們不建議停用或解除安裝 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="9968e-127">In general, we do not recommend disabling or uninstalling Microsoft Defender Antivirus.</span></span>  |

<span data-ttu-id="9968e-128">如需深入了解，請參閱 [Microsoft Defender 防毒軟體相容性](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="9968e-128">To learn more, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a><span data-ttu-id="9968e-129">檢查您裝置上的 Microsoft Defender 防毒軟體狀態</span><span class="sxs-lookup"><span data-stu-id="9968e-129">Check the state of Microsoft Defender Antivirus on your device</span></span>

<span data-ttu-id="9968e-130">如果您想要檢查裝置上的 Microsoft Defender 防毒軟體狀態，您有數種方法可以使用，例如 Windows 安全性應用程式或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="9968e-130">If you want to check the state of Microsoft Defender Antivirus on your device, you can use one of several methods, such as the Windows Security app or Windows PowerShell.</span></span>

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a><span data-ttu-id="9968e-131">使用 Windows 安全性應用程式檢查 Microsoft Defender 防毒軟體的狀態</span><span class="sxs-lookup"><span data-stu-id="9968e-131">Use the Windows Security app to check status of Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="9968e-132">在 Windows 裝置上，選取開始功能表，然後開始輸入 `Security`。</span><span class="sxs-lookup"><span data-stu-id="9968e-132">On your Windows device, select the Start menu, and begin typing `Security`.</span></span> <span data-ttu-id="9968e-133">然後在結果中開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="9968e-133">Then open the Windows Security app in the results.</span></span>

2. <span data-ttu-id="9968e-134">選取 **[病毒與威脅防護]**。</span><span class="sxs-lookup"><span data-stu-id="9968e-134">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="9968e-135">在 **[病毒與威脅防護]** 設定下方，選擇 **[管理提供者]**。</span><span class="sxs-lookup"><span data-stu-id="9968e-135">Under **Virus & threat protection settings**, choose **Manage settings**.</span></span>

<span data-ttu-id="9968e-136">您可以在設定頁面上看到防毒軟體/反惡意程式碼軟體解決方案的名稱。</span><span class="sxs-lookup"><span data-stu-id="9968e-136">You'll see the name of your antivirus/antimalware solution on the settings page.</span></span>

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a><span data-ttu-id="9968e-137">使用 PowerShell 檢查 Microsoft Defender 防毒軟體的狀態</span><span class="sxs-lookup"><span data-stu-id="9968e-137">Use PowerShell to check status of Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="9968e-138">選取開始功能表，然後開始輸入 `PowerShell`。</span><span class="sxs-lookup"><span data-stu-id="9968e-138">Select the Start menu, and begin typing `PowerShell`.</span></span> <span data-ttu-id="9968e-139">然後在結果中開啟 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="9968e-139">Then open Windows PowerShell in the results.</span></span>

2. <span data-ttu-id="9968e-140">輸入 `Get-MpComputerStatus`。</span><span class="sxs-lookup"><span data-stu-id="9968e-140">Type `Get-MpComputerStatus`.</span></span>

3. <span data-ttu-id="9968e-141">在結果清單中，查看 **AMRunningMode** 資料列。</span><span class="sxs-lookup"><span data-stu-id="9968e-141">In the list of results, look at the **AMRunningMode** row.</span></span>

   - <span data-ttu-id="9968e-142">**標準** 表示 Microsoft Defender 防毒軟體正在以主動模式執行。</span><span class="sxs-lookup"><span data-stu-id="9968e-142">**Normal** means Microsoft Defender Antivirus is running in active mode.</span></span>
   - <span data-ttu-id="9968e-143">**被動模式** 表示 Microsoft Defender 防毒軟體執行中，但不是裝置上的主要防毒軟體/反惡意程式碼軟體產品。</span><span class="sxs-lookup"><span data-stu-id="9968e-143">**Passive mode** means Microsoft Defender Antivirus running, but is not the primary antivirus/antimalware product on your device.</span></span>
   - <span data-ttu-id="9968e-144">**EDR 封鎖模式** 表示 Microsoft Defender 防毒軟體執行中，且適用於端點的 Microsoft Defender 中稱為「封鎖模式 EDR」的功能已啟用。</span><span class="sxs-lookup"><span data-stu-id="9968e-144">**EDR Block Mode** means Microsoft Defender Antivirus is running and a capability in Microsoft Defender for Endpoint that is called "EDR in block mode" is enabled.</span></span> <span data-ttu-id="9968e-145">(請參閱[封鎖模式中的端點偵測和回應 (EDR)](edr-in-block-mode.md)。)</span><span class="sxs-lookup"><span data-stu-id="9968e-145">(See [Endpoint detection and response (EDR) in block mode](edr-in-block-mode.md).)</span></span>
   - <span data-ttu-id="9968e-146">**SxS 被動模式** 表示 Microsoft Defender 防毒軟體正以被動模式與另一個防毒軟體/反惡意程式碼軟體產品一起執行，且您的裝置未加入適用於端點的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="9968e-146">**SxS Passive Mode** means Microsoft Defender Antivirus is running in passive mode alongside another antivirus/antimalware product, and your device is not onboarded to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9968e-147">在此情況下，Microsoft Defender 防毒軟體使用有限的定期掃描。</span><span class="sxs-lookup"><span data-stu-id="9968e-147">In this case, limited periodic scanning is used for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="9968e-148">若要深入了解，請參閱[在 Microsoft Defender 防毒軟體中使用有限的定期掃描](limited-periodic-scanning-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="9968e-148">To learn more, see [Use limited periodic scanning in Microsoft Defender Antivirus](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="9968e-149">若要深入了解 Get-MpComputerStatus PowerShell Cmdlet，請參閱參考文章 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。</span><span class="sxs-lookup"><span data-stu-id="9968e-149">To learn more about the Get-MpComputerStatus PowerShell cmdlet, see the reference article [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).</span></span>

## <a name="get-your-antivirusantimalware-platform-updates"></a><span data-ttu-id="9968e-150">取得您的防毒軟體和反惡意程式碼軟體平台更新</span><span class="sxs-lookup"><span data-stu-id="9968e-150">Get your antivirus/antimalware platform updates</span></span>

<span data-ttu-id="9968e-151">將 Microsoft Defender 防毒軟體或任何防毒軟體/反惡意程式碼軟體解決方案保持在最新狀態非常重要。</span><span class="sxs-lookup"><span data-stu-id="9968e-151">It's important to keep Microsoft Defender Antivirus, or any antivirus/antimalware solution, up to date.</span></span> <span data-ttu-id="9968e-152">Microsoft 會發行定期更新，確保您的裝置擁有最新的技術，以防範新的惡意程式碼軟體和攻擊技術。</span><span class="sxs-lookup"><span data-stu-id="9968e-152">Microsoft releases regular updates to help ensure that your devices have the latest technology to protect against new malware and attack techniques.</span></span> <span data-ttu-id="9968e-153">若要深入了解，請參閱[管理Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="9968e-153">To learn more, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> 

## <a name="see-also"></a><span data-ttu-id="9968e-154">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9968e-154">See also</span></span>

- [<span data-ttu-id="9968e-155">Windows Server 上的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="9968e-155">Microsoft Defender Antivirus on Windows Server</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="9968e-156">Microsoft Defender 防毒軟體管理和設定</span><span class="sxs-lookup"><span data-stu-id="9968e-156">Microsoft Defender Antivirus management and configuration</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9968e-157">評估 Microsoft Defender 防毒軟體保護</span><span class="sxs-lookup"><span data-stu-id="9968e-157">Evaluate Microsoft Defender Antivirus protection</span></span>](evaluate-microsoft-defender-antivirus.md)
