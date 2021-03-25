---
title: 切換至 Microsoft Defender 的端點-準備
description: 這是階段1，準備，用於遷移至 Microsoft Defender for Endpoint。
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
- m365solution-migratetomdatp
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: d5339ce795bff1451d6f4caaf37de39f996890be
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185524"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>切換至 Microsoft Defender 的端點-階段1：準備

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![階段1：準備](images/phase-diagrams/prepare.png)<br/>階段1：準備 | [![階段2：設定](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[階段2：設定](switch-to-microsoft-defender-setup.md) | [![階段3：板載](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[階段3：板載](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
|*您在這裡！*| | |

**歡迎使用 [切換至 Microsoft Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)的準備階段**。 

此遷移階段包含下列步驟：
1. [在組織裝置中取得及部署更新](#get-and-deploy-updates-across-your-organizations-devices)
2. [取得 Microsoft Defender For Endpoint](#get-microsoft-defender-for-endpoint)。
3. [授與 Microsoft Defender Security Center 的存取權](#grant-access-to-the-microsoft-defender-security-center)。
4. [設定裝置 proxy 和網際網路連線設定](#configure-device-proxy-and-internet-connectivity-settings)。

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>在組織裝置中取得及部署更新

最佳作法是將組織的裝置和端點保持在最新狀態。 請確定現有的 endpoint protection 和防病毒方案是最新的，而且您組織的作業系統和應用程式也會有最新的更新。 現在執行此動作可在您遷移至 Microsoft Defender for Endpoint 和 Microsoft Defender 防病毒時，協助避免發生問題。

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>確定現有的解決方案是最新的

保留現有的 endpoint protection 方案，並確定您組織的裝置具有最新的安全性更新。 

需要協助？ 請參閱您的解決方案供應商的檔。

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>確定貴組織的裝置是最新版本

需要協助更新您的組織裝置嗎？ 請參閱下列資源：

|作業系統 | 資源 |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [如何更新 Mac 上的軟體](https://support.apple.com/HT201541)|
|iOS |[更新 iPhone、iPad 或 iPod 觸控](https://support.apple.com/HT204204)|
|Android |[檢查 & 更新您的 Android 版本](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101：更新您的系統](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>取得 Microsoft Defender for Endpoint

現在，您已更新組織的裝置，下一個步驟是取得 Microsoft Defender for Endpoint、指派授權，並確定服務已布建。

1. 立即購買或試用 Microsoft Defender for Endpoint。 [開始免費試用或要求報價](https://aka.ms/mdatp)。 
2. 確認已正確布建您的授權。 [檢查您的授權狀態](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state)。
3. 以全域管理員或安全性管理員的身分，設定 Microsoft Defender for Endpoint 的專用雲端實例。 請參閱 [Microsoft Defender For Endpoint setup：承租人設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration)。
4. 如果 (例如組織中) 使用 proxy 來存取網際網路的端點，請參閱 [Microsoft Defender For Endpoint setup： Network configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration)。
 
此時，您已準備好授與安全性管理員的存取權，以及將使用 Microsoft Defender Security Center () 的安全性操作員 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。 

> [!NOTE]
> Microsoft Defender Security Center 有時稱為「Microsoft Defender 端點入口網站」，且可于存取 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>授與 Microsoft Defender Security Center 的存取權

Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) 是您用來存取及設定 Microsoft defender For Endpoint 的功能。 若要深入瞭解，請參閱 [Microsoft Defender Security Center 的概述](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)。

您可以使用基本許可權或以角色為基礎的存取控制 (RBAC) ，授與 Microsoft Defender Security Center 的許可權。 我們建議使用 RBAC，讓您可以更細微地控制許可權。

1. 規劃安全性管理員及安全性操作員的角色和許可權。 請參閱以 [角色為基礎的存取控制](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control)。
2. 設定和設定 RBAC。 建議使用 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 設定 RBAC，尤其是當您的組織使用 Windows 10、macOS、IOS 和 Android 裝置的組合時。 請參閱 [使用 Intune 設定 RBAC](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)。
    如果您的組織需要 Intune 以外的方法，請選擇下列其中一個選項：
    - [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [高級群組原則管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows 系統管理中心](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)
3. 授與 Microsoft Defender Security Center 的存取權。  (需要協助嗎？ 請參閱 [使用 RBAC) 管理入口網站存取](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac) 。

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>設定裝置 proxy 和網際網路連線設定

若要啟用裝置與 Microsoft Defender for Endpoint 之間的通訊，請設定 proxy 和網際網路設定。 下表包含可用於設定各種作業系統和功能之 proxy 和網際網路設定的資源連結：

|功能  | 作業系統 | 資源 |
|--|--|--|
|[端點偵測和回應](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR)  |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 或更新版本](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[設定電腦 proxy 和網際網路連線設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[設定 proxy 和網際網路連線設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS： <br/>-10.15 (Catalina) <br/>-10.14 (Mojave)  <br/>-10.13 (高塞拉里昂)   |[Mac 版端點的 Microsoft Defender：網路連接](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 或更新版本](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[設定及驗證 Microsoft Defender 防毒軟體網路連線](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|防毒 |macOS： <br/>-10.15 (Catalina) <br/>-10.14 (Mojave)  <br/>-10.13 (高塞拉里昂)  |[Mac 版端點的 Microsoft Defender：網路連接](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|防毒 |Linux： <br/>-RHEL 7.2 +<br/>-CentOS Linux 7.2 +<br/>-Ubuntu 16 LTS 或更高版本 LTS<br/>-SLES 12 +<br/>-Debian 9 +<br/>-Oracle Linux 7。2 |[適用于 Linux 的 Microsoft Defender Endpoint：網路連線](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections) |

## <a name="next-step"></a>下一步

**恭喜**！ 您已完成 [切換至 Microsoft Defender For Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)的 **準備** 階段！

- [繼續設定 Microsoft Defender For Endpoint](switch-to-microsoft-defender-setup.md)。
