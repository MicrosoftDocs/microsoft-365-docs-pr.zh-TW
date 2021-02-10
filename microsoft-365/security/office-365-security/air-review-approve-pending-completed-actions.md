---
title: 在 Microsoft Defender for Office 365 中複查和管理修正動作
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
description: 深入瞭解 Microsoft Defender for Office 365 方案2中自動調查和回應功能的修復動作。
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 3fb77fa41ff3e9af995cf80b9f4024aa92a51212
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176012"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>在 Office 365 中複查及管理修正動作

隨著電子郵件的自動調查 & 共同作業會導致 verdicts （例如 *惡意* 或 *可疑*）建立某些修正動作。 在 Microsoft Defender for Office 365 中，修正動作可包含：
- 封鎖 URL (按時) 
- 虛刪除電子郵件訊息或聚簇
- 隔離電子郵件或電子郵件附件
- 關閉外部郵件轉發

除非安全運作小組批准，否則不會採取這些修復動作。 我們建議您儘快檢查及核准任何擱置的動作，以便您的自動化調查能夠及時完成。 在某些情況下，您可以復原修復動作。

**適用於**
- [Microsoft Defender for Office 365 方案2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="approve-or-reject-pending-actions"></a>核准 (或拒絕) 擱置的動作

1. 請移至 Microsoft 365 security center [https://security.microsoft.com](https://security.microsoft.com)) 並登入。
2. 在功能窗格中，選取 [ **動作中心**]。
3. 在 [ **暫** 止] 索引標籤上，查看等候核准的動作清單。
4. 選取清單中的項目。 其快顯視窗隨即開啟。 
5. 查看彈出窗格中的資訊，然後執行下列其中一個步驟：
   - 選取 [ **開啟調查] 頁面** ，以查看有關調查的詳細資料。
   - 選取 [ **核准** ] 以啟動暫止的動作。
   - 選取 [ **拒絕** ] 以避免採取暫止的動作。

## <a name="undo-one-remediation-action"></a>復原一個修正動作

1. 請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 並登入。
2. 在 [ **記錄** ] 索引標籤上，選取您要復原的動作。
3. 在螢幕右側的窗格中，選取 [ **復原**]。

## <a name="undo-multiple-remediation-actions"></a>復原多項修復動作

1. 請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 並登入。
2. 在 [ **記錄** ] 索引標籤上，選取您要復原的動作。 請務必選取具有相同動作類型的專案。 隨即開啟彈出窗格。
3. 在快顯視窗中，選取 [復原]。

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>在多個裝置間移除隔離檔

1. 請移至「行動中心」 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 並登入。
2. 在 [ **記錄** ] 索引標籤上，選取具有 [ **隔離** 檔] 動作類型的檔案。
3. 在螢幕右側的窗格中，選取 [套用至此檔案 **的 X 個實例**]，然後選取 [ **復原**]。

## <a name="next-steps"></a>後續步驟

- [使用威脅瀏覽器](threat-explorer.md)
- [如何在自動化調查和回應功能中報告誤報/負片](air-report-false-positives-negatives.md)

## <a name="see-also"></a>另請參閱

- [在 Office 365 中查看自動調查的詳細資料和結果](air-view-investigation-results.md)
