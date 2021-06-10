---
title: 開始使用可訓練分類器
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
description: Microsoft 365 分類器是一種工具，可讓您訓練以辨識各種類型的內容，其範例可供您查看。 本文說明如何建立及訓練自訂的分類器，以及如何重新導流以提高精確度。
ms.openlocfilehash: 90e47ec94528bbadeb98dc9eb590929e25ae6ff1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918177"
---
# <a name="get-started-with-trainable-classifiers"></a>開始使用可訓練分類器

Microsoft 365 trainable 分類器是一種工具，可讓您訓練以辨識各種類型的內容，其範例可供您查看。 經過訓練之後，您可以使用它來識別 Office 敏感度標籤、通訊規範原則及保留標籤原則的應用程式專案。

建立自訂的 trainable 分類器優先于提供以人工方式挑選並正確符合類別的範例。 然後，在處理完這類功能之後，您可以透過提供正負樣本的混合來測試分類器的預測能力。 本文說明如何建立及訓練自訂的分類器，以及如何透過重新培訓，改善自訂 trainable 分類器和預先訓練的分類器的效能。

若要深入瞭解不同類型的分類器，請參閱 [瞭解如何 trainable 的分類](classifier-learn-about.md)器。

觀賞這段影片，以快速瞭解如何建立 trainable 的分類器。 您仍然需要閱讀本文的完整文章，以取得詳細資料。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a>必要條件

### <a name="licensing-requirements"></a>授權需求

分類器是 Microsoft 365 E5 或 E5 規範功能。 您必須具有這些訂閱中的其中一項，才能使用這些訂閱。

### <a name="permissions"></a>權限

在 UI 中存取分類器： 

- 全域管理員必須加入宣告租使用者，才能建立自訂分類符。
- 訓練分類器需要合規性系統管理員角色。

在下列情況下，您將需要具有這些許可權的帳戶才能使用分類器：

- 保留標籤原則案例：記錄管理和保留管理角色 
- 敏感度標籤原則案例：安全性管理員、合規性管理員、規範資料管理員
- 通訊相容性原則案例：內幕人士風險管理管理員、主管審查管理員 

> [!IMPORTANT]
> 根據預設，只有建立自訂分類器的使用者可以訓練及審核該分類器所進行的預測。

## <a name="prepare-for-a-custom-trainable-classifier"></a>準備自訂 trainable 分類器 

深入瞭解建立自訂 trainable 分類器之前，請先瞭解相關專案。 

### <a name="timeline"></a>時間表

此時程表會反映 trainable 分類器的範例部署。

