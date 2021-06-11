---
title: 切換至 Microsoft Defender for Endpoint 安裝
description: 階段2，設定處理常式切換至 Microsoft Defender for Endpoint 時。
keywords: 遷移，Microsoft Defender for Endpoint，edr，Windows Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
ms.topic: article
ms.custom: migrationguides
ms.date: 05/20/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 2ea8cc323220024406a49eda8d6a7c0b42ca71a4
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594046"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>切換至 Microsoft Defender for Endpoint-階段2：設定

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![階段 1：準備](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[階段 1：準備](switch-to-microsoft-defender-prepare.md) |![階段 2：設定](images/phase-diagrams/setup.png)<br/>階段 2：設定 |[![階段3： Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[第 3 階段：導入](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*您在這裡！* | |

**歡迎使用 [切換到 Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)的安裝階段**。 此階段包含下列步驟：

1. [在您的端點上重新安裝/啟用 Microsoft Defender 防毒軟體](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)。
2. [設定端點的 Defender](#configure-defender-for-endpoint)。
3. [將用於端點的 Defender 新增至現有解決方案的排除清單](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)。
4. [將現有的解決方案新增至 Microsoft Defender 防毒軟體的排除清單](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus)。
5. [設定您的裝置群組、裝置集合及組織單位](#set-up-your-device-groups-device-collections-and-organizational-units)。
6. [設定反惡意程式碼原則和即時保護](#configure-antimalware-policies-and-real-time-protection)。


## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>在您的端點上重新安裝/啟用 Microsoft Defender 防毒軟體

在某些版本的 Windows 上，當您安裝非 Microsoft 防毒軟體/反惡意軟體解決方案時，可能會卸載或停用 Microsoft Defender 防毒軟體。 除非裝置架至 Defender for Endpoint Microsoft Defender 防毒軟體，否則不會在 active 模式中以非 Microsoft 防病毒解決方案的模式執行。 若要深入瞭解，請參閱[Microsoft Defender 防毒軟體相容性](microsoft-defender-antivirus-compatibility.md)。

現在，您已計畫切換至 Defender for Endpoint，您可能需要採取一定的步驟來重新安裝或啟用 Microsoft Defender 防毒軟體。 


| 端點類型  | 處理方式  |
|---------|---------|
| Windows 用戶端 (如執行 Windows 10 的端點)      | 一般說來，除非已卸載 Microsoft Defender 防毒軟體) ，否則您不需要對 Windows 用戶端執行任何動作 (。 原因如下： <p>Microsoft Defender 防毒軟體應該仍然安裝，但在遷移程式的這一點很可能會停用。<p> 安裝非 Microsoft 防毒軟體/反惡意軟體方案，且用戶端尚未架至 Defender for Endpoint 時，會自動停用 Microsoft Defender 防毒軟體。 <p>稍後，當用戶端端點架至 Defender for Endpoint 時，如果這些端點執行的是非 Microsoft 防病毒方案，則 Microsoft Defender 防毒軟體會進入被動模式。 <p>如果卸載非 Microsoft 防病毒方案，Microsoft Defender 防毒軟體會自動進入主動模式。  |
|Windows 伺服器     | 在 Windows Server 上，您必須重新安裝 Microsoft Defender 防毒軟體，並手動將其設為被動模式。 原因如下： <p>在 Windows 伺服器上，當安裝非 microsoft 防毒軟體/反惡意軟體時，Microsoft Defender 防毒軟體無法與非 microsoft 防病毒解決方案一起執行。 在這種情況下，會以手動方式停用或卸載 Microsoft Defender 防毒軟體。 <p>若要在 Windows 伺服器上重新安裝或啟用 Microsoft Defender 防毒軟體，請執行下列 taks： <p>- 只有在必要時[，才 Windows Server (上設定 DisableAntiSpyware 為 false](#set-disableantispyware-to-false-on-windows-server)) <br/>- [重新安裝 Windows Server 上的 Microsoft Defender 防毒軟體](#reinstall-microsoft-defender-antivirus-on-windows-server)<br/>- [在 Windows 伺服器上將 Microsoft Defender 防毒軟體設定為被動模式](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)       |


若要深入瞭解使用非 Microsoft 防防毒保護的 Microsoft Defender 防毒軟體狀態，請參閱[Microsoft Defender 防毒軟體相容性](microsoft-defender-antivirus-compatibility.md)。

### <a name="set-disableantispyware-to-false-on-windows-server"></a>在 Windows Server 上將 DisableAntiSpyware 設定為 false

過去使用的[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)登錄機碼停用 Microsoft Defender 防毒軟體，並部署其他防病毒產品（例如 McAfee、Symantec 或其他）。 **一般說來，您的 Windows 裝置和端點上不應該使用此登錄機碼，** 不過，*如果您已* `DisableAntiSpyware` 設定，以下是將其值設為 false 的方式：

1. 在 Windows 伺服器裝置上，開啟 [登錄編輯程式]。

2. 瀏覽至 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`。

3. 在該資料夾中，尋找名為 **DisableAntiSpyware** 的 DWORD 專案。
   - 如果您看不到該專案，就表示您已全部設定。
   - 如果您看見 **DisableAntiSpyware**，請繼續執行步驟4。

4. 以滑鼠右鍵按一下 [DisableAntiSpyware] DWORD，然後選擇 [ **修改**]。

5. 設定值為 `0` 。  (此動作會將登錄機碼的值設為 *false*。 ) 

> [!TIP]
> 若要深入瞭解此登錄機碼，請參閱 [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)。

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>重新安裝 Windows Server 上的 Microsoft Defender 防毒軟體

> [!IMPORTANT]
> 下列程式僅適用于執行下列 Windows 版本的端點或裝置：
> - Windows Server 2019
> - Windows伺服器，版本 1803 (僅限核心模式) 
> - Windows Server 2016 (請參閱下一節[使用 Windows Server 2016？](#are-you-using-windows-server-2016)) 

1. 在端點或裝置上，以本機系統管理員身分開啟 Windows PowerShell。

2. 執行下列 PowerShell Cmdlet： <br/>   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <p>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
 
   > [!NOTE]
   > 在執行 PS 的任務順序中使用 DISM 命令時，需要下列 cmd.exe 路徑。
   > 範例：<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<p>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. 若要驗證 Microsoft Defender 防毒軟體是否正在執行中，請使用下列 PowerShell Cmdlet： <br/>
   `Get-Service -Name windefend`

   尋找 [ *正在* 執行] 的狀態。

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>在 Windows 伺服器上將 Microsoft Defender 防毒軟體設定為被動模式

1. 開啟登錄編輯程式，然後流覽至 <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. 編輯 (或建立) DWORD 專案（稱為 **ForcePassiveMode**），並指定下列設定：
   - 將 DWORD 的值設為 **1**。
   - 在 [ **基本**] 底下，選取 [ **十六進位**]。

> [!NOTE]
> 在上架至 Defender for Endpoint 之後，您可能必須將 Windows 伺服器上的 Microsoft Defender 防毒軟體設定為被動模式。

### <a name="are-you-using-windows-server-2016"></a>您是否正在使用 Windows Server 2016？

如果您有 Windows Server 2016 執行的端點，您就無法在非 Microsoft 防毒軟體/反惡意軟體方案旁執行 Microsoft Defender 防毒軟體。 Microsoft Defender 防毒軟體無法在 Windows Server 2016 上以被動模式執行。 在此情況下，您將需要卸載非 Microsoft 防病毒/反惡意程式碼解決方案，然後改為安裝/啟用 Microsoft Defender 防毒軟體。 若要深入瞭解，請參閱 [防病毒解決方案與 Defender For Endpoint 的相容性](microsoft-defender-antivirus-compatibility.md)。

如果您正在使用 Windows Server 2016，但在啟用 Microsoft Defender 防毒軟體時出現問題，請遵循下列步驟：

1. 在裝置上，以系統管理員身分開啟 PowerShell。

2. 輸入下列 PowerShell Cmdlet： `mpcmdrun -wdenable`

> [!TIP]
> 如需詳細資訊，請參閱[Windows Server 上的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-on-windows-server.md)。

## <a name="configure-defender-for-endpoint"></a>設定端點的 Defender

遷移程式的這個步驟包括設定端點的 Microsoft Defender 防毒軟體。 我們建議使用 Intune;不過，您可以在下表中列出的任何方法：

|方法  |處理方式  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**附注**： Intune 現在是 Microsoft 端點管理員的一部分。 | 1. 移至[Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)並登入。<p> 2. 選取 [**裝置** 設定配置  >  **檔**]，然後選取您要設定的配置檔案類型。 如果您尚未建立裝置限制配置檔案類型，或者您想要建立新的 **裝置限制** 配置檔案類型，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。<p> 3. 選取 [ **屬性**]，然後選取 [ **設定設定：編輯**]。<p> 4. 展開 **Microsoft Defender 防毒軟體**。 <p> 5. 啟用 **雲端提供的保護**。<p> 6. 在 [ **範例提交前提示使用者** ] 下拉式清單中，選取 [ **自動傳送所有範例**]。<p> 7. 在 [偵測 **可能有害的應用程式** ] 下拉式功能表中，選取 [ **啟用** ] 或 [ **審計**]。<p> 8. 選取 [ **審閱 + 儲存**]，然後選擇 [ **儲存**]。<p>**提示**：如需 Intune 裝置設定檔的詳細資訊，包括如何建立和設定其設定，請參閱 [什麼是 Microsoft Intune 裝置設定檔？](/intune/device-profiles)。|
|Windows 中的控制台     |請遵循以下的指導方針：[開啟 Microsoft Defender 防毒軟體](/mem/intune/user-help/turn-on-defender-windows)。 <p>**附注**：在某些版本的 Windows 中，您可能會看到 *Windows Defender 防毒軟體*，而不是 *Microsoft Defender 防毒軟體*。        |
|[高級群組原則管理](/microsoft-desktop-optimization-pack/agpm/) <br/>或<br/>[群組原則管理主控台](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  | 1. 移至 [電腦設定]**系統**  >  **管理範本**  >  **Windows 元件**]  >  **Microsoft Defender 防毒軟體**。 <p> 2. 尋找稱為「**關閉 Microsoft Defender 防毒軟體** 的原則」。<p> 3. 選擇 [ **編輯原則設定**]，並確定已停用原則。 此巨集指令會啟用 Microsoft Defender 防毒軟體。 <p>**附注**：在某些版本的 Windows 中，您可能會看到 *Windows Defender 防毒軟體*，而不是 *Microsoft Defender 防毒軟體*。 |

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>將 Microsoft Defender for Endpoint 新增至現有解決方案的排除清單

安裝程式的這個步驟包括將 Defender for Endpoint 新增至現有的 Endpoint protection 解決方案和組織所使用的任何其他安全性產品的排除清單。 

> [!TIP]
> 若要取得有關設定排除專案的說明，請參閱您的解決方案供應商的檔。

要設定的特定排除專案將取決於您的端點或裝置執行的 Windows 版本，如下表所列：

|作業系統 |排除項目 |
|--|--|
|Windows 10，[版本 1803](/windows/release-health/status-windows-10-1803)或更新版本 (請參閱[Windows 10 版本資訊](/windows/release-health/release-information)) <p>已安裝[KB4493441](https://support.microsoft.com/help/4493441)的 Windows 10 版本1703或1709 <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows伺服器，版本1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<p>  |
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows伺服器 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<p>**附注**：監控主機暫存檔 6 \ 45 可以是不同的編號子資料夾。 <p>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>將現有的解決方案新增至 Microsoft Defender 防毒軟體的排除清單

在安裝程式的這個步驟中，您可以將現有的解決方案新增至 Microsoft Defender 防毒軟體排除清單。 您可以選擇數種方法將您的排除專案新增至 Microsoft Defender 防毒軟體，如下表所列：

|方法 | 處理方式|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**附注**： Intune 現在是 Microsoft 端點管理員的一部分。 | 1. 移至[Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)並登入。<p> 2. 選取 [**裝置** 設定配置  >  **檔**]，然後選取您要設定的設定檔。<p> 3. 在 [ **管理**] 下，選取 [ **屬性**]。<p> 4. 選取 **設定設定：編輯**。<p> 5. 展開 **Microsoft Defender 防毒軟體**，然後展開 [ **Microsoft Defender 防毒軟體排除**]。<p> 6. 指定要從 Microsoft Defender 防毒軟體掃描中排除的檔案和資料夾、副檔名及處理常式。 如需參考，請參閱[Microsoft Defender 防毒軟體排除](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)。<p> 7. 選擇 [ **審閱 + 儲存**]，然後選擇 [ **儲存**]。  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) | 1. 使用 [Configuration Manager 主控台](/mem/configmgr/core/servers/manage/admin-console)，移至 [**資產及規範**  >  **Endpoint Protection**  >  **反惡意軟體原則**]，然後選取您要修改的原則。 <p> 2. 指定要排除在 Microsoft Defender 防毒軟體掃描之外之檔案和資料夾、副檔名及處理常式的排除設定。 |
|[群組原則物件](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. 在您的群組原則管理電腦上，開啟「 [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)」，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。<p> 2. 在 [**群組原則管理編輯器**] 中，移至 [電腦設定]，然後選取 [**系統****管理範本**]。<p> 3. 展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體 > 排除** 專案。<br/>**附注**：在某些版本的 Windows 中，您可能會看到 *Windows Defender 防毒軟體*，而不是 *Microsoft Defender 防毒軟體*。<p> 4. 按兩下 [ **路徑排除** ] 設定，並新增排除。<br/>-將選項設定為 [ **啟用**]。<br/>-在 [ **選項** ] 區段下，選取 [ **顯示 ...**]。<br/>-在 [ **值名稱** ] 欄底下，指定各自列的每一個資料夾。<br/>-如果您指定的是檔案，請務必輸入檔案的完整路徑，包含磁碟機號、資料夾路徑、檔案名及副檔名。 在 [**值**] 欄中輸入 **0** 。<p> 5. 選取 **[確定]**。<p> 6. 按兩下 [ **副檔名排除** ] 設定，並新增排除。<br/>-將選項設定為 [ **啟用**]。<br/>-在 [ **選項** ] 區段下，選取 [ **顯示 ...**]。<br/>-在 [ **值名稱** ] 欄位底下的獨佔行中輸入每個副檔名。  在 [**值**] 欄中輸入 **0** 。<p> 7. 選取 **[確定]**。 |
|本機組策略物件 |1. 在端點或裝置上，開啟 [本機群組原則編輯器]。 <p>2. 移至 [電腦設定]**系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **排除**。<p>**附注**：在某些版本的 Windows 中，您可能會看到 *Windows Defender 防毒軟體*，而不是 *Microsoft Defender 防毒軟體*。<p>3. 指定您的路徑與處理常式排除。 |
|登錄機碼 |1. 匯出下列登錄機 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` 碼：<p>2. 匯入登錄機碼。 以下列出兩個範例：<br/>-本機路徑： `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>-網路共用： `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>請留意有關排除的下列幾點

當您在[Microsoft Defender 防毒軟體掃描](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)時新增排除專案時，應新增路徑和程式排除。 

請牢記下列幾點：

- *路徑排除* 排除特定檔案，以及這些檔案存取的任何檔案。
- *處理常式排除* 排除程式所觸及的任何程式，但不會排除該進程本身。
- 使用完整路徑，而不是僅以其名稱來列出進程排除。  (僅限名稱的方法是較低的安全性。 ) 
- 如果您會列出每個可執行檔 (.exe) 做為路徑排除和程式排除的兩個專案，則會排除該程式和其接觸的任何內容。


## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>設定裝置群組、裝置集合及組織單位

裝置群組、裝置集合及組織單位可讓您的安全小組有效且有效地管理及指派安全性原則。 下表說明這些群組中的每一個，以及如何加以設定。 您的組織可能並未使用全部三個集合類型。

| 集合類型 | 處理方式 |
|--|--|
|[裝置群組](/microsoft-365/security/defender-endpoint/machine-groups) (先前稱為 *機器群組*) 可讓您的安全性作業小組設定安全性功能，例如自動調查和修正。<p>在指派對這些裝置的存取時，裝置群組也十分有用，讓安全性作業小組可以視需要採取補救措施。 <p>在[Microsoft Defender 資訊安全中心](microsoft-defender-security-center.md)中建立裝置群組。 |1. 移至 Microsoft Defender 資訊安全中心 ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) 。<p>2. 在左側的功能窗格中，選擇 [**設定**  >  **許可權**  >  **裝置群組**]。  <p>3. 選擇 [ **+ 新增裝置群組**]。<p>4. 指定裝置群組的名稱和描述。<p>5. 在 [ **自動化層級** ] 清單中，選取一個選項。  (**會自動修正完整修正威脅**。 ) 若要深入瞭解各種自動化層級，請參閱 [如何修正威脅](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)。<p>6. 指定符合規則的條件，以決定屬於設備群組的裝置。 例如，您可以選擇 [網域]、[作業系統版本] 或 [甚至使用 [裝置標記](/microsoft-365/security/defender-endpoint/machine-tags)]。<p>7. 在 [ **使用者存取** ] 索引標籤上，指定應該具有裝置群組中所含裝置之存取權的角色。 <p>8. 選擇 [ **完成**]。 |
|[裝置集合](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) 可讓您的安全性作業小組管理應用程式、部署規範設定，或在組織中的裝置上安裝軟體更新。<p>使用 [Configuration Manager](/mem/configmgr/)建立裝置集合。 |遵循 [ [建立集合](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create)] 中的步驟。 |
|[組織單位](/azure/active-directory-domain-services/create-ou) 可讓您邏輯群組物件，例如使用者帳戶、服務帳戶或電腦帳戶。 然後，您可以將系統管理員指派給特定的組織單位，並套用群組原則以強制執行目標設定設定。<p> 組織單位是在[Azure Active Directory 網域服務](/azure/active-directory-domain-services)中定義。 | 依照在[Azure Active Directory 網域服務管理網域中建立組織單位](/azure/active-directory-domain-services/create-ou)中的步驟進行。 |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>設定反惡意程式碼原則和即時時間保護

使用 Configuration Manager 和您的裝置集合 (s) 設定反惡意程式碼原則。

- 請參閱[在 Configuration Manager 中建立及部署 Endpoint Protection 的反惡意程式碼原則](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)。
- 當您建立及設定反惡意程式碼原則時，請務必複查 [即時保護設定](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) ，並 [在第一次看到封鎖時啟用封鎖](configure-block-at-first-sight-microsoft-defender-antivirus.md)。

> [!TIP]
> 您可以在架的組織裝置之前部署原則。

## <a name="next-step"></a>下一步

**恭喜**！ 您已完成 [切換至 Defender For Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)的安裝階段！

- [繼續進行階段3：板載到 Defender for Endpoint](switch-to-microsoft-defender-onboard.md)
