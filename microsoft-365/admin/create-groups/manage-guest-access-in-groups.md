---
title: 管理 Microsoft 365 群組中的來賓存取
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: 瞭解如何將來賓新增至 Microsoft 365 群組、查看來賓使用者，以及使用 PowerShell 控制來賓存取。
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571934"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>管理 Microsoft 365 群組中的來賓存取

根據預設，會為您的組織開啟 Microsoft 365 群組的來賓存取。 系統管理員可以控制是否允許來賓存取整個組織或個別群組的群組。

當其開啟時，群組成員可以透過網頁上 Outlook 邀請來賓使用者加入 Microsoft 365 群組。 邀請會傳送給群組擁有者以供核准。

一旦核准，就會將來賓使用者新增至目錄和群組。

> [!Note]
> Yammer 原生模式或[EU 地理](/yammer/manage-security-and-compliance/manage-data-compliance)位置不支援網路來賓的 Enterprise 網路。
> Microsoft 365連線 Yammer 群組目前不支援來賓存取，但您可以在 Yammer 網路中建立未連線的外部群組。 如需相關指示，請參閱[建立及管理 Yammer 中的外部群組](/yammer/work-with-external-users/create-and-manage-external-groups)。

群組中的來賓存取通常是用來包括 SharePoint 或 Teams 的更廣泛案例的一部分。 這些服務有自己的來賓共用設定。 如需在群組、SharePoint 及 Teams 中設定來賓共用的完整指示，請參閱：

- [在網站中與來賓共同作業](../../solutions/collaborate-in-site.md)
- [在小組中與來賓共同作業](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>管理群組來賓存取

如果您想要啟用或停用群組中的「來賓存取」，您可以在 Microsoft 365 系統管理中心進行。

1. 在系統管理中心中，移至 [**顯示所有** \> **設定** \> **組織設定**]，然後在 [**服務**] 索引標籤上，選取 [ **Microsoft 365 群組**]。
  
2. 在 [ **Microsoft 365 群組**] 頁面上，選擇您是否要讓組織外部人員存取群組資源，或讓群組擁有者將組織外部人員新增至群組。

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>從系統管理中心新增來賓至 Microsoft 365 群組

如果您的目錄中已存在來賓，您可以從 Microsoft 365 系統管理中心將其新增至您的群組。 具有動態成員資格的 (群組必須[在 Azure Active Directory 中管理](/azure/active-directory/enterprise-users/groups-create-rule)。 ) 
  
1. 在系統管理中心中，移至 [**群組**  >  **群組**] 頁面。
  
2. 按一下您要新增來賓的群組，然後選取 [**成員**] 索引標籤上的 [**全部查看] 和 [管理成員**]。 
  
4. 選取 [ **新增成員**]，然後選擇您要新增的客人名稱。
    
5. 選取 [儲存 **]**。

如果您想要直接將來賓新增至目錄，您可以[在 Azure 入口網站中新增 Azure Active Directory B2B](/azure/active-directory/b2b/add-users-administrator)共同作業使用者。

如果您想要編輯來賓的任何資訊，可以[使用 Azure Active Directory 新增或更新使用者的設定檔資訊](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。

## <a name="related-content"></a>相關內容

[從特定群組封鎖來賓使用者](../../solutions/per-group-guest-access.md) (文章) 

[管理 Microsoft 365 系統管理中心的群組成員資格](add-or-remove-members-from-groups.md) (文章) 
  
[Azure Active Directory 存取評論](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (文章) 

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (文章) 