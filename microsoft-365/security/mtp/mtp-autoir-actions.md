---
title: 自動調查後核准或拒絕擱置的動作
description: 使用重要訊息中心來管理與自動化調查和回應相關的動作
keywords: 動作, 中心, autoair, 自動化, 調查, 回應, 補救
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: ed0b9afa576f65d33cd9a49dfacd96ffaf173d28
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846529"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>自動調查後核准或拒絕擱置的動作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

當自動化調查執行時，可能會導致需要核准才能繼續的一或多個[補救動作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)。 例如，可能需要刪除一組電子郵件訊息，或可能需要移除隔離的檔案。 務必盡快核准 (或拒絕) 擱置中的動作，這樣您的自動化調查才能及時進行和完成。 

> [!TIP]
> 如果您認為 Microsoft 365 Defender 中的自動調查和回應功能已錯過或錯誤地偵測到某項功能，請讓我們知道！ 請參閱 [如何在自動調查和回應中報告誤報/負片 (Microsoft 365 Defender 中的 AIR) 功能](mtp-autoir-report-false-positives-negatives.md)。

您可以使用「 [行動中心](#review-a-pending-action-in-the-action-center) 」或「 [調查詳細資料」視圖](#review-a-pending-action-in-the-investigation-details-view)，檢查和核准擱置的動作。

> [!NOTE]
> 您必須具備[適當的權限](mtp-action-center.md#required-permissions-for-action-center-tasks)，才能核准或拒絕補救動作。

## <a name="review-a-pending-action-in-the-action-center"></a>在重要訊息中心檢閱擱置中的動作

1. 移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。 

2. 在功能窗格中，選擇 [重要訊息中心]。 

3. 在重要訊息中心的 [擱置中] 索引標籤上，選取清單中的一個項目。 

    - 如果您選取 [調查編號] 資料行中的項目，調查詳細資料頁面會隨即開啟。 您可以在該處檢視調查結果，然後核准或拒絕建議的動作。
 
    - 如果您選取清單中的資料列，就會開啟飛出視窗，您可以在此檢視該項目的相關資訊。 <br/>![核准或拒絕動作](../../media/air-actioncenter-itemselected.png)<br/>使用連結來檢視相關聯的警示或調查，並核准或拒絕動作。

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>在調查詳細資料檢視中檢閱擱置中的動作

![調查詳細資料](../../media/mtp-air-investdetails.png)

1. 在 [調查詳細資料][](mtp-autoir-results.md) 頁面上，選取 [擱置中的動作] (或 [動作]) 索引標籤。此處會列出核准擱置中的項目。

2. 選取清單中的項目，然後選擇 [核准] 或 [拒絕]。

## <a name="next-steps"></a>後續步驟

- [檢視自動調查的詳細資料和結果](mtp-autoir-results.md)
- [在自動化調查和回應功能中處理誤報/負片](mtp-autoir-report-false-positives-negatives.md)