![trainable-分類器-時程表](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> Trainable 分類器第一次需要自願加入。 Microsoft 365 完成組織內容的基準評估需要12天。 請與您的全域系統管理員聯繫，以啟動自願加入處理常式。

### <a name="overall-workflow"></a>整體工作流程

若要深入瞭解建立自訂 trainable 分類程式的整體工作流程，請參閱 [建立客戶 trainable 分類](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)器的處理流程。

### <a name="seed-content"></a>Seed 內容

當您想要 trainable 的分類器獨立且準確地將專案識別為屬於特定類別的內容時，您必須先呈現該類別中內容類型的許多範例。 Trainable 分類器的此樣本饋送稱為「 *植* 入」。 Seed content 是由人類選取，並會判斷代表內容的類別。

> [!TIP]
> 您必須具有至少50的肯定範例，以及多達500。 Trainable 分類程式會處理最多500最近建立的範例 (按檔建立的日期/時間戳記) 。 您提供的範例越多，分類器所做的預測就越精確。

### <a name="testing-content"></a>測試內容

Trainable 分類器處理足夠的肯定樣本來建立預測模型之後，您必須測試所做的預測，以查看分類器是否可以正確辨別與類別及專案不符的專案。 若要這麼做，您可以選取另一個，但願會包含應屬於類別的範例，也可以是更大的人工挑選內容集合，也就是不是的範例。 您應測試與您第一次提供之原始 seed 資料不同的資料。 一旦處理好，您就可以手動流覽結果，並確認每個預測是否正確、不正確或不確定。 Trainable 分類器使用這種意見反應來改善其預測模型。

> [!TIP]
> 為了獲得最佳結果，您的測試範例集合中至少有200個專案，且具有正值和負比對的均勻分佈。

## <a name="how-to-create-a-trainable-classifier"></a>如何建立 trainable 的分類器

1. 在 50-500 seed content 專案之間收集。 這兩個範例都必須是強烈代表您想要讓 trainable 分類器正確識別為分類類別中的內容類型的範例。 如需支援的檔案類型，請參閱[SharePoint Server 中的預設編目副檔名和分析檔案類型](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。

   > [!IMPORTANT]
   > Seed 及 test 範例專案不能加密，必須是英文。

   > [!IMPORTANT]
   > 請確定 seed 集合中的專案是類別的 **強** 範例。 Trainable 分類器最初會根據您植入的模型來建立模型。 分類器假設所有種子範例都是強陽性的，而且沒有任何方式知道樣本是否與類別弱或消極。

2. 將 seed 內容放在專為 *只保留 seed 內容* 的 SharePoint Online 資料夾中。 請記下網站、文件庫和資料夾 URL。

   > [!TIP]
   > 如果您為種子資料建立新的網站和資料夾，至少要有一個小時的時間進行索引，才可建立會使用該植入資料的 trainable 分類器。

3. 使用合規性系統管理員或安全性系統管理員角色存取，並開啟 **Microsoft 365 規範中心** 或 **Microsoft 365 安全性中心**  >  **資料分類**，登入 Microsoft 365 規範中心。

4. 選擇 [ **Trainable 類元** ] 索引標籤。

5. 選擇 [ **建立 trainable 的分類器**]。

6. 針對 `Name` `Description` 您想要此 trainable 的分類器識別之專案類別的 [和] 欄位填入適當的值。

7. 從步驟2挑選 seed 內容網站的 SharePoint 線上網站、程式庫和資料夾 URL。 選擇 `Add` 。

8. 複查設定並選擇 `Create trainable classifier` 。

9. 在24小時內，trainable 分類程式會處理 seed 資料，並建立預測模型。 分類器狀態是在 `In progress` 處理 seed 資料時。 當分類器完成處理 seed 資料時，狀態變更為 `Need test items` 。

10. 您現在可以選擇分類器來查看 [詳細資料] 頁面。

    > [!div class="mx-imgBorder"]
    > ![trainable 分類器準備好用於測試](../media/classifier-trainable-ready-to-test-detail.png)

11. 請至少收集200測試內容專案 (10000 最大) 以取得最佳結果。 這些專案應該混合使用強陽性、強負片和有些專案，但其性質卻不明顯。 如需支援的檔案類型，請參閱[SharePoint Server 中的預設編目副檔名和分析檔案類型](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。

    > [!IMPORTANT]
    > 範例專案不能加密，必須是英文。

12. 將測試內容放入專用於 *只保留測試內容* 的 SharePoint Online 資料夾中。 請記下 SharePoint 線上網站、文件庫和資料夾 URL。

    > [!TIP]
    > 如果您為測試資料建立新的網站和資料夾，至少要有一個小時的時間，才能建立會使用該植入資料的 trainable 分類程式。

13. 選擇 `Add items to test` 。

14. 從步驟12的測試內容網站，挑選 SharePoint 線上網站、程式庫和資料夾 URL。 選擇 `Add` 。

15. 選擇 [完成] `Done` 。 您的 trainable 分類程式會需要長達一小時才能處理測試檔案。

16. 當 trainable 分類器完成處理測試檔案時，[詳細資料] 頁面上的狀態會變更為 `Ready to review` 。 如果您需要增加測試樣本大小，請選擇 `Add items to test` 並允許 trainable 的分類器處理其他專案。

    > [!div class="mx-imgBorder"]
    > ![準備好回顧螢幕擷取畫面](../media/classifier-trainable-ready-to-review-detail.png)

17. 選擇 [索引標籤 `Tested items to review` ] 以查看專案。

18. Microsoft 365 一次會出現30個專案。 請加以檢查，然後在方塊中 `We predict this item is "Relevant". Do you agree?` 選擇 [ `Yes` 或] 或] `No` `Not sure, skip to next item` 。 模型準確性會在每30個專案之後自動更新。

    > [!div class="mx-imgBorder"]
    > ![[複查專案] 對話方塊](../media/classifier-trainable-review-detail.png)

19. 回顧 *至少* 200 個專案。 當精確度分數穩定之後，[ **發行** ] 選項就會變成可用，分類程式的狀態將會說 `Ready to use` 。

    > [!div class="mx-imgBorder"]
    > ![精確度分數並準備發佈](../media/classifier-trainable-review-ready-to-publish.png)

20. 發佈分類器。

21. 一旦已發佈，您的分類器就會在[使用敏感度標籤的 Office 自動標籤](apply-sensitivity-label-automatically.md)中提供條件，根據狀況和[通訊合規性](communication-compliance.md)，[自動套用保留標籤原則](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)。