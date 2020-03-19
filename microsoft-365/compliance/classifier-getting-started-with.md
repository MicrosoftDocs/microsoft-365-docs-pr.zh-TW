---
title: 開始使用可訓練的分類器 (預覽)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 trainable 分類器是一種工具，可讓您訓練以辨識各種類型的內容，方法是將它肯定和否定的範例，以查看。 在訓練分類器之後，請確認其結果是否正確。 然後，您可以使用它來搜尋組織的內容，並將其分類，以套用保留或敏感度標籤，或將其包含在資料遺失防護（DLP）或保留原則中。
ms.openlocfilehash: 6706fe25194191d57ffd91f07f13d22fe5ec6cfd
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826254"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a>開始使用可訓練的分類器 (預覽)

分類及標示內容，使其能受到保護和正確處理，是資訊保護訓練科目的開始位置。 Microsoft 365 有三種方式可對內容進行分類。

## <a name="manually"></a>手動

此方法需要人工判斷和動作。 系統管理員可以使用預先存在的標籤和敏感資訊類型，或自行建立，然後加以發佈。 使用者和系統管理員會在遇到時，將其套用至內容。 然後您就可以保護內容並管理其部署。

## <a name="automated-pattern-matching"></a>自動模式對應

這種分類機制類別包括尋找內容的方式：

