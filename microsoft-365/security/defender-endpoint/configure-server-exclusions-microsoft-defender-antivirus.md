---
title: 設定 Windows 伺服器上的 Microsoft Defender 防毒軟體排除
ms.reviewer: ''
manager: dansimp
description: Windows伺服器包含根據伺服器角色的自動排除。 您也可以新增自訂排除專案。
keywords: 排除、伺服器、自動排除、自動、自訂、掃描 Microsoft Defender 防毒軟體
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.topic: article
ms.openlocfilehash: f82da8eb0dcba39404c2b7f191e166aa78357cee
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274757"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>設定 Windows 伺服器上的 Microsoft Defender 防毒軟體排除

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Windows Server 2016 和 Windows Server 2019 上的 Microsoft Defender 防毒軟體會根據您指定的伺服器角色所定義的部分排除，自動為您註冊。 這些排除專案不會出現在[Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)中顯示的標準排除清單中。

> [!NOTE]
> [自動排除] 只適用于即時保護 (RTP) 掃描。 在完整/快速或隨選掃描期間，不會接受自動排除。

除了伺服器角色定義的自動排除專案之外，您還可以新增或移除自訂排除。 若要這麼做，請參閱下列文章：
- [根據檔案名、副檔名和資料夾位置，設定及驗證排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [設定及驗證由進程開啟之檔案的排除專案](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a>記住幾點

請牢記下列重要要點：

- 自訂排除優先于自動排除。
- [自動排除] 只適用于即時保護 (RTP) 掃描。 在完整/快速或隨選掃描期間，不會接受自動排除。
- 自訂和重複排除專案不會與自動排除項衝突。
- Microsoft Defender 防毒軟體使用「部署影像服務」和「管理」 (DISM) 工具來判斷電腦上所安裝的角色。

## <a name="opt-out-of-automatic-exclusions"></a>選擇不限自動排除

在 Windows Server 2016 和 Windows 伺服器2019中，安全性情報更新所提供的預先定義的排除只會排除角色或功能的預設路徑。 如果您已在自訂路徑中安裝角色或功能，或是您想要手動控制一組排除，請務必取消在安全性智慧更新中所提供的自動排除專案。 但是請記住，會自動傳遞的排除專案，針對 Windows Server 2016 和2019角色進行優化。 定義排除清單之前，請參閱[建議以定義](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)排除清單。

> [!WARNING]
> 退出自動排除可能會對效能造成不良影響，或導致資料損毀。 針對 Windows Server 2016 和 Windows Server 2019 角色，會自動傳遞的排除專案。

因為預先定義的排除只排除 **預設路徑**，所以如果您將 NTDS 和 SYSVOL 移至另一個 *不同于原始路徑* 的磁片磁碟機或路徑，您必須使用 [這裡](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) 的資訊手動新增排除。

您可以使用「群組原則」、「PowerShell Cmdlet」和 WMI 來停用自動排除清單。

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>使用群組原則來停用 Windows Server 2016 的自動排除清單及 Windows 伺服器2019

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11))]。 以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。
2. 在 [**群組原則管理編輯器**] 中，移至 [電腦設定]，然後按一下 [**系統****管理範本**]。
3. 展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **排除**。
4. 按兩下 [ **關閉自動排除**]，然後將選項設定為 [ **啟用**]。 然後按一下 **[確定]**。 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a>使用 PowerShell Cmdlet 停用 Windows Server 2016 和2019上的自動排除清單

使用下列 Cmdlet：

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

若要深入了解，請參閱下列資源：

- [使用 PowerShell Cmdlet 來設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)。
- 搭配[Microsoft Defender 防毒軟體使用 PowerShell](/powershell/module/defender/)。

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>使用 Windows 管理指令 (WMI) 停用 Windows Server 2016 上的自動排除清單及 Windows 伺服器2019

針對下列屬性，使用 [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference)類別的 **Set** 方法：

```WMI
DisableAutoExclusions
```

