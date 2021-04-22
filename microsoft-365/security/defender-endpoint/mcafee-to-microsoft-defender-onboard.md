---
title: McAfee to Microsoft Defender for Endpoint 板載
description: 這是第3階段，板載，可從 McAfee 遷移至 Microsoft Defender for Endpoint。
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
- m365solution-McAfeemigrate
- m365solution-scenario
ms.custom: migrationguides
ms.topic: article
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 973491ffd5f29cef4a6dd652676cad538182f009
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935950"
---
# <a name="migrate-from-mcafee---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>從 McAfee 遷移-階段3：板載至 Microsoft Defender for Endpoint

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


|[![階段 1：準備](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[階段 1：準備](mcafee-to-microsoft-defender-prepare.md) |[![階段 2：設定](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[階段 2：設定](mcafee-to-microsoft-defender-setup.md) |![第 3 階段：導入](images/phase-diagrams/onboard.png)<br/>第 3 階段：導入 |
|--|--|--|
|| |*您在這裡！* |

**歡迎您 [從 Mcafee 端點安全性 (mcafee) 至 Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)，以進行第3階段的遷移**。 此遷移階段包含下列步驟：

1. [板載裝置至 Microsoft Defender For Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint)。
2. [執行偵測測試](#run-a-detection-test)。
3. [卸載 McAfee](#uninstall-mcafee)。
4. [請確定 Microsoft Defender For Endpoint 處於主動模式](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>將裝置上線至適用於端點的 Microsoft Defender

1. 請移至 Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) 並登入。

2. 選擇 [**設定**  >  **裝置管理** 上  >  **架**]。 

3. 在 [ **選取作業系統以啟動上架** 程式] 清單中，選取作業系統。 

4. 在 [ **部署方法**] 底下，選取選項。 遵循連結，並提示您組織的裝置。 需要協助？ 請參閱本文中 (的內 [架方法](#onboarding-methods)) 。

### <a name="onboarding-methods"></a>上架方法
 
根據選取的作業系統而定，部署方法會有所不同。 請參閱下表中所列的資源，以取得上架的協助。

|作業系統  |方法  |
|---------|---------|
|Windows 10     |- [群組原則](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)<br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)<br/>- [Mobile Device Management (Intune) ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)<br/>- [本機腳本](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/><br/>**附注**：本機腳本適用于概念證明，但不適用於實際執行部署。 在實際執行部署中，我們建議使用群組原則、Microsoft 端點設定管理員或 Intune。         |
|-Windows 8.1 企業版 <br/>-Windows 8.1 Pro <br/>-Windows 7 SP1 企業版 <br/>-Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-atp)<br/><br/>**附注**： Microsoft Monitoring Agent 現在是 Azure 記錄分析代理程式。 若要深入瞭解，請參閱 [Log Analytics agent 一覽](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)。        |
|-Windows Server 2019 和更新版本 <br/>-Windows Server 2019 core edition <br/>-Windows Server 版本1803和更新版本 |- [本機腳本](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/>- [群組原則](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp) <br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) <br/>- [System Center Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager) <br/>- [非持久性裝置的 VDI 上架腳本](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi) <br/><br/>**附注**：本機腳本適用于概念證明，但不適用於實際執行部署。 在實際執行部署中，我們建議使用群組原則、Microsoft 端點設定管理員或 Intune。    |
|-Windows Server 2016 <br/>-Windows Server 2012 R2 <br/>-Windows Server 2008 R2 SP1  |- [Microsoft Defender 安全中心](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)<br/>- [Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>-10.15 (Catalina) <br/>-10.14 (Mojave) <br/>-10.13 (高塞拉里昂) <br/><br/>iOS<br/><br/>Linux：<br/>-RHEL 7.2 +<br/>-CentOS Linux 7.2 +<br/>-Ubuntu 16 LTS 或更高版本 LTS<br/>-SLES 12 +<br/>-Debian 9 +<br/>-Oracle Linux 7。2 |[將非 Windows 裝置上線](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-non-windows)  |

## <a name="run-a-detection-test"></a>執行偵測測試

若要驗證架裝置是否正確連接至 Microsoft Defender for Endpoint，您可以執行偵測測試。


|作業系統  |指導方針  |
|---------|---------|
|-Windows 10 <br/>-Windows Server 2019 <br/>-Windows Server，版本1803 <br/>-Windows Server 2016 <br/>-Windows Server 2012 R2     |請參閱 [執行偵測測試](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test)。 <br/><br/>流覽 Microsoft Defender for Endpoint 示範案例網站 ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) 並嘗試一或多個案例。 例如，嘗試 **雲端提供的保護** 示範案例。         |
|macOS<br/>-10.15 (Catalina) <br/>-10.14 (Mojave) <br/>-10.13 (高塞拉里昂)      |下載並使用 DIY 應用程式 [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) 。 <br/><br/>如需詳細資訊，請參閱 [Mac 上的 Microsoft Defender For Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)。        |
|Linux：<br/>-RHEL 7.2 +<br/>-CentOS Linux 7.2 +<br/>-Ubuntu 16 LTS 或更高版本 LTS<br/>-SLES 12 +<br/>-Debian 9 +<br/>-Oracle Linux 7。2 |1. 執行下列命令，並尋找 **1** 的結果： <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. 開啟終端視窗，並執行下列命令： <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. 執行下列命令，列出任何偵測到的威脅： <br/>`mdatp threat list`. <br/><br/>如需詳細資訊，請參閱 [Linux 上的 Microsoft Defender For Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux)。 |

## <a name="uninstall-mcafee"></a>卸載 McAfee

現在，您已將組織的裝置架至 Microsoft Defender for Endpoint，下一步是卸載 McAfee。

若要取得此步驟的協助，請移至您的 McAfee ServicePortal ([http://mysupport.mcafee.com](http://mysupport.mcafee.com)) 。

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>確定 Microsoft Defender for Endpoint 處於主動模式

現在，您已卸載 McAfee，下一步是確定已啟用 Microsoft Defender 防毒軟體和端點偵測和回應，並以主動模式進行。

若要這麼做，請造訪 Microsoft Defender for Endpoint 示範案例網站 ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) 。 請在該頁面上嘗試一或多個示範案例，至少包括下列專案：
- 雲端提供的保護
- PUA (可能有害的應用程式) 
- 網路保護 (NP) 

> [!IMPORTANT]
> 如果您使用的是 Windows Server 2016，您可能需要手動啟動 Microsoft Defender 防病毒。 您可以使用裝置上的 PowerShell Cmdlet 來執行此動作 `mpcmdrun.exe -wdenable` 。

## <a name="next-steps"></a>後續步驟

**恭喜**！ 您已完成 [從 McAfee 到 Microsoft Defender For Endpoint 的遷移](mcafee-to-microsoft-defender-migration.md#the-migration-process)！ 

- 請造訪 Microsoft Defender Security Center () 中的[安全性作業儀表板](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard) [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。 
- [管理 Microsoft Defender For Endpoint，後期遷移](manage-atp-post-migration.md)。
