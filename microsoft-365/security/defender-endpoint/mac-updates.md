---
title: 在 Mac 上為端點部署 Microsoft Defender 的更新
description: 在企業環境中控制 Microsoft Defender for Mac 上端點的更新。
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，更新，部署
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
ms.openlocfilehash: 886195de38856306d69932446eae34212fe4bb0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934498"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>在 macOS 上部署 Microsoft Defender for Endpoint 的更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [macOS 上適用於端點的 Microsoft Defender](microsoft-defender-endpoint-mac.md)
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft 會定期發行軟體更新，以提升效能、安全性，並提供新功能。

若要在 macOS 上更新 Microsoft Defender for Endpoint，請使用名為 Microsoft AutoUpdate (MAU) 的程式。 根據預設，MAU 會每日自動檢查更新，但您可以將其變更為每週、每月或手動。

![MAU 螢幕擷取畫面](images/MDATP-34-MAU.png)

如果您決定使用軟體發佈工具來部署更新，則應該設定 MAU 以手動檢查軟體更新。 您可以部署偏好設定，以設定 MAU 檢查組織中 Mac 的更新的方式和時間。

## <a name="use-msupdate"></a>使用 msupdate

MAU 包含一個名為 *msupdate* 的命令列工具，其專為 IT 系統管理員設計，讓使用者可以更精確地控制何時套用更新。 如何使用此工具的指示，可在 [使用 msupdate 的更新 Office For Mac](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)中找到。

在 MAU 中，Microsoft Defender for Endpoint on macOS 上的應用程式識別碼是 *WDAV00*。 若要在 macOS 上下載並安裝 Microsoft Defender for Endpoint 的最新更新，請從終端視窗執行下列命令：

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>設定 Microsoft AutoUpdate 的喜好設定

本節說明可用於設定 MAU 的最常見偏好設定。 您可以透過企業使用的管理主控台，將這些設定部署為設定設定檔。 以下各節將顯示設定設定檔的範例。

### <a name="set-the-channel-name"></a>設定通道名稱

通道會判斷透過 MAU 提供的更新類型和頻率。 中的裝置 `Beta` 可在和中嘗試裝置之前的新功能 `Preview` `Current` 。 

此 `Current` 通道包含最穩定的產品版本。

>[!IMPORTANT]
> 在 Microsoft AutoUpdate 版本4.29 之前，通道具有不同的名稱： 
> 
> - `Beta` 名為 `InsiderFast` (有問必答 Fast) 
> - `Preview` 名為 `External` (內幕人士慢速) 
> - `Current` 命名為 `Production`

>[!TIP]
>為了預覽新功能並提供及早的意見反應，建議您將企業中的一些裝置設定為 `Beta` 或 `Preview` 。

|區段|值|
|:--|:--|
| **網域** | `com.microsoft.autoupdate2` |
| **Key** | ChannelName |
| **資料類型** | 字串 |
| **可能值** | Beta 版 <br/> 預覽 <br/> 目前 |
|||

>[!WARNING]
>此設定會變更透過 Microsoft AutoUpdate 更新之所有應用程式的通道。 若要將 macOS 上的通道只變更為 Microsoft Defender for Endpoint，請在取代為 `[channel-name]` 所需的通道後執行下列命令：
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>設定更新檢查頻率

變更 MAU 搜尋更新的頻率。

|區段|值|
|:--|:--|
| **網域** | `com.microsoft.autoupdate2` |
| **Key** | UpdateCheckFrequency |
| **資料類型** | 整數 |
| **預設值** | 720 (分鐘)  |
| **Comment** | 此值是以分鐘為單位設定。 |


### <a name="change-how-mau-interacts-with-updates"></a>變更 MAU 與更新互動的方式

變更 MAU 搜尋更新的方式。

|區段|值|
|:--|:--|
| **網域** | `com.microsoft.autoupdate2` |
| **Key** | HowToCheck |
| **資料類型** | 字串 |
| **可能值** | 手動 <br/> AutomaticCheck <br/> AutomaticDownload |
| **Comment** |  請注意，如果可能的話，AutomaticDownload 將會以靜默方式下載及安裝。 |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>變更是否已啟用「檢查更新」按鈕

變更 [Microsoft AutoUpdate] 使用者介面中的「檢查更新」選項是否可供本機使用者按一下。

|區段|值|
|:--|:--|
| **網域** | `com.microsoft.autoupdate2` |
| **Key** | EnableCheckForUpdatesButton |
| **資料類型** | 布林值 |
| **可能值** | True (預設)  <br/> False |


### <a name="disable-insider-checkbox"></a>停用「有問必答] 核取方塊

設定為 true 可使「加入 Office 測試人員計畫 ...」核取方塊無法使用/向使用者顯示灰色。

|區段|值|
|:--|:--|
| **網域** | `com.microsoft.autoupdate2` |
| **Key** | DisableInsiderCheckbox |
| **資料類型** | 布林值 |
| **可能值** | False (預設)  <br/> 對 |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>限制從 MAU 傳送的遙測

設定為 false 以傳送最少的心跳資料、不使用應用程式，且沒有環境細節。

|區段|值|
|:--|:--|
| **網域** | `com.microsoft.autoupdate2` |
| **Key** | SendAllTelemetryEnabled |
| **資料類型** | 布林值 |
| **可能值** | True (預設)  <br/> False |


## <a name="example-configuration-profile"></a>設定檔範例

下列設定檔用於：
- 將裝置放在 Beta 通道中
- 自動下載並安裝更新
- 啟用使用者介面中的「檢查更新」按鈕
- 允許裝置上的使用者登錄到內幕通道

### <a name="jamf"></a>JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a>Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Beta</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

若要設定 MAU，您可以從您的企業所使用的管理工具部署此設定設定檔：
- 從 JAMF 上載此設定設定檔，並將偏好設定網域設定為 *autoupdate2*。
- 在 Intune 上，上傳此設定設定檔，並將自訂設定檔名稱設定為 *autoupdate2*。

## <a name="resources"></a>資源

- [msupdate 參照](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
