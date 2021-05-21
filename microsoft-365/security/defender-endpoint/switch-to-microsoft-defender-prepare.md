---
title: 切換至 Microsoft Defender 的端點-準備
description: 這是階段1，準備，用於遷移至 Microsoft Defender for Endpoint。
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
ms.topic: article
ms.custom: migrationguides
ms.date: 05/20/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 92dfc279344b003ab651110375982b0f065dfb0d
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594166"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>切換至 Microsoft Defender 的端點-階段1：準備

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![階段 1：準備](images/phase-diagrams/prepare.png)<br/>階段 1：準備 | [![階段 2：設定](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[階段 2：設定](switch-to-microsoft-defender-setup.md) | [![第 3 階段：導入](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[第 3 階段：導入](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
|*您在這裡！*| | |

**歡迎使用 [切換到 Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)的準備階段**。 

此遷移階段包含下列步驟：

1. [在組織裝置中取得及部署更新](#get-and-deploy-updates-across-your-organizations-devices)
2. [取得 Defender For Endpoint](#get-microsoft-defender-for-endpoint)。
3. [授與 Microsoft Defender 資訊安全中心的存取權](#grant-access-to-the-microsoft-defender-security-center)。
4. [設定裝置 proxy 和網際網路連線設定](#configure-device-proxy-and-internet-connectivity-settings)。

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>在組織裝置中取得及部署更新

最佳作法是將組織的裝置和端點保持在最新狀態。 請確定現有的 endpoint protection 和防病毒方案是最新的，而且您組織的作業系統和應用程式也會有最新的更新。 現在執行此動作可協助您在遷移至更新端點和 Microsoft Defender 防毒軟體時，避免發生問題。

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

現在，您已更新組織的裝置，下一個步驟是取得 Defender for Endpoint、指派授權，並確定服務已布建。

1. 立即購買或試用 Endpoint for Endpoint。 [開始免費試用或要求報價](https://aka.ms/mdatp)。 

2. 確認已正確布建您的授權。 [檢查您的授權狀態](production-deployment.md#check-license-state)。

3. 以全域管理員或安全性管理員的身分，設定您專用的 Defender for Endpoint 的雲端實例。 請參閱 [適用于 Endpoint 的 Defender 設定：承租人設定](production-deployment.md#tenant-configuration)。

4. 如果您組織中)  (等端點使用 proxy 來存取網際網路，請參閱 [Defender For Endpoint setup： Network configuration](production-deployment.md#network-configuration)。
 
此時，您已準備好授與安全性管理員的存取權，以及將使用 Microsoft Defender 資訊安全中心 () 的安全性操作員 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。 

> [!NOTE]
> Microsoft Defender 資訊安全中心有時稱為端點入口網站的 Defender，而且可以在此存取 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>授與 Microsoft Defender 資訊安全中心的存取權

Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 是您用來存取及設定用於端點之 Defender 的功能。 若要深入瞭解，請參閱[Microsoft Defender 資訊安全中心的總覽](use.md)。

您可以使用基本許可權或以角色為基礎的存取控制 (RBAC) 授與 Microsoft Defender 資訊安全中心許可權。 我們建議使用 RBAC，讓您可以更細微地控制許可權。

1. 規劃安全性管理員及安全性操作員的角色和許可權。 請參閱以 [角色為基礎的存取控制](prepare-deployment.md#role-based-access-control)。

2. 設定和設定 RBAC。 建議使用[Intune](/mem/intune/fundamentals/what-is-intune)設定 RBAC，尤其是當您的組織使用 Windows 10、macOS、iOS 和 Android 裝置的組合時。 請參閱 [使用 Intune 設定 RBAC](/mem/intune/fundamentals/role-based-access-control)。

    如果您的組織需要 Intune 以外的方法，請選擇下列其中一個選項：

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [高級群組原則管理](/microsoft-desktop-optimization-pack/agpm)
    - [Windows系統管理中心](/windows-server/manage/windows-admin-center/overview)

3. 授與 Microsoft Defender 資訊安全中心的存取權。  (需要協助嗎？ 請參閱 [使用 RBAC) 管理入口網站存取](rbac.md) 。

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>設定裝置 proxy 和網際網路連線設定

若要啟用裝置和 Defender for Endpoint 之間的通訊，請設定 proxy 和網際網路設定。 下表包含可用於設定各種作業系統和功能之 proxy 和網際網路設定的資源連結：

| 功能  | 作業系統 | 資源 |
|:--|:--|:--|
|  (EDR[的端點偵測和回應](overview-endpoint-detection-response.md))  | [Windows 10](/windows/release-health/release-information) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows伺服器1803或更新版本](/windows-server/get-started/whats-new-in-windows-server-1803)  | [設定電腦 proxy 和網際網路連線設定](configure-proxy-internet.md) |
| EDR | [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[設定 proxy 和網際網路連線設定](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
| EDR  | macOS：<p>11.3.1 (大型 Sur) <p>10.15 (Catalina) <p>10.14 (Mojave)    | [MacOS 上的 Defender for Endpoint： Network connections](microsoft-defender-endpoint-mac.md#network-connections)  |
| [Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md) | [Windows 10](/windows/release-health/release-information) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows伺服器1803或更新版本](/windows-server/get-started/whats-new-in-windows-server-1803) <p>[Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) | [設定及驗證 Microsoft Defender 防毒軟體網路連線](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
| 防毒 | macOS：<p>11.3.1 (大型 Sur) <p>10.15 (Catalina) <p>10.14 (Mojave)  | [MacOS 上的 Defender for Endpoint： Network connections](microsoft-defender-endpoint-mac.md#network-connections) |
| 防毒 | Linux： <p>RHEL 7.2 +<p>CentOS Linux 7.2 +<p>Ubuntu 16 LTS 或更高版本 LTS<p>SLES 12 +<p>Debian 9 +<p>Oracle Linux 7。2 | [Linux 上的 Defender Endpoint：網路連接](microsoft-defender-endpoint-linux.md#network-connections) |

## <a name="next-step"></a>後續步驟

**恭喜**！ 您已完成 [切換至 Defender For Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)的 **準備** 階段！

- [繼續設定端點的 Defender](switch-to-microsoft-defender-setup.md)。
