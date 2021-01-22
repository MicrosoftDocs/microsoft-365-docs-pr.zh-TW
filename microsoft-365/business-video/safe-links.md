---
title: 管理安全連結
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何管理安全連結以保護企業不受惡意網站攻擊。
ms.openlocfilehash: 1f5b3f61871e8d231029156631031dbb0ef4f2f5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928015"
---
# <a name="manage-safe-links"></a>管理安全連結

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender for Office 365 ， formerly called Microsoft 365 ATP， or Advanced Threat Protection， help protect your business against malicious sites when people click links in Office apps.

## <a name="try-it"></a>試試看吧！

1. 請前往系統 [管理中心，](https://admin.microsoft.com)**然後選取設定**。
1. 向下卷卷 **來增加進一步威脅的保護**。 選取 **查看**、 **管理**，然後 **選取 ATP 安全連結**。
1. 在 **適用于整個組織的** 原則下，選擇 **預設原則，** 然後 **選取編輯圖示** 。
1. 輸入要封鎖的 URL。
1. 選取 **在 Office 應用程式、iOS** 和 Android 版 Office 中使用安全連結;選取 **[不要追蹤使用者按一下安全連結時進行追蹤**;然後選取 **[不允許使用者按一下原始** URL 的安全連結。 如果您設定預設策略，可能已經選取這些設定了。 選取 [儲存]。
1. 在 **適用于特定收件者的規則** 下，選擇建議 **的安全連結規則**，然後選取 **編輯** 圖示。
1. 選取 **設定**、向下標籤、輸入您不要檢查的 URL，然後選取 **新增圖示。**
1. 選取 **已申請**，然後選取您的功能變數名稱。 選取您想要將規則應用至的其他網域。 選取 **新增**、**確定****，然後** 儲存。

ATP 安全連結現在已進行設置。 請允許最多 30 分鐘，變更才能生效。

當使用者收到包含連結的電子郵件時，會掃描連結。 如果連結是安全的，您可以按一下連結。 不過，如果連結位於封鎖清單上，使用者會看到一則訊息，指出該連結已被封鎖。