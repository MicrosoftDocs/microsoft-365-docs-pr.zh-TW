---
title: Microsoft 365 Defender 中的事件
description: 調查在不同裝置、使用者和信箱看到的事件。
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
ms.openlocfilehash: 5b2baa2041a8cffcea212eb449d40b9a9cbfc22a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759481"
---
# <a name="incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

> 想要體驗 Microsoft 365 Defender 嗎？ 您可以[在實驗室環境中評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[在生產環境中執行試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。
>

Microsoft 365 Defender 中的事件是組成攻擊之故事的相關警示和相關資料的集合。 

Microsoft 365 服務和應用程式會在偵測到可疑或惡意事件或活動時建立警示。 個別警示可提供關於已完成或進行中攻擊的重要線索。 不過，攻擊一般會針對不同類型的實體（例如裝置、使用者和信箱）採用各種技術。 其結果是針對您租使用者中的多個實體的多個警示。 

因為 piecing 個別警示來深入瞭解攻擊可能會非常困難而且耗時，所以 Microsoft 365 Defender 會自動將警示和相關資訊匯總到事件中。

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender 如何將實體中的事件與事件產生關聯":::

請觀看 Microsoft 365 Defender (4 分鐘) 中的事件簡短敘述。

<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

將相關警示分組到事件中，可讓您全面瞭解攻擊。 例如，您可以看到：

- 攻擊的開始位置。
- 使用的戰術。
- 攻擊進入您租使用者的距離。
- 攻擊的範圍，例如影響的裝置、使用者和信箱數目。 
- 所有與攻擊相關聯的資料。

若 [啟用](m365d-enable.md)，Microsoft 365 Defender 便可透過自動化和人工智慧，自動調查並解決警示。 您也可以執行其他修復步驟，以解決攻擊。 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Microsoft 365 安全中心的事件及警示

您可以在 Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上，管理事件 **& 警示 > 事件**。 以下為範例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 security center 中的 [事件] 頁面":::

選取 [事件名稱] 會顯示事件摘要，並可讓您存取具有其他資訊的索引標籤。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 安全中心內事件摘要頁面的範例":::

事件的其他索引標籤如下：

- 警示 

  與該事件相關的所有提醒，以及其資訊。

- 裝置

  已識別為屬於事件一部分或與其相關的所有裝置。

- 使用者

  已識別為屬於該事件或與其相關的所有使用者。

- 信箱

  已識別為屬於事件一部分或與其相關的所有信箱。

- 調查

  事件中的警示所觸發的所有自動調查。

- 證據與回應

  事件中警示中所有支援的事件及可疑的實體。

以下是事件與其資料之間的關係，以及 Microsoft 365 security center 中事件的索引標籤。

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="在 Microsoft 365 安全中心的事件索引標籤中，事件及其資料的關聯性":::

## <a name="next-step"></a>下一步

[ **事件** ] 頁面的 [事件] 佇列會列出最近的事件。 在這裡，您可以：

- 根據嚴重性及其他因素，查看應 [優先](incident-queue.md) 考慮哪些事件。 
- 對事件進行 [調查](investigate-incidents.md) 。
- [管理事件](manage-incidents.md)，包括重新命名、指派事件管理工作流程的標記、分類及新增標籤。
