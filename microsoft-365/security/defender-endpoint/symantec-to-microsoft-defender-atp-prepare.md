---
title: Symantec to Microsoft Defender for Endpoint-階段1，準備
description: 這是第1階段，準備從 Symantec 遷移至 Microsoft Defender for Endpoint。
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 8c8f91448415bc1e9490706ee23bd8cae7f51a63
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698241"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>從 Symantec 遷移-階段1：準備遷移

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![階段 1：準備](images/phase-diagrams/prepare.png)<br/>階段 1：準備 |[![階段 2：設定](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[階段 2：設定](symantec-to-microsoft-defender-atp-setup.md) |[![第 3 階段：導入](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[第 3 階段：導入](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*您在這裡！*| | |


**歡迎使用 [從 Symantec 遷移至 Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)的準備階段**。 

此遷移階段包含下列步驟：
1. [取得 Microsoft Defender For Endpoint](#get-microsoft-defender-for-endpoint)。
2. [授與 Microsoft Defender Security Center 的存取權](#grant-access-to-the-microsoft-defender-security-center)。
3. [設定裝置 proxy 和網際網路連線設定](#configure-device-proxy-and-internet-connectivity-settings)。

## <a name="get-microsoft-defender-for-endpoint"></a>取得 Microsoft Defender for Endpoint

若要開始使用，您必須擁有 Microsoft Defender for Endpoint，並已指派及布建授權。

1. 立即購買或試用 Microsoft Defender for Endpoint。 [請造訪 Microsoft Defender For Endpoint，以開始免費試用版或要求報價](https://aka.ms/mdatp)。 
2. 確認已正確布建您的授權。 [檢查您的授權狀態](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state)。
3. 以全域管理員或安全性管理員的身分，設定 Microsoft Defender for Endpoint 的專用雲端實例。 請參閱 [Microsoft Defender For Endpoint setup：承租人設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration)。
4. 如果 (例如組織中) 使用 proxy 來存取網際網路的端點，請參閱 [Microsoft Defender For Endpoint setup： Network configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration)。
 
此時，您已準備好授與安全性管理員的存取權，以及將使用 Microsoft Defender Security Center () 的安全性操作員 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。 

> [!NOTE]
> Microsoft Defender Security Center 有時稱為「Microsoft Defender 端點入口網站」。 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>授與 Microsoft Defender Security Center 的存取權

Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) 是您用來存取及設定 Microsoft defender For Endpoint 的功能。 若要深入瞭解，請參閱 [Microsoft Defender Security Center 的概述](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)。

您可以使用基本許可權或以角色為基礎的存取控制 (RBAC) ，授與 Microsoft Defender Security Center 的許可權。 我們建議使用 RBAC，讓您可以更細微地控制許可權。

1. 規劃安全性管理員及安全性操作員的角色和許可權。 請參閱以 [角色為基礎的存取控制](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control)。
2. 設定和設定 RBAC。 建議使用 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 設定 RBAC，尤其是當您的組織使用 Windows 10、macOS、IOS 和 Android 裝置的組合時。 請參閱 [使用 Intune 設定 RBAC](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)。<br/>
   如果您的組織需要 Intune 以外的方法，請選擇下列其中一個選項：
    - [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [高級群組原則管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows 系統管理中心](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)
3. 授與 Microsoft Defender Security Center 的存取權。  (需要協助嗎？ 請參閱 [使用 RBAC) 管理入口網站存取](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac) 。

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>設定裝置 proxy 和網際網路連線設定

若要啟用裝置與 Microsoft Defender for Endpoint 之間的通訊，請設定 proxy 和網際網路設定。 下表包含可用於設定各種作業系統和功能之 proxy 和網際網路設定的資源連結：

|功能  | 作業系統 | 資源 |
|:----|:----|:---|
|[端點偵測和回應](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR)  |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 或更新版本](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[設定電腦 proxy 和網際網路連線設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[設定 proxy 和網際網路連線設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS： <br/>-10.15 (Catalina) <br/>-10.14 (Mojave)  <br/>-10.13 (高塞拉里昂)   |[MacOS 上的 Microsoft Defender for Endpoint： Network connections](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 或更新版本](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[設定及驗證 Microsoft Defender 防毒軟體網路連線](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|防毒 |macOS： <br/>-10.15 (Catalina) <br/>-10.14 (Mojave)  <br/>-10.13 (高塞拉里昂)  |[Mac 版上的 Microsoft Defender for Endpoint： Network connections](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|防毒 |Linux： <br/>-RHEL 7.2 +<br/>-CentOS Linux 7.2 +<br/>-Ubuntu 16 LTS 或更高版本 LTS<br/>-SLES 12 +<br/>-Debian 9 +<br/>-Oracle Linux 7。2 |[Linux 上的 Microsoft Defender for Endpoint： Network connections](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections)  |

## <a name="next-step"></a>下一步

**恭喜**！ 您已完成 [從 Symantec 遷移至 Microsoft Defender For Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)的 **準備** 階段！
- [繼續設定 Microsoft Defender For Endpoint](symantec-to-microsoft-defender-atp-setup.md)。
