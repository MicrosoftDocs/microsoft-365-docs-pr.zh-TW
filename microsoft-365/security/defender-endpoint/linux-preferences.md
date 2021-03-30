---
title: 設定 Microsoft Defender ATP 的首選項（適用于 Linux）
ms.reviewer: ''
description: 說明如何在企業中為 Linux 設定 Microsoft Defender ATP。
keywords: microsoft，defender，atp，linux，安裝，部署，卸載，puppet，ansible，linux，redhat，ubuntu，debian，sles，suse，centos
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
ms.openlocfilehash: a8595bae216911350d3f18fcceef729ef020a424
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408162"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-linux"></a>為 Linux 設定 Microsoft Defender for Endpoint 的喜好設定

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
>本主題包含如何在企業環境中設定適用于 Linux 之 Defender 的 Defender 偏好設定的指示。 如果您想要從命令列在裝置上設定產品，請參閱 [Resources](linux-resources.md#configure-from-the-command-line)。

在企業環境中，可透過設定設定檔管理適用于 Linux 的 Defender。 此設定檔是從您選擇的管理工具部署。 由企業管理的喜好設定會優先于裝置上的本機設定。 換句話說，您企業中的使用者無法變更透過此設定檔設定的喜好設定。

本文說明此設定檔的結構 (，包括可供您開始使用的建議設定檔) 及如何部署設定檔的指示。

## <a name="configuration-profile-structure"></a>設定設定檔結構

設定設定檔是由按鍵 (所識別的專案所組成的一個 json 檔案，該專案會指出喜好設定) 的名稱，後面接著會根據喜好設定的性質而定。 值可以是簡單的，例如數值或複雜，例如首選項的嵌套清單。

一般來說，您會使用設定管理工具將名稱中的檔案推入 ```mdatp_managed.json``` 該位置 ```/etc/opt/microsoft/mdatp/managed/``` 。

設定設定檔的最上層包含產品的子領域首選項及專案，在下一節將詳細說明。

### <a name="antivirus-engine-preferences"></a>防病毒引擎偏好設定

設定設定檔的 [ *antivirusEngine* ] 區段是用來管理產品之防病毒元件的喜好設定。

|||
|:---|:---|
| **Key** | antivirusEngine |
| **資料類型** | 字典 (嵌套偏好)  |
| **Comments** | 請參閱下列各節以取得字典內容的描述。 |
|||

#### <a name="enable--disable-real-time-protection"></a>啟用/停用即時保護

會決定在啟用或未啟用) 時，是否即時保護 (掃描檔案。

|||
|:---|:---|
| **Key** | enableRealTimeProtection |
| **資料類型** | 布林值 |
| **可能值** | true (預設)  <br/> 假 |
|||

#### <a name="enable--disable-passive-mode"></a>啟用/停用被動模式

決定防病毒引擎是否以被動模式執行。 在被動模式：
- 已關閉即時保護功能。
- 已開啟隨選掃描。
- 關閉自動威脅修復功能。
- 已開啟安全性智慧更新。
- [狀態] 功能表圖示已隱藏。

|||
|:---|:---|
| **Key** | passiveMode |
| **資料類型** | 布林值 |
| **可能值** | false (預設)  <br/> 真 |
| **Comments** | 在100.67.60 或更高版本的 Defender 中提供。 |
|||

#### <a name="exclusion-merge-policy"></a>排除合併原則

指定排除專案的合併原則。 它可以是管理員定義和使用者定義排除的組合 (`merge`) 或只) 系統管理員定義的排除 (`admin_only` 。 您可以使用此設定來限制本機使用者定義自己的排除專案。

|||
|:---|:---|
| **Key** | exclusionsMergePolicy |
| **資料類型** | 字串 |
| **可能值** | merge (預設值)  <br/> admin_only |
| **Comments** | 在100.83.73 或更高版本的 Defender 中提供。 |
|||

#### <a name="scan-exclusions"></a>掃描排除

已從掃描中排除的實體。 您可以使用完整路徑、副檔名或檔案名來指定排除。

|||
|:---|:---|
| **Key** | 排除 |
| **資料類型** | 字典 (嵌套偏好)  |
| **Comments** | 請參閱下列各節以取得字典內容的描述。 |
|||

**排除的類型**

指定排除在掃描之外的內容類型。

|||
|:---|:---|
| **Key** | $type |
| **資料類型** | 字串 |
| **可能值** | excludedPath <br/> excludedFileExtension <br/> excludedFileName |
|||

**排除內容的路徑**

用於從掃描的完整檔案路徑中排除內容。

|||
|:---|:---|
| **Key** | 路徑 |
| **資料類型** | 字串 |
| **可能值** | 有效路徑 |
| **Comments** | 僅適用于 *excludedPath* *$type* |
|||

**(檔/目錄的路徑類型)**

會指出 *path* 屬性參照的是檔案或目錄。 

|||
|:---|:---|
| **Key** | isDirectory |
| **資料類型** | 布林值 |
| **可能值** | false (預設)  <br/> 真 |
| **Comments** | 僅適用于 *excludedPath* *$type* |
|||

**從掃描排除的副檔名**

用於從 [掃描者] 副檔名排除內容。

|||
|:---|:---|
| **Key** | 擴展 |
| **資料類型** | 字串 |
| **可能值** | 有效的副檔名 |
| **Comments** | 僅適用于 *excludedFileExtension* *$type* |
|||

**從掃描排除的處理常式**

指定從掃描排除所有檔案活動的處理常式。 您可以透過名稱來指定程式 (例如， `cat`) 或完整路徑 (例如 `/bin/cat`) 。

|||
|:---|:---|
| **Key** | name |
| **資料類型** | 字串 |
| **可能值** | 任何字串 |
| **Comments** | 僅適用于 *excludedFileName* *$type* |
|||

#### <a name="allowed-threats"></a>允許的威脅

根據其名稱) 所識別的威脅清單，其 (未被產品封鎖，但改為允許執行。

|||
|:---|:---|
| **Key** | allowedThreats |
| **資料類型** | 字串陣列 |
|||

#### <a name="disallowed-threat-actions"></a>不允許的威脅動作

限制偵測到威脅時，裝置的本機使用者可以採取的動作。 在此清單中包含的動作不會顯示在使用者介面中。

|||
|:---|:---|
| **Key** | disallowedThreatActions |
| **資料類型** | 字串陣列 |
| **可能值** | 允許 (限制使用者允許威脅)  <br/> restore (會限制使用者從隔離區還原威脅)  |
| **Comments** | 在100.83.73 或更高版本的 Defender 中提供。 |
|||

#### <a name="threat-type-settings"></a>威脅類型設定

防病毒引擎中的 *threatTypeSettings* 首選項是用來控制產品如何處理特定威脅類型。

|||
|:---|:---|
| **Key** | threatTypeSettings |
| **資料類型** | 字典 (嵌套偏好)  |
| **Comments** | 請參閱下列各節以取得字典內容的描述。 |
|||

**威脅類型**

設定行為的威脅類型。

|||
|:---|:---|
| **Key** | 機碼 |
| **資料類型** | 字串 |
| **可能值** | potentially_unwanted_application <br/> archive_bomb |
|||

**要採取的動作**

當您在上述區段中所指定類型的威脅到來時採取的動作。 可以是：

- **Audit**：此裝置沒有針對這類威脅進行保護，但是會記錄有關威脅的專案。
- **封鎖**：針對這類威脅保護裝置，並在安全性主控台中通知您。
- **Off**：裝置不會受到這種威脅類型的保護，而且不會記錄任何內容。

|||
|:---|:---|
| **Key** | 數值 |
| **資料類型** | 字串 |
| **可能值** | 審核 (預設)  <br/> 塊 <br/> 遠離 |
|||

#### <a name="threat-type-settings-merge-policy"></a>威脅類型設定合併原則

指定威脅類型設定的合併原則。 這可以是管理員定義和使用者定義設定的組合， (`merge`) 或只 () 的系統管理員定義的設定 `admin_only` 。 此設定可用來限制本機使用者針對不同威脅類型定義自己的設定。

|||
|:---|:---|
| **Key** | threatTypeSettingsMergePolicy |
| **資料類型** | 字串 |
| **可能值** | merge (預設值)  <br/> admin_only |
| **Comments** | 在100.83.73 或更高版本的 Defender 中提供。 |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a>防病毒掃描記錄保留 (天數) 

指定在裝置上的掃描歷程記錄中保留結果的天數。 舊的掃描結果會從歷史記錄中移除。 也會從磁片中移除的舊隔離檔案。

|||
|:---|:---|
| **Key** | scanResultsRetentionDays |
| **資料類型** | 字串 |
| **可能值** | 90 (預設) 。 允許的值介於1天到180天。 |
| **Comments** | 在101.04.76 或更高版本的 Defender 中提供。 |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>防病毒掃描歷程記錄中的專案數上限

指定要保留在掃描記錄中的專案數上限。 專案包括過去執行的所有按需掃描及所有防病毒偵測。

|||
|:---|:---|
| **Key** | scanHistoryMaximumItems |
| **資料類型** | 字串 |
| **可能值** | 10000 (預設) 。 允許的值是從5000專案到15000專案。 |
| **Comments** | 在101.04.76 或更高版本的 Defender 中提供。 |
|||

### <a name="cloud-delivered-protection-preferences"></a>雲端提供的保護偏好設定

設定設定檔中的 *cloudService* 專案是用來設定產品的雲端驅動保護功能。

|||
|:---|:---|
| **Key** | cloudService |
| **資料類型** | 字典 (嵌套偏好)  |
| **Comments** | 請參閱下列各節以取得字典內容的描述。 |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a>啟用/停用雲端已傳送保護

決定是否已在裝置上啟用雲端傳送保護。 若要改善服務的安全性，建議您保持此功能開啟。

|||
|:---|:---|
| **Key** | 啟用 |
| **資料類型** | 布林值 |
| **可能值** | true (預設)  <br/> 假 |
|||

#### <a name="diagnostic-collection-level"></a>診斷集合層級

診斷資料是用來將 Defender 設定為安全和更新、偵測、診斷和修正問題，也可讓產品改進。 此設定會決定由產品所傳送給 Microsoft 的診斷層級。

|||
|:---|:---|
| **Key** | diagnosticLevel |
| **資料類型** | 字串 |
| **可能值** | 選用 (預設)  <br/> 必要 |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a>啟用/停用自動範例報送

會決定是否有可疑的範例 (可能包含) 傳送給 Microsoft 的威脅。 有三個層級可用於控制範例提交：

- **None**：沒有可疑的範例提交給 Microsoft。
- **安全**：只有不含個人身分識別資訊 (PII) 的可疑範例會自動提交。 此為此設定的預設值。
- **All**：將所有可疑的範例提交給 Microsoft。

|||
|:---|:---|
| **Key** | automaticSampleSubmissionConsent |
| **資料類型** | 字串 |
| **可能值** | 無 <br/> 安全 (預設)  <br/> 所有 |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>啟用/停用自動安全性智慧更新

決定是否自動安裝安全性智慧更新：

|||
|:---|:---|
| **Key** | automaticDefinitionUpdateEnabled |
| **資料類型** | 布林值 |
| **可能值** | true (預設)  <br/> 假 |
|||

## <a name="recommended-configuration-profile"></a>建議的設定設定檔

若要開始使用，我們建議您的企業使用下列設定設定檔，以利用所有供 Endpoint 的 Defender 提供的保護功能。

下列設定檔將會：

- 啟用 (RTP) 的即時保護
- 指定如何處理下列威脅類型：
  - 封鎖 **(PUA) 可能有害的應用程式**
  - 將 bombs 具有高壓縮率) 的封存檔 (**檔案**，審核至產品記錄
- 啟用自動安全性情報更新
- 啟用雲端傳送保護
- 啟用層級的自動範例提交 `safe`

### <a name="sample-profile"></a>範例設定檔

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a>完整設定檔範例

下列設定設定檔包含本檔中所述所有設定的專案，而且可用於更高級的案例，您想要更進一步控制產品。

### <a name="full-profile"></a>完整設定檔

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a>設定設定檔驗證

設定設定檔必須是有效的 JSON 格式檔。 有許多工具可以用來確認這一點。 例如，如果您已 `python` 在裝置上安裝：

```bash
python -m json.tool mdatp_managed.json
```

如果 JSON 格式正確，上述命令會將其輸出到終端，並傳回的退出程式碼 `0` 。 否則，會顯示描述問題的錯誤，且命令會傳回的退出程式碼 `1` 。

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>驗證檔案上的 mdatp_managed.js是否如預期般運作
若要確認您的/etc/opt/microsoft/mdatp/managed/mdatp_managed.js開啟中是否正常運作，您應該會在下列設定旁看到「[managed]」：  
- cloud_enabled
- cloud_automatic_sample_submission_consent
- passice_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> 為使 mdatp_managed.js生效，不需要重新開機 wdavdaemon。

## <a name="configuration-profile-deployment"></a>設定設定檔部署

在您為企業建立設定檔之後，您可以透過企業使用的管理工具加以部署。 /Etc/opt/microsoft/mdatp/managed/版的 Defender for Linux 會從檔案上的 *mdatp_managed.js* 讀取 managed 設定。
