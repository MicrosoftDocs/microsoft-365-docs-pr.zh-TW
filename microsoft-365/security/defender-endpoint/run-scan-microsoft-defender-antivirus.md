---
title: 在 Microsoft Defender 防毒軟體中執行及自訂隨選掃描
description: 在具有 Windows 安全性應用程式的端點上，使用 PowerShell、Windows 管理工具或個別的方式執行及設定隨選掃描
keywords: 掃描、隨選、dos、intune、立即掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b2910f9fe1c49178b8696d1a421248156b0fc4c2
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925728"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="9673a-104">設定和執行隨選 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="9673a-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="9673a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9673a-105">**Applies to:**</span></span>

- [<span data-ttu-id="9673a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9673a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9673a-107">您可以在個別端點上執行隨選掃描。</span><span class="sxs-lookup"><span data-stu-id="9673a-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="9673a-108">這些掃描會立即開始，您可以定義掃描的參數，例如位置或類型。</span><span class="sxs-lookup"><span data-stu-id="9673a-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span> <span data-ttu-id="9673a-109">當您執行掃描時，可以選擇三種類型：快速掃描、完整掃描及自訂掃描。</span><span class="sxs-lookup"><span data-stu-id="9673a-109">When you run a scan, you can choose from among three types: Quick scan, full scan, and custom scan.</span></span> <span data-ttu-id="9673a-110">在大多數情況下，請使用快速掃描。</span><span class="sxs-lookup"><span data-stu-id="9673a-110">In most cases, use a quick scan.</span></span> <span data-ttu-id="9673a-111">快速掃描會查看可能已註冊惡意程式碼的所有位置，例如登錄機碼和已知 Windows 開機檔案夾。</span><span class="sxs-lookup"><span data-stu-id="9673a-111">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="9673a-112">結合 always on 即時保護，可在開啟及關閉檔時對其進行審閱; 每當使用者流覽至資料夾時，快速掃描可協助對以系統和內核層級惡意程式碼開頭的惡意程式碼提供強防護。</span><span class="sxs-lookup"><span data-stu-id="9673a-112">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="9673a-113">在大多數情況下，快速掃描足以滿足計畫或隨選掃描的建議選項。</span><span class="sxs-lookup"><span data-stu-id="9673a-113">In most cases, a quick scan is sufficient and is the recommended option for scheduled or on-demand scans.</span></span>  <span data-ttu-id="9673a-114">[深入瞭解掃描類型](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)。</span><span class="sxs-lookup"><span data-stu-id="9673a-114">[Learn more about scan types](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9673a-115">執行本機掃描時，Microsoft Defender 防毒軟體會在[LocalSystem](/windows/win32/services/localsystem-account)帳戶的上下文中執行。</span><span class="sxs-lookup"><span data-stu-id="9673a-115">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="9673a-116">若為網路掃描，它會使用裝置帳戶的內容。</span><span class="sxs-lookup"><span data-stu-id="9673a-116">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="9673a-117">如果網域裝置帳戶沒有存取共用的適當許可權，則掃描將無法運作。</span><span class="sxs-lookup"><span data-stu-id="9673a-117">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="9673a-118">確定裝置具有存取網路共用的許可權。</span><span class="sxs-lookup"><span data-stu-id="9673a-118">Ensure that the device has permissions to the access network share.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="9673a-119">使用 Microsoft 端點管理員執行掃描</span><span class="sxs-lookup"><span data-stu-id="9673a-119">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="9673a-120">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="9673a-120">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="9673a-121">選擇 [ **Endpoint security**  >  **防病毒**]。</span><span class="sxs-lookup"><span data-stu-id="9673a-121">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="9673a-122">在索引標籤清單中，選取 [ **Windows 10 不健全的端點**]。</span><span class="sxs-lookup"><span data-stu-id="9673a-122">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>

4. <span data-ttu-id="9673a-123">從提供的動作清單中，選取 [ **快速掃描** (建議) 或 **完整掃描**]。</span><span class="sxs-lookup"><span data-stu-id="9673a-123">From the list of actions provided, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

<span data-ttu-id="9673a-124">[![影像 ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9673a-124">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="9673a-125">如需使用 Microsoft 端點管理員執行掃描的詳細資訊，請參閱[反惡意軟體和防火牆工作：如何執行隨選掃描](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。</span><span class="sxs-lookup"><span data-stu-id="9673a-125">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="9673a-126">使用 mpcmdrun.exe 命令列公用程式執行掃描</span><span class="sxs-lookup"><span data-stu-id="9673a-126">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="9673a-127">使用下列 `-scan` 參數：</span><span class="sxs-lookup"><span data-stu-id="9673a-127">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="9673a-128">如需如何使用工具及其他參數（包括開始完整掃描或定義路徑）的詳細資訊，請參閱[use the mpcmdrun.exe 命令列工具來設定及管理 Microsoft Defender 防毒軟體](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="9673a-128">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="9673a-129">使用 Microsoft Intune 執行掃描</span><span class="sxs-lookup"><span data-stu-id="9673a-129">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="9673a-130">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="9673a-130">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="9673a-131">從側邊選取 [**裝置**  >  **所有裝置**]，然後選擇您要掃描的裝置。</span><span class="sxs-lookup"><span data-stu-id="9673a-131">From the sidebar, select **Devices** > **All Devices** and choose the device you want to scan.</span></span>

3. <span data-ttu-id="9673a-132">選取 **.。。其他**。</span><span class="sxs-lookup"><span data-stu-id="9673a-132">Select **...More**.</span></span> <span data-ttu-id="9673a-133">在 [選項] 中，選取 [ **快速掃描** (建議) 或 **完整掃描**]。</span><span class="sxs-lookup"><span data-stu-id="9673a-133">From the options, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="9673a-134">使用 Windows 安全性應用程式執行掃描</span><span class="sxs-lookup"><span data-stu-id="9673a-134">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="9673a-135">請參閱[在 Windows 安全性應用程式中執行掃描](microsoft-defender-security-center-antivirus.md)，以取得在個別端點上執行掃描的指示。</span><span class="sxs-lookup"><span data-stu-id="9673a-135">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="9673a-136">使用 PowerShell Cmdlet 執行掃描</span><span class="sxs-lookup"><span data-stu-id="9673a-136">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="9673a-137">請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9673a-137">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="9673a-138">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="9673a-138">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="9673a-139">使用 Windows 管理指令 (WMI) 執行掃描</span><span class="sxs-lookup"><span data-stu-id="9673a-139">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="9673a-140">使用 **MSFT_MpScan** 類別的 [ **Start** 方法](/previous-versions/windows/desktop/defender/start-msft-mpscan)。</span><span class="sxs-lookup"><span data-stu-id="9673a-140">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="9673a-141">如需允許哪些參數的詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="9673a-141">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

