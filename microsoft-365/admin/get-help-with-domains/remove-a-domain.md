---
title: 移除網域
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: 瞭解如何從 Microsoft 365 中移除舊的網域，並將使用者和群組移至另一個網域或取消您的訂閱。
ms.openlocfilehash: deec298dda037009e2c66f1b686396c689ecd883
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683352"
---
# <a name="remove-a-domain"></a>移除網域
  
 若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。 
  
您移除的是您的網域，因為您想要將它新增至不同的 Microsoft 365 訂閱計畫嗎？ 還是您只想取消訂閱？ 您可以[變更您的方案或訂閱](../../commerce/subscriptions/switch-to-a-different-plan.md)或[取消您的訂閱](../../commerce/subscriptions/cancel-your-subscription.md)。
  
### <a name="step-1-move-users-to-another-domain"></a>步驟1：將使用者移至另一個網域

#### <a name="move-users"></a>移動使用者

::: moniker range="o365-worldwide"

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">[系統管理中心]</a>。

::: moniker-end

::: moniker range="o365-germany"

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[系統管理中心]</a>。  

::: moniker-end

::: moniker range="o365-21vianet"

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[系統管理中心]</a>。  

::: moniker-end

2. 選取 [**使用者** 作用  >  中 **使用者**]。

3. 選取您要移動之所有使用者之名稱旁的方塊。

4. ，然後選擇 [ **變更網域**]。

5. 在 [ **變更網域** ] 窗格中，選取另一個網域。

如果您所處的網域也是您要移除的網域，您也必須為自己執行這個程序。為您的帳戶編輯網域時，您必須先登出，然後使用您選擇的新網域重新登入，才能繼續執行。

#### <a name="move-yourself"></a>自行移動

::: moniker range="o365-worldwide"

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">[系統管理中心]</a>。

::: moniker-end

::: moniker range="o365-germany"

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[系統管理中心]</a>。  

::: moniker-end

::: moniker range="o365-21vianet"

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[系統管理中心]</a>。  

::: moniker-end

2. 移至 [ **使用者** 作用 \> 中 **使用者**]，然後從清單中選取您的帳戶。

3. 在 [ **帳戶** ] 索引標籤上，選取 [ **管理使用者名稱**]，然後選擇不同的網域。
  
4. 在頂端，選取您的帳戶名稱，然後選取 **[登出]。**

5. 使用新的網域登入，並使用相同的密碼登入。

您也可以使用 PowerShell 將使用者移至另一個網域。如需詳細資訊，請參閱 [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0&preserve-view=true) (英文)。若要設定預設網域，請使用 [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0&preserve-view=true) (英文)。

### <a name="step-2-move-groups-to-another-domain"></a>步驟2：將群組移至另一個網域

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 [ **群組** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a> ] 頁面。

::: moniker-end
::: moniker range="o365-germany"

1. 在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [ **群組** > **群組** ] 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [ **群組** > **群組** ] 頁面。

::: moniker-end
  
2. 選取組名，然後在 [**電子郵件地址，主要** **] 索引** 標籤底下，選取 [**編輯**]。

3. 使用下拉式清單選擇另一個網域。

4. 選取 **[儲存]**，再選取 **[關閉]**。 針對與您要移除之網域關聯的任何群組或通訊群組清單，重複這個程序。

### <a name="step-3-remove-the-old-domain"></a>步驟3：移除舊的網域

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 [ **安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">網域</a> ] 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 [ **安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">網域</a> ] 頁面。

::: moniker-end
  
2. 在 [ **網域** ] 頁面上，選取您要移除的網域。

3. 在右窗格中，選取 [ **移除**]。

4. 遵循任何其他提示，然後選取 [ **關閉**]。

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>移除網域需要多久的時間？

如果不是在許多地方（如安全性群組、通訊群組清單、使用者及 Microsoft 365 群組）中參照，則 Microsoft 365 移除網域可能需要很少五分鐘的時間。 如果有許多參照都使用此網域，就會花費數小時 (一天) 的時間才能將網域移除。
  
如果您有數百名或數千名使用者，請使用 PowerShell 來查詢所有使用者，然後將他們移到另一個網域。否則，UI 中很可能會遺失一些使用者，當您隨後想移除此網域時，將無法執行且不知道原因為何。如需詳細資訊，請參閱 [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0&preserve-view=true) (英文)。若要設定預設網域，請使用 [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0&preserve-view=true) (英文)。
  
## <a name="still-need-help"></a>仍需要協助嗎？

::: moniker range="o365-worldwide"

> [!NOTE]
> 您無法移除帳戶中的 [".onmicrosoft.com"](../setup/domains-faq.yml) 網域。 當您移除網域時，使用者帳戶會回復為 "onmicrosoft.com" 位址，成為主要 SMTP/UserprincipalName。
  
仍無法運作嗎？您的網域可能需要手動移除。[打電話給我們](../../business-video/get-help-support.md)，我們會協助您處理。
  
::: moniker-end

::: moniker range="o365-germany"

> [!NOTE]
> 您無法從您的帳戶移除 ["onmicrosoft.de"](../setup/domains-faq.yml) 網域。 當您移除網域時，使用者帳戶會回復為 "onmicrosoft.de" 位址，成為主要 SMTP/UserprincipalName。
  
仍無法運作嗎？您的網域可能需要手動移除。[打電話給我們](../../business-video/get-help-support.md?view=o365-germany&preserve-view=true)，我們會協助您處理。
  
::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> 您無法從您的帳戶移除 ["partner.onmschina.cn"](../setup/domains-faq.yml) 網域。 當您移除網域時，使用者帳戶會回復為 "partner.onmschina.cn" 位址，成為主要 SMTP/UserprincipalName。
  
仍無法運作嗎？您的網域可能需要手動移除。[打電話給我們](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true)，我們會協助您處理。
  
::: moniker-end

## <a name="related-content"></a>相關內容

[網域常見問題集](../setup/domains-faq.yml) (文章)
[切換至不同 Microsoft 365 的 business plan](../../commerce/subscriptions/switch-to-a-different-plan.md) (文章) 
 (文章) [取消您的訂閱](../../commerce/subscriptions/cancel-your-subscription.md)