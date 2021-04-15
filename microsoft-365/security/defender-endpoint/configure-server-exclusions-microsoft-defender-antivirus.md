---
title: 設定 Windows Server 上的 Microsoft Defender 防病毒排除
ms.reviewer: ''
manager: dansimp
description: Windows Server 包含根據伺服器角色的自動排除。 您也可以新增自訂排除專案。
keywords: 排除、伺服器、自動排除、自動、自訂、掃描、Microsoft Defender 防毒程式
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.openlocfilehash: 507edb980f671b2f39403cc41e540150f5e82891
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764338"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a><span data-ttu-id="8cc48-105">設定 Windows Server 上的 Microsoft Defender 防病毒排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-105">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8cc48-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8cc48-106">**Applies to:**</span></span>

- [<span data-ttu-id="8cc48-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8cc48-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8cc48-108">Windows Server 2016 和 Windows Server 2019 上的 Microsoft Defender 防毒程式會根據您指定伺服器角色的定義，自動在某些排除專案中登記您。</span><span class="sxs-lookup"><span data-stu-id="8cc48-108">Microsoft Defender Antivirus on Windows Server 2016 and Windows Server 2019 automatically enrolls you in certain exclusions, as defined by your specified server role.</span></span> <span data-ttu-id="8cc48-109">這些排除專案不會出現在 [Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)中顯示的標準排除清單中。</span><span class="sxs-lookup"><span data-stu-id="8cc48-109">These exclusions do not appear in the standard exclusion lists that are shown in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8cc48-110">[自動排除] 只適用于即時保護 (RTP) 掃描。</span><span class="sxs-lookup"><span data-stu-id="8cc48-110">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="8cc48-111">在完整/快速或隨選掃描期間，不會接受自動排除。</span><span class="sxs-lookup"><span data-stu-id="8cc48-111">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>

<span data-ttu-id="8cc48-112">除了伺服器角色定義的自動排除專案之外，您還可以新增或移除自訂排除。</span><span class="sxs-lookup"><span data-stu-id="8cc48-112">In addition to server role-defined automatic exclusions, you can add or remove custom exclusions.</span></span> <span data-ttu-id="8cc48-113">若要這麼做，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="8cc48-113">To do that, refer to these articles:</span></span>
- [<span data-ttu-id="8cc48-114">根據檔案名、副檔名和資料夾位置，設定及驗證排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-114">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8cc48-115">設定及驗證由進程開啟之檔案的排除專案</span><span class="sxs-lookup"><span data-stu-id="8cc48-115">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a><span data-ttu-id="8cc48-116">記住幾點</span><span class="sxs-lookup"><span data-stu-id="8cc48-116">A few points to keep in mind</span></span>

<span data-ttu-id="8cc48-117">請牢記下列重要要點：</span><span class="sxs-lookup"><span data-stu-id="8cc48-117">Keep the following important points in mind:</span></span>

- <span data-ttu-id="8cc48-118">自訂排除優先于自動排除。</span><span class="sxs-lookup"><span data-stu-id="8cc48-118">Custom exclusions take precedence over automatic exclusions.</span></span>
- <span data-ttu-id="8cc48-119">[自動排除] 只適用于即時保護 (RTP) 掃描。</span><span class="sxs-lookup"><span data-stu-id="8cc48-119">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="8cc48-120">在完整/快速或隨選掃描期間，不會接受自動排除。</span><span class="sxs-lookup"><span data-stu-id="8cc48-120">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>
- <span data-ttu-id="8cc48-121">自訂和重複排除專案不會與自動排除項衝突。</span><span class="sxs-lookup"><span data-stu-id="8cc48-121">Custom and duplicate exclusions do not conflict with automatic exclusions.</span></span>
- <span data-ttu-id="8cc48-122">Microsoft Defender 防毒軟體使用「部署影像服務」和「管理」 (DISM) 工具來判斷電腦上安裝的角色。</span><span class="sxs-lookup"><span data-stu-id="8cc48-122">Microsoft Defender Antivirus uses the Deployment Image Servicing and Management (DISM) tools to determine which roles are installed on your computer.</span></span>

## <a name="opt-out-of-automatic-exclusions"></a><span data-ttu-id="8cc48-123">選擇不限自動排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-123">Opt out of automatic exclusions</span></span>

<span data-ttu-id="8cc48-124">在 Windows Server 2016 和 Windows Server 2019 中，安全性情報更新所傳遞的預先定義排除只會排除角色或功能的預設路徑。</span><span class="sxs-lookup"><span data-stu-id="8cc48-124">In Windows Server 2016 and Windows Server 2019, the predefined exclusions delivered by Security intelligence updates only exclude the default paths for a role or feature.</span></span> <span data-ttu-id="8cc48-125">如果您已在自訂路徑中安裝角色或功能，或是您想要手動控制一組排除，請務必取消在安全性智慧更新中所提供的自動排除專案。</span><span class="sxs-lookup"><span data-stu-id="8cc48-125">If you installed a role or feature in a custom path, or you want to manually control the set of exclusions, make sure to opt out of the automatic exclusions delivered in Security intelligence updates.</span></span> <span data-ttu-id="8cc48-126">但是請記住，會自動傳遞的排除專案，針對 Windows Server 2016 和2019角色進行優化。</span><span class="sxs-lookup"><span data-stu-id="8cc48-126">But keep in mind that the exclusions that are delivered automatically are optimized for Windows Server 2016 and 2019 roles.</span></span> <span data-ttu-id="8cc48-127">定義排除清單之前，請參閱定義排除專案 [的建議](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 。</span><span class="sxs-lookup"><span data-stu-id="8cc48-127">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

> [!WARNING]
> <span data-ttu-id="8cc48-128">退出自動排除可能會對效能造成不良影響，或導致資料損毀。</span><span class="sxs-lookup"><span data-stu-id="8cc48-128">Opting out of automatic exclusions may adversely impact performance, or result in data corruption.</span></span> <span data-ttu-id="8cc48-129">針對 Windows Server 2016 和 Windows Server 2019 角色，會自動傳遞的排除專案。</span><span class="sxs-lookup"><span data-stu-id="8cc48-129">The exclusions that are delivered automatically are optimized for Windows Server 2016 and Windows Server 2019 roles.</span></span>

<span data-ttu-id="8cc48-130">因為預先定義的排除只排除 **預設路徑**，所以如果您將 NTDS 和 SYSVOL 移至另一個 *不同于原始路徑* 的磁片磁碟機或路徑，您必須使用 [這裡](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) 的資訊手動新增排除。</span><span class="sxs-lookup"><span data-stu-id="8cc48-130">Because predefined exclusions only exclude **default paths**, if you move NTDS and SYSVOL to another drive or path that is *different from the original path*, you must add exclusions manually using the information [here](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span></span>

<span data-ttu-id="8cc48-131">您可以使用「群組原則」、「PowerShell Cmdlet」和 WMI 來停用自動排除清單。</span><span class="sxs-lookup"><span data-stu-id="8cc48-131">You can disable the automatic exclusion lists with Group Policy, PowerShell cmdlets, and WMI.</span></span>

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="8cc48-132">使用群組原則在 Windows Server 2016 和 Windows Server 2019 上停用自動排除清單</span><span class="sxs-lookup"><span data-stu-id="8cc48-132">Use Group Policy to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

1. <span data-ttu-id="8cc48-133">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11))]。</span><span class="sxs-lookup"><span data-stu-id="8cc48-133">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span></span> <span data-ttu-id="8cc48-134">以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="8cc48-134">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>
2. <span data-ttu-id="8cc48-135">在 [**群組原則管理編輯器**] 中，移至 [電腦設定]，然後按一下 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="8cc48-135">In the **Group Policy Management Editor** go to **Computer configuration**, and then click **Administrative templates**.</span></span>
3. <span data-ttu-id="8cc48-136">將樹狀目錄展開為  >  **microsoft Defender 防病毒**  >  **排除** 專案的 Windows 元件。</span><span class="sxs-lookup"><span data-stu-id="8cc48-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>
4. <span data-ttu-id="8cc48-137">按兩下 [ **關閉自動排除**]，然後將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="8cc48-137">Double-click **Turn off Auto Exclusions**, and set the option to **Enabled**.</span></span> <span data-ttu-id="8cc48-138">然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8cc48-138">Then click **OK**.</span></span> 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a><span data-ttu-id="8cc48-139">在 Windows Server 2016 和2019上使用 PowerShell Cmdlet 來停用自動排除清單</span><span class="sxs-lookup"><span data-stu-id="8cc48-139">Use PowerShell cmdlets to disable the auto-exclusions list on Windows Server 2016 and 2019</span></span>

<span data-ttu-id="8cc48-140">使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8cc48-140">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

<span data-ttu-id="8cc48-141">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="8cc48-141">To learn more, see the following resources:</span></span>

- <span data-ttu-id="8cc48-142">[使用 PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md)程式。</span><span class="sxs-lookup"><span data-stu-id="8cc48-142">[Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>
- <span data-ttu-id="8cc48-143">[使用 Microsoft Defender 防病毒 PowerShell](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="8cc48-143">[Use PowerShell with Microsoft Defender Antivirus](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="8cc48-144">使用 Windows Management 指令 (WMI) 以停用 Windows Server 2016 和 Windows Server 2019 上的自動排除清單</span><span class="sxs-lookup"><span data-stu-id="8cc48-144">Use Windows Management Instruction (WMI) to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

<span data-ttu-id="8cc48-145">針對下列屬性，使用 [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference)類別的 **Set** 方法：</span><span class="sxs-lookup"><span data-stu-id="8cc48-145">Use the **Set** method of the [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) class for the following properties:</span></span>

```WMI
DisableAutoExclusions
```

<span data-ttu-id="8cc48-146">如需詳細資訊及允許的參數，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="8cc48-146">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="8cc48-147">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="8cc48-147">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a><span data-ttu-id="8cc48-148">自動排除清單</span><span class="sxs-lookup"><span data-stu-id="8cc48-148">List of automatic exclusions</span></span>

<span data-ttu-id="8cc48-149">下列各節包含與自動排除檔路徑及檔案類型一起傳遞的排除專案。</span><span class="sxs-lookup"><span data-stu-id="8cc48-149">The following sections contain the exclusions that are delivered with automatic exclusions file paths and file types.</span></span>

### <a name="default-exclusions-for-all-roles"></a><span data-ttu-id="8cc48-150">所有角色的預設排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-150">Default exclusions for all roles</span></span>

<span data-ttu-id="8cc48-151">本節列出所有 Windows Server 2016 和2019角色的預設排除專案。</span><span class="sxs-lookup"><span data-stu-id="8cc48-151">This section lists the default exclusions for all Windows Server 2016 and 2019 roles.</span></span>

> [!NOTE]
> <span data-ttu-id="8cc48-152">預設位置可能會不同于本文所列的位置。</span><span class="sxs-lookup"><span data-stu-id="8cc48-152">The default locations could be different than what's listed in this article.</span></span>

#### <a name="windows-tempedb-files"></a><span data-ttu-id="8cc48-153">Windows "temp" 檔案</span><span class="sxs-lookup"><span data-stu-id="8cc48-153">Windows "temp.edb" files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a><span data-ttu-id="8cc48-154">Windows 更新檔或自動更新檔案</span><span class="sxs-lookup"><span data-stu-id="8cc48-154">Windows Update files or Automatic Update files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a><span data-ttu-id="8cc48-155">Windows 安全性檔案</span><span class="sxs-lookup"><span data-stu-id="8cc48-155">Windows Security files</span></span>

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a><span data-ttu-id="8cc48-156">群組原則檔</span><span class="sxs-lookup"><span data-stu-id="8cc48-156">Group Policy files</span></span>

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a><span data-ttu-id="8cc48-157">WINS 檔案</span><span class="sxs-lookup"><span data-stu-id="8cc48-157">WINS files</span></span>

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a><span data-ttu-id="8cc48-158">檔案複寫服務 (FRS) 排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-158">File Replication Service (FRS) exclusions</span></span>

- <span data-ttu-id="8cc48-159">檔案複寫服務中的檔案 (FRS) 工作資料夾。</span><span class="sxs-lookup"><span data-stu-id="8cc48-159">Files in the File Replication Service (FRS) working folder.</span></span> <span data-ttu-id="8cc48-160">在登錄機碼中指定 FRS 工作資料夾 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span><span class="sxs-lookup"><span data-stu-id="8cc48-160">The FRS working folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span></span>

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- <span data-ttu-id="8cc48-161">FRS 資料庫記錄檔。</span><span class="sxs-lookup"><span data-stu-id="8cc48-161">FRS Database log files.</span></span> <span data-ttu-id="8cc48-162">FRS 資料庫記錄檔資料夾是在登錄機碼中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span><span class="sxs-lookup"><span data-stu-id="8cc48-162">The FRS Database log file folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span></span>

  - `%windir%\Ntfrs\*\Edb\*.log`

- <span data-ttu-id="8cc48-163">FRS 暫存資料夾。</span><span class="sxs-lookup"><span data-stu-id="8cc48-163">The FRS staging folder.</span></span> <span data-ttu-id="8cc48-164">在登錄機碼中指定暫存資料夾 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span><span class="sxs-lookup"><span data-stu-id="8cc48-164">The staging folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span></span>

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- <span data-ttu-id="8cc48-165">FRS 預先安裝資料夾。</span><span class="sxs-lookup"><span data-stu-id="8cc48-165">The FRS preinstall folder.</span></span> <span data-ttu-id="8cc48-166">這個資料夾是由資料夾指定 `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span><span class="sxs-lookup"><span data-stu-id="8cc48-166">This folder is specified by the folder `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span></span>

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- <span data-ttu-id="8cc48-167">分散式檔案系統複寫 (DFSR) 資料庫和工作資料夾。</span><span class="sxs-lookup"><span data-stu-id="8cc48-167">The Distributed File System Replication (DFSR) database and working folders.</span></span> <span data-ttu-id="8cc48-168">這些資料夾是由登錄機碼指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span><span class="sxs-lookup"><span data-stu-id="8cc48-168">These folders are specified by the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span></span>

  > [!NOTE]
  > <span data-ttu-id="8cc48-169">若為自訂位置，請參閱選擇 [不限 [自動排除](#opt-out-of-automatic-exclusions)]。</span><span class="sxs-lookup"><span data-stu-id="8cc48-169">For custom locations, see [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span></span>

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a><span data-ttu-id="8cc48-170">處理程序排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-170">Process exclusions</span></span>

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a><span data-ttu-id="8cc48-171">Hyper-V 排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-171">Hyper-V exclusions</span></span>

<span data-ttu-id="8cc48-172">下表列出當您安裝 Hyper-V 角色時，會自動傳遞的檔案類型排除、資料夾排除和程式排除專案。</span><span class="sxs-lookup"><span data-stu-id="8cc48-172">The following table lists the file type exclusions, folder exclusions, and process exclusions that are delivered automatically when you install the Hyper-V role.</span></span>

|<span data-ttu-id="8cc48-173">檔案類型排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-173">File type exclusions</span></span> |<span data-ttu-id="8cc48-174">資料夾排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-174">Folder exclusions</span></span>  | <span data-ttu-id="8cc48-175">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="8cc48-175">Process exclusions</span></span> |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a><span data-ttu-id="8cc48-176">SYSVOL 檔案</span><span class="sxs-lookup"><span data-stu-id="8cc48-176">SYSVOL files</span></span>

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a><span data-ttu-id="8cc48-177">Active Directory 排除專案</span><span class="sxs-lookup"><span data-stu-id="8cc48-177">Active Directory exclusions</span></span>

<span data-ttu-id="8cc48-178">本節列出當您安裝 Active Directory 網域服務時，會自動傳遞的排除專案。</span><span class="sxs-lookup"><span data-stu-id="8cc48-178">This section lists the exclusions that are delivered automatically when you install Active Directory Domain Services.</span></span>

#### <a name="ntds-database-files"></a><span data-ttu-id="8cc48-179">NTDS 資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="8cc48-179">NTDS database files</span></span>

<span data-ttu-id="8cc48-180">資料庫檔案是在登錄機碼中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span><span class="sxs-lookup"><span data-stu-id="8cc48-180">The database files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span></span>

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a><span data-ttu-id="8cc48-181">AD DS 交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="8cc48-181">The AD DS transaction log files</span></span>

<span data-ttu-id="8cc48-182">交易記錄檔是在登錄機碼中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span><span class="sxs-lookup"><span data-stu-id="8cc48-182">The transaction log files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span></span>

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a><span data-ttu-id="8cc48-183">NTDS 工作資料夾</span><span class="sxs-lookup"><span data-stu-id="8cc48-183">The NTDS working folder</span></span>

<span data-ttu-id="8cc48-184">這個資料夾是在登錄機碼中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span><span class="sxs-lookup"><span data-stu-id="8cc48-184">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span></span>

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a><span data-ttu-id="8cc48-185">針對 AD DS 和 AD DS 相關支援檔案的處理常式排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-185">Process exclusions for AD DS and AD DS-related support files</span></span>

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a><span data-ttu-id="8cc48-186">DHCP 伺服器排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-186">DHCP Server exclusions</span></span>

<span data-ttu-id="8cc48-187">本節列出當您安裝 DHCP 伺服器角色時，會自動傳遞的排除專案。</span><span class="sxs-lookup"><span data-stu-id="8cc48-187">This section lists the exclusions that are delivered automatically when you install the DHCP Server role.</span></span> <span data-ttu-id="8cc48-188">DHCP 伺服器檔案位置是由登錄機碼中的 *move-databasepath*、 *DhcpLogFilePath* 和 *BackupDatabasePath* 參數所指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span><span class="sxs-lookup"><span data-stu-id="8cc48-188">The DHCP Server file locations are specified by the *DatabasePath*, *DhcpLogFilePath*, and *BackupDatabasePath* parameters in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span></span>

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a><span data-ttu-id="8cc48-189">DNS 伺服器排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-189">DNS Server exclusions</span></span>

<span data-ttu-id="8cc48-190">本節列出當您安裝 DNS 伺服器角色時，會自動傳遞的檔案和資料夾排除專案和程式排除專案。</span><span class="sxs-lookup"><span data-stu-id="8cc48-190">This section lists the file and folder exclusions and the process exclusions that are delivered automatically when you install the DNS Server role.</span></span>

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a><span data-ttu-id="8cc48-191">DNS 伺服器角色的檔案和資料夾排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-191">File and folder exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a><span data-ttu-id="8cc48-192">處理 DNS 伺服器角色的排除專案</span><span class="sxs-lookup"><span data-stu-id="8cc48-192">Process exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a><span data-ttu-id="8cc48-193">檔和儲存服務排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-193">File and Storage Services exclusions</span></span>

<span data-ttu-id="8cc48-194">本節列出當您安裝 [檔案和儲存服務] 角色時，會自動傳遞的檔案和資料夾排除專案。</span><span class="sxs-lookup"><span data-stu-id="8cc48-194">This section lists the file and folder exclusions that are delivered automatically when you install the File and Storage Services role.</span></span> <span data-ttu-id="8cc48-195">以下所列的排除專案不包括叢集角色的排除專案。</span><span class="sxs-lookup"><span data-stu-id="8cc48-195">The exclusions listed below do not include exclusions for the Clustering role.</span></span>

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a><span data-ttu-id="8cc48-196">列印伺服器排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-196">Print Server exclusions</span></span>

<span data-ttu-id="8cc48-197">本節列出當您安裝列印伺服器角色時，會自動傳遞的檔案類型排除、資料夾排除和程式排除。</span><span class="sxs-lookup"><span data-stu-id="8cc48-197">This section lists the file type exclusions, folder exclusions, and the process exclusions that are delivered automatically when you install the Print Server role.</span></span>

#### <a name="file-type-exclusions"></a><span data-ttu-id="8cc48-198">檔案類型排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-198">File type exclusions</span></span>

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a><span data-ttu-id="8cc48-199">資料夾排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-199">Folder exclusions</span></span>

<span data-ttu-id="8cc48-200">這個資料夾是在登錄機碼中指定 `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span><span class="sxs-lookup"><span data-stu-id="8cc48-200">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span></span>

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a><span data-ttu-id="8cc48-201">處理程序排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-201">Process exclusions</span></span>

- `spoolsv.exe`

### <a name="web-server-exclusions"></a><span data-ttu-id="8cc48-202">網頁伺服器排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-202">Web Server exclusions</span></span>

<span data-ttu-id="8cc48-203">本節列出當您安裝網頁伺服器角色時，會自動傳遞的資料夾排除和程式排除專案。</span><span class="sxs-lookup"><span data-stu-id="8cc48-203">This section lists the folder exclusions and the process exclusions that are delivered automatically when you install the Web Server role.</span></span>

#### <a name="folder-exclusions"></a><span data-ttu-id="8cc48-204">資料夾排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-204">Folder exclusions</span></span>

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a><span data-ttu-id="8cc48-205">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="8cc48-205">Process exclusions</span></span>

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a><span data-ttu-id="8cc48-206">關閉掃描 Sysvol\Sysvol 資料夾或 SYSVOL_DFSR \Sysvol 資料夾中的檔案</span><span class="sxs-lookup"><span data-stu-id="8cc48-206">Turning off scanning of files in the Sysvol\Sysvol folder or the SYSVOL_DFSR\Sysvol folder</span></span>

<span data-ttu-id="8cc48-207">或資料夾的目前位置 `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` 及所有子資料夾是複本集根的「檔案系統重新分析」目標。</span><span class="sxs-lookup"><span data-stu-id="8cc48-207">The current location of the `Sysvol\Sysvol` or `SYSVOL_DFSR\Sysvol` folder and all the subfolders is the file system reparse target of the replica set root.</span></span> <span data-ttu-id="8cc48-208">`Sysvol\Sysvol`和 `SYSVOL_DFSR\Sysvol` 資料夾預設會使用下列位置：</span><span class="sxs-lookup"><span data-stu-id="8cc48-208">The `Sysvol\Sysvol` and `SYSVOL_DFSR\Sysvol` folders use the following locations by default:</span></span>

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

<span data-ttu-id="8cc48-209">目前使用中的路徑 `SYSVOL` 是由 NETLOGON 共用所參照，而且可由下列子機碼中的 SysVol 值名稱所決定： `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span><span class="sxs-lookup"><span data-stu-id="8cc48-209">The path to the currently active `SYSVOL` is referenced by the NETLOGON share and can be determined by the SysVol value name in the following subkey: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span></span>

<span data-ttu-id="8cc48-210">從此資料夾及其所有子資料夾中排除下列檔案：</span><span class="sxs-lookup"><span data-stu-id="8cc48-210">Exclude the following files from this folder and all its subfolders:</span></span>

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a><span data-ttu-id="8cc48-211">Windows Server 更新服務排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-211">Windows Server Update Services exclusions</span></span>

<span data-ttu-id="8cc48-212">本節列出當您安裝 Windows Server Update Services (WSUS) 角色時，會自動傳遞的資料夾排除專案。</span><span class="sxs-lookup"><span data-stu-id="8cc48-212">This section lists the folder exclusions that are delivered automatically when you install the Windows Server Update Services (WSUS) role.</span></span> <span data-ttu-id="8cc48-213">WSUS 資料夾是在登錄機碼中指定 `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span><span class="sxs-lookup"><span data-stu-id="8cc48-213">The WSUS folder is specified in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span></span>

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a><span data-ttu-id="8cc48-214">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8cc48-214">See also</span></span>

- [<span data-ttu-id="8cc48-215">設定及驗證 Microsoft Defender 防病毒掃描的排除專案</span><span class="sxs-lookup"><span data-stu-id="8cc48-215">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8cc48-216">根據檔案名、副檔名和資料夾位置，設定及驗證排除</span><span class="sxs-lookup"><span data-stu-id="8cc48-216">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8cc48-217">設定及驗證由進程開啟之檔案的排除專案</span><span class="sxs-lookup"><span data-stu-id="8cc48-217">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8cc48-218">定義排除時所避免的常見錯誤</span><span class="sxs-lookup"><span data-stu-id="8cc48-218">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8cc48-219">自訂、啟動和審閱 Microsoft Defender 防病毒掃描和修正的結果</span><span class="sxs-lookup"><span data-stu-id="8cc48-219">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8cc48-220">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="8cc48-220">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)