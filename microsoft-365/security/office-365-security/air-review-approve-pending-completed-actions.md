---
title: 在 Office 365 自動化調查與回應中複查及核准擱置的修復動作
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
ms.collection: M365-security-compliance
description: 深入瞭解 Office 365 Advanced 威脅防護方案2中自動化調查和回應功能的修復動作。
ms.openlocfilehash: d2b617e29fc36d1f39ab6c9ef6f708d5f608b206
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826432"
---
# <a name="view-pending-or-completed-remediation-actions-following-an-automated-investigation-in-office-365"></a>在 Office 365 中進行自動調查後，查看擱置或已完成的修復動作

## <a name="approve-or-reject-pending-actions"></a>核准（或拒絕）暫止的動作

![AIR 調查動作頁面](../../media/air-investigationactionspage.png)

當您查看[調查的詳細資料](air-view-investigation-results.md)時，您可以核准或拒絕任何擱置的修復動作。 我們建議您儘快執行這種操作，以完成您的自動化調查。

> [!IMPORTANT]
> 核准或拒絕修正動作必須具有適當的許可權。 請參閱[使用 AIR 功能所需的許可權](office-365-air.md#required-permissions-to-use-air-capabilities)。

1. 移至 [https://protection.office.com](https://protection.office.com) 並登入。 這樣會帶您前往安全性與合規性中心。

2. 移至 [威脅管理]****  >  [調查]****。

3. 在調查清單中，選取 [識別碼]**** 欄中的項目。 

4. 選取 [**動作**] 索引標籤。

5. 選取清單中的項目。 （這會啟用 [核准] 和 [拒絕] 按鈕。）

6. 查看您選取之專案的可用資訊，然後核准或拒絕動作。 
 - **核准**允許開始修復。
 - **拒絕**不再採取任何動作

## <a name="next-steps"></a>後續步驟

- [Office 365 中自動調查的詳細資料和結果](air-view-investigation-results.md)

- [使用威脅瀏覽器](threat-explorer.md)