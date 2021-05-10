---
title: 使用群組原則設定 Microsoft Defender 防毒軟體
description: 瞭解如何使用群組原則來設定及管理 Microsoft Defender for Endpoint 中的端點上的 Microsoft Defender 防毒軟體。
keywords: 群組原則、GPO、設定、設定
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/08/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 74f58959c22313806ebc95aef14e8ccb2d75326b
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302097"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>使用群組原則設定來設定及管理 Microsoft Defender 防毒軟體

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用[群組原則](/windows/win32/srvnodes/group-policy)來設定及管理端點上的 Microsoft Defender 防毒軟體。

## <a name="configure-microsoft-defender-antivirus-using-group-policy"></a>使用群組原則設定 Microsoft Defender 防毒軟體

一般來講，您可以使用下列程式設定或變更 Microsoft Defender 防毒軟體群組原則設定：

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下要設定 (GPO) 的群組原則物件，然後按一下 [ **編輯**]。

2. 使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]。

3. 按一下 [系統 **管理範本**]。

4. 展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**。

5. 在本主題中，展開包含您要設定之設定的此區段中 (參照為 **Location 的位置**) ，按兩下此設定以開啟它，然後進行設定變更。

6. 照常[部署更新的 GPO](/windows/win32/srvnodes/group-policy)。 

## <a name="group-policy-settings-and-resources"></a>群組原則設定和資源

