---
title: 切換至 Microsoft Defender 的端點-板載
description: 這是第3階段，板載，用於從非 Microsoft 解決方案遷移至 Microsoft Defender for Endpoint。
keywords: 遷移，Microsoft Defender for Endpoint，edr
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
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.custom: migrationguides
ms.topic: article
ms.date: 06/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 832414e9b2a88114cafafbba78e22ea656cc7949
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930460"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>切換至 Microsoft Defender 的端點-階段3：板載

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![階段1： Prepare3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[階段 1：準備](switch-to-microsoft-defender-prepare.md) | [![階段 2：設定](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[階段 2：設定](switch-to-microsoft-defender-setup.md) | ![第 3 階段：導入](images/phase-diagrams/onboard.png)<br/>第 3 階段：導入 |
|--|--|--|
|| |*您在這裡！* |


**歡迎使用 [切換至 Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)的階段 3**。 此遷移階段包含下列步驟：

1. [適用于 Endpoint 的板載裝置](#onboard-devices-to-microsoft-defender-for-endpoint)。
2. [執行偵測測試](#run-a-detection-test)。
3. [確認 Microsoft Defender 防毒軟體在您端點上的被動模式](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints)。
4. [取得 Microsoft Defender 防毒軟體的更新](#get-updates-for-microsoft-defender-antivirus)。
5. [卸載非 Microsoft 解決方案](#uninstall-your-non-microsoft-solution)。 
6. [請確定 Endpoint For Endpoint 的運作正常](#make-sure-defender-for-endpoint-is-working-correctly)。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>將裝置上線至適用於端點的 Microsoft Defender

1. 移至 Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。

2. 選擇 [**設定**  >  **裝置管理** 上  >  **架**]。 

3. 在 [ **選取作業系統以啟動上架** 程式] 清單中，選取作業系統。 

4. 在 [ **部署方法**] 底下，選取選項。 遵循連結，並提示您組織的裝置。 需要協助？ 請參閱本文中 (的內 [架方法](#onboarding-methods)) 。

### <a name="onboarding-methods"></a>上架方法
 
根據作業系統和慣用的方法，部署方法會有所不同。 下表列出可協助您板載 Defender for Endpoint 的資源：

|作業系統  |方法  |
|---------|---------|
| Windows 10     | [群組原則](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[Mobile Device Management (Intune) ](configure-endpoints-mdm.md)<p>[本機腳本](configure-endpoints-script.md) <p>**附注**：本機腳本適用于概念證明，但不適用於實際執行部署。 在實際執行部署中，我們建議使用群組原則、Microsoft Endpoint Configuration Manager 或 Intune。         |
| Windows 8.1 企業版 <p>Windows 8.1 專業版 <p>Windows 7 SP1 Enterprise <p>Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<p>**附注**： Microsoft Monitoring Agent 現在是 Azure 記錄分析代理程式。 若要深入瞭解，請參閱 [Log Analytics agent 一覽](/azure/azure-monitor/platform/log-analytics-agent)。        |
| Windows伺服器2019和更新版本 <p>Windows伺服器2019核心版 <p>Windows伺服器版本1803和更新版本 | [本機腳本](configure-endpoints-script.md) <p>[群組原則](configure-endpoints-gp.md) <p>[Configuration Manager](configure-endpoints-sccm.md) <p>[System Center Configuration Manager](configure-endpoints-sccm.md) <p>[非持久性裝置的 VDI 上架腳本](configure-endpoints-vdi.md) <p>**附注**：本機腳本適用于概念證明，但不適用於實際執行部署。 在實際執行部署中，我們建議使用群組原則、Microsoft Endpoint Configuration Manager 或 Intune。    |
| Windows Server 2016 <p>Windows Server 2012 R2 <p>Windows Server 2008 R2 SP1  | [Microsoft Defender 資訊安全中心](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
| macOS：<p>11.3.1 (大型 Sur)  <p>10.15 (Catalina) <p>10.14 (Mojave)  | [將非 Windows 裝置上線](configure-endpoints-non-windows.md)  |
| iOS | [將非 Windows 裝置上線](configure-endpoints-non-windows.md)  |
| Linux：<p>RHEL 7.2 +<p>CentOS Linux 7.2 +<p>Ubuntu 16 LTS 或更高版本 LTS<p>SLES 12 +<p>Debian 9 +<p>Oracle Linux 7。2 | [將非 Windows 裝置上線](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>執行偵測測試

若要確認您的架裝置已正確連接至 Defender for Endpoint，您可以執行偵測測試。

|作業系統  |指導方針  |
|---------|---------|
| Windows 10 <p>Windows Server 2019 <p>Windows伺服器，版本1803 <p>Windows Server 2016 <p>Windows Server 2012 R2     | 請參閱 [執行偵測測試](run-detection-test.md)。 <p>流覽 Defender for Endpoint 示範案例網站 ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) ，然後嘗試一或多個案例。 例如，嘗試 **雲端提供的保護** 示範案例。    |
| macOS：<p>11.3.1 (大型 Sur)  <p>10.15 (Catalina) <p>10.14 (Mojave)     | 下載並使用 DIY 應用程式 [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) 。 <p>如需詳細資訊，請參閱 [macOS 上的 Defender For Endpoint](microsoft-defender-endpoint-mac.md)。        |
| Linux：<p>RHEL 7.2 +<p>CentOS Linux 7.2 +<p>Ubuntu 16 LTS 或更高版本 LTS<p>SLES 12 +<p>Debian 9 +<p>Oracle Linux 7。2 | 1. 執行下列命令，並尋找 **1** 的結果： <br/>`mdatp health --field real_time_protection_enabled`. <p>2. 開啟終端視窗，並執行下列命令： <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. 執行下列命令，列出任何偵測到的威脅： <br/>`mdatp threat list`. <p>如需詳細資訊，請參閱 [Linux 上的 Defender For Endpoint](microsoft-defender-endpoint-linux.md)。 |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>確認 Microsoft Defender 防毒軟體在您端點上的被動模式中

現在，您的端點已架至 Defender for Endpoint，下一個步驟是確定 Microsoft Defender 防毒軟體是以被動模式執行。 您可以使用 [命令提示字元] 或 PowerShell 執行這項工作，如下表所述：

| 方法  | 處理方式  |
|:-------|:-------|
|命令提示字元     | 1. 在 Windows 裝置上，以系統管理員身分開啟命令提示字元。<p>2. 輸入 `sc query windefend` ，然後按 enter 鍵。<p>3. 檢查結果，確認 Microsoft Defender 防毒軟體是以被動模式執行。         |
| PowerShell     | 1. 在 Windows 裝置上，以系統管理員身分開啟 Windows PowerShell。<p>2. 執行 [MpComputerStatus](/powershell/module/defender/Get-MpComputerStatus) Cmdlet。 <p>3. 在結果清單中，尋找 [ **AMRunningMode：被動式 Mode]** 或 **AMRunningMode： SxS 被動式模式**。    |

> [!NOTE]
> 在某些版本的 Windows 中，您可能會看到 *Windows Defender 防毒軟體*，而不是 *Microsoft Defender 防毒軟體*。

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>手動將 Windows 伺服器上的 Microsoft Defender 防毒軟體設定為被動模式

若要在 Windows 伺服器上，將 Microsoft Defender 防毒軟體設定為被動模式，版本1803或更新版本，或 Windows Server 2019，請遵循下列步驟：

1. 開啟登錄編輯程式，然後流覽至 <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. 編輯 (或建立) DWORD 專案（稱為 **ForcePassiveMode**），並指定下列設定：
   - 將 DWORD 的值設為 **1**。
   - 在 [ **基本**] 底下，選取 [ **十六進位**]。

> [!NOTE]
> 您可以使用其他方法來設定登錄機碼，如下所示：
>- [群組原則喜好設定](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [本機組策略物件工具](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Configuration Manager 中的套件](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Windows Server 2016 上的開始 Microsoft Defender 防毒軟體

如果您使用 Windows Server 2016，您可能必須手動啟動 Microsoft Defender 防毒軟體。 您可以使用裝置上的 PowerShell Cmdlet 來執行此動作 `mpcmdrun.exe -wdenable` 。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>取得 Microsoft Defender 防毒軟體的更新

將 Microsoft Defender 防毒軟體保持在最新狀態，可確保您的裝置具備保護新惡意程式碼和攻擊技巧所需的最新技術和功能，即使 Microsoft Defender 防毒軟體是以被動模式執行。  (請參閱[Microsoft Defender 防毒軟體相容性](microsoft-defender-antivirus-compatibility.md)。 ) 

有兩種與 Microsoft Defender 防毒軟體保持最新狀態相關的更新：

- 安全性智慧更新
- 產品更新

若要取得更新，請遵循[管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)的指導方針。

## <a name="uninstall-your-non-microsoft-solution"></a>卸載非 Microsoft 解決方案

若此時，您可以：

- 將貴組織的裝置架至 Defender for Endpoint，並 
- 已安裝並啟用 Microsoft Defender 防毒軟體， 

接下來的步驟是卸載非 Microsoft endpoint protection 解決方案。 

若要取得此工作的說明，請與您的解決方案供應商的技術支援小組聯繫。

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>確定 Endpoint 已正確運作

現在，您已架至 Defender for Endpoint，而且您已卸載先前的非 Microsoft 解決方案，下一步是確定該 Defender for Endpoint 可以正確運作。 若要達到此目的，一種很好的作法是透過訪問「Defender for Endpoint 示範案例」網站 ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) 。 請在該頁面上嘗試一或多個示範案例，至少包括下列專案：

- 雲端提供的保護
- PUA (可能有害的應用程式) 
- 網路保護 (NP) 

## <a name="next-steps"></a>後續步驟

**恭喜**！ 您已完成 [遷移到 Endpoint 的 Defender](switch-to-microsoft-defender-migration.md#the-migration-process)！ 

- 請造訪 Microsoft Defender 資訊安全中心 () 中的[安全性作業儀表板](security-operations-dashboard.md) [https://securitycenter.windows.com](https://securitycenter.windows.com) 。 
- [管理用於端點、後遷移的 Defender](manage-atp-post-migration.md)。
