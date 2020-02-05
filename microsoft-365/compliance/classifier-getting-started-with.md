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
description: Microsoft 365 trainable 類別器是內容的的工具，您可以訓練，讓它正值與負值的範例，來查看辨識各種類型。 類別器調校完成之後，您確認它的結果正確無誤。 然後您可以用它來搜尋整個組織的內容及分類它納入資料外洩防護 (DLP) 或保留原則或套用保留或敏感度標籤。
ms.openlocfilehash: c0ac644f3435d81159156e175c01e1916b0aeaf3
ms.sourcegitcommit: 836bd8135cc49d6db37e78a7cfeb7d2cc4159e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722024"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a>開始使用可訓練的分類器 (預覽)

來分類和標籤內容，以便將其受保護，並適當地處理是的起始位置的資訊保護法則。 Microsoft 365 有三種方法可以將內容分類。

## <a name="manually"></a>手動

此方法需要人工判斷和巨集指令。 系統管理員可能是使用既有的標籤和敏感資訊類型或建立自己並將它們發行。 使用者與系統管理員將其套用至內容為他們發生。 然後可以保護內容，並管理其處理。

## <a name="automated-pattern-matching"></a>自動的模式比對

這個類別的分類機制包括尋找內容：

- 關鍵字或中繼資料值 （關鍵字查詢語言）
- 使用先前識別社會安全、 信用卡或銀行帳戶號碼[（敏感資訊類型）](what-the-sensitive-information-types-look-for.md)相似的敏感資訊的模式
- 辨識項目，因為它是一項變異範本[（文件手指列印）](document-fingerprinting.md)
- 使用管制的確切字串[（符合確切資料）](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。

若要讓內容可供使用中[資料外洩防護 (DLP)](data-loss-prevention-policies.md)和[保留原則](retention-policies.md)可以再是自動套用敏感度和保留標籤。

## <a name="trainable-classifiers"></a>Trainable 相關性

此分類方法是特別適用於不容易辨識，由任一手動或自動模式比對方法的內容。 分類的這個方法是更多關於訓練器來識別哪些項目，不由 （模式比對） 的項目中的項目為基礎的項目。 類別器可學習如何識別類型的內容可以查看數百個內容的範例您感興趣來分類。 您啟動饋送肯定都是類別中的範例。 它會處理那些，一旦您進行測試給予混合的比對和非比對的範例。 類別器接著讓預測想指定的任何項目是否落在類別，您正在建立的。 您然後確認它的結果，其排序出 positive、 負號、 誤判，以協助增進及其預測的正確性漏報中。 當您發佈受過訓練類別器時，它透過像 SharePoint Online、 Exchange 和 OneDrive 的位置中的項目排序，並將內容分類。

> [!IMPORTANT]
> 這兩種相關性可做為[自動套用保留標籤原則式根據條件](labels.md#applying-a-retention-label-automatically-based-on-conditions)和[通訊符合性](communication-compliance.md)條件。

> [!IMPORTANT]
> Trainable 相關性只使用未加密，都會以英文顯示的項目。

### <a name="licensing-requirements"></a>授權需求

Trainable 相關性為 Microsoft 365 E5 或 E5 合規性功能。 您必須有一個進行這些訂閱加以使用。

## <a name="types-of-classifiers"></a>類型的相關性

有已準備好使用相關性和 trainable 相關性。 取得 trainable 類別器可發行狀態需要訓練時間投資。 若要協助您開始使用相關性、 Microsoft 365 隨附一些準備好使用相關性。

> [!NOTE]
> 使用之前任何準備使用分類和標示的工作流程中的類別器，您應測試其對您組織的範例內容您認為符合要確認其分類預測符合您預期的類別。

### <a name="understanding-ready-to-use-classifiers"></a>了解準備好使用相關性

Microsoft 365 隨附六個準備好使用相關性：

- **冒犯**： 偵測到包含 profanities、 slurs、 嘲諷和偽裝的運算式 （也就是具有相同的意義更冒犯性字詞運算式） 的文字項目。
- **履歷表**： 偵測到之應徵者個人、 教育、 專業資格、 工作經驗及其他個人識別資訊的文字帳戶的項目。
- **SourceCode**： 偵測到項目包含一組指示和廣泛使用電腦程式設計語言所撰寫的陳述式。
- **騷擾**： 偵測到特定類別的冒犯的語言文字項目與目標根據下列特性的一或多個個人的不良管理辦法： 競爭、 ethnicity、 宗教、 國家原點、 性別、 性別方向、 保留、 行動不便。
- **褻瀆**： 偵測到特定類別冒犯的語言文字包含的項目讓大多數人的運算式。
- **威脅**： 偵測到特定類別的威脅，從而認可暴力或執行實體損害或損壞的人員或屬性相關的不良的語言文字項目。

這些會出現在**Microsoft 365 合規性中心** > **資料分類 （預覽）** > **Trainable 相關性**檢視狀態的`Ready to use`。

![相關性-準備-要-使用-相關性](media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 請注意冒犯、 騷擾、 褻瀆和威脅相關性只使用可搜尋的文字不詳盡或完整。  此外，語言和文化的標準不斷變更，並根據這些最新資訊，Microsoft 保留來更新其自行斟酌中的這些相關性的權限。 雖然相關性可能會協助您組織中監視冒犯與使用其他語言，相關性沒有解決這種語言的後果，而不提供監視或所使用之回應的貴組織的唯一方法這類的語言。 您的組織，並不 Microsoft 或其子公司，會維持負責監視、 強制執行、 封鎖、 移除和保留的預先受過訓練類別器所識別的所有內容的相關的所有決策。

#### <a name="process-flow-for-using-ready-to-use-classifiers"></a>使用準備好使用相關性的程序流程

若要使用相關性不需要訓練，但您需要確認他們會識別類型的內容，您會需要他們協助您在合規性解決方案中使用它們之前，已準備好。 測試前受過訓練類別器遵循此流程。

![測試前受過訓練類別器的程序流程](media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a>了解 trainable 相關性

當準備好使用相關性不符合您的需求時，您可以建立及訓練您自己的相關性。 沒有建立您自己，所涉及的更多工作，但他們將會更好量身訂做您組織的需求。 如需有關如何使用預先受過訓練類別器的詳細資訊，請參閱[使用準備好使用類別器](classifier-using-a-ready-to-use-classifier.md)

> [!IMPORTANT]
> 只會建立 trainable 類別器使用者可以訓練，並檢閱該類別器所做的預測。

#### <a name="process-flow-for-creating-trainable-classifiers"></a>建立 trainable 相關性的程序流程

建立及發佈使用 trainable 類別器在合規性解決方案，例如保留原則和通訊監督，後面這個的流程。 如需詳細資訊，在建立 trainable 類別器，請參閱[建立 trainable 類別器](classifier-creating-a-trainable-classifier.md)。

![處理程序流程 trainable 類別器](media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a>另請參閱

- [保留標籤](labels.md)
- [保留原則](retention-policies.md)
- [資料外洩防護 (DLP)](data-loss-prevention-policies.md)
- [敏感度標籤](sensitivity-labels.md)
- [敏感資訊類型](what-the-sensitive-information-types-look-for.md)
- [文件手指列印](document-fingerprinting.md)
- [精確資料相符項目](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
