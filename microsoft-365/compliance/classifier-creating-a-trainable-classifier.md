---
title: 建立 trainable 的分類器（預覽）
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
description: 當其中一個內建的分類器無法滿足您的需求時，請使用 trainable 的分類程式。 Microsoft 365 分類器是一種工具，可讓您訓練以辨識各種類型的內容，其範例可供您查看。 本主題說明如何建立自訂分類符。
ms.openlocfilehash: 05ec9992fb4ec072403e193df3d7dbbbb8b1a96b
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126354"
---
# <a name="creating-a-trainable-classifier-preview"></a>建立 trainable 的分類器（預覽）

當其中一個現成的分類器無法滿足您的需求時，請使用 trainable 的分類程式。 Microsoft 365 分類器是一種工具，可讓您訓練以辨識各種類型的內容，其範例可供您查看。 訓練分類器首先會將人工挑選和正確符合類別的範例提供給它。 然後，在處理完後，您可以透過提供正負樣本的混合來測試預測。

若要深入瞭解不同類型的分類器，請參閱[trainable 分類器的快速入門（預覽）](classifier-getting-started-with.md)

此時程表會反映部署範例。

![trainable-分類器-時程表](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> Trainable 分類器第一次需要自願加入。 Microsoft 365 需要12天的時間來完成組織內容的基準評估。 請與您的全域系統管理員聯繫，以啟動自願加入處理常式。

## <a name="seed-content"></a>Seed 內容

當您想要 trainable 的分類器獨立且準確地將專案識別為屬於特定類別的內容時，您必須先呈現該類別中內容類型的許多範例。 Trainable 分類器的此樣本饋送稱為「*植*入」。 Seed content 是由人類選取，並會判斷代表內容的類別。

> [!TIP]
> 您必須具有至少50的肯定範例，以及多達500。 Trainable 分類程式會處理最多500個最近建立的範例（透過檔案建立的日期/時間戳記）。 您提供的範例越多，分類器所做的預測就越精確。

## <a name="testing-content"></a>測試內容

Trainable 分類器處理足夠的肯定樣本來建立預測模型之後，您必須測試所做的預測，以查看分類器是否可以正確辨別與類別及專案不符的專案。 若要這麼做，您可以將它放在另一個中，但願其包含的範例應屬於類別，而不是使用的範例。 一旦處理好，您就可以手動流覽結果，並確認每個預測是否正確、不正確或不確定。 Trainable 分類器使用這種意見反應來改善其預測模型。

> [!TIP]
> 為了獲得最佳結果，您的測試範例集合中有10000個專案，且具有正值和負值的均勻分佈。

## <a name="how-to-create-a-trainable-classifier"></a>如何建立 trainable 的分類器

1. 在 50-500 seed content 專案之間收集。 這兩個範例都必須是強烈代表您想要讓 trainable 分類器正確識別為分類類別中的內容類型的範例。 如需支援的檔案類型，請參閱[SharePoint Server 中的預設編目副檔名和分析檔案類型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。

> [!IMPORTANT]
> Seed 及 test 範例專案不能加密，必須是英文。

> [!IMPORTANT]
> 請確定 seed 集合中的專案是類別的**強**範例。 Trainable 分類器最初會根據您植入的模型來建立模型。 分類器假設所有種子範例都是強陽性的，而且沒有任何方式知道樣本是否與類別弱或消極。

2. 將 seed 內容放在專為*只保留 seed 內容*的 SharePoint Online 資料夾中。 請記下網站、文件庫和資料夾 URL。

> [!TIP]
> 如果您為種子資料建立新的網站和資料夾，至少要有一個小時的時間進行索引，才可建立會使用該植入資料的 trainable 分類器。

3. 使用合規性管理員或安全性管理員角色存取及開啟**microsoft 365 規範中心**或**microsoft 365 安全中心**  >  **資料分類**，登入 Microsoft 365 合規性中心

4. 選擇 [ **Trainable 類元**] 索引標籤。

5. 選擇 [**建立 trainable 的分類器**]。

6. 填寫適當的值 `Name` ，以及 `Description` 您想要此 trainable 分類器識別之專案類別的欄位。

7. 輸入從步驟2開始，實際的 SharePoint 線上網站、程式庫和資料夾 URL 的 seed 內容網站。 選擇 `Add` 。

8. 複查設定並選擇 `Create trainable classifier` 。

9. 在24小時內，trainable 分類程式會處理 seed 資料，並建立預測模型。 分類器狀態是在 `In progress` 處理 seed 資料時。 當分類器完成處理 seed 資料時，狀態變更為 `Need test items` 。

10. 您現在可以選擇分類器來查看 [詳細資料] 頁面。


![trainable 分類器準備好用於測試](../media/classifier-trainable-ready-to-test-detail.png)

11. 至少收集200測試內容專案。 Microsoft 建議10000以取得最佳結果。 這些專案應該混合使用強陽性、強負片和有些專案，但其性質卻不明顯。 如需支援的檔案類型，請參閱[SharePoint Server 中的預設編目副檔名和分析檔案類型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。

> [!IMPORTANT]
> 範例專案不能加密，必須是英文。

12. 將測試內容放入專用於*只保留測試內容*的 SharePoint Online 資料夾中。 請記下 SharePoint 線上網站、文件庫和資料夾 URL。

> [!TIP]
> 如果您為測試資料建立新的網站和資料夾，至少要有一個小時的時間，才能建立會使用該植入資料的 trainable 分類程式。

13. 選擇 `Add items to test` 。

14. 輸入實際的 SharePoint 線上網站、程式庫，以及步驟12之測試內容網站的資料夾 URL。 選擇 `Add` 。

15. 選擇 [完成] `Done` 。 您的 trainable 分類程式會需要長達一小時才能處理測試檔案。

16. 當 trainable 分類器完成處理測試檔案時，[詳細資料] 頁面上的狀態會變更為 `Ready to review` 。 如果您需要增加測試樣本大小，請選擇 `Add items to test` 並允許 trainable 的分類器處理其他專案。

![準備好回顧螢幕擷取畫面](../media/classifier-trainable-ready-to-review-detail.png)

17. 選擇 [索引標籤 `Tested items to review` ] 以查看專案。

18. Microsoft 365 一次會出現30個專案。 請加以檢查，然後在方塊中 `We predict this item is "Relevant". Do you agree?` 選擇 [ `Yes` 或] 或] `No` `Not sure, skip to next item` 。 模型準確性會在每30個專案之後自動更新。

![[複查專案] 對話方塊](../media/classifier-trainable-review-detail.png)

19. 回顧*至少*200 個專案。

<!-- insert Analyze steps here-->

20. 繼續進行檢查，直到精確度達到至少70%，且 `Publish the classifier` 狀態為 `Ready to use` 。

![準確性並準備發佈](../media/classifier-trainable-review-ready-to-publish.png)

21. 發佈分類器。

22. 一旦發佈您的分類器，就會在[使用敏感度標籤的 Office autolabeling](apply-sensitivity-label-automatically.md)中提供條件，根據狀況和[通訊規範](communication-compliance.md)[自動套用保留標籤原則](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)。

> [!CAUTION]
> 在發佈分類器之後，它不能進行任何其他訓練，因此請務必確定您已測試並檢查盡可能多的專案，以確保精確度盡可能高。

## <a name="see-also"></a>另請參閱

- [開始使用可訓練的分類器 (預覽)](classifier-getting-started-with.md)
- [SharePoint Server 中預設編目的檔案副檔名及剖析的檔案類型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
