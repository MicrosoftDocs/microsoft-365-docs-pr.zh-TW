---
title: 調查 Microsoft 365 Defender 中的警示
description: 調查透過裝置、使用者和信箱查看的警示。
keywords: 事件、警示、調查、分析、回應、關聯、攻擊、電腦、裝置、使用者、身分識別、身分識別、信箱、電子郵件、365、microsoft、m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 567916e9e1a1d96d77bc6c187b384a1ec3be72a5
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022676"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>調查 Microsoft 365 Defender 中的警示

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

提醒是指所有的事件，並指出您環境中發生惡意或可疑事件的基礎。 警示通常是廣泛攻擊的一部分，並提供有關事件的線索。

在 Microsoft 365 Defender 中，會將相關的警示彙集在一起，以形成[事件](incidents-overview.md)。 事件一定會提供更廣泛的攻擊內容，不過，當需要深入分析時，分析警示可能很重要。 

[ **警示] 佇列** 會顯示目前的警示集。 您可以從事件中取得警示佇列， **& 警示 >** Microsoft 365 Defender 入口網站 ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上的警示。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="警示佇列的範例":::

不同 microsoft security 解決方案（如 microsoft defender for Endpoint、microsoft defender for Office 365 和 Microsoft 365 Defender）中的警示會出現在這裡。

根據預設，Microsoft 365 Defender 入口網站中的 [警示] 佇列會顯示過去30天的新和進行中的警示。 最新的警示是在清單頂端，您可以先查看它。 

您可以從預設的 [提醒] 佇列中，選取 [ **篩選** ]，以查看 **篩選** 窗格，您可以從中指定提醒的子集。 以下為範例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="警示佇列之篩選窗格的範例":::

您可以根據這些準則來篩選警示：

- 嚴重性
- 狀態
- 類別
- 偵測來源
- 標記
- 原則
- 受影響資產

## <a name="analyze-an-alert"></a>分析警示

若要查看 [主要提醒] 頁面，請選取警示的名稱。 以下為範例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Microsoft 365 Defender 入口網站中警示的詳細資料頁面範例":::

您也可以從 [**管理警示**] 窗格中選取 [**開啟主要警示] 頁面** 動作。

警示頁面是由下列區段所組成： 

- 警示案例，這是以時間順序與此警示相關的事件及警示鏈
- 摘要詳細資料

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Microsoft 365 Defender 入口網站中警示的詳細資料頁面範例":::

在 [警示] 頁面中，您可以選取任何實體旁的省略號 () **...** ]，以查看可用的動作，例如開啟警示頁面或將警示連結至另一個事件。

### <a name="alert-sources"></a>警示來源
Microsoft 365 Defender 警示可能來自 microsoft defender for Endpoint、microsoft defender for Office 365 及 Microsoft Cloud App Security 等解決方案。 您可能會注意到警示中帶有前置字元的警示。 下表提供指導方針，可協助您瞭解根據警示上的前置字母，警示來源的對應。

> [!NOTE]
> - 預置的 Guid 只是針對整合的經驗，例如整合的警示佇列、整合的提醒頁面、整合調查和整合事件。<br>
> - 預先符不會變更警示的 GUID。 GUID 的唯一變更是預置的元件。<br>


警示來源 | 預先符 
:---|:---
適用於 Office 365 的 Microsoft Defender | `fa{GUID}` <br> 範例：`fa123a456b-c789-1d2e-12f1g33h445h6i` 
適用於端點的 Microsoft Defender | `da` 或 `ed` 自訂偵測警示 <br> 
適用於身分識別的 Microsoft Defender | `aa{GUID}` <br> 範例：`aa123a456b-c789-1d2e-12f1g33h445h6i` 
Microsoft 雲端 App 安全性 |`ca{GUID}` <br> 範例：`ca123a456b-c789-1d2e-12f1g33h445h6i` 

### <a name="analyze-affected-assets"></a>分析受影響的資產

[ **採取的動作** ] 區段包含受影響的資產清單，例如信箱、裝置，以及受此警示影響的使用者。 

您也可以 **在 [操作中心**] 中選取 [view] （查看），以在 Microsoft 365 Defender 入口網站中查看 **動作中心** 的 [**記錄**] 索引卷 

### <a name="trace-an-alerts-role-in-the-alert-story"></a>追蹤警示案例中的警示角色

警示案例會在處理樹狀檢視中顯示與警示相關的所有資產或實體。 當您第一次在選取的警示頁面上移動時，標題中的警示會是焦點。 提醒文章中的資產可展開和按一下。 它們可讓您在警示頁面的內容中採取動作，以提供額外的資訊並加速您的回應。 

> [!NOTE]
> 「警示案例」區段中可能會包含一個以上的警示，在您所選取的警示之前或之後，會顯示與相同執行樹狀目錄相關的其他警示。

### <a name="view-more-alert-information-on-the-details-page"></a>在 [詳細資料] 頁面上查看其他警示資訊

[詳細資料] 頁面會顯示所選警示的詳細資料，以及與其相關聯的詳細資料和動作。 如果您選取預警案例中的任何受影響的資產或實體，[詳細資料] 頁面會變更，以提供所選物件的上下文資訊和動作。

當您選取相關實體時，[詳細資料] 頁面會變更，以顯示所選實體類型的相關資訊、可用的歷史資訊，以及直接從 [警示] 頁面對此實體採取動作的選項。

## <a name="manage-alerts"></a>管理警示

若要管理警示，請在其所在列的 [警示] 佇列中選取警示，以查看 [ **管理警示** ] 窗格。 以下為範例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="警示摘要窗格的範例":::

[ **管理警示** ] 窗格可讓您指定：

- 警示狀態 (新的，已解決，正在進行中) 。
- 警示的分類 (未設定、True 警示、False 警示) 。
- 針對分類為 true 的警示，在 [ **判斷** ] 欄位中，警示的威脅類型。
- 警示上的批註。

> [!NOTE]
> 透過使用標記來管理提醒的一種方式。 Microsoft Defender for Office 365 的標籤功能會逐漸向內進行，而且目前在預覽中。 <br>
> 目前，已修改的標籤名稱只會套用至更新 *後* 所建立的警示。 在修改之前產生的警示將不會反映已更新的標記名稱。 

您也可以從這個窗格執行下列額外的動作： 

- 開啟 [主要提醒] 頁面
- 諮詢 Microsoft 威脅專家
- 查看提交
- 連結至另一個事件
- 在時程表中查看警示
- 建立隱藏規則

以下為範例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Microsoft 365 Defender 入口網站上警示的動作範例":::

其他動作的清單取決於警示類型。

## <a name="resolve-an-alert"></a>解決警示

當您完成對警示的分析而且可以解決後，請移至 [ **管理警示** ] 窗格中的警示，並將 it 狀態標示為 [ **已解決** ]，然後將其歸類為 **錯誤警示** 或 **True 警示**。 若為 true 警示，請在 **判斷** 欄位中指定警示的威脅類型。

分類提醒並指定其判斷，可協助調整 Microsoft 365 Defender，以提供更真實的警示及較少的虛假警示。

## <a name="next-steps"></a>後續步驟

視需要進行處理內事件，繼續進行 [調查](investigate-incidents.md)。

## <a name="see-also"></a>另請參閱

- [事件概觀](incidents-overview.md)
- [管理事件](manage-incidents.md)
- [調查事件](investigate-incidents.md)
