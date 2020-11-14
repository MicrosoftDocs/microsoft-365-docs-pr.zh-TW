---
title: 深入瞭解可訓練分類器（預覽版）
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 trainable 分類器是一種工具，可讓您訓練以辨識各種類型的內容，方法是將它肯定和否定的範例，以查看。 在訓練分類器之後，請確認其結果是否正確。 然後，您可以使用它來搜尋組織的內容，並將其分類，以套用保留或敏感度標籤，或將其包含在資料遺失防護 (DLP) 或保留原則。
ms.openlocfilehash: d26e33efea09c2afb33c2b5e5ade264cb8bfaee6
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2020
ms.locfileid: "49072942"
---
# <a name="learn-about-classifiers-preview"></a>瞭解 (預覽的分類器) 

分類及標示內容，使其能受到保護和正確處理，是資訊保護訓練科目的開始位置。 Microsoft 365 有三種方式可對內容進行分類。

## <a name="manually"></a>手動

此方法需要人工判斷和動作。 系統管理員可以使用預先存在的標籤和敏感資訊類型，或自行建立，然後加以發佈。 使用者和系統管理員會在遇到時，將其套用至內容。 然後您就可以保護內容並管理其部署。

## <a name="automated-pattern-matching"></a>自動模式對應

這種分類機制類別包括尋找內容的方式如下：

