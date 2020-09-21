---
title: '如何重新培訓內容瀏覽器中的分類器 (預覽) '
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 瞭解如何在內容瀏覽器中提供對 trainable 分類器的意見反應。
ms.openlocfilehash: 0fbce595894cbbf2a017fc1bf657b14a5b812e29
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132308"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a>如何重新培訓內容瀏覽器中的分類器 (預覽) 

Microsoft 365 trainable 分類器是一種工具，可讓您訓練以辨識各種類型的內容，其範例可供您查看。 經過訓練之後，您可以使用它來識別應用 Office 敏感度標籤、通訊合規性原則及保留標籤原則的專案。

本文說明如何透過提供額外的意見反應，以改善自訂 trainable 分類器和部分預先訓練的分類器的效能。

若要深入瞭解不同類型的分類器，請參閱 [瞭解如何 trainable 的分類器 (預覽) ](classifier-learn-about.md)。

## <a name="permissions"></a>權限

若要在 Microsoft 365 規範中心存取分類器：

- 合規性管理員角色或符合性資料管理員是訓練分類器所需的

在下列情況下，您將需要具有這些許可權的帳戶才能使用分類器：

- 保留標籤原則案例：記錄管理和保留管理角色 

## <a name="overall-workflow"></a>整體工作流程

> [!IMPORTANT]
> 您可以在內容瀏覽器中為自動套用保留標籤原則提供反應，以進行 Exchange 專案，並使用分類器做為條件。 **如果您沒有保留原則可將保留標籤自動套用至 Exchange 專案，並使用分類器做為條件，請停止這裡。**

當您使用分類器時，您可能會想要增加所進行之分類的精確度。 為此，您需要評估其所識別為符合或不符合專案之專案的分類品質。 在您對分類器進行30個評估之後，就會使用該意見反應，並自動 retrains 自身。

若要深入瞭解重新培訓分類器的整體工作流程，請參閱 [用於重新培訓分類器的處理](classifier-learn-about.md#retraining-classifiers)流程。

> [!NOTE]
> 分類器必須已發佈且在使用之前才能 retrained。

## <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a>如何重新培訓內容瀏覽器中的分類器 (預覽) 

1. 使用合規性管理員或安全性系統管理員角色存取權登入 microsoft 365 合規性中心，並開啟**microsoft 365 規範中心**  >  **資料分類**  >  **內容瀏覽器**。 
2. 在 [ **標籤、資訊類型] 或 [類別** ] 清單中的 [篩選] 底下，展開 [ **Trainable**類別]。

> [!IMPORTANT]
> 匯總專案最多可以花八天，顯示在 trainable 的分類器標題下。

3. 選擇您在自動套用保留標籤原則中使用的 trainable 分類器。 這是您將提供意見反應的 trainable 分類器。

> [!NOTE]
> 如果專案的 [ **保留標籤** ] 欄中有專案，則表示專案已分類為 `match` 。  如果專案沒有 [ **保留標籤** ] 欄中的專案，表示它是分類為 `close match` 。 您可以提供專案的意見反應，以提升最大分類器的精確度 `close match` 。 

4. 選擇一個專案，然後開啟它。
 
 > [!TIP]
> 您可以同時提供多個專案的意見反應，方法是全部選擇，然後選擇 [改進命令列中的 **分類** ]。

5. 選擇 [ **提供意見**反應]。
6. 在 [ **詳細意見** 反應] 窗格中，如果專案為 true，請選擇 [ **符合**]。  如果專案是誤報，表示它不正確地包含在類別中，請選擇 [ **不相符**]。
7. 如果有其他的分類器更適合該專案，您可以從 [ **建議其他 trainable** 系系] 清單中加以選擇。 這會觸發其他分類器來評估專案。
8. 選擇 [ **傳送意見** 反應] 以傳送您的評價 `match` 、 `not a match` 分類及建議其他 trainable 的分類程式。 當您向分類器提供30個反應實例時，它會自動重新導流。 重新培訓可能需要一到四個小時的時間。 分類器每日只能有兩次 retrained。

> [!IMPORTANT]
> 此資訊會前往您租使用者中的分類器， **不會傳回 Microsoft**。

9. 開啟 **Trainable 的分類 (預覽) **。
10. 通訊合規性原則中使用的分類程式會出現在 [ **重新訓練** ] 標題下。

![以重新培訓狀態分類的分類器](../media/classifier-retraining.png)

11. 重新培訓完成後，請選擇分類器以開啟 [重新培訓一覽表]。

![分類器重新培訓結果概述](../media/classifier-retraining-overview.png)

12. 查看建議的動作，以及 retrained 及目前發佈之版本的分類器的預測比較。
13. 如果您已滿意重新培訓的結果，請選擇 [ **重新發佈**]。
14. 如果您不滿意重新培訓的結果，您可以選擇在通訊規範介面中為分類器提供額外的意見反應，並開始另一種重新培訓週期; 或者，在這種情況下，將繼續使用分類器目前發行的版本。 

## <a name="details-on-republishing-recommendations"></a>重新發佈建議的詳細資料

以下是關於如何提出建議以重新發佈 retrained 分類器或建議進一步重新培訓的詳細資訊。 這需要稍微深入瞭解 trainable 的分類器的運作方式。

在重新導流之後，我們會使用意見反應，以及原來用於訓練分類器的任何專案，來評估分類程式的效能。 

- 針對內建模型，用來訓練分類器的專案是 Microsoft 用來建立模型的專案。
- 針對自訂模型，在原始訓練中使用的專案分類器來自您已新增以進行測試及檢查的網站。

我們比較 retrained 和發行的分類器之兩組專案的效能值，以提供是否有改進重新發佈的建議。 

## <a name="see-also"></a>另請參閱

- [深入瞭解 trainable 的分類器 (預覽) ](classifier-learn-about.md)
- [SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
