---
title: Microsoft Compliance Manager 版本資訊
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
description: Microsoft Compliance Manager 是在 Microsoft 服務信任入口網站中的可用工作流程為基礎的風險評估工具。 合規性管理員可讓您追蹤、 指派及驗證與 Microsoft 雲端服務相關的法規合規性活動。
ms.openlocfilehash: 1f233a6bc19f4a7afa495f49ad77e39e496c1dc5
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202164"
---
# <a name="release-notes-for-compliance-manager-preview"></a>版本資訊的合規性管理員 （預覽）

公開預覽的合規性管理員為您提供搶先即將推出的功能和更新。

您可以使用[服務信任入口網站](https://servicetrust.microsoft.com)上更新的[合規性管理員](https://servicetrust.microsoft.com/ComplianceManager)」 來追蹤、 指派，並確認與 Microsoft 雲端服務相關的法規合規性活動。

## <a name="whats-new-in-compliance-manager-preview"></a>What's new 合規性管理員中 （預覽）

- **角色型存取合規性管理員：** 已移除預設**的來賓存取**角色。 為了讓使用者存取合規性管理員中，全域系統管理員必須[指派每位使用者的權限](compliance-manager-overview.md#permissions)。

- **更新合規性分數**： 合規性分數現在包含分數的 Microsoft 受管理的動作。 因此會增加您的分數。

- **動作項目：** 動作項目現在的個別項目，而且許多包括來自 Microsoft 安全分數 Graph API 的遙測集合。 請儘可能技術巨集指令建議現在有適用的設定] 頁面上的連結 Office 365 服務中。

- **租用戶管理：** 管理新的資料元素合規性管理員中 （預覽） 的新介面：
    - **維度：** 檢視、 新增並自訂的中繼資料的範本、 評估以及動作項目，可讓您建立自訂的樞紐分析表的篩選器。
    - **擁有者：** 指定每個動作項目擁有者。
    - **客戶動作：** 管理動作項目包含在合規性管理員 （預覽） 的完整清單，並啟用/停用安全分數監控與安全分數整合在一起的動作項目。

## <a name="known-issues-in-compliance-manager-preview"></a>已知的問題合規性管理員中 （預覽）

下列各節討論在即將發行的合規性管理員中解析的已知的問題。

### <a name="compliance-score"></a>合規性分數

- 標示為**不在範圍中**的動作項目，分數指派動作項目不是從合規性分數計算中排除。 標示為**不在範圍中**的動作項目不會增加您的合規性分數。

### <a name="secure-score"></a>安全分數

- 安全分數結果訣不適用於特定 Microsoft 365 和 Office 365 訂閱中的某些動作項目。 安全分數結果是**無法偵測**在這些情況下。
- 有時安全分數結果會傳回對應的原則並不會完成的動作項目。
- 針對新租用戶的所有動作的安全分數更新自動處於開啟狀態。 全域系統管理員可以設定安全分數連續更新切換到關閉，這會關閉的所有動作的更新。
  - **附註**： 當組織第一次部署 Microsoft 365 或 Office 365，它會採用約七天的安全分數 」 來完全收集資料，並因素入您的分數。 在這段時間，將安全分數連續更新參數設定為 [**關閉**，並以手動方式設定為**實作**的 [巨集指令會計算向您的分數該巨集指令。 初始七天之後，開啟安全分數連續更新將會啟用該點之後的持續監視。
- 安全分數更新已開啟時，會主動監視動作可以安全分數，雖然巨集指令的測試日期不會更新以反映監視。
- 當建立新的評估時，分數自動包含 Microsoft 管理控制項分數和安全分數整合。
- 安全分數整合不支援任何動作以手動方式可實作。 手動實作將因素入該巨集指令群組的分數。

### <a name="microsoft-managed-controls"></a>Microsoft 管理控制措施

- Microsoft 管理控制措施的測試日期不會出現在 UI 中，即使納入評估。 若要查看測試日期的詳細資訊，您必須先匯出評估。

### <a name="customization"></a>自訂

- 新增自訂控制項可讓將新的控制項新增至現有的控制項系列，但不允許您將新增新的控制項系列。
- 此版本不支援連結動作項目新增動作項目或評估控制項。
- 如果您建立的自訂動作，您無法編輯或刪除它。

### <a name="control-families-not-shown-in-assessments"></a>不會顯示在 「 評估 」 控制項系列

- 當您匯入範本時，該範本為基礎的所有評定都反映是範本的一部份的所有控制項系列。 但是，如果您新增至範本的新控制項系列，任何現有 「 評估 」 不會反映所做的變更。 僅限關閉更新的範本建立新的評估會反映所做的變更。

### <a name="templates"></a>範本

- 在建立範本時，您必須包含維度這兩個**產品**和**憑證**以確保您的範本會顯示在 [合規性分數。
- 封存的範本可編輯，而且它們不應該是可編輯。
- 當他們不應該評估建立允許鎖定的範本。 鎖定範本是用來防止其被用來建立評估。

### <a name="export"></a>匯出

- 範本匯出至 JSON 失敗時的範本狀態設為**匯入**或**擱置中的核准**。

### <a name="supported-browsers"></a>支援的瀏覽器

- 支援最新版的 Microsoft Edge、 Chrome 和 Safari。
- 可能會有更新的資料不會在重新整理瀏覽器直到出現的執行個體。
- Microsoft Edge 的預覽版本不支援，但有任何已知的問題。
- 不支援 Internet Explorer。

### <a name="session-timeout"></a>工作階段逾時

- 當工作階段逾時，可能會出現 「 發生錯誤 」 錯誤。 若要解決，移至[合規性管理員中](https://servicetrust.microsoft.com/ComplianceManager)，並再次登入。
 
### <a name="language-support"></a>語言支援

- 所有語言都不支援所有的網頁。 如果您當地語言不受支援，在美式英文的檢視。