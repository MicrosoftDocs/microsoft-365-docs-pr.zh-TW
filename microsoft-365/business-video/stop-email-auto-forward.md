---
title: 停止自動轉寄電子郵件
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
description: 瞭解如何停止自動轉轉電子郵件。
ms.openlocfilehash: ebbe37ab5c4a60c6ac4b6ebf8877247199460fa1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925883"
---
# <a name="stop-email-auto-forward"></a>停止自動轉轉電子郵件

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

如果駭客取得使用者信箱的存取權，駭客就可以自動將使用者的電子郵件轉會到外部地址，並竊取專利資訊。 您可以建立郵件流程規則來停止此程式。

## <a name="try-it"></a>試試看吧！

1. 從 Microsoft 365 系統管理中心，選取 **Exchange、** 郵件流程，然後選取規則上的加號，然後選擇建立 **新規則**。
1. 選取 **更多選項**。 命名您的新規則。
1. 然後，開啟下拉式清單，以在選取寄件者，然後是外部內部時 **，適用此規則**。
1. 選取 **組織內部，****然後確定**。
1. 選擇 **新增條件**、開啟下拉式清單、 **選取郵件** 內容，然後 **包含訊息類型**。
1. 開啟選取 **訊息類型** 下拉式選檔，選擇自動 **轉送**，然後選擇 **確定**。
1. 開啟執行 **下列下拉** 式清單，選取 **封鎖** 訊息，然後拒絕 **訊息並包含說明**。
1. 輸入訊息文字以做為說明， **然後選取確定**。
1. 卷到底部 **，然後選取** 儲存。

    您的規則已建立完成，駭客將無法再自動轉轉郵件。