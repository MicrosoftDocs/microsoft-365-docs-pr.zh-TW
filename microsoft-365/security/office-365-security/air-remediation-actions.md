---
title: Office 365 中的修復動作自動化調查和回應
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
ms.openlocfilehash: 2efe0124304a9f9dcfdc92b548c850882ad507a0
ms.sourcegitcommit: 841c06a5d566d404c35d5e9c0c7de5088daab976
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2020
ms.locfileid: "42836855"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Office 365 中的自動調查遵循的修正動作

## <a name="remediation-actions"></a>補救動作

Office 365 中的[自動化調查和回應功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)（AIR）[高級威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)（Office 365 ATP）方案2包含某些修正動作。 當自動調查執行或完成時，您通常會看到一或多項修正動作需要由安全性作業小組進行核准，才能繼續進行。 

下表摘要列出 Office 365 ATP 中目前可用的修復動作。 

|動作 | 描述 |
|-----|-----|
|封鎖 URL (點擊時) |針對包含惡意 URLs 的電子郵件訊息和檔加以防護。 這可讓您在使用者按一下現有 Office 檔案或舊的電子郵件中的連結時，透過[安全連結](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)封鎖惡意連結和任何相關的網頁。 |
|虛刪除電子郵件  |從使用者的信箱中，Soft 刪除特定的電子郵件。 <br/>虛刪除的郵件會移至使用者的 [可復原的專案] 資料夾，並且會保留直到刪除的專案保留期間到期為止。 |
|虛刪除電子郵件聚簇  |Soft delete 惡意電子郵件訊息符合來自所有使用者信箱的查詢。 <br/>虛刪除的郵件會移至使用者的 [可復原的專案] 資料夾，並且會保留，直到刪除的專案保留期間到期為止。 |
|關閉外部郵件轉寄 |移除特定使用者信箱的轉寄規則。|

> [!NOTE]
> 在 Office 365 ATP 中，不會自動採取任何修正動作。 只有組織的安全小組核准時，才會採取補救措施。 

## <a name="next-steps"></a>後續步驟

- [在 Office 365 中進行自動調查後，查看擱置或已完成的修復動作](air-review-approve-pending-completed-actions.md)

- [Office 365 中自動調查的詳細資料和結果](air-view-investigation-results.md)