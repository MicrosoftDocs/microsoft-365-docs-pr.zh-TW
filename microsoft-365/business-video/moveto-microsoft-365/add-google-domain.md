---
title: 新增您的 Google Workspace 網域
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 瞭解如何將網域從 Google Workspace 移至商務用 Microsoft 365。
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49924999"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>新增 Google Workspace 網域至 Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

新增 Google Workspace 網域至商務用 Microsoft 365，以便持續使用公司電子郵件地址。

## <a name="try-it"></a>試試看吧！

1. 請前往 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
1. 在 Microsoft 365 系統管理中心中，于左側NAV中，選取顯示全部、設定，然後選取網 **域。**
1. 選擇 **新增網域**，輸入您的功能變數名稱，然後選取使用 **這個網域**。 
1. 選擇一 **個 TXT 記錄至** 網域 DNS 記錄，選取 **繼續，然後** 複製 TXT 值。 
1. 回到 Google [管理](https://admin.google.com)主控台，選擇網域、**管理** 網域 **、查看詳細資料**、管理 **網** 域 **、DNS，** 然後向下卷到 **自訂資源記錄**。 
1. 開啟記錄類型下拉式選項，選擇 **TXT，** 貼上您複製的 TXT 值， **然後選取新增**。 

    更新通常會花幾分鐘的時間完成，但最多可能需要 48 小時。 
1. 返回 Microsoft 365 系統管理中心， **選取驗證，** 然後 **關閉**。 
1. 若要將網域設定為使用者的主要電子郵件，請在左側 Nav 中選取使用者  >  **使用中使用者**。 
1. 選擇使用者，**選取管理使用者名稱和** 電子郵件，**編輯**，從下拉清單中選擇您的網域，然後選取完成 **和****儲存變更**。 
1. 為每個使用者重複此程式。 

    完成後，您可以開始安裝 Office App，以及將電子郵件和日曆專案遷移到 Microsoft 365。 