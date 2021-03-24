---
title: McAfee to Microsoft Defender for Endpoint 安裝
description: 這是安裝程式，用於從 McAfee 遷移至 Microsoft Defender for Endpoint 的階段2。
keywords: 遷移、windows defender 高級威脅防護、atp、edr
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
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 50e87eb188b64c99372d1a141f6a70e6748ecd2b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058747"
---
# <a name="migrate-from-mcafee---phase-2-set-up-microsoft-defender-for-endpoint"></a>從 McAfee 遷移-階段2：設定 Microsoft Defender for Endpoint

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![階段1：準備](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[階段1：準備](mcafee-to-microsoft-defender-prepare.md) |![階段2：設定](images/phase-diagrams/setup.png)<br/>階段2：設定 |[![階段3：板載](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[階段3：板載](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
||*您在這裡！* | |

**歡迎使用 [從 Mcafee 端點安全性遷移 (mcafee) 至 Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)的安裝階段**。 此階段包含下列步驟：
1. [啟用 Microsoft Defender 防病毒，並確認它是以被動模式](#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)。
2. [取得 Microsoft Defender 防毒軟體的更新](#get-updates-for-microsoft-defender-antivirus)。
3. [將 Microsoft Defender For Endpoint 新增至 McAfee 的排除清單](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-mcafee)。
4. [將 McAfee 新增至 Microsoft Defender 防病毒的排除清單](#add-mcafee-to-the-exclusion-list-for-microsoft-defender-antivirus)。
5. [將 McAfee 新增至 Microsoft Defender For Endpoint 的排除清單](#add-mcafee-to-the-exclusion-list-for-microsoft-defender-for-endpoint)。
6. [設定您的裝置群組、裝置集合及組織單位](#set-up-your-device-groups-device-collections-and-organizational-units)。
7. [設定反惡意程式碼原則和即時保護](#configure-antimalware-policies-and-real-time-protection)。

## <a name="enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode"></a>啟用 Microsoft Defender 防病毒，並確認其為被動模式

在某些 Windows 版本（如 Windows Server）上，當您安裝 McAfee 解決方案時，Microsoft Defender 防毒程式可能已卸載或停用。 這是因為當您安裝協力廠商防病毒產品（例如 McAfee）時，Microsoft Defender 防病毒未進入被動式或 disabled 模式。  (若要深入瞭解，請參閱 [Microsoft Defender 防毒程式相容性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。 ) 

遷移程式的這個步驟包含下列工作：
- [在 Windows Server 上將 DisableAntiSpyware 設定為 false](#set-disableantispyware-to-false-on-windows-server)
- [在 Windows Server 上重新安裝 Microsoft Defender 防病毒](#reinstall-microsoft-defender-antivirus-on-windows-server)程式;
- [在 Windows Server 上將 Microsoft Defender 防毒軟體設為被動模式](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)
- [在 Windows 用戶端裝置上啟用 Microsoft Defender 防病毒](#enable-microsoft-defender-antivirus-on-your-windows-client-devices);和
- [確認 Microsoft Defender 防病毒已設定為被動模式](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode)。  

### <a name="set-disableantispyware-to-false-on-windows-server"></a>在 Windows Server 上將 DisableAntiSpyware 設定為 false

過去使用的 [DisableAntiSpyware](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 登錄機碼停用 Microsoft Defender 防病毒，並部署其他防病毒產品（例如 McAfee）。 一般說來，您的 Windows 裝置和端點上不應該使用此登錄機碼，不過，如果您已 `DisableAntiSpyware` 設定，以下是將其值設為 false 的方式：

1. 在 Windows Server 裝置上，開啟 [登錄編輯程式]。

2. 瀏覽至 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`。

3. 在該資料夾中，尋找名為 **DisableAntiSpyware** 的 DWORD 專案。

   - 如果您看不到該專案，就表示您已全部設定。

   - 如果您看見 **DisableAntiSpyware**，請繼續執行步驟4。

4. 以滑鼠右鍵按一下 [DisableAntiSpyware] DWORD，然後選擇 [ **修改**]。

5. 設定值為 `0` 。  (此項會將登錄機碼的值設為 *false*。 ) 

> [!TIP]
> 若要深入瞭解此登錄機碼，請參閱 [DisableAntiSpyware](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)。

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>在 Windows Server 上重新安裝 Microsoft Defender 防毒程式

> [!NOTE]
> 下列程式僅適用于執行下列 Windows 版本的端點或裝置：
> - Windows Server 2019
> - Windows Server，版本 1803 (僅限核心模式) 
> - Windows Server 2016

1. 在端點或裝置上以本機管理員身分開啟 Windows PowerShell。

2. 執行下列 PowerShell Cmdlet： <br/>
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>

> [!NOTE]
> 在執行 PS 的任務順序中使用 DISM 命令時，需要下列 cmd.exe 路徑。
> 範例：<br/>
> `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
> `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. 若要驗證 Microsoft Defender 防毒程式是否正在執行中，請使用下列 PowerShell Cmdlet： <br/>
   
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>您使用的是 Windows Server 2016 嗎？

如果您使用的是 Windows Server 2016，但在啟用 Microsoft Defender 防病毒時遇到問題，請使用下列 PowerShell Cmdlet：

`mpcmdrun -wdenable`

> [!TIP]
> 仍需要協助嗎？ 請參閱 [Windows Server 2016 和2019上的 Microsoft Defender 防毒軟體](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016)。

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>在 Windows Server 上將 Microsoft Defender 防毒軟體設定為被動模式

因為您的組織仍在使用 McAfee，所以您必須將 Microsoft Defender 防毒軟體設定為被動模式。 如此一來，McAfee 和 Microsoft Defender 防毒軟體可並排執行，直到您完成對 Microsoft Defender for Endpoint 的加入。

1. 開啟登錄編輯程式，然後流覽至 <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. 編輯 (或建立) DWORD 專案（稱為 **ForceDefenderPassiveMode**），並指定下列設定：
   
   - 將 DWORD 的值設為 **1**。
   
   - 在 [ **基本**] 底下，選取 [ **十六進位**]。

> [!NOTE]
> 您可以使用其他方法來設定登錄機碼，如下所示：
>- [群組原則喜好設定](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [本機組策略物件工具](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Configuration Manager 中的套件](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="enable-microsoft-defender-antivirus-on-your-windows-client-devices"></a>在 Windows 用戶端裝置上啟用 Microsoft Defender 防毒程式

因為您的組織已使用 McAfee 作為主要的防病毒方案，所以在組織的 Windows 裝置上很可能會停用 Microsoft Defender 防毒軟體。 遷移程式的這個步驟包含啟用 Microsoft Defender 防毒軟體。 

若要啟用 Microsoft Defender 防病毒，我們建議使用 Intune。 不過，您可以在下表中列出的任何方法：

|方法  |處理方式  |
|---------|---------|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/>**附注**： Intune 現在是 Microsoft 端點管理員。 |1. 移至 [Microsoft 端點管理員管理中心](https://go.microsoft.com/fwlink/?linkid=2109431) 並登入。<br/><br/>2. 選取 [**裝置** 設定配置  >  **檔**]，然後選取您要設定的配置檔案類型。 <br/>如果您尚未建立裝置限制配置檔案類型，或者您想要建立新的 **裝置限制** 配置檔案類型，請參閱 [在 Microsoft Intune 中設定裝置限制設定](https://docs.microsoft.com/intune/device-restrictions-configure)。<br/><br/>3. 選取 [ **屬性**]，然後選取 [ **設定設定：編輯**]。<br/><br/>4. 展開 **Microsoft Defender 防毒軟體**。 <br/><br/>5. 啟用 **雲端提供的保護**。<br/><br/>6. 在 [ **範例提交前提示使用者** ] 下拉式清單中，選取 [ **自動傳送所有範例**]。<br/><br/>7. 在 [偵測 **可能有害的應用程式** ] 下拉式功能表中，選取 [ **啟用** ] 或 [ **審計**]。<br/><br/>8. 選取 [ **審閱 + 儲存**]，然後選擇 [ **儲存**]。<br/><br/>如需 Intune 裝置設定檔的詳細資訊，包括如何建立和設定其設定，請參閱 [什麼是 Microsoft Intune 裝置設定檔？](https://docs.microsoft.com/intune/device-profiles)。|
|Windows 中的控制台     |遵循下列指導： [開啟 Microsoft Defender 防毒軟體](https://docs.microsoft.com/mem/intune/user-help/turn-on-defender-windows)。 <br/><br/>**附注**：在某些 windows 版本中，您可能會看到 *Windows defender 防病毒* ，而不是 *Microsoft Defender 防毒軟體* 。        |
|[高級群組原則管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) <br/>或<br/>[群組原則管理主控台](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. 移至 `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` 。 <br/><br/>2. 尋找稱為關閉 **Microsoft Defender 防病毒** 程式的原則。<br/> <br/>3. 選擇 [ **編輯原則設定**]，並確定已停用原則。 這會啟用 Microsoft Defender 防毒軟體。 <br/><br/>**附注**：在某些 windows 版本中，您可能會看到 *Windows defender 防病毒* ，而不是 *Microsoft Defender 防毒軟體* 。 |

### <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>確認 Microsoft Defender 防病毒處於被動模式

如果您將 Microsoft Defender 防毒軟體設定為被動模式，則 microsoft Defender 防病毒可以與 McAfee 執行。 您可以使用 [命令提示字元] 或 PowerShell 執行這項工作，如下表所述：

|方法  |處理方式  |
|---------|---------|
|命令提示字元     |1. 在 Windows 裝置上，以系統管理員身分開啟命令提示字元。 <br/><br/>2. 輸入 `sc query windefend` ，然後按 enter 鍵。<br/><br/>3. 檢查結果，以確認 Microsoft Defender 防病毒是以被動模式執行。         |
|PowerShell     |1. 在 Windows 裝置上，以系統管理員身分開啟 Windows PowerShell。<br/><br/>2. 執行 [MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/Get-MpComputerStatus) Cmdlet。 <br/><br/>3. 在結果清單中，尋找 [ **AMRunningMode：被動式 Mode]** 或 **AMRunningMode： SxS 被動式模式**。|

> [!NOTE]
> 在某些 Windows 版本中，您可能會看到 *Windows Defender 防病毒* ，而不是 *Microsoft Defender 防毒軟體* 。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>取得 Microsoft Defender 防毒軟體的更新

將 Microsoft Defender 防病毒保持在最新狀態，可確保您的裝置具備保護新惡意程式碼和攻擊技巧所需的最新技術和功能，即使 Microsoft Defender 防病毒是以 [被動模式](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)執行。

有兩種與保持 Microsoft Defender 防病毒的更新相關的更新類型：
- 安全性智慧更新
- 產品更新

若要取得更新，請遵循 [管理 Microsoft Defender 防病毒更新及套用基準](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)的指導方針。

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-mcafee"></a>將 Microsoft Defender for Endpoint 新增至 McAfee 的排除清單

安裝程式的這個步驟包括將 Microsoft Defender for Endpoint 新增至 McAfee 的排除清單和您組織使用的任何其他安全性產品。 

> [!TIP]
> 若要取得排除資訊的說明，請參閱 McAfee 檔，例如下列文章： [Mcafee Endpoint Security 10.5.0-威脅防護模組產品手冊 (McAfee EPolicy Orchestrator) -Windows：設定排除](https://docs.mcafee.com/bundle/endpoint-security-10.5.0-threat-prevention-product-guide-epolicy-orchestrator-windows/page/GUID-71C5FB4B-A143-43E6-8BF0-8B2C16ABE6DA.html)。

要設定的特定排除取決於您的端點或裝置執行所在的 Windows 版本，如下表所列：

|作業系統 |排除 |
|--|--|
|-Windows 10、 [版本 1803](https://docs.microsoft.com/windows/release-health/status-windows-10-1803) 或更新版本 (請參閱 [windows 10 版本資訊](https://docs.microsoft.com/windows/release-health/release-information)) <br/>-安裝[KB4493441](https://support.microsoft.com/help/4493441)的 Windows 10、版本1703或[1709](https://docs.microsoft.com/windows/release-health/status-windows-10-1709) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server，版本1803](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>  |
|- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/><br/>**附注**：監控主機臨時檔案的位置 6 \ 45 可以是不同的編號子資料夾。<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-mcafee-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>將 McAfee 新增至 Microsoft Defender 防病毒的排除清單

在安裝程式的這個步驟中，您可以將 McAfee 和其他安全性解決方案新增至 Microsoft Defender 防病毒排除清單。 

當您將 [排除專案新增至 Microsoft Defender 防病毒掃描](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)時，應新增路徑和程式排除。 請牢記下列幾點：
- 路徑排除排除特定檔案，以及這些檔案存取的任何檔案。
- 處理常式排除排除程式所觸及的任何程式，但不會排除該進程本身。
- 如果您會列出每個可執行檔 ( .exe) 做為路徑排除和程式排除的兩個專案，則會排除該程式及其任何觸控。
- 使用完整路徑，而不是僅以其名稱來列出進程排除。  (僅限名稱的方法是較低的安全性。 ) 

您可以選擇數種方法將您的排除專案新增至 Microsoft Defender 防病毒，如下表所列：

|方法 | 處理方式|
|--|--|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/>**附注**： Intune 現在是 Microsoft 端點管理員。 |1. 移至 [Microsoft 端點管理員管理中心](https://go.microsoft.com/fwlink/?linkid=2109431) 並登入。<br/><br/>2. 選取 [**裝置** 設定配置  >  **檔**]，然後選取您要設定的設定檔。<br/><br/>3. 在 [ **管理**] 下，選取 [ **屬性**]。 <br/><br/>4. 選取 **設定設定：編輯**。<br/><br/>5. 展開 [ **Microsoft Defender 防病毒** 程式]，然後展開 [ **Microsoft Defender 防病毒排除**]。<br/><br/>6. 指定要從 Microsoft Defender 防病毒掃描中排除的檔案和資料夾、副檔名及處理常式。 如需參考，請參閱 [Microsoft Defender 防病毒排除](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)。<br/><br/>7. 選擇 [ **審閱 + 儲存**]，然後選擇 [ **儲存**]。  |
|[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/) |1. 使用 [Configuration Manager 主控台](https://docs.microsoft.com/mem/configmgr/core/servers/manage/admin-console)，移至 [**資產和合規性**  >  **端點保護**  >  的 **反惡意程式碼原則**]，然後選取您要修改的原則。 <br/><br/>2. 指定要從 Microsoft Defender 防病毒掃描中排除的檔案和資料夾、副檔名及處理常式的排除設定。 |
|[群組原則物件](https://docs.microsoft.com/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. 在您的群組原則管理電腦上，開啟「 [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)」，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。<br/><br/>2. 在 [**群組原則管理編輯器**] 中，移至 [電腦設定]，然後按一下 [**系統****管理範本**]。<br/><br/>3. 展開樹狀目錄至 **Windows 元件 > Microsoft Defender 防病毒 > 排除**。<br/>**附注**：在某些 windows 版本中，您可能會看到 *Windows defender 防病毒* ，而不是 *Microsoft Defender 防毒軟體* 。<br/><br/>4. 按兩下 [ **路徑排除** ] 設定，並新增排除。<br/>-將選項設定為 [ **啟用**]。<br/>-在 [ **選項** ] 區段下方，按一下 [ **顯示 ...**]。<br/>-在 [ **值名稱** ] 欄底下，指定各自列的每一個資料夾。<br/>-如果您指定的是檔案，請務必輸入檔案的完整路徑，包含磁碟機號、資料夾路徑、檔案名及副檔名。 在 [**值**] 欄中輸入 **0** 。<br/><br/>5. 按一下 **[確定]**。<br/><br/>6. 按兩下 [ **副檔名排除** ] 設定，並新增排除。<br/>-將選項設定為 [ **啟用**]。<br/>-在 [ **選項** ] 區段下方，按一下 [ **顯示 ...**]。<br/>-在 [ **值名稱** ] 欄位底下的獨佔行中輸入每個副檔名。  在 [**值**] 欄中輸入 **0** 。<br/><br/>7. 按一下 **[確定]**。 |
|本機組策略物件 |1. 在端點或裝置上，開啟 [本機群組原則編輯器]。 <br/><br/>2. 移至 [電腦設定]**系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防病毒**  >  **排除**。 <br/>**附注**：在某些 windows 版本中，您可能會看到 *Windows defender 防病毒* ，而不是 *Microsoft Defender 防毒軟體* 。<br/><br/>3. 指定您的路徑與處理常式排除。 |
|登錄機碼 |1. 匯出下列登錄機 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` 碼：<br/><br/>2. 匯入登錄機碼。 以下列出兩個範例：<br/>-本機路徑： `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>-網路共用： `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-mcafee-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>將 McAfee 新增至 Microsoft Defender for Endpoint 的排除清單

若要將排除專案新增至 Microsoft Defender for Endpoint，您會建立 [指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files)。

1. 請移至 Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) 並登入。

2. 在功能窗格中，選擇 [**設定**  >  **規則** 指標]  >  ****。

3.  在 [檔案 **雜湊** ] 索引標籤上，選擇 [ **新增指示器**]。

3. 在 [ **標記** ] 索引標籤上，指定下列設定：
   - 檔案雜湊 (需要協助嗎？ 請參閱本文中的 [使用 CMPivot 尋找檔案雜湊](#find-a-file-hash-using-cmpivot) 。 ) 
   - 在 [ **(UTC) 到期**] 底下，選擇 [ **從不**]。

4. 在 [ **動作** ] 索引標籤上，指定下列設定：
   - **回應動作**： **允許**
   - 標題和描述

5. 在 [ **範圍** ] 索引標籤的 [ **裝置群組**] 下，選取 [ **所有裝置在我的範圍** ] 或 [ **從清單中選取**]。

6. 在 [ **摘要** ] 索引標籤上，複查設定，然後按一下 [ **儲存**]。

### <a name="find-a-file-hash-using-cmpivot"></a>使用 CMPivot 尋找檔案雜湊

CMPivot 是 Configuration Manager 的內部主控台公用程式。 CMPivot 可讓您存取您環境中裝置的即時狀態。 它會立即在目標集合中所有目前連線的裝置上執行查詢，並傳回結果。 若要深入瞭解，請參閱 [CMPivot 一覽](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot-overview)。

若要使用 CMPivot 來取得檔案雜湊，請遵循下列步驟：

1. 複查 [必要條件](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#prerequisites)。

2. [啟動 CMPivot](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot)。 

3. 連接到 Configuration Manager (`SCCM_ServerName.DomainName.com`) 。

4. 選取 [ **查詢** ] 索引標籤。
 
5. 在 [ **裝置集合** ] 清單中，選擇 [ **所有系統] (預設)**。

6. 在 [查詢] 方塊中，輸入下列查詢：<br/>

```kusto
File(c:\\windows\\notepad.exe)
| project Hash
```
> [!NOTE]
> 在上面的查詢中，以協力廠商的安全性產品流程名稱取代 *notepad.exe* 。 

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>設定裝置群組、裝置集合及組織單位

| 集合類型 | 處理方式 |
|--|--|
|[裝置群組](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) (先前稱為機器群組) 可讓您的安全性作業小組設定安全性功能，例如自動調查和修正。<br/><br/> 在指派對這些裝置的存取時，裝置群組也十分有用，讓安全性作業小組可以視需要採取補救措施。 <br/><br/>裝置群組是在 Microsoft Defender Security Center 中建立的。 |1. 移至 Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) 。<br/><br/>2. 在左側的功能窗格中，選擇 [**設定**  >  **許可權**] [  >  **裝置群組**]。  <br/><br/>3. 選擇 [ **+ 新增裝置群組**]。<br/><br/>4. 指定裝置群組的名稱和描述。<br/><br/>5. 在 [ **自動化層級** ] 清單中，選取一個選項。  (**會自動修正完整修正威脅**。 ) 若要深入瞭解各種自動化層級，請參閱 [如何修正威脅](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)。<br/><br/>6. 指定符合規則的條件，以決定屬於設備群組的裝置。 例如，您可以選擇 [網域]、[作業系統版本] 或 [甚至使用 [裝置標記](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags)]。 <br/><br/>7. 在 [ **使用者存取** ] 索引標籤上，指定應該具有裝置群組中所含裝置之存取權的角色。 <br/><br/>8. 選擇 [ **完成**]。 |
|[裝置集合](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/introduction-to-collections) 可讓您的安全性作業小組管理應用程式、部署規範設定，或在組織中的裝置上安裝軟體更新。 <br/><br/>使用 [Configuration Manager](https://docs.microsoft.com/mem/configmgr/)建立裝置集合。 |遵循 [ [建立集合](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create)] 中的步驟。 |
|[組織單位](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) 可讓您邏輯群組物件，例如使用者帳戶、服務帳戶或電腦帳戶。 然後，您可以將系統管理員指派給特定的組織單位，並套用群組原則以強制執行目標設定設定。<br/><br/> 組織單位是在 [Azure Active Directory 網域服務](https://docs.microsoft.com/azure/active-directory-domain-services)中定義。 | 依照在 [Azure Active Directory 網域服務管理網域中建立組織單位](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou)中的步驟進行。 |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>設定反惡意程式碼原則和即時時間保護

使用 Configuration Manager 和您的裝置集合 (s) 設定反惡意程式碼原則。

- 請參閱 [在 Configuration Manager 中建立及部署 Endpoint Protection 的反惡意程式碼原則](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)。

- 當您建立及設定反惡意程式碼原則時，請務必複查 [即時保護設定](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) ，並 [在第一次看到封鎖時啟用封鎖](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)。

> [!TIP]
> 您可以在架的組織裝置之前部署原則。

## <a name="next-step"></a>下一步

**恭喜**！ 您已完成 [從 McAfee 遷移至 Microsoft Defender For Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)的設定階段！

- [繼續進行階段3：板載至 Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-onboard.md)
