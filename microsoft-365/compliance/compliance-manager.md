---
title: Microsoft 合規性管理員
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合規性管理員可協助組織簡化及自動化風險評估，並建議採取的措施以協助解決風險。
ms.openlocfilehash: 7bff6a2a7a150a08b98fe7a92cd71d266df9fda7
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376544"
---
# <a name="microsoft-compliance-manager"></a>Microsoft 合規性管理員

**本文內容：** 瞭解合規性管理員是什麼，它如何協助簡化法規遵從性及降低風險，以及其重要元件。

## <a name="whats-new-the-ga-release-of-compliance-manager"></a>新功能：相容性管理員的公開發行版

合規性管理員現在已 (GA) 成為 [Microsoft 365 規範中心](microsoft-365-compliance-center.md)內的端對端規範管理解決方案。 在此版本中，合規性管理員會從 Microsoft 服務信任入口網站中的先前位置轉換。 合規性管理員現在也可供美國政府社區 (GCC) 適中和 GCC 高的客戶。

公開的合規性分數的公開預覽已演變成集中式工具，其具有增強的合規性管理功能和更輕鬆使用。  GA 發行版本提供了更大的預先構建評估集合，可協助您擴大合規性活動。

**深入瞭解 GA 版本：**
- 我們的 [常見問題](compliance-manager-faq.md) 會逐步引導您深入瞭解演變。
- 閱讀 [此博客文章](https://aka.ms/compliancemanager/GAblog)中的 GA 功能增強功能。

觀看下列影片，瞭解合規性管理員如何協助簡化組織管理規範的方式：
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a>何謂合規性管理員

[Microsoft 合規性管理員](https://compliance.microsoft.com/compliancemanager) 是 [microsoft 365 規範中心](microsoft-365-compliance-center.md) 中的一項功能，可協助您管理組織的合規性需求，以提高便利性和便利性。 合規性管理員可以協助您整個規範旅程，從清查您的資料保護風險到管理實施控制措施的複雜性、保持目前與法規和憑證的複雜性，以及向審計員報告。

合規性管理員提供下列功能，協助簡化法規遵從性並降低風險：

- 適用于一般行業和地區性標準及法規的預先建評估，或自訂評估以符合您的獨特法規遵從性需求 (可用評估取決於您的授權合約; [深入瞭解](https://go.microsoft.com/fwlink/?linkid=2132371)) 。

- 工作流程功能，可協助您透過單一工具有效率地完成風險評估。

- 詳細的逐步指導方針，可協助您遵循組織最相關的標準及規定。 針對 Microsoft 所管理的動作，您將會看到「執行詳細資料」和「審計結果」。

- 以風險為基礎的符合性分數，可協助您瞭解符合性狀況，方法是測量您完成改進動作的進度。

您的合規性管理員儀表板會顯示您目前的合規性分數，協助您瞭解需要注意的事項，並引導您進行重要改進動作。 以下是合規性管理員儀表板外觀的範例：

![合規性管理員-儀表板](../media/compliance-manager-dashboard.png "合規性管理員儀表板")

## <a name="understanding-your-compliance-score"></a>瞭解您的合規性分數

合規性管理員獎項您是為了完成遵循法規、標準或原則所採取的改進動作，並將這些點數結合為整體合規性分數。 每個動作對您的分數有不同的影響，取決於可能的風險。 您的合規性分數可協助您決定關注的動作，以改善您的整體相容性狀況。

合規性管理員為您提供根據 Microsoft 365 資料保護基準的初始分數。 此基準是一組控制項，包含資料保護和一般資料控管的重要規章和標準。

##### <a name="learn-more"></a>深入了解

[瞭解如何計算您的合規性分數](compliance-score-calculation.md)。

[瞭解如何使用 [改進] 動作](compliance-manager-improvement-actions.md)。

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>主要元素：控制項、評估、範本、改進動作

合規性管理員使用多個資料元素，協助您管理相容性活動。 當您使用合規性管理員指派、測試及監視合規性活動時，讓基本瞭解主要元素非常有用： controls、評估、範本及改進動作。

### <a name="controls"></a>控制項

控制項是法規、標準或原則的必要條件。 它會定義如何評估和管理系統設定、組織處理常式，以及負責滿足法規、標準或原則的特定需求的人員。

合規性管理員會追蹤下列類型的控制項：

1. **Microsoft managed controls**： microsoft 雲端服務的控制項，microsoft 負責執行這種服務
2. **您的控制項**：有時候稱為客戶管理控制項，這些是由您的組織所實施及管理的控制項。
3. **共用控制項**：這些是您的組織和 Microsoft 共同共同執行的控制措施

##### <a name="learn-more"></a>深入了解

[監視控制項的進度](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)。

[深入瞭解合規性管理員如何持續評估控制項](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)。

### <a name="assessments"></a>評估

評估是指來自特定法規、標準或原則的控制項群組。 完成評估內的動作可協助您符合標準、法規或法律的需求。 例如，您可能會有一個評估，當您完成其中的所有動作時，可協助您將 Microsoft 365 設定放入符合 ISO 27001 的需求。

評估包含數個元件：

- **範圍內的服務**：適用于評估的特定 Microsoft 服務集合
- **Microsoft managed controls**： microsoft 雲端服務的控制項，microsoft 代表您執行的動作
- **您的控制項**：有時候稱為客戶管理控制項，這些是由您的組織所實施及管理的控制項。
- **共用控制項**：這些是您的組織和 Microsoft 共同共同執行的控制措施
- **評估分數**：顯示從評估中的動作到您的組織及 Microsoft 所管理的所有可能分數的進度

在建立評估時，您會將其指派給群組。 您可以以組織最具邏輯的任何方式來設定群組。 例如，您可以透過審計年、地區、解決方案、組織內的小組或其他方式來群組評估。 一旦您建立群組，您就可以 [篩選合規性管理員儀表板](compliance-manager-setup.md#filtering-your-dashboard-view) ，以查看一或多個群組的分數。

##### <a name="learn-more"></a>深入了解

[在合規性管理員中建立及管理評估](compliance-manager-assessments.md)。

### <a name="templates"></a>範本

合規性管理員提供範本，協助您快速建立評估。 您可以修改這些範本，以依據您的需求建立評估優化。 您也可以建立具有您自己的控制項和動作的範本，以建立自訂評估。 例如，您可能想要範本涵蓋內部的商務程式控制，或是一個 150 + 預先建立的評估範本未涵蓋的地區性資料保護標準。

##### <a name="learn-more"></a>深入了解

[查看合規性管理員所提供之評估範本的清單](compliance-manager-templates-list.md)。

[取得建立及修改評估範本的詳細指示](compliance-manager-templates.md)。

### <a name="improvement-actions"></a>改進動作

改進的動作有助於集中執行您的合規性活動。 每個改進動作都提供建議的指導方針，以協助您與資料保護法規和標準相符。 您可以將改進動作指派給組織中的使用者，以執行實施和測試工作。 您也可以在改進動作中儲存檔、記事及記錄狀態更新。

##### <a name="learn-more"></a>深入了解

[使用提高的動作來管理您的合規性工作流程](compliance-manager-improvement-actions.md)。

[深入瞭解動作會如何影響您的合規性分數](compliance-score-calculation.md#action-types-and-points)。

## <a name="supported-languages"></a>支援的語言

合規性管理員可以採用下列語言：

- 英文
- Bahasa 印尼
- Bahasa 馬來
- 簡體中文
- 繁體中文
- 捷克文
- 丹麥文
- 荷蘭文
- 芬蘭文
- 法文
- 德文
- 希伯來文
- 匈牙利文
- 義大利文
- 日文
- 韓文
- 挪威文
- 波蘭文
- 葡萄牙文 (巴西) 
- 俄文
- 西班牙文
- 瑞典文
- 泰文
- 土耳其文

## <a name="next-steps-set-up-and-customize"></a>後續步驟：設定和自訂

瞭解如何登入、指派許可權和角色、設定設定，以及在 [開始使用合規性管理員](compliance-manager-setup.md)時個人化儀表板視圖。

然後開始自訂合規性管理員，以協助您遵循對組織最重要的行業標準， [設定評估](compliance-manager-assessments.md)。