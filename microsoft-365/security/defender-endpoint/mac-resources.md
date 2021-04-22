---
title: Mac 上的 Microsoft Defender for Endpoint 的資源
description: Mac 上的 Microsoft Defender for Endpoint 的資源，包括如何卸載，如何收集診斷記錄、CLI 命令及產品的已知問題。
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，安裝，部署，卸載，intune，jamf，macos，catalina，mojave，高塞拉里昂
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
ms.openlocfilehash: 34feeec0f8c34748678862b9aa7b20f84087eb5e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934522"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>macOS 上的 Microsoft Defender for Endpoint 資源

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>收集診斷資訊

如果您可以重現問題，請增加記錄層級、執行系統一段時間，並將記錄等級還原為預設值。

1. 提升記錄等級：

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. 再現問題

3. 執行 `sudo mdatp diagnostic create` 以備份 Microsoft Defender For Endpoint 記錄。 檔案會儲存在 .zip 封存中。 在作業成功之後，此命令也會將檔案路徑輸出到備份。

   > [!TIP]
   > 根據預設，診斷記錄會儲存至 `/Library/Application Support/Microsoft/Defender/wdavdiag/` 。 若要變更儲存診斷記錄的目錄，請傳送 `--path [directory]` 至下列命令，以 `[directory]` 所需的目錄取代。

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. 還原記錄等級：

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>記錄安裝問題

若安裝時發生錯誤，安裝程式將只會報告一般失敗。

詳細記錄會儲存至 `/Library/Logs/Microsoft/mdatp/install.log` 。 如果您在安裝時發生問題，請將此檔案傳送給我們，讓我們能夠協助您診斷原因。

## <a name="uninstalling"></a>卸載

有幾種方式可以在 macOS 上卸載 Microsoft Defender for Endpoint。 請注意，在 JAMF 中提供集中式管理的卸載時，Microsoft Intune 仍無法使用它。

### <a name="interactive-uninstallation"></a>互動式卸載

- 開啟 **Finder > 應用程式**。 在 **Microsoft Defender For Endpoint 上按一下滑鼠右鍵 > 移至垃圾桶**。

### <a name="from-the-command-line"></a>從命令列

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a>從命令列設定

您可以從命令列完成重要的工作，例如控制產品設定及觸發隨選掃描。

|Group        |案例                                   |命令                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|組態|開啟/關閉即時保護           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|組態|開啟/關閉雲端保護               |`mdatp config cloud --value [enabled/disabled]`                                   |
|組態|開啟/關閉產品診斷程式            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|組態|開啟/關閉自動範例提交    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|組態|新增威脅名稱至允許清單      |`mdatp threat allowed add --name [threat-name]`                                   |
|組態|從允許的清單中移除威脅名稱 |`mdatp threat allowed remove --name [threat-name]`                                |
|組態|列出所有允許的威脅名稱              |`mdatp threat allowed list`                                                       |
|組態|開啟 PUA 保護                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|組態|關閉 PUA 保護                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|組態|開啟 PUA 保護的審計模式      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|組態|開啟/關閉 passiveMode                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|診斷  |變更記錄層級                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|診斷  |產生診斷記錄                   |`mdatp diagnostic create --path [directory]`                                      |
|健康情況       |檢查產品的健康情況                 |`mdatp health`                                                                    |
|健康情況       |檢查 spefic 產品屬性       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|保護   |掃描路徑                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|保護   |進行快速掃描                            |`mdatp scan quick`                                                                |
|保護   |執行完整掃描                             |`mdatp scan full`                                                                 |
|保護   |取消進行中的隨選掃描           |`mdatp scan cancel`                                                               |
|保護   |要求安全性智慧更新     |`mdatp definitions update`                                                        |
|EDR          |Add group tag to to device。 EDR 標記是用來管理裝置群組。 如需詳細資訊，請造訪 https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups |`mdatp edr tag set --name GROUP --value [name]` |
|EDR          |從裝置移除組標記               |`mdatp edr tag remove --tag-name [name]`                                          |
|EDR          |新增群組識別碼                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a>如何啟用自動完成

若要在 bash 中啟用自動完成功能，請執行下列命令，並重新啟動終端機會話：

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

若要在 zsh 中啟用自動執行：

- 檢查您的裝置是否已啟用自動完成功能：

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- 如果上述命令沒有產生任何輸出，您可以使用下列命令來啟用自動完成功能：

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- 執行下列命令，在 macOS 上啟用 Microsoft Defender for Endpoint 的自動完成功能，並重新啟動終端機：

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>用戶端 Microsoft Defender 端點隔離目錄

`/Library/Application Support/Microsoft/Defender/quarantine/` 包含隔離的檔案 `mdatp` 。 檔案會在威脅 trackingId 之後命名。 目前的 trackingIds 會顯示 `mdatp threat list` 。

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Microsoft Defender for Endpoint 入口網站資訊

[MacOS 的 EDR 功能現在已到達](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)，在 microsoft Defender for endpoint 博客上，提供 microsoft Defender For Endpoint Security Center 中預期內容的詳細指引。
