---
title: 變更電子郵件地址以使用您的自訂網域
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: '變更您的初始電子郵件地址的易記電子郵件地址，例如 tom@fourthcoffee.com。 若要這麼做，您需要購買網域名稱，並將其新增至 Office 365。 '
ms.openlocfilehash: 3e01f0bfb97fbef762fbd7162944ca25d882f142
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251710"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>變更電子郵件地址以使用您的自訂網域

 **[檢查網域的常見問題集](../setup/domains-faq.md)** ：供您在找不到所需功能時參考。 
  
::: moniker range="o365-worldwide"

您在 Office 365 中的初始電子郵件地址包括 .onMicrosoft.com，例如 tom@fourthcoffee.onMicrosoft.com。您可以將它改成更好記的位址，例如 tom@fourthcoffee.com。您必須先有自己的網域名稱，例如 fourthcoffee.com。如果您已經有了，那很好！如果還沒有，則可以了解如何[向網域註冊機構購買](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-germany"

您的初始電子郵件地址，Office 365 Germany 中包含。 onmicrosoft.de，像是 tom@fourthcoffee.onmicrosoft.de。 您可以變更它像 tom@fourthcoffee.de 好記的位址。 您需要您自己的網域名稱，如 fourthcoffee.de 第一次。 如果您已經有了，那很好！ 如果還沒有，則可以了解如何[向網域註冊機構購買](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-21vianet"

由 21Vianet 運作的 Office 365 中您最初的電子郵件地址包含 partner.onmschina.cn，像是 tom@fourthcoffee.partner.onmschina.cn。 您可以變更它像 tom@fourthcoffee.cn 好記的位址。 您必須自己的網域名稱，例如 fourthcoffee.cn 第一次。 如果您已經有了，那很好！ 如果還沒有，則可以了解如何[向網域註冊機構購買](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

如果您在設定期間更新網域的 MX 記錄，藉此將網域的電子郵件變更為寄送至 Office 365，寄送至該網域的「所有」電子郵件將開始寄送至 Office 365。請確定您已經先在 Office 365 中為在您網域上有電子郵件的每個人新增使用者並建立信箱，然後再變更 MX 記錄。假如不想將您網域上每個人的電子郵件都移動到 Office 365，可以採取相關步驟[改為只使用幾個電子郵件地址來試驗 Office 365](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx)。
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>變更您的電子郵件地址，若要使用您使用 Microsoft 365 系統管理中心的自訂網域

您必須執行這些步驟的全域系統管理員帳戶。 

::: moniker range="o365-worldwide"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的系統管理中心。 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. 移至系統管理中心， <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>。 

::: moniker-end 

2. 移至 [**設定** > **網域**] 頁面。 

3. 在 [**網域**] 頁面上選取 [**新增網域**]。
    
4. 遵循步驟操作，確認您擁有該網域並變更您的電子郵件地址。
    
系統將引導您完成在 Office 365 正確設定您的網域的所有操作。

> [!NOTE]
> 如果您未使用的 Exchange 授權，您無法使用網域來傳送或接收電子郵件從 Office 365 租用戶。
  
## <a name="related-articles"></a>相關文章

[購買使用 Office 365 的自訂網域](../get-help-with-domains/buy-a-domain-name.md)
 