- 關鍵字或中繼資料值 (關鍵字查詢語言) 。
- 使用先前識別的敏感資訊模式，例如社會保險、信用卡或銀行帳戶號碼 [ (敏感資訊類型實體定義) ](sensitive-information-type-entity-definitions.md)。
- 識別專案，因為它是範本的變化 (的 [ 檔指紋列印) ](document-fingerprinting.md)。
- 使用完全字串的目前狀態 [ (完全相符的資料) ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。

敏感度和保留標籤可以自動套用，讓內容可用於 [資料遺失防護 (DLP) ](data-loss-prevention-policies.md) 和 [自動套用保留標籤](apply-retention-labels-automatically.md)的原則。

## <a name="classifiers"></a>分類

這種分類方法特別適合無法透過手動或自動模式相符方法輕易識別的內容。 這種分類方法更詳細地訓練分類器，以根據專案 (模式相符) 中的元素來識別專案。 分類器透過查看您要分類之內容的數百個範例，瞭解如何識別內容類型。 您可以在類別中進一步送入明確的範例。 一旦處理這些程式，您可以讓它混合使用比對和不相符的範例。 分類器接著會作出預測，以判斷是否有任何指定的專案屬於您所建立的類別。 然後，您可以確認其結果、將 true 正值、true 負片、誤報和漏報排序，以提升其預測的準確性。 

當您發佈分類器時，它會在 SharePoint Online、Exchange 及 OneDrive 等位置中排序專案，並將內容分類。 在您發佈分類器之後，您可以繼續使用類似于初始訓練程式的意見反應進行訓練。

### <a name="where-you-can-use-trainable-classifiers"></a>您可以使用 trainable 的分類器
內建的分類器和 trainable 分類器皆可作為[使用靈敏度標籤的 Office autolabeling](apply-sensitivity-label-automatically.md)條件，並根據狀況和[通訊規範](communication-compliance.md)[自動套用保留標籤原則](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)。 

敏感度標籤可以使用分類器做為條件，請參閱 [自動套用敏感度標籤至內容](apply-sensitivity-label-automatically.md)。

> [!IMPORTANT]
> 分類器只會使用未加密及英文的專案。

## <a name="types-of-classifiers"></a>分類器類型

- **預先訓練的分類** 器-Microsoft 已建立並預先訓練許多的分類器，您可以開始使用而不訓練它們。 這些分類器的狀態會顯示為 `Ready to use` 。
- **自訂分類** 器-如果您需要擴充預先訓練的分類器所涵蓋專案以外的分類需求，您可以建立及訓練您自己的分類器。

### <a name="pre-trained-classifiers"></a>預先訓練的分類器

Microsoft 365 隨附五個預先訓練的分類器：

> [!CAUTION]
> 我們正在取代 **冒犯性語言** 的預先訓練分類符，因為它已經產生大量的誤報。 請勿使用它，如果您目前使用它，您應該將商務程式移出它。 建議您改為使用 **威脅** 、 **猥褻** 和 **騷擾** 預先訓練的分類器。

- **簡歷** ：偵測屬於申請人個人、教育、專業資格、工作經驗及其他個人識別資訊的文字帳戶的專案
- **原始程式碼** ：偵測包含一組指令和語句的專案，這些專案是以前25種使用的電腦程式設計語言所撰寫的 GitHub
    - ActionScript
    - C
    - C#
    - C++
    - Clojure
    - CoffeeScript
    - 移至
    - Haskell
    - JAVA
    - JavaScript
    - Lua
    - Matlab
    - 目標-C
    - Perl
    - Php
    - Python
    - R
    - 紅寶石
    - Scala
    - 命令介面
    - 迅速
    - Tex
    - Vim 腳本

> [!NOTE]
> 原始程式碼經過訓練，可在大量文字是原始程式碼時進行偵測。 它不會偵測到以純文字交錯的原始程式碼文字。

- **騷擾** ：偵測特定類別的冒犯性語言的文字專案，這些專案會根據下列特性，針對一或多個個人設定相關的冒犯性語言：種族、ethnicity、宗教、本國原產地、性別、性方向、年齡、傷殘
- **猥褻** 語言：偵測特定類別的冒犯性語言的文字專案，包含 embarrass 大部分人員的運算式
- **威脅** ：偵測特定類別的冒犯性語言的文字專案與威脅以認可暴力或對人員或財產造成實體損毀或損毀的威脅

這些會出現在 **Microsoft 365 規範中心**  >  **資料分類 (預覽)**  >  **Trainable 的分類** 器視圖中，狀態為 `Ready to use` 。

![分類器-預先訓練的分類器](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 請注意，冒犯性語言、騷擾、猥褻和威脅分類器只會使用可搜尋文字，並非完整或完整。  此外，語言和文化標準也會不斷變更，但在這些現實中，Microsoft 保留以其判斷來更新這些分類器的權利。 雖然分類程式可協助您的組織監控冒犯性和其他語言，但分類程式不會解決這類語言的影響，而且不是為了提供組織的唯一監視或回應這類語言的使用方式。 您的組織，而不是 Microsoft 或其子公司，仍然負責所有與監控、強制執行、封鎖、移除及保留預先訓練的分類器所識別的內容相關的決策。

### <a name="custom-classifiers"></a>自訂分類器

當預先訓練的分類器不符合您的需求時，您可以建立及訓練您自己的分類器。 建立您自己的工作會相當多，但他們會更適合組織的需求。

#### <a name="process-flow-for-creating-custom-classifiers"></a>建立自訂分類程式的程式流程

在此流程中，建立及發行用於規範解決方案（例如保留原則及通訊監督）的分類程式。 如需建立自訂 trainable 分類器的詳細資訊，請參閱 [建立自訂分類器](classifier-get-started-with.md)。

![處理常式流程自訂分類符](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>重新培訓分類器

您可以透過提供其所執行分類的意見反應，協助改善所有自訂分類器和某些預先訓練的分類器的準確性。 這稱為重新培訓，遵循此工作流程。

![分類器重新培訓工作流程](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>請參閱

- [保留標籤](retention.md)
- [資料外洩防護 (DLP)](data-loss-prevention-policies.md)
- [敏感性標籤](sensitivity-labels.md)
- [敏感性資訊類型實體定義](sensitive-information-type-entity-definitions.md)
- [檔指紋列印](document-fingerprinting.md)
- [完全相符的資料](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
