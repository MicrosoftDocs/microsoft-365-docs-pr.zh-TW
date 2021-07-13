---
title: 還原使用者
f1.keywords:
- NOCSH
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
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: 在刪除使用者帳戶後的30天內，您可以還原帳戶和所有資料，而且使用者可以使用相同的帳戶登入。
ms.openlocfilehash: e37f913bcc6a54bdcc1e0f52168fe1aab0c8afdd
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394264"
---
# <a name="restore-a-user"></a>還原使用者
   
只要在刪除使用者帳戶後的 30 天內還原，該帳戶及其所有相關資料都會全部還原。使用者可以透過相同的公司或學校帳戶登入。信箱的內容會完全還原。若您要查詢某個使用者帳戶還剩多少時間可以還原，[請連絡我們](../../business-video/get-help-support.md)。
  
以下是幾個祕訣︰
  
- 請確定授權可指派給該帳戶。
    
- 如果您的公司使用 Active Directory，針對還原使用者帳戶的 instrutcions，請參閱 how [to 疑難排解 Office 365 中已刪除的使用者帳戶](/office365/troubleshoot/active-directory/restore-deleted-user-accounts)。 
    
## <a name="restore-one-or-more-user-accounts"></a>若要還原一或多個使用者帳戶

您必須是 Microsoft 365 全域系統管理員或使用者管理系統管理員，才可執行這些步驟。 

1. 在系統管理中心中，移至 [ **使用者** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">刪除的使用者</a> ] 頁面。

2. 在 [ **刪除的使用者** ] 頁面上，選取您要還原的使用者名稱，然後選取 [ **還原**]。
    
3. 依照提示設定密碼，然後選取 [ **還原**]。
    
4. 若使用者成功還原，請選取 [ **傳送電子郵件並關閉**]。 如果您遇到名稱衝突或 Proxy 位址衝突，請參閱下方說明，了解如何還原這類帳戶。
    
還原使用者後，請確定通知他們密碼已變更，並追蹤這些密碼。
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>還原有使用者名稱衝突的使用者

當您刪除使用者帳戶，以相同的使用者名稱建立新的使用者帳戶 (不論是同一名使用者，還是另一名具有類似名稱的使用者)，稍後又試圖還原已刪除的帳戶時，即會發生名稱衝突的情形。
  
若要修正此問題，您可以將您要還原的使用者帳戶取代作用中的使用者帳戶，或是為您要還原的帳戶指派不同的使用者名稱，以避免產生兩個具相同使用者名稱的帳戶。步驟如下：

1. 在系統管理中心中，移至 [ **使用者** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">刪除的使用者</a> ] 頁面。
  
2. 在 [ **刪除的使用者** ] 頁面上，選取您要還原的使用者名稱，然後選取 [ **還原**]。
    
    > [!NOTE]
    > 若無法還原兩名或多名使用者，一則錯誤訊息會通知您某些使用者的還原作業失敗。請檢視記錄，了解哪些使用者無法順利還原，接著逐一對這些帳戶進行還原作業。 
  
3. 依照提示設定密碼，然後選取 [ **還原**]。
    
4. 隨即會跳出一則訊息，提示您還原帳戶時發生問題。請執行下列其中一項操作：
    
  - 取消還原並重新命名目前作用中的使用者，然後再次嘗試還原。
    
  - 或者，輸入使用者的新主要電子郵件地址，然後選取 [ **還原**]。
    
5. 檢查結果，然後選取 [ **關閉**]。
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>還原 Proxy 位址衝突的使用者

當您刪除包含 Proxy 位址的使用者帳戶、將相同的 Proxy 位址指派給另一個帳戶，然後試圖還原已刪除的帳戶時，會發生 Proxy 位址衝突的情形。請依照下列步驟操作以修正此問題。
  
您必須具備 Microsoft 365 的系統[管理員許可權](about-admin-roles.md)，才可執行此動作。 

1. 在系統管理中心中，移至 [ **使用者** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">刪除的使用者</a> ] 頁面。

2. 在 [ **刪除的使用者** ] 頁面上，選取您要還原的使用者，然後選取 [ **還原**]。 
    
3. 在 [ **還原** ] 頁面上，依照指示設定密碼，然後選取 [ **還原**]。 所有衝突的 Proxy 位址都會自動從您要還原的使用者移除。
    
4. 檢查結果，然後選取 [ **關閉**]。

## <a name="related-content"></a>相關內容

[刪除使用者](delete-a-user.md) (文章) \
 (影片[指派系統管理員角色](assign-admin-roles.md)) \
 (文章) [指派授權給使用者](../manage/assign-licenses-to-users.md)
