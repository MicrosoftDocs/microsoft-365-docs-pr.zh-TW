---
title: 為您的組織設定待過濾郵件
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: '了解如何啟用或停用待過濾郵件功能的所有或使用 Exchange PowerShell 中您的組織，特定的使用者。 '
ms.openlocfilehash: 65aa614095ecbebaad3d7eb38af1e74166ce20ac
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251703"
---
# <a name="configure-clutter-for-your-organization"></a>為您的組織設定待過濾郵件

> [!TIP]
> [焦點收件匣](../setup/configure-focused-inbox.md)將要取代待過濾郵件。 了解更多：[焦點收件匣和待過濾郵件我們計劃的更新](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
身為系統管理員，您可能要管理 Office 365 中的 [待過濾郵件] 功能。 若要開啟開啟/關閉待過濾郵件功能的使用者在組織中，您必須使用 Exchange PowerShell。 (個人可以將它開啟開/關使用這些指示：[關閉/使用待過濾郵件在 Outlook 中開啟](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)。) 
  
如需使用 Exchange PowerShell 的詳細資訊請參閱[Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831)和[Exchange Online PowerShell 連線到](https://go.microsoft.com/fwlink/?LinkID=722415)。 您必須擁有帳戶至少具備 Exchange 服務系統管理員角色和能夠連線至 Exchange Online powershell。 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>使用 Exchange PowerShell 在開啟待過濾郵件

您可以啟用待過濾郵件手動信箱透過執行[Set-clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet。 您也可以執行[Get-clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet，來檢視您組織中的信箱的待過濾郵件設定。 
  
開啟單一使用者名稱為 Allie Bellew 待過濾郵件
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>關閉待過濾郵件使用 Exchange PowerShell

您可以停用待過濾郵件手動信箱執行[Set-clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet。 您也可以執行[Get-clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet，來檢視您組織中的信箱的**待過濾郵件**設定。 
  
關閉單一使用者名稱為 Allie Bellew 待過濾郵件：
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

如果您使用 PowerShell 大量建立您的使用者，則您必須先執行[Set-clutter](https://go.microsoft.com/fwlink/?LinkID=834446)針對管理待過濾郵件的每位使用者的信箱。 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>開啟/關閉切換待過濾郵件時顯示在網頁型 Outlook 中的使用者？
<a name="bkmk_onoff"> </a>

身為系統管理員，您可以重新啟用待過濾郵件使用 Exchange PowerShell。 完成之後，將會關閉焦點收件匣和待過濾郵件是作用中一次。 
  
 **如果您使用網頁型 Outlook 與 Office 365 商務版訂閱：**
  
- 如果使用者目前已啟用的待過濾郵件： 
    
  - 會顯示待過濾郵件設定
    
- 如果使用者目前是否有焦點收件匣啟用： 
    
  - 將不會出現待過濾郵件設定
    
- 如果已啟用未待過濾郵件或焦點收件匣： 
    
  - 待過濾郵件與焦點收件匣會顯示為使用者的郵件設定] 中的選項
    
 **如果您使用 Outlook.com:**
  
- 如果使用者目前已啟用的待過濾郵件： 
    
  - 會顯示待過濾郵件設定
    
- 如果使用者目前是否有焦點收件匣啟用： 
    
  - 將不會出現待過濾郵件設定
    
- 如果已啟用未待過濾郵件或焦點收件匣： 
    
  - 待過濾郵件與焦點收件匣會顯示為使用者的郵件設定] 中的選項
    
- 如果使用者在過去中有些時候啟用焦點收件匣：
    
  - 永遠不會出現待過濾郵件設定
    
    否則， 
    
  - 將會出現待過濾郵件設定
    
## <a name="related-articles"></a>相關文章
<a name="bkmk_onoff"> </a>

[若要排序低優先順序的郵件，在 Outlook 中使用待過濾郵件](https://support.office.com/article/7755ebf5-4585-469b-b1ab-8b12425c6b6b.aspx)
    
[用來排序低優先順序的郵件，在 OWA 中的待過濾郵件](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[關閉 Outlook 中的待過濾郵件](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

