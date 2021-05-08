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
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 8b6889a2eabcfb777983be79d78060165497de72
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246341"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="562fb-104">設定和執行隨選 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="562fb-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="562fb-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="562fb-105">**Applies to:**</span></span>

- [<span data-ttu-id="562fb-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="562fb-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="562fb-107">您可以在個別端點上執行隨選掃描。</span><span class="sxs-lookup"><span data-stu-id="562fb-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="562fb-108">這些掃描會立即開始，您可以定義掃描的參數，例如位置或類型。</span><span class="sxs-lookup"><span data-stu-id="562fb-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="562fb-109">快速掃描與完整掃描</span><span class="sxs-lookup"><span data-stu-id="562fb-109">Quick scan versus full scan</span></span>

<span data-ttu-id="562fb-110">快速掃描查看可能已註冊惡意程式碼的所有位置，例如登錄機碼和已知 Windows 開機檔案夾。</span><span class="sxs-lookup"><span data-stu-id="562fb-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="562fb-111">執行本機掃描時，Microsoft Defender 防毒軟體會在[LocalSystem](/windows/win32/services/localsystem-account)帳戶的上下文中執行。</span><span class="sxs-lookup"><span data-stu-id="562fb-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="562fb-112">若為網路掃描，它會使用裝置帳戶的內容。</span><span class="sxs-lookup"><span data-stu-id="562fb-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="562fb-113">如果網域裝置帳戶沒有存取共用的適當許可權，則掃描將無法運作。</span><span class="sxs-lookup"><span data-stu-id="562fb-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="562fb-114">確定裝置具有存取網路共用的許可權。</span><span class="sxs-lookup"><span data-stu-id="562fb-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="562fb-115">與 [always on 即時保護功能](configure-real-time-protection-microsoft-defender-antivirus.md)組合在一起，可在開啟和關閉檔時檢查檔案，以及每當使用者流覽至資料夾時，都可以為以系統和內核層級惡意程式碼開頭的惡意程式碼提供強大的覆蓋。</span><span class="sxs-lookup"><span data-stu-id="562fb-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md)--which reviews files when they're opened and closed, and whenever a user navigates to a folder--a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="562fb-116">在大多數的情況下，快速掃描足以找到即時保護未挑選的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="562fb-116">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="562fb-117">完整掃描可用於已經報告惡意程式碼威脅的端點。</span><span class="sxs-lookup"><span data-stu-id="562fb-117">A full scan can be useful on endpoints that have reported a malware threat.</span></span> <span data-ttu-id="562fb-118">掃描可識別是否有任何非使用中的元件需要更徹底的清理。</span><span class="sxs-lookup"><span data-stu-id="562fb-118">The scan can identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="562fb-119">如果您的組織執行的是手動掃描，則這是理想的功能。</span><span class="sxs-lookup"><span data-stu-id="562fb-119">This is  ideal if your organization is running on-demand scans.</span></span>

> [!NOTE]
> <span data-ttu-id="562fb-120">根據預設，在裝載的可拆卸裝置（例如 USB 磁片磁碟機）上執行快速掃描。</span><span class="sxs-lookup"><span data-stu-id="562fb-120">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="562fb-121">使用 Microsoft 端點管理員執行掃描</span><span class="sxs-lookup"><span data-stu-id="562fb-121">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="562fb-122">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="562fb-122">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="562fb-123">選擇 [ **Endpoint security**  >  **防病毒**]。</span><span class="sxs-lookup"><span data-stu-id="562fb-123">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="562fb-124">在索引標籤清單中，選取 [ **Windows 10 不健全的端點**]。</span><span class="sxs-lookup"><span data-stu-id="562fb-124">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="562fb-125">從提供的動作清單中，選取 [ **快速掃描** ] 或 [ **完全掃描**]。</span><span class="sxs-lookup"><span data-stu-id="562fb-125">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="562fb-126">[![影像 ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="562fb-126">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="562fb-127">如需使用 Microsoft 端點管理員執行掃描的詳細資訊，請參閱[反惡意軟體和防火牆工作：如何執行隨選掃描](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。</span><span class="sxs-lookup"><span data-stu-id="562fb-127">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="562fb-128">使用 mpcmdrun.exe 命令列公用程式執行掃描</span><span class="sxs-lookup"><span data-stu-id="562fb-128">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="562fb-129">使用下列 `-scan` 參數：</span><span class="sxs-lookup"><span data-stu-id="562fb-129">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="562fb-130">如需如何使用工具及其他參數（包括開始完整掃描或定義路徑）的詳細資訊，請參閱[use the mpcmdrun.exe 命令列工具來設定及管理 Microsoft Defender 防毒軟體](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="562fb-130">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="562fb-131">使用 Microsoft Intune 執行掃描</span><span class="sxs-lookup"><span data-stu-id="562fb-131">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="562fb-132">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="562fb-132">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="562fb-133">從側邊選取 [ **裝置 > 所有裝置** ]，然後選擇您要掃描的裝置。</span><span class="sxs-lookup"><span data-stu-id="562fb-133">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="562fb-134">選取 **.。。其他**。</span><span class="sxs-lookup"><span data-stu-id="562fb-134">Select **...More**.</span></span> <span data-ttu-id="562fb-135">從選項中，選取 [ **快速掃描** ] 或 [ **完全掃描**]。</span><span class="sxs-lookup"><span data-stu-id="562fb-135">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="562fb-136">使用 Windows 安全性應用程式執行掃描</span><span class="sxs-lookup"><span data-stu-id="562fb-136">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="562fb-137">請參閱[在 Windows 安全性應用程式中執行掃描](microsoft-defender-security-center-antivirus.md)，以取得在個別端點上執行掃描的指示。</span><span class="sxs-lookup"><span data-stu-id="562fb-137">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="562fb-138">使用 PowerShell Cmdlet 執行掃描</span><span class="sxs-lookup"><span data-stu-id="562fb-138">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="562fb-139">請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="562fb-139">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="562fb-140">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="562fb-140">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="562fb-141">使用 Windows 管理指令 (WMI) 執行掃描</span><span class="sxs-lookup"><span data-stu-id="562fb-141">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="562fb-142">使用 **MSFT_MpScan** 類別的 [ **Start** 方法](/previous-versions/windows/desktop/defender/start-msft-mpscan)。</span><span class="sxs-lookup"><span data-stu-id="562fb-142">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="562fb-143">如需允許哪些參數的詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="562fb-143">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="562fb-144">相關文章</span><span class="sxs-lookup"><span data-stu-id="562fb-144">Related articles</span></span>

- [<span data-ttu-id="562fb-145">設定 Microsoft Defender 防毒軟體掃描選項</span><span class="sxs-lookup"><span data-stu-id="562fb-145">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="562fb-146">設定排定的 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="562fb-146">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="562fb-147">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="562fb-147">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)