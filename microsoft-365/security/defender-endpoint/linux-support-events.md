---
title: 針對 Linux 上的 Microsoft Defender for Endpoint 的缺失事件或警示問題進行疑難排解
description: 疑難排解 Linux 上的 Microsoft Defender for Endpoint 中遺失的事件或警示問題。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，事件
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
ms.openlocfilehash: 7de216c1397a7cc4806af8221257eeedd2290830
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933310"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="88b9d-104">針對 Linux 上的 Microsoft Defender for Endpoint 的缺失事件或警示問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="88b9d-104">Troubleshoot missing events or alerts issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="88b9d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="88b9d-105">**Applies to:**</span></span>

- [<span data-ttu-id="88b9d-106">Linux 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="88b9d-106">Microsoft Defender for Endpoint on Linux</span></span>](microsoft-defender-endpoint-linux.md)

<span data-ttu-id="88b9d-107">本文提供一些一般步驟，以減輕 [安全性中心](https://securitycenter.windows.com/) 入口網站中遺失的事件或警示。</span><span class="sxs-lookup"><span data-stu-id="88b9d-107">This article provides some general steps to mitigate missing events or alerts in the [security center](https://securitycenter.windows.com/) portal.</span></span>

<span data-ttu-id="88b9d-108">在裝置上正確安裝 **Microsoft Defender For Endpoint** 後，就會在入口網站中產生 _裝置頁面_ 。</span><span class="sxs-lookup"><span data-stu-id="88b9d-108">Once **Microsoft Defender for Endpoint** has been installed properly on a device, a _device page_ will be generated in the portal.</span></span> <span data-ttu-id="88b9d-109">您可以在 [裝置] 頁面上的 [時程表] 索引標籤或 [高級搜尋] 頁面中，複查所有錄製的事件。</span><span class="sxs-lookup"><span data-stu-id="88b9d-109">You can review all recorded events in the timeline tab in the device page, or in advanced hunting page.</span></span> <span data-ttu-id="88b9d-110">此區段用於診斷部分或所有預期事件的情況缺失。</span><span class="sxs-lookup"><span data-stu-id="88b9d-110">This section troubleshoots the case of some or all expected events are missing.</span></span>
<span data-ttu-id="88b9d-111">例如，如果所有的 _CreatedFile_ 事件都缺失。</span><span class="sxs-lookup"><span data-stu-id="88b9d-111">For instance, if all _CreatedFile_ events are missing.</span></span>

## <a name="missing-network-and-login-events"></a><span data-ttu-id="88b9d-112">遺失網路和登入事件</span><span class="sxs-lookup"><span data-stu-id="88b9d-112">Missing network and login events</span></span>

<span data-ttu-id="88b9d-113">Microsoft Defender for a Endpoint 利用 `audit` framework （來自 linux）以追蹤網路和登入活動。</span><span class="sxs-lookup"><span data-stu-id="88b9d-113">Microsoft Defender for Endpoint utilized `audit` framework from linux to track network and login activity.</span></span>

1. <span data-ttu-id="88b9d-114">請確定審核架構是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="88b9d-114">Make sure audit framework is working.</span></span>

    ```bash
    service auditd status
    ```

    <span data-ttu-id="88b9d-115">期望的輸出：</span><span class="sxs-lookup"><span data-stu-id="88b9d-115">expected output:</span></span>

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

2. <span data-ttu-id="88b9d-116">如果 `auditd` 標示為已停止，請啟動它。</span><span class="sxs-lookup"><span data-stu-id="88b9d-116">If `auditd` is marked as stopped, start it.</span></span>

    ```bash
    service auditd start
    ```

<span data-ttu-id="88b9d-117">**在 SLES 系統上** ，可能預設會停用的 SYSCALL 審核，而且可能會 `auditd` 考慮遺失的事件。</span><span class="sxs-lookup"><span data-stu-id="88b9d-117">**On SLES** systems, SYSCALL auditing in `auditd` might be disabled by default and can be accounted for missing events.</span></span>

1. <span data-ttu-id="88b9d-118">若要驗證 SYSCALL 審核未停用，請列出目前的審計規則：</span><span class="sxs-lookup"><span data-stu-id="88b9d-118">To validate that SYSCALL auditing is not disabled, list the current audit rules:</span></span>

    ```bash
    sudo auditctl -l
    ```

    <span data-ttu-id="88b9d-119">如果出現下列行，請將其移除或進行編輯，讓 Microsoft Defender for Endpoint 能夠追蹤特定 SYSCALLs。</span><span class="sxs-lookup"><span data-stu-id="88b9d-119">if the following line is present, remove it or edit it to enable Microsoft Defender for Endpoint to track specific SYSCALLs.</span></span>

    ```output
    -a task, never
    ```

    <span data-ttu-id="88b9d-120">審核規則位於 `/etc/audit/rules.d/audit.rules` 。</span><span class="sxs-lookup"><span data-stu-id="88b9d-120">audit rules are located at `/etc/audit/rules.d/audit.rules`.</span></span>

## <a name="missing-file-events"></a><span data-ttu-id="88b9d-121">遺失檔案事件</span><span class="sxs-lookup"><span data-stu-id="88b9d-121">Missing file events</span></span>

<span data-ttu-id="88b9d-122">檔案事件是以 `fanotify` 架構收集。</span><span class="sxs-lookup"><span data-stu-id="88b9d-122">File events are collected with `fanotify` framework.</span></span> <span data-ttu-id="88b9d-123">若部分或所有檔案事件遺失，請確定已 `fanotify` 在裝置上啟用，且 [支援](microsoft-defender-endpoint-linux.md#system-requirements)檔案系統。</span><span class="sxs-lookup"><span data-stu-id="88b9d-123">In case some or all file events are missing, make sure `fanotify` is enabled on the device and that the file system is [supported](microsoft-defender-endpoint-linux.md#system-requirements).</span></span>

<span data-ttu-id="88b9d-124">列出電腦上的檔案系統：</span><span class="sxs-lookup"><span data-stu-id="88b9d-124">List the filesystems on the machine with:</span></span>

```bash
df -Th
```
