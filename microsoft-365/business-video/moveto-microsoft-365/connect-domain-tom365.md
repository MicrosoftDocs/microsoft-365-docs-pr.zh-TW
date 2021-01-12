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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何將您的網域連接至 Microsoft 365。
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794601"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>將您的網域連線至 Microsoft 365 for business

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

當您設定 Microsoft 365 並將電子郵件資料從 Google Workspace 移出後，您就可以將您的網域連線至 Microsoft 365。 

首先，您將需要從 Google 刪除現有的 DNS 記錄，然後我們可以從 Microsoft 365 新增 DNS 記錄。

## <a name="try-it"></a>試試看吧！

1. 在 [admin.google.com](https://admin.google.com)中登入 Google Workspace 管理主控台。
1. 選取 [ **網域**]、[ **管理網域**]、[ **查看詳細資料**]、[ **管理網域**] 及左導覽中的 [ **DNS** ]
1. 向下滾動至 **綜合記錄**，開啟 **Google Workspace**，選取 [ **刪除**]，然後重新 **刪除** 。
1. 向下滾動至 **自訂資源記錄** ，並刪除任何出現的現有 DNS 記錄，包括您先前針對 Microsoft 365 建立的任何 DNS 記錄。
1. 移至 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
1. 在左側導覽中，選擇 [ **全部顯示**]、[ **設定**]、[ **網域**]。
1. 然後選擇您的預設網域。
1. 選取 [ **繼續安裝**]，然後按一下 [  **繼續**]。
1. 向中向左下以查看需要複製到 Google 的 DNS 記錄。
1. 開啟 **MX 記錄**，然後在 [ **指向位址] 或 [值**] 底下複製記錄。
1. 回到 Google，然後在 [ **自訂資源記錄** ] 區段中，開啟 [記錄類型] 下拉式清單，然後選取 [ **MX**]。
1. 在 [ **資料** ] 欄位中，貼上您複製的記錄。
1. 然後選取 **[新增]**。
1. 針對 CNAME 和 TXT 記錄重複此程式，並在 [Google DNS 管理] 頁面中新增值。
1. 回到 Microsoft 365 系統管理中心，然後選取 [ **繼續**]。

    您的網域設定已完成。