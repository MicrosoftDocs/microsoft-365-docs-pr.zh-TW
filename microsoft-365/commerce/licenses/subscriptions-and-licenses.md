---
title: 瞭解商務 Microsoft 365 中的訂閱與授權
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: 您收到的應用程式和服務取決於您購買的 Microsoft 365 產品，例如 Microsoft 365 Apps 商務版。
ms.date: 07/01/2020
ms.openlocfilehash: 817ea454bf471fdc2f175658af9030925d29189a
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779876"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>瞭解商務 Microsoft 365 中的訂閱與授權

當您購買商務用 Microsoft 365 訂閱時，您會註冊一組應用程式和服務，您可以使用每月或每年的頻率支付。 您在訂閱中所收到的應用程式和服務，取決於您購買的產品，例如 Microsoft 365 Apps 商務版或 Microsoft 365 商務標準版。 您可以在中小型企業頁面上看到每個產品的[Microsoft 365](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1) 。

購買訂閱時，您會依據貴組織中的人數，指定您所需的「授權」數目。 購買訂閱後，您會為組織中的人員建立帳戶，然後將授權指派給每個人。 當您的組織需要變更時，您可以購買更多授權，以容納新人員，或在某人離開您的組織時，將授權重新指派給其他使用者。

如果您有多個訂閱，您可以針對每個訂閱指派授權給人員。 例如，您可以將所有的使用者指派給所有 Microsoft 365 的應用程式和服務，成為 Microsoft 365 商務標準版訂閱的一部分。 您也可以指派使用者的子集，以透過個別 Visio 訂閱 Visio 線上。

## <a name="how-many-devices-can-people-install-office-on"></a>使用者可以在多少部裝置上安裝 Office？

如果您的訂閱包含下列任何產品，每個人都可以在最多五部 pc 或 Mac、五部平板電腦和五部電話上安裝 Office。

:::row:::
   :::column span="":::
        -Microsoft 365 Apps 商務版 Microsoft 365 Apps 企業版 Microsoft 365 商務標準版 Microsoft 365 商務進階版 Microsoft 365 A3-Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        -Microsoft 365 E3 Microsoft 365 E5 Office 365 A1 + Office 365 A3 Office 365 A5 E3-Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>當您指派授權給某人時會發生什麼情況？

下表列出當您指派授權給某人時會自動發生的情況：
  
|**如果訂閱含有此服務**|**會自動發生以下情況**|
|:-----|:-----|
|Exchange Online  <br/> |系統會為該人員建立信箱。 <br/> 若要瞭解此工作完成的 SLA，請參閱「[設定 ...」Microsoft 365 系統管理中心中的郵件](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)。 |
|SharePoint Online  <br/> |系統會指派預設 SharePoint Online 小組網站的編輯權限給該人員。  <br/> |
|商務用 Skype Online  <br/> |人員可以存取與授權相關聯的功能。  <br/> |
|Microsoft 365 Apps 企業版  <br/> |使用者最多可以在五台的 mac 或電腦、五台平板電腦和五部 smartphone 上下載 Office 應用程式。  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>了解非使用者信箱的授權

您不需要指派授權給資源信箱、會議室信箱及共用信箱，除非這些信箱超過其 50 GB 的儲存配額。如需非使用者信箱的詳細資訊，請參閱下列文章：
  
- [建立共用信箱](../../admin/email/create-a-shared-mailbox.md)
- [從共用信箱中移除授權](../../admin/email/remove-license-from-shared-mailbox.md)
- 所有其他 Microsoft 365 計畫的[Exchange Online 中的共用信箱](/exchange/collaboration-exo/shared-mailboxes)。

## <a name="who-can-assign-licenses"></a>神秘可以指派授權？

不同類型的系統管理員根據其角色可以有不同的授權處理方式。下表列出最常用的選項。如需系統管理員角色和權限的完整清單，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  
|**系統管理員角色**|**指派授權**|**取消指派授權**|**購買更多授權**|**刪除帳戶**|
|:-----|:-----|:-----|:-----|:-----|
|計費系統管理員  <br/> |否  <br/> |否  <br/> |是  <br/> |否  <br/> |
|全域系統管理員  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|授權系統管理員 <br/> |是 <br/>|是 <br/> |否 <br/> |否 <br/> |
|服務支援系統管理員  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|使用者系統管理員  <br/> |是  <br/> |是  <br/> |否  <br/> |是  <br/> |

## <a name="related-content"></a>相關內容

[購買或移除商務用訂閱的授權](buy-licenses.md) (文章) \
[將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md) (文章)\
[取消指派給使用者的授權](../../admin/manage/remove-licenses-from-users.md) (文章)\
[從共用信箱移除授權](../../admin/email/remove-license-from-shared-mailbox.md) (文章)
