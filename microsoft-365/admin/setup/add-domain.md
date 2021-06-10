---
title: 將網域新增至 Microsoft 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: 在您的 dns 主機上新增 dns 記錄，使用設定向導將您的網域新增至 Microsoft 365 系統管理中心的 Microsoft 365。
ms.openlocfilehash: 152144737b0ff8cb8b0c27db2a4fc1051fb2a8a7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635675"
---
# <a name="add-a-domain-to-microsoft-365"></a>將網域新增至 Microsoft 365

 若您找不到所需內容，請 **[查看網域常見問題集](domains-faq.yml)**。 
  
 *若要新增、修改或移除網域，您 **必須** 是 [企業或企業方案](https://products.office.com/business/office)的 **全域系統管理員**。這些變更會影響整個承租人、*自訂* 的系統管理員或 *一般使用者* 無法進行這些變更。*  

 ## <a name="add-a-domain"></a>新增網域

請遵循下列步驟來新增、設定或繼續設定網域。 

::: moniker range="o365-worldwide"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。

::: moniker-end
::: moniker range="o365-germany"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的系統管理中心。

::: moniker-end

::: moniker range="o365-21vianet"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的系統管理中心。

::: moniker-end
    
2. 移至 [**設定**  >  **網域**] 頁面。 

3. 選取 ****[新增網域]。
    
4. 輸入您要新增的功能變數名稱，然後選取 **[下一步]**。
    
5. 選擇您要如何驗證您擁有該網域。
    
    1. 如果您的網域註冊機構使用[網域連線](#domain-connect-registrars-integrating-with-microsoft-365)，Microsoft 將會您登入註冊機構，並確認要 Microsoft 365 的連線，以[自動設定記錄](../get-help-with-domains/domain-connect.md)。 您將會傳回系統管理中心，然後 Microsoft 將會自動驗證您的網域。
    2. 您可以使用 TXT 記錄來驗證您的網域。 選取 **[下一步]，然後選取 [下一步]** ，查看如何將此 DNS 記錄新增至您註冊機構網站的指示。 在您新增記錄後，可能需要長達30分鐘的時間來進行驗證。 
    3. 您可以將文字檔新增至您網域的網站。 從安裝精靈選取並下載 .txt 檔案，然後將檔案上傳至網站的最上層資料夾。 檔案的路徑看起來應該類似下列所示： `http://mydomain.com/ms39978200.txt` 。 我們會在您的網站上尋找檔案，以確認您擁有該網域。
    
6. 選擇您想要如何進行 DNS 變更，Microsoft 才能使用您的網域。
    
    1. 如果您的註冊機構支援 [網域連線](#domain-connect-registrars-integrating-with-microsoft-365)，請選擇 [**為我新增 DNS 記錄**]，Microsoft 將會您登入註冊機構，並確認要 Microsoft 365 的連線，以 [自動設定記錄](../get-help-with-domains/domain-connect.md)。
    2. 如果您只想要將特定的 Microsoft 365 服務附加至您的網域，或是您現在略過這種情況，請選擇 [**我要自行新增 DNS 記錄**]，否則請稍後再做。 **如果您確切知道您在做什麼，請選擇此選項。**

7. 如果您選擇 *自行新增 DNS 記錄*  ，請選取 **[下一步]** ，您將會看到一個頁面，其中包含您需要新增至註冊機構網站以設定網域的所有記錄。 

    如果入口網站無法辨認您的註冊機構，您可以[遵循這些一般指示](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (機器翻譯)。
    
    查看我們的[特定主機指示](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) 來尋找您的主機，並遵循步驟來新增您需要的所有記錄。 
    
    如果您不知道您網域的 DNS 主機提供者或網域註冊機構，請參閱[尋找您的網域註冊機構或 DNS 主機服務提供者](../get-help-with-domains/find-your-domain-registrar.md)。
    
    若要稍等片刻，請取消選取 [所有服務]，然後按一下 [ **繼續**]，或在先前的網域連線步驟中，選取 [ **更多選項** ]，然後選取 [ **立即略過此** 項]。
    
8. 選取 **[完成]** -您已經完成！

## <a name="add-or-edit-custom-dns-records"></a>新增或編輯自訂 DNS 記錄

請遵循下列步驟，為網站或協力廠商服務新增自訂記錄。

1. 登入 Microsoft 系統管理中心，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 移至 [**設定**   >  **網域**] 頁面。

3. 在 [ **網域** ] 頁面上，選取網域。 
    
4. 在 [ **DNS 設定**] 底下，選取 [ **自訂記錄**]，然後選取 [ **新增自訂記錄**]。

5. 選取您要新增的 DNS 記錄類型，然後輸入新記錄的資訊。
    
6. 選取 ****[儲存]。

## <a name="registrars-with-domain-connect"></a>使用網域連線的註冊機構

[網域連線](https://www.domainconnect.org/)啟用型註冊機構可讓您將您的網域新增至以每三個步驟為間隔的三個步驟中 Microsoft 365。 
  
在 [！附注] 中，我們只會確認您擁有網域，然後自動設定您的網域記錄，所以電子郵件會送出 Microsoft 365 和其他 Microsoft 365 服務，如 Teams，請與您的網域搭配使用。
  
> [!NOTE]
> 啟動設定精靈之前，務必停用瀏覽器中的所有快顯封鎖程式。
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>與 Microsoft 365 整合的網域連線註冊機構

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- 使用 SecureServer DNS 主機的 SecureServer 或 WildWestDomains (GoDaddy 轉銷商) 
    - 範例：
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>我的電子郵件和網站會發生什麼情況？

完成設定之後，您的網域的 MX 記錄會更新，以指向 Microsoft 365，而且您網域的所有電子郵件都將開始進入 Microsoft 365。 請確認您已新增使用者，並為在您的網域中取得電子郵件的所有人設定 Microsoft 365 中的信箱！
  
如果您擁有商務用途的網站，該網站將會在原處繼續運作。 網域連線設定步驟不會影響您的網站。

## <a name="related-content"></a>相關內容

[網域常見問題集](domains-faq.yml) (文章)
[什麼是網域？](../get-help-with-domains/what-is-a-domain.md) (文章)\
[在 Microsoft 365 (文章中購買功能變數名稱](../get-help-with-domains/buy-a-domain-name.md)) \
[設定您的網域](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (文章) 