---
title: 網域常見問題集
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: 找到您常見問題的答案以深入瞭解網域。
ms.openlocfilehash: 093125d1652355fbd9b624e1f15b5858fd586301
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049733"
---
# <a name="domains-faq"></a>網域常見問題集

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end

本文包含有關 Microsoft 365 中網域的常見問題解答。

如果您找不到問題的答案，請留言讓我們知道，我們會將它新增至清單。

本文內容

[什麼是 MX 優先順序？](#what-is-mx-priority) 
[如何驗證我的網域的 SPF 記錄？](#how-can-i-validate-spf-records-for-my-domain) 
[何謂功能變數名稱？](#what-is-a-domain-name) 
[如果我的 DNS 提供者不支援某些記錄類型，會發生什麼事？](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types) 
[如何在 Microsoft 365 中設定或變更預設網域？](#how-do-i-set-or-change-the-default-domain-in-microsoft-365) 
[我可以將自訂子域或多個網域新增至 Microsoft 365 嗎？](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365) 
[為什麼我有「onmicrosoft.com」網域？](#why-do-i-have-an-onmicrosoftcom-domain) 
[為什麼我有「onmicrosoft.de」網域？](#why-do-i-have-an-onmicrosoftde-domain) 
[如何驗證我的非盈利性或教育狀態？](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>什麼是 MX 優先順序？

郵件會以最低喜好設定值（最高優先順序）傳遞到郵件 exchange 伺服器，因此用於郵件路由的 MX 記錄應該具有最低的喜好設定值，通常是0或*高*優先順序。 
  
- 當您建立 MX 記錄時，大部分的 DNS 主機服務提供者要求您設定偏好設定號碼。
    
- 某些標籤的方塊*偏好*，有些標籤*優先順序*。 
    
- 有些需要數位，有些會要求您選取 [*低*]、[*中*] 或 [*高*]。 
    
- 如果您只有一個 MX 記錄，則優先順序或喜好設定的任何值都很好。
    
- 如果您有一個以上的，請確定郵件路由的 MX 記錄的優先順序高於用於驗證您擁有該網域的 MX 記錄。
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>如何驗證我的網域的 SPF 記錄？

您必須具有或建立**一個 SPF 的 TXT 記錄**，這一點很重要。 如果您已經有 SPF 記錄，應將新的 Microsoft 365 值附加到它，而不是建立新的記錄。 在您新增或更新 Microsoft 電子郵件的 SPF 記錄之後，您應該檢查下列其中一項工具，確定語法是否正確： 
  
- [SPF 記錄測試控管](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [挖出 web 介面](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>何謂功能變數名稱？

網域是在電子郵件地址的 **@** 符號後，以及網址的 **www.** 後出現的唯一名稱。 它通常採用組織名稱和標準 Internet 尾碼的形式，例如*yourbusiness.com*或*stateuniversity.edu。* 
  
使用自訂網域（例如「可信性** \@ contoso.com**」）與 Microsoft 365，可協助您建立品牌的信譽及認可。 
  
您可以[在 Microsoft 365 中購買網域，我們會自動加以設定](../get-help-with-domains/buy-a-domain-name.md)，或者您可以從網域註冊機構購買或為您提供自己的現有功能。
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>如果我的 DNS 提供者不支援某些記錄類型，會發生什麼事？

如果您管理自己的 DNS 記錄，而且 DNS 主機不支援 Microsoft 365 所需的所有 DNS 記錄，有些 Microsoft 365 功能將無法運作。 建議您將網域轉接至支援所有必要 DNS 記錄的註冊機構。
  
支援所有必要 DNS 記錄的提供者：
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- 懸停
    
- MyHosting.com
    
- Name.com
    
- 幾乎自由語音
    
- Nettica
    
- 網際網路資訊中心 (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>如何在 Microsoft 365 中設定或變更預設網域？

您必須至少有一個自訂網域新增至 Microsoft 365，您才能選擇預設網域。

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[網域]</a> 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[網域]</a> 頁面。

::: moniker-end
    
2. 在 [**網域**] 頁面上，選取您要設定為新電子郵件地址的預設網域。 
    
3. 選取 [設定成預設值]****。
    
::: moniker range="o365-worldwide"

您無法變更*onmicrosoft.com*網域的名稱。 

::: moniker-end

::: moniker range="o365-germany"

您無法變更*onmicrosoft.de*網域的名稱。 

::: moniker-end

::: moniker range="o365-21vianet"

您無法變更*partner.onmschina.cn*網域的名稱。 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>我可以將自訂子域或多個網域新增至 Microsoft 365 嗎？

::: moniker range="o365-worldwide"

是。 若要新增子域，您必須在註冊機構網站上管理自己的 DNS 設定。 如果您要讓 Microsoft 使用 NS 記錄來管理您的 DNS 設定，或者您購買的是 Microsoft 的網域，您就無法新增子域。

::: moniker-end

::: moniker range="o365-germany"

是的！ 若要新增子域，您必須在註冊機構網站上管理自己的 DNS 設定。 如果您要讓 Microsoft 使用 NS 記錄來管理您的 DNS 設定，或者您購買的是 Microsoft 的網域，您就無法新增子域。

::: moniker-end

::: moniker range="o365-21vianet"

是的！ 若要新增子域，您必須在註冊機構網站上管理自己的 DNS 設定。 如果您是讓世紀以 NS 記錄來管理您的 DNS 設定，就無法新增子域。

::: moniker-end

一般來說，您最多可以將900個網域新增至您的 Microsoft 365 訂閱。
  
例如，您可以新增網域 contoso.com 及 contosomarketing.com，然後新增子域 www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com 等等。
  
當您新增子域時，會根據所驗證的父系網域，自動驗證。
  
當您將多個網域新增至 Microsoft 365 時，您可以在您已新增的任何網域上裝載任何服務（如電子郵件）。  *當您將電子郵件變更為 Microsoft 365 時，更新網域的 MX 記錄，所有傳送至該網域的電子郵件都會開始成為 Microsoft 365。* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> 如果您已將 contoso.com 網域新增至 Microsoft 365 訂閱，您也可以將子域 xyz.contoso.com 新增至其他 Microsoft 365 組織。 新增子域時，系統會提示您在 DNS 主機服務提供者中新增 TXT 記錄。

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>為什麼我有「onmicrosoft.com」網域？

當您註冊服務時，Microsoft 365 會為您建立網域，例如*contoso.onmicrosoft.com*。 您註冊時所建立的使用者識別碼包含網域，如*alan@contoso.onmicrosoft.com*。 
  
 **如果您想要讓您的電子郵件看起來像是*alan \@ contoso.com*：** [購買網域](../get-help-with-domains/buy-a-domain-name.md)，或是只要您擁有現有的使用者和網域中的步驟，即可執行 [[將您的使用者與網域新增至 Microsoft 365](add-domain.md) ]。 
  
- **您無法在註冊後重新命名 name.onmicrosoft.com17 網域。** 例如，如果您所選擇的初始網域是 fourthcoffee.onmicrosoft.com，您就無法將它變更為 fabrikam.onmicrosoft.com。 若要使用不同的 onmicrosoft.com 網域，您必須開始使用 Microsoft 365 的新訂閱。 
    
- **您無法重新命名您的小組網站 URL。** 您的小組網站 URL 是以您的 onmicrosoft.com 功能變數名稱為基礎。 不幸的是，由於 SharePoint 線上架構的運作方式，您無法重新命名小組網站。 
    
- **您無法移除您的 name.onmicrosoft.com17 網域。** Microsoft 365 必須保留它，因為它是用於您訂閱的幕後。 不過，您不需要在新增自訂網域之後，自行使用網域。 
    
您可以繼續使用初始 onmicrosoft.com 網域，即使是在您新增網域之後。 它仍適用于電子郵件和其他服務，所以是您的選擇。
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>為什麼我有「onmicrosoft.de」網域？

當您註冊服務時，Microsoft 365 會為您建立網域，例如*contoso.onmicrosoft.de*。 您註冊時所建立的使用者識別碼包含網域，如*alan@contoso.onmicrosoft.de*。 
  
 **如果您想要讓您的電子郵件看起來像是*alan@contoso.de*：** [購買網域](../get-help-with-domains/buy-a-domain-name.md)，或是只要[將您的使用者與網域新增至 Microsoft 365](add-domain.md) ，便執行步驟。 
  
- **您無法在註冊後重新命名 name.onmicrosoft.com17 網域。** 例如，如果您所選擇的初始網域是 fourthcoffee.onmicrosoft.de，您就無法將它變更為 fabrikam.onmicrosoft.de。 若要使用不同的 onmicrosoft.de 網域，您必須開始使用 Microsoft 365 的新訂閱。 
    
- **您無法重新命名您的小組網站 URL。** 您的小組網站 URL 是以您的 onmicrosoft.de 功能變數名稱為基礎。不幸的是，由於 SharePoint 線上架構的運作方式，您無法重新命名小組網站。 
    
- **您無法移除您的 name.onmicrosoft.com17 網域。** Microsoft 365 必須保留它，因為它是用於您訂閱的幕後。 不過，您不需要在新增自訂網域之後，自行使用網域。 
    
您可以繼續使用初始 onmicrosoft.de 網域，即使是在您新增網域之後。 它仍適用于電子郵件和其他服務，所以是您的選擇。
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>如何驗證我的非盈利性或教育狀態？

1. 在系統[管理中心](https://docs.microsoft.com/microsoft-365/admin/admin-home)選取 [**安裝**] 以啟動嚮導。 （請務必先登入 Microsoft 365。） 
    
2. 若要成為您的學校系統管理員，請在 Microsoft 365 中選取 [**成為系統管理員**] 選項。 
    
3. 系統會提示您在網域的 DNS 主機網站上新增 TXT DNS 記錄。 為什麼？ 由於是在 DNS 主機登入，並為您的網域新增記錄，因此您可以向 Microsoft 365 證明您擁有該功能變數名稱。
    
4. 在您新增記錄後，您會回到 Microsoft 365 入口網站，並確認您已新增該記錄，所以 Microsoft 365 可以進行檢查。
    
是否有非贏利且想要取得 Microsoft 365？ [請確定您的組織符合資格](https://www.microsoft.com/en-us/nonprofits/eligibility)，然後註冊服務。 
  
想要深入瞭解如何成為您的學校管理員？ [深入瞭解](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。