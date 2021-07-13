---
title: 為您的組織設定混亂
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
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: '瞭解如何使用 Exchange PowerShell 來啟用或停用組織中所有或特定使用者的雜亂功能。 '
ms.openlocfilehash: 91098047bdf2ab8190283990bdc6b0292e3e57ba
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393976"
---
# <a name="configure-clutter-for-your-organization"></a>為您的組織設定混亂

> [!TIP]
> [焦點收件](../setup/configure-focused-inbox.md) 匣即將取代雜亂的收件匣。 深入瞭解： [更新焦點收件匣和待過濾的計畫](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
身為系統管理員，您可能需要在 Microsoft 365 中管理雜亂功能。 若要開啟/關閉組織中使用者的雜亂功能，您必須使用 Exchange PowerShell。  (個人可以使用這些指示將其開啟/關閉：[在 Outlook 中關閉/開啟雜亂功能](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)。
  
[使用具有 Exchange Online](/powershell/exchange/exchange-online-powershell)和連線的 PowerShell，查看[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) ，以取得使用 Exchange PowerShell 的詳細資料。 您必須具有至少具備 Exchange 服務系統管理員角色的帳戶，以及使用 PowerShell 連線到 Exchange Online 的許可權。 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>使用 Exchange PowerShell 開啟雜亂

您可以執行 [Set-Clutter](/powershell/module/exchange/set-clutter) Cmdlet，手動為信箱啟用雜亂功能。 您也可以執行 [Get-Clutter](/powershell/module/exchange/get-clutter) Cmdlet，以查看組織中信箱的雜亂設定。 
  
針對名為 Allie 的單一使用者開啟雜亂 Bellew
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>使用 Exchange PowerShell 關閉雜亂功能

您可以執行 [Set-Clutter](/powershell/module/exchange/set-clutter) Cmdlet，手動停用信箱的雜亂。 您也可以執行 [Get-Clutter](/powershell/module/exchange/get-clutter) Cmdlet，以查看組織中信箱的 **雜亂** 設定。 
  
針對名為 Allie Bellew 的單一使用者關閉雜亂：
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

如果您使用 PowerShell 大量建立使用者，則必須針對每個使用者的信箱執行 [Set-Clutter](/powershell/module/exchange/set-clutter) ，以管理雜亂。 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>何時對 Outlook 網頁版中的使用者顯示雜亂的功能？
<a name="bkmk_onoff"> </a>

身為系統管理員，您可以使用 Exchange PowerShell 重新啟用雜亂功能。 完成此動作後，焦點收件匣會關閉，而雜亂的功能將會重新成為作用中。 
  
 **如果您使用的是 Microsoft 365 商務進階版訂閱 Outlook 網頁版：**
  
- 如果使用者目前已啟用雜亂功能： 
    
  - 會出現雜亂設定
    
- 如果使用者目前已啟用焦點收件匣： 
    
  - 不會出現雜亂設定
    
- 如果沒有啟用雜亂或焦點收件匣： 
    
  - 雜亂及焦點收件匣會顯示為使用者郵件中的選項設定
    
 **如果您使用的是 Outlook .com：**
  
- 如果使用者目前已啟用雜亂功能： 
    
  - 會出現雜亂設定
    
- 如果使用者目前已啟用焦點收件匣： 
    
  - 不會出現雜亂設定
    
- 如果沒有啟用雜亂或焦點收件匣： 
    
  - 雜亂及焦點收件匣會顯示為使用者郵件中的選項設定
    
- 如果使用者在過去某點啟用焦點收件匣：
    
  - 將永遠不會出現雜亂設定
    
    否則 
    
  - 會出現雜亂設定
    
## <a name="related-content"></a>相關內容

[使用雜亂 Outlook (文章中的低優先順序郵件進行排序](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)) \
使用雜亂專案 (文章) \[中排序低優先順序郵件](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
[在 Outlook (文章中關閉雜亂](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)) 
