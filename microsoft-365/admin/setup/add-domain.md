---
title: 新增網域至 Office 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: 在您的 DNS 主機上新增 DNS 記錄，將您的網域新增至 Microsoft 365 系統管理中心中的 Office 365。 安裝精靈會引導您完成此程式。
ms.openlocfilehash: bab4da6e4a8191d91ccdd38dd54f62f4d790c3b8
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140772"
---
# <a name="add-a-domain-to-office-365"></a>新增網域至 Office 365

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心變更。 [！附注] 如果您的經驗不符合這裡所述的詳細資料，請參閱[關於新的 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

 若您找不到所需內容，請**[查看網域常見問題集](domains-faq.md)**。 
  
 *若要新增、修改或移除網域，您**必須**是[企業或企業方案](https://products.office.com/business/office)的**全域系統管理員**。這些變更會影響整個承租人、*自訂*的系統管理員或*一般使用者*無法進行這些變更。*  

 請遵循下列步驟來新增、設定或繼續設定網域。 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。

::: moniker-end
::: moniker range="o365-germany"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的系統管理中心。

::: moniker-end

::: moniker range="o365-21vianet"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的系統管理中心。

::: moniker-end
    
2. 移至 [**安裝** > **網域**] 頁面。 

3. 選取 [**新增網域**]。
    
4. 輸入您要新增的功能變數名稱，然後選取 **[下一步]**。
    
5. 選擇您要如何驗證您擁有該網域。
    
    1. 如果您的網域註冊于 GoDaddy 或 1&amp;1，請**選取** > **[下一步]** ，Microsoft[將會自動設定記錄](../get-help-with-domains/domain-connect.md)。
    
    2. 您可以傳送一封含有驗證碼的電子郵件給網域的已登記連絡人。 如果您無法辨識或存取記錄中的電子郵件，您可以使用第三個選項。
    
    3. 您可以使用 TXT 記錄來驗證您的網域。 選取 **[下一步]，然後選取 [下一步]** ，查看如何將此 DNS 記錄新增至您註冊機構網站的指示。 在您新增記錄後，可能需要長達30分鐘的時間來進行驗證。 
    
6. 選擇您想要如何進行 DNS 變更，Office 才能使用您的網域。
    
    1. 如果您想要讓 Office 自動設定 DNS，請選擇 [**為我新增 dns 記錄**]。 
    
  
    2. 如果您只想要將特定的 Office 365 服務附加至您的網域，請選擇 [**我要自行新增 DNS 記錄**]，否則請稍後再進行此操作。 **如果您確切知道您在做什麼，請選擇此選項。**
    
7. 如果您選擇*自行新增 DNS 記錄*，請選取 **[下一步]** ，您將會看到一個頁面，其中包含您需要新增至註冊機構網站以設定網域的所有記錄。 
    
  
  
    如果入口網站無法辨認您的註冊機構，您可以[遵循這些一般指示](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (機器翻譯)。
    
    查看我們的[特定主機指示](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) 來尋找您的主機，並遵循步驟來新增您需要的所有記錄。 
    
    如果您不知道您網域的 DNS 主機提供者或網域註冊機構，請參閱[尋找您的網域註冊機構或 DNS 主機服務提供者](../get-help-with-domains/find-your-domain-registrar.md)。
    
    如果您想稍後等候，請滾動至底部，然後選取 [**略過此步驟**]。
    
8. 選取 **[完成]** -您已經完成！ 

## <a name="add-or-edit-custom-dns-records"></a>新增或編輯自訂 DNS 記錄

請遵循下列步驟，為網站或協力廠商服務新增自訂記錄。

1. 登入 Microsoft 系統管理中心，網址<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>為。

2. 移至 [**設定**  > **網域**] 頁面。

3. 在 [**網域**] 頁面上，選取網域。 
    
4. 在 [ **DNS 設定**] 底下，選取 [**自訂記錄**]，然後選取 [**新增自訂記錄**]。

5. 選取您要新增的 DNS 記錄類型，然後輸入新記錄的資訊。
    
6. 選取 [儲存]****。

## <a name="registrars-with-domain-connect"></a>使用網域連接的註冊機構

已啟用[網域](https://www.domainconnect.org/)連線註冊機構可讓您將網域新增至 Microsoft 365，並以三個步驟為單位，以分鐘為單位。 
  
在 [！附注] 中，我們只會確認您擁有網域，然後自動設定您的網域記錄，所以電子郵件會送出至 Microsoft 365 和其他 Microsoft 365 服務，如小組，請與您的網域合作。
  
> [!NOTE]
> 啟動設定精靈之前，務必停用瀏覽器中的所有快顯封鎖程式。
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>與 Microsoft 365 整合的網域連接註冊機構

- [1&amp;1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [Wordpress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer 或 WildWestDomains （使用 SecureServer DNS 主控的 GoDaddy 轉銷商）
    - [MadDog 網域](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a>我的電子郵件和網站會發生什麼情況？

完成設定之後，您的網域的 MX 記錄會更新，以指向 Microsoft 365，而您網域的所有電子郵件都會開始進入 Microsoft 365。 請確認您已針對在您的網域取得電子郵件的每位人員，在 Office 365 中新增使用者並設定信箱。
  
如果您擁有商務用途的網站，該網站將會在原處繼續運作。 網域連接設定步驟不會影響您的網站。

## <a name="related-articles"></a>相關文章

[網域常見問題集](domains-faq.md)

[什麼是網域？](../get-help-with-domains/what-is-a-domain.md)

[在 Office 365 中購買網域名稱](../get-help-with-domains/buy-a-domain-name.md)

[設定您的網域 (主機專用指示)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[取得網域的說明](../get-help-with-domains/get-help-with-domains.md)
