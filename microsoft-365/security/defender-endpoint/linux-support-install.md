---
title: 疑難排解適用于 Linux 的 Microsoft Defender ATP 安裝問題
ms.reviewer: ''
description: 疑難排解適用于 Linux 的 Microsoft Defender ATP 安裝問題
keywords: microsoft、defender、atp、linux、安裝
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
ms.openlocfilehash: 347528def6929dde200249cd9710f7ce33484c7f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688810"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a>疑難排解 Linux 上 Microsoft Defender for Endpoint 的安裝問題

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a>確認安裝是否成功

「安裝」中的錯誤可能會或不會由封裝管理員產生有意義的錯誤訊息。 若要確認安裝是否成功，請使用下列步驟取得並檢查安裝記錄檔：

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

先前命令的輸出和安裝的正確日期和時間會指出成功。

此外，請檢查 [用戶端](linux-install-manually.md#client-configuration) 設定，以確認產品的健康情況，並偵測 eicar.txt 文字檔。

## <a name="make-sure-you-have-the-correct-package"></a>請確定您有正確的套件

請注意，您要安裝的套件符合主機發佈和版本。

| 包                       | 分佈                             |
|-------------------------------|------------------------------------------|
| mdatp-rhel8.Linux.x86_64 rpm  | Oracle、RHEL 和 CentOS ∞              |
| mdatp-sles12.Linux.x86_64 rpm | SuSE Linux Enterprise Server 12v        |
| mdatp-sles15.Linux.x86_64 rpm | SuSE Linux Enterprise Server 15。        |
| mdatp.Linux.x86_64 rpm        | Oracle、RHEL 和 CentOS 7. x              |
| mdatp.Linux.x86_64。 deb        | Debian 和 Ubuntu 16.04、18.04 及20.04 |

若要進行 [手動部署](linux-install-manually.md)，請確定已選取正確的 distro 和版本。

## <a name="installation-failed"></a>安裝失敗

檢查 mdatp 服務是否正在執行：

```bash
systemctl status mdatp
```
```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a>Mdatp 服務未執行時的疑難排解步驟

1. 檢查是否存在 "mdatp" 使用者：

    ```bash
    id "mdatp"
    ```

    如果沒有輸出，請執行

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. 嘗試啟用並重啟服務，請使用：

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. 若執行先前命令時未找到 mdatp，請執行：

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    ```<systemd_path>```位於 ```/lib/systemd/system``` Ubuntu 和 Debian 發行的位置， ```/usr/lib/systemd/system``` 以及 Rhel、CentOS、Oracle 和 SLES 的位置。
   然後重新執行步驟2。

4. 如果上述步驟無法運作，請檢查是否已安裝 SELinux，並檢查強制模式。 如果是的話，請嘗試將其設為「許可」 (首選) 或已停用的模式。 您可以在檔案中將參數設 `SELINUX` 為「容許」或「停用」 `/etc/selinux/config` ，接著再重新開機。 如需詳細資訊，請參閱 selinux 的手冊頁面。
現在請嘗試使用步驟2重新開機 mdatp 服務。 請立即還原設定變更，但出於安全性原因，請試一試並重啟。

5. 如果 `/opt` 目錄是符號連結，請建立 bind 裝載 `/opt/microsoft` 。

6. 確定守護程式具有可執行檔許可權。

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    如果此守護程式沒有可執行檔許可權，請使用下列方式進行：

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    並重試執行步驟2。

7. 確定包含 wdavdaemon 的檔案系統未裝載為 "noexec"。

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a>如果 mdatp 服務正在執行，但 EICAR.TXT 文字檔偵測無法運作

1. 使用下列專案檢查檔案系統類型：

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    目前支援的內部存取使用中的檔案[系統如下所列。](microsoft-defender-endpoint-linux.md#system-requirements) 不會掃描這些檔案系統以外的任何檔案。

## <a name="command-line-tool-mdatp-isnt-working"></a>命令列工具 "mdatp" 無法運作

1. 如果執行命令列工具 `mdatp` 時發生錯誤 `command not found` ，請執行下列命令：

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    然後再試一次。

    如果上述步驟都沒有説明，請收集診斷記錄：

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    包含記錄檔的 zip 檔案路徑會顯示為輸出。 使用這些記錄與我們的客戶支援部門聯繫。
