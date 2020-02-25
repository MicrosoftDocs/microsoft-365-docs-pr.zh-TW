---
title: 新增網域至 Office 365
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
description: 在您的 DNS 主機新增 DNS 記錄，您的網域新增至 Microsoft 365 系統管理中心中的 Office 365。 安裝精靈引導您逐步完成程序。
ms.openlocfilehash: 4170fd74ae734a6fda9e535c17086997b1db6f6b
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240270"
---
# <a name="add-a-domain-to-office-365"></a>新增網域至 Office 365

 若您找不到所需功能，請**[檢查網域常見問題集](domains-faq.md)**。 
  
 *要新增、 修改或移除您**必須**是**全域系統管理員**的[商務或企業方案](https://products.office.com/business/office)的網域。這些變更會影響整個租用戶*自訂系統管理員*或*一般使用者*將無法進行這些變更。*  

 遵循下列步驟來新增、 設定，或繼續設定網域。 

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
    
2. 移至 [**設定** > **網域**] 頁面。 

3. 選取 [**新增網域]**。
    
4. 輸入您想要新增的網域名稱，然後選取 [**下一步**]。
    
5. 選擇您要驗證您擁有該網域的方式。
    
    1. 如果您的網域註冊在 GoDaddy 或 1&amp;1，選取 [**登入** > **下一個**] 和 [Office 365[會自動設定您的記錄](../get-help-with-domains/domain-connect.md)。
    
    2. 您可以傳送一封含有驗證碼的電子郵件給網域的已登記連絡人。 如果您無法辨識，或是在記錄上無法存取電子郵件，您可以使用第三個選項。
    
    3. 您可以使用 TXT 記錄來驗證您的網域。 選取此選項，然後選取 [**下一步**若要查看如何將這個 DNS 記錄新增至您的註冊機構網站的指示。 這可能需要 30 分鐘，若要確認您已新增記錄之後。 
    
6. 選擇您想要進行所需的 Office，以使用您的網域的 DNS 變更的方式。
    
    1. 如果您想要 Office 自動設定您的 DNS，請選擇 [**新增我的 DNS 記錄**]。 
    
  
    2. 如果您想要將只有特定的 Office 365 服務附加到您的網域，或如果您想要跳過此現在和更新版本執行這項操作，選擇 [**我將自己新增 DNS 記錄**。 **如果您確切知道您在做什麼，請選擇此選項。**
    
7. 如果您選擇要*新增您自己的 DNS 記錄*，選取 [**下一步]** 並您會看到您要新增至您的註冊機構網站，以設定您的網域的所有記錄的頁面。 
    
  
  
    如果入口網站無法辨認您的註冊機構，您可以[遵循這些一般指示](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (機器翻譯)。
    
    查看我們的[特定主機指示](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) (機器翻譯) 來尋找您的主機，並遵循步驟來新增您需要的所有記錄。 
    
    如果您不知道您網域的 DNS 主機提供者或網域註冊機構，請參閱[尋找您的網域註冊機構或 DNS 主機服務提供者](../get-help-with-domains/find-your-domain-registrar.md)。
    
    如果您想要稍後，捲動至底部，然後選取 [**略過此步驟**。
    
8. 選取 [**完成**]-大功告成 ！ 

## <a name="related-articles"></a>相關文章

[網域常見問題集](domains-faq.md)

[什麼是網域？](../get-help-with-domains/what-is-a-domain.md)

[在 Office 365 中購買網域名稱](../get-help-with-domains/buy-a-domain-name.md)

[設定您的網域 (主機專用指示)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[取得 Office 365 網域的說明](../get-help-with-domains/get-help-with-domains.md)
