---
title: 自動化調查詳細資料與結果
description: 在自動調查過程中和完成之後，您就可以查看結果和重要結果
keywords: 自動, 調查, 結果, 分析, 詳細資料, 修正, autoair
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.technology: m365d
ms.openlocfilehash: c050683bb3ed052ae4752ffdee66fe51fb99b88b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930363"
---
# <a name="details-and-results-of-an-automated-investigation"></a>自動化調查詳細資料與結果

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

當 Microsoft 365 Defender 進行自動化調查時，可在自動化調查程式期間及之後獲得該調查的詳細資訊。 如果您擁有[必要權限](mtp-action-center.md#required-permissions-for-action-center-tasks)，您可以在調查詳細資料檢視中查看這些詳細資料。 調查詳細資料檢視可提供您最新的狀態，以及核准任何待核准動作的能力。 

![調查詳細資料](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>開啟調查詳細資料檢視

您可以使用下列其中一種方法開啟調查詳細資料檢視：
- [選取 [控制中心] 中的項目](#select-an-item-in-the-action-center)
- [從事件詳細資料頁面中選取調查](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>選取 [控制中心] 中的項目

使用 [控制中心] 查看處於待核准狀態 (在 [待核准] 索引標籤上) 或已核准 (在 [歷史記錄] 索引標籤上) 的動作。 

1. 移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。 

2. 在功能窗格中，選擇 [控制中心]。 

3. 在 [待核准] 或 [歷史記錄] 索引標籤上，選取一個項目。 如果您擁有[必要權限](mtp-action-center.md#required-permissions-for-action-center-tasks)，您可以核准 (或拒絕) 待核准的動作。

### <a name="open-an-investigation-from-an-incident-details-page"></a>從事件詳細資料頁面開啟調查

使用事件詳細資料頁面來查看事件的詳細資訊，包括觸發任何受影響裝置、使用者帳戶或信箱之資訊的警示。

1. 移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。 

2. 在功能窗格中，選擇 [事件]。 

3. 選取清單中的項目以開啟事件詳細資料檢視。<br/>![事件詳細資料](../../media/mtp-incidentdetails-tabs.png)

4. 在 [調查] 索引標籤上，選取清單中的調查。

## <a name="investigation-details"></a>調查詳細資料

使用調查詳細資料檢視，查看與調查相關的過去、目前和待核准的活動。 調查詳細資料檢視類似以下影像：

![調查詳細資料](../../media/mtp-air-investdetails.png)

在調查詳細資料檢視中，您可以在 [調查圖表]、[警示]、[裝置]、[身分識別]、[重要結果]、[實體]、**[記錄]**，以及 [待核准的動作] 索引標籤上查看資訊，如下表所述。

| 索引標籤 | 描述 |
|--------|--------|
| **調查圖表**   | 提供調查的視覺呈現。 描述實體並列出發現的威脅和警示，以及是否有任何待核准的動作。<br/>您可以按一下圖表上的項目來查看更多詳細資料。 例如，按一下 [找到的威脅] 圖示會帶您移至 [重要結果] 索引標籤。 |
| **提醒**    | 列出與調查相關聯的警示。 警示可能來自使用者電腦上、Office 應用程式、雲端 App 安全性和其他 Microsoft 365 Defender 功能的威脅防護功能。|
| **裝置** | 列出調查中包含的電腦及其修正等級。|
| **重要結果**  | 列出調查結果，以及狀態和已執行或待核准的動作。 您可以在這個索引標籤上核准裝置和身分識別的待核准動作。|
| **Entities**  | 列出與調查相關聯的使用者活動、檔案、處理程序、服務、驅動程式、IP 位址和持續性方法，以及狀態和採取的動作。|
|**Log**    | 提供調查過程中所有步驟的詳細資訊，以及狀態。|
| **待核准的動作** | 列出需要核准才能繼續的項目。|

## <a name="next-steps"></a>後續步驟

- [與自動化調查及回應相關的核准或拒絕動作](mtp-autoir-actions.md)
- [審查補救動作](mtp-remediation-actions.md)
