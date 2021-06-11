---
title: 管理 Microsoft 365 Defender 中的事件
description: 了解如何指派及更新狀態
keywords: 事件、事件、分析、回應、警示、關聯警示、指派、更新、狀態、管理、分類、microsoft、365、m365
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
ms.openlocfilehash: 9cb3cc67c3992773897ea8178f261d25dcd87da0
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594144"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>管理 Microsoft 365 Defender 中的事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

事件管理對於確保威脅已包含並加以解決非常重要。

您可以在 Microsoft 365 安全性中心 ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上，管理事件 **& 警示 > 事件**。 以下為範例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件佇列的範例":::

您可以透過下列方式管理您的事件：

- [編輯事件名稱](#edit-the-incident-name)
- [新增事件標籤](#add-incident-tags)
- [指派事件給您自己](#assign-incidents)
- [解決這些問題](#resolve-an-incident)
- [設定它的分類和決定](#set-the-classification-and-determination)
- [新增註解](#add-comments)

您可以從「 **管理事件** 」窗格中管理事件的事件。 以下為範例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="事件的管理事件窗格範例":::

您可以從下列專案上的 **管理事件** 連結，顯示此窗格：

- 事件佇列中事件的屬性窗格。
- 事件的 **摘要** 頁面。

當您想要將警示從某個事件移動到另一個事件時，您也可以從 [ **警示** ] 索引標籤，建立一個包含所有相關警示的較大或較小的事件。

## <a name="edit-the-incident-name"></a>編輯事件名稱

Microsoft 365Defender 會根據警示屬性（如受影響的端點數目、受影響的使用者、偵測來源或類別）自動指派名稱。 這可讓您快速瞭解事件的範圍。 例如：多 *個來源所報告之多個端點上的多階段事件。*

您可以在 [**管理事件**] 窗格上的 [**事件名稱**] 欄位中編輯事件名稱。

> [!NOTE]
> 在自動事件命名功能的展示中所發生的事件，會保留其名稱。

## <a name="add-incident-tags"></a>新增事件標籤

您可以將自訂標記新增至事件，例如標示具有共同特性的事件群組。 您可以稍後針對所有包含特定標記的事件，篩選事件佇列。

當您開始輸入時，您可以選擇從選取的標記清單中進行選取。

## <a name="assign-incidents"></a>指派事件

若要指派事件，請選取 [ **指派給我**]。 這樣做會將事件的擁有權及與其相關聯的所有警示指派給您的使用者帳戶。

您可以篩選事件佇列，以取得指派給您的事件清單。 

1. 在 [事件] 佇列中，選取 [ **篩選**]。
2. 在 [ **事件指派** ] 區段中，清除 [ **全選** ]，然後選取 [ **指派給我**]。
3. 選取 **[** 套用]，然後關閉 [ **篩選** ] 窗格。

然後您可以將瀏覽器中產生的 URL 儲存為書簽，以快速查看指派給您的事件清單。

## <a name="resolve-an-incident"></a>解決事件

如果事件已經修正，請選取 [ **解決事件** ]，將切換移至右邊。 請注意，解決事件也會解決與該事件相關的所有連結和主動警示。

未解析的事件會顯示為作用 **中。**

## <a name="set-the-classification-and-determination"></a>設定分類和決定

「事件分類」是指從 [ **分類** ] 欄位設定的是 true 警示或假警示。 

如果是真正的警示，您也應該指定其 **判斷** 欄位所使用的威脅類型。 指定威脅類型可協助安全小組看到威脅模式，並採取行動以保護組織。 

## <a name="add-comments"></a>新增註解

您可以使用 [ **批註** ] 欄位，將多個批註新增至事件。 每個評論都會新增至事件的歷史事件。 您可以在 [**摘要**] 頁面上，看到 [**批註和記錄**] 連結中的事件批註和記錄。

## <a name="next-steps"></a>後續步驟

針對新的事件，開始進行 [調查](investigate-incidents.md)。

若為處理中的事件，請繼續進行 [調查](investigate-incidents.md)。

若為解決的事件，請執行 [事件後檢查](first-incident-post.md)。

## <a name="see-also"></a>另請參閱

- [事件概觀](incidents-overview.md)
- [設定事件優先順序](incident-queue.md)
- [調查事件](investigate-incidents.md)
