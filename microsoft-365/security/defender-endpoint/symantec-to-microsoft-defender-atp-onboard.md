---
title: Symantec to Microsoft Defender for Endpoint-階段3，上架
description: 這是第3階段，將從 Symantec 遷移至 Microsoft Defender for Endpoint
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: f2b2d5ca9f841e36df37f025a9b5856fc7e2dc6a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538360"
---
# <a name="migrate-from-symantec---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>從 Symantec 遷移-階段3：板載至 Microsoft Defender for Endpoint

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![階段 1：準備](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[階段 1：準備](symantec-to-microsoft-defender-atp-prepare.md) |[![階段 2：設定](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[階段 2：設定](symantec-to-microsoft-defender-atp-setup.md) |![第 3 階段：導入](images/phase-diagrams/onboard.png)<br/>第 3 階段：導入 |
|--|--|--|
|| |*您在這裡！* |


**歡迎您 [從 Symantec 遷移至 Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)的階段 3**。 此遷移階段包含下列步驟：

1. [板載裝置至 Microsoft Defender For Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint)。

2. [執行偵測測試](#run-a-detection-test)。

3. [確認 Microsoft Defender 防毒軟體在您端點上的被動模式](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints)。

4. [取得 Microsoft Defender 防毒軟體的更新](#get-updates-for-microsoft-defender-antivirus)。

5. [卸載 Symantec](#uninstall-symantec)。

6. [請確定 Microsoft Defender For Endpoint 是否運作正常](#make-sure-microsoft-defender-for-endpoint-is-working-correctly)。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>將裝置上線至適用於端點的 Microsoft Defender

1. 移至 Microsoft Defender 資訊安全中心 ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) 並登入。

2. 選擇 [**設定**  >  **裝置管理** 上  >  **架**]。 

3. 在 [ **選取作業系統以啟動上架** 程式] 清單中，選取作業系統。 

4. 在 [ **部署方法**] 底下，選取選項。 遵循連結，並提示您組織的裝置。 需要協助？ 請參閱本文中 (的內 [架方法](#onboarding-methods)) 。

### <a name="onboarding-methods"></a>上架方法
 
根據選取的作業系統而定，部署方法會有所不同。 請參閱下表中所列的資源，以取得上架的協助。

|作業系統  |方法  |
|---------|---------|
|Windows 10     | [群組原則](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[Mobile Device Management (Intune) ](configure-endpoints-mdm.md)<p>[本機腳本](configure-endpoints-script.md) <br/>**附注**：本機腳本適用于概念證明，但不適用於實際執行部署。 在實際執行部署中，我們建議使用群組原則、Microsoft Endpoint Configuration Manager 或 Intune。         |
| Windows 8.1 企業版 <p>Windows 8.1 專業版 <p>Windows 7 SP1 Enterprise<p>Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)<br/>**附注**： Microsoft Monitoring Agent 現在是 Azure 記錄分析代理程式。 若要深入瞭解，請參閱 [Log Analytics agent 一覽](/azure/azure-monitor/platform/log-analytics-agent)。        |
| Windows伺服器2019和更新版本 <p>Windows伺服器2019核心版<p>Windows伺服器版本1803和更新版本 | [本機腳本](configure-endpoints-script.md)<p>[群組原則](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[System Center Configuration Manager](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)<p>[非持久性裝置的 VDI 上架腳本](configure-endpoints-vdi.md) <br/>**附注**：本機腳本適用于概念證明，但不適用於實際執行部署。 在實際執行部署中，我們建議使用群組原則、Microsoft Endpoint Configuration Manager 或 Intune。    |
| Windows Server 2016<p>Windows Server 2012 R2<p>Windows Server 2008 R2 SP1  | [Microsoft Defender 資訊安全中心](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS<p>11.3.1 (大型 Sur)  <p>10.15 (Catalina) <p>10.14 (Mojave)  |[將非 Windows 裝置上線](configure-endpoints-non-windows.md)  |
|iOS |[將非 Windows 裝置上線](configure-endpoints-non-windows.md)  |
|Linux：<p>RHEL 7.2 +<p>CentOS Linux 7.2 +<p>Ubuntu 16 LTS 或更高版本 LTS<p>SLES 12 +<p>Debian 9 +<p>Oracle Linux 7。2 |[將非 Windows 裝置上線](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>執行偵測測試

若要驗證架裝置是否正確連接至 Microsoft Defender for Endpoint，您可以執行偵測測試。

|作業系統  |指導方針  |
|---------|---------|
| Windows 10<p>Windows Server 2019<p>Windows伺服器，版本1803<p>Windows Server 2016<p>Windows Server 2012 R2     |請參閱 [執行偵測測試](run-detection-test.md)。 <p>流覽 Microsoft Defender for Endpoint 示範案例網站 ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) 並嘗試一或多個案例。 例如，嘗試 **雲端提供的保護** 示範案例。         |
|macOS：<p>11.3.1 (大型 Sur) <p>10.15 (Catalina) <p>10.14 (Mojave)      |下載並使用 DIY 應用程式 [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) 。 <p>如需詳細資訊，請參閱 [macOS 上的 Microsoft Defender For Endpoint](microsoft-defender-endpoint-mac.md)。        |
|Linux：<p>RHEL 7.2 +<p>CentOS Linux 7.2 +<p>Ubuntu 16 LTS 或更高版本 LTS<p>SLES 12 +<p>Debian 9 +<p>Oracle Linux 7。2 |1. 執行下列命令，並尋找 **1** 的結果： <br/>`mdatp health --field real_time_protection_enabled`. <p>2. 開啟終端視窗，並執行下列命令： <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. 執行下列命令，列出任何偵測到的威脅： <br/>`mdatp threat list`. <p>如需詳細資訊，請參閱 [Linux 上的 Microsoft Defender For Endpoint](microsoft-defender-endpoint-linux.md)。 |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>確認 Microsoft Defender 防毒軟體在您端點上的被動模式中

現在，您的端點已架至 Defender for Endpoint，下一個步驟是確定 Microsoft Defender 防毒軟體是以被動模式執行。 您可以使用 [命令提示字元] 或 PowerShell 執行這項工作，如下表所述：

| 方法    | 處理方式 |
|:--|:--|
| 命令提示字元    | 1. 在 Windows 裝置上，以系統管理員身分開啟命令提示字元。 <p>2. 輸入 `sc query windefend` ，然後按 enter 鍵。 <p>3. 檢查結果，確認 Microsoft Defender 防毒軟體是以被動模式執行。 |
|PowerShell | 1. 在 Windows 裝置上，以系統管理員身分開啟 Windows PowerShell。 <p>2. 執行 `Get-MpComputerStatus` Cmdlet。 <p>3. 在結果清單中，尋找 [ **AMRunningMode：被動式 Mode]** 或 **AMRunningMode： SxS 被動式模式**。 |

> [!NOTE]
> 在某些版本的 Windows 中，您可能會看到 Windows Defender 防毒軟體，而不是 Microsoft Defender 防毒軟體。

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>手動將 Windows 伺服器上的 Microsoft Defender 防毒軟體設定為被動模式

若要在 Windows 伺服器上，將 Microsoft Defender 防毒軟體設定為被動模式，版本1803或更新版本，或 Windows Server 2019，請遵循下列步驟：

1. 開啟 [登錄編輯程式]，然後流覽至 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` 。

2. 編輯 (或建立) DWORD 專案（稱為 **ForcePassiveMode**），並指定下列設定：

   - 將 DWORD 的值設為1。
   - 在 [基本] 底下，選取 [十六進位]。

> [!NOTE]
> 您可以使用其他方法來設定登錄機碼，如下所示：
> - 群組原則喜好設定
> - 本機組策略物件工具
> - Configuration Manager 中的套件

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Windows Server 2016 上的開始 Microsoft Defender 防毒軟體

如果您使用 Windows Server 2016，您可能必須手動啟動 Microsoft Defender 防毒軟體。 您可以使用裝置上的 PowerShell Cmdlet 來執行此動作 `mpcmdrun.exe -wdenable` 。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>取得 Microsoft Defender 防毒軟體的更新

將 Microsoft Defender 防毒軟體保持在最新狀態，可確保您的裝置具備保護新惡意程式碼和攻擊技巧所需的最新技術和功能，即使 Microsoft Defender 防毒軟體是以被動模式執行。

有兩種與 Microsoft Defender 防毒軟體保持最新狀態相關的更新：

- 安全性智慧更新
- 產品更新

若要取得更新，請遵循[管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)的指導方針。

## <a name="uninstall-symantec"></a>卸載 Symantec

現在，您已將組織的裝置架至 Microsoft Defender for Endpoint，下一步是卸載 Symantec。

1. 停用 Symantec 中的[篡改保護](https://knowledge.broadcom.com/external/article?legacyId=tech192023)。

2. 刪除 Symantec 的卸載密碼：<br/>

   1. 在您的 Windows 裝置上，以系統管理員身分開啟登錄編輯程式。

   2. 移至`HKEY_LOCAL_MACHINE\SOFTWARE\Symantec\Symantec Endpoint Protection\SMC`。

   3. 尋找名為 **SmcInstData** 的專案。 

   4. 以滑鼠右鍵按一下專案，然後選擇 [ **刪除**]。 

3. 從您的裝置移除 Symantec。 如需相關資訊，請參閱 Broadcom 的檔。 以下是一些 Broadcom 資源： 

   - [卸載 Symantec Endpoint Protection](https://knowledge.broadcom.com/external/article/156148/uninstall-symantec-endpoint-protection.html)

   - Windows 裝置：[手動卸載 Windows 上的 Endpoint Protection 14 用戶端](https://knowledge.broadcom.com/external/article?articleId=170040)
   
   - macOS 電腦： [使用 RemoveSymantecMacFiles 移除 Mac 版 Symantec 軟體](https://knowledge.broadcom.com/external/article?articleId=151387)
   
   - linux 裝置：[在 Linux 上的 Endpoint Protection 常見問題](https://knowledge.broadcom.com/external/article?articleId=162054)

## <a name="make-sure-microsoft-defender-for-endpoint-is-working-correctly"></a>確定 Microsoft Defender for Endpoint 是否運作正常

現在，您已卸載 Symantec，下一個步驟是確定已正確使用 Defender for Endpoint。 流覽 Microsoft Defender for Endpoint 示範案例網站 ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) 。 請在該頁面上嘗試一或多個示範案例，至少包括下列專案：
- 雲端提供的保護
- PUA (可能有害的應用程式) 
- 網路保護 (NP) 

## <a name="next-steps"></a>後續步驟

**恭喜**！ 您已完成 [從 Symantec 遷移至 Microsoft Defender For Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)！ 
- 請造訪 Microsoft Defender 資訊安全中心 () 中的[安全性作業儀表板](security-operations-dashboard.md) [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。 
- [管理 Microsoft Defender For Endpoint，後期遷移](manage-atp-post-migration.md)。
