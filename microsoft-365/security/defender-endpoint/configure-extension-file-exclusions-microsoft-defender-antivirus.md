---
title: 根據副檔名、名稱或位置來設定及驗證排除
description: 根據檔案副檔名、檔案名或位置，將檔案從 Microsoft Defender 防毒軟體掃描中排除。
keywords: 排除專案、檔、副檔名、檔案類型、資料夾名稱、檔案名、掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 71df43639a719acb9436f64deba6b6c5cc9317f5
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924276"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a><span data-ttu-id="31f4f-104">根據副檔名和資料夾位置，設定及驗證排除</span><span class="sxs-lookup"><span data-stu-id="31f4f-104">Configure and validate exclusions based on file extension and folder location</span></span>



<span data-ttu-id="31f4f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="31f4f-105">**Applies to:**</span></span>

- [<span data-ttu-id="31f4f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="31f4f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="31f4f-107">Microsoft Defender 防毒軟體排除項不會套用至其他 Microsoft Defender for endpoint 功能，包括[端點偵測和回應 (EDR) ](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)、[攻擊面降低 (ASR) 規則](/microsoft-365/security/defender-endpoint/attack-surface-reduction)及[受控資料夾存取](/microsoft-365/security/defender-endpoint/controlled-folders)。</span><span class="sxs-lookup"><span data-stu-id="31f4f-107">Microsoft Defender Antivirus exclusions don't apply to other Microsoft Defender for Endpoint capabilities, including [endpoint detection and response (EDR)](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response), [attack surface reduction (ASR) rules](/microsoft-365/security/defender-endpoint/attack-surface-reduction), and [controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span> <span data-ttu-id="31f4f-108">使用本文所述方法排除的檔案，仍然可以觸發 EDR 警示及其他偵測。</span><span class="sxs-lookup"><span data-stu-id="31f4f-108">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span> <span data-ttu-id="31f4f-109">若要排除廣泛的檔案，請將其新增至 Microsoft Defender for Endpoint [自訂指示器](/microsoft-365/security/defender-endpoint/manage-indicators)。</span><span class="sxs-lookup"><span data-stu-id="31f4f-109">To exclude files broadly, add them to the Microsoft Defender for Endpoint [custom indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

## <a name="exclusion-lists"></a><span data-ttu-id="31f4f-110">排除清單</span><span class="sxs-lookup"><span data-stu-id="31f4f-110">Exclusion lists</span></span>

<span data-ttu-id="31f4f-111">您可以修改排除清單，以排除 Microsoft Defender 防毒軟體掃描中的某些檔案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-111">You can exclude certain files from Microsoft Defender Antivirus scans by modifying exclusion lists.</span></span> <span data-ttu-id="31f4f-112">**一般來說，您不需要套用排除**。</span><span class="sxs-lookup"><span data-stu-id="31f4f-112">**Generally, you shouldn't need to apply exclusions**.</span></span> <span data-ttu-id="31f4f-113">Microsoft Defender 防毒軟體包含許多以已知作業系統行為和一般管理檔案為基礎的自動排除專案，例如在企業管理、資料庫管理及其他企業案例及案例中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="31f4f-113">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>

> [!NOTE]
> <span data-ttu-id="31f4f-114">例外狀況也適用于可能有害的應用程式 (PUA) 偵測。</span><span class="sxs-lookup"><span data-stu-id="31f4f-114">Exclusions apply to Potentially Unwanted Apps (PUA) detections as well.</span></span>

> [!NOTE]
> <span data-ttu-id="31f4f-115">自動排除只適用于 Windows Server 2016 及以上的專案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-115">Automatic exclusions apply only to Windows Server 2016 and above.</span></span> <span data-ttu-id="31f4f-116">在 Windows 安全性應用程式和 PowerShell 中看不到這些排除專案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-116">These exclusions are not visible in the Windows Security app and in PowerShell.</span></span>

<span data-ttu-id="31f4f-117">本文說明如何設定檔案和資料夾的排除清單。</span><span class="sxs-lookup"><span data-stu-id="31f4f-117">This article  describes how to configure exclusion lists for the files and folders.</span></span> <span data-ttu-id="31f4f-118">定義排除清單之前，請參閱[建議以定義](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)排除清單。</span><span class="sxs-lookup"><span data-stu-id="31f4f-118">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

| <span data-ttu-id="31f4f-119">排除</span><span class="sxs-lookup"><span data-stu-id="31f4f-119">Exclusion</span></span> | <span data-ttu-id="31f4f-120">範例</span><span class="sxs-lookup"><span data-stu-id="31f4f-120">Examples</span></span> | <span data-ttu-id="31f4f-121">排除清單</span><span class="sxs-lookup"><span data-stu-id="31f4f-121">Exclusion list</span></span> |
|:---|:---|:---|
|<span data-ttu-id="31f4f-122">具有特定副檔名的任何檔案</span><span class="sxs-lookup"><span data-stu-id="31f4f-122">Any file with a specific extension</span></span> | <span data-ttu-id="31f4f-123">電腦上任何位置具有指定副檔名的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-123">All files with the specified extension, anywhere on the machine.</span></span> <p> <span data-ttu-id="31f4f-124">有效語法： `.test` 和 `test`</span><span class="sxs-lookup"><span data-stu-id="31f4f-124">Valid syntax: `.test` and `test`</span></span>  | <span data-ttu-id="31f4f-125">副檔名排除</span><span class="sxs-lookup"><span data-stu-id="31f4f-125">Extension exclusions</span></span> |
|<span data-ttu-id="31f4f-126">特定資料夾底下的任何檔案</span><span class="sxs-lookup"><span data-stu-id="31f4f-126">Any file under a specific folder</span></span> | <span data-ttu-id="31f4f-127">資料夾底下的所有檔案 `c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="31f4f-127">All files under the `c:\test\sample` folder</span></span> | <span data-ttu-id="31f4f-128">檔案與資料夾排除</span><span class="sxs-lookup"><span data-stu-id="31f4f-128">File and folder exclusions</span></span> |
| <span data-ttu-id="31f4f-129">特定資料夾中的特定檔案</span><span class="sxs-lookup"><span data-stu-id="31f4f-129">A specific file in a specific folder</span></span> | <span data-ttu-id="31f4f-130">僅檔案 `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="31f4f-130">The file `c:\sample\sample.test` only</span></span> | <span data-ttu-id="31f4f-131">檔案與資料夾排除</span><span class="sxs-lookup"><span data-stu-id="31f4f-131">File and folder exclusions</span></span> |
| <span data-ttu-id="31f4f-132">特定進程</span><span class="sxs-lookup"><span data-stu-id="31f4f-132">A specific process</span></span> | <span data-ttu-id="31f4f-133">可執行檔 `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="31f4f-133">The executable file `c:\test\process.exe`</span></span> | <span data-ttu-id="31f4f-134">檔案與資料夾排除</span><span class="sxs-lookup"><span data-stu-id="31f4f-134">File and folder exclusions</span></span> |

<span data-ttu-id="31f4f-135">排除清單具有下列特性：</span><span class="sxs-lookup"><span data-stu-id="31f4f-135">Exclusion lists have the following characteristics:</span></span>

- <span data-ttu-id="31f4f-136">除非子資料夾是重新分析點，否則資料夾排除會套用到該資料夾底下的所有檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="31f4f-136">Folder exclusions apply to all files and folders under that folder, unless the subfolder is a reparse point.</span></span> <span data-ttu-id="31f4f-137">重新分析點必須個別排除子資料夾。</span><span class="sxs-lookup"><span data-stu-id="31f4f-137">Reparse point subfolders must be excluded separately.</span></span>
- <span data-ttu-id="31f4f-138">副檔名若未定義路徑或資料夾，則會套用至具有定義副檔名的任何檔案名。</span><span class="sxs-lookup"><span data-stu-id="31f4f-138">File extensions apply to any file name with the defined extension if a path or folder is not defined.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="31f4f-139">使用萬用字元（如星號 (\*) ）將會變更如何轉譯排除規則。</span><span class="sxs-lookup"><span data-stu-id="31f4f-139">Using wildcards such as the asterisk (\*) will alter how the exclusion rules are interpreted.</span></span> <span data-ttu-id="31f4f-140">如需有關萬用字元如何運作的重要資訊，請參閱在檔案名 [和資料夾路徑或副檔名排除清單區段中使用萬用字元](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 。</span><span class="sxs-lookup"><span data-stu-id="31f4f-140">See the [Use wildcards in the file name and folder path or extension exclusion lists](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) section for important information about how wildcards work.</span></span>
> - <span data-ttu-id="31f4f-141">您無法排除對應的網路磁碟機。</span><span class="sxs-lookup"><span data-stu-id="31f4f-141">You cannot exclude mapped network drives.</span></span> <span data-ttu-id="31f4f-142">您必須指定實際的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="31f4f-142">You must specify the actual network path.</span></span>
> - <span data-ttu-id="31f4f-143">在 Microsoft Defender 防毒軟體服務啟動之後所建立的重新分析點，也不會包含在 [排除] 清單中的資料夾。</span><span class="sxs-lookup"><span data-stu-id="31f4f-143">Folders that are reparse points that are created after the Microsoft Defender Antivirus service starts and that have been added to the exclusion list will not be included.</span></span> <span data-ttu-id="31f4f-144">您必須重新開機服務 (以重新開機 Windows) ，以將新重新分析點辨識為有效的排除目標。</span><span class="sxs-lookup"><span data-stu-id="31f4f-144">You must restart the service (by restarting Windows) for new reparse points to be recognized as a valid exclusion target.</span></span>

<span data-ttu-id="31f4f-145">若要排除特定程式所開啟的檔案，請參閱 [Configure and validate 由進程開啟的檔案排除](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)專案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-145">To exclude files opened by a specific process, see [Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="31f4f-146">[排除] 適用于 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、 [隨選掃描](run-scan-microsoft-defender-antivirus.md)和 [即時保護](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="31f4f-146">The exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31f4f-147">使用「群組原則」所做的排除清單變更 **會顯示** 在 [Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)的清單中。</span><span class="sxs-lookup"><span data-stu-id="31f4f-147">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
> <span data-ttu-id="31f4f-148">在 Windows 安全性應用程式中所做的變更 **將不會顯示** 在 [群組原則] 清單中。</span><span class="sxs-lookup"><span data-stu-id="31f4f-148">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="31f4f-149">根據預設，具有系統管理員許可權之使用者所做之 (清單的本機變更（包括 PowerShell 與 WMI) 所做的變更）會與清單一起合併，如定義 (及) 群組原則、Configuration Manager 或 Intune 部署。</span><span class="sxs-lookup"><span data-stu-id="31f4f-149">By default, local changes made to the lists (by users with administrator privileges, including changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="31f4f-150">當發生衝突時，群組原則清單會優先。</span><span class="sxs-lookup"><span data-stu-id="31f4f-150">The Group Policy lists take precedence when there are conflicts.</span></span>

<span data-ttu-id="31f4f-151">您可以 [設定如何合併本機和全域定義的排除清單](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) ，以允許本機變更覆寫受管理的部署設定。</span><span class="sxs-lookup"><span data-stu-id="31f4f-151">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a><span data-ttu-id="31f4f-152">根據資料夾名稱或副檔名設定排除清單</span><span class="sxs-lookup"><span data-stu-id="31f4f-152">Configure the list of exclusions based on folder name or file extension</span></span>

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="31f4f-153">使用 Intune 設定檔案名、資料夾或副檔名排除專案</span><span class="sxs-lookup"><span data-stu-id="31f4f-153">Use Intune to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="31f4f-154">請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="31f4f-154">See the following articles:</span></span>
- [<span data-ttu-id="31f4f-155">在 Microsoft Intune 中設定裝置限制設定</span><span class="sxs-lookup"><span data-stu-id="31f4f-155">Configure device restriction settings in Microsoft Intune</span></span>](/intune/device-restrictions-configure)
- [<span data-ttu-id="31f4f-156">在 Intune 中 Microsoft Defender 防毒軟體 Windows 10 裝置限制設定</span><span class="sxs-lookup"><span data-stu-id="31f4f-156">Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune</span></span>](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="31f4f-157">使用 Configuration Manager 來設定檔案名、資料夾或副檔名排除</span><span class="sxs-lookup"><span data-stu-id="31f4f-157">Use Configuration Manager to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="31f4f-158">請參閱[如何建立及部署反惡意程式碼原則：設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)Microsoft 端點管理員 (目前分支) 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="31f4f-158">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a><span data-ttu-id="31f4f-159">使用群組原則來設定資料夾或副檔名排除</span><span class="sxs-lookup"><span data-stu-id="31f4f-159">Use Group Policy to configure folder or file extension exclusions</span></span>

>[!NOTE]
><span data-ttu-id="31f4f-160">如果您指定檔案的完整路徑，則只會排除該檔案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-160">If you specify a fully qualified path to a file, then only that file is excluded.</span></span> <span data-ttu-id="31f4f-161">如果在排除中定義資料夾，則會排除該資料夾下的所有檔案和子目錄。</span><span class="sxs-lookup"><span data-stu-id="31f4f-161">If a folder is defined in the exclusion, then all files and subdirectories under that folder are excluded.</span></span>

1. <span data-ttu-id="31f4f-162">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="31f4f-162">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="31f4f-163">在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]，然後選取 [ **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="31f4f-163">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="31f4f-164">展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **排除**。</span><span class="sxs-lookup"><span data-stu-id="31f4f-164">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>

4. <span data-ttu-id="31f4f-165">開啟 [ **路徑排除** ] 設定進行編輯，然後新增您的排除專案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-165">Open the **Path Exclusions** setting for editing, and add your exclusions.</span></span>

    1. <span data-ttu-id="31f4f-166">將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="31f4f-166">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="31f4f-167">在 [ **選項** ] 區段中，按一下 [ **顯示**]。</span><span class="sxs-lookup"><span data-stu-id="31f4f-167">Under the **Options** section, click **Show**.</span></span>
    1. <span data-ttu-id="31f4f-168">在 [ **值名稱** ] 欄中，指定各自列的每一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="31f4f-168">Specify each folder on its own line under the **Value name** column.</span></span>
    1. <span data-ttu-id="31f4f-169">如果您指定的是檔案，請確定您輸入的是完整的檔案路徑，包含磁碟機號、資料夾路徑、檔案名及副檔名。</span><span class="sxs-lookup"><span data-stu-id="31f4f-169">If you are specifying a file, ensure that you enter a fully qualified path to the file, including the drive letter, folder path, file name, and extension.</span></span> <span data-ttu-id="31f4f-170">在 [**值**] 欄中輸入 **0** 。</span><span class="sxs-lookup"><span data-stu-id="31f4f-170">Enter **0** in the **Value** column.</span></span>

5. <span data-ttu-id="31f4f-171">選擇 [確定]。</span><span class="sxs-lookup"><span data-stu-id="31f4f-171">Choose **OK**.</span></span>

6. <span data-ttu-id="31f4f-172">開啟 [ **副檔名排除** ] 設定以進行編輯，並新增您的排除專案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-172">Open the **Extension Exclusions** setting for editing and add your exclusions.</span></span>

    1. <span data-ttu-id="31f4f-173">將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="31f4f-173">Set the option to **Enabled**.</span></span>
    1. <span data-ttu-id="31f4f-174">在 [ **選項** ] 區段中，選取 [ **顯示**]。</span><span class="sxs-lookup"><span data-stu-id="31f4f-174">Under the **Options** section, select **Show**.</span></span>
    1. <span data-ttu-id="31f4f-175">在 [ **值名稱** ] 欄底下的獨佔行中輸入每個副檔名。</span><span class="sxs-lookup"><span data-stu-id="31f4f-175">Enter each file extension on its own line under the **Value name** column.</span></span>  <span data-ttu-id="31f4f-176">在 [**值**] 欄中輸入 **0** 。</span><span class="sxs-lookup"><span data-stu-id="31f4f-176">Enter **0** in the **Value** column.</span></span>

7. <span data-ttu-id="31f4f-177">選擇 [確定]。</span><span class="sxs-lookup"><span data-stu-id="31f4f-177">Choose **OK**.</span></span>

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="31f4f-178">使用 PowerShell Cmdlet 來設定檔案名、資料夾或副檔名排除</span><span class="sxs-lookup"><span data-stu-id="31f4f-178">Use PowerShell cmdlets to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="31f4f-179">使用 PowerShell 若要新增或移除以副檔名、位置或檔案名為基礎的檔案排除，需要使用三個 Cmdlet 及適當的排除清單參數的組合。</span><span class="sxs-lookup"><span data-stu-id="31f4f-179">Using PowerShell to add or remove exclusions for files based on the extension, location, or file name requires using a combination of three cmdlets and the appropriate exclusion list parameter.</span></span> <span data-ttu-id="31f4f-180">Cmdlet 全都位於 [Defender 模組](/powershell/module/defender/)中。</span><span class="sxs-lookup"><span data-stu-id="31f4f-180">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="31f4f-181">Cmdlet 的格式如下：</span><span class="sxs-lookup"><span data-stu-id="31f4f-181">The format for the cmdlets is as follows:</span></span>

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

<span data-ttu-id="31f4f-182">下列專案是允許的 `<cmdlet>` ：</span><span class="sxs-lookup"><span data-stu-id="31f4f-182">The following are allowed as the `<cmdlet>`:</span></span>

| <span data-ttu-id="31f4f-183">設定動作</span><span class="sxs-lookup"><span data-stu-id="31f4f-183">Configuration action</span></span> | <span data-ttu-id="31f4f-184">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="31f4f-184">PowerShell cmdlet</span></span> |
|:---|:---|
|<span data-ttu-id="31f4f-185">建立或覆寫清單</span><span class="sxs-lookup"><span data-stu-id="31f4f-185">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="31f4f-186">新增至清單</span><span class="sxs-lookup"><span data-stu-id="31f4f-186">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="31f4f-187">從清單中移除專案</span><span class="sxs-lookup"><span data-stu-id="31f4f-187">Remove item from the list</span></span> | `Remove-MpPreference` |

<span data-ttu-id="31f4f-188">下列專案是允許的 `<exclusion list>` ：</span><span class="sxs-lookup"><span data-stu-id="31f4f-188">The following are allowed as the `<exclusion list>`:</span></span>

| <span data-ttu-id="31f4f-189">排除類型</span><span class="sxs-lookup"><span data-stu-id="31f4f-189">Exclusion type</span></span> | <span data-ttu-id="31f4f-190">PowerShell 參數</span><span class="sxs-lookup"><span data-stu-id="31f4f-190">PowerShell parameter</span></span> |
|:---|:---|
| <span data-ttu-id="31f4f-191">具有指定副檔名的所有檔案</span><span class="sxs-lookup"><span data-stu-id="31f4f-191">All files with a specified file extension</span></span> | `-ExclusionExtension` |
| <span data-ttu-id="31f4f-192">資料夾下的所有檔案 (包括子目錄) 中的檔案，或特定檔案的檔</span><span class="sxs-lookup"><span data-stu-id="31f4f-192">All files under a folder (including files in subdirectories), or a specific file</span></span> | `-ExclusionPath` |

> [!IMPORTANT]
> <span data-ttu-id="31f4f-193">如果您已建立清單，請使用 `Set-MpPreference` 或 `Add-MpPreference` 再次使用 Cmdlet， `Set-MpPreference` 將覆寫現有清單。</span><span class="sxs-lookup"><span data-stu-id="31f4f-193">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="31f4f-194">例如，下列程式碼段會導致 Microsoft Defender 防毒軟體掃描排除副檔名為下列的任何檔案 `.test` ：</span><span class="sxs-lookup"><span data-stu-id="31f4f-194">For example, the following code snippet would cause Microsoft Defender Antivirus scans to exclude any file with the `.test` file extension:</span></span>

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

<span data-ttu-id="31f4f-195">要深入了解，請參閱 [《使用 PowerShell Cmdlets 設定和執行 Microsoft Defender 防毒軟體》](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlets](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="31f4f-195">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="31f4f-196">使用 Windows 管理指令 (WMI) 設定檔案名、資料夾或副檔名排除專案</span><span class="sxs-lookup"><span data-stu-id="31f4f-196">Use Windows Management Instruction (WMI) to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="31f4f-197">針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set**、 **Add** 和 **Remove** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：</span><span class="sxs-lookup"><span data-stu-id="31f4f-197">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionExtension
ExclusionPath
```

<span data-ttu-id="31f4f-198">[ **設定**]、[ **新增**] 和 [ **移除** ] 的使用與其在 PowerShell:、] 和中的對等專案類似 `Set-MpPreference` `Add-MpPreference` `Remove-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="31f4f-198">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="31f4f-199">如需詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="31f4f-199">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a><span data-ttu-id="31f4f-200">使用 Windows 安全性應用程式設定檔案名、資料夾或副檔名排除專案</span><span class="sxs-lookup"><span data-stu-id="31f4f-200">Use the Windows Security app to configure file name, folder, or file extension exclusions</span></span>

<span data-ttu-id="31f4f-201">如需相關指示，請參閱[Add Windows 安全性 app 中的排除](microsoft-defender-security-center-antivirus.md)專案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-201">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="31f4f-202">在檔案名和資料夾路徑或副檔名排除清單中使用萬用字元</span><span class="sxs-lookup"><span data-stu-id="31f4f-202">Use wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="31f4f-203">在 `*` `?` 定義檔案名或資料夾路徑排除清單中的專案時，可以使用星號、問號或環境變數 (例如 `%ALLUSERSPROFILE%`) 做為萬用字元。</span><span class="sxs-lookup"><span data-stu-id="31f4f-203">You can use the asterisk `*`, question mark `?`, or environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the file name or folder path exclusion list.</span></span> <span data-ttu-id="31f4f-204">這些萬用字元的轉譯方式，與其他應用程式和語言中的一般使用方式不同。</span><span class="sxs-lookup"><span data-stu-id="31f4f-204">The way in which these wildcards are interpreted differs from their usual usage in other apps and languages.</span></span> <span data-ttu-id="31f4f-205">請務必閱讀本節，以瞭解其特定限制。</span><span class="sxs-lookup"><span data-stu-id="31f4f-205">Make sure to read this section to understand their specific limitations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31f4f-206">這些萬用字元有主要限制和使用案例：</span><span class="sxs-lookup"><span data-stu-id="31f4f-206">There are key limitations and usage scenarios for these wildcards:</span></span>
> - <span data-ttu-id="31f4f-207">環境變數的使用方式限制為電腦變數，以及適用于執行為 NT AUTHORITY\SYSTEM 帳戶的進程的變數。</span><span class="sxs-lookup"><span data-stu-id="31f4f-207">Environment variable usage is limited to machine variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span>
> - <span data-ttu-id="31f4f-208">您無法使用萬用字元取代磁碟機號。</span><span class="sxs-lookup"><span data-stu-id="31f4f-208">You cannot use a wildcard in place of a drive letter.</span></span>
> - <span data-ttu-id="31f4f-209">`*`資料夾排除中的星號會代替單一資料夾。</span><span class="sxs-lookup"><span data-stu-id="31f4f-209">An asterisk `*` in a folder exclusion stands in place for a single folder.</span></span> <span data-ttu-id="31f4f-210">使用多個實例 `\*\` 來表示多個嵌套資料夾具有未指定的名稱。</span><span class="sxs-lookup"><span data-stu-id="31f4f-210">Use multiple instances of `\*\` to indicate multiple nested folders with unspecified names.</span></span>

<span data-ttu-id="31f4f-211">下表說明如何使用萬用字元，並提供一些範例。</span><span class="sxs-lookup"><span data-stu-id="31f4f-211">The following table describes how the wildcards can be used and provides some examples.</span></span>


|<span data-ttu-id="31f4f-212">萬用字元</span><span class="sxs-lookup"><span data-stu-id="31f4f-212">Wildcard</span></span>  |<span data-ttu-id="31f4f-213">範例</span><span class="sxs-lookup"><span data-stu-id="31f4f-213">Examples</span></span>  |
|:---------|:---------|
|<span data-ttu-id="31f4f-214">`*` (星號) </span><span class="sxs-lookup"><span data-stu-id="31f4f-214">`*` (asterisk)</span></span> <p> <span data-ttu-id="31f4f-215">在 [檔案名] **和 [副檔名** 包含] 中，星號會取代任何數目的字元，而且只適用于引數中定義的最後一個資料夾中的檔案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-215">In **file name and file extension inclusions**, the asterisk replaces any number of characters, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="31f4f-216">在 **資料夾排除** 中，星號會取代單一資料夾。</span><span class="sxs-lookup"><span data-stu-id="31f4f-216">In **folder exclusions**, the asterisk replaces a single folder.</span></span> <span data-ttu-id="31f4f-217">使用多個搭配 `*` 資料夾斜線 `\` 表示多個嵌套資料夾。</span><span class="sxs-lookup"><span data-stu-id="31f4f-217">Use multiple `*` with folder slashes `\` to indicate multiple nested folders.</span></span> <span data-ttu-id="31f4f-218">在比對萬用字元 carded 及命名資料夾的數目之後，也會包含所有子資料夾。</span><span class="sxs-lookup"><span data-stu-id="31f4f-218">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   | <span data-ttu-id="31f4f-219">`C:\MyData\*.txt` 包括 `C:\MyData\notes.txt`</span><span class="sxs-lookup"><span data-stu-id="31f4f-219">`C:\MyData\*.txt` includes `C:\MyData\notes.txt`</span></span> <p> <span data-ttu-id="31f4f-220">`C:\somepath\*\Data`包含位於及其 `C:\somepath\Archives\Data` 子資料夾及其子資料夾中的任何檔案 `C:\somepath\Authorized\Data`</span><span class="sxs-lookup"><span data-stu-id="31f4f-220">`C:\somepath\*\Data` includes any file in `C:\somepath\Archives\Data` and its subfolders, and `C:\somepath\Authorized\Data` and its subfolders</span></span> <p> <span data-ttu-id="31f4f-221">`C:\Serv\*\*\Backup`包含位於及其 `C:\Serv\Primary\Denied\Backup` 子資料夾及其子資料夾中的任何檔案 `C:\Serv\Secondary\Allowed\Backup`</span><span class="sxs-lookup"><span data-stu-id="31f4f-221">`C:\Serv\*\*\Backup` includes any file in `C:\Serv\Primary\Denied\Backup` and its subfolders and `C:\Serv\Secondary\Allowed\Backup` and its subfolders</span></span>     |
|<span data-ttu-id="31f4f-222">`?` (問號) </span><span class="sxs-lookup"><span data-stu-id="31f4f-222">`?` (question mark)</span></span>  <p> <span data-ttu-id="31f4f-223">在 [檔案名] **和 [副檔名** 包含] 中，問號會取代單一字元，而且只適用于引數中所定義之最後一個資料夾中的檔案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-223">In **file name and file extension inclusions**, the question mark replaces a single character, and only applies to files in the last folder defined in the argument.</span></span> <p> <span data-ttu-id="31f4f-224">在 [ **資料夾排除**] 中，問號會取代資料夾名稱中的單一字元。</span><span class="sxs-lookup"><span data-stu-id="31f4f-224">In **folder exclusions**, the question mark replaces a single character in a folder name.</span></span> <span data-ttu-id="31f4f-225">在比對萬用字元 carded 及命名資料夾的數目之後，也會包含所有子資料夾。</span><span class="sxs-lookup"><span data-stu-id="31f4f-225">After matching the number of wild carded and named folders, all subfolders are also included.</span></span>   |<span data-ttu-id="31f4f-226">`C:\MyData\my?.zip` 包括 `C:\MyData\my1.zip`</span><span class="sxs-lookup"><span data-stu-id="31f4f-226">`C:\MyData\my?.zip` includes `C:\MyData\my1.zip`</span></span> <p> <span data-ttu-id="31f4f-227">`C:\somepath\?\Data`包含位於及其子資料夾中的任何檔案 `C:\somepath\P\Data`</span><span class="sxs-lookup"><span data-stu-id="31f4f-227">`C:\somepath\?\Data` includes any file in `C:\somepath\P\Data` and its subfolders</span></span>  <p> <span data-ttu-id="31f4f-228">`C:\somepath\test0?\Data` 會包含任何位於 `C:\somepath\test01\Data` 及其子資料夾中的檔案</span><span class="sxs-lookup"><span data-stu-id="31f4f-228">`C:\somepath\test0?\Data` would include any file in `C:\somepath\test01\Data` and its subfolders</span></span>          |
|<span data-ttu-id="31f4f-229">環境變數</span><span class="sxs-lookup"><span data-stu-id="31f4f-229">Environment variables</span></span> <p> <span data-ttu-id="31f4f-230">在評估排除時，已定義的變數會填入為路徑。</span><span class="sxs-lookup"><span data-stu-id="31f4f-230">The defined variable is populated as a path when the exclusion is evaluated.</span></span>          |<span data-ttu-id="31f4f-231">`%ALLUSERSPROFILE%\CustomLogFiles` 會包含 `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span><span class="sxs-lookup"><span data-stu-id="31f4f-231">`%ALLUSERSPROFILE%\CustomLogFiles` would include `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`</span></span>         |
        

