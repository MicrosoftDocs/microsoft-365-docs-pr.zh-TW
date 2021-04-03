---
title: 調查 Microsoft 365 Defender 中的警示
description: 調查透過裝置、使用者和信箱查看的警示。
keywords: 事件, 警示, 調查, 關聯, 攻擊, 電腦, 裝置, 使用者, 身分識別, 身分識別, 信箱, 電子郵件, 365, microsoft, m365
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
ms.openlocfilehash: 989574a860bea798c48e077f5633c31eb857e85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500939"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>調查 Microsoft 365 Defender 中的警示

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease](../includes/prerelease.md)]

提醒是指所有的事件，並指出您環境中發生惡意或可疑事件的基礎。 警示通常是廣泛攻擊的一部分，並提供有關事件的線索。

在 Microsoft 365 Defender 中，相關的警示會彙集在一起，以形成事件。 事件一定會提供更廣泛的攻擊內容，但是在需要深入分析時，調查警示會非常有用。 



## <a name="using-alert-pages-in-investigations"></a>使用調查中的警示頁面

在任何事件頁面的 [警示] 索引標籤中，選取警示可將您帶入個別警示頁面。 警示頁面包含三個區段：受影響的資產、警示案例及詳細資料窗格。

![警示範例的影像頁面](../../media/new-alert-page2.png)

在 [提醒] 頁面中，您可以選取任何實體旁邊的三個點圖示 () **...** ，這樣您就能看到可用的動作，例如開啟特定資產頁面或執行特定的修復步驟。

### <a name="analyze-affected-assets"></a>分析受影響的資產
「受影響的資產」區段會列出受此警示影響的信箱、裝置和使用者。 選取任何資產卡片都會以資訊顯示詳細資料側窗格，包括有關資產的其他警示（如果有的話）。


### <a name="trace-an-alerts-role-in-the-alert-story"></a>追蹤警示案例中的警示角色
警示案例會在處理樹狀檢視中顯示與警示相關的所有資產或實體。 當您第一次在選取的警示頁面上移動時，標題中的警示會是焦點。 提醒文章中的資產可展開和按一下。 它們可讓您在警示頁面的內容中採取行動，以提供額外的資訊並加速回應。 

> [!NOTE]
> 「警示案例」區段中可能會包含一個以上的警示，在您所選取的警示之前或之後，會顯示與相同執行樹狀目錄相關的其他警示。

### <a name="view-more-alert-information-in-the-details-pane"></a>在詳細資料窗格中查看更多警示資訊

[詳細資料] 窗格會先顯示選取警示的詳細資料，以及與其相關聯的詳細資料和動作。 如果您選取預警案例中的任何受影響的資產或實體，詳細資料窗格會變更，以提供所選物件的上下文資訊和動作。

當您選取相關實體時，[詳細資料] 窗格會變更，以顯示所選實體類型的相關資訊、可用的歷史資訊，以及直接從 [警示] 頁面採取動作的選項。

### <a name="manage-alerts"></a>管理警示

當您完成調查提醒後，您可以回到您已開始的警示，將警示的狀態標示為 [已解決]，然後將其歸類為「錯誤警示」或「True 警示」。 分類提醒可協助調整您的產品，以提供更真實的警示及不太虛假的提醒。

> [!NOTE]
> 透過使用標記來管理提醒的一種方式。 Microsoft Defender for Office 365 的標記功能會逐漸推出，而且目前在預覽中。 <br>
> 目前，已修改的標籤名稱只會套用至更新 *後* 所建立的警示。 修改之前產生的警示不會反映已更新的標記名稱。 


## <a name="manage-the-unified-alert-queue"></a>管理整合的提醒佇列

在 [事件] 下選取 [Microsoft 365 安全性中心] 導覽窗格中的警示 & 警示會帶您前往整合提醒佇列。 來自不同 Microsoft security 解決方案（如 Microsoft Defender for Endpoint、Microsoft Defender for Office 365 及 Microsoft 365 Defender）的警示會顯示在此區段中。 

![[範例警示] 頁面的圖像](../../media/unified-alert-queue.png)

[警示] 佇列顯示網路中已標示的警示清單。 根據預設，佇列會顯示過去30天內看到的警示。 最新的警示會顯示在清單的頂端，可協助您先看到最近的警示。

> [!NOTE]
> 在啟動時，[整合的提醒] 佇列只會有7天的 Microsoft Defender for Office 365 的可用警示。 佇列將繼續隨著時間建立。 如果您需要在啟動 [整合提醒] 佇列之前，對提醒進行分類，請使用 [安全性與合規性中心](https://protection.office.com/viewalerts)中的 [警示] 佇列。


在上方導覽中，您可以：

- 套用篩選
- 自訂欄以新增或移除欄
- 匯出資料

您也可以根據不同的準則來篩選警示：

- 嚴重性
- 狀態
- Category
- 偵測來源
- 原則
- 受影響資產
- 第一個活動
- 最後一個活動


若要開始調查事件，請參閱[Microsoft 365 Defender 中的調查事件](investigate-incidents.md)。
## <a name="see-also"></a>另請參閱

- [事件概觀](incidents-overview.md)
- [調查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
