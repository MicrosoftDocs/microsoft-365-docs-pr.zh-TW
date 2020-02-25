---
title: 比較封鎖存取 Office 365 的方法
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: 了解如何當員工離開組織時，封鎖 Office 365 存取權限。
ms.openlocfilehash: 3aafef37a43747557ef9a3fcda8ffe0fe3713717
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254328"
---
# <a name="compare-ways-to-block-access-to-office-365"></a>比較封鎖存取 Office 365 的方法

當員工離開組織，很好的字詞或損毀上, 您要封鎖其 Office 365 存取權。 以下是幾種方法，您可以這麼做。
  
||||
|:-----|:-----|:-----|
|**若要封鎖存取的方式** <br/> |**定義** <br/> |**最佳做法** <br/> |
|封鎖登入  <br/> |封鎖使用者存取 Office 365 的一種方式是將他們登入的狀態變更為**登入封鎖**。 這會禁止使用者從他們的電腦登入 Office 365 和行動裝置但是他們仍然可以檢視先前下載或同步處理電子郵件和文件。 如果您正在使用 Blackberry 企業服務，您可以一併停用那里其存取。  <br/> |當員工離開組織計劃或他們計劃要進行長期請假時使用。  <br/> |
|重設使用者密碼  <br/> |若要防止使用者存取 Office 365 的另一個方法是重設其密碼。 這會防止他們使用自己的帳戶，但是他們仍然可以檢視先前已下載或同步處理的電子郵件和文件。 您可以然後為他們登入，並將密碼變更為您所選擇的其中一個。  <br/> |當員工離開突然和永久和您覺得有使用此連接器是商務資料的考量。  <br/> |
|移除所有指派授權  <br/> |另一個選項是要移除任何指派給使用者的 Office 365 授權。 這會防止它們使用的網頁伺服器、 Yammer 與 SharePoint Online 的應用程式和服務，例如 Office 套件、 Office 應用程式。 他們仍可以登入，但是不能使用這些服務。  <br/> |當您認為這位使用者無法再使用此連接器必須在 Office 365 中的特定功能的存取權。  <br/> <br> **重要：** 當您移除授權時，將會 30 天內刪除使用者的信箱。
   
## <a name="related-articles"></a>相關文章

[登出 Office 365 中的使用者](../add-users/remove-former-employee.md)
    
[重設 Office 365 中的使用者的密碼](../add-users/reset-passwords.md)
    
[在商務用 Office 365 中指派授權給使用者](../manage/assign-licenses-to-users.md)
    
[在商務用 Office 365 中從使用者移除授權](../manage/remove-licenses-from-users.md)
    

