---
title: 疑難排解 Linux 上 Microsoft Defender for Endpoint 的效能問題
description: 疑難排解 Linux 上的 Microsoft Defender for Endpoint 中的效能問題。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，效能
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
ms.openlocfilehash: 998d8c500613ffa9fc6d790535e555ff9503f590
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281014"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="df8fa-104">疑難排解 Linux 上 Microsoft Defender for Endpoint 的效能問題</span><span class="sxs-lookup"><span data-stu-id="df8fa-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="df8fa-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="df8fa-105">**Applies to:**</span></span>
- [<span data-ttu-id="df8fa-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="df8fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="df8fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df8fa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
> <span data-ttu-id="df8fa-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="df8fa-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="df8fa-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="df8fa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="df8fa-110">本文提供一些一般步驟，可用來縮小與在 Linux 上的 Defender for Endpoint 相關的效能問題。</span><span class="sxs-lookup"><span data-stu-id="df8fa-110">This article provides some general steps that can be used to narrow down performance issues related to Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="df8fa-111">[！注意] 即時保護 (RTP) 是一種適用于 Linux 上的端點的功能，可以持續監視和保護您的裝置免受威脅。</span><span class="sxs-lookup"><span data-stu-id="df8fa-111">Real-time protection (RTP) is a feature of Defender for Endpoint on Linux that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="df8fa-112">它包含檔案和程式監視及其他試探法。</span><span class="sxs-lookup"><span data-stu-id="df8fa-112">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="df8fa-113">根據您執行的應用程式和您的裝置特性，在 Linux 上執行 Defender for Endpoint 時，可能會體驗到最優效能。</span><span class="sxs-lookup"><span data-stu-id="df8fa-113">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Defender for Endpoint on Linux.</span></span> <span data-ttu-id="df8fa-114">特別是，在短時間記憶體取許多資源的應用程式或系統進程，可能會在 Linux 上的 Endpoint for Endpoint 中導致效能問題。</span><span class="sxs-lookup"><span data-stu-id="df8fa-114">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="df8fa-115">開始之前， **請確定目前沒有在裝置上執行其他安全性產品**。</span><span class="sxs-lookup"><span data-stu-id="df8fa-115">Before starting, **please make sure that other security products are not currently running on the device**.</span></span> <span data-ttu-id="df8fa-116">多個安全性產品可能會衝突，並影響主機效能。</span><span class="sxs-lookup"><span data-stu-id="df8fa-116">Multiple security products may conflict and impact the host performance.</span></span>

<span data-ttu-id="df8fa-117">下列步驟可用於疑難排解及緩解下列問題：</span><span class="sxs-lookup"><span data-stu-id="df8fa-117">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="df8fa-118">使用下列其中一種方法來停用即時保護，並觀察效能是否提高。</span><span class="sxs-lookup"><span data-stu-id="df8fa-118">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="df8fa-119">這種方法有助於縮小效能的 Defender 是否對效能問題產生影響。</span><span class="sxs-lookup"><span data-stu-id="df8fa-119">This approach helps narrow down whether Defender for Endpoint on Linux is contributing to the performance issues.</span></span>

    <span data-ttu-id="df8fa-120">如果您的裝置不是由您的組織管理，可以從命令列停用即時保護：</span><span class="sxs-lookup"><span data-stu-id="df8fa-120">If your device is not managed by your organization, real-time protection can be disabled from the command line:</span></span>

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="df8fa-121">如果您的裝置是由您的組織管理，您的系統管理員可以使用在 [Linux 上的 Defender For Endpoint 的 Set 偏好設定](linux-preferences.md)中的指示來停用即時保護。</span><span class="sxs-lookup"><span data-stu-id="df8fa-121">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span></span>

    <span data-ttu-id="df8fa-122">如果在即時保護關閉時出現效能問題，則問題的來源可能是端點偵測和回應元件。</span><span class="sxs-lookup"><span data-stu-id="df8fa-122">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="df8fa-123">在此情況下，請與客戶支援部門聯繫，以取得進一步的指示和緩解。</span><span class="sxs-lookup"><span data-stu-id="df8fa-123">In this case please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="df8fa-124">若要尋找觸發大多數掃描的應用程式，您可以使用在 Linux 上的 Defender for Endpoint 所收集的即時統計資料。</span><span class="sxs-lookup"><span data-stu-id="df8fa-124">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint on Linux.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df8fa-125">100.90.70 或更新版本中提供此功能。</span><span class="sxs-lookup"><span data-stu-id="df8fa-125">This feature is available in version 100.90.70 or newer.</span></span>

    <span data-ttu-id="df8fa-126">預設會在和頻道上啟用此 `Dogfood` 功能 `InsiderFast` 。</span><span class="sxs-lookup"><span data-stu-id="df8fa-126">This feature is enabled by default on the `Dogfood` and `InsiderFast` channels.</span></span> <span data-ttu-id="df8fa-127">如果您是使用不同的更新通道，可以從命令列啟用此功能：</span><span class="sxs-lookup"><span data-stu-id="df8fa-127">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    <span data-ttu-id="df8fa-128">這項功能需要啟用即時保護。</span><span class="sxs-lookup"><span data-stu-id="df8fa-128">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="df8fa-129">若要檢查即時保護的狀態，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="df8fa-129">To check the status of real-time protection, run the following command:</span></span>

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    <span data-ttu-id="df8fa-130">確認 `real_time_protection_enabled` 專案是 `true` 。</span><span class="sxs-lookup"><span data-stu-id="df8fa-130">Verify that the `real_time_protection_enabled` entry is `true`.</span></span> <span data-ttu-id="df8fa-131">否則，請執行下列命令來啟用它：</span><span class="sxs-lookup"><span data-stu-id="df8fa-131">Otherwise, run the following command to enable it:</span></span>

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="df8fa-132">若要收集目前的統計資料，請執行：</span><span class="sxs-lookup"><span data-stu-id="df8fa-132">To collect current statistics, run:</span></span>

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > <span data-ttu-id="df8fa-133">使用 ```--output json``` (請注意雙破折號) 確保輸出格式準備好進行分析。</span><span class="sxs-lookup"><span data-stu-id="df8fa-133">Using ```--output json``` (note the double dash) ensures that the output format is ready for parsing.</span></span>

    <span data-ttu-id="df8fa-134">這個命令的輸出會顯示所有程式及其相關聯的掃描活動。</span><span class="sxs-lookup"><span data-stu-id="df8fa-134">The output of this command will show all processes and their associated scan activity.</span></span>

3. <span data-ttu-id="df8fa-135">在您的 Linux 系統上，使用命令下載範例 Python 分析程式 **high_cpu_parser py** ：</span><span class="sxs-lookup"><span data-stu-id="df8fa-135">On your Linux system, download the sample Python parser **high_cpu_parser.py** using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    <span data-ttu-id="df8fa-136">此命令的輸出應類似下列所示：</span><span class="sxs-lookup"><span data-stu-id="df8fa-136">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. <span data-ttu-id="df8fa-137">接下來，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="df8fa-137">Next, type the following commands:</span></span>

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      <span data-ttu-id="df8fa-138">以上的輸出是效能問題的最熱門貢獻因素清單。</span><span class="sxs-lookup"><span data-stu-id="df8fa-138">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="df8fa-139">第一欄是進程識別碼 (PID) ，第二欄是 te 進程名稱，最後一欄是依影響排序的掃描檔數目。</span><span class="sxs-lookup"><span data-stu-id="df8fa-139">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>
    <span data-ttu-id="df8fa-140">例如，命令的輸出會如下所示：</span><span class="sxs-lookup"><span data-stu-id="df8fa-140">For example, the output of the command will be something like the below:</span></span> 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool     1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd    407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    <span data-ttu-id="df8fa-141">若要提升 Linux 上的 Defender for Endpoint 的效能，請找出列在列下方的最大值 `Total files scanned` ，並為其新增排除。</span><span class="sxs-lookup"><span data-stu-id="df8fa-141">To improve the performance of Defender for Endpoint on Linux, locate the one with the highest number under the `Total files scanned` row and add an exclusion for it.</span></span> <span data-ttu-id="df8fa-142">如需詳細資訊，請參閱 [設定及驗證 Linux 上的 Defender For Endpoint 的排除](linux-exclusions.md)專案。</span><span class="sxs-lookup"><span data-stu-id="df8fa-142">For more information, see [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

    >[!NOTE]
    > <span data-ttu-id="df8fa-143">應用程式會將統計資料儲存在記憶體中，且只會在啟動之後繼續追蹤檔活動，並啟用即時保護。</span><span class="sxs-lookup"><span data-stu-id="df8fa-143">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="df8fa-144">在即時保護關閉之前或期間所啟動的處理常式不會計算在內。</span><span class="sxs-lookup"><span data-stu-id="df8fa-144">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="df8fa-145">此外，只會計算觸發掃描的事件。</span><span class="sxs-lookup"><span data-stu-id="df8fa-145">Additionally, only events which triggered scans are counted.</span></span>

5. <span data-ttu-id="df8fa-146">針對影響效能問題及重新啟用即時保護的處理常式或磁片位置，設定 Linux 上的 Microsoft Defender for Endpoint with 排除專案。</span><span class="sxs-lookup"><span data-stu-id="df8fa-146">Configure Microsoft Defender for Endpoint on Linux with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="df8fa-147">如需詳細資訊，請參閱[設定及驗證 Linux 上適用於端點的 Microsoft Defender 排除項目](linux-exclusions.md)。</span><span class="sxs-lookup"><span data-stu-id="df8fa-147">For more information, see [Configure and validate exclusions for Microsoft Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="df8fa-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="df8fa-148">See also</span></span>
- [<span data-ttu-id="df8fa-149">調查代理程式健康狀況問題</span><span class="sxs-lookup"><span data-stu-id="df8fa-149">Investigate agent health issues</span></span>](health-status.md)