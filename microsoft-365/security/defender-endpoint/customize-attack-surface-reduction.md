---
title: 自訂受攻擊面縮小規則
description: 個別設定審核、封鎖或已停用模式中的規則，以及新增應從攻擊面減少規則排除的檔案和資料夾
keywords: 攻擊面減少，hips，主機入侵防護系統，保護規則，反惡意攻擊，antiexploit，exploit，感染防護，自訂，設定，排除
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: c03bc2a61ba2dae1b5db34c6b48d623c58c0c613
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782870"
---
# <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="6fcb6-104">自訂受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="6fcb6-104">Customize attack surface reduction rules</span></span>

<span data-ttu-id="6fcb6-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="6fcb6-105">**Applies to:**</span></span>
- [<span data-ttu-id="6fcb6-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6fcb6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6fcb6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6fcb6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6fcb6-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6fcb6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6fcb6-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="6fcb6-110">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6fcb6-111">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6fcb6-112">[攻擊面減少規則](enable-attack-surface-reduction.md) 可協助避免經常濫用的軟體行為，損害您的裝置或網路。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-112">[Attack surface reduction rules](enable-attack-surface-reduction.md) help prevent software behaviors that are often abused to compromise your device or network.</span></span> <span data-ttu-id="6fcb6-113">例如，攻擊者可能會嘗試從 USB 磁片磁碟機關閉未簽署的腳本，或是 Office 檔中的宏直接撥打 WIN32 API。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-113">For example, an attacker might try to run an unsigned script off of a USB drive, or have a macro in an Office document make calls directly to the Win32 API.</span></span> <span data-ttu-id="6fcb6-114">攻擊面減少規則可限制這些類型的危險行為，並改善組織的防禦性狀況。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-114">Attack surface reduction rules can constrain these kinds of risky behaviors and improve your organization's defensive posture.</span></span>

<span data-ttu-id="6fcb6-115">瞭解如何自訂攻擊面減少規則，方法是 [排除檔案和資料夾](#exclude-files-and-folders) ，或 [將自訂文字新增至](#customize-the-notification) 使用者電腦上出現的通知警示。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-115">Learn how to customize attack surface reduction rules by [excluding files and folders](#exclude-files-and-folders) or [adding custom text to the notification](#customize-the-notification) alert that appears on a user's computer.</span></span>

<span data-ttu-id="6fcb6-116">您可以針對執行下列任何版本和版本的裝置，設定攻擊面減少規則 Windows：</span><span class="sxs-lookup"><span data-stu-id="6fcb6-116">You can set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="6fcb6-117">Windows 10 專業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="6fcb6-117">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="6fcb6-118">Windows 10 企業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="6fcb6-118">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="6fcb6-119">Windows伺服器，[版本 1803 (半年通道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更新版本</span><span class="sxs-lookup"><span data-stu-id="6fcb6-119">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- <span data-ttu-id="6fcb6-120">[Windows Server 2019](/windows-server/get-started-19/whats-new-19)您可以使用「群組原則」、「PowerShell」和「行動裝置管理」 (MDM) 設定服務提供者 (CSP) 來設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-120">[Windows Server 2019](/windows-server/get-started-19/whats-new-19) You can use Group Policy, PowerShell, and Mobile Device Management (MDM) configuration service providers (CSP) to configure these settings.</span></span>

## <a name="exclude-files-and-folders"></a><span data-ttu-id="6fcb6-121">排除檔案和資料夾</span><span class="sxs-lookup"><span data-stu-id="6fcb6-121">Exclude files and folders</span></span>

<span data-ttu-id="6fcb6-122">您可以選擇排除受攻擊面降低規則所評估的檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-122">You can choose to exclude files and folders from being evaluated by attack surface reduction rules.</span></span> <span data-ttu-id="6fcb6-123">排除之後，即使攻擊面降低規則偵測到該檔案包含惡意行為，檔案也不會執行封鎖。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-123">Once excluded, the file won't be blocked from running even if an attack surface reduction rule detects that the file contains malicious behavior.</span></span>

<span data-ttu-id="6fcb6-124">例如，您會考慮勒索軟體的以下規則：</span><span class="sxs-lookup"><span data-stu-id="6fcb6-124">For example, consider the ransomware rule:</span></span>

<span data-ttu-id="6fcb6-125">勒索軟體的原則是專門設計用來協助企業客戶降低勒索軟體攻擊的風險，同時確保商務持續性。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-125">The ransomware rule is designed to help enterprise customers reduce risks of ransomware attacks while ensuring business continuity.</span></span> <span data-ttu-id="6fcb6-126">根據預設，勒索軟體規則會在警告的兩側發生錯誤，並防止尚未具備足夠信譽和信任的檔案。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-126">By default, the ransomware rule will error on the side of caution and protect against files that haven't yet attained sufficient reputation and trust.</span></span> <span data-ttu-id="6fcb6-127">若要 reemphasize，勒索軟體規則只會觸發未獲得足夠肯定信譽和流行的檔案，根據數百萬客戶的使用量計量。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-127">To reemphasize, the ransomware rule only triggers on files that have not gained enough positive reputation and prevalence, based on usage metrics of millions of our customers.</span></span> <span data-ttu-id="6fcb6-128">通常，區塊會自行解決，因為每個檔案的「信譽和信任」值會隨著非問題的使用量而逐漸升級。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-128">Usually, the blocks are self resolved, because each file's “reputation and trust” values are incrementally upgraded as non-problematic usage increases.</span></span>

<span data-ttu-id="6fcb6-129">在未及時解決區塊問題的情況下，客戶 _可以自行解決問題：使用_ 自助服務機制或損害指示器 (IOC) 型「允許清單」功能，自行解除封鎖檔。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-129">In cases in which blocks aren’t self resolved in a timely manner, customers can - _at their own risk_ - make use of either the self-service mechanism or an Indicator of Compromise (IOC)-based "allow list" capability to unblock the files themselves.</span></span>  

> [!WARNING]
> <span data-ttu-id="6fcb6-130">排除或取消阻止檔案或資料夾可能會允許不安全的檔案執行並感染您的裝置。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-130">Excluding or unblocking files or folders could potentially allow unsafe files to run and infect your devices.</span></span> <span data-ttu-id="6fcb6-131">排除檔案或資料夾可能會嚴重降低受攻擊面縮小規則所提供的保護。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-131">Excluding files or folders can severely reduce the protection provided by attack surface reduction rules.</span></span> <span data-ttu-id="6fcb6-132">會允許執行已被規則封鎖的檔案，而且不會記錄任何報表或事件。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-132">Files that would have been blocked by a rule will be allowed to run, and there will be no report or event recorded.</span></span>

<span data-ttu-id="6fcb6-133">排除會套用到允許排除的所有規則。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-133">An exclusion applies to all rules that allow exclusions.</span></span> <span data-ttu-id="6fcb6-134">您可以指定個別的檔案、資料夾路徑或資源的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-134">You can specify an individual file, folder path, or the fully qualified domain name for a resource.</span></span> <span data-ttu-id="6fcb6-135">不過，您無法限制特定規則的排除。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-135">However, you cannot limit an exclusion to a specific rule.</span></span>

<span data-ttu-id="6fcb6-136">只有在已排除的應用程式或服務啟動時，才會套用排除。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-136">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="6fcb6-137">例如，如果您為已在執行的更新服務新增排除，更新服務會繼續觸發事件，直到停止並重新啟動服務為止。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-137">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="6fcb6-138">攻擊面減少支援環境變數和萬用字元。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-138">Attack surface reduction supports environment variables and wildcards.</span></span> <span data-ttu-id="6fcb6-139">如需使用萬用字元的詳細資訊，請參閱 [在檔案名和資料夾路徑或副檔名排除清單中使用萬用字元](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-139">For information about using wildcards, see [use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) .</span></span>
<span data-ttu-id="6fcb6-140">如果您遇到的錯誤偵測不應該偵測到的檔案，請 [使用稽核模式來測試規則](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-140">If you are encountering problems with rules detecting files that you believe should not be detected, [use audit mode to test the rule](evaluate-attack-surface-reduction.md).</span></span>

| <span data-ttu-id="6fcb6-141">規則說明</span><span class="sxs-lookup"><span data-stu-id="6fcb6-141">Rule description</span></span> | <span data-ttu-id="6fcb6-142">GUID</span><span class="sxs-lookup"><span data-stu-id="6fcb6-142">GUID</span></span> |
|:----|:----|
| <span data-ttu-id="6fcb6-143">封鎖所有 Office 的應用程式建立子流程</span><span class="sxs-lookup"><span data-stu-id="6fcb6-143">Block all Office applications from creating child processes</span></span> | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` |
| <span data-ttu-id="6fcb6-144">封鎖可能混淆的腳本執行</span><span class="sxs-lookup"><span data-stu-id="6fcb6-144">Block execution of potentially obfuscated scripts</span></span> | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` |
| <span data-ttu-id="6fcb6-145">從 Office 宏封鎖 WIN32 API 呼叫</span><span class="sxs-lookup"><span data-stu-id="6fcb6-145">Block Win32 API calls from Office macro</span></span> | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` |
| <span data-ttu-id="6fcb6-146">封鎖 Office 應用程式建立可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="6fcb6-146">Block Office applications from creating executable content</span></span> | `3B576869-A4EC-4529-8536-B80A7769E899` |
| <span data-ttu-id="6fcb6-147">封鎖 Office 的應用程式將程式碼注入其他進程</span><span class="sxs-lookup"><span data-stu-id="6fcb6-147">Block Office applications from injecting code into other processes</span></span> | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` |
| <span data-ttu-id="6fcb6-148">從啟動下載的可執行內容封鎖 JavaScript 或 VBScript</span><span class="sxs-lookup"><span data-stu-id="6fcb6-148">Block JavaScript or VBScript from launching downloaded executable content</span></span> | `D3E037E1-3EB8-44C8-A917-57927947596D` |
| <span data-ttu-id="6fcb6-149">從電子郵件客戶程式和 web 郵件封鎖可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="6fcb6-149">Block executable content from email client and webmail</span></span> | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` |
| <span data-ttu-id="6fcb6-150">封鎖可執行檔，除非符合流行、age 或受信任的清單準則</span><span class="sxs-lookup"><span data-stu-id="6fcb6-150">Block executable files from running unless they meet a prevalence, age, or trusted list criteria</span></span> | `01443614-cd74-433a-b99e-2ecdc07bfc25` |
| <span data-ttu-id="6fcb6-151">使用勒索軟體的高級防護</span><span class="sxs-lookup"><span data-stu-id="6fcb6-151">Use advanced protection against ransomware</span></span> | `c1db55ab-c21a-4637-bb3f-a12568109d35` |
| <span data-ttu-id="6fcb6-152">封鎖 Windows 本機安全性群組子系統 (lsass.exe 中的認證竊取) </span><span class="sxs-lookup"><span data-stu-id="6fcb6-152">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span> | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` |
| <span data-ttu-id="6fcb6-153">封鎖來自 PSExec 和 WMI 命令的進程建立</span><span class="sxs-lookup"><span data-stu-id="6fcb6-153">Block process creations originating from PSExec and WMI commands</span></span> | `d1e49aac-8f56-4280-b9ba-993a6d77406c` |
| <span data-ttu-id="6fcb6-154">封鎖從 USB 執行的不受信任和未簽署程式</span><span class="sxs-lookup"><span data-stu-id="6fcb6-154">Block untrusted and unsigned processes that run from USB</span></span> | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` |
| <span data-ttu-id="6fcb6-155">封鎖 Office 的通訊應用程式以建立子流程</span><span class="sxs-lookup"><span data-stu-id="6fcb6-155">Block Office communication applications from creating child processes</span></span> | `26190899-1602-49e8-8b27-eb1d0a1ce869` |
| <span data-ttu-id="6fcb6-156">封鎖 Adobe Reader，以建立子流程</span><span class="sxs-lookup"><span data-stu-id="6fcb6-156">Block Adobe Reader from creating child processes</span></span> | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` |
| <span data-ttu-id="6fcb6-157">透過 WMI 事件訂閱封鎖持久性</span><span class="sxs-lookup"><span data-stu-id="6fcb6-157">Block persistence through WMI event subscription</span></span> | `e6db77e5-3df2-4cf1-b95a-636979351e5b` |

<span data-ttu-id="6fcb6-158">如需每個規則的詳細資訊，請參閱 [攻擊面減少](attack-surface-reduction.md) 主題。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-158">See the [attack surface reduction](attack-surface-reduction.md) topic for details on each rule.</span></span>

### <a name="use-group-policy-to-exclude-files-and-folders"></a><span data-ttu-id="6fcb6-159">使用群組原則排除檔案和資料夾</span><span class="sxs-lookup"><span data-stu-id="6fcb6-159">Use Group Policy to exclude files and folders</span></span>

1. <span data-ttu-id="6fcb6-160">在您的群組原則管理電腦上，開啟 [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)，以滑鼠右鍵按一下您要設定的群組原則物件，然後選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-160">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="6fcb6-161">在 [**群組原則管理編輯器**] 中，移至 [電腦設定]，然後按一下 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-161">In the **Group Policy Management Editor**, go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="6fcb6-162">展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **Windows Defender Exploit Guard**  >  **攻擊面降低**。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-162">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="6fcb6-163">按兩下 [排除檔案 **和攻擊面減規則的路徑** ] 設定，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-163">Double-click the **Exclude files and paths from Attack surface reduction Rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="6fcb6-164">選取 [ **顯示** ]，然後在 [ **值名稱** ] 欄位中輸入每個檔案或資料夾。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-164">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="6fcb6-165">在 [**值**] 欄中，為每個專案輸入 **0** 。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-165">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="6fcb6-166">請勿使用 " **值名稱** ] 欄或 [ **值** ] 欄中不支援的引號。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-166">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

### <a name="use-powershell-to-exclude-files-and-folders"></a><span data-ttu-id="6fcb6-167">使用 PowerShell 排除檔案和資料夾</span><span class="sxs-lookup"><span data-stu-id="6fcb6-167">Use PowerShell to exclude files and folders</span></span>

1. <span data-ttu-id="6fcb6-168">在 [開始] 功能表中輸入 **powershell** ，以滑鼠右鍵按一下 **Windows PowerShell** 並選取 [以 **系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="6fcb6-168">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="6fcb6-169">輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6fcb6-169">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

<span data-ttu-id="6fcb6-170">繼續使用將 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 更多資料夾新增至清單。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-170">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more folders to the list.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fcb6-171">用於 `Add-MpPreference` 附加或新增應用程式至清單。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-171">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="6fcb6-172">使用此 `Set-MpPreference` Cmdlet 將會覆寫現有清單。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-172">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a><span data-ttu-id="6fcb6-173">使用 MDM Csp 排除檔案和資料夾</span><span class="sxs-lookup"><span data-stu-id="6fcb6-173">Use MDM CSPs to exclude files and folders</span></span>

<span data-ttu-id="6fcb6-174">使用 [/Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service PROVIDER (CSP) 新增排除專案。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-174">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="6fcb6-175">自訂通知</span><span class="sxs-lookup"><span data-stu-id="6fcb6-175">Customize the notification</span></span>

<span data-ttu-id="6fcb6-176">您可以自訂觸發規則的通知，並封鎖應用程式或檔案。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-176">You can customize the notification for when a rule is triggered and blocks an app or file.</span></span> <span data-ttu-id="6fcb6-177">請參閱[Windows 安全性](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)文章。</span><span class="sxs-lookup"><span data-stu-id="6fcb6-177">See the [Windows Security](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) article.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6fcb6-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="6fcb6-178">Related topics</span></span>

* [<span data-ttu-id="6fcb6-179">使用攻擊面減少規則來減少攻擊面</span><span class="sxs-lookup"><span data-stu-id="6fcb6-179">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="6fcb6-180">啟用受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="6fcb6-180">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
* [<span data-ttu-id="6fcb6-181">評估受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="6fcb6-181">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
* [<span data-ttu-id="6fcb6-182">受攻擊面縮小常見問題集</span><span class="sxs-lookup"><span data-stu-id="6fcb6-182">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