本主題中的下表列出 Windows 10 中可用的群組原則設定，版本1703，並提供此文件庫中適當主題的連結，以便在適用) 中 (。 

> [!TIP]
> [下載 Windows 10 (2004) 的群組原則設定參考試算表（可能為2020更新](https://www.microsoft.com/download/101451)）。 這個試算表會列出電腦和使用者設定的原則設定，這些設定會包含在隨之傳送的系統管理範本檔案中 Windows 10 可能是2020更新 (2004) 。 您可以設定在編輯群組原則物件時，參考試算表。

| 位置 | 設定 | 文章 |
|:---|:---|:---|
| 用戶端介面 | 啟用無周邊 UI 模式 | [防止使用者看到或與 Microsoft Defender 防毒軟體使用者介面互動](prevent-end-user-interaction-microsoft-defender-antivirus.md) |
| 用戶端介面 | 在用戶端需要執行動作時，向其顯示其他文字 | [設定出現在端點上的通知](configure-notifications-microsoft-defender-antivirus.md) |
| 用戶端介面 | 抑制所有通知 | [設定出現在端點上的通知](configure-notifications-microsoft-defender-antivirus.md) |
| 用戶端介面 | 抑制重新開機通知 | [設定出現在端點上的通知](configure-notifications-microsoft-defender-antivirus.md) |
| 排除項目 | 副檔名排除 | [設定及驗證 Microsoft Defender 防毒軟體掃描中的排除專案](configure-exclusions-microsoft-defender-antivirus.md) |
| 排除項目 | 路徑排除 | [設定及驗證 Microsoft Defender 防毒軟體掃描中的排除專案](configure-exclusions-microsoft-defender-antivirus.md) |
| 排除項目 | 處理常式排除 | [設定及驗證 Microsoft Defender 防毒軟體掃描中的排除專案](configure-exclusions-microsoft-defender-antivirus.md) | 
| 排除項目 | 關閉自動排除 | [設定及驗證 Microsoft Defender 防毒軟體掃描中的排除專案](configure-exclusions-microsoft-defender-antivirus.md) |
| 地圖 | 設定「第一次看到的封鎖」功能 | [啟用封鎖第一次看到](configure-block-at-first-sight-microsoft-defender-antivirus.md) |
| 地圖 | 加入 Microsoft MAPS | [啟動雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md) |
| 地圖 | 需要進一步分析時傳送檔範例 | [啟動雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md) |
| 地圖 | 設定本地設定覆寫以進行 Microsoft MAPS 報告 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| MpEngine | 設定擴充的雲端檢查 | [設定雲端封鎖逾時期間](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) |
| MpEngine | 選取雲端保護層級 | [指定雲端提供的保護層級](specify-cloud-protection-level-microsoft-defender-antivirus.md) |
| 網路檢查系統 | 指定網路流量檢查的其他定義集 | [指定網路流量檢查的其他定義集](specify-additional-definitions-network-traffic-inspection-mdav.md) |
| 網路檢查系統 | 開啟定義停用 | [設定定義退休](turn-on-definition-retirement.md)  |
| 網路檢查系統 | 開啟通訊協定識別 | [開啟通訊協定識別](turn-on-protocol-recognition.md)  |
| 隔離 | 設定從隔離區移除專案的本機設定覆寫 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 隔離 | 設定從隔離資料夾中移除專案 | [設定 Microsoft Defender 防毒軟體掃描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 即時保護 | 設定本機設定覆寫以監控電腦上的檔案和程式活動 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 即時保護 | 設定針對內送和外寄檔案活動進行監視的本機設定覆寫 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 即時保護 | 設定本機設定覆寫以掃描所有已下載的檔案和附件 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 即時保護 | 設定本機設定超越開啟行為監控 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 即時保護 | 設定本機設定覆寫以開啟即時保護 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 即時保護 | 定義要掃描的下載檔案和附件大小上限 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 即時保護 | 監視電腦上的檔案和程式活動 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 即時保護 | 掃描所有已下載的檔案和附件 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 即時保護 | 關閉即時保護 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 即時保護 | 開啟行為監控 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 即時保護 | 在啟用即時保護時開啟處理常式掃描 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 即時保護 | 開啟原始大量寫入通知 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 即時保護 | 設定對內送和外寄檔案和程式活動的監控 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 修復 | 設定本機設定覆寫以執行排定的完整掃描以完成修復的時間 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 修復 | 指定一周中的哪幾天執行排程完整掃描以完成修復 | [設定排定的 Microsoft Defender 防毒軟體掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 修復 | 指定一天中執行計畫完整掃描以完成修復的時間 | [設定排定的 Microsoft Defender 防毒軟體掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 報告 | 關閉增強型通知 | [設定出現在端點上的通知](configure-notifications-microsoft-defender-antivirus.md)
| 根 | 關閉 Microsoft Defender 防毒軟體 | 未使用 (此設定必須設定為 [ **未** 設定]，以確保任何已安裝的協力廠商防病毒應用程式正確運作) 
| 根 | 定義位址以略過 proxy 伺服器 | 未使用 |
| 根 | 定義 proxy 自動設定 (。用於連線至網路的 pac)  | 未使用 |
| 根 | 定義用來連線到網路的 proxy 伺服器 | 未使用 |
| 根 | 設定清單的本機系統管理員合併行為 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 根 | 允許反惡意軟體服務以一般優先順序啟動 | [設定 Microsoft Defender 防毒軟體掃描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 根 | 允許反惡意程式碼服務持續保持執行狀態 | [設定 Microsoft Defender 防毒軟體掃描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 根 | 關閉常式修復 | [設定 Microsoft Defender 防毒軟體掃描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 根 | 隨機化排程的任務時間 | [設定 Microsoft Defender 防毒軟體的排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 掃描 | 允許使用者暫停掃描 | [避免使用者看到 Microsoft Defender 防毒軟體使用者介面 (或與其互動](prevent-end-user-interaction-microsoft-defender-antivirus.md)，Windows 10 上不支援)  |
| 掃描 | 執行排程掃描之前，請先檢查是否有最新的病毒和間諜軟體定義 | [管理事件型強制更新](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 掃描 | 定義要強制執行追趕掃描的天數 | [管理已過期端點的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 掃描 | 開啟追趕完整掃描 | [管理已過期端點的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 掃描 | 開啟追趕快速掃描 | [管理已過期端點的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 掃描 | 設定本機設定覆寫以取得 CPU 使用率的最大百分比 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 掃描 | 設定排程掃描日的本機設定覆寫 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 掃描 | 設定計劃快速掃描時間的本機設定覆寫 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 掃描 | 設定計劃掃描時間的本機設定覆寫 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 掃描 | 設定針對掃描類型用於排程掃描的本機設定覆寫 | [防止或允許使用者本機修改原則設定](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 掃描 | 建立系統還原點 | [設定 Microsoft Defender 防毒軟體掃描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 掃描 | 開啟從掃描歷程記錄資料夾中移除專案 | [設定 Microsoft Defender 防毒軟體掃描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 掃描 | 開啟試探法 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 掃描 | 開啟電子郵件掃描 | [在 Microsoft Defender 防毒軟體中設定掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 掃描 | 開啟重新分析點掃描 | [在 Microsoft Defender 防毒軟體中設定掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 掃描 | 在對應的網路磁碟機上執行完整掃描 | [在 Microsoft Defender 防毒軟體中設定掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 掃描 | 掃描封存檔案 | [在 Microsoft Defender 防毒軟體中設定掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 掃描 | 掃描網路檔 | [在 Microsoft Defender 防毒軟體中設定掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 掃描 | 掃描打包的可執行檔 | [在 Microsoft Defender 防毒軟體中設定掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 掃描 | 掃描可移除的磁片磁碟機 | [在 Microsoft Defender 防毒軟體中設定掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 掃描 | 指定掃描封存檔案的最大深度 | [在 Microsoft Defender 防毒軟體中設定掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 掃描 | 指定掃描期間 CPU 使用率的最大百分比 | [在 Microsoft Defender 防毒軟體中設定掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 掃描 | 指定要掃描的封存檔案大小上限 | [在 Microsoft Defender 防毒軟體中設定掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 掃描 | 指定一周中的哪一天執行排程掃描 | [設定 Microsoft Defender 防毒軟體的排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 掃描 | 指定每天執行快速掃描的間隔 | [設定 Microsoft Defender 防毒軟體的排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 掃描 | 指定用於排程掃描的掃描類型 | [設定 Microsoft Defender 防毒軟體的排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 掃描 | 指定每日快速掃描的時間 | [設定 Microsoft Defender 防毒軟體的排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 掃描 | 指定一天中執行排程掃描的時間 | [設定 Microsoft Defender 防毒軟體的排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 掃描 | 僅當電腦已開啟但未在使用中時啟動排程掃描 | [設定 Microsoft Defender 防毒軟體的排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 允許來自 Microsoft Update 的安全性智慧更新 | [管理行動裝置和虛擬機器 (VM) 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 使用電池電源時，允許安全性智慧更新 | [管理行動裝置和虛擬機器 (VM) 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 允許通知以停用 Microsoft MAPS 的定義型報告 | [管理事件型強制更新](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 允許以 Microsoft MAPS 報告為基礎的即時安全性智慧更新 | [管理事件型強制更新](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 在啟動時檢查最新的病毒和間諜軟體定義 | [管理事件型強制更新](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 定義下載安全性智慧更新的檔案共用 | [管理 Microsoft Defender 防毒軟體保護和安全性智慧更新](manage-protection-updates-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 定義需要追趕安全情報更新的天數 | [管理已過期端點的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 定義間諜軟體定義視為過期的天數 | [管理已過期端點的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 定義病毒定義視為過期的天數 | [管理已過期端點的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 定義下載安全性智慧更新的來源順序 | [管理 Microsoft Defender 防毒軟體保護和安全性智慧更新](manage-protection-updates-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 啟動時啟動安全性智慧更新 | [管理事件型強制更新](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 指定一周中檢查安全性智慧更新的星期幾 | [管理應下載及套用防護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 指定檢查安全性智慧更新的間隔 | [管理應下載及套用防護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 指定檢查安全性智慧更新的時間 | [管理應下載及套用防護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| 安全性智慧更新 | 在安全性智慧更新後開啟掃描 | [設定 Microsoft Defender 防毒軟體的排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 威脅 | 指定偵測到預設動作時不應該採取的威脅警示層級 | [設定 Microsoft Defender 防毒軟體掃描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 威脅 | 指定當偵測到預設動作時不應該採取的威脅 | [設定 Microsoft Defender 防毒軟體掃描的修正](configure-remediation-microsoft-defender-antivirus.md) |

## <a name="see-also"></a>請參閱

- [管理及設定工具的參考主題](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
