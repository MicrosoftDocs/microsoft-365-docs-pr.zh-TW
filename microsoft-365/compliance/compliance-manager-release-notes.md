---
title: Microsoft 合規性管理員版本資訊
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合規性管理員是 Microsoft 服務信任入口網站中免費的工作流程型風險評估工具。 合規性管理員可讓您追蹤、指派及驗證與 Microsoft 雲端服務相關的法規遵從性活動。
ms.openlocfilehash: 3fc16e92e912676d7aedc861ffe8306d68388c95
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42635141"
---
# <a name="release-notes-for-compliance-manager-preview"></a>合規性管理員的版本附注（預覽）

合規性管理員的公開預覽可讓您及早存取即將推出的功能和更新。

您可以在[服務信任入口網站](https://servicetrust.microsoft.com)上使用更新的[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)工具，以追蹤、指派及驗證與 Microsoft 雲端服務相關的法規遵從性活動。

## <a name="whats-new-in-compliance-manager-preview"></a>合規性管理員的新功能（預覽）

- **以角色為基礎的訪問合規性管理員：** 已移除預設**來賓存取**角色。 若要讓使用者存取合規性管理員，全域管理員必須[將許可權指派給每位使用者](compliance-manager-overview.md#permissions)。

- **更新的合規性分數**：符合性分數現在包括 Microsoft 管理的動作分數。 結果會使您的分數增加。

- **Actions 專案：** 動作專案現在是個別專案，許多包括來自 Microsoft 安全分數圖形 API 的遙測集合。 您可以盡可能使用技術動作建議，以連結至 Office 365 服務中適用的設定頁面。

- **承租人管理：** 在合規性管理員中管理新資料元素的新介面（預覽）：
    - **維度：** View、新增及自訂範本、評估和動作專案的中繼資料，可讓您建立自訂的篩選器。
    - **擁有者：** 指定每個即席專案的擁有者。
    - **客戶動作：** 管理合規性管理員（預覽）中包含的完整動作專案清單，並啟用/停用以安全得分整合之動作專案的安全評分監控。

## <a name="known-issues-in-compliance-manager-preview"></a>合規性管理員中的已知問題（預覽）

下列各節涵蓋合規性管理員即將推出的版本中解決的已知問題。

### <a name="compliance-score"></a>合規性分數

- 對於標示為**Not In 範圍**的動作專案，指派給交辦事項的分數不會從相容性分數計算中排除。 標記為**Not In 範圍的**動作專案不會提升您的合規性分數。

### <a name="secure-score"></a>安全分數

- 在某些 Microsoft 365 和 Office 365 訂閱中，有些動作專案無法使用安全分數結果。 在這些情況下，**無法偵測到**安全分數結果。
- 有時候會為對應的原則及未完成的動作專案傳回安全分數結果。
- 針對新承租人，會自動開啟所有動作的安全分數更新。 全域管理員可以將安全計分連續更新切換為 [關閉]，這樣會關閉所有動作的更新。
  - **附注**：當組織第一次部署 Microsoft 365 或 Office 365 時，會花大約7天的時間進行安全的評分，以完全收集資料，並將其劃分為您的分數。 在這段時間內，將安全計分連續更新參數設定為**Off** ，並手動設定所要**執行**的動作，就會將該動作計算為您的分數。 在最初7天后，開啟安全分數連續更新會啟用從該點繼續進行監視。
- 當安全分數更新開啟時，安全分數會積極監控動作，不過動作的測試日期不會更新以反映監控。
- 當建立新的評估時，會自動包含 Microsoft 受管理的控制分數和安全分數整合。
- 安全分數整合不支援的任何動作都可以手動實施。 手動執行將會考慮該動作群組的分數。

### <a name="microsoft-managed-controls"></a>Microsoft 管理的控制項

- Microsoft 管理控制項的測試日期不會出現在 UI 中，甚至會包含在評估中。 若要查看測試日期資訊，您必須匯出評估。

### <a name="customization"></a>自訂

- 新增自訂控制項可將新控制項新增至現有的控制項系列，但不允許您新增新的控制項系列。
- 此版本不支援連結動作專案，或新增動作專案或控制項給評估。
- 如果您建立自訂動作，便無法進行編輯或刪除。

### <a name="control-families-not-shown-in-assessments"></a>控制評估中未顯示的系列

- 當您匯入範本時，以該範本為基礎的所有評估會反映屬於該範本的所有控制系列。 不過，如果您將新的控制項系列新增至範本，任何現有評估將不會反映所做的變更。 只有已更新的範本所建立的新評估會反映這些變更。

### <a name="templates"></a>範本

- 建立範本時，您必須同時包含**產品**和憑證的維度 **，以**確保您的範本會以合規性分數顯示。
- 封存的範本是可編輯的，不應是可編輯的。
- 鎖定的範本允許評估建立。 鎖定範本的目的是為了避免使用它來建立評估。

### <a name="export"></a>匯出

- 當範本的狀態設定為 [匯**入**] 或 [**待處理核准**] 時，範本匯出至 JSON 失敗。

### <a name="supported-browsers"></a>支援的瀏覽器

- 支援最新版本的 Microsoft Edge、Chrome 和 Safari。
- 在您的瀏覽器重新整理之前，可能會出現更新的資料不會出現的情況。
- 不支援預覽版本的 Microsoft Edge，但沒有已知問題。
- 不支援 Internet Explorer。

### <a name="session-timeout"></a>會話超時

- 當會話超時時，可能會出現「發生錯誤」錯誤。 若要解決此問題，請移至 [[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)]，然後再登入。
 
### <a name="language-support"></a>語言支援

- 所有語言都不支援所有的網頁。 如果不支援您的本機語言，請以美國英文查看。
