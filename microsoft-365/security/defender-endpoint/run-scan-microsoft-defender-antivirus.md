---
title: 在 Microsoft Defender 防毒軟體中執行及自訂隨選掃描
description: 在具有 Windows 安全性應用程式的端點上，使用 PowerShell、Windows 管理工具或個別的方式執行及設定隨選掃描
keywords: 掃描、隨選、dos、intune、立即掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789168"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="f49ca-104">設定和執行隨選 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="f49ca-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="f49ca-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f49ca-105">**Applies to:**</span></span>

- [<span data-ttu-id="f49ca-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f49ca-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f49ca-107">您可以在個別端點上執行隨選掃描。</span><span class="sxs-lookup"><span data-stu-id="f49ca-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="f49ca-108">這些掃描會立即開始，您可以定義掃描的參數，例如位置或類型。</span><span class="sxs-lookup"><span data-stu-id="f49ca-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="f49ca-109">快速掃描與完整掃描</span><span class="sxs-lookup"><span data-stu-id="f49ca-109">Quick scan versus full scan</span></span>

<span data-ttu-id="f49ca-110">快速掃描查看可能已註冊惡意程式碼的所有位置，例如登錄機碼和已知 Windows 開機檔案夾。</span><span class="sxs-lookup"><span data-stu-id="f49ca-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f49ca-111">執行本機掃描時，Microsoft Defender 防毒軟體會在[LocalSystem](/windows/win32/services/localsystem-account)帳戶的上下文中執行。</span><span class="sxs-lookup"><span data-stu-id="f49ca-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="f49ca-112">若為網路掃描，它會使用裝置帳戶的內容。</span><span class="sxs-lookup"><span data-stu-id="f49ca-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="f49ca-113">如果網域裝置帳戶沒有存取共用的適當許可權，則掃描將無法運作。</span><span class="sxs-lookup"><span data-stu-id="f49ca-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="f49ca-114">確定裝置具有存取網路共用的許可權。</span><span class="sxs-lookup"><span data-stu-id="f49ca-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="f49ca-115">[！注意] 結合了 [always on 即時保護功能](configure-real-time-protection-microsoft-defender-antivirus.md)，快速掃描可為以系統和內核層級惡意程式碼開頭的惡意程式碼提供強大的覆蓋。</span><span class="sxs-lookup"><span data-stu-id="f49ca-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="f49ca-116">[永遠開啟] 即時保護會在開啟及關閉檔案時，以及每當使用者流覽至資料夾時，就會檢查檔案。</span><span class="sxs-lookup"><span data-stu-id="f49ca-116">Always-on, real-time protection reviews files when they're opened and closed, and whenever a user navigates to a folder.</span></span> <span data-ttu-id="f49ca-117">根據預設，在裝載的可拆卸裝置（例如 USB 磁片磁碟機）上執行快速掃描。</span><span class="sxs-lookup"><span data-stu-id="f49ca-117">By default, quick scans run on mounted removable devices, such as USB drives.</span></span> <span data-ttu-id="f49ca-118">在大多數的情況下，快速掃描足以找到即時保護未挑選的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="f49ca-118">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="f49ca-119">當在端點上報告惡意程式碼威脅時，完整掃描會非常有用。</span><span class="sxs-lookup"><span data-stu-id="f49ca-119">A full scan can be useful when a malware threat is reported on an endpoint.</span></span> <span data-ttu-id="f49ca-120">掃描可識別是否有任何非使用中的元件需要更徹底的清理。</span><span class="sxs-lookup"><span data-stu-id="f49ca-120">The scan can identify whether there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="f49ca-121">不過，Microsoft 一般建議使用快速掃描，而不是完整掃描。</span><span class="sxs-lookup"><span data-stu-id="f49ca-121">However, Microsoft generally recommends using quick scans instead of full scans.</span></span> <span data-ttu-id="f49ca-122">根據需要掃描的資料量和類型，完整掃描可能需要數小時或數天才能完成。</span><span class="sxs-lookup"><span data-stu-id="f49ca-122">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span> 

> [!TIP]
> <span data-ttu-id="f49ca-123">若要深入瞭解快速和完整掃描之間的差異，請參閱 [快速掃描與完整掃描及自訂掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)。</span><span class="sxs-lookup"><span data-stu-id="f49ca-123">To learn more about the differences between quick and full scans, see [Quick scan versus full scan and custom scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan).</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="f49ca-124">使用 Microsoft 端點管理員執行掃描</span><span class="sxs-lookup"><span data-stu-id="f49ca-124">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="f49ca-125">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="f49ca-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="f49ca-126">選擇 [ **Endpoint security**  >  **防病毒**]。</span><span class="sxs-lookup"><span data-stu-id="f49ca-126">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="f49ca-127">在索引標籤清單中，選取 [ **Windows 10 不健全的端點**]。</span><span class="sxs-lookup"><span data-stu-id="f49ca-127">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="f49ca-128">從提供的動作清單中，選取 [ **快速掃描** ] 或 [ **完全掃描**]。</span><span class="sxs-lookup"><span data-stu-id="f49ca-128">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="f49ca-129">[![影像 ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="f49ca-129">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="f49ca-130">如需使用 Microsoft 端點管理員執行掃描的詳細資訊，請參閱[反惡意軟體和防火牆工作：如何執行隨選掃描](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。</span><span class="sxs-lookup"><span data-stu-id="f49ca-130">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="f49ca-131">使用 mpcmdrun.exe 命令列公用程式執行掃描</span><span class="sxs-lookup"><span data-stu-id="f49ca-131">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="f49ca-132">使用下列 `-scan` 參數：</span><span class="sxs-lookup"><span data-stu-id="f49ca-132">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="f49ca-133">如需如何使用工具及其他參數（包括開始完整掃描或定義路徑）的詳細資訊，請參閱[use the mpcmdrun.exe 命令列工具來設定及管理 Microsoft Defender 防毒軟體](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="f49ca-133">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="f49ca-134">使用 Microsoft Intune 執行掃描</span><span class="sxs-lookup"><span data-stu-id="f49ca-134">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="f49ca-135">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="f49ca-135">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="f49ca-136">從側邊選取 [ **裝置 > 所有裝置** ]，然後選擇您要掃描的裝置。</span><span class="sxs-lookup"><span data-stu-id="f49ca-136">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="f49ca-137">選取 **.。。其他**。</span><span class="sxs-lookup"><span data-stu-id="f49ca-137">Select **...More**.</span></span> <span data-ttu-id="f49ca-138">從選項中，選取 [ **快速掃描** ] 或 [ **完全掃描**]。</span><span class="sxs-lookup"><span data-stu-id="f49ca-138">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="f49ca-139">使用 Windows 安全性應用程式執行掃描</span><span class="sxs-lookup"><span data-stu-id="f49ca-139">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="f49ca-140">請參閱[在 Windows 安全性應用程式中執行掃描](microsoft-defender-security-center-antivirus.md)，以取得在個別端點上執行掃描的指示。</span><span class="sxs-lookup"><span data-stu-id="f49ca-140">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="f49ca-141">使用 PowerShell Cmdlet 執行掃描</span><span class="sxs-lookup"><span data-stu-id="f49ca-141">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="f49ca-142">請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f49ca-142">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="f49ca-143">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="f49ca-143">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="f49ca-144">使用 Windows 管理指令 (WMI) 執行掃描</span><span class="sxs-lookup"><span data-stu-id="f49ca-144">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="f49ca-145">使用 **MSFT_MpScan** 類別的 [ **Start** 方法](/previous-versions/windows/desktop/defender/start-msft-mpscan)。</span><span class="sxs-lookup"><span data-stu-id="f49ca-145">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="f49ca-146">如需允許哪些參數的詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="f49ca-146">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="f49ca-147">相關文章</span><span class="sxs-lookup"><span data-stu-id="f49ca-147">Related articles</span></span>

- [<span data-ttu-id="f49ca-148">設定 Microsoft Defender 防毒軟體掃描選項</span><span class="sxs-lookup"><span data-stu-id="f49ca-148">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f49ca-149">設定排定的 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="f49ca-149">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f49ca-150">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="f49ca-150">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)