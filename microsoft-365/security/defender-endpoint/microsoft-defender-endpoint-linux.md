---
title: Microsoft Defender ATP （適用于 Linux）
ms.reviewer: ''
description: 說明如何安裝及使用 Microsoft Defender ATP for Linux。
keywords: microsoft，defender，atp，linux，安裝，部署，卸載，puppet，ansible，linux，redhat，ubuntu，debian，sles，suse，centos
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
ms.openlocfilehash: 84d85b723d4dcbdfc07a074c40241242c57bc390
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185584"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a>適用于 Linux 的 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

本主題說明如何針對 Linux 安裝、設定、更新及使用 Microsoft Defender for Endpoint。

> [!CAUTION]
> 針對 Linux 執行其他協力廠商端點保護產品及 Microsoft Defender for Linux，都可能會造成效能問題和不可預期的系統錯誤。

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a>如何為 Linux 安裝 Microsoft Defender for Endpoint

### <a name="prerequisites"></a>必要條件

- 存取 Microsoft Defender 安全中心入口網站
- 使用 [systemd](https://systemd.io/) 系統管理員的 Linux 發行
- 在 Linux 和 BASH 腳本中的初級層級體驗
- 當手動部署時，裝置上的系統管理許可權 () 

### <a name="installation-instructions"></a>安裝指示

您可以使用數種方法和部署工具，為 Linux 安裝和設定 Microsoft Defender for Endpoint。

一般說來，您必須採取下列步驟：

- 確定您有 Microsoft Defender for Endpoint 訂閱，且您可以存取 [Microsoft defender For endpoint 入口網站](microsoft-defender-security-center.md)。
- 使用下列其中一個部署方法，為 Linux 部署 Microsoft Defender for Linux：
  - 命令列工具：
    - [手動部署](linux-install-manually.md)
  - 協力廠商管理工具：
    - [使用 Puppet 建構管理工具進行部署](linux-install-with-puppet.md)
    - [使用 Ansible 建構管理工具進行部署](linux-install-with-ansible.md)

如果您遇到任何安裝失敗，請參閱 [Microsoft Defender For Linux 中的疑難排解安裝失敗](linux-support-install.md)。

### <a name="system-requirements"></a>系統需求

- 支援的 Linux 伺服器發行及版本：

  - Red Hat Enterprise Linux 7.2 或更高版本
  - CentOS 7.2 或更高版本
  - Ubuntu 16.04 LTS 或更高版本 LTS
  - Debian 9 或更高版本
  - SUSE Linux Enterprise Server 12 或更高版本
  - Oracle Linux 7.2 或更高版本

- 最小內核版本 3.10.0-327
- `fanotify`必須啟用內核選項
  > [!CAUTION]
  > 不支援以其他方式的安全性解決方案為基礎，針對 Linux 的端點執行 Defender `fanotify` 。 這可能會造成無法預期的結果，包括懸掛作業系統。

- 磁碟空間：1GB
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
  >[!NOTE]
  > 新增至審核記錄的規則所捕獲的系統事件 `audit.logs` 會將其新增至審核記錄，而且可能會影響主機審核和上游集合。 Microsoft Defender for Endopoint for Linux 新增的事件將會以 `mdatp` 金鑰標示。

### <a name="network-connections"></a>網路連線

下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。 您應確定沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取權。 如果有，您可能需要專門為其建立一個 *allow* 規則。

|**網域清單的試算表**|**描述**|
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
> 出於安全性原因，也不支援 SSL 檢查和截取 proxy。 設定 SSL 檢查和 proxy 伺服器的例外狀況，以直接透過來自 Linux 的 Defender 的資料傳遞至相關的 URLs，而不需截獲。 將您的截取憑證新增至全域存放區將不允許截取。

如需疑難排解步驟，請參閱 [疑難排解 Microsoft Defender for a For Linux 之 cloud connectivity connectivity 的問題](linux-support-connectivity.md)。

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a>如何為 Linux 更新 Microsoft Defender for Endpoint

Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。 若要更新 Microsoft Defender for Linux，請參閱為 [Linux 部署 Microsoft defender For endpoint 的更新](linux-updates.md)。

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a>如何為 Linux 設定 Microsoft Defender for Endpoint

有關如何在企業環境中設定產品的指引，可在 [設定 Microsoft Defender For Linux 的首選項中取得](linux-preferences.md)。

## <a name="resources"></a>資源

- 如需有關記錄、卸載或其他主題的詳細資訊，請參閱 [Resources](linux-resources.md)。
