---
title: 為效能問題疑難排解
description: 疑難排解 Microsoft Defender for Endpoint 中與即時保護服務相關的高 CPU 使用率。
keywords: 疑難排解、效能、高 CPU 使用率、高 CPU 使用率、錯誤、修正、更新規範、oms、監視器、報告、Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: normal
manager: dansimp
ms.date: 04/14/2021
audience: ITPro
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 5175d630dd5d80b62451b3a1eafc4c2f6350ac32
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876334"
---
# <a name="troubleshoot-performance-issues-related-to-real-time-protection"></a><span data-ttu-id="27112-104">疑難排解與即時保護相關的效能問題</span><span class="sxs-lookup"><span data-stu-id="27112-104">Troubleshoot performance issues related to real-time protection</span></span>


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="27112-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="27112-105">**Applies to:**</span></span>

- [<span data-ttu-id="27112-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="27112-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
 
<span data-ttu-id="27112-107">如果您的系統與 Microsoft Defender for Endpoint 中的即時保護服務有高 CPU 使用量或效能問題，您可以將票證提交給 Microsoft 支援人員。</span><span class="sxs-lookup"><span data-stu-id="27112-107">If your system is having high CPU usage or performance issues related to the real-time protection service in Microsoft Defender for Endpoint, you can submit a ticket to Microsoft support.</span></span> <span data-ttu-id="27112-108">依照 [收集 Microsoft DEFENDER AV 診斷資料](/collect-diagnostic-data.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="27112-108">Follow the steps in [Collect Microsoft Defender AV diagnostic data](/collect-diagnostic-data.md).</span></span>

<span data-ttu-id="27112-109">身為系統管理員，您也可以自行疑難排解這些問題。</span><span class="sxs-lookup"><span data-stu-id="27112-109">As an admin, you can also troubleshoot these issues on your own.</span></span> 

<span data-ttu-id="27112-110">首先，您可能想要檢查問題是否由其他軟體所導致。</span><span class="sxs-lookup"><span data-stu-id="27112-110">First, you might want to check if the issue is being caused by another software.</span></span> <span data-ttu-id="27112-111">[請與廠商聯繫以取得防病毒排除](#check-with-vendor-for-antivirus-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="27112-111">Read [Check with vendor for antivirus exclusions](#check-with-vendor-for-antivirus-exclusions).</span></span>

<span data-ttu-id="27112-112">否則，您可以遵循 [分析 Microsoft Protection 記錄](#analyze-the-microsoft-protection-log)中的步驟，識別哪個軟體與識別的性能問題相關。</span><span class="sxs-lookup"><span data-stu-id="27112-112">Otherwise, you can identify which software is related to the identified performance issue by following the steps in [Analyze the Microsoft Protection Log](#analyze-the-microsoft-protection-log).</span></span> 

<span data-ttu-id="27112-113">您也可以遵循下列步驟，將您提交的其他記錄提供給 Microsoft 支援：</span><span class="sxs-lookup"><span data-stu-id="27112-113">You can also provide additional logs to your submission to Microsoft support by following the steps in:</span></span>
- [<span data-ttu-id="27112-114">使用進程監視器捕獲處理常式記錄</span><span class="sxs-lookup"><span data-stu-id="27112-114">Capture process logs using Process Monitor</span></span>](#capture-process-logs-using-process-monitor)
- [<span data-ttu-id="27112-115">使用 Windows 效能錄製器捕獲效能記錄</span><span class="sxs-lookup"><span data-stu-id="27112-115">Capture performance logs using Windows Performance Recorder</span></span>](#capture-performance-logs-using-windows-performance-recorder) 

## <a name="check-with-vendor-for-antivirus-exclusions"></a><span data-ttu-id="27112-116">向廠商核實防病毒排除</span><span class="sxs-lookup"><span data-stu-id="27112-116">Check with vendor for antivirus exclusions</span></span>

<span data-ttu-id="27112-117">如果您可以輕鬆識別影響系統效能的軟體，請移至軟體廠商的知識文庫或支援中心。</span><span class="sxs-lookup"><span data-stu-id="27112-117">If you can readily identify the software affecting system performance, go to the software vendor's knowledge base or support center.</span></span> <span data-ttu-id="27112-118">搜尋是否有有關防病毒排除專案的建議。</span><span class="sxs-lookup"><span data-stu-id="27112-118">Search if they have recommendations about antivirus exclusions.</span></span> <span data-ttu-id="27112-119">若廠商的網站沒有，您可以與他們一起開啟支援票證，並要求他們發佈一個。</span><span class="sxs-lookup"><span data-stu-id="27112-119">If the vendor's website does not have them, you can open a support ticket with them and ask them to publish one.</span></span> 

<span data-ttu-id="27112-120">我們建議軟體廠商遵循與行業合作的各種指導方針 [，以盡可能減少](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/)誤報。</span><span class="sxs-lookup"><span data-stu-id="27112-120">We recommend that software vendors follow the various guidelines in [Partnering with the industry to minimize false positives](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/).</span></span> <span data-ttu-id="27112-121">廠商可以透過 [Microsoft Defender Security 情報入口網站提交其軟體 (MDSI) ](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper)。</span><span class="sxs-lookup"><span data-stu-id="27112-121">The vendor can submit their software through the [Microsoft Defender Security Intelligence portal (MDSI)](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper).</span></span>


## <a name="analyze-the-microsoft-protection-log"></a><span data-ttu-id="27112-122">分析 Microsoft 保護記錄</span><span class="sxs-lookup"><span data-stu-id="27112-122">Analyze the Microsoft Protection Log</span></span>

<span data-ttu-id="27112-123">在 **MPLog-xxxxxxxx-xxxxxx** 中，您可以在 *EstimatedImpact* 的情況下，找出執行軟體的預估效能影響資訊：</span><span class="sxs-lookup"><span data-stu-id="27112-123">In **MPLog-xxxxxxxx-xxxxxx.log**, you can find the estimated performance impact information of running software as *EstimatedImpact*:</span></span>
    
`Per-process counts:ProcessImageName: smsswd.exe, TotalTime: 6597, Count: 1406, MaxTime: 609, MaxTimeFile: \Device\HarddiskVolume3\_SMSTaskSequence\Packages\WQ1008E9\Files\FramePkg.exe, EstimatedImpact: 65%`

| <span data-ttu-id="27112-124">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="27112-124">Field name</span></span> | <span data-ttu-id="27112-125">描述</span><span class="sxs-lookup"><span data-stu-id="27112-125">Description</span></span> |
|---|---|
|<span data-ttu-id="27112-126">ProcessImageName</span><span class="sxs-lookup"><span data-stu-id="27112-126">ProcessImageName</span></span> | <span data-ttu-id="27112-127">處理常式影像名稱</span><span class="sxs-lookup"><span data-stu-id="27112-127">Process image name</span></span> |
| <span data-ttu-id="27112-128">TotalTime</span><span class="sxs-lookup"><span data-stu-id="27112-128">TotalTime</span></span> | <span data-ttu-id="27112-129">掃描此程式所存取之檔案所花費的累計持續時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="27112-129">The cumulative duration in milliseconds spent in scans of files accessed by this process</span></span> |
|<span data-ttu-id="27112-130">計數</span><span class="sxs-lookup"><span data-stu-id="27112-130">Count</span></span> | <span data-ttu-id="27112-131">此處理程式存取的掃描檔數目</span><span class="sxs-lookup"><span data-stu-id="27112-131">The number of scanned files accessed by this process</span></span> |
|<span data-ttu-id="27112-132">MaxTime</span><span class="sxs-lookup"><span data-stu-id="27112-132">MaxTime</span></span> |  <span data-ttu-id="27112-133">此程式存取之檔案的最長單一掃描的持續時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="27112-133">The duration in milliseconds in the longest single scan of a file accessed by this process</span></span> |
| <span data-ttu-id="27112-134">MaxTimeFile</span><span class="sxs-lookup"><span data-stu-id="27112-134">MaxTimeFile</span></span> | <span data-ttu-id="27112-135">此程式所存取之記錄的最長掃描時間的路徑 `MaxTime`</span><span class="sxs-lookup"><span data-stu-id="27112-135">The path of the file accessed by this process for which the longest scan of `MaxTime` duration was recorded</span></span> |
| <span data-ttu-id="27112-136">EstimatedImpact</span><span class="sxs-lookup"><span data-stu-id="27112-136">EstimatedImpact</span></span> | <span data-ttu-id="27112-137">在此程式經歷掃描活動的期間內，掃描此程式所存取之檔案所花費的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="27112-137">The percentage of time spent in scans for files accessed by this process out of the period in which this process experienced scan activity</span></span> |

<span data-ttu-id="27112-138">如果效能影響很高，請遵循 [Configure and validate the The Microsoft Defender 防病毒掃描](collect-diagnostic-data.md)中的步驟，嘗試將此程式新增至路徑/進程排除。</span><span class="sxs-lookup"><span data-stu-id="27112-138">If the performance impact is high, try adding the process to the Path/Process exclusions by following the steps in [Configure and validate exclusions for Microsoft Defender Antivirus scans](collect-diagnostic-data.md).</span></span>

<span data-ttu-id="27112-139">如果上一個步驟沒有解決問題，您可以在下列各節中透過「程式 [監視器](#capture-process-logs-using-process-monitor) 」或「 [Windows 效能記錄器](#capture-performance-logs-using-windows-performance-recorder) 」來收集詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="27112-139">If the previous step doesn't solve the problem, you can collect more information through the [Process Monitor](#capture-process-logs-using-process-monitor) or the [Windows Performance Recorder](#capture-performance-logs-using-windows-performance-recorder) in the following sections.</span></span>
     
## <a name="capture-process-logs-using-process-monitor"></a><span data-ttu-id="27112-140">使用進程監視器捕獲處理常式記錄</span><span class="sxs-lookup"><span data-stu-id="27112-140">Capture process logs using Process Monitor</span></span>

<span data-ttu-id="27112-141">Process Monitor (ProcMon) 是一種可顯示即時處理程式的高級監控工具。</span><span class="sxs-lookup"><span data-stu-id="27112-141">Process Monitor (ProcMon) is an advanced monitoring tool that can show real-time processes.</span></span> <span data-ttu-id="27112-142">您可以使用此功能，在出現效能問題時進行捕獲。</span><span class="sxs-lookup"><span data-stu-id="27112-142">You can use this to capture the performance issue as it is occurring.</span></span>

1. <span data-ttu-id="27112-143">下載程式將 [3.60](/sysinternals/downloads/procmon) 至資料夾（如所示） `C:\temp` 。</span><span class="sxs-lookup"><span data-stu-id="27112-143">Download [Process Monitor v3.60](/sysinternals/downloads/procmon) to a folder like `C:\temp`.</span></span>

2. <span data-ttu-id="27112-144">若要移除檔案的網站標記：</span><span class="sxs-lookup"><span data-stu-id="27112-144">To remove the file's mark of the web:</span></span>
    1. <span data-ttu-id="27112-145">以滑鼠右鍵按一下 [ **ProcessMonitor.zip** ]，然後選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="27112-145">Right-click **ProcessMonitor.zip** and select **Properties**.</span></span>
    1. <span data-ttu-id="27112-146">在 [ *一般* ] 索引標籤下，尋找 [ *安全性*]。</span><span class="sxs-lookup"><span data-stu-id="27112-146">Under the *General* tab, look for *Security*.</span></span>
    1. <span data-ttu-id="27112-147">核取方塊旁邊的 [ **解除封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="27112-147">Check the box beside **Unblock**.</span></span>
    1. <span data-ttu-id="27112-148">選取 **套用**。</span><span class="sxs-lookup"><span data-stu-id="27112-148">Select **Apply**.</span></span>
    
    ![移除 MOTW](images/procmon-motw.png) 

3. <span data-ttu-id="27112-150">解壓縮檔， `C:\temp` 以將資料夾路徑 `C:\temp\ProcessMonitor` 。</span><span class="sxs-lookup"><span data-stu-id="27112-150">Unzip the file in `C:\temp` so that the folder path will be `C:\temp\ProcessMonitor`.</span></span> 

4. <span data-ttu-id="27112-151">將 **ProcMon.exe**  複製到您要進行疑難排解的 windows 用戶端或 windows server。</span><span class="sxs-lookup"><span data-stu-id="27112-151">Copy **ProcMon.exe**  to the Windows client or Windows server you're troubleshooting.</span></span>  

5. <span data-ttu-id="27112-152">在執行 ProcMon 之前，請確定未關閉與高 CPU 使用率問題相關的所有其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="27112-152">Before running ProcMon, make sure all other applications not related to the high CPU usage issue are closed.</span></span> <span data-ttu-id="27112-153">這樣做會使要檢查的程式數目降至最低。</span><span class="sxs-lookup"><span data-stu-id="27112-153">Doing this will minimize the number of processes to check.</span></span>

6. <span data-ttu-id="27112-154">您可以透過兩種方式啟動 ProcMon。</span><span class="sxs-lookup"><span data-stu-id="27112-154">You can launch ProcMon in two ways.</span></span>
    1. <span data-ttu-id="27112-155">以滑鼠右鍵按一下 **ProcMon.exe** ，然後選取 [以 **系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="27112-155">Right-click **ProcMon.exe** and select **Run as administrator**.</span></span> 
    

        <span data-ttu-id="27112-156">因為記錄會自動開始，請選取放大鏡圖示以停止目前的捕獲或使用鍵盤快速鍵 **Ctrl + E**。</span><span class="sxs-lookup"><span data-stu-id="27112-156">Since logging starts automatically, select the magnifying glass icon  to stop the current capture or use the keyboard shortcut **Ctrl+E**.</span></span>
 
        ![放大鏡圖示](images/procmon-magglass.png)

        <span data-ttu-id="27112-158">若要確認您已停止捕獲，請檢查放大鏡圖示現在是否出現紅色的 X。</span><span class="sxs-lookup"><span data-stu-id="27112-158">To verify that you have stopped the capture, check if the magnifying glass icon now appears with a red X.</span></span>

        ![紅色斜線](images/procmon-magglass-stop.png)         

        <span data-ttu-id="27112-160">接下來，若要清除先前的捕獲，請選取橡皮擦圖示。</span><span class="sxs-lookup"><span data-stu-id="27112-160">Next, to clear the earlier capture, select the eraser icon.</span></span>

        ![清除圖示](images/procmon-eraser-clear.png)

        <span data-ttu-id="27112-162">或使用鍵盤快速鍵 **Ctrl + X**。</span><span class="sxs-lookup"><span data-stu-id="27112-162">Or use the keyboard shortcut **Ctrl+X**.</span></span>

    2. <span data-ttu-id="27112-163">第二種方式是以系統管理員身分執行 **命令列** ，然後從進程監視器路徑執行：</span><span class="sxs-lookup"><span data-stu-id="27112-163">The second way is to run the **command line** as admin, then from the Process Monitor path, run:</span></span>

        ![cmd procmon](images/cmd-procmon.png)
 
        ```console
        Procmon.exe /AcceptEula /Noconnect /Profiling
        ```
        
        >[!TIP] 
        ><span data-ttu-id="27112-165">在捕獲資料時，讓 [ProcMon] 視窗盡可能小型，這樣您就能輕鬆地開始及停止追蹤。</span><span class="sxs-lookup"><span data-stu-id="27112-165">Make the ProcMon window as small as possible when capturing data so you can easily start and stop the trace.</span></span>
        > 
        >![最小化 Procmon](images/procmon-minimize.png)
    
7. <span data-ttu-id="27112-167">遵循步驟6中的其中一個程式之後，您將會看到一個設定篩選的選項。</span><span class="sxs-lookup"><span data-stu-id="27112-167">After following one of the procedures in step 6, you'll next see an option to set filters.</span></span> <span data-ttu-id="27112-168">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="27112-168">Select **OK**.</span></span> <span data-ttu-id="27112-169">您可以在捕獲完成後，永遠篩選結果。</span><span class="sxs-lookup"><span data-stu-id="27112-169">You can always filter the results after the capture is completed.</span></span>
 
    ![篩選輸出進程名稱為系統排除](images/procmon-filter-options.png) 

8. <span data-ttu-id="27112-171">若要開始捕獲，請再次選取放大鏡圖示。</span><span class="sxs-lookup"><span data-stu-id="27112-171">To start the capture, select the magnifying glass icon again.</span></span>
     
9. <span data-ttu-id="27112-172">再現問題。</span><span class="sxs-lookup"><span data-stu-id="27112-172">Reproduce the problem.</span></span>
 
    >[!TIP] 
    ><span data-ttu-id="27112-173">請等候問題完全再現，然後記下追蹤開始時的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="27112-173">Wait for the problem to be fully reproduced, then take note of the timestamp when the trace started.</span></span>
    

10. <span data-ttu-id="27112-174">當 CPU 使用量高的情況時，有兩到四分鐘的處理常式活動，請選取放大鏡圖示以停止捕獲。</span><span class="sxs-lookup"><span data-stu-id="27112-174">Once you have two to four minutes of process activity during the high CPU usage condition, stop the capture by selecting the magnifying glass icon.</span></span>

11. <span data-ttu-id="27112-175">若要以唯一名稱及 pml 格式儲存捕獲，請選取 [檔案] **，然後選取** [ **儲存 ...**]。請務必選取 [ **所有事件** ] 和 [ **原生進程監控] 格式 (PML)** 中的選項按鈕。</span><span class="sxs-lookup"><span data-stu-id="27112-175">To save the capture with a unique name and with the .pml format, select **File** then select **Save...**. Make sure to select the radio buttons **All events** and **Native Process Monitor Format (PML)**.</span></span>

    ![儲存設定](images/procmon-savesettings1.png)

12. <span data-ttu-id="27112-177">若要更好地追蹤，請將預設路徑從 `C:\temp\ProcessMonitor\LogFile.PML` 到 `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` ：</span><span class="sxs-lookup"><span data-stu-id="27112-177">For better tracking, change the default path from `C:\temp\ProcessMonitor\LogFile.PML` to `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` where:</span></span>
    - <span data-ttu-id="27112-178">`%ComputerName%` 是裝置名稱</span><span class="sxs-lookup"><span data-stu-id="27112-178">`%ComputerName%` is the device name</span></span>
    - <span data-ttu-id="27112-179">`MMDDYEAR` 為月、日、年</span><span class="sxs-lookup"><span data-stu-id="27112-179">`MMDDYEAR` is the month, day, and year</span></span>
    -  <span data-ttu-id="27112-180">`Repro_of_issue` 是您要嘗試再現之問題的名稱</span><span class="sxs-lookup"><span data-stu-id="27112-180">`Repro_of_issue` is the name of the issue you're trying to reproduce</span></span>

    >[!TIP] 
    > <span data-ttu-id="27112-181">如果您有正常運作的系統，您可能想要取得範例記錄以進行比較。</span><span class="sxs-lookup"><span data-stu-id="27112-181">If you have a working system, you might want to get a sample log to compare.</span></span>

13. <span data-ttu-id="27112-182">請壓縮 pml 檔案，並將它提交給 Microsoft 支援部門。</span><span class="sxs-lookup"><span data-stu-id="27112-182">Zip the .pml file and submit it to Microsoft support.</span></span>


## <a name="capture-performance-logs-using-windows-performance-recorder"></a><span data-ttu-id="27112-183">使用 Windows 效能錄製器捕獲效能記錄</span><span class="sxs-lookup"><span data-stu-id="27112-183">Capture performance logs using Windows Performance Recorder</span></span>

<span data-ttu-id="27112-184">您可以使用 Windows 效能錄影機 (WPR) ，在提交給 Microsoft 支援人員時包含其他資訊。</span><span class="sxs-lookup"><span data-stu-id="27112-184">You can use Windows Performance Recorder (WPR) to include additional information in your submission to Microsoft support.</span></span> <span data-ttu-id="27112-185">WPR 是一種強大的錄製工具，可建立 Windows 錄製的事件追蹤。</span><span class="sxs-lookup"><span data-stu-id="27112-185">WPR is a powerful recording tool that creates Event Tracing for Windows recordings.</span></span> 

<span data-ttu-id="27112-186">WPR 是 Windows 評估和部署套件 (Windows ADK) 的一部分，而且可以從 [下載和安裝 WINDOWS adk](/windows-hardware/get-started/adk-install)下載。</span><span class="sxs-lookup"><span data-stu-id="27112-186">WPR is part of the Windows Assessment and Deployment Kit (Windows ADK) and can be downloaded from [Download and install the Windows ADK](/windows-hardware/get-started/adk-install).</span></span> <span data-ttu-id="27112-187">您也可以在 [windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk/)中，以 Windows 10 軟體發展套件的一部分下載。</span><span class="sxs-lookup"><span data-stu-id="27112-187">You can also download it as part of the Windows 10 Software Development Kit at [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk/).</span></span>

<span data-ttu-id="27112-188">您可以使用 WPR 使用者介面，遵循透過 [WPR UI 捕獲效能記錄](#capture-performance-logs-using-the-wpr-ui)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="27112-188">You can use the WPR user interface by following the steps in [Capture performance logs using the WPR UI](#capture-performance-logs-using-the-wpr-ui).</span></span> 

<span data-ttu-id="27112-189">或者，您也可以使用命令列工具 *wpr.exe*，在 Windows 8 和更新版本中，遵循透過 [WPR CLI 取得效能記錄](#capture-performance-logs-using-the-wpr-cli)檔中的步驟，即可使用此工具。</span><span class="sxs-lookup"><span data-stu-id="27112-189">Alternatively, you can also use the command-line tool *wpr.exe*, which is available in Windows 8 and later versions  by following the steps in [Capture performance logs using the WPR CLI](#capture-performance-logs-using-the-wpr-cli).</span></span>


### <a name="capture-performance-logs-using-the-wpr-ui"></a><span data-ttu-id="27112-190">使用 WPR UI 捕獲效能記錄</span><span class="sxs-lookup"><span data-stu-id="27112-190">Capture performance logs using the WPR UI</span></span>

>[!TIP]
><span data-ttu-id="27112-191">如果有多個裝置發生問題，請使用具有最多 RAM 的一個裝置。</span><span class="sxs-lookup"><span data-stu-id="27112-191">If you have multiple devices where the issue is occurring, use the one which has the most amount of RAM.</span></span>

1. <span data-ttu-id="27112-192">下載並安裝 WPR。</span><span class="sxs-lookup"><span data-stu-id="27112-192">Download and install WPR.</span></span>

2. <span data-ttu-id="27112-193">在 [ *Windows 工具組*] 底下，以滑鼠右鍵按一下 [ **windows Performance 答錄機**]。</span><span class="sxs-lookup"><span data-stu-id="27112-193">Under *Windows Kits*, right-click **Windows Performance Recorder**.</span></span> 

    ![[開始] 功能表](images/wpr-01.png)

    <span data-ttu-id="27112-195">選取 [ **更多**]。</span><span class="sxs-lookup"><span data-stu-id="27112-195">Select **More**.</span></span> <span data-ttu-id="27112-196">選取 [以 **系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="27112-196">Select **Run as administrator**.</span></span>

3. <span data-ttu-id="27112-197">出現 [使用者帳戶控制] 對話方塊時，選取 [ **是]**。</span><span class="sxs-lookup"><span data-stu-id="27112-197">When the User Account Control dialog box appears, select **Yes**.</span></span>

    ![Uac](images/wpt-yes.png)

4. <span data-ttu-id="27112-199">接下來，下載 [Microsoft Defender For Endpoint 分析](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp) 設定檔，並將其另存為 `WD.wprp` 資料夾（如） `C:\temp` 。</span><span class="sxs-lookup"><span data-stu-id="27112-199">Next, download the [Microsoft Defender for Endpoint analysis](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp) profile and save as `WD.wprp` to a folder like `C:\temp`.</span></span> 
     
5. <span data-ttu-id="27112-200">在 [WPR] 對話方塊中，選取 [ **更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="27112-200">On the WPR dialog box, select **More options**.</span></span>

    ![選取更多選項](images/wpr-03.png)

6. <span data-ttu-id="27112-202">選取 [ **新增設定檔** ]，然後流覽至檔案的路徑 `WD.wprp` 。</span><span class="sxs-lookup"><span data-stu-id="27112-202">Select **Add Profiles...** and browse to the path of the `WD.wprp` file.</span></span>

7. <span data-ttu-id="27112-203">之後，您應該會在它底下的 [ *Microsoft Defender For Endpoint analysis* *] 下看到* 新的設定檔集。</span><span class="sxs-lookup"><span data-stu-id="27112-203">After that, you should see a new profile set under *Custom measurements* named *Microsoft Defender for Endpoint analysis* underneath it.</span></span>

    ![檔內](images/wpr-infile.png)

    >[!WARNING]
    ><span data-ttu-id="27112-205">如果您的 Windows 伺服器有 64 GB 或以上的 RAM，請使用自訂度量， `Microsoft Defender for Endpoint analysis for large servers` 而不要使用 `Microsoft Defender for Endpoint analysis` 。</span><span class="sxs-lookup"><span data-stu-id="27112-205">If your Windows Server has 64 GB of RAM or more, use the custom measurement `Microsoft Defender for Endpoint analysis for large servers` instead of `Microsoft Defender for Endpoint analysis`.</span></span> <span data-ttu-id="27112-206">否則，您的系統可能會耗用大量的非分頁集區記憶體或緩衝區，可能會導致系統不穩定。</span><span class="sxs-lookup"><span data-stu-id="27112-206">Otherwise, your system could consume a high amount of non-paged pool memory or buffers which can lead to system instability.</span></span> <span data-ttu-id="27112-207">您可以透過展開 **資源分析** 來選擇要新增的設定檔。</span><span class="sxs-lookup"><span data-stu-id="27112-207">You can choose which profiles to add by expanding **Resource Analysis**.</span></span> <span data-ttu-id="27112-208">這個自訂設定檔提供深入效能分析所需的內容。</span><span class="sxs-lookup"><span data-stu-id="27112-208">This custom profile provides the necessary context for in-depth performance analysis.</span></span>
 
8. <span data-ttu-id="27112-209">若要在 WPR UI 中使用自訂度量值 Microsoft Defender for Endpoint verbose analysis profile：</span><span class="sxs-lookup"><span data-stu-id="27112-209">To use the custom measurement Microsoft Defender for Endpoint verbose analysis profile in the WPR UI:</span></span>

    1. <span data-ttu-id="27112-210">確定在 *第一層會審*、 *資源分析* 和 *案例分析* 群組下沒有選取設定檔。</span><span class="sxs-lookup"><span data-stu-id="27112-210">Ensure no profiles are selected under the *First-level triage*, *Resource Analysis* and *Scenario Analysis* groups.</span></span>
    2. <span data-ttu-id="27112-211">選取 [ **自訂測量**]。</span><span class="sxs-lookup"><span data-stu-id="27112-211">Select **Custom measurements**.</span></span>
    3. <span data-ttu-id="27112-212">選取 [ **Microsoft Defender For Endpoint analysis**]。</span><span class="sxs-lookup"><span data-stu-id="27112-212">Select **Microsoft Defender for Endpoint analysis**.</span></span>
    4. <span data-ttu-id="27112-213">選取 \**詳細\*\*\*資料* 層級。</span><span class="sxs-lookup"><span data-stu-id="27112-213">Select **Verbose** under *Detail* level.</span></span>
    1. <span data-ttu-id="27112-214">選取 [記錄模式] **底下的 [** 檔案] 或 [ **記憶體** ]。</span><span class="sxs-lookup"><span data-stu-id="27112-214">Select **File** or **Memory** under Logging mode.</span></span> 

    >[!important]
    ><span data-ttu-id="27112-215">當使用者可以直接再現效能問題 *時，應選取 [* 檔案] 以使用檔記錄模式。</span><span class="sxs-lookup"><span data-stu-id="27112-215">You should select *File* to use the file logging mode if the performance issue can be reproduced directly by the user.</span></span> <span data-ttu-id="27112-216">大多數問題都屬於這類類別。</span><span class="sxs-lookup"><span data-stu-id="27112-216">Most issues fall under this category.</span></span> <span data-ttu-id="27112-217">不過，如果使用者無法直接再現問題，但是只要發生問題，使用者就應該選取 [ *記憶體* ]，以使用記憶體記錄模式。</span><span class="sxs-lookup"><span data-stu-id="27112-217">However, if the user cannot directly reproduce the issue but can easily notice it once the issue occurs, the user should select *Memory* to use the memory logging mode.</span></span> <span data-ttu-id="27112-218">這可確保追蹤記錄檔不會因長期的執行時間而過度膨脹。</span><span class="sxs-lookup"><span data-stu-id="27112-218">This ensures that the trace log will not inflate excessively due to the long run time.</span></span>

9. <span data-ttu-id="27112-219">現在您已經準備好收集資料。</span><span class="sxs-lookup"><span data-stu-id="27112-219">Now you're ready to collect data.</span></span> <span data-ttu-id="27112-220">請退出所有與再現效能問題無關的應用程式。</span><span class="sxs-lookup"><span data-stu-id="27112-220">Exit all the applications that are not relevant to reproducing the performance issue.</span></span> <span data-ttu-id="27112-221">您可以選取 [ **隱藏選項** ]，將 WPR 視窗所佔用的空間變小。</span><span class="sxs-lookup"><span data-stu-id="27112-221">You can select **Hide options** to keep the space occupied by the WPR window small.</span></span>

    ![Hipe 選項](images/wpr-08.png)

    >[!TIP]
    ><span data-ttu-id="27112-223">嘗試以整數秒數秒開始追蹤。</span><span class="sxs-lookup"><span data-stu-id="27112-223">Try starting the trace at whole number seconds.</span></span> <span data-ttu-id="27112-224">例如，01:30:00。</span><span class="sxs-lookup"><span data-stu-id="27112-224">For instance, 01:30:00.</span></span> <span data-ttu-id="27112-225">這可讓您更輕鬆地分析資料。</span><span class="sxs-lookup"><span data-stu-id="27112-225">This will make it easier to analyze the data.</span></span> <span data-ttu-id="27112-226">此外，請嘗試追蹤完全在問題再現時的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="27112-226">Also try to keep track of the timestamp of exactly when the issue is reproduced.</span></span>

10. <span data-ttu-id="27112-227">選取 [開始]。</span><span class="sxs-lookup"><span data-stu-id="27112-227">Select **Start**.</span></span>

    ![選取追蹤的開始](images/wpr-09.png)

11. <span data-ttu-id="27112-229">再現問題。</span><span class="sxs-lookup"><span data-stu-id="27112-229">Reproduce the issue.</span></span>

    >[!TIP]
    ><span data-ttu-id="27112-230">將資料收集保留在五分鐘內。</span><span class="sxs-lookup"><span data-stu-id="27112-230">Keep the data collection to no more than five minutes.</span></span> <span data-ttu-id="27112-231">在收集大量資料後，有兩到三分鐘是很好的範圍。</span><span class="sxs-lookup"><span data-stu-id="27112-231">Two to three minutes is a good range since a lot of data is being collected.</span></span>

12. <span data-ttu-id="27112-232">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="27112-232">Select **Save**.</span></span>

    ![選取 [儲存]](images/wpr-10.png)

13. <span data-ttu-id="27112-234">填寫 **問題的詳細描述中的類型：** 包括有關問題的資訊以及再現問題的方式。</span><span class="sxs-lookup"><span data-stu-id="27112-234">Fill up **Type in a detailed description of the problem:** with information about the problem and how you reproduced the issue.</span></span>

    ![填滿詳細資料](images/wpr-12.png)

    1. <span data-ttu-id="27112-236">選取檔案名 **：** 以決定儲存追蹤檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="27112-236">Select **File Name:** to determine where your trace file will be saved.</span></span> <span data-ttu-id="27112-237">根據預設，1.is 會儲存至 `%user%\Documents\WPR Files\` 。</span><span class="sxs-lookup"><span data-stu-id="27112-237">By default, it 1.is saved to `%user%\Documents\WPR Files\`.</span></span>
    1. <span data-ttu-id="27112-238">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="27112-238">Select **Save**.</span></span>

14. <span data-ttu-id="27112-239">正在合併追蹤，請稍候。</span><span class="sxs-lookup"><span data-stu-id="27112-239">Wait while the trace is being merged.</span></span>

    ![WPR 收集一般追蹤](images/wpr-13.png)

15. <span data-ttu-id="27112-241">儲存追蹤後，選取 [ **開啟資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="27112-241">Once the trace is saved, select **Open folder**.</span></span>

    ![儲存 WPR 追蹤](images/wpr-14.png)

    <span data-ttu-id="27112-243">將您提交的檔案和資料夾都包含在 Microsoft 支援檔中。</span><span class="sxs-lookup"><span data-stu-id="27112-243">Include both the file and the folder in your submission to Microsoft support.</span></span>

    ![檔案和資料夾](images/wpr-15.png)

### <a name="capture-performance-logs-using-the-wpr-cli"></a><span data-ttu-id="27112-245">使用 WPR CLI 捕獲效能記錄</span><span class="sxs-lookup"><span data-stu-id="27112-245">Capture performance logs using the WPR CLI</span></span>

<span data-ttu-id="27112-246">命令列工具 *wpr.exe* 是以 Windows 8 開頭的作業系統的一部分。</span><span class="sxs-lookup"><span data-stu-id="27112-246">The command-line tool *wpr.exe* is part of the operating system starting with Windows 8.</span></span> <span data-ttu-id="27112-247">若要使用命令列工具 wpr.exe 收集 WPR 追蹤，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="27112-247">To collect a WPR trace using the command-line tool wpr.exe:</span></span>

1. <span data-ttu-id="27112-248">下載 **[Microsoft Defender For Endpoint 分析](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** 設定檔，以取得 `WD.wprp` 在本機目錄（如）中指定的檔案效能追蹤 `C:\traces` 。</span><span class="sxs-lookup"><span data-stu-id="27112-248">Download **[Microsoft Defender for Endpoint analysis](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** profile for performance traces to a file named `WD.wprp` in a local directory such as `C:\traces`.</span></span>

3. <span data-ttu-id="27112-249">在 [開始] **功能表** 圖示上按一下滑鼠右鍵，然後選取 [ **Windows Powershell (管理員])** 或 **命令提示字元 (Admin)** 以開啟系統管理員命令提示字元視窗。</span><span class="sxs-lookup"><span data-stu-id="27112-249">Right-click the **Start Menu** icon and select **Windows Powershell (Admin)** or **Command Prompt (Admin)** to open an Admin command prompt window.</span></span>

4. <span data-ttu-id="27112-250">出現 [使用者帳戶控制] 對話方塊時，選取 [ **是]**。</span><span class="sxs-lookup"><span data-stu-id="27112-250">When the User Account Control dialog box appears, select **Yes**.</span></span>

5. <span data-ttu-id="27112-251">在 [提升] 提示中執行下列命令，以啟動 Microsoft Defender for Endpoint 效能追蹤：</span><span class="sxs-lookup"><span data-stu-id="27112-251">At the elevated prompt, run the following command to start a Microsoft Defender for Endpoint performance trace:</span></span>

    ```console
    wpr.exe -start C:\traces\WD.wprp!WD.Verbose -filemode
    ```
    
    >[!WARNING]
    ><span data-ttu-id="27112-252">如果您的 Windows Server 有 64 GB 或 RAM 或更多，請使用設定檔 `WDForLargeServers.Light` ， `WDForLargeServers.Verbose` 而不是設定檔和設定檔 `WD.Light` `WD.Verbose` 。</span><span class="sxs-lookup"><span data-stu-id="27112-252">If your Windows Server has 64 GB or RAM or more, use profiles `WDForLargeServers.Light` and `WDForLargeServers.Verbose` instead of profiles `WD.Light` and `WD.Verbose`, respectively.</span></span> <span data-ttu-id="27112-253">否則，您的系統可能會耗用大量的非分頁集區記憶體或緩衝區，可能會導致系統不穩定。</span><span class="sxs-lookup"><span data-stu-id="27112-253">Otherwise, your system could consume a high amount of non-paged pool memory or buffers which can lead to system instability.</span></span>

6. <span data-ttu-id="27112-254">再現問題。</span><span class="sxs-lookup"><span data-stu-id="27112-254">Reproduce the issue.</span></span>

    >[!TIP]
    ><span data-ttu-id="27112-255">將資料收集保留5分鐘以上。</span><span class="sxs-lookup"><span data-stu-id="27112-255">Keep the data collection no to more than five minutes.</span></span>  <span data-ttu-id="27112-256">視案例而定，在收集大量資料後，兩到三分鐘是一個很好的範圍。</span><span class="sxs-lookup"><span data-stu-id="27112-256">Depending on the scenario, two to three minutes is a good range since a lot of data is being collected.</span></span>

7. <span data-ttu-id="27112-257">在 [提升] 提示中執行下列命令，以停止效能追蹤，並確定提供有關問題的資訊以及再現問題的方式：</span><span class="sxs-lookup"><span data-stu-id="27112-257">At the elevated prompt, run the following command to stop the performance trace, making sure to provide information about the problem and how you reproduced the issue:</span></span>

    ```console
    wpr.exe -stop merged.etl "Timestamp when the issue was reproduced, in HH:MM:SS format" "Description of the issue" "Any error that popped up"
    ```

8. <span data-ttu-id="27112-258">請稍候，直到合併追蹤。</span><span class="sxs-lookup"><span data-stu-id="27112-258">Wait until the trace is merged.</span></span> 

9. <span data-ttu-id="27112-259">將您提交的檔案和資料夾都包含在 Microsoft 支援檔中。</span><span class="sxs-lookup"><span data-stu-id="27112-259">Include both the file and the folder in your submission to Microsoft support.</span></span>

## <a name="see-also"></a><span data-ttu-id="27112-260">另請參閱</span><span class="sxs-lookup"><span data-stu-id="27112-260">See also</span></span>

- [<span data-ttu-id="27112-261">收集 Microsoft Defender AV 診斷資料</span><span class="sxs-lookup"><span data-stu-id="27112-261">Collect Microsoft Defender AV diagnostic data</span></span>](collect-diagnostic-data.md)
- [<span data-ttu-id="27112-262">設定及驗證 Microsoft Defender 防病毒掃描的排除專案</span><span class="sxs-lookup"><span data-stu-id="27112-262">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)