---
title: 疑難排解 Microsoft Defender for Mac 的性能問題
description: 疑難排解 Microsoft Defender for Mac 中的效能問題。
keywords: microsoft、defender、atp、mac、效能
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
ms.openlocfilehash: 6ff93b44627cf876384522f0c4f25d22347c8661
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476252"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="7d296-104">疑難排解 Microsoft Defender for Mac 的性能問題</span><span class="sxs-lookup"><span data-stu-id="7d296-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7d296-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="7d296-105">**Applies to:**</span></span>

- [<span data-ttu-id="7d296-106">Mac 版適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7d296-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="7d296-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7d296-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7d296-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d296-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7d296-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="7d296-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7d296-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="7d296-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="7d296-111">本主題提供一些一般步驟，可用來縮小 Microsoft Defender for Mac 之相關的效能問題。</span><span class="sxs-lookup"><span data-stu-id="7d296-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="7d296-112">即時保護 (RTP) 是適用于 Mac 的 Microsoft Defender 端點的功能，可持續監視和保護您的裝置免受威脅。</span><span class="sxs-lookup"><span data-stu-id="7d296-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="7d296-113">它包含檔案和程式監視及其他試探法。</span><span class="sxs-lookup"><span data-stu-id="7d296-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="7d296-114">視您執行的應用程式和裝置特性而定，當您執行 Microsoft Defender for Mac 時，可能會遇到效能效能。</span><span class="sxs-lookup"><span data-stu-id="7d296-114">Depending on the applications that you're running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="7d296-115">特別是，透過簡短的 timespan 存取許多資源的應用程式或系統進程，可能會導致 Microsoft Defender for Mac 中的效能問題。</span><span class="sxs-lookup"><span data-stu-id="7d296-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="7d296-116">下列步驟可用於疑難排解及緩解下列問題：</span><span class="sxs-lookup"><span data-stu-id="7d296-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="7d296-117">使用下列其中一種方法來停用即時保護，並觀察效能是否提高。</span><span class="sxs-lookup"><span data-stu-id="7d296-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="7d296-118">這種方法可協助縮小 Microsoft Defender for Mac 是否對效能問題造成的影響。</span><span class="sxs-lookup"><span data-stu-id="7d296-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

      <span data-ttu-id="7d296-119">如果您的裝置不是由您的組織管理，則可以使用下列其中一個選項停用即時保護：</span><span class="sxs-lookup"><span data-stu-id="7d296-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="7d296-120">從使用者介面。</span><span class="sxs-lookup"><span data-stu-id="7d296-120">From the user interface.</span></span> <span data-ttu-id="7d296-121">開啟 Mac 版的 Microsoft Defender 端點，並流覽至 [ **管理設定**]。</span><span class="sxs-lookup"><span data-stu-id="7d296-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![管理即時保護螢幕擷取畫面](images/mdatp-36-rtp.png)

    - <span data-ttu-id="7d296-123">從終端。</span><span class="sxs-lookup"><span data-stu-id="7d296-123">From the Terminal.</span></span> <span data-ttu-id="7d296-124">基於安全性的考慮，此作業需要提升。</span><span class="sxs-lookup"><span data-stu-id="7d296-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      <span data-ttu-id="7d296-125">如果您的裝置是由您的組織管理，您的系統管理員可以使用 [Microsoft Defender For Mac 的設定偏好設定](mac-preferences.md)中的指示，停用即時保護。</span><span class="sxs-lookup"><span data-stu-id="7d296-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>
      
      <span data-ttu-id="7d296-126">如果在即時保護關閉時出現效能問題，則問題的來源可能是端點偵測和回應元件。</span><span class="sxs-lookup"><span data-stu-id="7d296-126">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="7d296-127">在此情況下，請與客戶支援部門聯繫以取得進一步的指示和緩解。</span><span class="sxs-lookup"><span data-stu-id="7d296-127">In this case, please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="7d296-128">開啟 Finder，並流覽至 **應用程式**  >  **公用程式**。</span><span class="sxs-lookup"><span data-stu-id="7d296-128">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="7d296-129">開啟 **活動監視器** 並分析哪些應用程式正在使用您系統上的資源。</span><span class="sxs-lookup"><span data-stu-id="7d296-129">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="7d296-130">典型範例包括軟體 updaters 及編譯器。</span><span class="sxs-lookup"><span data-stu-id="7d296-130">Typical examples include software updaters and compilers.</span></span>

1. <span data-ttu-id="7d296-131">若要找出觸發大多數掃描的應用程式，您可以使用由 Defender for Mac 所收集的即時統計資料。</span><span class="sxs-lookup"><span data-stu-id="7d296-131">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint for Mac.</span></span>

      > [!NOTE]
      > <span data-ttu-id="7d296-132">100.90.70 或更新版本中提供此功能。</span><span class="sxs-lookup"><span data-stu-id="7d296-132">This feature is available in version 100.90.70 or newer.</span></span>
      <span data-ttu-id="7d296-133">在 **Dogfood** 和 **InsiderFast** 通道上，此功能預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="7d296-133">This feature is enabled by default on the **Dogfood** and **InsiderFast** channels.</span></span> <span data-ttu-id="7d296-134">如果您是使用不同的更新通道，可以從命令列啟用此功能：</span><span class="sxs-lookup"><span data-stu-id="7d296-134">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      <span data-ttu-id="7d296-135">這項功能需要啟用即時保護。</span><span class="sxs-lookup"><span data-stu-id="7d296-135">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="7d296-136">若要檢查即時保護的狀態，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7d296-136">To check the status of real-time protection, run the following command:</span></span>

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    <span data-ttu-id="7d296-137">確認 **real_time_protection_enabled** 專案為 true。</span><span class="sxs-lookup"><span data-stu-id="7d296-137">Verify that the **real_time_protection_enabled** entry is true.</span></span> <span data-ttu-id="7d296-138">否則，請執行下列命令來啟用它：</span><span class="sxs-lookup"><span data-stu-id="7d296-138">Otherwise, run the following command to enable it:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      <span data-ttu-id="7d296-139">若要收集目前的統計資料，請執行：</span><span class="sxs-lookup"><span data-stu-id="7d296-139">To collect current statistics, run:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      > [!NOTE]
      > <span data-ttu-id="7d296-140">使用 **--輸出 json** (請注意，雙劃線) 可確保輸出格式準備好進行分析。</span><span class="sxs-lookup"><span data-stu-id="7d296-140">Using **--output json** (note the double dash) ensures that the output format is ready for parsing.</span></span>
      <span data-ttu-id="7d296-141">這個命令的輸出會顯示所有程式及其相關聯的掃描活動。</span><span class="sxs-lookup"><span data-stu-id="7d296-141">The output of this command will show all processes and their associated scan activity.</span></span>

1. <span data-ttu-id="7d296-142">在您的 Mac 系統上，使用命令下載範例 Python 分析程式 high_cpu_parser py：</span><span class="sxs-lookup"><span data-stu-id="7d296-142">On your Mac system, download the sample Python parser high_cpu_parser.py using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    <span data-ttu-id="7d296-143">此命令的輸出應類似下列所示：</span><span class="sxs-lookup"><span data-stu-id="7d296-143">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 
    0s
    ```

1. <span data-ttu-id="7d296-144">接下來，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="7d296-144">Next, type the following commands:</span></span>

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      <span data-ttu-id="7d296-145">以上的輸出是效能問題的最熱門貢獻因素清單。</span><span class="sxs-lookup"><span data-stu-id="7d296-145">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="7d296-146">第一欄是進程識別碼 (PID) ，第二欄是 te 進程名稱，最後一欄是依影響排序的掃描檔數目。</span><span class="sxs-lookup"><span data-stu-id="7d296-146">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>

      <span data-ttu-id="7d296-147">例如，命令的輸出會如下所示：</span><span class="sxs-lookup"><span data-stu-id="7d296-147">For example, the output of the command will be something like the below:</span></span>

      ```output
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

      <span data-ttu-id="7d296-148">若要改善用於 Mac 之 Defender 的 Defender 的效能，請在 [已掃描的檔案總數] 列底下找到最高號碼的，並為其新增排除。</span><span class="sxs-lookup"><span data-stu-id="7d296-148">To improve the performance of Defender for Endpoint for Mac, locate the one with the highest number under the Total files scanned row and add an exclusion for it.</span></span> <span data-ttu-id="7d296-149">如需詳細資訊，請參閱 [Configure and validate 的 Defender For Endpoint For Linux](linux-exclusions.md)。</span><span class="sxs-lookup"><span data-stu-id="7d296-149">For more information, see [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="7d296-150">應用程式會將統計資料儲存在記憶體中，且只會在啟動之後繼續追蹤檔活動，並啟用即時保護。</span><span class="sxs-lookup"><span data-stu-id="7d296-150">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="7d296-151">在即時保護關閉之前或期間所啟動的處理常式不會計算在內。</span><span class="sxs-lookup"><span data-stu-id="7d296-151">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="7d296-152">此外，只會計算觸發掃描的事件。</span><span class="sxs-lookup"><span data-stu-id="7d296-152">Additionally, only events which triggered scans are counted.</span></span>
      > 
1. <span data-ttu-id="7d296-153">針對影響效能問題及重新啟用即時保護的處理常式或磁片位置，針對 Mac 設定 Microsoft Defender for Mac 的排除專案。</span><span class="sxs-lookup"><span data-stu-id="7d296-153">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

     <span data-ttu-id="7d296-154">如需詳細資訊，請參閱 [設定及驗證 Microsoft Defender For Mac 的排除](mac-exclusions.md) 專案。</span><span class="sxs-lookup"><span data-stu-id="7d296-154">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
