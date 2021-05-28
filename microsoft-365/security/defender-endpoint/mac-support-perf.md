---
title: 疑難排解 Microsoft Defender for Endpoint on macOS 的效能問題
description: 在 macOS 上疑難排解 Microsoft Defender for Endpoint 中的效能問題。
keywords: microsoft、defender、Microsoft Defender for Endpoint、mac、performance
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
ms.openlocfilehash: a4ebb360bc606845bfd3f80f31082c836b896477
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694254"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="67aa1-104">疑難排解 Microsoft Defender for Endpoint on macOS 的效能問題</span><span class="sxs-lookup"><span data-stu-id="67aa1-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="67aa1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="67aa1-105">**Applies to:**</span></span>

- [<span data-ttu-id="67aa1-106">macOS 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="67aa1-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="67aa1-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="67aa1-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="67aa1-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67aa1-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="67aa1-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="67aa1-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="67aa1-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="67aa1-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="67aa1-111">本主題提供一些一般步驟，可用來縮小 macOS 上與 Microsoft Defender for Endpoint 相關的效能問題。</span><span class="sxs-lookup"><span data-stu-id="67aa1-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="67aa1-112">[！注意] 即時保護 (RTP) 是一種 macOS 上的 Microsoft Defender for Endpoint 的功能，可以持續監視和保護您的裝置免受威脅。</span><span class="sxs-lookup"><span data-stu-id="67aa1-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint on macOS that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="67aa1-113">它包含檔案和程式監視及其他試探法。</span><span class="sxs-lookup"><span data-stu-id="67aa1-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="67aa1-114">視您執行的應用程式和裝置特性而定，在 macOS 上執行 Microsoft Defender for Endpoint 時，可能會遇到效能效能。</span><span class="sxs-lookup"><span data-stu-id="67aa1-114">Depending on the applications that you're running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="67aa1-115">特別是，透過簡短的 timespan 存取許多資源的應用程式或系統進程，可能會導致 macOS 中的端點的效能問題。</span><span class="sxs-lookup"><span data-stu-id="67aa1-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="67aa1-116">下列步驟可用於疑難排解及緩解下列問題：</span><span class="sxs-lookup"><span data-stu-id="67aa1-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="67aa1-117">使用下列其中一種方法來停用即時保護，並觀察效能是否提高。</span><span class="sxs-lookup"><span data-stu-id="67aa1-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="67aa1-118">這種方法可協助縮小 macOS 上的 Microsoft Defender for Endpoint 是否會影響效能問題。</span><span class="sxs-lookup"><span data-stu-id="67aa1-118">This approach helps narrow down whether Microsoft Defender for Endpoint on macOS is contributing to the performance issues.</span></span>

      <span data-ttu-id="67aa1-119">如果您的裝置不是由您的組織管理，則可以使用下列其中一個選項停用即時保護：</span><span class="sxs-lookup"><span data-stu-id="67aa1-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="67aa1-120">從使用者介面。</span><span class="sxs-lookup"><span data-stu-id="67aa1-120">From the user interface.</span></span> <span data-ttu-id="67aa1-121">在 macOS 上開啟 Microsoft Defender for Endpoint，然後流覽至 [ **管理設定**]。</span><span class="sxs-lookup"><span data-stu-id="67aa1-121">Open Microsoft Defender for Endpoint on macOS and navigate to **Manage settings**.</span></span>

      ![管理即時保護螢幕擷取畫面](images/mdatp-36-rtp.png)

    - <span data-ttu-id="67aa1-123">從終端。</span><span class="sxs-lookup"><span data-stu-id="67aa1-123">From the Terminal.</span></span> <span data-ttu-id="67aa1-124">基於安全性的考慮，此作業需要提升。</span><span class="sxs-lookup"><span data-stu-id="67aa1-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      <span data-ttu-id="67aa1-125">如果您的裝置是由您的組織管理，則系統管理員可以使用 [macOS 上 Microsoft Defender For Endpoint 的 [設定偏好設定](mac-preferences.md)] 中的指示來停用即時保護。</span><span class="sxs-lookup"><span data-stu-id="67aa1-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>
      
      <span data-ttu-id="67aa1-126">如果在即時保護關閉時出現效能問題，則問題的來源可能是端點偵測和回應元件。</span><span class="sxs-lookup"><span data-stu-id="67aa1-126">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="67aa1-127">在此情況下，請與客戶支援部門聯繫以取得進一步的指示和緩解。</span><span class="sxs-lookup"><span data-stu-id="67aa1-127">In this case, please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="67aa1-128">開啟 Finder，並流覽至 **應用程式**  >  **公用程式**。</span><span class="sxs-lookup"><span data-stu-id="67aa1-128">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="67aa1-129">開啟 **活動監視器** 並分析哪些應用程式正在使用您系統上的資源。</span><span class="sxs-lookup"><span data-stu-id="67aa1-129">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="67aa1-130">典型範例包括軟體 updaters 及編譯器。</span><span class="sxs-lookup"><span data-stu-id="67aa1-130">Typical examples include software updaters and compilers.</span></span>

1. <span data-ttu-id="67aa1-131">若要尋找觸發大部分掃描的應用程式，您可以使用由 Defender 針對 Mac 上的端點所收集的即時統計資料。</span><span class="sxs-lookup"><span data-stu-id="67aa1-131">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint on Mac.</span></span>

      > [!NOTE]
      > <span data-ttu-id="67aa1-132">100.90.70 或更新版本中提供此功能。</span><span class="sxs-lookup"><span data-stu-id="67aa1-132">This feature is available in version 100.90.70 or newer.</span></span>
      <span data-ttu-id="67aa1-133">在 **Dogfood** 和 **InsiderFast** 通道上，此功能預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="67aa1-133">This feature is enabled by default on the **Dogfood** and **InsiderFast** channels.</span></span> <span data-ttu-id="67aa1-134">如果您是使用不同的更新通道，可以從命令列啟用此功能：</span><span class="sxs-lookup"><span data-stu-id="67aa1-134">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      <span data-ttu-id="67aa1-135">這項功能需要啟用即時保護。</span><span class="sxs-lookup"><span data-stu-id="67aa1-135">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="67aa1-136">若要檢查即時保護的狀態，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="67aa1-136">To check the status of real-time protection, run the following command:</span></span>

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    <span data-ttu-id="67aa1-137">確認 **real_time_protection_enabled** 專案為 true。</span><span class="sxs-lookup"><span data-stu-id="67aa1-137">Verify that the **real_time_protection_enabled** entry is true.</span></span> <span data-ttu-id="67aa1-138">否則，請執行下列命令來啟用它：</span><span class="sxs-lookup"><span data-stu-id="67aa1-138">Otherwise, run the following command to enable it:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      <span data-ttu-id="67aa1-139">若要收集目前的統計資料，請執行：</span><span class="sxs-lookup"><span data-stu-id="67aa1-139">To collect current statistics, run:</span></span>

      ```bash
      mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
      ```

      > [!NOTE]
      > <span data-ttu-id="67aa1-140">使用 **--輸出 json** (請注意，雙劃線) 可確保輸出格式準備好進行分析。</span><span class="sxs-lookup"><span data-stu-id="67aa1-140">Using **--output json** (note the double dash) ensures that the output format is ready for parsing.</span></span>
      <span data-ttu-id="67aa1-141">這個命令的輸出會顯示所有程式及其相關聯的掃描活動。</span><span class="sxs-lookup"><span data-stu-id="67aa1-141">The output of this command will show all processes and their associated scan activity.</span></span>

1. <span data-ttu-id="67aa1-142">在您的 Mac 系統上，使用命令下載範例 Python 分析程式 high_cpu_parser py：</span><span class="sxs-lookup"><span data-stu-id="67aa1-142">On your Mac system, download the sample Python parser high_cpu_parser.py using the command:</span></span>

    ```bash
    curl -O https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    <span data-ttu-id="67aa1-143">此命令的輸出應類似下列所示：</span><span class="sxs-lookup"><span data-stu-id="67aa1-143">The output of this command should be similar to the following:</span></span>

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

1. <span data-ttu-id="67aa1-144">接下來，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="67aa1-144">Next, type the following commands:</span></span>

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      <span data-ttu-id="67aa1-145">以上的輸出是效能問題的最熱門貢獻因素清單。</span><span class="sxs-lookup"><span data-stu-id="67aa1-145">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="67aa1-146">第一欄是進程識別碼 (PID) ，第二欄是 te 進程名稱，最後一欄是依影響排序的掃描檔數目。</span><span class="sxs-lookup"><span data-stu-id="67aa1-146">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>

      <span data-ttu-id="67aa1-147">例如，命令的輸出會如下所示：</span><span class="sxs-lookup"><span data-stu-id="67aa1-147">For example, the output of the command will be something like the below:</span></span>

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

      <span data-ttu-id="67aa1-148">若要改善 Mac 上的 Defender for Endpoint 的效能，請在 [已掃描的檔案總數] 列中找出最高編號的，並為其新增排除。</span><span class="sxs-lookup"><span data-stu-id="67aa1-148">To improve the performance of Defender for Endpoint on Mac, locate the one with the highest number under the Total files scanned row and add an exclusion for it.</span></span> <span data-ttu-id="67aa1-149">如需詳細資訊，請參閱 [設定及驗證 Linux 上的 Defender For Endpoint 的排除](linux-exclusions.md)專案。</span><span class="sxs-lookup"><span data-stu-id="67aa1-149">For more information, see [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="67aa1-150">應用程式會將統計資料儲存在記憶體中，且只會在啟動之後繼續追蹤檔活動，並啟用即時保護。</span><span class="sxs-lookup"><span data-stu-id="67aa1-150">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="67aa1-151">在即時保護關閉之前或期間所啟動的處理常式不會計算在內。</span><span class="sxs-lookup"><span data-stu-id="67aa1-151">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="67aa1-152">此外，只會計算觸發掃描的事件。</span><span class="sxs-lookup"><span data-stu-id="67aa1-152">Additionally, only events which triggered scans are counted.</span></span>
      > 
1. <span data-ttu-id="67aa1-153">針對影響效能問題及重新啟用即時保護的處理常式或磁片位置，以排除 macOS，設定 Microsoft Defender for Endpoint on。</span><span class="sxs-lookup"><span data-stu-id="67aa1-153">Configure Microsoft Defender for Endpoint on macOS with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

     <span data-ttu-id="67aa1-154">如需詳細資訊，請參閱 [設定及驗證 macOS 的 Microsoft Defender For Endpoint 的排除](mac-exclusions.md) 專案。</span><span class="sxs-lookup"><span data-stu-id="67aa1-154">See [Configure and validate exclusions for Microsoft Defender for Endpoint on macOS](mac-exclusions.md) for details.</span></span>