> [!IMPORTANT]
> <span data-ttu-id="31f4f-232">如果您混合使用資料夾排除引數的檔案排除引數，則規則會在符合資料夾中的檔案引數相符時停止，而且不會在任何子資料夾中尋找檔的相符性。</span><span class="sxs-lookup"><span data-stu-id="31f4f-232">If you mix a file exclusion argument with a folder exclusion argument, the rules will stop at the file argument match in the matched folder, and will not look for file matches in any subfolders.</span></span>
> <span data-ttu-id="31f4f-233">例如，您可以在資料夾中排除以 "date" 開頭的所有檔案 `c:\data\final\marked` ，並 `c:\data\review\marked` 使用 rule 引數 `c:\data\*\marked\date*` 。</span><span class="sxs-lookup"><span data-stu-id="31f4f-233">For example, you can exclude all files that start with "date" in the folders `c:\data\final\marked` and `c:\data\review\marked` by using the rule argument `c:\data\*\marked\date*`.</span></span>
> <span data-ttu-id="31f4f-234">不過，此引數不會符合或的子資料夾中的任何檔案 `c:\data\final\marked` `c:\data\review\marked` 。</span><span class="sxs-lookup"><span data-stu-id="31f4f-234">This argument, however, will not match any files in subfolders under `c:\data\final\marked` or `c:\data\review\marked`.</span></span>

