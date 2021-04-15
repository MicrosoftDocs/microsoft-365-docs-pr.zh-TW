---
title: 疑難排解網路保護的問題
description: 用於疑難排解 Microsoft Defender for Endpoint 中的網路保護問題的資源和範例程式碼。
keywords: 疑難排解，錯誤，修正，windows defender 例如，asr，rules，hips，疑難排解，審核，排除，錯誤正值，已中斷，封鎖，microsoft defender for endpoint，microsoft defender 高級威脅防護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 9efc42441c2cb30f35abf658071088f7f7bbaf00
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760095"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="8cdef-104">疑難排解網路保護</span><span class="sxs-lookup"><span data-stu-id="8cdef-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8cdef-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8cdef-105">**Applies to:**</span></span>
- [<span data-ttu-id="8cdef-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8cdef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8cdef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8cdef-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="8cdef-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8cdef-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8cdef-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="8cdef-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="8cdef-110">當您使用 [網路保護](network-protection.md) 時，可能會發生問題，例如：</span><span class="sxs-lookup"><span data-stu-id="8cdef-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="8cdef-111">網路保護會封鎖安全 (誤報) 的網站</span><span class="sxs-lookup"><span data-stu-id="8cdef-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="8cdef-112">網路保護無法封鎖可疑或已知惡意的網站 (false 負數) </span><span class="sxs-lookup"><span data-stu-id="8cdef-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="8cdef-113">疑難排解這些問題有四個步驟：</span><span class="sxs-lookup"><span data-stu-id="8cdef-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="8cdef-114">確認必要條件</span><span class="sxs-lookup"><span data-stu-id="8cdef-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="8cdef-115">使用稽核模式來測試規則</span><span class="sxs-lookup"><span data-stu-id="8cdef-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="8cdef-116">針對誤報) 新增指定之規則 (的排除</span><span class="sxs-lookup"><span data-stu-id="8cdef-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="8cdef-117">提交支援記錄檔</span><span class="sxs-lookup"><span data-stu-id="8cdef-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="8cdef-118">確認必要條件</span><span class="sxs-lookup"><span data-stu-id="8cdef-118">Confirm prerequisites</span></span>

<span data-ttu-id="8cdef-119">只有在下列情況下，網路保護才能在裝置上運作：</span><span class="sxs-lookup"><span data-stu-id="8cdef-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="8cdef-120">端點執行的是 Windows 10 專業版或 Enterprise edition 版本1709或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8cdef-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="8cdef-121">端點使用 Microsoft Defender 防病毒作為獨立的防防毒保護應用程式。</span><span class="sxs-lookup"><span data-stu-id="8cdef-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="8cdef-122">[請參閱使用非 Microsoft 防病毒方案時會發生什麼情況](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="8cdef-122">[See what happens when you are using a non-Microsoft antivirus solution](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="8cdef-123">已啟用[即時保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="8cdef-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="8cdef-124">已啟用[雲端傳送保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)功能。</span><span class="sxs-lookup"><span data-stu-id="8cdef-124">[Cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="8cdef-125">未啟用稽核模式。</span><span class="sxs-lookup"><span data-stu-id="8cdef-125">Audit mode is not enabled.</span></span> <span data-ttu-id="8cdef-126">使用 [群組原則](enable-network-protection.md#group-policy) 將規則設定為 **停用** (值： **0**) 。</span><span class="sxs-lookup"><span data-stu-id="8cdef-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="8cdef-127">使用稽核模式</span><span class="sxs-lookup"><span data-stu-id="8cdef-127">Use audit mode</span></span>

<span data-ttu-id="8cdef-128">您可以在稽核模式中啟用網路保護，然後再流覽我們所建立的網站，以示範該功能。</span><span class="sxs-lookup"><span data-stu-id="8cdef-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="8cdef-129">網路保護將允許所有的網站連線，但是會記錄事件，以指出在啟用網路保護時，任何已封鎖的連線。</span><span class="sxs-lookup"><span data-stu-id="8cdef-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="8cdef-130">將 [網路保護] 設定為 [ **稽核模式]**。</span><span class="sxs-lookup"><span data-stu-id="8cdef-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="8cdef-131">執行導致問題的連線活動 (例如，嘗試訪問網站，或連線至您要封鎖) 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8cdef-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="8cdef-132">[查看網路保護事件記錄](network-protection.md#review-network-protection-events-in-windows-event-viewer) 檔，以查看該功能是否已設定為 **啟用**，以查看該功能是否會封鎖連線。</span><span class="sxs-lookup"><span data-stu-id="8cdef-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="8cdef-133">如果網路保護未封鎖您期望它封鎖的連線，請啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="8cdef-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="8cdef-134">報告誤報或 false 負數</span><span class="sxs-lookup"><span data-stu-id="8cdef-134">Report a false positive or false negative</span></span>

<span data-ttu-id="8cdef-135">如果您已使用示範網站和審計模式來測試功能，且網路保護在預先設定的案例上運作，但沒有如預期的方式運作，請使用 [Windows Defender 安全性情報 web 提交表單](https://www.microsoft.com/wdsi/filesubmission) 報告誤報或 false 陽性的網路保護。</span><span class="sxs-lookup"><span data-stu-id="8cdef-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="8cdef-136">透過 E5 訂閱，您也可以 [提供任何相關聯警示的連結](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="8cdef-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="8cdef-137">請參閱 [Microsoft Defender For Endpoint 中的 Address false 陽性/負片](defender-endpoint-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="8cdef-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="8cdef-138">從網路保護範圍排除網站</span><span class="sxs-lookup"><span data-stu-id="8cdef-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="8cdef-139">若要允許封鎖的網站 (誤報) ，請將其 URL 新增至信任的 [網站清單](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)。</span><span class="sxs-lookup"><span data-stu-id="8cdef-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="8cdef-140">來自此清單的網頁資源略過網路保護檢查。</span><span class="sxs-lookup"><span data-stu-id="8cdef-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="8cdef-141">收集診斷資料以取得檔提交</span><span class="sxs-lookup"><span data-stu-id="8cdef-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="8cdef-142">當您報告網路保護的問題時，系統會要求您收集並提交可供 Microsoft 支援人員和工程團隊使用的診斷資料，以協助疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="8cdef-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="8cdef-143">開啟提升許可權的命令提示字元，並變更為 Windows Defender 目錄：</span><span class="sxs-lookup"><span data-stu-id="8cdef-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="8cdef-144">執行下列命令以產生診斷記錄：</span><span class="sxs-lookup"><span data-stu-id="8cdef-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="8cdef-145">將檔案附加到提交表單。</span><span class="sxs-lookup"><span data-stu-id="8cdef-145">Attach the file to the submission form.</span></span> <span data-ttu-id="8cdef-146">根據預設，診斷記錄會儲存在 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。</span><span class="sxs-lookup"><span data-stu-id="8cdef-146">By default, diagnostic logs are saved at `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a><span data-ttu-id="8cdef-147">解決 (E5 客戶之網路保護的連線問題) </span><span class="sxs-lookup"><span data-stu-id="8cdef-147">Resolve connectivity issues with network protection (for E5 customers)</span></span>

<span data-ttu-id="8cdef-148">由於網路保護的執行環境，Microsoft 無法看到您的作業系統 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="8cdef-148">Due to the environment where network protection runs, Microsoft is unable to see your operating system proxy settings.</span></span> <span data-ttu-id="8cdef-149">在某些情況下，網路保護用戶端無法到達雲端服務。</span><span class="sxs-lookup"><span data-stu-id="8cdef-149">In some cases, network protection clients are unable to reach the cloud service.</span></span> <span data-ttu-id="8cdef-150">若要解決網路保護的連線問題，請設定下列其中一個登錄機碼，讓網路防護知道 proxy 設定：</span><span class="sxs-lookup"><span data-stu-id="8cdef-150">To resolve connectivity issues with network protection, configure one of the following registry keys so that network protection becomes aware of the proxy configuration:</span></span>

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

<span data-ttu-id="8cdef-151">---或---</span><span class="sxs-lookup"><span data-stu-id="8cdef-151">---OR---</span></span>


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

<span data-ttu-id="8cdef-152">您可以使用 [PowerShell]、[Microsoft 端點管理員] 或「群組原則」來設定登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="8cdef-152">You can configure the registry key by using PowerShell, Microsoft Endpoint Manager, or Group Policy.</span></span> <span data-ttu-id="8cdef-153">以下是一些可協助的資源：</span><span class="sxs-lookup"><span data-stu-id="8cdef-153">Here are some resources to help:</span></span>
- [<span data-ttu-id="8cdef-154">使用登錄機碼</span><span class="sxs-lookup"><span data-stu-id="8cdef-154">Working with Registry Keys</span></span>](/powershell/scripting/samples/working-with-registry-keys)
- [<span data-ttu-id="8cdef-155">設定 Endpoint Protection 的自訂用戶端設定</span><span class="sxs-lookup"><span data-stu-id="8cdef-155">Configure custom client settings for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [<span data-ttu-id="8cdef-156">使用群組原則設定來管理 Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="8cdef-156">Use Group Policy settings to manage Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a><span data-ttu-id="8cdef-157">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8cdef-157">See also</span></span>

- [<span data-ttu-id="8cdef-158">網路保護</span><span class="sxs-lookup"><span data-stu-id="8cdef-158">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="8cdef-159">評估網路保護</span><span class="sxs-lookup"><span data-stu-id="8cdef-159">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="8cdef-160">啟用網路保護</span><span class="sxs-lookup"><span data-stu-id="8cdef-160">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="8cdef-161">在 Defender 中為端點處理誤報/負片</span><span class="sxs-lookup"><span data-stu-id="8cdef-161">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
