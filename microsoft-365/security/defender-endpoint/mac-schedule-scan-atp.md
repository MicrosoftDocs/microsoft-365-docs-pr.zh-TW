---
title: 如何使用 MDATP 為 macOS 排程掃描
description: 瞭解如何在 macOS 中安排 Microsoft Defender ATP 的自動掃描時間，以更好地保護組織的資產。
keywords: microsoft、defender、atp、mac、掃描、防毒程式
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
ms.openlocfilehash: 4694ff0c0d0892b9261e61683654dfb58dfd724b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187394"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a>使用 Mac 的 Microsoft Defender 端點排程掃描

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

雖然您可以在任何時候使用 Microsoft Defender for Endpoint 開始進行威脅掃描，但您的企業可能會受益于排程或定時掃描。 例如，您可以在每個 workday 或每週開始排程掃描，以執行。 

## <a name="schedule-a-scan-with-launchd"></a>使用 *launchd* 排程掃描

您可以使用 macOS 裝置上的 *launchd* 幕後程式建立掃描排程。

1. 下列程式碼會顯示您需要用來排程掃描的架構。 開啟文字編輯器，並使用此範例做為您自己的排程掃描檔案的指南。

    如需此處所用之 *plist* 檔案格式的詳細資訊，請參閱官方 Apple 開發人員網站上的 [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) 。

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

2. 將檔案儲存為 *wdav schedquickscan*。

    > [!TIP]
    > 若要執行完整掃描而非快速掃描，請變更行12， `<string>/usr/local/bin/mdatp scan quick</string>` 以使用選項， `full` 而不是 `quick` (，例如 `<string>/usr/local/bin/mdatp scan full</string>`) 並將檔案儲存為 wdav （wdav）。 plist，而非. 已計畫的 ***快速** 掃描。 plist*。 **

3. 開啟 **終端**。
4. 輸入下列命令以載入檔案：

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. 您排程的掃描會在您于 p-清單中所定義的日期、時間及頻率執行。 在此範例中，掃描會于每星期五的 2:00 AM 執行。 

    的 `Weekday` 值 `StartCalendarInterval` 使用整數來表示一周的第五天或星期五。

 > [!IMPORTANT]
 > 以 *launchd* 執行的代理程式不會在裝置休眠時于排程的時間執行。 當裝置從睡眠模式中恢復後，就會立即執行。
 >
 > 如果裝置關閉，則掃描會在下一個排程的掃描時間執行。

## <a name="schedule-a-scan-with-intune"></a>使用 Intune 排程掃描

您也可以使用 Microsoft Intune 排程掃描。 當裝置從睡眠模式繼續時，可在[Microsoft Defender For Endpoint 的腳本](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP)中使用的[runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh)命令介面腳本將會保留。 

如需如何在您的企業中使用此腳本的詳細指示，請參閱 [在 Intune 中的 macOS 裝置上使用命令介面腳本](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) 。
