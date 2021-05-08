---
title: Windows 10 中的 Microsoft Defender Offline
description: 您可以從 Windows Defender 防毒軟體應用程式直接使用 Microsoft Defender Offline。 您也可以管理在網路中部署的方式。
keywords: 掃描、defender、離線
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a25a2ec513cd7c25f9f6ddf3d5e328928837bf2d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275141"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a><span data-ttu-id="de482-105">執行和檢查 Microsoft Defender Offline 掃描的結果</span><span class="sxs-lookup"><span data-stu-id="de482-105">Run and review the results of a Microsoft Defender Offline scan</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="de482-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="de482-106">**Applies to:**</span></span>

- [<span data-ttu-id="de482-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="de482-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="de482-108">Microsoft Defender Offline 是反惡意軟體掃描工具，可讓您從信任的環境引導及執行掃描。</span><span class="sxs-lookup"><span data-stu-id="de482-108">Microsoft Defender Offline is an antimalware scanning tool that lets you boot and run a scan from a trusted environment.</span></span> <span data-ttu-id="de482-109">掃描會從一般 Windows 內核以外的地方執行，因此可以針對企圖略過 Windows 命令介面的惡意程式碼，例如感染或覆寫主開機記錄 (MBR) 的病毒和 rootkit。</span><span class="sxs-lookup"><span data-stu-id="de482-109">The scan runs from outside the normal Windows kernel so it can target malware that attempts to bypass the Windows shell, such as viruses and rootkits that infect or overwrite the master boot record (MBR).</span></span>

<span data-ttu-id="de482-110">您可以使用 Microsoft Defender Offline 若懷疑惡意程式碼受到感染，或想要在惡意程式碼爆發後確認完全清除的端點。</span><span class="sxs-lookup"><span data-stu-id="de482-110">You can use Microsoft Defender Offline if you suspect a malware infection, or you want to confirm a thorough clean of the endpoint after a malware outbreak.</span></span>

<span data-ttu-id="de482-111">在 Windows 10 中，您可以直接從[Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)按一下一次，即可執行 Microsoft Defender Offline。</span><span class="sxs-lookup"><span data-stu-id="de482-111">In Windows 10, Microsoft Defender Offline can be run with one click directly from the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="de482-112">在舊版的 Windows 中，使用者必須將 Microsoft Defender Offline 安裝至可引導的媒體、重新開機端點，然後載入可啟動的媒體。</span><span class="sxs-lookup"><span data-stu-id="de482-112">In previous versions of Windows, a user had to install Microsoft Defender Offline to bootable media, restart the endpoint, and load the bootable media.</span></span>

## <a name="prerequisites-and-requirements"></a><span data-ttu-id="de482-113">必要條件和需求</span><span class="sxs-lookup"><span data-stu-id="de482-113">prerequisites and requirements</span></span>

<span data-ttu-id="de482-114">Windows 10 中 Microsoft Defender Offline 的硬體需求與 Windows 10 相同。</span><span class="sxs-lookup"><span data-stu-id="de482-114">Microsoft Defender Offline in Windows 10 has the same hardware requirements as Windows 10.</span></span> 

<span data-ttu-id="de482-115">如需 Windows 10 需求的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="de482-115">For more information about Windows 10 requirements, see the following topics:</span></span>

- [<span data-ttu-id="de482-116">最低硬體需求</span><span class="sxs-lookup"><span data-stu-id="de482-116">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [<span data-ttu-id="de482-117">硬體元件指導方針</span><span class="sxs-lookup"><span data-stu-id="de482-117">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> <span data-ttu-id="de482-118">在具有 ARM 處理器的機器上，或在 Windows 伺服器股票保留單位上不支援 Microsoft Defender Offline。</span><span class="sxs-lookup"><span data-stu-id="de482-118">Microsoft Defender Offline is not supported on machines with ARM processors, or on Windows Server Stock Keeping Units.</span></span>

<span data-ttu-id="de482-119">若要從端點執行 Microsoft Defender Offline，使用者必須以系統管理員許可權登入。</span><span class="sxs-lookup"><span data-stu-id="de482-119">To run Microsoft Defender Offline from the endpoint, the user must be logged in with administrator privileges.</span></span>
 
## <a name="microsoft-defender-offline-updates"></a><span data-ttu-id="de482-120">Microsoft Defender Offline 更新</span><span class="sxs-lookup"><span data-stu-id="de482-120">Microsoft Defender Offline updates</span></span>

<span data-ttu-id="de482-121">Microsoft Defender Offline 會使用端點上可用的最新保護更新;每當更新 Windows Defender 防毒軟體時，它就會更新。</span><span class="sxs-lookup"><span data-stu-id="de482-121">Microsoft Defender Offline uses the most recent protection updates available on the endpoint; it's updated whenever Windows Defender Antivirus is updated.</span></span> 

> [!NOTE]
> <span data-ttu-id="de482-122">在執行離線掃描之前，您應該嘗試更新 Microsoft Defender AV 保護。</span><span class="sxs-lookup"><span data-stu-id="de482-122">Before running an offline scan, you should attempt to update Microsoft Defender AV protection.</span></span> <span data-ttu-id="de482-123">您可以使用群組原則強制執行更新，也可以一般將更新部署至端點，也可以手動從[Microsoft 惡意程式碼防護中心](https://www.microsoft.com/security/portal/definitions/adl.aspx)下載並安裝最新的保護更新。</span><span class="sxs-lookup"><span data-stu-id="de482-123">You can either force an update with Group Policy or however you normally deploy updates to endpoints, or you can manually download and install the latest protection updates from the [Microsoft Malware Protection Center](https://www.microsoft.com/security/portal/definitions/adl.aspx).</span></span>

<span data-ttu-id="de482-124">如需詳細資訊，請參閱[Manage Microsoft Defender 防毒軟體 Security 情報更新](manage-protection-updates-microsoft-defender-antivirus.md)主題。</span><span class="sxs-lookup"><span data-stu-id="de482-124">See the [Manage Microsoft Defender Antivirus Security intelligence  updates](manage-protection-updates-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="usage-scenarios"></a><span data-ttu-id="de482-125">使用情況</span><span class="sxs-lookup"><span data-stu-id="de482-125">Usage scenarios</span></span>

<span data-ttu-id="de482-126">在 Windows 10 版本1607中，您可以手動強制執行離線掃描。</span><span class="sxs-lookup"><span data-stu-id="de482-126">In Windows 10, version 1607, you can manually force an offline scan.</span></span> <span data-ttu-id="de482-127">或者，如果 Windows Defender 判斷 Microsoft Defender Offline 需要執行，它會在端點上提示使用者。</span><span class="sxs-lookup"><span data-stu-id="de482-127">Alternatively, if Windows Defender determines that Microsoft Defender Offline needs to run, it will prompt the user on the endpoint.</span></span> 

<span data-ttu-id="de482-128">如果您要使用它來管理端點，也會在 Microsoft 端點管理員中顯示執行離線掃描的需求。</span><span class="sxs-lookup"><span data-stu-id="de482-128">The need to perform an offline scan will also be revealed in Microsoft Endpoint Manager if you're using it to manage your endpoints.</span></span>

<span data-ttu-id="de482-129">提示會透過通知進行，類似如下所示：</span><span class="sxs-lookup"><span data-stu-id="de482-129">The prompt can occur via a notification, similar to the following:</span></span>

![顯示需要執行的 Windows 通知 Microsoft Defender Offline](images/defender/notification.png)

<span data-ttu-id="de482-131">在 Windows Defender 用戶端中也會通知使用者。</span><span class="sxs-lookup"><span data-stu-id="de482-131">The user will also be notified within the Windows Defender client.</span></span>

<span data-ttu-id="de482-132">在 [設定管理員] 中，您可以流覽至 **監視 > 一覽 > 安全性 > Endpoint Protection 狀態 > System Center Endpoint Protection 狀態**，識別端點的狀態。</span><span class="sxs-lookup"><span data-stu-id="de482-132">In Configuration Manager, you can identify the status of endpoints by navigating to **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**.</span></span> 

<span data-ttu-id="de482-133">Microsoft Defender Offline 掃描會在 **惡意程式碼修復狀態** 下指出為 **需要離線掃描**。</span><span class="sxs-lookup"><span data-stu-id="de482-133">Microsoft Defender Offline scans are indicated under **Malware remediation status** as **Offline scan required**.</span></span>

![Microsoft 端點管理員指出需要 Microsoft Defender Offline 掃描](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a><span data-ttu-id="de482-135">設定通知</span><span class="sxs-lookup"><span data-stu-id="de482-135">Configure notifications</span></span>

<span data-ttu-id="de482-136">Microsoft Defender Offline 通知是以與其他 Microsoft Defender AV 通知相同的原則設定進行設定。</span><span class="sxs-lookup"><span data-stu-id="de482-136">Microsoft Defender Offline notifications are configured in the same policy setting as other Microsoft Defender AV notifications.</span></span>

<span data-ttu-id="de482-137">如需 Windows Defender 中通知的詳細資訊，請參閱[設定出現在端點上的通知](configure-notifications-microsoft-defender-antivirus.md)主題。</span><span class="sxs-lookup"><span data-stu-id="de482-137">For more information about notifications in Windows Defender, see the [Configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md) topic.</span></span>

## <a name="run-a-scan"></a><span data-ttu-id="de482-138">執行掃描</span><span class="sxs-lookup"><span data-stu-id="de482-138">Run a scan</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="de482-139">在您使用 Microsoft Defender Offline 之前，請確定您已儲存任何檔案並關閉執行中的程式。</span><span class="sxs-lookup"><span data-stu-id="de482-139">Before you use Microsoft Defender Offline, make sure you save any files and shut down running programs.</span></span> <span data-ttu-id="de482-140">Microsoft Defender Offline 掃描大約需要15分鐘才能執行。</span><span class="sxs-lookup"><span data-stu-id="de482-140">The Microsoft Defender Offline scan takes about 15 minutes to run.</span></span> <span data-ttu-id="de482-141">掃描完成後，它會重新開機端點。</span><span class="sxs-lookup"><span data-stu-id="de482-141">It will restart the endpoint when the scan is complete.</span></span> <span data-ttu-id="de482-142">掃描會在一般的 Windows 運作環境以外執行。</span><span class="sxs-lookup"><span data-stu-id="de482-142">The scan is performed outside of the usual Windows operating environment.</span></span> <span data-ttu-id="de482-143">使用者介面會出現在 Windows Defender 執行的一般掃描時有所不同。</span><span class="sxs-lookup"><span data-stu-id="de482-143">The user interface will appear different to a normal scan performed by Windows Defender.</span></span> <span data-ttu-id="de482-144">掃描完成後，將會重新開機端點，而且 Windows 會正常載入。</span><span class="sxs-lookup"><span data-stu-id="de482-144">After the scan is completed, the endpoint will be restarted and Windows will load normally.</span></span>

<span data-ttu-id="de482-145">您可以使用下列執行 Microsoft Defender Offline 掃描：</span><span class="sxs-lookup"><span data-stu-id="de482-145">You can run a Microsoft Defender Offline scan with the following:</span></span>

- <span data-ttu-id="de482-146">PowerShell</span><span class="sxs-lookup"><span data-stu-id="de482-146">PowerShell</span></span>
- <span data-ttu-id="de482-147">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="de482-147">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="de482-148">Windows 安全性應用程式</span><span class="sxs-lookup"><span data-stu-id="de482-148">The Windows Security app</span></span>



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a><span data-ttu-id="de482-149">使用 PowerShell Cmdlet 執行離線掃描</span><span class="sxs-lookup"><span data-stu-id="de482-149">Use PowerShell cmdlets to run an offline scan</span></span>

<span data-ttu-id="de482-150">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="de482-150">Use the following cmdlets:</span></span>

```PowerShell
Start-MpWDOScan
```

<span data-ttu-id="de482-151">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/) 。</span><span class="sxs-lookup"><span data-stu-id="de482-151">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a><span data-ttu-id="de482-152">使用 Windows 管理指令 (WMI) 執行離線掃描</span><span class="sxs-lookup"><span data-stu-id="de482-152">Use Windows Management Instruction (WMI) to run an offline scan</span></span>

<span data-ttu-id="de482-153">使用 [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 類別執行離線掃描。</span><span class="sxs-lookup"><span data-stu-id="de482-153">Use the [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class to run an offline scan.</span></span>

<span data-ttu-id="de482-154">下列 WMI 腳本片段會立即執行 Microsoft Defender Offline 掃描，這會導致端點重新開機、執行離線掃描，然後重新開機並引導至 Windows。</span><span class="sxs-lookup"><span data-stu-id="de482-154">The following WMI script snippet will immediately run a Microsoft Defender Offline scan, which will cause the endpoint to restart, run the offline scan, and then restart and boot into Windows.</span></span>

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

<span data-ttu-id="de482-155">如需詳細資訊，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="de482-155">See the following for more information:</span></span>
- [<span data-ttu-id="de482-156">Windows DefenderWMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="de482-156">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a><span data-ttu-id="de482-157">使用 Windows Defender 安全性應用程式執行離線掃描</span><span class="sxs-lookup"><span data-stu-id="de482-157">Use the Windows Defender Security app to run an offline scan</span></span>

1. <span data-ttu-id="de482-158">按一下工作列中的盾牌圖示，或搜尋 **Defender** 的 [開始] 功能表，以開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="de482-158">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="de482-159">在左功能表列上，按一下 [ **病毒 & 威脅防護** 磚] (或盾牌圖示) ，然後按一下 [ **高級掃描** ] 標籤：</span><span class="sxs-lookup"><span data-stu-id="de482-159">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Advanced scan** label:</span></span>
    
3. <span data-ttu-id="de482-160">選取 [ **Microsoft Defender Offline 掃描**]，然後按一下 [**立即掃描**]。</span><span class="sxs-lookup"><span data-stu-id="de482-160">Select **Microsoft Defender Offline scan** and click **Scan now**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="de482-161">在 Windows 10 中，版本1607，可從 **Windows 設定**  >  **Update & security**  >  **Windows Defender** 或從 Windows Defender 用戶端執行離線掃描。</span><span class="sxs-lookup"><span data-stu-id="de482-161">In Windows 10, version 1607, the offline scan could be run from under **Windows Settings** > **Update & security** > **Windows Defender** or from the Windows Defender client.</span></span>


## <a name="review-scan-results"></a><span data-ttu-id="de482-162">查看掃描結果</span><span class="sxs-lookup"><span data-stu-id="de482-162">Review scan results</span></span>

<span data-ttu-id="de482-163">Microsoft Defender Offline 掃描結果將會列在[Windows 安全性應用程式的 [掃描記錄] 區段](microsoft-defender-security-center-antivirus.md)中。</span><span class="sxs-lookup"><span data-stu-id="de482-163">Microsoft Defender Offline scan results will be listed in the [Scan history section of the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> 


## <a name="related-articles"></a><span data-ttu-id="de482-164">相關文章</span><span class="sxs-lookup"><span data-stu-id="de482-164">Related articles</span></span>

- [<span data-ttu-id="de482-165">自訂、啟動和審查掃描和修正的結果</span><span class="sxs-lookup"><span data-stu-id="de482-165">Customize, initiate, and review the results of scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="de482-166">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="de482-166">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)