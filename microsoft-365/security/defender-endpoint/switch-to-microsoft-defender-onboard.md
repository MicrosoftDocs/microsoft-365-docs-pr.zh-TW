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
ms.custom: migrationguides
ms.topic: article
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 6b3b9fda0060108bd6a3c48188ff6e89261be096
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327243"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>切換至 Microsoft Defender 的端點-階段3：板載

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![階段1： Prepare3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[階段 1：準備](switch-to-microsoft-defender-prepare.md) | [![階段 2：設定](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[階段 2：設定](switch-to-microsoft-defender-setup.md) | ![第 3 階段：導入](images/phase-diagrams/onboard.png)<br/>第 3 階段：導入 |
|--|--|--|
|| |*您在這裡！* |


**歡迎使用 [切換至 Microsoft Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)的階段 3**。 此遷移階段包含下列步驟：

1. [板載裝置至 Microsoft Defender For Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint)。
2. [執行偵測測試](#run-a-detection-test)。
3. [卸載非 Microsoft 解決方案](#uninstall-your-non-microsoft-solution)。
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
|Windows 10     |- [群組原則](configure-endpoints-gp.md)<br/>- [Configuration Manager](configure-endpoints-sccm.md)<br/>- [Mobile Device Management (Intune) ](configure-endpoints-mdm.md)<br/>- [本機腳本](configure-endpoints-script.md) <p>**附注**：本機腳本適用于概念證明，但不適用於實際執行部署。 在實際執行部署中，我們建議使用群組原則、Microsoft 端點設定管理員或 Intune。         |
|-Windows 8.1 企業版 <br/>-Windows 8.1 Pro <br/>-Windows 7 SP1 企業版 <br/>-Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<p>**附注**： Microsoft Monitoring Agent 現在是 Azure 記錄分析代理程式。 若要深入瞭解，請參閱 [Log Analytics agent 一覽](/azure/azure-monitor/platform/log-analytics-agent)。        |
|-Windows Server 2019 和更新版本 <br/>-Windows Server 2019 core edition <br/>-Windows Server 版本1803和更新版本 |- [本機腳本](configure-endpoints-script.md) <br/>- [群組原則](configure-endpoints-gp.md) <br/>- [Configuration Manager](configure-endpoints-sccm.md) <br/>- [System Center Configuration Manager](configure-endpoints-sccm.md) <br/>- [非持久性裝置的 VDI 上架腳本](configure-endpoints-vdi.md) <p>**附注**：本機腳本適用于概念證明，但不適用於實際執行部署。 在實際執行部署中，我們建議使用群組原則、Microsoft 端點設定管理員或 Intune。    |
|-Windows Server 2016 <br/>-Windows Server 2012 R2 <br/>-Windows Server 2008 R2 SP1  |- [Microsoft Defender 安全中心](configure-server-endpoints.md)<br/>- [Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS<br/>-11.3.1 (大型 Sur)  <br/>-10.15 (Catalina) <br/>-10.14 (Mojave) <p>iOS<p>Linux：<br/>-RHEL 7.2 +<br/>-CentOS Linux 7.2 +<br/>-Ubuntu 16 LTS 或更高版本 LTS<br/>-SLES 12 +<br/>-Debian 9 +<br/>-Oracle Linux 7。2 |[將非 Windows 裝置上線](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>執行偵測測試

若要驗證架裝置是否正確連接至 Microsoft Defender for Endpoint，您可以執行偵測測試。

|作業系統  |指導方針  |
|---------|---------|
|-Windows 10 <br/>-Windows Server 2019 <br/>-Windows Server，版本1803 <br/>-Windows Server 2016 <br/>-Windows Server 2012 R2     |請參閱 [執行偵測測試](run-detection-test.md)。 <p>流覽 Microsoft Defender for Endpoint 示範案例網站 ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) 並嘗試一或多個案例。 例如，嘗試 **雲端提供的保護** 示範案例。         |
|macOS<br/>-11.3.1 (大型 Sur)  <br/>-10.15 (Catalina) <br/>-10.14 (Mojave)     |下載並使用 DIY 應用程式 [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) 。 <p>如需詳細資訊，請參閱 [macOS 上的 Microsoft Defender For Endpoint](microsoft-defender-endpoint-mac.md)。        |
|Linux：<br/>-RHEL 7.2 +<br/>-CentOS Linux 7.2 +<br/>-Ubuntu 16 LTS 或更高版本 LTS<br/>-SLES 12 +<br/>-Debian 9 +<br/>-Oracle Linux 7。2 |1. 執行下列命令，並尋找 **1** 的結果： <br/>`mdatp health --field real_time_protection_enabled`. <p>2. 開啟終端視窗，並執行下列命令： <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. 執行下列命令，列出任何偵測到的威脅： <br/>`mdatp threat list`. <p>如需詳細資訊，請參閱 [Linux 上的 Microsoft Defender For Endpoint](microsoft-defender-endpoint-linux.md)。 |

## <a name="uninstall-your-non-microsoft-solution"></a>卸載非 Microsoft 解決方案

現在，您已將組織的裝置架至 Microsoft Defender for Endpoint，下一步是卸載非 Microsoft Endpoint protection 解決方案。

若要取得此步驟的說明，請與您的解決方案供應商的技術支援小組聯繫。

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>確定 Microsoft Defender for Endpoint 處於主動模式

現在，您已卸載非 Microsoft endpoint protection 解決方案，下一步是確定已啟用 Microsoft Defender 防病毒和 Microsoft Defender for Endpoint，並以主動模式。

若要這麼做，請造訪 Microsoft Defender for Endpoint 示範案例網站 ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) 。 請在該頁面上嘗試一或多個示範案例，至少包括下列專案：
- 雲端提供的保護
- PUA (可能有害的應用程式) 
- 網路保護 (NP) 

> [!IMPORTANT]
> 如果您使用的是 Windows Server 2016，您可能需要手動啟動 Microsoft Defender 防病毒。 您可以使用裝置上的 PowerShell Cmdlet 來執行此動作 `mpcmdrun.exe -wdenable` 。

## <a name="next-steps"></a>後續步驟

**恭喜**！ 您已完成 [遷移至 Microsoft Defender For Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)！ 

- 請造訪 Microsoft Defender Security Center () 中的[安全性作業儀表板](security-operations-dashboard.md) [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。 
- [管理 Microsoft Defender For Endpoint，後期遷移](manage-atp-post-migration.md)。
