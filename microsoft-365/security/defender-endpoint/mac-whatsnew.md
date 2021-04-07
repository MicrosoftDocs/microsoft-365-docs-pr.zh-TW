---
title: Mac 版端點的 Microsoft Defender 新增功能
description: 瞭解舊版 Microsoft Defender for Mac 的主要變更。
keywords: microsoft、defender、atp、mac、安裝、macos、whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 5cd1f64d006b5462634dd47df9083e1a89db0e8c
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615207"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a>Mac 版端點的 Microsoft Defender 新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> 在 macOS 11 (Big Sur) 上，Microsoft Defender for Endpoint 需要其他設定設定檔。 如果您是現有的客戶從舊版的 macOS 升級，請務必部署 [此頁面](mac-sysext-policies.md)所列的其他設定檔。

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0) 

- Microsoft Defender for Mac 的端點現在可供美國政府客戶預覽。 如需詳細資訊，請參閱 [適用于美國政府客戶的 Microsoft Defender For Endpoint](gov.md)。
- 在使用 XCode 模擬器應用程式) & bug 修正時，特別針對狀況的效能增強 (

## <a name="1012364-20121021123640"></a>101.23.64 (20.121021.12364.0) 

- 將新的選項新增至命令列工具，以查看上次隨選掃描的相關資訊。 若要查看上次隨選掃描的相關資訊，請執行 `mdatp health --details antivirus`
- 效能 & bug 修正的增強功能

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0) 

- 效能 & bug 修正的增強功能

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0) 

- 效能 & bug 修正的增強功能

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0) 

> [!NOTE]
> 舊的命令列工具語法已被取代，此版本已被取代。 如需新語法的詳細資訊，請參閱 [Resources](mac-resources.md#configuring-from-the-command-line)。

- 新增命令列參數，以停用網路分機： `mdatp system-extension network-filter disable` 。 此命令可用於疑難排解 Microsoft Defender for Mac 可能相關的網路問題
- 效能 & bug 修正的增強功能

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0) 

- 錯誤修正

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0) 

- 在 macOS 11 大 Sur 上執行時，增強代理程式的可靠性
- 在 `--ignore-exclusions` 自訂掃描期間，新增命令列參數 () 忽略 AV 排除 (`mdatp scan custom`) 
- 效能 & bug 修正的增強功能

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0) 

- 當 Microsoft Defender for Endpoint 觸發 macOS 11 (大型 Sur) bug，資訊清單進入內核緊急情況時，已移除條件
- 在 mac 11 上執行時，修正端點安全性系統分機中的記憶體洩漏 (大型 Sur) 
- 錯誤修正

## <a name="1011072"></a>101.10.72

- 錯誤修正

## <a name="1010961"></a>101.09.61

