---
title: 針對 Linux 上的 Microsoft Defender for Endpoint 的缺失事件或警示問題進行疑難排解
description: 疑難排解 Linux 上的 Microsoft Defender for Endpoint 中遺失的事件或警示問題。
keywords: microsoft、defender、atp、linux、事件
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 40d394a4fc7349789dea9bd96ccdaf71067ab39e
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903995"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>針對 Linux 上的 Microsoft Defender for Endpoint 的缺失事件或警示問題進行疑難排解

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [Linux 上適用於端點的 Microsoft Defender](microsoft-defender-endpoint-linux.md)

本文提供一些一般步驟，以減輕 [安全性中心](https://securitycenter.windows.com/) 入口網站中遺失的事件或警示。

在裝置上正確安裝 **Microsoft Defender For Endpoint** 後，就會在入口網站中產生 _裝置頁面_ 。 您可以在 [裝置] 頁面上的 [時程表] 索引標籤或 [高級搜尋] 頁面中，複查所有錄製的事件。 此區段用於診斷部分或所有預期事件的情況缺失。
例如，如果所有的 _CreatedFile_ 事件都缺失。

## <a name="missing-network-and-login-events"></a>遺失網路和登入事件

Microsoft Defender for a Endpoint 利用 `audit` framework （來自 linux）以追蹤網路和登入活動。

1. 請確定審核架構是否正常運作。

    ```bash
    service auditd status
    ```

    期望的輸出：

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. 如果 `auditd` 標示為已停止，請啟動它。

    ```bash
    service auditd start
    ```

**在 SLES 系統上** ，可能預設會停用的 SYSCALL 審核，而且可能會 `auditd` 考慮遺失的事件。

1. 若要驗證 SYSCALL 審核未停用，請列出目前的審計規則：

    ```bash
    sudo auditctl -l
    ```

    如果出現下列行，請將其移除或進行編輯，讓 Microsoft Defender for Endpoint 能夠追蹤特定 SYSCALLs。

    ```output
    -a task, never
    ```

    審核規則位於 `/etc/audit/rules.d/audit.rules` 。

## <a name="missing-file-events"></a>遺失檔案事件

檔案事件是以 `fanotify` 架構收集。 若部分或所有檔案事件遺失，請確定已 `fanotify` 在裝置上啟用，且 [支援](microsoft-defender-endpoint-linux.md#system-requirements)檔案系統。

列出電腦上的檔案系統：

```bash
df -Th
```
