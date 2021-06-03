---
title: Linux 上適用於端點的 Microsoft Defender
ms.reviewer: ''
description: 說明如何在 Linux 上安裝及使用 Microsoft Defender for Endpoint。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，安裝，部署，卸載，puppet，ansible，linux，redhat，ubuntu，debian，sles，suse，centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2242d195f4a4ea4b8f0c345d82fa0ad1f947bfa2
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730759"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Linux 上適用於端點的 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

本主題說明如何在 Linux 上安裝、設定、更新及使用 Microsoft Defender for Endpoint。

> [!CAUTION]
> 在 Linux 上執行其他協力廠商端點保護產品及 Microsoft Defender for Endpoint 時，可能會造成效能問題和不可預測的副作用。 若非 Microsoft endpoint protection 是您環境中的絕對需求，則在將防病毒功能設定為以[被動式模式](linux-preferences.md#enable--disable-passive-mode)執行之前，您仍然可以在 Linux EDR 功能上安全地利用 Defender for endpoint。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>如何在 Linux 上安裝 Microsoft Defender for Endpoint

### <a name="prerequisites"></a>必要條件

- 存取 Microsoft Defender 資訊安全中心入口網站
- 使用 [systemd](https://systemd.io/) 系統管理員的 Linux 發行
- 在 Linux 和 BASH 腳本中的初級層級體驗
- 當手動部署時，裝置上的系統管理許可權 () 

> [!NOTE]
>  Linux 代理程式上的 Microsoft Defender for Endpoint 獨立于 [OMS 代理程式](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)。 Microsoft Defender for Endpoint 依賴其自身的獨立遙測管線。
> 
> Linux 上的 Microsoft Defender for Endpoint 尚未整合到 Azure Security Center 中。



### <a name="installation-instructions"></a>安裝指示

您可以使用數種方法和部署工具，在 Linux 上安裝及設定 Microsoft Defender for Endpoint。

一般說來，您必須採取下列步驟：

- 確定您有 Microsoft Defender for Endpoint 訂閱，且您可以存取 [Microsoft defender For endpoint 入口網站](microsoft-defender-security-center.md)。
- 使用下列其中一個部署方法，在 Linux 上部署 Microsoft Defender for Endpoint：
  - 命令列工具：
    - [手動部署](linux-install-manually.md)
  - 協力廠商管理工具：
    - [使用 Puppet 建構管理工具進行部署](linux-install-with-puppet.md)
    - [使用 Ansible 建構管理工具進行部署](linux-install-with-ansible.md)

如果您遇到任何安裝失敗問題，請參閱在 [Linux 上的 Microsoft Defender For Endpoint 中的安裝失敗疑難排解](linux-support-install.md)。



### <a name="system-requirements"></a>系統需求

- 支援的 Linux 伺服器發行和 x64 (AMD64/EM64T) 版本：

  - 紅色帽子 Enterprise Linux 7.2 或更高版本
  - CentOS 7.2 或更高版本
  - Ubuntu 16.04 LTS 或更高版本 LTS
  - Debian 9 或更高版本
  - SUSE Linux Enterprise Server 12 或更高版本
  - Oracle Linux 7.2 或更高版本

    > [!NOTE]
    > 未明確列出的發行及版本不受支援 (，即使它們派生自正式支援的發行) 也是一樣。


- 最小內核版本 3.10.0-327

- `fanotify`必須啟用內核選項

  > [!CAUTION]
  > 不支援以其他方式的安全性解決方案，並排在 Linux 上執行 Defender for Endpoint `fanotify` 。 這可能會造成無法預期的結果，包括懸掛作業系統。

- 磁碟空間： 1 GB

- /opt/microsoft/mdatp/sbin/wdavdaemon 需要可執行檔許可權。 如需詳細資訊，請參閱 [疑難排解 Microsoft Defender for The Linux 上的 Microsoft Defender For Endpoint 的安裝問題](/microsoft-365/security/defender-endpoint/linux-support-install)。

- 記憶體： 1 GB

    > [!NOTE]
    > 請確認您在/var. 中有可用的磁碟空間。

- 目前的解決方案為下列檔案系統類型提供即時保護：

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

在您啟用服務之後，您可能需要設定網路或防火牆，以允許它和您的端點之間的輸出連線。

- 必須啟用審核架構 (`auditd`) 。
  > [!NOTE]
  > 新增至的規則所捕獲的系統事件 `/etc/audit/rules.d/` 會新增至 `audit.log` (s) ，而且可能會影響主機審核和上游集合。 在 Linux 上由 Microsoft Defender for Endpoint 新增的事件將會以 `mdatp` 金鑰標示。

### <a name="network-connections"></a>網路連線

下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。 您應確定沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取權。 如果有，您可能需要專門為其建立一個 *allow* 規則。

| 網域清單的試算表 | 描述 |
|:-----|:-----|
|![Microsoft Defender for Endpoint URLs 試算表的縮圖影像](images/mdatp-urls.png)<br/>  | 服務位置、地理位置和作業系統的特定 DNS 記錄試算表。 <br><br>[在這裡下載試算表。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> 如需詳細的 URL 清單，請參閱 [設定 proxy 和網際網路連線設定](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。

「！的 Defender」可以使用下列探索方法探索 proxy 伺服器：
- 透明Proxy
- 手動靜態 proxy 設定

如果 proxy 或防火牆封鎖匿名流量，請確定先前所列的 URLs 允許匿名流量。 針對透明 proxy，不需要其他設定供 Defender 用於端點。 針對靜態 proxy，依照 [手動靜態 proxy](linux-static-proxy-configuration.md)設定中的步驟進行。

> [!WARNING]
> 不支援 PAC、WPAD 及已驗證的 proxy。 確定只使用靜態 proxy 或透明 proxy。
>
> 出於安全性原因，也不支援 SSL 檢查和截取 proxy。 設定 SSL 檢查和 proxy 伺服器的例外狀況，以直接將來自 Linux 之 Defender 的資料傳遞至相關的 URLs，而不需截獲。 將您的截取憑證新增至全域存放區將不允許截取。

如需疑難排解步驟，請參閱 [疑難排解 Microsoft Defender for a For Endpoint On Linux 上的 cloud connectivity connectivity 問題](linux-support-connectivity.md)。

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>如何在 Linux 上更新 Microsoft Defender for Endpoint

Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。 若要在 Linux 上更新 Microsoft Defender for Endpoint，請參閱 [在 linux 上為 Microsoft defender For Endpoint 部署更新](linux-updates.md)。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>如何在 Linux 上設定 Microsoft Defender for Endpoint

有關如何在企業環境中設定產品的指引，可在 [Linux 上的 Microsoft Defender For Endpoint 的 [設定偏好設定](linux-preferences.md)] 中取得。

## <a name="resources"></a>資源

- 如需有關記錄、卸載或其他主題的詳細資訊，請參閱 [Resources](linux-resources.md)。
