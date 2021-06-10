---
title: Linux 資源上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 描述 Linux 上的 Microsoft Defender for Endpoint 的資源，包括如何卸載，如何收集診斷記錄、CLI 命令，以及產品的已知問題。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，安裝，部署，卸載，puppet，ansible，linux，redhat，ubuntu，debian，sles，suse，centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 176ee89c8d60a1515855296e2565f0649f908a33
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933322"
---
# <a name="resources"></a>資源

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>收集診斷資訊

如果您可以重現問題，請先增加記錄層級，在一段時間執行系統，然後將記錄等級還原為預設值。

1. 提升記錄等級：

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. 再現問題。

3. 執行下列命令以備份端點記錄的 Defender。 檔案會儲存在 .zip 封存內。

   ```bash
   sudo mdatp diagnostic create
   ```

    在作業成功後，此命令也會將檔案路徑輸出到備份：

   ```Output
   Diagnostic file created: <path to file>
   ```

4. 還原記錄等級：

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>記錄安裝問題

若安裝時發生錯誤，安裝程式將只會報告一般失敗。

詳細記錄會儲存至 `/var/log/microsoft/mdatp_install.log` 。 如果您在安裝時發生問題，請將此檔案傳送給我們，讓我們能夠協助您診斷原因。

## <a name="uninstall"></a>解除安裝

有幾種方式可以在 Linux 上卸載端點的 Defender。 如果您使用的是設定工具（例如 Puppet），請遵循設定工具的套件卸載指示。

### <a name="manual-uninstallation"></a>手動卸載

- `sudo yum remove mdatp` 對於 RHEL 和 variant (CentOS 和 Oracle Linux) 。
- `sudo zypper remove mdatp` 用於 SLES 和變種。
- `sudo apt-get purge mdatp` 適用于 Ubuntu 和 Debian 系統。

## <a name="configure-from-the-command-line"></a>從命令列設定

您可以從命令列完成重要的工作，例如控制產品設定及觸發隨選的掃描。

### <a name="global-options"></a>全域選項

命令列工具預設會以人類可讀取的格式來輸出結果。 此外，此工具也支援將結果輸出為 JSON，這對自動化案例很有用。 若要將輸出變更為 JSON，請傳遞 `--output json` 至下列任何命令。

### <a name="supported-commands"></a>支援命令

下表列出一些最常見案例的命令。 `mdatp help`從終端執行，以查看完整的支援命令清單。

|Group                 |案例                                                |命令                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|設定         |開啟/關閉即時保護                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|設定         |開啟/關閉行為監控                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|設定         |開啟/關閉雲端保護                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|設定         |開啟/關閉產品診斷程式                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|設定         |開啟/關閉自動範例提交                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|設定         |開啟/關閉 AV 被動式模式                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|設定         |新增/移除副檔名的防病毒排除  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|設定         |新增/移除檔案的防病毒排除            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|設定         |新增/移除目錄的防病毒排除       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|設定         |新增/移除處理常式的防病毒排除         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|設定         |列出所有防病毒排除                           |`mdatp exclusion list`                                                 |
|設定         |新增威脅名稱至允許清單                   |`mdatp threat allowed add --name [threat-name]`                        |
|設定         |從允許的清單中移除威脅名稱              |`mdatp threat allowed remove --name [threat-name]`                     |
|設定         |列出所有允許的威脅名稱                           |`mdatp threat allowed list`                                            |
|設定         |開啟 PUA 保護                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|設定         |關閉 PUA 保護                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|設定         |開啟 PUA 保護的審計模式                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|診斷           |變更記錄層級                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|診斷           |產生診斷記錄                                |`mdatp diagnostic create --path [directory]`                           |
|健康情況                |檢查產品的健康情況                              |`mdatp health`                                                         |
|保護            |掃描路徑                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|保護            |進行快速掃描                                         |`mdatp scan quick`                                                     |
|保護            |執行完整掃描                                          |`mdatp scan full`                                                      |
|保護            |取消進行中的隨選掃描                        |`mdatp scan cancel`                                                    |
|保護            |要求安全性智慧更新                  |`mdatp definitions update`                                             |
|保護歷程記錄    |列印完整保護歷程記錄                       |`mdatp threat list`                                                    |
|保護歷程記錄    |取得威脅詳細資料                                      |`mdatp threat get --id [threat-id]`                                    |
|隔離管理 |列出所有隔離的檔案                              |`mdatp threat quarantine list`                                         |
|隔離管理 |從隔離區移除所有檔案                    |`mdatp threat quarantine remove-all`                                   |
|隔離管理 |新增已偵測到隔離威脅的檔案       |`mdatp threat quarantine add --id [threat-id]`                         |
|隔離管理 |從隔離區中移除被偵測為威脅的檔案  |`mdatp threat quarantine remove --id [threat-id]`                      |
|隔離管理 |從隔離區還原檔案                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|端點偵測和回應 |設定早期預覽 (未使用)                     |`mdatp edr early-preview [enable|disable]`                             |
|端點偵測和回應 |設定群組識別碼                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|端點偵測和回應 |設定/移除標籤，只 `GROUP` 支援        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|端點偵測和回應 |列出排除 (根)                         |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Microsoft Defender for Endpoint 入口網站資訊

在 [Defender for Endpoint] 入口網站中，您將會看到兩類資訊：

- 防病毒警示，包括：
  - 嚴重性
  - 掃描類型
  - 裝置資訊 (主機名稱、裝置識別碼、租使用者識別碼、應用程式版本及作業系統類型) 
  - 檔案資訊 (名稱、路徑、大小和雜湊) 
  - 威脅資訊 (名稱、類型及狀態) 
- 裝置資訊，包括：
  - 裝置識別碼
  - 租使用者識別碼
  - 應用程式版本
  - 主機名稱
  - 作業系統類型
  - 作業系統版本
  - 電腦模型
  - 處理器架構
  - 裝置是否為虛擬機器

### <a name="known-issues"></a>已知問題

- 在 Microsoft Defender 資訊安全中心入口網站的 [機器資訊] 頁面中，您可能會看到 [沒有感應器資料、受損的通訊]，即使產品如預期般運作也一樣。 我們正在努力解決此問題。
- 登入的使用者不會出現在 Microsoft Defender 資訊安全中心入口網站中。
- 在 SUSE 分配中，如果 *libatomic1* 安裝失敗，您應該確認您的作業系統已登錄：

   ```bash
   sudo SUSEConnect --status-text
   ```
