---
title: 在 Microsoft Defender for Office 365 中檢查和管理修正動作
keywords: AIR，autoIR，Microsoft Defender for Endpoint，自動化，調查，回應，修正，威脅，高級，威脅，保護
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 深入瞭解 Microsoft Defender 中 Office 365 方案2的自動化調查和回應功能中的修復動作。
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 987771616acfd2f2faf425e525505b320155388e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108532"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>在 Office 365 中檢查和管理修正動作

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 2](defender-for-office-365.md)

隨著電子郵件的自動調查 & 共同作業會導致 verdicts （例如 *惡意* 或 *可疑*）建立某些修正動作。 在 Microsoft Defender for Office 365 中，修正動作可包含：

- 虛刪除電子郵件訊息或聚簇
- 關閉外部郵件轉發

除非安全運作小組批准，否則不會採取這些修復動作。 我們建議您儘快檢查及核准任何擱置的動作，以便您的自動化調查能夠及時完成。 在某些情況下，您可以重新考慮提交的動作。  您必須是搜尋 & 清除角色的一部分，才能採取任何動作。

## <a name="approve-or-reject-pending-actions"></a>核准 (或拒絕) 擱置的動作
有四種不同的方式可尋找及採取自動調查動作：

- [事件佇列](https://security.microsoft.com/incidents)
- [行動中心](https://security.microsoft.com/action-center/pending)
- 自行調查 (透過事件或警示存取) 
- [調查和修正調查佇列](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>事件佇列

1. 開啟 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 並登入。
2. 在功能窗格中，選取 [ **事件] & 警示 > 事件**。
3. 選取 [事件名稱] 以開啟其 [摘要] 頁面。
4. 選取 [ **證據與回應** ] 索引標籤。
5. 選取清單中的項目。 其側邊窗格隨即開啟。
6. 在側窗格中，進行核准或拒絕動作。

## <a name="investigation-queue"></a>調查佇列

1. 開啟 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 並登入。
2. 從 [警示/事件] 頁面流覽。
3. 在 [調查] 頁面上，移至 [ **擱置的動作** ] 索引標籤。
4. 選取清單中的項目。 其側邊窗格隨即開啟。
5. 在側窗格中，進行核准或拒絕動作。

## <a name="action-center"></a>控制中心

1. 開啟 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 並登入。
2. 在功能窗格中，選取 [ **動作中心**]。
3. 在 [ **暫** 止] 索引標籤上，查看等候核准的動作清單。
   - 選取 [ **開啟調查] 頁面** ，以查看有關調查的詳細資料。
   - 選取 [ **核准** ] 以啟動暫止的動作。
   - 選取 [ **拒絕** ] 以避免採取暫止的動作。

## <a name="investigation-and-remediation-investigations-queue"></a>調查和修正調查佇列

1. 開啟 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 並登入。
2. 開啟暫止的調查。
3. 在 [調查] 頁面上，移至 [ **擱置的動作** ] 索引標籤。
4. 選取清單中的項目。 其側邊窗格隨即開啟。
5. 在側窗格中，進行核准或拒絕動作。

## <a name="change-or-undo-one-remediation-action"></a>變更或撤銷一個修正動作

有兩種不同的方式可重新考慮提交的動作：

- 透過「 [整合」行動中心](https://security.microsoft.com/action-center)。
- 雖然[Office 的動作中心](https://security.microsoft.com/threatincidents)。

## <a name="change-or-undo-through-the-unified-action-center"></a>變更或撤銷整合動作中心

1. 移至 [ [整合] 動作中心](https://security.microsoft.com/action-center) 並登入。
2. 在 [ **記錄** ] 索引標籤上，選取您要變更或撤銷的動作。
3. 在螢幕右側的窗格中，選取適當的動作 (**移至 [收件** 匣]、[ **移至垃圾** 郵件]、[ **移至刪除的專案**]、[ **虛刪除**] 或 [ **實刪除** ]) 。

## <a name="change-or-undo-through-the-office-action-center"></a>變更或撤銷 Office 的活動中心

1. 請移至[Office 的動作中心](https://security.microsoft.com/threatincidents)並登入。
2. 選取適當的修復。
3. 在側窗格中，按一下 [郵件提交專案]，然後等候載入清單。
4. 等候上方的動作按鈕以啟用並選取動作按鈕以變更動作類型。
5. 這將會建立適當的動作。

## <a name="next-steps"></a>後續步驟

- [使用威脅瀏覽器](threat-explorer.md)
- [系統管理/Manual 動作](remediate-malicious-email-delivered-office-365.md)
- [如何在自動化調查和回應功能中報告誤報/負片](air-report-false-positives-negatives.md)

## <a name="see-also"></a>另請參閱

- [在 Office 365 中查看自動調查的詳細資料和結果](air-view-investigation-results.md)
