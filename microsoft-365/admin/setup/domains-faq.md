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
description: 在 FAQ 中尋找問題的答案以深入瞭解網域。
ms.openlocfilehash: a52513130f9bbbf7c4cd25d4c4827e833700d992
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739161"
---
# <a name="domains-faq"></a>網域常見問題集

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end

本文包含有關 Office 365 中的網域的常見問題解答。

如果您找不到問題的答案，請留言讓我們知道，我們會將它新增至清單。
    
## <a name="what-is-mx-priority"></a>什麼是 MX 優先順序？

郵件會以最低喜好設定值（最高優先順序）傳遞到郵件 exchange 伺服器，因此用於郵件路由的 MX 記錄應該具有最低的喜好設定值，通常是0或*高*優先順序。 
  
- 當您建立 MX 記錄時，大部分的 DNS 主機服務提供者要求您設定偏好設定號碼。
    
- 某些標籤的方塊*偏好*，有些標籤*優先順序*。 
    
- 有些需要數位，有些會要求您選取 [*低*]、[*中*] 或 [*高*]。 
    
- 如果您只有一個 MX 記錄，則優先順序或喜好設定的任何值都很好。
    
- 如果您有一個以上的，請確定郵件路由的 MX 記錄的優先順序高於用於驗證您擁有該網域的 MX 記錄。
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>如何驗證我的網域的 SPF 記錄？

您必須具有或建立**一個 SPF 的 TXT 記錄**，這一點很重要。 如果您已經有 SPF 記錄，您應該將新的 Office 365 值附加到它，而不是建立新的記錄。 在您新增或更新 Microsoft 電子郵件的 SPF 記錄之後，您應該檢查下列其中一項工具，確定語法是否正確： 
  
