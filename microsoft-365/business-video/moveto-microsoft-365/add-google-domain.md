---
title: 新增 Google Workspace 網域
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何將網域從 Google Workspace 移至 Microsoft 365 for business。
ms.openlocfilehash: 1abc05867147d2b52e26804918e8247053b5e1d5
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794617"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>將 Google Workspace 網域新增至 Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

將 Google Workspace 網域新增至 Microsoft 365 for business，以便您可以繼續使用您的商務電子郵件地址。

## <a name="try-it"></a>試試看吧！

1. 移至 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
1. 在 Microsoft 365 系統管理中心的左側導覽中，選取 [ **全部顯示**]、[ **設定** ] 及 [ **網域**]。
1. 選擇 [ **新增網域**]，輸入您的功能變數名稱，然後選取 [ **使用此網域**]。 
1. 選擇、 **將 txt 記錄新增至網域的 DNS 記錄** 中，選取 [ **繼續**]，然後複製 TXT 值。 
1. 請回到 Google 系統 [管理主控台](https://admin.google.com)、選擇 [ **網域**]、[ **管理網域**]、[ **查看詳細資料**]、[ **網域**]、[ **DNS**]，然後向下滾動至 **自訂資源記錄**。 
1. 開啟 [記錄類型] 下拉式清單，選擇 [ **txt**]，貼上您複製的 TXT 值，然後選取 [ **新增**]。 

    更新通常會在幾分鐘內取得，但可能需要長達48小時。 
1. 回到 Microsoft 365 系統管理中心，選取 [ **驗證**]，然後按一下 [ **關閉**]。 
1. 若要將您的網域設為使用者的主要電子郵件，請在左側流覽中選取 [**使用者** 作用中  >  **使用者**]。 
1. 選擇使用者，選取 [ **管理使用者名稱和電子郵件**]，[ **編輯**]，從下拉式清單中選取您的網域，然後選取 [ **完成** ] 並 **儲存變更**。 
1. 針對每個使用者重複此程式。 

    當您完成時，您就可以安裝 Office 應用程式，並將電子郵件和行事曆專案遷移至 Microsoft 365。 