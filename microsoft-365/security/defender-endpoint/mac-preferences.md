---
title: 設定 Mac 上的 Microsoft Defender for Endpoint 的喜好設定
description: 在企業組織中設定 Mac 上端點的 MMicrosoft Defender。
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，management，喜好設定，enterprise，intune，jamf，macos，catalina，mojave，high 塞拉里昂
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
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346399"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a>在 macOS 上設定 Microsoft Defender for Endpoint 的喜好設定

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [macOS 上適用於端點的 Microsoft Defender](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
>本文包含如何針對企業組織中 macOS 之 Microsoft Defender for Endpoint 設定偏好設定的指示。 若要在使用命令列介面的 macOS 上設定 Microsoft Defender for Endpoint，請參閱 [Resources](mac-resources.md#configuring-from-the-command-line)。

## <a name="summary"></a>摘要

在企業組織中，可透過使用其中一種管理工具部署的設定檔來管理 macOS 上的 Microsoft Defender for Endpoint。 安全作業小組所管理的喜好設定優先順序高於裝置上本機設定的喜好設定。 變更透過設定設定檔設定的喜好設定時，需要提升許可權，且不需要系統管理許可權的使用者才能使用。

本文說明設定檔的結構，包含您可以用來開始使用的建議設定檔，並提供如何部署設定檔的指示。

## <a name="configuration-profile-structure"></a>設定設定檔結構

設定設定檔是由按鍵 (所識別之專案所識別的 *plist* 檔案，該專案會指出喜好設定) 的名稱，後面接著會根據喜好設定的性質而定。 值既可以是簡單的 (例如數值) 或複雜，例如首選項的嵌套清單。

>[!CAUTION]
>設定設定檔的版面配置取決於您所使用的管理主控台。 下列各節包含 JAMF 及 Intune 之設定檔的範例。

設定設定檔的最上層包括 Microsoft Defender for Endpoint 之子領域的產品範圍偏好設定和專案，在下一節將詳細說明。

### <a name="antivirus-engine-preferences"></a>防病毒引擎偏好設定

設定設定檔的 [ *antivirusEngine* ] 區段是用來管理 Microsoft Defender for Endpoint 之防病毒元件的喜好設定。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | antivirusEngine |
| **資料類型** | 字典 (嵌套偏好)  |
| **Comments** | 請參閱下列各節以取得字典內容的描述。 |

#### <a name="enable--disable-real-time-protection"></a>啟用/停用即時保護

指定是否要啟用即時保護，以在存取檔時進行掃描。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | enableRealTimeProtection |
| **資料類型** | 布林值 |
| **可能值** | true (預設)  <br/> 假 |

#### <a name="enable--disable-passive-mode"></a>啟用/停用被動模式

指定防病毒引擎是否以被動模式執行。 被動式模式的含義如下： 
- 已關閉即時保護
- 已開啟隨選掃描
- 關閉自動威脅修復功能
- 已開啟安全性智慧更新
- 隱藏狀態功能表圖示

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | passiveMode |
| **資料類型** | 布林值 |
| **可能值** | false (預設)  <br/> 真 |
| **Comments** | 可在 Microsoft Defender for Endpoint 版本100.67.60 或更新版本中使用。 |

#### <a name="exclusion-merge-policy"></a>排除合併原則

指定排除的合併原則。 這可以是管理員定義和使用者定義排除 (的組合， `merge`) 或僅限系統管理員定義的排除 (`admin_only`) 。 您可以使用此設定來限制本機使用者定義自己的排除專案。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | exclusionsMergePolicy |
| **資料類型** | 字串 |
| **可能值** | merge (預設值)  <br/> admin_only |
| **Comments** | 可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。 |

#### <a name="scan-exclusions"></a>掃描排除

指定排除在掃描之外的實體。 您可以使用完整路徑、副檔名或檔案名來指定排除。
 (排除專案是以專案陣列的形式指定，管理員可以根據需要依任何順序指定任意數目的元素。 ) 

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | 排除 |
| **資料類型** | 字典 (嵌套偏好)  |
| **Comments** | 請參閱下列各節以取得字典內容的描述。 |

##### <a name="type-of-exclusion"></a>排除的類型

指定 [依類型掃描排除的內容]。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | $type |
| **資料類型** | 字串 |
| **可能值** | excludedPath <br/> excludedFileExtension <br/> excludedFileName |

##### <a name="path-to-excluded-content"></a>排除內容的路徑

指定以完整檔案路徑掃描排除的內容。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | 路徑 |
| **資料類型** | 字串 |
| **可能值** | 有效路徑 |
| **Comments** | 僅適用于 *excludedPath* *$type* |

## <a name="supported-exclusion-types"></a>支援的排除類型

下表顯示 Mac 上的 Defender for Endpoint 所支援的排除類型。

排除 | 定義 | 範例
---|---|---
副檔名 | 在裝置上的任何位置具有分機的所有檔案 | `.test`
檔案 | 完整路徑所識別的特定檔案 | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
資料夾 | 指定資料夾底下的所有檔案 (以遞迴方式)  | `/var/log/`<br/>`/var/*/`
流程 | 指定的程式 (會以完整路徑或檔案名指定，也可以是由它所開啟的所有檔案)  | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> 以上的路徑必須是硬連結，而不是符號連結，才可成功排除。 您可以執行，檢查路徑是否為符號連結 `file <path-name>` 。

檔案、資料夾及處理常式排除支援下列萬用字元：

萬用字元 | 描述 | 範例 | 比賽 | 不符合
---|---|---|---|---
\* |    符合任何數目的任何字元，包含無 (請注意，當路徑內使用此萬用字元時，它只會取代一個資料夾)  | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
? | 符合任何單一字元 | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a> (檔/目錄的路徑類型) 

指出 *path* 屬性參照的是檔案或目錄。 

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | isDirectory |
| **資料類型** | 布林值 |
| **可能值** | false (預設)  <br/> 真 |
| **Comments** | 僅適用于 *excludedPath* *$type* |

##### <a name="file-extension-excluded-from-the-scan"></a>從掃描排除的副檔名

指定 [依副檔名掃描排除的內容]。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | 擴展 |
| **資料類型** | 字串 |
| **可能值** | 有效的副檔名 |
| **Comments** | 僅適用于 *excludedFileExtension* *$type* |

##### <a name="process-excluded-from-the-scan"></a>從掃描排除的處理常式

指定從掃描排除所有檔案活動的處理常式。 您可以透過名稱指定程式 (例如 `cat`) 或完整路徑 (例如 `/bin/cat`) 。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | name |
| **資料類型** | 字串 |
| **可能值** | 任何字串 |
| **Comments** | 僅適用于 *excludedFileName* *$type* |

#### <a name="allowed-threats"></a>允許的威脅

以 Mac 上的 Endpoint for Endpoint 未封鎖的名稱來指定威脅。 這些威脅都會允許執行。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | allowedThreats |
| **資料類型** | 字串陣列 |

#### <a name="disallowed-threat-actions"></a>不允許的威脅動作

限制偵測到威脅時，裝置的本機使用者可以採取的動作。 在此清單中包含的動作不會顯示在使用者介面中。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | disallowedThreatActions |
| **資料類型** | 字串陣列 |
| **可能值** | 允許 (限制使用者允許威脅)  <br/> restore (會限制使用者從隔離區還原威脅)  |
| **Comments** | 可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。 |

#### <a name="threat-type-settings"></a>威脅類型設定

指定 macOS 上的 Microsoft Defender for Endpoint 處理特定威脅類型的方式。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | threatTypeSettings |
| **資料類型** | 字典 (嵌套偏好)  |
| **Comments** | 請參閱下列各節以取得字典內容的描述。 |

##### <a name="threat-type"></a>威脅類型

指定威脅類型。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | 機碼 |
| **資料類型** | 字串 |
| **可能值** | potentially_unwanted_application <br/> archive_bomb |

##### <a name="action-to-take"></a>要採取的動作

指定當偵測到上述區段中所指定類型的威脅時所採取的動作。 請從下列選項中選擇：

- **Audit**：您的裝置不會受到這種威脅類型的保護，但是會記錄有關威脅的專案。
- **封鎖**：您的裝置會受到此威脅類型的保護，而且您會收到使用者介面及安全性主控台的通知。
- **Off**：您的裝置不會受到這種威脅類型的保護，而且不會記錄任何內容。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | 數值 |
| **資料類型** | 字串 |
| **可能值** | 審核 (預設)  <br/> 塊 <br/> 遠離 |

#### <a name="threat-type-settings-merge-policy"></a>威脅類型設定合併原則

指定威脅類型設定的合併原則。 這可以是管理員定義和使用者定義設定的組合， (`merge`) 或只 () 的系統管理員定義的設定 `admin_only` 。 此設定可用來限制本機使用者針對不同威脅類型定義自己的設定。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | threatTypeSettingsMergePolicy |
| **資料類型** | 字串 |
| **可能值** | merge (預設值)  <br/> admin_only |
| **Comments** | 可在 Microsoft Defender for Endpoint 版本100.83.73 或更新版本中使用。 |

#### <a name="antivirus-scan-history-retention-in-days"></a>防病毒掃描記錄保留 (天數) 

指定在裝置上的掃描歷程記錄中保留結果的天數。 舊的掃描結果會從歷史記錄中移除。 也會從磁片中移除的舊隔離檔案。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | scanResultsRetentionDays |
| **資料類型** | 字串 |
| **可能值** | 90 (預設) 。 允許的值介於1天到180天。 |
| **Comments** | 可在 Microsoft Defender for Endpoint 版本101.07.23 或更新版本中使用。 |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>防病毒掃描歷程記錄中的專案數上限

指定要保留在掃描記錄中的專案數上限。 專案包括過去執行的所有按需掃描及所有防病毒偵測。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | scanHistoryMaximumItems |
| **資料類型** | 字串 |
| **可能值** | 10000 (預設) 。 允許的值是從5000專案到15000專案。 |
| **Comments** | 可在 Microsoft Defender for Endpoint 版本101.07.23 或更新版本中使用。 |

### <a name="cloud-delivered-protection-preferences"></a>雲端提供的保護偏好設定

設定 macOS 上的 Microsoft Defender for Endpoint 的雲端驅動保護功能。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | cloudService |
| **資料類型** | 字典 (嵌套偏好)  |
| **Comments** | 請參閱下列各節以取得字典內容的描述。 |

#### <a name="enable--disable-cloud-delivered-protection"></a>啟用/停用雲端傳送保護

指定是否要對裝置啟用雲端提供保護。 若要改善服務的安全性，建議您保持此功能開啟。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | 啟用 |
| **資料類型** | 布林值 |
| **可能值** | true (預設)  <br/> 假 |

#### <a name="diagnostic-collection-level"></a>診斷集合層級

診斷資料是用來保持 Microsoft Defender 的端點安全且最新、偵測、診斷與修正問題，也可讓產品改進。 此設定會決定 Microsoft Defender for Microsoft Defender 所傳送的診斷層級。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | diagnosticLevel |
| **資料類型** | 字串 |
| **可能值** | 選用 (預設)  <br/> 必要 |

#### <a name="enable--disable-automatic-sample-submissions"></a>啟用/停用自動範例報送

會決定是否有可疑的範例 (可能包含) 傳送給 Microsoft 的威脅。 如果提交的檔案可能包含個人資訊，系統會提示您。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | automaticSampleSubmission |
| **資料類型** | 布林值 |
| **可能值** | true (預設)  <br/> 假 |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>啟用/停用自動安全性智慧更新

決定是否自動安裝安全性智慧更新：

|區段|值|
|:---|:---|
| **機碼** | automaticDefinitionUpdateEnabled |
| **資料類型** | 布林值 |
| **可能值** | true (預設)  <br/> 假 |

### <a name="user-interface-preferences"></a>使用者介面偏好設定

管理 macOS 上之 Microsoft Defender for Endpoint 之使用者介面的喜好設定。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | userInterface |
| **資料類型** | 字典 (嵌套偏好)  |
| **Comments** | 請參閱下列各節以取得字典內容的描述。 |

#### <a name="show--hide-status-menu-icon"></a>顯示/隱藏狀態功能表圖示

指定是否要顯示或隱藏螢幕右上角的 [狀態] 功能表圖示。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | hideStatusMenuIcon |
| **資料類型** | 布林值 |
| **可能值** | false (預設)  <br/> 真 |

#### <a name="show--hide-option-to-send-feedback"></a>[顯示/隱藏] 選項以傳送意見反應

指定使用者是否可以前往提交對 Microsoft 的意見反應 `Help`  >  `Send Feedback` 。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | userInitiatedFeedback |
| **資料類型** | 字串 |
| **可能值** | 已啟用 (預設)  <br/> 禁用 |
| **Comments** | 可在 Microsoft Defender for Endpoint 版本101.19.61 或更新版本中使用。 |

### <a name="endpoint-detection-and-response-preferences"></a>端點偵測和回應喜好設定

在 macOS 上管理之 Microsoft Defender for endpoint 的端點偵測和回應 (EDR) 元件。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | edr |
| **資料類型** | 字典 (嵌套偏好)  |
| **Comments** | 請參閱下列各節以取得字典內容的描述。 |

#### <a name="device-tags"></a>裝置標記

指定標記名稱及其值。 

- GROUP 標記，以指定的值標記裝置。 標記會反映在入口網站的 [裝置] 頁面底下，可用於篩選和群組裝置。

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | 標籤 |
| **資料類型** | 字典 (嵌套偏好)  |
| **Comments** | 請參閱下列各節以取得字典內容的描述。 |

##### <a name="type-of-tag"></a>標記類型

會指定標記的類型

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | 機碼 |
| **資料類型** | 字串 |
| **可能值** | `GROUP` |

##### <a name="value-of-tag"></a>標記值

指定 tag 的值

|區段|值|
|:---|:---|
| **網域** | `com.microsoft.wdav` |
| **機碼** | 數值 |
| **資料類型** | 字串 |
| **可能值** | 任何字串 |

> [!IMPORTANT]  
> - 每個 tag 類型只能設定一個值。
> - 標記的類型是唯一的，不應該在相同的設定檔中重複。

## <a name="recommended-configuration-profile"></a>建議的設定設定檔

若要開始使用，我們建議您的企業進行下列設定，以利用 Microsoft Defender for Endpoint 所提供的所有保護功能。

下列設定設定檔 (，如果 JAMF，可以上傳至自訂設定設定檔的屬性清單) 會：
- 啟用 (RTP) 的即時保護
- 指定如何處理下列威脅類型：
  - 封鎖 **(PUA) 可能有害的應用程式**
  - 將具有高壓縮率) 的封存 **bombs (檔案** 審核至 Microsoft Defender for Endpoint 記錄檔
- 啟用自動安全性情報更新
- 啟動雲端提供的保護
- 啟用自動範例提交

### <a name="property-list-for-jamf-configuration-profile"></a>JAMF 設定檔的屬性清單

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Intune 設定檔

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a>完整設定檔範例

下列範本包含本檔中所述所有設定的專案，而且可用於更高級的案例，您想要在 macOS 上進一步控制端點的 Microsoft Defender。

### <a name="property-list-for-jamf-configuration-profile"></a>JAMF 設定檔的屬性清單

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Intune 設定檔

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a>屬性清單驗證

屬性清單必須是有效的 *plist* 檔案。 您可以執行下列動作來檢查：

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

如果檔案的格式良好，上述命令會輸出並傳回 `OK` 的退出程式碼 `0` 。 否則，會顯示描述問題的錯誤，且命令會傳回的退出程式碼 `1` 。

## <a name="configuration-profile-deployment"></a>設定設定檔部署

在您為企業建立設定檔之後，您可以透過企業使用的管理主控台來部署它。 下列各節提供如何使用 JAMF 和 Intune 部署此設定檔的指示。

### <a name="jamf-deployment"></a>JAMF 部署

從 JAMF 主控台，開啟 [**電腦** 設定配置  >  **檔**]，流覽至您想要使用的設定設定檔，然後選取 [**自訂設定**]。 建立具有 `com.microsoft.wdav` 偏好的網域的專案，並上傳先前產生的 *plist* 。

>[!CAUTION]
>您必須輸入正確的喜好網域 (`com.microsoft.wdav`) ; 否則，Microsoft Defender For Endpoint 將不會識別首選項。

### <a name="intune-deployment"></a>Intune 部署

1. 開啟 [**管理**  >  **裝置** 設定]。 選取 [**管理**  >  **設定檔**  >  **建立設定檔**]。

2. 選擇設定檔的名稱。 將 **平臺 = macOS** 變更為 **Profile type = Custom**。 選取 [設定]。

3. 儲存先前產生的 plist `com.microsoft.wdav.xml` 。

4. 輸入 `com.microsoft.wdav` 為 **自訂設定設定檔名稱**。

5. 開啟設定設定檔，並上傳 `com.microsoft.wdav.xml` 檔。  (此檔案是在步驟3中建立。 ) 

6. 選取 **[確定]**。

7. 選取 [**管理**  >  **指派**]。 在 [ **包含** ] 索引標籤中，選取 [ **指派給所有使用者 & 所有裝置**]。

>[!CAUTION]
>您必須輸入正確的自訂設定檔名稱;否則，Microsoft Defender for Endpoint 將不會識別這些喜好設定。

## <a name="resources"></a>資源

- [組態設定檔參照 (Apple 開發人員文件)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