<a id="review"></a>

### <a name="system-environment-variables"></a><span data-ttu-id="31f4f-235">系統內容變數</span><span class="sxs-lookup"><span data-stu-id="31f4f-235">System environment variables</span></span>

<span data-ttu-id="31f4f-236">下表列出並說明系統帳戶環境變數。</span><span class="sxs-lookup"><span data-stu-id="31f4f-236">The following table lists and describes the system account environment variables.</span></span> 

| <span data-ttu-id="31f4f-237">這個系統內容變數 .。。</span><span class="sxs-lookup"><span data-stu-id="31f4f-237">This system environment variable...</span></span> | <span data-ttu-id="31f4f-238">重新導向至此</span><span class="sxs-lookup"><span data-stu-id="31f4f-238">Redirects to this</span></span> |
|:--|:--|
| `%APPDATA%`| `C:\Users\UserName.DomainName\AppData\Roaming` |
| `%APPDATA%\Microsoft\Internet Explorer\Quick Launch` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch` |
| `%APPDATA%\Microsoft\Windows\Start Menu` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu` |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs` |
| `%LOCALAPPDATA%` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%ProgramData%` | `C:\ProgramData` |
| `%ProgramFiles%` | `C:\Program Files` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles%\Windows Sidebar\Gadgets` | `C:\Program Files\Windows Sidebar\Gadgets` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles(x86)%` | `C:\Program Files (x86)` |
| `%ProgramFiles(x86)%\Common Files` | `C:\Program Files (x86)\Common Files` |
| `%SystemDrive%` | `C:` |
| `%SystemDrive%\Program Files` | `C:\Program Files` |
| `%SystemDrive%\Program Files (x86)` | `C:\Program Files (x86)` |
| `%SystemDrive%\Users` | `C:\Users` |
| `%SystemDrive%\Users\Public` | `C:\Users\Public` |
| `%SystemRoot%` | `C:\Windows` |
| `%windir%` | `C:\Windows` |
| `%windir%\Fonts` | `C:\Windows\Fonts` |
| `%windir%\Resources` | `C:\Windows\Resources` |
| `%windir%\resources\0409` | `C:\Windows\resources\0409` |
| `%windir%\system32` | `C:\Windows\System32` |
| `%ALLUSERSPROFILE%` | `C:\ProgramData` |
| `%ALLUSERSPROFILE%\Application Data` | `C:\ProgramData\Application Data` |
| `%ALLUSERSPROFILE%\Documents` | `C:\ProgramData\Documents` |
| `%ALLUSERSPROFILE%\Documents\My Music\Sample Music` | `C:\ProgramData\Documents\My Music\Sample Music` |
| `%ALLUSERSPROFILE%\Documents\My Music` | `C:\ProgramData\Documents\My Music` |
| `%ALLUSERSPROFILE%\Documents\My Pictures` | `C:\ProgramData\Documents\My Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures` | `C:\ProgramData\Documents\My Pictures\Sample Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Videos` | `C:\ProgramData\Documents\My Videos` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore` | `C:\ProgramData\Microsoft\Windows\DeviceMetadataStore` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer` | `C:\ProgramData\Microsoft\Windows\GameExplorer` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones` | `C:\ProgramData\Microsoft\Windows\Ringtones` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu` | `C:\ProgramData\Microsoft\Windows\Start Menu` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Templates` | `C:\ProgramData\Microsoft\Windows\Templates` |
| `%ALLUSERSPROFILE%\Start Menu` | `C:\ProgramData\Start Menu` |
| `%ALLUSERSPROFILE%\Start Menu\Programs` | <span data-ttu-id="31f4f-239">C:\ProgramData\Start Menu\Programs</span><span class="sxs-lookup"><span data-stu-id="31f4f-239">C:\ProgramData\Start Menu\Programs</span></span> |
| `%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Start Menu\Programs\Administrative Tools` | 
| `%ALLUSERSPROFILE%\Templates` | `C:\ProgramData\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\History` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History` |
| `%PUBLIC%` | `C:\Users\Public` |
| `%PUBLIC%\AccountPictures` | `C:\Users\Public\AccountPictures` |
| `%PUBLIC%\Desktop` | `C:\Users\Public\Desktop` |
| `%PUBLIC%\Documents` | `C:\Users\Public\Documents` |
| `%PUBLIC%\Downloads` | `C:\Users\Public\Downloads` |
| `%PUBLIC%\Music\Sample Music` | `C:\Users\Public\Music\Sample Music` |
| `%PUBLIC%\Music\Sample Playlists` | `C:\Users\Public\Music\Sample Playlists` |
| `%PUBLIC%\Pictures\Sample Pictures` | `C:\Users\Public\Pictures\Sample Pictures` |
| `%PUBLIC%\RecordedTV.library-ms` | `C:\Users\Public\RecordedTV.library-ms` |
| `%PUBLIC%\Videos` | `C:\Users\Public\Videos` |
| `%PUBLIC%\Videos\Sample Videos` | `C:\Users\Public\Videos\Sample Videos` | 
| `%USERPROFILE%` | `C:\Windows\System32\config\systemprofile` |
| `%USERPROFILE%\AppData\Local` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%USERPROFILE%\AppData\LocalLow` | `C:\Windows\System32\config\systemprofile\AppData\LocalLow` |
| `%USERPROFILE%\AppData\Roaming` | `C:\Windows\System32\config\systemprofile\AppData\Roaming` |


## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="31f4f-240">審閱排除清單</span><span class="sxs-lookup"><span data-stu-id="31f4f-240">Review the list of exclusions</span></span>

<span data-ttu-id="31f4f-241">您可以使用下列其中一種方法，在排除清單中取得專案：</span><span class="sxs-lookup"><span data-stu-id="31f4f-241">You can retrieve the items in the exclusion list using one of the following methods:</span></span>
- [<span data-ttu-id="31f4f-242">Intune</span><span class="sxs-lookup"><span data-stu-id="31f4f-242">Intune</span></span>](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [<span data-ttu-id="31f4f-243">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="31f4f-243">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- <span data-ttu-id="31f4f-244">MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="31f4f-244">MpCmdRun</span></span>
- <span data-ttu-id="31f4f-245">PowerShell</span><span class="sxs-lookup"><span data-stu-id="31f4f-245">PowerShell</span></span>
- [<span data-ttu-id="31f4f-246">Windows 安全性應用程式</span><span class="sxs-lookup"><span data-stu-id="31f4f-246">Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)

>[!IMPORTANT]
><span data-ttu-id="31f4f-247">使用「群組原則」所做的排除清單變更 **會顯示** 在 [Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)的清單中。</span><span class="sxs-lookup"><span data-stu-id="31f4f-247">Exclusion list changes made with Group Policy **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>
>
><span data-ttu-id="31f4f-248">在 Windows 安全性應用程式中所做的變更 **將不會顯示** 在 [群組原則] 清單中。</span><span class="sxs-lookup"><span data-stu-id="31f4f-248">Changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="31f4f-249">如果您使用 PowerShell，您可以使用下列兩種方式來找回清單：</span><span class="sxs-lookup"><span data-stu-id="31f4f-249">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="31f4f-250">取得所有 Microsoft Defender 防毒軟體首選項的狀態。</span><span class="sxs-lookup"><span data-stu-id="31f4f-250">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="31f4f-251">每個清單都顯示在不同的行上，但是每個清單中的專案會組合成同一行。</span><span class="sxs-lookup"><span data-stu-id="31f4f-251">Each list is displayed on separate lines, but the items within each list are combined into the same line.</span></span>
- <span data-ttu-id="31f4f-252">將所有喜好設定的狀態寫入變數中，並使用該變數只呼叫您感興趣的特定清單。</span><span class="sxs-lookup"><span data-stu-id="31f4f-252">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="31f4f-253">每次使用 `Add-MpPreference` 都會寫入新行。</span><span class="sxs-lookup"><span data-stu-id="31f4f-253">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="31f4f-254">使用 MpCmdRun 驗證排除清單</span><span class="sxs-lookup"><span data-stu-id="31f4f-254">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="31f4f-255">若要使用專用 [命令列工具 mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)檢查排除，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="31f4f-255">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.1812.3 (Where 4.18.1812.3 is this month's MDAV "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

>[!NOTE]
><span data-ttu-id="31f4f-256">檢查包含 MpCmdRun 的排除專案時，需要 (2018 年) 或更新版本中發佈 Microsoft Defender 防毒軟體預約通話版本4.18.1812.3。</span><span class="sxs-lookup"><span data-stu-id="31f4f-256">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="31f4f-257">使用 PowerShell，查看排除清單及所有其他 Microsoft Defender 防毒軟體偏好設定</span><span class="sxs-lookup"><span data-stu-id="31f4f-257">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="31f4f-258">請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="31f4f-258">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="31f4f-259">在下列範例中，會將清單中包含的專案反 `ExclusionExtension` 白顯示：</span><span class="sxs-lookup"><span data-stu-id="31f4f-259">In the following example, the items contained in the `ExclusionExtension` list are highlighted:</span></span>

![Get-MpPreference 的 PowerShell 輸出，顯示排除清單及其他喜好設定](images/defender/wdav-powershell-get-exclusions-all.png)

<span data-ttu-id="31f4f-261">要深入了解，請參閱 [《使用 PowerShell Cmdlets 設定和執行 Microsoft Defender 防毒軟體》](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlets](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="31f4f-261">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="31f4f-262">使用 PowerShell 來檢索特定排除清單</span><span class="sxs-lookup"><span data-stu-id="31f4f-262">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="31f4f-263">使用下列程式碼片段 (將每一行輸入為個別的命令) ;以您想要命名變數的任何標籤取代 **WDAVprefs** ：</span><span class="sxs-lookup"><span data-stu-id="31f4f-263">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

<span data-ttu-id="31f4f-264">在下列範例中，會將清單分割為每次使用 Cmdlet 的新行 `Add-MpPreference` ：</span><span class="sxs-lookup"><span data-stu-id="31f4f-264">In the following example, the list is split into new lines for each use of the `Add-MpPreference` cmdlet:</span></span>

![PowerShell 輸出僅顯示排除清單中的專案](images/defender/wdav-powershell-get-exclusions-variable.png)

<span data-ttu-id="31f4f-266">要深入了解，請參閱 [《使用 PowerShell Cmdlets 設定和執行 Microsoft Defender 防毒軟體》](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender Cmdlets](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="31f4f-266">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="31f4f-267">使用 EICAR.TXT 測試檔案驗證排除清單</span><span class="sxs-lookup"><span data-stu-id="31f4f-267">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="31f4f-268">您可以使用 Cmdlet 或 .NET WebClient 類別的 PowerShell，驗證您的排除清單是否正常運作 `Invoke-WebRequest` ，以下載測試檔案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-268">You can validate that your exclusion lists are working by using PowerShell with either the `Invoke-WebRequest` cmdlet or the .NET WebClient class to download a test file.</span></span>

<span data-ttu-id="31f4f-269">在下列 PowerShell 片段中，將 *test.txt* 取代為符合您的排除規則的檔案。</span><span class="sxs-lookup"><span data-stu-id="31f4f-269">In the following PowerShell snippet, replace *test.txt* with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="31f4f-270">例如，如果您已排除該 `.testing` 副檔名，請將其取代 `test.txt` `test.testing` 。</span><span class="sxs-lookup"><span data-stu-id="31f4f-270">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="31f4f-271">若要測試路徑，請確定您在該路徑內執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="31f4f-271">If you are testing a path, ensure you run the cmdlet within that path.</span></span>

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

<span data-ttu-id="31f4f-272">如果 Microsoft Defender 防毒軟體報告惡意程式碼，則規則不會正常運作。</span><span class="sxs-lookup"><span data-stu-id="31f4f-272">If Microsoft Defender Antivirus reports malware, then the rule is not working.</span></span> <span data-ttu-id="31f4f-273">如果沒有惡意軟體的報表，而且下載的檔案存在，則排除作業正常運作。</span><span class="sxs-lookup"><span data-stu-id="31f4f-273">If there is no report of malware and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="31f4f-274">您可以開啟檔案，確認內容與 [eicar.txt test file 網站](http://www.eicar.org/86-0-Intended-use.html)上所述的內容相同。</span><span class="sxs-lookup"><span data-stu-id="31f4f-274">You can open the file to confirm the contents are the same as what is described on the [EICAR test file website](http://www.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="31f4f-275">您也可以使用下列 PowerShell 程式碼，它會呼叫 .NET WebClient 類別以下載測試檔-如 Cmdlet 所示 `Invoke-WebRequest` ; 將 *c:\test.txt* 取代為符合您所驗證之規則的檔案：</span><span class="sxs-lookup"><span data-stu-id="31f4f-275">You can also use the following PowerShell code, which calls the .NET WebClient class to download the test file - as with the `Invoke-WebRequest` cmdlet; replace *c:\test.txt* with a file that conforms to the rule you are validating:</span></span>

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

<span data-ttu-id="31f4f-276">如果您沒有網際網路存取權，您可以使用下列 PowerShell 命令，將 EICAR.TXT 字串寫入新的文字檔，以建立您自己的 EICAR.TXT 測試檔案：</span><span class="sxs-lookup"><span data-stu-id="31f4f-276">If you do not have Internet access, you can create your own EICAR test file by writing the EICAR string to a new text file with the following PowerShell command:</span></span>

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

<span data-ttu-id="31f4f-277">您也可以將字串複製到空白的文字檔中，並嘗試使用檔案名或您嘗試排除的資料夾來儲存。</span><span class="sxs-lookup"><span data-stu-id="31f4f-277">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="related-topics"></a><span data-ttu-id="31f4f-278">相關主題</span><span class="sxs-lookup"><span data-stu-id="31f4f-278">Related topics</span></span>

- [<span data-ttu-id="31f4f-279">設定及驗證 Microsoft Defender 防毒軟體掃描中的排除專案</span><span class="sxs-lookup"><span data-stu-id="31f4f-279">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="31f4f-280">設定及驗證由進程開啟之檔案的排除專案</span><span class="sxs-lookup"><span data-stu-id="31f4f-280">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="31f4f-281">設定 Windows 伺服器上的 Microsoft Defender 防毒軟體排除</span><span class="sxs-lookup"><span data-stu-id="31f4f-281">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="31f4f-282">定義排除時應避免的常見錯誤</span><span class="sxs-lookup"><span data-stu-id="31f4f-282">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
