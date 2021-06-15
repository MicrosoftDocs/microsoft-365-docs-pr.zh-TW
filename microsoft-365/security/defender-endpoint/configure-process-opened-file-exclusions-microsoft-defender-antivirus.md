---
title: 設定特定進程開啟之檔案的排除專案
description: 您可以從掃描中排除檔案（如果這些檔案已由特定進程開啟）。
keywords: Microsoft Defender 防毒軟體、處理、排除、檔案、掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 0470f4f03ba5fd6fc768a1e652f51b8c44207107
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925548"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a><span data-ttu-id="2c489-104">設定處理常式開啟之檔案的排除專案</span><span class="sxs-lookup"><span data-stu-id="2c489-104">Configure exclusions for files opened by processes</span></span>


<span data-ttu-id="2c489-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2c489-105">**Applies to:**</span></span>

- [<span data-ttu-id="2c489-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2c489-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2c489-107">您可以從 Microsoft Defender 防毒軟體掃描中排除特定進程已開啟的檔案。</span><span class="sxs-lookup"><span data-stu-id="2c489-107">You can exclude files that have been opened by specific processes from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="2c489-108">定義排除清單之前，請參閱[建議以定義](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)排除清單。</span><span class="sxs-lookup"><span data-stu-id="2c489-108">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

<span data-ttu-id="2c489-109">本文說明如何設定排除清單。</span><span class="sxs-lookup"><span data-stu-id="2c489-109">This article describes how to configure exclusion lists.</span></span> 

## <a name="examples-of-exclusions"></a><span data-ttu-id="2c489-110">排除的範例</span><span class="sxs-lookup"><span data-stu-id="2c489-110">Examples of exclusions</span></span>

|<span data-ttu-id="2c489-111">排除</span><span class="sxs-lookup"><span data-stu-id="2c489-111">Exclusion</span></span> | <span data-ttu-id="2c489-112">範例</span><span class="sxs-lookup"><span data-stu-id="2c489-112">Example</span></span> |
|---|---|
|<span data-ttu-id="2c489-113">電腦上任何具有特定檔案名之進程所開啟的檔案</span><span class="sxs-lookup"><span data-stu-id="2c489-113">Any file on the machine that is opened by any process with a specific file name</span></span> | <span data-ttu-id="2c489-114">指定 `test.exe` 會排除以下列方式開啟的檔案：</span><span class="sxs-lookup"><span data-stu-id="2c489-114">Specifying `test.exe` would exclude files opened by:</span></span> <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|<span data-ttu-id="2c489-115">電腦上的任何檔案，由特定資料夾下的任何處理程式開啟</span><span class="sxs-lookup"><span data-stu-id="2c489-115">Any file on the machine that is opened by any process under a specific folder</span></span> | <span data-ttu-id="2c489-116">指定 `c:\test\sample\*` 會排除以下列方式開啟的檔案：</span><span class="sxs-lookup"><span data-stu-id="2c489-116">Specifying `c:\test\sample\*` would exclude files opened by:</span></span><br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|<span data-ttu-id="2c489-117">電腦上特定資料夾中特定進程所開啟的任何檔案</span><span class="sxs-lookup"><span data-stu-id="2c489-117">Any file on the machine that is opened by a specific process in a specific folder</span></span> | <span data-ttu-id="2c489-118">指定 `c:\test\process.exe` 會排除只開啟的檔案 `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="2c489-118">Specifying `c:\test\process.exe` would exclude files only opened by `c:\test\process.exe`</span></span> |


<span data-ttu-id="2c489-119">當您在程式排除清單中新增程式時，Microsoft Defender 防毒軟體不會掃描由該進程所開啟的檔案，不論檔案位於何處。</span><span class="sxs-lookup"><span data-stu-id="2c489-119">When you add a process to the process exclusion list, Microsoft Defender Antivirus won't scan files opened by that process, no matter where the files are located.</span></span> <span data-ttu-id="2c489-120">不過，系統會先掃描此程式，除非該程式也已新增至 [檔排除清單](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="2c489-120">The process itself, however, will be scanned unless it has also been added to the [file exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="2c489-121">[排除] 只適用于 [永不間斷的即時保護和監控](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="2c489-121">The exclusions only apply to [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="2c489-122">它們不適用於排程或隨選的掃描。</span><span class="sxs-lookup"><span data-stu-id="2c489-122">They don't apply to scheduled or on-demand scans.</span></span>

<span data-ttu-id="2c489-123">使用群組原則對排除清單所做的變更，**會顯示** 在 [Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)的清單中。</span><span class="sxs-lookup"><span data-stu-id="2c489-123">Changes made with Group Policy to the exclusion lists **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="2c489-124">不過，在 Windows 安全性應用程式中所做的變更 **將不會顯示** 在 [群組原則] 清單中。</span><span class="sxs-lookup"><span data-stu-id="2c489-124">However, changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="2c489-125">您可以新增、移除及檢查群組原則中排除專案的清單、Microsoft Endpoint Configuration Manager、Microsoft Intune 和 Windows 安全性應用程式，也可以使用萬用字元進一步自訂清單。</span><span class="sxs-lookup"><span data-stu-id="2c489-125">You can add, remove, and review the lists for exclusions in Group Policy, Microsoft Endpoint Configuration Manager, Microsoft Intune, and with the Windows Security app, and you can use wildcards to further customize the lists.</span></span>

<span data-ttu-id="2c489-126">您也可以使用 PowerShell Cmdlet 和 WMI 來設定排除清單，包括複查清單。</span><span class="sxs-lookup"><span data-stu-id="2c489-126">You can also use PowerShell cmdlets and WMI to configure the exclusion lists, including reviewing your lists.</span></span>

<span data-ttu-id="2c489-127">依預設，具有系統管理員許可權之使用者 (清單的本機變更;使用 PowerShell 和 WMI) 所做的變更，會隨著群組原則、設定管理員或 Intune 的定義 (和部署) ，與清單合併。</span><span class="sxs-lookup"><span data-stu-id="2c489-127">By default, local changes made to the lists (by users with administrator privileges; changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="2c489-128">群組原則清單會在衝突的情況下優先。</span><span class="sxs-lookup"><span data-stu-id="2c489-128">The Group Policy lists will take precedence in the case of conflicts.</span></span>

<span data-ttu-id="2c489-129">您可以 [設定如何合併本機和全域定義的排除清單](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) ，以允許本機變更覆寫受管理的部署設定。</span><span class="sxs-lookup"><span data-stu-id="2c489-129">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a><span data-ttu-id="2c489-130">針對由指定的程式開啟的檔案，設定排除清單</span><span class="sxs-lookup"><span data-stu-id="2c489-130">Configure the list of exclusions for files opened by specified processes</span></span>

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="2c489-131">使用 Microsoft Intune 排除已由指定的程式從掃描中開啟的檔案</span><span class="sxs-lookup"><span data-stu-id="2c489-131">Use Microsoft Intune to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="2c489-132">請參閱 [《在 Microsoft Intune 中設定裝置限制設定》](/intune/device-restrictions-configure) 及 [《Windows 10 中 Intune 的 Microsoft Defender 防毒軟體裝置限制設定》](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 了解詳情。</span><span class="sxs-lookup"><span data-stu-id="2c489-132">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="2c489-133">使用 Microsoft 端點管理員排除已由指定的程式從掃描中開啟的檔案</span><span class="sxs-lookup"><span data-stu-id="2c489-133">Use Microsoft Endpoint Manager to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="2c489-134">請參閱[如何建立及部署反惡意程式碼原則：設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)Microsoft 端點管理員 (目前分支) 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2c489-134">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="2c489-135">使用群組原則來排除已由指定的進程從掃描開啟的檔案</span><span class="sxs-lookup"><span data-stu-id="2c489-135">Use Group Policy to exclude files that have been opened by specified processes from scans</span></span>

1. <span data-ttu-id="2c489-136">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2c489-136">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="2c489-137">在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="2c489-137">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="2c489-138">展開樹狀目錄， **Windows 元件 > Microsoft Defender 防毒軟體 > 排除** 專案。</span><span class="sxs-lookup"><span data-stu-id="2c489-138">Expand the tree to **Windows components > Microsoft Defender Antivirus > Exclusions**.</span></span>

4. <span data-ttu-id="2c489-139">按兩下 [ **處理常式排除** ]，並新增排除專案：</span><span class="sxs-lookup"><span data-stu-id="2c489-139">Double-click **Process Exclusions** and add the exclusions:</span></span>

    1. <span data-ttu-id="2c489-140">將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="2c489-140">Set the option to **Enabled**.</span></span>
    2. <span data-ttu-id="2c489-141">在 [ **選項** ] 區段中，按一下 [ **顯示 ...**]。</span><span class="sxs-lookup"><span data-stu-id="2c489-141">Under the **Options** section, click **Show...**.</span></span>
    3. <span data-ttu-id="2c489-142">在 [ **值名稱** ] 欄底下，于各自的行上輸入每個程式。</span><span class="sxs-lookup"><span data-stu-id="2c489-142">Enter each process on its own line under the **Value name** column.</span></span> <span data-ttu-id="2c489-143">請參閱範例表格，以瞭解不同的程式排除類型。</span><span class="sxs-lookup"><span data-stu-id="2c489-143">See the example table for the different types of process exclusions.</span></span>  <span data-ttu-id="2c489-144">在 [**值**] 欄中輸入 [所有處理常式] 的 [ **0** ]。</span><span class="sxs-lookup"><span data-stu-id="2c489-144">Enter **0** in the **Value** column for all processes.</span></span>

5. <span data-ttu-id="2c489-145">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="2c489-145">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="2c489-146">使用 PowerShell Cmdlet 來排除已由指定的進程從掃描開啟的檔案</span><span class="sxs-lookup"><span data-stu-id="2c489-146">Use PowerShell cmdlets to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="2c489-147">使用 PowerShell 新增或移除已由進程開啟之檔案的排除專案時，需要使用三個 Cmdlet 搭配 `-ExclusionProcess` 參數。</span><span class="sxs-lookup"><span data-stu-id="2c489-147">Using PowerShell to add or remove exclusions for files that have been opened by processes requires using a combination of three cmdlets with the `-ExclusionProcess` parameter.</span></span> <span data-ttu-id="2c489-148">Cmdlet 全都位於 [Defender 模組](/powershell/module/defender/)中。</span><span class="sxs-lookup"><span data-stu-id="2c489-148">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="2c489-149">Cmdlet 的格式為：</span><span class="sxs-lookup"><span data-stu-id="2c489-149">The format for the cmdlets is:</span></span>

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

<span data-ttu-id="2c489-150">下列專案是允許的 \<cmdlet> ：</span><span class="sxs-lookup"><span data-stu-id="2c489-150">The following are allowed as the \<cmdlet>:</span></span>

|<span data-ttu-id="2c489-151">設定動作</span><span class="sxs-lookup"><span data-stu-id="2c489-151">Configuration action</span></span> | <span data-ttu-id="2c489-152">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2c489-152">PowerShell cmdlet</span></span> |
|---|---|
|<span data-ttu-id="2c489-153">建立或覆寫清單</span><span class="sxs-lookup"><span data-stu-id="2c489-153">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="2c489-154">新增至清單</span><span class="sxs-lookup"><span data-stu-id="2c489-154">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="2c489-155">從清單中移除專案</span><span class="sxs-lookup"><span data-stu-id="2c489-155">Remove items from the list</span></span> | `Remove-MpPreference` |

>[!IMPORTANT]
><span data-ttu-id="2c489-156">如果您已建立清單，請使用 `Set-MpPreference` 或 `Add-MpPreference` 再次使用 Cmdlet， `Set-MpPreference` 將覆寫現有清單。</span><span class="sxs-lookup"><span data-stu-id="2c489-156">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="2c489-157">例如，下列程式碼段會導致 Microsoft Defender AV 掃描排除指定程式所開啟的任何檔案：</span><span class="sxs-lookup"><span data-stu-id="2c489-157">For example, the following code snippet would cause Microsoft Defender AV scans to exclude any file that is opened by the specified process:</span></span>

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

<span data-ttu-id="2c489-158">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱使用 PowerShell Cmdlet 及[Microsoft Defender 防毒軟體 Cmdlet](/powershell/module/defender)管理防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="2c489-158">For more information on how to use PowerShell with Microsoft Defender Antivirus, see Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span></span>

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="2c489-159">使用 Windows 管理指令 (WMI) ，以排除已由指定的進程從掃描開啟的檔案</span><span class="sxs-lookup"><span data-stu-id="2c489-159">Use Windows Management Instruction (WMI) to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="2c489-160">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set**、 **Add** 和 **Remove** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="2c489-160">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionProcess
```

<span data-ttu-id="2c489-161">[ **設定**]、[ **新增**] 和 [ **移除** ] 的使用與其在 PowerShell:、] 和中的對等專案類似 `Set-MpPreference` `Add-MpPreference` `Remove-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="2c489-161">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="2c489-162">如需詳細資訊及允許的參數，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="2c489-162">For more information and allowed parameters, see  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="2c489-163">使用 Windows 安全性應用程式排除已由指定的進程從掃描開啟的檔案</span><span class="sxs-lookup"><span data-stu-id="2c489-163">Use the Windows Security app to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="2c489-164">如需相關指示，請參閱[Add Windows 安全性 app 中的排除](microsoft-defender-security-center-antivirus.md)專案。</span><span class="sxs-lookup"><span data-stu-id="2c489-164">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

## <a name="use-wildcards-in-the-process-exclusion-list"></a><span data-ttu-id="2c489-165">在進程排除清單中使用萬用字元</span><span class="sxs-lookup"><span data-stu-id="2c489-165">Use wildcards in the process exclusion list</span></span>

<span data-ttu-id="2c489-166">在處理常式排除清單中使用萬用字元，與在其他排除清單中使用的順序不同。</span><span class="sxs-lookup"><span data-stu-id="2c489-166">The use of wildcards in the process exclusion list is different from their use in other exclusion lists.</span></span>

<span data-ttu-id="2c489-167">具體說來，您無法使用問號 (`?`) 萬用字元，而且星號 (`*`) 萬用字元只會在完整路徑的結尾使用。</span><span class="sxs-lookup"><span data-stu-id="2c489-167">In particular, you cannot use the question mark (`?`) wildcard, and the asterisk (`*`) wildcard can only be used at the end of a complete path.</span></span> <span data-ttu-id="2c489-168">在程式排除清單中定義專案時，您仍然可以使用環境變數 (例如 `%ALLUSERSPROFILE%`) 做為萬用字元。</span><span class="sxs-lookup"><span data-stu-id="2c489-168">You can still use environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the process exclusion list.</span></span>

<span data-ttu-id="2c489-169">下表說明如何在進程排除清單中使用萬用字元：</span><span class="sxs-lookup"><span data-stu-id="2c489-169">The following table describes how the wildcards can be used in the process exclusion list:</span></span>

|<span data-ttu-id="2c489-170">萬用字元</span><span class="sxs-lookup"><span data-stu-id="2c489-170">Wildcard</span></span> | <span data-ttu-id="2c489-171">範例使用</span><span class="sxs-lookup"><span data-stu-id="2c489-171">Example use</span></span> | <span data-ttu-id="2c489-172">範例符合</span><span class="sxs-lookup"><span data-stu-id="2c489-172">Example matches</span></span> |
|:---|:---|:---|
|<span data-ttu-id="2c489-173">`*` (星號) </span><span class="sxs-lookup"><span data-stu-id="2c489-173">`*` (asterisk)</span></span> <br/><br/> <span data-ttu-id="2c489-174">會取代任何數目的字元</span><span class="sxs-lookup"><span data-stu-id="2c489-174">Replaces any number of characters</span></span> | `C:\MyData\*` | <span data-ttu-id="2c489-175">任何開啟的檔案 `C:\MyData\file.exe`</span><span class="sxs-lookup"><span data-stu-id="2c489-175">Any file opened by `C:\MyData\file.exe`</span></span> |
|<span data-ttu-id="2c489-176">環境變數</span><span class="sxs-lookup"><span data-stu-id="2c489-176">Environment variables</span></span> <br/><br/> <span data-ttu-id="2c489-177">在評估排除時，已定義的變數會填入為路徑</span><span class="sxs-lookup"><span data-stu-id="2c489-177">The defined variable is populated as a path when the exclusion is evaluated</span></span> | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | <span data-ttu-id="2c489-178">任何開啟的檔案 `C:\ProgramData\CustomLogFiles\file.exe`</span><span class="sxs-lookup"><span data-stu-id="2c489-178">Any file opened by `C:\ProgramData\CustomLogFiles\file.exe`</span></span> |

## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="2c489-179">審閱排除清單</span><span class="sxs-lookup"><span data-stu-id="2c489-179">Review the list of exclusions</span></span>

<span data-ttu-id="2c489-180">您可以使用 MpCmdRun、PowerShell、 [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)、 [Intune](/intune/device-restrictions-configure)或[Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)，在排除清單中取得專案。</span><span class="sxs-lookup"><span data-stu-id="2c489-180">You can retrieve the items in the exclusion list with MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure), or the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

<span data-ttu-id="2c489-181">如果您使用 PowerShell，您可以使用下列兩種方式來找回清單：</span><span class="sxs-lookup"><span data-stu-id="2c489-181">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="2c489-182">取得所有 Microsoft Defender 防毒軟體首選項的狀態。</span><span class="sxs-lookup"><span data-stu-id="2c489-182">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="2c489-183">每個清單都會顯示在不同的行上，但是每個清單中的專案會組合成同一行。</span><span class="sxs-lookup"><span data-stu-id="2c489-183">Each of the lists will be displayed on separate lines, but the items within each list will be combined into the same line.</span></span>
- <span data-ttu-id="2c489-184">將所有喜好設定的狀態寫入變數中，並使用該變數只呼叫您感興趣的特定清單。</span><span class="sxs-lookup"><span data-stu-id="2c489-184">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="2c489-185">每次使用 `Add-MpPreference` 都會寫入新行。</span><span class="sxs-lookup"><span data-stu-id="2c489-185">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="2c489-186">使用 MpCmdRun 驗證排除清單</span><span class="sxs-lookup"><span data-stu-id="2c489-186">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="2c489-187">若要使用專用 [命令列工具 mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)檢查排除，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="2c489-187">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> <span data-ttu-id="2c489-188">檢查包含 MpCmdRun 的排除專案時，需要 (2018 年) 或更新版本中發佈 Microsoft Defender 防毒軟體預約通話版本4.18.1812.3。</span><span class="sxs-lookup"><span data-stu-id="2c489-188">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="2c489-189">使用 PowerShell，查看排除清單及所有其他 Microsoft Defender 防毒軟體偏好設定</span><span class="sxs-lookup"><span data-stu-id="2c489-189">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="2c489-190">請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2c489-190">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="2c489-191">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender) 。</span><span class="sxs-lookup"><span data-stu-id="2c489-191">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="2c489-192">使用 PowerShell 來檢索特定排除清單</span><span class="sxs-lookup"><span data-stu-id="2c489-192">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="2c489-193">使用下列程式碼片段 (將每一行輸入為個別的命令) ;以您想要命名變數的任何標籤取代 **WDAVprefs** ：</span><span class="sxs-lookup"><span data-stu-id="2c489-193">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

<span data-ttu-id="2c489-194">如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[Use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender) 。</span><span class="sxs-lookup"><span data-stu-id="2c489-194">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2c489-195">相關文章</span><span class="sxs-lookup"><span data-stu-id="2c489-195">Related articles</span></span>

- [<span data-ttu-id="2c489-196">設定及驗證 Microsoft Defender 防毒軟體掃描中的排除專案</span><span class="sxs-lookup"><span data-stu-id="2c489-196">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2c489-197">根據檔案名、副檔名和資料夾位置，設定及驗證排除</span><span class="sxs-lookup"><span data-stu-id="2c489-197">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2c489-198">設定 Windows 伺服器上的 Microsoft Defender 防毒軟體排除</span><span class="sxs-lookup"><span data-stu-id="2c489-198">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2c489-199">定義排除時應避免的常見錯誤</span><span class="sxs-lookup"><span data-stu-id="2c489-199">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2c489-200">自訂、啟動及審閱 Microsoft Defender 防毒軟體掃描和修正的結果</span><span class="sxs-lookup"><span data-stu-id="2c489-200">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2c489-201">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="2c489-201">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