- [SPF 記錄測試控管](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [挖出 web 介面](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>Office 365 如何管理我的 DNS 記錄？

使用 Office 365 的 DNS 管理有兩個選項：
  
1. 您變更了名稱伺服器（NS）記錄，然後 Microsoft 會處理所有服務特有的記錄，例如設定電子郵件的 MX 記錄。 **推薦**
    
2. 您可以在 DNS 主機自行新增電子郵件和其他 Office 365 服務的 DNS 記錄。 **（僅限專家）**
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>Office 365 會建立及裝載 DNS 記錄 
**優點** 
- 您不需要擔心您為 Office 365 服務的 DNS 記錄輸入的值錯誤。  
- 您選擇的網域註冊機構和 DNS 主機具有較大的彈性。 
- 任何可讓您變更名稱伺服器記錄的提供者都會運作，即使提供者不支援所有必要的記錄類型。   
- 當 Office 365 新增 DNS 記錄時，您不需要進行更新。  

#### <a name="disadvantages"></a>缺點 
- 您無法變更您的 DNS 記錄以主控 Office 365 以外的電子郵件。 
- 如果您已在網域上使用公用網站的位址（如 www.fourthcoffee.com），您必須將人員重新導向至 Office 365 的該位址。 
- 設定重新導向需要靜態 IP 位址，但不一定能輕易用於公用網站。 -如果您目前的網域註冊機構不允許您變更網域的名稱伺服器記錄，您必須切換至不同的註冊機構，才能使用此 DNS 管理選項。  

 ### <a name="you-manage-the-dns-records-yourself"></a>您自行管理 DNS 記錄 
 #### <a name="advantages"></a>優點
- 您可以控制 Office 365 服務的 DNS 記錄。   
- 如果您擁有網域的公用網站的位址（如 www.fourthcoffee.com），您不需要擔心在您設定 Office 365 中的網域後，使用者仍可進入您的網站。    
- 您可以靈活地在其他地方主控電子郵件，例如使用內部部署 Exchange 伺服器。  
 
#### <a name="disadvantages"></a>缺點
您必須自行設定 Office 365 服務的 DNS 記錄（除非您有 GoDaddy 網域）。 
-  如果目前的 DNS 主機不支援 Microsoft 365 的所有必要記錄類型，有些功能將無法使用，您可能需要切換至不同的 DNS 主機。 
- 當 Office 365 變更 DNS 記錄的需求，或加入新的服務時，您必須自行在您的 DNS 主機上進行更新。 
   
## <a name="what-is-a-domain-name"></a>何謂功能變數名稱？


網域是在電子郵件地址的 **@** 符號後，以及網址的 **www.** 後出現的唯一名稱。 它通常採用組織名稱和標準 Internet 尾碼的形式，例如*yourbusiness.com*或*stateuniversity.edu。* 
  
使用自訂網域（例如「可信性** \@ contoso.com**」）與 Office 365，可協助您建立品牌的信譽及認可。 
  
您可以[在 Office 365 購買網域，我們會自動加以設定](../get-help-with-domains/buy-a-domain-name.md)，或者您可以從網域註冊機構購買或為您提供自己的現有功能。
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>我可以將從 Microsoft 購買的網域轉移至其他提供者嗎？

是的，但是您無法將 Office 365 網域轉接至其他註冊機構，直到您購買 Office 365 的60天之後。

請注意， *Whois*查詢會將 Office 365 購買的網域註冊機構顯示為通配的 WEST 網域 LLC。 不過，請只針對您的 Office 365 購買的網域，請與 Office 365 取得聯繫。
  
請遵循下列步驟，取得 Office 365 的程式碼，然後移至另一個網域註冊機構的網站，設定將您的功能變數名稱轉移到該註冊機構。

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[網域]</a> 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 [**設定** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">授權</a>] 頁面。

::: moniker-end
    
2. 在 [**網域**] 頁面上，選取您要傳送至其他網域註冊機構的 Office 365 網域，然後選取 [**網域傳輸**  >  **啟用網域傳輸**]。
       
4. 遵循步驟來準備轉移您的網域。
    
5. 在您取得程式碼之後，請移至網域註冊機構的網站，以供您用來管理功能變數名稱的位置，並遵循傳送網域（搜尋其網站上的說明）的指導。
    
6. 如果您需要重新查看此程式碼，請在 Office 365 的 [**網域設定**] 頁面上，選取 [ **View the domain transfer 的授權碼**]。
    
7. 完成傳輸後，您將會在新的網域註冊機構中更新您的網域。
    
8. 若要完成此程式，請回到管理中心的 [**網域**] 頁面，並選取 [**完整網域傳輸**]。 

*附注：請注意，Office 365 購買的網域不適用於名稱伺服器變更，或無法在 Office 365 承租人間傳輸網域。 若有任何一項是必要的，則必須將網域註冊轉給另一個註冊機構。*
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a>如何變更我的 DNS 記錄在 Office 365 中的管理方式？

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a>將 DNS 管理變更為 Office 365 以外的 DNS 主機
   
1. 登入網域的網域註冊機構。
    
2. 在註冊機構網站上尋找您更新名稱伺服器記錄的區域，並更新名稱伺服器以指向您網域的 DNS 主機。 （DNS 主機通常是網域註冊機構。）
    
3. 遵循連結移至網域安裝精靈：

::: moniker range="o365-worldwide"

4. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

::: moniker-end

::: moniker range="o365-germany"

4. 在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[網域]</a> 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

4. 在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[網域]</a> 頁面。

::: moniker-end
    
5. 在 [**網域**] 頁面上，選取您要切換的網域，然後選取 [ **DNS 管理**]。
    
6. 在 [網域安裝精靈] 中，在 [**設定您的線上服務**] 頁面上，選取 [**我要管理自己的 DNS 記錄**]，然後選取 **[下一步]**。
    
7. 在 [**更新 dns 設定**] 頁面上，將嚮導建議的 DNS 記錄新增至您的註冊機構網站。 
    
8. 在您新增記錄後，請回到 Office 365 並選取 [**驗證**]。
    

### <a name="change-dns-management-to-office-365"></a>將 DNS 管理變更為 Office 365

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[網域]</a> 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[網域]</a> 頁面。

::: moniker-end
    
2. 在 [**網域**] 頁面上，選取您要切換的網域，然後選取 [ **DNS 管理**]。
    
3. 在 [網域安裝精靈] 中，在 [**設定您的線上服務**] 頁面上，選取 [**設定我的線上服務給我]。（建議）**，然後選取 **[下一步]**。
    
4. 如果您還沒有驗證網域，請遵循執行第一步的步驟。
    
5. 在 [**更新 DNS 設定**] 頁面上，列出 Office 365 的名稱伺服器。 移至網域的網域註冊機構，並將名稱伺服器更新為 Office 365 名稱伺服器。 
    
4. 更新名稱伺服器後，請**至少等候一小時**。 然後，回到 Office 365 的嚮導中，選取 [**驗證**]。
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>如果我的 DNS 提供者不支援某些記錄類型，會發生什麼事？

如果您管理自己的 DNS 記錄，而且 DNS 主機不支援 Office 365 所需的所有 DNS 記錄，有些 Office 365 功能將無法運作。 建議您將網域轉接至支援所有必要 DNS 記錄的註冊機構。
  
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
    
 **如果不支援 SRV 記錄**，則無法使用下列 Office 365 功能： 
  
- 商務用 Skype Online IM 和目前狀態與 Outlook Web App 的整合
    
- 與其他組織中商務用 Skype Online 使用者的外部通訊（同盟）。
    
- 公用網際網路連線（PIC）與商務用 Skype Online 使用者使用 Microsoft 帳戶登入（以前稱為 Windows Live ID）。
    
 **如果不支援多個 CNAME 記錄，** 您必須為商務用 Skype Online 選擇下列功能： 
  
- 電子郵件桌面用戶端和行動用戶端可以使用自動探索自動尋找 Exchange Online 服務，讓使用者不必輸入伺服器名稱即可登入。
    
- 商務用 skype Online 桌面用戶端可以使用自動探索，自動尋找商務用 Skype Online 服務，讓使用者不必輸入伺服器名稱即可登入。
    
- 商務用 skype Online 行動用戶端可以使用自動探索，自動尋找商務用 Skype Online 服務，讓使用者不必輸入伺服器名稱即可登入。

- Microsoft 團隊同盟與商務用 Skype 的同盟，不論是內部部署或線上。 如需詳細資訊，請參閱為[Microsoft 團隊準備組織的網路](https://docs.microsoft.com/microsoftteams/prepare-network)。
    
 **如果不支援 SPF/TXT 記錄**，其他人可能會使用您的網域來傳送垃圾郵件或其他惡意的電子郵件。 SPF 記錄會透過識別從您的網域傳送電子郵件的授權伺服器運作。 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a>如何在 Office 365 中設定或變更預設網域？

您必須至少有一個自訂網域新增至 Office 365，您才能選擇預設網域。

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

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a>我可以將自訂子域或多個網域新增至 Office 365 嗎？

::: moniker range="o365-worldwide"

是的！ 若要新增子域，您必須在註冊機構網站上管理自己的 DNS 設定。 如果您要讓 Microsoft 使用 NS 記錄來管理您的 DNS 設定，或者您購買的是 Microsoft 的網域，您就無法新增子域。

::: moniker-end

::: moniker range="o365-germany"

是的！ 若要新增子域，您必須在註冊機構網站上管理自己的 DNS 設定。 如果您要讓 Microsoft 使用 NS 記錄來管理您的 DNS 設定，或者您購買的是 Microsoft 的網域，您就無法新增子域。

::: moniker-end

::: moniker range="o365-21vianet"

是的！ 若要新增子域，您必須在註冊機構網站上管理自己的 DNS 設定。 如果您是讓世紀以 NS 記錄來管理您的 DNS 設定，就無法新增子域。

::: moniker-end

一般來說，您最多可以將900個網域新增至 Office 365 訂閱。
  
例如，您可以新增網域 contoso.com 及 contosomarketing.com，然後新增子域 www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com 等等。
  
當您新增子域時，會根據所驗證的父系網域，自動驗證。
  
當您將多個網域新增至 Office 365 時，您可以在您已新增的任何網域上裝載任何服務（如電子郵件）。  *當您將電子郵件變更為 Office 365 時，更新網域的 MX 記錄，所有傳送至該網域的電子郵件都會開始進入 Office 365。* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> 如果您已將 contoso.com 網域新增至 Office 365 租使用者，您也可以將子域 xyz.contoso.com 新增至另一個 Office 365 租使用者。 新增子域時，系統會提示您在 DNS 主機服務提供者中新增 TXT 記錄。

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>為什麼我有「onmicrosoft.com」網域？

當您註冊服務時，Office 365 會為您建立網域，例如*contoso.onmicrosoft.com*。 您註冊時所建立的使用者識別碼包含網域，如*alan@contoso.onmicrosoft.com*。 
  
 **如果您想要讓您的電子郵件看起來像是*alan \@ contoso.com*：** [購買網域，](../get-help-with-domains/buy-a-domain-name.md)或是只要您已擁有您的使用者和網域，請依照將您的[使用者與網域新增至 Office 365](add-domain.md)中的步驟進行。 
  
- **您無法在註冊後重新命名 name.onmicrosoft.com17 網域。** 例如，如果您所選擇的初始網域是 fourthcoffee.onmicrosoft.com，您就無法將它變更為 fabrikam.onmicrosoft.com。 若要使用不同的 onmicrosoft.com 網域，您必須開始使用 Office 365 的新訂閱。 
    
- **您無法重新命名您的小組網站 URL。** 您的小組網站 URL 是以您的 onmicrosoft.com 功能變數名稱為基礎。 不幸的是，由於 SharePoint 線上架構的運作方式，您無法重新命名小組網站。 
    
- **您無法移除您的 name.onmicrosoft.com17 網域。** Office 365 需要保留它，因為它是用於您訂閱的幕後。 不過，您不需要在新增自訂網域之後，自行使用網域。 
    
您可以繼續使用初始 onmicrosoft.com 網域，即使是在您新增網域之後。 它仍適用于電子郵件和其他服務，所以是您的選擇。
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>為什麼我有「onmicrosoft.de」網域？

當您註冊服務時，Office 365 會為您建立網域，例如*contoso.onmicrosoft.de*。 您註冊時所建立的使用者識別碼包含網域，如*alan@contoso.onmicrosoft.de*。 
  
 **如果您想要讓您的電子郵件看起來像是*alan@contoso.de*：** [購買網域](../get-help-with-domains/buy-a-domain-name.md)，或是只要[將您的使用者與網域新增至 Office 365](add-domain.md) ，也請依照下列步驟進行。 
  
- **您無法在註冊後重新命名 name.onmicrosoft.com17 網域。** 例如，如果您所選擇的初始網域是 fourthcoffee.onmicrosoft.de，您就無法將它變更為 fabrikam.onmicrosoft.de。 若要使用不同的 onmicrosoft.de 網域，您必須開始使用 Office 365 的新訂閱。 
    
- **您無法重新命名您的小組網站 URL。** 您的小組網站 URL 是以您的 onmicrosoft.de 功能變數名稱為基礎。不幸的是，由於 SharePoint 線上架構的運作方式，您無法重新命名小組網站。 
    
- **您無法移除您的 name.onmicrosoft.com17 網域。** Office 365 需要保留它，因為它是用於您訂閱的幕後。 不過，您不需要在新增自訂網域之後，自行使用網域。 
    
您可以繼續使用初始 onmicrosoft.de 網域，即使是在您新增網域之後。 它仍適用于電子郵件和其他服務，所以是您的選擇。
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>如何驗證我的非盈利性或教育狀態？

1. 在系統[管理中心](https://docs.microsoft.com/microsoft-365/admin/admin-home)選取 [**安裝**] 以啟動嚮導。 （請務必先登入 Office 365。） 
    
2. 若要成為 school 的系統管理員，請選取 [成為 Office 365 的系統**管理員**] 選項。 
    
3. 系統會提示您在網域的 DNS 主機網站上新增 TXT DNS 記錄。 為什麼？ 由於是在 DNS 主機登入，並為您的網域新增記錄，因此您可以為 Office 365 證明您擁有該功能變數名稱。
    
4. 在您新增記錄後，您會回到 Office 365 入口網站，並確認您已新增該記錄，因此 Office 365 可以進行檢查。
    
是否有非贏利且想要取得 Office 365？ [請確定您的組織符合資格](https://www.microsoft.com/en-us/nonprofits/eligibility)，然後註冊服務。 
  
想要深入瞭解如何成為您的學校管理員？ [深入瞭解](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>我可以使用來自自訂網域的一些電子郵件地址試驗 Office 365 嗎？

您可以，但有一些限制：
  
- 您目前的電子郵件提供者必須提供電子郵件轉接功能。
    
- 您需要在您的 DNS 主機服務提供者管理與 Office 365 相關的 DNS 記錄，而不是讓 Office 365 為您管理這些記錄。 若要瞭解這需要做什麼，請參閱將您的網域新增至 Office 365，以管理您自己的 DNS 記錄。
    
- 有些 Office 365 功能無法使用：
- 使用者將無法查看位於其他電子郵件提供者上之使用者的空閒/忙碌資訊。
- 系統管理員無法從單一位置管理所有人的帳戶。
- 使用者可能無法使用 Office 365 垃圾郵件篩選

### <a name="how-to-set-up-an-office-365-pilot"></a>如何設定 Office 365 試驗
    
1. 登入 Microsoft 365 系統管理中心
    
    1. 使用您的公司或學校帳戶登入 Office 365。
        
    2. 移至 [**設定**] [ \> **網域**]。 
    
2. 確認您擁有要使用的網域
    
    1. 在 [**網域**] 頁面上，選取 [**新增網域**]。 
        
    2. 在面板中，輸入網域，在此範例中 cohowinery.com，然後選取 **[下一步]**。 
        
    3. 在 [**驗證**網域] 頁面上，遵循逐步指示。 
        
    4. 在下拉式清單中，選取您的 DNS 主機服務提供者，然後依照指示，顯示您擁有該網域。
        
    5. 選取 [**驗證**]。 DNS 變更會在幾分鐘和72小時之間生效。 
        
    6. 驗證成功時，系統會要求您修改您的 DNS 記錄。
    
3. 在 Exchange Online 中將網域標示為「共用」
    
    1. 移至**Exchange 系統管理中心**（EAC）。 
        
    2. 在 [**郵件流程**] 區段中，選取 [**公認的網域**]。 
        
    3. 按兩下您要修改的網域。
        
    4. 在開啟的視窗中，選取 [**內部轉送**]。 
        
    5. 選取 **[儲存]**。 此設定可能需要幾分鐘才會生效。 
    
4. （選用）解除封鎖現有的電子郵件伺服器
    
    1. Office 365 使用 Exchange Online Protection （EOP）進行垃圾郵件保護。 如果 EOP 偵測到您目前的郵件伺服器轉寄大量的垃圾郵件，可能會封鎖垃圾郵件，這樣會使轉接無法運作。 如果您確信其他電子郵件提供者所用的垃圾郵件保護，您可以將其伺服器新增至 Office 365 中的允許清單。 不過，這也會讓透過您原始伺服器到達的任何垃圾郵件都進入 Office 365 信箱，而且您將無法評估 Office 365 如何防止垃圾郵件。
    
    2. 移至 Exchange 系統管理中心（EAC）。
        
    3. 在 EAC 中，選取 [**保護**]，然後選取 [連線**篩選**]。 
        
    4. 在 [ **IP 允許] 清單**中，選取 **+** ，並新增您可以從目前的電子郵件提供者取得的郵件伺服器 IP 位址。 
    
5. 建立使用者帳戶並設定主要（回復）位址
    
    1. 移至 Microsoft 365 系統管理中心。
        
    2. 在左導覽列中，選取 [**使用者**作用中 \> **使用者**]。 
        
    3. 建立使用者帳戶。
        
    4. 針對每個帳戶選取 **[+] （新增）**，並填寫必要的資訊。 
        
    5. 若要讓使用者的電子郵件與其目前相同，[**使用者名稱**] 欄位應該與使用者的現有電子郵件地址完全相同。 
        
    6. 在 [使用者名稱] 旁，從下拉式清單中選取您的自訂功能變數名稱。
        
    7. 選取 [**建立** \> **關閉**]。 
        
6. 在您的 DNS 主機服務提供者更新 DNS 記錄
    
    1. 登入您的 DNS 主機服務提供者的網站，並遵循在[任何 dns 主機服務提供者上為 Office 365 步驟建立 dns 記錄](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。 **請進行下列例外狀況：**
    
        1. 請勿建立新的 MX 記錄或變更現有的 MX 記錄。
            
        2. 如果您先前的電子郵件提供者已具備寄件者原則架構（SPF）記錄，而不是為 Exchange Online 建立新的 SPF （TXT）記錄，請直接在目前的 TXT 記錄中新增「包含: spf.protection.outlook.com .com」。 例如，"v = spf1 mx 包含:adatum 包含: spf.protection.outlook.com. .com ~ all"。
            
        3. 如果您還沒有 SPF 記錄，請修改 Office 365 建議的一個，以包含目前電子郵件提供者的網域，加上 spf.protection.outlook.com。 這會從兩個電子郵件系統中授權外寄郵件。
            
7. 在您目前的提供者設定電子郵件轉寄
    
    1. 在您目前的電子郵件提供者中，將您的使用者電子郵件帳戶的轉寄功能設定為您的 onmicrosoft.com 網域：
        
    2. 使用者 A 的信箱應該轉寄至 usera@yourcompany.onmicrosoft.com
        
    3. 使用者 B 的信箱應該轉寄至 userb@yourcompany.onmicrosoft.com
        
    4. 當您完成此步驟：
        
    5. 所有傳送至 usera@yourcompany.com 和 userb@yourcompany.com 的郵件都會出現在 Office 365。
    
    6. 附註：
        
        - 如需設定轉接的確切步驟，請與您目前的電子郵件提供者聯繫。
            
        - 您不需要在目前的電子郵件提供者中保留郵件複本。
            
        - 大部分提供者會轉寄電子郵件，讓寄件者的回復位址保持不變，因此回復會移至原始寄件者。
    
8. 測試郵件流程
    
    1. 使用使用者 A 的認證登入 Outlook Web App。
        
    2. 請執行下列測試：
        
    3. 測試本機 Microsoft 電子郵件。 例如，傳送電子郵件給使用者 B。這封電子郵件應該會立即傳遞。 在此情況下，郵件將不會路由傳送至原始伺服器上的使用者 B 信箱，因為 Office 365 會將信箱視為本機。
        
    4. 測試電子郵件給其他電子郵件系統上的某人。 例如，傳送電子郵件給使用者 C。這封電子郵件應該傳送至原始郵件伺服器上的使用者 C 信箱。
        
    5. 從外部帳戶，或是從其他電子郵件系統上某員工的電子郵件帳戶，確認已在其他電子郵件系統上正確設定轉寄功能。 例如，從使用者 C 的原始伺服器帳戶或 Hotmail 帳戶傳送使用者 A 電子郵件，並確認其送達使用者 A 的 Office 365 信箱。
        
9. 移動信箱內容
    
    1. 由於只有兩位使用者可以移動，而且由於使用者 A 和使用者 B 都使用 Outlook，因此可以開啟舊的電子郵件來移動電子郵件。PST 檔案，並複製郵件、行事曆專案、連絡人等，如從 Outlook 資料檔（.pst）匯入 Outlook 專案中所示。 在 Office 365 信箱中的適當位置進行組織時，這些專案就可以從任何裝置從任何地方存取。
        
    2. 當涉及更多信箱，或如果員工尚未使用 Outlook，您可以使用 Exchange 系統管理中心提供的遷移工具。 若要開始使用，請移至 Exchange 系統管理中心，並遵循將電子郵件從 IMAP 伺服器遷移至 Exchange Online 信箱的指示。
    
