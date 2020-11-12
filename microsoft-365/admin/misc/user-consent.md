---
title: 管理使用者對 Microsoft 365 應用程式的同意
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 瞭解使用者對應用程式的同意，以及如何將其開啟以允許協力廠商應用程式存取使用者的 Microsoft 365 資訊。
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999562"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>管理使用者對 Microsoft 365 應用程式的同意

此設定會控制使用者是否可同意使用 OpenID Connect 及 OAuth 2.0 的應用程式，以進行登入及存取資料的要求。 您可以從您自己的組織中建立應用程式，也可以從其他 Office 365 組織或協力廠商來建立應用程式。

如果您開啟此設定，這些應用程式會要求使用者有權存取您組織的資料，而且使用者可以選擇是否允許。 如果您關閉此設定，系統管理員必須先同意這些應用程式，使用者才能使用它們。 在此情況下，請考慮在 Azure 入口網站中設定系統管理員同意工作流程，讓使用者可以傳送要求以進行系統管理員核准，以使用任何封鎖的應用程式。

使用者可以授與權限給他們擁有的應用程式存取自己的 Office 365 資訊。 他們無法讓應用程式存取任何其他使用者的資訊。

## <a name="turning-user-consent-on-or-off"></a>開啟或關閉使用者同意
<a name="__toc379982114"> </a>

以下說明如何開啟或關閉應用程式的使用者同意。

1. 在系統管理中心中，移至 [ **設定** \> **組織設定**  >  [服務](https://go.microsoft.com/fwlink/p/?linkid=2053743)] 頁面，然後選取 [ **使用者同意應用程式** ]。

2. 在 [ **使用者同意應用程式** ] 頁面上，選取開啟或關閉使用者同意的選項。

## <a name="more-info"></a>詳細資訊
<a name="__toc379982114"> </a>

若要瞭解如何在 Azure active directory 中設定同意設定，請參閱 [設定系統管理員同意工作流程](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)。

若要瞭解如何管理使用者對應用程式的同意，請閱讀 [對應用程式的同意並評估同意要求](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)。