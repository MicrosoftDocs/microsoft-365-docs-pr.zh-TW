---
title: 網域常見問題集
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: 深入了解 Office 365 中的網域的常見問題集中尋找您的問題的答案。
ms.custom: okr_smb
ms.openlocfilehash: f3c72f1ce772e3021d79aa4568dbfdb700400803
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252379"
---
# <a name="domains-faq"></a>網域常見問題集

本文包含有關在 Office 365 中的網域的常見問題集解答。

如果您找不到問題的答案，請留言讓我們知道，我們會將它新增至清單。
    
## <a name="what-is-mx-priority"></a>什麼是 MX 優先順序？

郵件傳遞到郵件 exchange 伺服器與最低的喜好設定編號 （最高優先順序），所以您使用的郵件路由 MX 記錄應具備的最低的喜好設定編號，通常是 0 或*高*優先順序。 
  
- 當您建立 MX 記錄時，大部分的 DNS 主機服務提供者需要您設定喜好設定編號。
    
- 某些標籤] 方塊中的 [*喜好設定*中，並將一些標籤其*優先順序*。 
    
- 某些需要一個數字，和某些要求您選取 [*低*、*中*或*高*。 
    
- 如果您只有一個 MX 記錄，任何值會是好的優先順序或喜好設定。
    
- 如果您有多個的話，請確定郵件路由的 MX 記錄是一種可以用來驗證您擁有該網域的較高優先順序。
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>如何驗證我的網域的 SPF 記錄？

請務必您擁有或建立**只有一個 SPF TXT 記錄**。 如果您已經有 SPF 記錄，您應該附加到文件的新的 Office 365 值，而不是建立一個新。 您已新增或更新您的 Office 365 電子郵件的 SPF 記錄之後，您應先確認語法不正確的其中一種工具： 
  
- [SPF 記錄測試工具](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [深入了 web 介面](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>Office 365 如何管理我的 DNS 記錄？

有兩個選項可使用 Office 365 的 DNS 管理：
  
1. 變更名稱伺服器 (NS) 記錄，並再 Office 365 的所有特定服務的記錄，例如電子郵件的 MX 記錄設定。 **（建議使用）**
    
2. 您的電子郵件和其他 Office 365 服務的 DNS 記錄在您的 DNS 主機將自己新增。 **（專家只）**
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>Office 365 建立和主控的 DNS 記錄 
**優點** 
- 您不必擔心犯錯在您輸入的 Office 365 服務的 DNS 記錄的值。  
- 您選擇的網域註冊機構和 DNS 主機中有更大的彈性。 
- 可讓您變更名稱伺服器記錄任何提供者將會運作，即使提供者不支援所有必要的記錄類型。   
- 當 Office 365 會新增新的 DNS 記錄時，您不需要進行更新。  

#### <a name="disadvantages"></a>缺點 
- 您無法變更您的 DNS 記錄到 Office 365 外部的主機電子郵件。 
- 如果您已使用的公用網站與您的網域，請在其地址，例如 www.fourthcoffee.com，您必須將重新導向人員至該地址從 Office 365。 
- 設定重新導向需要不一定容易取得的公用網站的靜態 IP 位址。 -如果您目前的網域註冊機構不允許您變更您的網域名稱伺服器記錄，您必須切換到不同的註冊機構，才能使用此 DNS 管理選項。  

 ### <a name="you-manage-the-dns-records-yourself"></a>您的 DNS 記錄自行管理 
 #### <a name="advantages"></a>優點
- 您可以控制 Office 365 服務的 DNS 記錄。   
- 如果您有一個公用網站與您的網域，其地址，例如 www.fourthcoffee.com，您不必擔心使用重新導向若要確保人員還是可以至您的網站後您設定 Office 365 中的網域。    
- 您有其他地方，例如與內部部署 Exchange server 的主機電子郵件的彈性。  
 
#### <a name="disadvantages"></a>缺點
您必須設定 Office 365 服務的 DNS 記錄自行 （除非您有 GoDaddy 網域）。 
-  如果您目前的 DNS 主機不支援所有必要的記錄類型的 Office 365，某些 Office 365 的功能將無法使用，而且您可能需要切換至不同的 DNS 主機。 
- 當 Office 365 變更 DNS 記錄的需求，或新增新的服務時，您必須自行進行更新，在您的 DNS 主機。 
   
## <a name="what-is-a-domain-name"></a>什麼是網域名稱？


網域是在電子郵件地址的 **@** 符號後，以及網址的 **www.** 後出現的唯一名稱。 它通常採用的表單貴組織的名稱和標準網際網路尾碼組成，例如*yourbusiness.com*或*stateuniversity.edu。* 
  
使用自訂的網域，例如 「**rob\@contoso.com**」 與 Office 365 可協助建立信譽及辨識您的品牌。 
  
您可以[購買 Office 365 中的網域，我們將它自動設定](../get-help-with-domains/buy-a-domain-name.md)，或者您可以購買或帶您已擁有一個向網域註冊機構。
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>可以轉移我向 Microsoft 購買其他提供者的網域嗎？

是的但您無法 Office 365 網域轉移至另一個登錄器直到 60 天後您購買 Office 365。

請注意*Whois*查詢將會顯示為多西網域 LLC Office 365 購買的網域註冊機構。 不過，只有 Office 365 應該連絡有關您購買的 Office 365 的網域。
  
請遵循下列步驟來取得 Office 365 程式碼，然後移至其他網域註冊機構的網站，以設定您的網域名稱傳送至該登錄器。
  
1. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。
    
    如果您使用 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">的網域</a>頁面。 
    
    如果您使用 21vianet 運作的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">的網域</a>頁面。
    
2. 在 [**網域**] 頁面上，選取您想要轉接至其他網域註冊機構，Office 365 網域，然後選取 [**網域傳輸** > **啟用網域傳輸**。
       
4. 請依照下列步驟來準備轉移您的網域。
    
5. 取得程式碼之後，移至的網域註冊機構網站您想要用來管理您接下來的網域名稱，並遵循指示其轉送的網域 （在他們網站上的協助搜尋）。
    
6. 如果您要一次，請參閱程式碼，在 Office 365 中的 [**網域設定**] 頁面上選取 [**網域傳輸時必須使用檢視授權程式碼**。
    
7. 傳輸完成之後，您將會更新您的網域，在新的網域註冊機構。
    
8. 若要完成程序，回到系統管理中心**的網域**] 頁面上，選取 [**完整網域傳送**。 

*附註： 請注意，Office 365 購買網域是不合格的名稱伺服器變更或 Office 365 租用戶間轉送網域。 如果兩者所需，網域註冊必須轉接至另一個登錄器。*
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a>如何變更我的 DNS 記錄在 Office 365 中的管理方式？

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a>變更為外部 Office 365 的 DNS 主機的 DNS 管理
   
1. 登入您的網域的網域註冊機構。
    
2. 尋找您更新名稱伺服器記錄，其中的註冊機構的網站上的區域，並更新為指向您的網域的 DNS 主機的名稱伺服器。 （的 DNS 主機通常是網域註冊機構）。
    
3. 請依照下列連結，前往 [網域設定精靈：
    
4. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。
    
    如果您使用 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">的網域</a>頁面。 
    
    如果您使用 21vianet 運作的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">的網域</a>頁面。
    
5. 在 [**網域**] 頁面上選取的網域扣款，並選取 [ **DNS 管理**]。
    
6. 在 [網域設定精靈，在 [**設定您的線上服務**] 頁面上，選取 [**我會管理自己的 DNS 記錄**，，然後選取 [**下一步**。
    
7. 新增至您的註冊機構網站的 [**更新 DNS 設定**] 頁面上的精靈所建議之 DNS 記錄。 
    
8. 您已新增記錄之後，回到 Office 365，並選取 [**驗證**。
    

### <a name="change-dns-management-to-office-365"></a>將 DNS 管理變更為 Office 365
  
1. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。
    
    如果您使用 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">的網域</a>頁面。 
    
    如果您使用 21vianet 運作的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">的網域</a>頁面。
    
2. 在 [**網域**] 頁面上選取的網域扣款，並選取 [ **DNS 管理**]。
    
3. 在 [網域設定精靈，在 [**設定您的線上服務**] 頁面上，選取 [ **Set up my 為我的線上服務。（建議使用）**，然後選取 [**下一步**。
    
4. 如果您還沒有尚未驗證網域，請遵循先執行的步驟。
    
5. 在 [ **Update DNS 設定**] 頁面中，我們會列出名稱伺服器的 Office 365。 移至您的網域的網域註冊機構，並更新至 Office 365 名稱伺服器的名稱伺服器。 
    
4. 之後您已更新名稱伺服器，**請等候至少一小時**。 然後，回到 [Office 365 中的精靈，選取 [**驗證**。
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>如果我的 DNS 提供者不支援某些記錄類型，會發生什麼事？

如果您管理 DNS 記錄，而且您的 DNS 主機不支援 Office 365 所需的所有 DNS 記錄，某些 Office 365 功能將無法使用。 我們建議您將網域移轉到註冊機構的支援所有必要的 DNS 記錄。
  
支援所有必要的 DNS 記錄的提供者：
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- 將游標暫留
    
- MyHosting.com
    
- Name.com
    
- 幾乎空閒語音
    
- Nettica
    
- 網際網路資訊中心 (NIC)
    
- Network Solutions
    
- Register.com
    
 **不支援如果 SRV 記錄**，Office 365 不的可用功能如下： 
  
- 商務用 Skype 商務 Online IM 和目前狀態整合與 Outlook Web App
    
- 外部通訊 （同盟） 與 Skype 商務 Online 其他組織中的使用者。
    
- 與 Skype for Business Online 使用者的公用網際網路連線能力 (PIC) 登入 Microsoft 帳戶 （以前稱為 Windows Live ID）。
    
 **如果不支援多個 CNAME 記錄，** 您必須選擇商務用 Skype 的下列功能： 
  
- 電子郵件桌面用戶端和行動用戶端可以使用自動探索來自動尋找 Exchange Online 服務，以便使用者可以登入，而不必輸入伺服器名稱。
    
- Skype 商務 Online 桌面用戶端可用於自動探索自動尋找 Skype 商務 Online 服務，讓使用者可以登入，而不必輸入伺服器名稱。
    
- Skype 商務 Online 行動用戶端可用於自動探索自動尋找 Skype 商務 Online 服務，讓使用者可以登入，而不必輸入伺服器名稱。
    
 **如果 SPF/TXT 記錄不受支援**，其他人可能無法使用您的網域來傳送垃圾郵件或其他惡意電子郵件。 SPF 記錄運作識別來自您網域傳送電子郵件會獲授權的伺服器。 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a>如何設定或變更 Office 365 中的預設網域？

您必須至少一個自訂的網域，您可以選擇預設網域之前，已新增至 Office 365。
  
1. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。
    
    如果您使用 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">的網域</a>頁面。 
    
    如果您使用 21vianet 運作的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">的網域</a>頁面。
    
2. 在 [**網域**] 頁面上，選取您想要設定為預設值為新的電子郵件地址的網域。 
    
3. 選取 [**設成預設值**。
    
::: moniker range="o365-worldwide"

您無法變更自己的初始名稱 *。 onmicrosoft.com*網域。 

::: moniker-end

::: moniker range="o365-germany"

您無法變更自己的初始名稱 *。 onmicrosoft.de*網域。 

::: moniker-end

::: moniker range="o365-21vianet"

您無法變更自己的初始名稱 *。 partner.onmschina.cn*網域。 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a>新增自訂的子網域或多個網域到 Office 365？

::: moniker range="o365-worldwide"

Yes ！ 若要新增子網域，您必須管理自己的 DNS 設定，在您的註冊機構網站。 如果您要讓 Microsoft 管理您的 DNS 設定 NS 記錄，或如果您向 Microsoft 購買網域，您無法新增子網域。

::: moniker-end

::: moniker range="o365-germany"

Yes ！ 若要新增子網域，您必須管理自己的 DNS 設定，在您的註冊機構網站。 如果您要讓 Microsoft 管理您的 DNS 設定 NS 記錄，或如果您向 Microsoft 購買網域，您無法新增子網域。

::: moniker-end

::: moniker range="o365-21vianet"

Yes ！ 若要新增子網域，您必須管理自己的 DNS 設定，在您的註冊機構網站。 如果您要讓 21Vianet 管理您的 NS 記錄的 DNS 設定，您無法新增子網域。

::: moniker-end

一般而言，您可以新增多達 900 個網域到 Office 365 訂閱。
  
例如，您無法新增網域 contoso.com 和 contosomarketing.com，，然後再新增子網域 www.contoso.com、 www.partners.contoso.com、 www.partners.marketing.contoso.com，依此類推。
  
當您新增子網域時，會自動驗證並已確認父系網域為基礎。
  
當您將多個網域新增至 Office 365 時，您可以在任何已新增的網域上裝載任何服務 （例如電子郵件）。  *當您變更您的電子郵件到 Office 365，藉由更新網域的 MX 記錄時，傳送至該網域的所有電子郵件都會開始送往 Office 365。* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> 如果您已新增 contoso.com 網域至 Office 365 租用戶，您也可以新增子網域 xyz.contoso.com 到另一個 Office 365 租用戶。 當新增子網域，系統將提示您 DNS 主機服務提供者中新增 TXT 記錄。

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>為什麼有 「 onmicrosoft.com"網域？

Office 365 網域為您建立，例如*contoso.onmicrosoft.com*，當您註冊的服務。 當您註冊您建立的使用者識別碼包含的網域，例如*alan@contoso.onmicrosoft.com*。 
  
 **如果您想要有您的電子郵件看起來像*alan\@contoso.com*:** [購買網域](../get-help-with-domains/buy-a-domain-name.md)，或如果您已擁有只是依照中[新增您的使用者與網域至 Office 365](add-domain.md)的步驟。 
  
- **您無法重新命名後的 onmicrosoft 網域註冊。** 例如，如果您選擇的初始網域 fourthcoffee.onmicrosoft.com，您無法變更其設為 fabrikam.onmicrosoft.com。 若要使用不同的 onmicrosoft.com 網域，您必須使用 Office 365 中開始新的訂閱。 
    
- **您無法重新命名您的小組網站 URL。** 您的小組網站 URL 根據您的 onmicrosoft.com 網域名稱。 不幸的是，因為 SharePoint Online 的架構的運作方式，您無法重新命名小組網站。 
    
- **您無法移除 onmicrosoft 網域。** Office 365 需要保留其周圍，因為它在幕後用於您的訂閱。 但您不需要使用網域自行後您已新增自訂的網域。 
    
您可以繼續使用初始的 onmicrosoft.com 網域即使之後新增您的網域。 它仍適用於電子郵件和其他服務，因此您可以選擇。
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>為什麼有 「 onmicrosoft.de 」 網域？

Office 365 網域為您建立，例如*contoso.onmicrosoft.de*，當您註冊的服務。 當您註冊您建立的使用者識別碼包含的網域，例如*alan@contoso.onmicrosoft.de*。 
  
 **如果您想要有您的電子郵件看起來像*alan@contoso.de*:** [購買網域](../get-help-with-domains/buy-a-domain-name.md)，或如果您已擁有只是依照中[新增您的使用者與網域至 Office 365](add-domain.md)的步驟。 
  
- **您無法重新命名後的 onmicrosoft 網域註冊。** 例如，如果您選擇的初始網域 fourthcoffee.onmicrosoft.de，您無法變更它 fabrikam.onmicrosoft.de。 若要使用不同的 onmicrosoft.de 網域，您必須使用 Office 365 中開始新的訂閱。 
    
- **您無法重新命名您的小組網站 URL。** 您的小組網站 URL 根據您的 onmicrosoft.de 網域名稱。不幸的是，因為 SharePoint Online 的架構的運作方式，您無法重新命名小組網站。 
    
- **您無法移除 onmicrosoft 網域。** Office 365 需要保留其周圍，因為它在幕後用於您的訂閱。 但您不需要使用網域自行後您已新增自訂的網域。 
    
您可以繼續使用初始 onmicrosoft.de 網域即使之後新增您的網域。 它仍適用於電子郵件和其他服務，因此您可以選擇。
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>如何確認我非營利組織版或教育版的狀態？

1. 在[系統管理中心](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx)來啟動精靈，請選取 [**安裝**]。 （請務必先登入 Office 365）。 
    
2. 若要成為系統管理員為您的學校，選取 [**成為系統管理員**選項在 Office 365 中。 
    
3. 系統會提示您在您網域的 DNS 主機網站上新增 TXT DNS 記錄。 為什麼？ 因為在 DNS 主機登入，並新增您的網域的記錄，您證明到 Office 365 您擁有的網域名稱。
    
4. 新增記錄之後，您會回到 Office 365 入口網站，並確認您已新增它，因此可以檢查 Office 365。
    
有非營利組織版，且想要取得 Office 365？ [請確定您的組織符合要求](https://www.microsoft.com/en-us/nonprofits/eligibility)，然後註冊服務。 
  
想要深入了解成為您學校的系統管理員嗎？ [解它](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>可以我試驗 Office 365 與幾電子郵件地址從我的自訂網域？

您可以但有一些限制：
  
- 您目前的電子郵件提供者必須提供電子郵件轉寄功能。
    
- 管理您的 Office 365 相關的 DNS 記錄，在 DNS 主機服務提供者，所需，而不是具有 Office 365 為您管理這些記錄。 若要了解這項功能的需要，請參閱新增網域至 Office 365 時您想要管理自己的 DNS 記錄。
    
- 某些 Office 365 的功能將無法使用：
- 使用者將無法看到其他電子郵件提供者上使用者的空閒/忙碌資訊。
- 系統管理員將無法從一個地方管理所有人的帳戶。
- 使用者可能無法使用 Office 365 垃圾郵件篩選

### <a name="how-to-set-up-an-office-365-pilot"></a>如何設定 Office 365 試驗部署
    
1. 登入 Microsoft 365 系統管理中心
    
    1. 使用您的公司或學校帳戶登入 Office 365。
        
    2. 移至 [**設定** \> **網域**。 
    
2. 驗證您擁有您想要使用的網域
    
    1. 在 [**網域**] 頁面上選取 [**新增網域**]。 
        
    2. 在面板中，輸入網域，在此範例 cohowinery.com，，然後選取 [**下一步**。 
        
    3. 在**驗證**網域] 頁面上，依照逐步指示。 
        
    4. 在下拉式清單中，選取 [DNS 主機服務提供者，並遵循指示來顯示您擁有該網域。
        
    5. 選取 [**驗證**]。 花幾分鐘的時間和 72 小時，才會生效的 DNS 變更之間。 
        
    6. 驗證成功時，系統會要求您修改您的 DNS 記錄。
    
3. 標記為 Exchange Online 中共用的網域
    
    1. 移至**Exchange 系統管理中心**(EAC)。 
        
    2. 在 [**郵件流程**] 區段中，選取 **[公認的網域**。 
        
    3. 按兩下您要修改的網域。
        
    4. 在開啟視窗中，選取 [**內部轉送**]。 
        
    5. 選取 **[儲存]**。 此設定可能需要幾分鐘的時間才會生效。 
    
4. （選用） 解除封鎖在現有的電子郵件伺服器
    
    1. Office 365 會使用 Exchange Online Protection (EOP) 的垃圾郵件保護。 如果 EOP 偵測到大量垃圾郵件轉寄您目前的郵件伺服器，可能會封鎖，以防止轉寄功能無法運作。 如果您有自信與垃圾郵件保護您電子郵件提供者使用，您可以 whitelist 他們在 Office 365 中的伺服器。 不過，這也可讓送達您原始的伺服器到 Office 365 信箱、 來自透過任何垃圾郵件，而且您將無法評估 Office 365 如何防止垃圾郵件。
    
    2. 移至 Exchange 系統管理中心 (EAC)。
        
    3. 在 EAC 中，選取 [**保護**]，然後選取**連線篩選器**。 
        
    4. 在**IP 允許清單**中，選取 [ **+**，並新增您可以從目前的電子郵件提供者取得的郵件伺服器 IP 位址。 
    
5. 建立使用者帳戶，並設定主要 (回覆-to) 地址
    
    1. 移至 Microsoft 365 系統管理中心。
        
    2. 在左的導覽列中，選取 [**使用者** \> **作用中的使用者**。 
        
    3. 建立使用者帳戶。
        
    4. 每個帳戶選取 **+ （新增）**，並填寫所需的資訊。 
        
    5. 若要保留使用者的電子郵件相同為它目前正被，**使用者名稱**] 欄位應完全使用者的現有電子郵件地址相同。 
        
    6. 使用者名稱] 旁邊，從下拉式清單中選取您的自訂網域名稱。
        
    7. 選取 [**建立** \> **關閉**。 
        
6. 更新 DNS 主機服務提供者的 DNS 記錄
    
    1. 登入您 DNS 主機服務提供者的網站，並遵循[Office 365 步驟任何 DNS 主機服務提供者處建立 DNS 記錄](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。 **進行下列例外：**
    
        1. 請勿建立新的 MX 記錄或變更現有的 MX 記錄。
            
        2. 如果您已為您舊的電子郵件提供者的寄件者原則架構 (SPF) 記錄，而不是建立新的 SPF (TXT) 記錄的 Exchange Online 中，剛加入 「 include: spf.protection.outlook.com 「 目前的 TXT 記錄。 例如，「 v = spf1 mx include:adatum.com include: spf.protection.outlook.com ~ 所有 」。
            
        3. 如果您不具備 SPF 記錄，修改，故 Office 365 所要包含您目前的電子郵件提供者，再加上 spf.protection.outlook.com 的網域。 這會授與來自這兩個電子郵件系統的外寄郵件。
            
7. 設定在您目前的提供者的電子郵件轉寄
    
    1. 在您目前的電子郵件提供者，設定為您的使用者轉接至您的 onmicrosoft.com 網域的電子郵件帳戶：
        
    2. 使用者 A 的信箱應轉寄給 usera@yourcompany.onmicrosoft.com
        
    3. 使用者 B 的信箱應轉寄給 userb@yourcompany.onmicrosoft.com
        
    4. 當您完成此步驟：
        
    5. 所有傳送到 usera@yourcompany.com 和 userb@yourcompany.com 郵件則可在 Office 365。
    
    6. 附註：
        
        - 如需設定轉寄的確切步驟連絡您目前的電子郵件提供者。
            
        - 您不需要保留在目前的電子郵件提供者的郵件的副本。
            
        - 大部分提供者轉寄電子郵件離開寄件者的回覆地址不變，以便回覆移至原始寄件者。
    
8. 測試郵件流程
    
    1. 登入 Outlook Web App 使用者 A 的認證。
        
    2. 執行下列測試：
        
    3. 測試本機的 Office 365 電子郵件。 例如，傳送電子郵件給使用者 b。應該會立即傳遞這封電子郵件。 在此案例中，郵件將不會路由傳送到原始的伺服器上的使用者 B 的信箱因為 Office 365 會為本機看到該信箱。
        
    4. 測試電子郵件給其他電子郵件系統上的任何人。 例如，傳送電子郵件給使用者 c。這封電子郵件應該傳遞至原始的郵件伺服器上的 C 使用者的信箱。
        
    5. 從外部的帳戶，或從其他電子郵件系統上的員工的電子郵件帳戶，請確認轉寄已正確設定，其他電子郵件系統上。 例如，從使用者 C origninal 伺服器帳戶或 Hotmail 帳戶，使用者傳送的電子郵件，並確認它送達使用者 A 的 Office 365 信箱。
        
9. 移動信箱內容
    
    1. 由於有移動，只有兩位使用者，因為使用者 A 和 B 使用者都使用 Outlook 已可以藉由開啟舊移動電子郵件。在 [新的 Outlook 設定檔並複製郵件、 行事曆項目、 連絡人、 等，從 Outlook 資料檔 (.pst) 匯入 Outlook 項目中所示的 PST 檔案。 一旦組織中的 Office 365 信箱中的適當位置、 項目所有可從任何裝置，任何地方。
        
    2. 當涉及多個信箱時，或員工您尚未使用 Outlook，您可以使用可用的移轉工具在 Exchange 系統管理中心。 若要開始，移至 Exchange 系統管理中心，並按照指示中遷移電子郵件從 IMAP 伺服器至 Exchange Online 信箱。
    