- 關鍵字或中繼資料值（關鍵字查詢語言）
- 使用先前識別的敏感資訊模式，如社會保險、信用卡或銀行帳戶號碼[（敏感資訊類型）](what-the-sensitive-information-types-look-for.md)
- 識別專案，因為它是範本的變化[（檔指紋列印）](document-fingerprinting.md)
- 使用完全字串的狀態[（完全符合資料）](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。 '

然後，您可以自動套用敏感度和保留標籤，讓內容可用於[資料遺失防護（DLP）](data-loss-prevention-policies.md)和[保留原則](retention-policies.md)。

## <a name="trainable-classifiers"></a>Trainable 分類器

這種分類方法特別適合無法透過手動或自動模式相符方法輕易識別的內容。 這種分類方法更詳細地訓練分類器，以根據專案的專案，而不是專案中的元素（模式對應）來識別專案。 分類器透過查看您要分類之內容的數百個範例，瞭解如何識別內容類型。 您可以在類別中進一步送入明確的範例。 一旦處理這些程式，您可以讓它混合使用比對和不相符的範例。 分類器接著會作出預測，以判斷是否有任何指定的專案屬於您所建立的類別。 然後，您可以確認其結果、將正值、負、誤報和 false 的否定排序，以提升預測的準確性。 當您發佈訓練的分類器時，它會在 SharePoint Online、Exchange 及 OneDrive 等位置中排序專案，並將內容分類。

> [!IMPORTANT]
> 內建的分類器和 trainable 分類器皆為根據條件和[通訊相容性](communication-compliance.md)[自動套用保留標籤原則](labels.md#applying-a-retention-label-automatically-based-on-conditions)的條件。 敏感度標籤只能使用內建的分類器作為條件，請參閱[自動將敏感度標籤套用至內容](apply-sensitivity-label-automatically.md)。

> [!IMPORTANT]
> Trainable 的分類程式只會使用未加密及英文的專案。

### <a name="licensing-requirements"></a>授權需求

Trainable 分類器是 Microsoft 365 E5 或 E5 規範功能。 您必須具有這些訂閱中的其中一項，才能使用這些訂閱。

## <a name="types-of-classifiers"></a>分類器類型

有內建的分類器和 trainable 的分類器。 若要讓 trainable 分類器成為可發佈的狀態，需要花費時間投資進行訓練。 為了協助您開始使用類元，Microsoft 365 附帶一些內建的分類符。

> [!NOTE]
> 在您的分類和標籤工作流程中使用任何內建的分類器之前，您應該針對您想要的組織內容範例進行測試，以確認該類別的分類預測符合您的預期。

### <a name="understanding-built-in-classifiers"></a>瞭解內建的分類器

Microsoft 365 隨附六個內建的分類器：

- **冒犯性語言**：偵測包含 profanities、slurs、taunts 及偽裝運算式（也就是具有更具冒犯性字詞之意義的運算式）的文字專案。
- **簡歷**：偵測屬於申請人個人、教育、專業資格、工作經驗及其他個人識別資訊的文字帳戶的專案。
- **原始程式碼**：偵測包含一組指令和語句的專案，這些專案是以前25種使用電腦程式設計語言的 GitHub 上所撰寫。

|語言名稱|||||
|---------|---------|---------|---------|---------|
|ActionScript|C        |C#       |C++     |Clojure  |
|CoffeeScript|Css     |移至       |Haskell |HTML     |
|JAVA     |JavaScript|Lua      |Matlab   |目標-C|
|Perl     |Php      |Python   |R        |紅寶石     |
|Scala    |命令介面    |迅速    |Tex      |Vim 腳本|


- **騷擾**：偵測特定類別的冒犯性語言的文字專案，這些專案會根據下列特性，偵測一或多個個人：種族、ethnicity、宗教、全國原始、性別、性方向、年齡、傷殘等相關的攻擊性設定。
- **猥褻**語言：偵測特定類別的冒犯性語言文字專案，包含 embarrass 大部分人員的運算式。
- **威脅**：偵測特定類別的冒犯性語言的文字專案與威脅，以認可暴力或對人員或財產造成實體損毀或損毀。

這些會出現在**Microsoft 365 規範中心** > **資料分類（預覽）** > **Trainable 的分類**器視圖中， `Ready to use`狀態為。

![分類器-可供使用-分類器](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 請注意，冒犯性語言、騷擾、猥褻和威脅分類器只會使用可搜尋文字，並非完整或完整。  此外，語言和文化標準也會不斷變更，但在這些現實中，Microsoft 保留以其判斷來更新這些分類器的權利。 雖然分類程式可協助您的組織監控冒犯性及其他使用的語言，但是分類程式不會解決這類語言的影響，而且不是為了提供組織的唯一監視或回應使用的方式這類語言。 您的組織，而不是 Microsoft 或其子公司，仍然負責所有與監控、強制執行、封鎖、移除及保留預先訓練的分類器所識別的內容相關的決策。

#### <a name="process-flow-for-using-built-in-classifiers"></a>使用內建分類器的處理流程

內建的分類器不需要經過訓練，但是您必須先確認他們會識別您需要的內容類型，才可在規範方案中使用它們。 測試預先訓練的分類器遵循此流程。

![處理預先訓練的分類器的程式流程測試](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a>瞭解 trainable 的分類器

當內建的分類器不符合您的需求時，您可以建立及訓練您自己的分類器。 建立您自己的工作會相當多，但他們會更適合組織的需求。 如需如何使用預先訓練的分類器的詳細資訊，請參閱[使用內建的分類器](classifier-using-a-ready-to-use-classifier.md)

> [!IMPORTANT]
> 只有建立 trainable 分類器的使用者可以訓練及審核該分類器所做的預測。

#### <a name="process-flow-for-creating-trainable-classifiers"></a>建立 trainable 的分類程式流程

建立及發佈用於規範解決方案（如保留原則及通訊監督）的 trainable 分類程式，遵循此流程。 如需建立 trainable 分類器的詳細資訊，請參閱[建立 trainable 的分類器](classifier-creating-a-trainable-classifier.md)。

![處理流程 trainable 分類器](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a>另請參閱

- [保留標籤](labels.md)
- [保留原則](retention-policies.md)
- [資料遺失防護（DLP）](data-loss-prevention-policies.md)
- [敏感度標籤](sensitivity-labels.md)
- [敏感資訊類型](what-the-sensitive-information-types-look-for.md)
- [檔指紋列印](document-fingerprinting.md)
- [完全相符的資料](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
