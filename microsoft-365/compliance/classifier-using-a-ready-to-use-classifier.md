---
title: 使用內建的分類器（預覽）
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
description: Microsoft 365 隨附許多內建的分類符，您可以用來識別及標記整個組織中的內容。 本主題將告訴您如何準備使用這些分類器。
ms.openlocfilehash: 2157e06da251b1f02b6a4623c573d350d838aff0
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634461"
---
# <a name="using-a-built-in-classifier-preview"></a>使用內建的分類器（預覽）

Microsoft 已使用極大的範例資料集訓練及測試了許多分類器，可協助識別特定的內容類別別。 請參閱[trainable 類元的快速入門（預覽）](classifier-getting-started-with.md)。 這些分類器預設會顯示`Ready to use`在群組中。

- **冒犯性語言**：偵測包含 profanities、slurs、taunts 及偽裝運算式（也就是具有更具冒犯性字詞之意義的運算式）的文字專案。
- **簡歷**：偵測屬於申請人個人、教育、專業資格、工作經驗及其他個人識別資訊的文字帳戶的專案。
- **SourceCode**：偵測包含一組廣泛使用電腦程式設計語言所撰寫的指令和語句的專案。
- **騷擾**：偵測特定類別的冒犯性語言的文字專案，這些專案會根據下列特性，偵測一或多個個人：種族、ethnicity、宗教、全國原始、性別、性方向、年齡、傷殘等相關的攻擊性設定。
- **猥褻**語言：偵測特定類別的冒犯性語言文字專案，包含 embarrass 大部分人員的運算式。
- **威脅**：偵測特定類別的冒犯性語言的文字專案與威脅，以認可暴力或對人員或財產造成實體損毀或損毀。

> [!NOTE]
> 在您的分類和標籤工作流程中使用內建的分類器之前，您應該針對組織內容的範例進行測試，以確認類別的分類預測符合您的預期。

> [!IMPORTANT]
> 請注意，冒犯性語言、騷擾、猥褻和威脅分類器只會使用可搜尋文字，並非完整或完整。 此外，語言和文化標準也會不斷變更，但在這些現實中，Microsoft 保留以其判斷來更新這些分類器的權利。 雖然分類程式可協助您的組織監控冒犯性及其他使用的語言，但是分類程式不會解決這類語言的影響，而且不是為了提供組織的唯一監視或回應使用的方式這類語言。 您的組織，而不是 Microsoft 或其子公司，仍然負責所有與監控、強制執行、封鎖、移除及保留預先訓練的分類器所識別的內容相關的決策。

## <a name="how-to-prepare-for-and-use-a-built-in-classifier"></a>如何準備及使用內建的分類器

1. 收集您認為屬於內建分類器（肯定比對）類別的可處置內容專案，以及您要測試之類別中不應該包含的專案（負數相符）。

> [!IMPORTANT]
> 範例專案不能加密，必須是英文。

2. 建立專用的 SharePoint 線上資料夾;至少等候一個小時的資料夾新增至搜尋索引。 請記下資料夾 URL。

3. 使用合規性管理員或安全性系統管理員角色存取，登入 microsoft 365 合規性中心，並開啟**microsoft 365 規範中心** > **記錄管理（預覽）** > **標籤原則] 索引標籤**。

4. 選擇`Auto-apply a label`。

5. 選擇`Choose a label to auto-apply`。

6. 選擇`Create new labels`並建立標籤，以用於此測試。 當您執行此動作時`Retention` ，請將設定為 [關閉]。 您不想開啟任何保留或其他動作。 在此情況下，您只會使用保留標籤做為文字標籤，而不會強制執行任何動作。 例如，您可以建立一個名為 "SourceCode 分類程式 test" 的保留標籤，但不會執行任何動作，然後將該保留標籤自動套用至來原始程式碼分類器為條件的內容。 若要深入瞭解建立保留標籤的詳細資訊，請參閱[保留標籤簡介](labels.md)。
  
7. 選擇`Auto-apply a label` [和`Choose a label to auto-apply`]。 若要深入瞭解使用條件自動套用標籤的詳細資訊，請參閱，[根據條件自動套用保留標籤原則](labels.md#applying-a-retention-label-automatically-based-on-conditions)。

8. 從清單中選擇您的測試卷標`Next`，然後選擇 [。

9. 選擇`Apply label to content that matches a trainable classifier`。

![選取分類器做為條件](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png).

10. 在此情況下，從清單中選擇您的分類器`Source Code`

11. 命名原則，例如「原始程式碼內建的分類程式測試」。

12. 選擇`Let me choose specific locations`。

13. 關閉除及選擇`SharePoint sites` `Choose sites`以外的所有位置。

14. 輸入步驟2中之網站的 URL。

15. 完成該嚮導並選擇`Auto-apply`

16. 將測試專案放入專用的 SharePoint 線上資料夾中。

17. 允許套用標籤的小時數。

18. 檢查標籤的檔內容，查看是否有分類程式包含與您預期的測試內容。

19. 查看已標示的專案。

20. 如果您已經完成測試，請刪除內容和標籤原則。

另請參閱：

- [開始使用可訓練的分類器 (預覽)](classifier-getting-started-with.md)
- [保留標籤概觀](labels.md)
- [根據條件自動套用保留標籤原則](labels.md#applying-a-retention-label-automatically-based-on-conditions)
