---
title: 在自動調查和回應中複查及核准擱置的修復動作
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 深入瞭解 Microsoft Defender for Office 365 方案2中自動調查和回應功能的修復動作。
ms.openlocfilehash: 7dc5c0ba2e320e3f140d26e79e5c2e4a8fde79d7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844557"
---
# <a name="view-pending-or-completed-remediation-actions-following-an-automated-investigation-in-office-365"></a>在 Office 365 中進行自動調查後，查看擱置或已完成的修復動作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]



![AIR 調查動作頁面](../../media/air-investigationactionspage.png)

## <a name="approve-or-reject-pending-actions"></a>核准 (或拒絕) 擱置的動作

當您查看 [調查的詳細資料](air-view-investigation-results.md)時，您可以核准或拒絕任何擱置的修復動作。 我們建議您儘快執行這種操作，以完成您的自動化調查。

> [!IMPORTANT]
> 核准或拒絕修正動作必須具有適當的許可權。 請參閱 [使用 AIR 功能所需的許可權](office-365-air.md#required-permissions-to-use-air-capabilities)。

1. 移至 [https://protection.office.com](https://protection.office.com) 並登入。 這樣會帶您前往安全性與合規性中心。

2. 移至 [威脅管理]  >  [調查]。

3. 在調查清單中，選取 [識別碼] 欄中的項目。 

4. 選取 [ **動作** ] 索引標籤。

5. 選取清單中的項目。  (這會啟用 [核准] 及 [拒絕] 按鈕。 ) 

6. 查看您所選取之專案 () 可用資訊，然後核准或拒絕該動作 (s) 。 
   - **核准** 允許開始修復。
   - **拒絕** 不再採取任何動作

## <a name="next-steps"></a>後續步驟

- [Office 365 中自動調查的詳細資料和結果](air-view-investigation-results.md)

- [使用威脅瀏覽器](threat-explorer.md)
