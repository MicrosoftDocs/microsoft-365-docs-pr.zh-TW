---
title: 變更電子郵件地址以使用您的自訂網域
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 購買功能變數名稱並將其新增至 Microsoft 365，將您的電子郵件地址變更為易記的電子郵件地址（例如 tom@fourthcoffee.com）。
ms.openlocfilehash: 1a248cb67bab5d0467cad35dc5be8023b8013a12
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635519"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>變更電子郵件地址以使用您的自訂網域

 若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。 
  
::: moniker range="o365-worldwide"

您的 Microsoft 365 包括 onmicrosoft.com （如 tom@fourthcoffee.onmicrosoft.com）中的初始電子郵件地址。 您可以將它改成更好記的位址，例如 tom@fourthcoffee.com。 您必須先有自己的網域名稱，例如 fourthcoffee.com。 如果您已經有了，那很好！ 如果還沒有，則可以了解如何[向網域註冊機構購買](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-germany"

Office 365 德國的初始電子郵件地址包括 onmicrosoft.de，例如 tom@fourthcoffee.onmicrosoft.de。 您可以將它變更為更友好的位址（如 tom@fourthcoffee.de）。 您需要自己的功能變數名稱，例如 fourthcoffee.de first。 如果您已經有了，那很好！ 如果還沒有，則可以了解如何[向網域註冊機構購買](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-21vianet"

由世紀運作的 Office 365 中的初始電子郵件地址包含 partner.onmschina.cn，例如 tom@fourthcoffee.partner.onmschina.cn。 您可以將它變更為更友好的位址（如 tom@fourthcoffee.cn）。 您需要自己的功能變數名稱，例如 fourthcoffee.cn first。 如果您已經有了，那很好！ 如果還沒有，則可以了解如何[向網域註冊機構購買](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

當您將網域的電子郵件變更為 Microsoft 365，當您在設定期間更新網域的 MX 記錄時，所有傳送至該網域的電子郵件都會開始進行 Microsoft 365。 在您變更 MX 記錄之前，請確定已在 Microsoft 365 中為已在您的網域上擁有電子郵件的所有人新增使用者並建立信箱。 不想將您網域中的每個人的電子郵件移至 Microsoft 365 嗎？ 您可以[只使用少量的電子郵件地址，進行試驗 Microsoft 365 的](../misc/pilot-microsoft-365-from-my-custom-domain.md)步驟。
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心變更您的電子郵件地址以使用您的自訂網域

您必須具有全域管理員帳戶，才可執行這些步驟。 

::: moniker range="o365-worldwide"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的系統管理中心。 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. 移至 admin center，網址<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>為。 

::: moniker-end 

2. 移至 [**安裝**  >  **網域**] 頁面。 

3. 在 **[網域]** 頁面上，選取 **[新增網域]**。
    
4. 遵循步驟操作，確認您擁有該網域並變更您的電子郵件地址。
    
您將會引導您在 Microsoft 365 中，讓您的網域正確設定所有專案。

> [!NOTE]
> 如果您未使用 Exchange 授權，則無法使用網域從 Microsoft 365 租使用者傳送或接收電子郵件。
  
## <a name="related-content"></a>相關內容

[使用 Microsoft 365 (文章購買自訂網域](../get-help-with-domains/buy-a-domain-name.md)) \
[管理網域](../get-help-with-domains/index.yml) (連結頁面) \
[網域常見問題集](../setup/domains-faq.yml) (文章)