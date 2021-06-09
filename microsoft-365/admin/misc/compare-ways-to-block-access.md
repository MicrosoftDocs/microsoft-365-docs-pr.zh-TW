---
title: 比較封鎖存取的方式
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
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: 瞭解如何在員工離開組織時，封鎖 Microsoft 365 的存取權。
ms.openlocfilehash: b913655065d4c57322aee6dc04e53f7a35cf5760
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399431"
---
# <a name="compare-ways-to-block-access"></a>比較封鎖存取的方式

當員工休假或不良時，您必須封鎖他們對 Microsoft 365 的存取。 以下是一些您可以執行這項作業的方法。
  
||||
|:-----|:-----|:-----|
|**封鎖存取的方式** <br/> |**定義** <br/> |**最佳做法** <br/> |
|封鎖登入  <br/> |封鎖使用者存取 Microsoft 365 的一種方式是將其登入狀態變更為 [已 **封鎖登入**]。 這可防止他們從其電腦和行動裝置登入 Microsoft 365，但他們仍可查看先前下載或同步處理的電子郵件和檔。 如果您是使用 Blackberry Enterprise 服務，您也可以停用其存取權。  <br/> |當員工計畫離開組織或打算進行長期請假時使用。  <br/> |
|重設使用者密碼  <br/> |防止使用者存取 Microsoft 365 的另一種方式是重設其密碼。 這樣做可以防止使用者使用他們的帳戶，但是他們仍然可以查看先前下載或同步處理的電子郵件和檔。 您可以接著登入，並將密碼變更為您所選擇的其中一個。  <br/> |當員工突然且永久離職時使用，而您覺得商務資料有問題。  <br/> |
|移除所有指派的授權  <br/> |另一種方法是移除指派給使用者的任何 Microsoft 365 授權。 這樣可防止使用者使用 Office 套件等應用程式和服務、Office web 應用程式、Yammer 和 SharePoint 線上。 他們仍可登入，但無法使用這些服務。  <br/> |當您感覺此使用者不再需要存取 Microsoft 365 中的特定功能時，請使用此功能。  <br/> <br> **重要：** 當您移除授權時，使用者的信箱將會在30天內刪除。
   
## <a name="related-articles"></a>相關文章

[從 Microsoft 365 下架使用者](../add-users/remove-former-employee.md)
    
[在 Microsoft 365 中重設使用者的密碼](../add-users/reset-passwords.md)
    
[在商務用 Microsoft 365 中指派授權給使用者](../manage/assign-licenses-to-users.md)
    
[在商務用 Microsoft 365 中移除使用者的授權](../manage/remove-licenses-from-users.md)
    

