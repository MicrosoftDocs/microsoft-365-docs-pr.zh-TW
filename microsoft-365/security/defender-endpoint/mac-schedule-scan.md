---
title: 如何在 macOS 上使用 Microsoft Defender for Endpoint 排程掃描
description: 瞭解如何為 macOS 中的 Microsoft Defender for Endpoint 排程自動掃描時間，以便更好地保護組織的資產。
keywords: microsoft、defender、Microsoft Defender for Endpoint、mac、掃描、防毒程式
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
ms.openlocfilehash: a93ea3427c72eb5529715b92cb18d01462493cc6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842851"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="c73d8-104">在 macOS 上使用 Microsoft Defender for Endpoint 排程掃描</span><span class="sxs-lookup"><span data-stu-id="c73d8-104">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c73d8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c73d8-105">**Applies to:**</span></span>
- [<span data-ttu-id="c73d8-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c73d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c73d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c73d8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c73d8-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="c73d8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c73d8-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="c73d8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c73d8-110">雖然您可以在任何時候使用 Microsoft Defender for Endpoint 開始進行威脅掃描，但您的企業可能會受益于排程或定時掃描。</span><span class="sxs-lookup"><span data-stu-id="c73d8-110">While you can start a threat scan at any time with Microsoft Defender for Endpoint, your enterprise might benefit from scheduled or timed scans.</span></span> <span data-ttu-id="c73d8-111">例如，您可以在每個 workday 或每週開始排程掃描，以執行。</span><span class="sxs-lookup"><span data-stu-id="c73d8-111">For example, you can schedule a scan to run at the beginning of every workday or week.</span></span> 

## <a name="schedule-a-scan-with-launchd"></a><span data-ttu-id="c73d8-112">使用 *launchd* 排程掃描</span><span class="sxs-lookup"><span data-stu-id="c73d8-112">Schedule a scan with *launchd*</span></span>

<span data-ttu-id="c73d8-113">您可以使用 macOS 裝置上的 *launchd* 幕後程式建立掃描排程。</span><span class="sxs-lookup"><span data-stu-id="c73d8-113">You can create a scanning schedule using the *launchd* daemon on a macOS device.</span></span>

1. <span data-ttu-id="c73d8-114">下列程式碼會顯示您需要用來排程掃描的架構。</span><span class="sxs-lookup"><span data-stu-id="c73d8-114">The following code shows the schema you need to use to schedule a scan.</span></span> <span data-ttu-id="c73d8-115">開啟文字編輯器，並使用此範例做為您自己的排程掃描檔案的指南。</span><span class="sxs-lookup"><span data-stu-id="c73d8-115">Open a text editor and use this example as a guide for your own scheduled scan file.</span></span>

    <span data-ttu-id="c73d8-116">如需此處所用之 *plist* 檔案格式的詳細資訊，請參閱官方 Apple 開發人員網站上的 [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) 。</span><span class="sxs-lookup"><span data-stu-id="c73d8-116">For more information on the *.plist* file format used here, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) at the official Apple developer website.</span></span>

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. <span data-ttu-id="c73d8-117">將檔案儲存為 *wdav schedquickscan*。</span><span class="sxs-lookup"><span data-stu-id="c73d8-117">Save the file as *com.microsoft.wdav.schedquickscan.plist*.</span></span>

    > [!TIP]
    > <span data-ttu-id="c73d8-118">若要執行完整掃描而非快速掃描，請變更行12， `<string>/usr/local/bin/mdatp scan quick</string>` 以使用選項， `full` 而不是 `quick` (，例如 `<string>/usr/local/bin/mdatp scan full</string>`) 並將檔案儲存為 wdav （wdav）。 plist，而非. 已計畫的 ***快速** 掃描。 plist*。 \*\*</span><span class="sxs-lookup"><span data-stu-id="c73d8-118">To run a full scan instead of a quick scan, change line 12, `<string>/usr/local/bin/mdatp scan quick</string>`, to use the `full` option instead of `quick` (i.e. `<string>/usr/local/bin/mdatp scan full</string>`) and save the file as *com.microsoft.wdav.sched **full** scan.plist* instead of *com.microsoft.wdav.sched **quick** scan.plist*.</span></span>

3. <span data-ttu-id="c73d8-119">開啟 **終端**。</span><span class="sxs-lookup"><span data-stu-id="c73d8-119">Open **Terminal**.</span></span>
4. <span data-ttu-id="c73d8-120">輸入下列命令以載入檔案：</span><span class="sxs-lookup"><span data-stu-id="c73d8-120">Enter the following commands to load your file:</span></span>

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. <span data-ttu-id="c73d8-121">您排程的掃描會在您于 p-清單中所定義的日期、時間及頻率執行。</span><span class="sxs-lookup"><span data-stu-id="c73d8-121">Your scheduled scan will run at the date, time, and frequency you defined in your p-list.</span></span> <span data-ttu-id="c73d8-122">在此範例中，掃描會于每星期五的 2:00 AM 執行。</span><span class="sxs-lookup"><span data-stu-id="c73d8-122">In the example, the scan runs at 2:00 AM every Friday.</span></span> 

    <span data-ttu-id="c73d8-123">的 `Weekday` 值 `StartCalendarInterval` 使用整數來表示一周的第五天或星期五。</span><span class="sxs-lookup"><span data-stu-id="c73d8-123">The `Weekday` value of `StartCalendarInterval` uses an integer to indicate the fifth day of the week, or Friday.</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="c73d8-124">以 *launchd* 執行的代理程式不會在裝置休眠時于排程的時間執行。</span><span class="sxs-lookup"><span data-stu-id="c73d8-124">Agents executed with *launchd* will not run at the scheduled time while the device is asleep.</span></span> <span data-ttu-id="c73d8-125">當裝置從睡眠模式中恢復後，就會立即執行。</span><span class="sxs-lookup"><span data-stu-id="c73d8-125">They will instead run once the device resumes from sleep mode.</span></span>
 >
 > <span data-ttu-id="c73d8-126">如果裝置關閉，則掃描會在下一個排程的掃描時間執行。</span><span class="sxs-lookup"><span data-stu-id="c73d8-126">If the device is turned off, the scan will run at the next scheduled scan time.</span></span>

## <a name="schedule-a-scan-with-intune"></a><span data-ttu-id="c73d8-127">使用 Intune 排程掃描</span><span class="sxs-lookup"><span data-stu-id="c73d8-127">Schedule a scan with Intune</span></span>

<span data-ttu-id="c73d8-128">您也可以使用 Microsoft Intune 排程掃描。</span><span class="sxs-lookup"><span data-stu-id="c73d8-128">You can also schedule scans with Microsoft Intune.</span></span> <span data-ttu-id="c73d8-129">當裝置從睡眠模式繼續時，可在[Microsoft Defender For Endpoint 的腳本](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP)中使用的[runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh)命令介面腳本將會保留。</span><span class="sxs-lookup"><span data-stu-id="c73d8-129">The [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell script available at [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) will persist when the device resumes from sleep mode.</span></span> 

<span data-ttu-id="c73d8-130">如需如何在您的企業中使用此腳本的詳細指示，請參閱 [在 Intune 中的 macOS 裝置上使用命令介面腳本](/mem/intune/apps/macos-shell-scripts) 。</span><span class="sxs-lookup"><span data-stu-id="c73d8-130">See [Use shell scripts on macOS devices in Intune](/mem/intune/apps/macos-shell-scripts) for more detailed instructions on how to use this script in your enterprise.</span></span>
