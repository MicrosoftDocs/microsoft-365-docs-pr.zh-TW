---
title: 在 Microsoft 365 中管理應用程式的使用者同意
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 瞭解使用者對應用程式的同意，以及如何將其開啟以允許協力廠商應用程式存取使用者的 Microsoft 365 資訊。
ms.openlocfilehash: 629e64494c6d72a13c3b155370a8f47505e9fa20
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391228"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>在 Microsoft 365 中管理應用程式的使用者同意

此設定會控制使用者是否可以同意使用 OpenID 連線的應用程式，以及 OAuth 2.0 以進行登錄和要求存取資料。 您可以從您自己的組織中建立應用程式，也可以從另一部 Office 365 組織或協力廠商來建立。

如果您開啟此設定，這些應用程式會要求使用者有權存取您組織的資料，而且使用者可以選擇是否允許。 如果您關閉此設定，系統管理員必須先同意這些應用程式，使用者才能使用它們。 在此情況下，請考慮在 Azure 入口網站中設定系統管理員同意工作流程，讓使用者可以傳送要求以進行系統管理員核准，以使用任何封鎖的應用程式。

使用者可以授與權限給他們擁有的應用程式存取自己的 Office 365 資訊。 他們無法讓應用程式存取任何其他使用者的資訊。

## <a name="turning-user-consent-on-or-off"></a>開啟或關閉使用者同意

以下說明如何開啟或關閉應用程式的使用者同意。

1. 在系統管理中心中，移至 [**設定** 的 \> **組織設定**  >  [服務](https://go.microsoft.com/fwlink/p/?linkid=2053743)] 頁面，然後選取 [**使用者同意應用程式**]。

2. 在 [ **使用者同意應用程式** ] 頁面上，選取開啟或關閉使用者同意的選項。

## <a name="related-content"></a>相關內容 

[設定系統管理員同意工作流程](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (篇) \
 (文章) 中[管理應用程式的同意和評估同意要求](/azure/active-directory/manage-apps/manage-consent-requests)