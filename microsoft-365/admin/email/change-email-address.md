---
title: 變更電子郵件地址以使用您的自訂網域
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: '將您的初始電子郵件地址變更為類似 tom@fourthcoffee.com 的易記電子郵件地址。 若要這麼做，您必須購買功能變數名稱，並將其新增至 Office 365。 '
ms.openlocfilehash: dc0ab64003b48eec50bf34e60d8a6df463b4fe89
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212030"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>變更電子郵件地址以使用您的自訂網域

 **[檢查網域的常見問題集](../setup/domains-faq.md)** ：供您在找不到所需功能時參考。 
  
::: moniker range="o365-worldwide"

您在 Office 365 中的初始電子郵件地址包括 .onMicrosoft.com，例如 tom@fourthcoffee.onMicrosoft.com。您可以將它改成更好記的位址，例如 tom@fourthcoffee.com。您必須先有自己的網域名稱，例如 fourthcoffee.com。如果您已經有了，那很好！如果還沒有，則可以了解如何[向網域註冊機構購買](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-germany"

您的 Office 365 德國的初始電子郵件地址包括 onmicrosoft.de，例如 tom@fourthcoffee.onmicrosoft.de。 您可以將它變更為更友好的位址（如 tom@fourthcoffee.de）。 您需要自己的功能變數名稱，例如 fourthcoffee.de first。 如果您已經有了，那很好！ 如果還沒有，則可以了解如何[向網域註冊機構購買](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-21vianet"

您在由世紀運作的 Office 365 中的初始電子郵件地址包括 partner.onmschina.cn，例如 tom@fourthcoffee.partner.onmschina.cn。 您可以將它變更為更友好的位址（如 tom@fourthcoffee.cn）。 您需要自己的功能變數名稱，例如 fourthcoffee.cn first。 如果您已經有了，那很好！ 如果還沒有，則可以了解如何[向網域註冊機構購買](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

如果您在設定期間更新網域的 MX 記錄，藉此將網域的電子郵件變更為寄送至 Office 365，寄送至該網域的「所有」電子郵件將開始寄送至 Office 365。請確定您已經先在 Office 365 中為在您網域上有電子郵件的每個人新增使用者並建立信箱，然後再變更 MX 記錄。假如不想將您網域上每個人的電子郵件都移動到 Office 365，可以採取相關步驟[改為只使用幾個電子郵件地址來試驗 Office 365](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx)。
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心變更您的電子郵件地址以使用您的自訂網域

您必須具有全域管理員帳戶，才可執行這些步驟。 

::: moniker range="o365-worldwide"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的系統管理中心。 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. 移至 admin center，網址<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>為。 

::: moniker-end 

2. 移至 [**安裝** > **網域**] 頁面。 

3. 在 [**網域**] 頁面上，選取 [**新增網域**]。
    
4. 遵循步驟操作，確認您擁有該網域並變更您的電子郵件地址。
    
系統將引導您完成在 Office 365 正確設定您的網域的所有操作。

> [!NOTE]
> 如果您不是使用 Exchange 授權，則無法使用網域從 Office 365 租使用者傳送或接收電子郵件。
  
## <a name="related-articles"></a>相關文章

[購買使用 Office 365 的自訂網域](../get-help-with-domains/buy-a-domain-name.md)
 
