---
title: 將您的網域連線到 Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 瞭解如何將您的網域連接至 Microsoft 365。
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925107"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>將您的網域連接到商務用 Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

一旦設定好 Microsoft 365，並移動了來自 Google Workspace 的電子郵件資料，就可以將您的網域連結至 Microsoft 365。 

首先，您必須從 Google 刪除現有的 DNS 記錄，然後我們可以從 Microsoft 365 新增 DNS 記錄。

## <a name="try-it"></a>試試看吧！

1. 在 admin.google.com 上，[請admin.google.com。](https://admin.google.com)
1. 在 **左側流覽****中選取網域、管理網域**、**查看** 詳細資料、管理 **網** 域，然後選取 **DNS。**
1. 向下卷到 **Records 記錄**，開啟 Google **Workspace，** 選取 **Delete，** 然後再次 **刪除** 。
1. 向下卷到 **自訂資源記錄** ，並刪除任何出現的現有 DNS 記錄，包括您先前可能為 Microsoft 365 建立的任何 DNS 記錄。
1. 請前往 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
1. 在左側 NAV 中，選擇 、顯示 **全部**、**設定、****網域**。
1. 然後選擇您的預設網域。
1. 選取 **繼續設定**，然後選擇繼續以連接您的  **網域**。
1. 向下卷卷來查看需要複製到 Google 的 DNS 記錄。
1. 開啟 **MX 記錄**，在 **指向位址或值** 下複製記錄。
1. 返回 Google，**在自訂資源** 記錄區段，開啟記錄類型下拉式清單，然後選取 **MX。**
1. 在資料 **欄位中** ，貼上您複製的記錄。
1. 然後選取 **[新增]**。
1. 對 CNAME 和 TXT 記錄重複此程式，並新增 Google DNS 管理頁面上的值。
1. 返回 Microsoft 365 系統管理中心， **然後選取繼續**。

    您的網域設定已完成。