如需詳細資訊及允許的參數，請參閱下列各項：
- [Windows DefenderWMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a>自動排除清單

下列各節包含與自動排除檔路徑及檔案類型一起傳遞的排除專案。

### <a name="default-exclusions-for-all-roles"></a>所有角色的預設排除

本節列出所有 Windows Server 2016 和2019角色的預設排除專案。

> [!NOTE]
> 預設位置可能會不同于本文所列的位置。

#### <a name="windows-tempedb-files"></a>Windows"temp" 檔案

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a>Windows更新檔或自動更新檔案

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a>Windows 安全性檔案

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a>群組原則檔

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a>WINS 檔案

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a>檔案複寫服務 (FRS) 排除

- 檔案複寫服務中的檔案 (FRS) 工作資料夾。 在登錄機碼中指定 FRS 工作資料夾 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- FRS 資料庫記錄檔。 FRS 資料庫記錄檔資料夾是在登錄機碼中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- FRS 暫存資料夾。 在登錄機碼中指定暫存資料夾 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- FRS 預先安裝資料夾。 這個資料夾是由資料夾指定 `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- 分散式檔案系統複寫 (DFSR) 資料庫和工作資料夾。 這些資料夾是由登錄機碼指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > 若為自訂位置，請參閱選擇 [不限 [自動排除](#opt-out-of-automatic-exclusions)]。

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

#### <a name="process-exclusions"></a>處理程序排除

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a>Hyper-V 排除

下表列出當您安裝 Hyper-V 角色時，會自動傳遞的檔案類型排除、資料夾排除和程式排除專案。

|檔案類型排除 |資料夾排除  | Process exclusions |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a>SYSVOL 檔案

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a>Active Directory 排除專案

本節列出當您安裝 Active Directory 網域服務時，會自動傳遞的排除專案。

#### <a name="ntds-database-files"></a>NTDS 資料庫檔案

資料庫檔案是在登錄機碼中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a>AD DS 交易記錄檔

交易記錄檔是在登錄機碼中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a>NTDS 工作資料夾

這個資料夾是在登錄機碼中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a>針對 AD DS 和 AD DS 相關支援檔案的處理常式排除

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a>DHCP 伺服器排除

本節列出當您安裝 DHCP 伺服器角色時，會自動傳遞的排除專案。 DHCP 伺服器檔案位置是由登錄機碼中的 *move-databasepath*、 *DhcpLogFilePath* 和 *BackupDatabasePath* 參數所指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a>DNS 伺服器排除

本節列出當您安裝 DNS 伺服器角色時，會自動傳遞的檔案和資料夾排除專案和程式排除專案。

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>DNS 伺服器角色的檔案和資料夾排除

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a>處理 DNS 伺服器角色的排除專案

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a>檔案和儲存體服務排除

本節列出當您安裝檔案及儲存體服務角色時，會自動傳遞的檔案和資料夾排除專案。 以下所列的排除專案不包括叢集角色的排除專案。

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a>列印伺服器排除

本節列出當您安裝列印伺服器角色時，會自動傳遞的檔案類型排除、資料夾排除和程式排除。

#### <a name="file-type-exclusions"></a>檔案類型排除

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a>資料夾排除

這個資料夾是在登錄機碼中指定 `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a>處理程序排除

- `spoolsv.exe`

### <a name="web-server-exclusions"></a>網頁伺服器排除

本節列出當您安裝網頁伺服器角色時，會自動傳遞的資料夾排除和程式排除專案。

#### <a name="folder-exclusions"></a>資料夾排除

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a>Process exclusions

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>關閉掃描 Sysvol\Sysvol 資料夾或 SYSVOL_DFSR \Sysvol 資料夾中的檔案

或資料夾的目前位置 `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` 及所有子資料夾是複本集根的「檔案系統重新分析」目標。 `Sysvol\Sysvol`和 `SYSVOL_DFSR\Sysvol` 資料夾預設會使用下列位置：

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

目前使用中的路徑 `SYSVOL` 是由 NETLOGON 共用所參照，而且可由下列子機碼中的 SysVol 值名稱所決定： `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

從此資料夾及其所有子資料夾中排除下列檔案：

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

### <a name="windows-server-update-services-exclusions"></a>Windows Server Update Services 排除

本節列出當您安裝 Windows Server Update Services (WSUS) 角色時，會自動傳遞的資料夾排除專案。 WSUS 資料夾是在登錄機碼中指定 `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a>另請參閱

- [設定及驗證 Microsoft Defender 防毒軟體掃描的排除專案](configure-exclusions-microsoft-defender-antivirus.md)
- [根據檔案名、副檔名和資料夾位置，設定及驗證排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [設定及驗證由進程開啟之檔案的排除專案](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [定義排除時應避免的常見錯誤](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [自訂、啟動及審閱 Microsoft Defender 防毒軟體掃描和修正的結果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)