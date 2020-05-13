---
title: 瞭解 Microsoft 365 for business 中的訂閱與授權
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7ac93507-0e38-4398-8bfe-9c1d123cb387
description: '深入瞭解 Microsoft 365 for business 中的訂閱與授權，並知道誰可以指派授權，以及當您指派授權給某人時會發生什麼情況。 '
ms.custom: okr_SMB
ms.openlocfilehash: 5178b25de6f66968f8a89c7b2c34ee466f8855bd
ms.sourcegitcommit: 4cfb8a9c3675d0aefcabd690273e2af85f2e38b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44211435"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>瞭解 Microsoft 365 for business 中的訂閱與授權

本文說明訂閱與授權之間的關係，並提供其他有關[誰可以指派授權](#find-out-who-can-assign-licenses)的資訊，[瞭解當您指派授權給某人時所發生的情況](#understand-what-happens-when-you-assign-a-license-to-someone)，以及[人員可以在哪個裝置上安裝 Office](#how-many-devices-can-people-install-office-on)。 此外，它也包含[瞭解非使用者信箱之授權的](#understand-licenses-for-non-user-mailboxes)連結，以及[管理授權的相關文章](#articles-about-managing-licenses)。
  
當您為商務用 Microsoft 365 購買訂閱時，您會註冊一組應用程式和服務，以每月或每年的頻率支付。 您在訂閱中所收到的應用程式和服務，取決於您購買的是哪一種產品，例如 Microsoft 365 Apps for business Standard 或 Microsoft 365 Business Standard。 您可以在「[購買 Microsoft 365」頁面](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)上查看每個產品隨附的功能。 

購買訂閱時，您會依據貴組織中的人數，指定您所需的「授權」數目。 完成購買後，您會為人員建立帳戶，並指派授權給每個人。 當您的組織需要變更時，您可以購買更多授權，以容納新人員，或在某人離開您的組織時，將授權重新指派給其他使用者。 

如果您有多個訂閱，您可以針對每個訂閱指派授權給人員。 例如，您的所有使用者都可以指派給所有 Microsoft 365 應用程式和服務做為 Microsoft 365 商務標準訂閱的一部分，而使用者的子集也可以透過個別的 Visio 訂閱指派給 Visio Online。 

  
## <a name="find-out-who-can-assign-licenses"></a>找出誰可以指派授權

不同類型的系統管理員根據其角色可以有不同的授權處理方式。下表列出最常用的選項。如需系統管理員角色和權限的完整清單，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  
|**系統管理員角色**|**指派授權**|**移除授權**|**購買更多授權**|**刪除帳戶**|
|:-----|:-----|:-----|:-----|:-----|
|全域系統管理員  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|計費系統管理員  <br/> |否  <br/> |否  <br/> |是  <br/> |否  <br/> |
|使用者管理系統管理員  <br/> |是  <br/> |是  <br/> |否  <br/> |是  <br/> |
|服務系統管理員  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|密碼系統管理員  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a>了解當您指派授權給某人時會發生什麼情況

下表列出當您指派授權給某人時會自動發生的情況：
  
|**如果訂閱含有此服務**|**會自動發生以下情況**|
|:-----|:-----|
|Exchange Online  <br/> |系統會為該人員建立信箱。  <br/> 若要瞭解此工作完成的 SLA，請參閱「[設定 ...」Microsoft 365 系統管理中心中的郵件](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center)。 |
|SharePoint Online  <br/> |系統會指派預設 SharePoint Online 小組網站的編輯權限給該人員。  <br/> |
|商務用 Skype Online  <br/> |該人員會獲得授權相關功能的存取權限。  <br/> |
|Microsoft 365 Apps 企業版  <br/> |該人員可在最多 5 部 Mac 或 PC、5 台平板電腦和 5 支智慧型手機上下載 Microsoft Office。  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a>使用者可以在多少部裝置上安裝 Office？

如果您的訂閱包含下列任何產品，每個人員都能在最多 5 部 Mac 或 PC、5 台平板電腦和 5 支智慧型手機上安裝 Office。
  
- Microsoft 365 Apps 商務版
    
- Microsoft 365 商務標準版
    
- Microsoft 365 Apps 企業版
    
- Office 365 Enterprise E3
    
- Office 365 企業版 E5
    
## <a name="understand-licenses-for-non-user-mailboxes"></a>了解非使用者信箱的授權

您不需要指派授權給資源信箱、會議室信箱及共用信箱，除非這些信箱超過其 50 GB 的儲存配額。如需非使用者信箱的詳細資訊，請參閱下列文章：
  
- [建立共用信箱](../../admin/email/create-a-shared-mailbox.md)
    
- [Exchange Online 中的共用信箱](https://go.microsoft.com/fwlink/p/?linkid=847433)，適用于所有其他 Microsoft 365 方案。 
    
- [建立及管理會議室信箱](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- [管理設備信箱](https://go.microsoft.com/fwlink/p/?linkid=847435) (機器翻譯)
    
## <a name="articles-about-managing-licenses"></a>管理授權的相關文章

- [將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md)
    
- [從使用者移除授權](../../admin/manage/remove-licenses-from-users.md)
    
- [購買訂閱授權](buy-licenses.md)
    
- [購買其他訂閱](../buy-another-subscription.md)
    
- [購買或編輯附加元件](../buy-or-edit-an-add-on.md)
    
- [從您的訂閱中移除授權](remove-licenses-from-subscription.md)
    
- [解決授權衝突](../../admin/manage/resolve-license-conflicts.md) (機器翻譯)
    
- [管理 Yammer 使用者授權](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