- 新增受管理的首選項，以[停用傳送意見](mac-preferences.md#show--hide-option-to-send-feedback)反應的選項
- 「狀態」功能表圖示現在會顯示管理產品設定時的健康狀態。 先前，[狀態] 功能表圖示會顯示警告或錯誤狀態，即使產品設定是由系統管理員管理，也是一樣。
- 效能 & bug 修正的增強功能

## <a name="1010950"></a>101.09.50

- 本產品版本已在 macOS 大型 Sur 11 Beta 9 上驗證

- `mdatp`命令列工具的新語法現在是預設的語法。 如需新語法的詳細資訊，請參閱適用于 [Mac 的 Microsoft Defender 端點的資源](mac-resources.md#configuring-from-the-command-line)

  > [!NOTE]
  > 舊的命令列工具語法會在 **2021 年1月1日** 從產品中移除。

- `mdatp diagnostic create`使用新的參數進行擴充 (`--path [directory]`) ，可讓診斷記錄儲存至不同的目錄
- 效能 & bug 修正的增強功能

## <a name="1010949"></a>101.09.49

- 使用者介面的增強功能，可將由 IT 系統管理員所管理的排除專案與本機使用者定義的排除項加以增強
- 改進的隨選掃描的 CPU 使用率
- 效能 & bug 修正的增強功能

## <a name="1010723"></a>101.07.23

- 新增欄位至輸出中以 `mdatp --health` 檢查被動模式和 EDR 群組識別碼的狀態

  > [!NOTE]
  > `mdatp --health` 將 `mdatp health` 在未來的產品更新中取代。

- 修正了在使用者介面中未標示為受管理之自動範例提交的錯誤
- 新增設定，以控制防病毒掃描歷程記錄中專案的保留。 您現在可以[指定掃描記錄中的專案保留天數](mac-preferences.md#antivirus-scan-history-retention-in-days)，並[指定掃描歷程記錄中的專案數上限](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)。
- 錯誤修正

## <a name="1010663"></a>101.06.63

- 解決版本中引入的效能回歸 `101.05.17` 。 修正是隨修正一起引入，以消除某些客戶在存取 SMB 共用時所看到的內核緊急音。 我們已還原這段程式碼變更，並調查消除內核死機的替代方法。

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> 我們正在使用命令列工具的新的增強語法 `mdatp` 。 新的語法目前是內幕人士快速和有問必答緩慢更新通道的預設值。 我們鼓勵您使用這個新的語法來 famliliarize 您。
> 
> 我們將繼續支援舊的語法，並以新的語法平行，並在未來的月份中提供更多關於舊語法的取代計畫。

- 解決當存取 SMB 檔案共用時，有時發生的內核死機
- 效能 & bug 修正的增強功能

## <a name="1010516"></a>101.05.16

- 改進快速掃描邏輯，以大幅減少掃描的檔案數目
- 新增命令列工具的自動完成[支援](mac-resources.md#how-to-enable-autocompletion)
- 錯誤修正

## <a name="1010312"></a>101.03.12

- 效能 & bug 修正的增強功能

## <a name="1010154"></a>101.01.54

- 與時間機器相容性的增強功能
- 協助工具改進
- 效能 & bug 修正的增強功能

## <a name="1010031"></a>101.00.31

- 改進 [Intune 使用者的產品上架體驗](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)
- 防病毒 [排除現在支援萬用字元](mac-exclusions.md#supported-exclusion-types)
- 新增從 macOS 內容功能表觸發防病毒掃描的功能。 您現在可以在 Finder 中以滑鼠右鍵按一下檔案或資料夾，然後選取 [**使用 Microsoft Defender 做為端點掃描**]
- 就地產品降級現在已由安裝程式明確地禁止使用。 如果您需要降級，請先卸載現有版本，然後重新設定裝置
- & 錯誤修正的其他效能增強功能

## <a name="1009027"></a>100.90.27

- 您現在可以為 Mac 的 Microsoft Defender 端點 [設定更新通道](mac-updates.md#set-the-channel-name) ，該通道與系統範圍的更新通道不同
- 新產品圖示
- 其他使用者經驗增強功能
- 錯誤修正

## <a name="1008692"></a>100.86.92

- 與時間機器相容性的增強功能
- 解決此問題：產品有時候未清除所有卸載時所下的檔案 `/Library/Application Support/Microsoft/Defender`
- 使用 Microsoft 更新 Microsoft 產品時，降低產品的 CPU 使用率 AutoUpdate
- & 錯誤修正的其他效能增強功能

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> 為確保您的 macOS 裝置的最大保護，以及將 macOS 原生安全性更新的 Apple 停止傳遞到舊于 [current – 2] 的作業系統版本，macOS 塞拉里昂 [10.12] 上不再支援 Mac 部署和更新的 MDATP。 MDATP for Mac 更新及增強功能將會傳送至執行版本 Catalina [10.15]、Mojave [10.14] 和 High 塞拉里昂 [10.13] 的裝置。 
>
> 如果您已將 Mac 部署至您的塞拉里昂 [10.12] 裝置，請升級至最新的 macOS 版本，以避免遺失保護的風險。

- 效能 & bug 修正的增強功能

## <a name="1008373"></a>100.83.73

- 針對[排除管理](mac-preferences.md#exclusion-merge-policy)、[威脅類型設定的管理](mac-preferences.md#threat-type-settings-merge-policy)和不[允許的威脅動作](mac-preferences.md#disallowed-threat-actions)，新增更多 IT 系統管理員控制項
- 當裝置上沒有啟用完整磁片存取時，[狀態] 功能表中隨即會顯示警告。
- 效能 & bug 修正的增強功能

## <a name="1008260"></a>100.82.60

- 解決此問題：產品無法開始遵循定義更新。

## <a name="1008042"></a>100.80.42

- 錯誤修正

## <a name="1007942"></a>100.79.42

- 已修正此問題： Mac 版端點的 Microsoft Defender 有時會干擾時間機器
- 新增切換至命令列公用程式，以測試與後端服務的連線能力
  ```bash
  mdatp connectivity test
  ```
- 新增在使用者介面 (中查看完整威脅史的能力，可從 [ **保護歷史記錄** ] 視圖中存取) 
- 效能 & bug 修正的增強功能

## <a name="1007215"></a>100.72.15

- 錯誤修正

## <a name="1007099"></a>100.70.99

- 解決問題，會影響某些使用者在啟用即時保護時升級至 macOS Catalina 的能力。 這種偶發性的問題是 Microsoft Defender 在 Catalina 升級套件內針對端點鎖定檔案所造成，在掃描威脅時，這會導致升級順序失敗。

## <a name="1006899"></a>100.68.99

- 新增將防病毒功能設定為在[被動模式](mac-preferences.md#enable--disable-passive-mode)中執行的功能
- 效能 & bug 修正的增強功能

## <a name="1006528"></a>100.65.28

- 新增 macOS Catalina 的支援

  > [!CAUTION]
  > macOS 10.15 (Catalina) 包含新的安全性和隱私權增強功能。 從這個版本開始，依預設，應用程式無法存取磁片 (上的某些位置，例如檔、下載、桌面等 ) 不經明確同意。 在缺少這種同意的情況下，Microsoft Defender for Endpoint 無法完全保護您的裝置。
  >
  > 授與同意的機制取決於您部署 Microsoft Defender for Endpoint 的方式：
  >
  > - 如需手動部署，請參閱 [手動部署](mac-install-manually.md#how-to-allow-full-disk-access) 主題中的更新指示。
  > - 針對受管理的部署，請參閱以 [JAMF 為基礎的部署](mac-install-with-jamf.md) 和 [Microsoft Intune 型部署](mac-install-with-intune.md#create-system-configuration-profiles) 主題中的更新指示。

- 效能 & bug 修正的增強功能
