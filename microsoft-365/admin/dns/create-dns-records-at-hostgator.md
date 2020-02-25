---
title: 在 Hostgator 建立 Office 365 的 DNS 記錄
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: 了解如何驗證您的網域和設定 Office 365 電子郵件、 Skype for Business Online，與其他服務 hostgator 的 DNS 記錄。
ms.openlocfilehash: cb0b26081e5946ed2558d090c976847197ed7eb8
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240882"
---
# <a name="create-dns-records-at-hostgator-for-office-365"></a>在 Hostgator 建立 Office 365 的 DNS 記錄

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果 Hostgator 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。
  
> [!IMPORTANT]
> 您新增 DNS 記錄在本文中使用任何其他程序之前，您必須執行第一個 procedurebelow，也就是[點網域至您的代管帳戶](#point-your-domain-to-your-hosting-account)]。 

您所有的這些變更 hostgator 之後，請您的網域就是設定為搭配 Office 365 服務。
  
若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果您遇到與郵件流程或其他問題新增 DNS 記錄之後，請參閱[尋找並修正新增網域或 Office 365 中的 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="point-your-domain-to-your-hosting-account"></a>您的網域指向您的代管帳戶
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> 本文中執行任何其他程序之前，您必須執行此程序。 
  
請遵循下列步驟，建立您的網域和代管帳戶的關聯。
  
1. 若要開始，使用[這個連結](https://portal.hostgator.com/)移至 hostgator 上您的網域管理頁面。 You'll be prompted to log in.
    
2. 選取左側的 [**網域**]。
  
3. 在 [**管理網域**] 頁面上，選取您想要更新的網域。 
  
4. 在左側快顯功能表，選取**名稱伺服器**。
  
5. 在您的網域，在**自動指向此網域來主控我的帳戶**] 下拉式清單中的 [**名稱伺服器**] 頁面上選擇 [您的網域相關聯的代管帳戶]。 
  
6. 選取 [**儲存名稱伺服器**。
    
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> 執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。 
  
在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 若要開始使用，請移至您位於 Hostgator 的 cPanel 頁面。系統會提示您先登入。
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Nm-server-w15-cpanel-short 地址應該看起來像這樣： https://YourSiteAddress:secure-port-number。 註冊您要從 Hostgator 收到的電子郵件將會指定該位址，以及 Nm-server-w15-cpanel-short 連結上也會有 [**裝載**] 頁面。）
    
    > [!IMPORTANT]
    > 若要讓 cPanel 與您的網域相關聯，要有一個 Hostgator 代管的帳戶。若要開始使用 Office 365，您可以從 Hostgator 購買代管帳戶或[重新委派您的名稱伺服器以指向 Office 365](change-nameservers-at-hostgator.md)。 
  
2. 在 **[控制台]** 頁面上，在 [**網域**] 區域中，選取**進階區域編輯器**。
    
3. 在 [**進階區域編輯器**] 頁面中**新增記錄**] 區域中，於新記錄的方塊中輸入或複製並貼上下表中的值。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**TTL** <br/> |**類型** <br/> |**TXT Data** <br/> |
    |使用您的*domain_name*。 (for example, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. 選取 [**新增記錄**]。
    
5. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。
    
2. 在 [**網域**] 頁面上，選取您要驗證的網域。 
    
3. 在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。
    
4. 在 [**驗證網域**] 頁面上，選取 [**驗證**]。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果您遇到與郵件流程或其他問題新增 DNS 記錄之後，請參閱[尋找並修正新增網域或 Office 365 中的 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> 執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Nm-server-w15-cpanel-short 地址應該看起來像這樣： https://YourSiteAddress:secure-port-number。 註冊您要從 Hostgator 收到的電子郵件將會指定該位址，以及 Nm-server-w15-cpanel-short 連結上也會有 [**裝載**] 頁面。）
    
    > [!IMPORTANT]
    > 若要讓 cPanel 與您的網域相關聯，要有一個 Hostgator 代管的帳戶。若要開始使用 Office 365，您可以從 Hostgator 購買代管帳戶或[重新委派您的名稱伺服器以指向 Office 365](change-nameservers-at-hostgator.md)。 
  
2. 在 **[控制台]** 頁面上，在 [**電子郵件**] 區域中，選取**MX 項目**。
    
 
3. 在 [**電子郵件路由**] 區域中，選取 [**遠端郵件交換程式**]。

4. 選取 [**變更**]。
  
5. 在 [**新增新的記錄**] 區域中，於新記錄的方塊中輸入或複製並貼上下表中的值。 
    
    |**優先順序**|**目的地**|
    |:-----|:-----|
    |0  <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<網域金鑰\>*  .mail.protection.outlook.com  <br/> **附註：** 取得您\<*網域金鑰*\>從您的 Office 365 帳戶。    [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
  
6. 選取 [**加入新的記錄**。
   
 
7. 如果 [ **MX 記錄**] 區段中有任何其他 MX 記錄，逐一移除。 

    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>新增 Office 365 所需的六筆 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> 執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Nm-server-w15-cpanel-short 地址應該看起來像這樣： https://YourSiteAddress:secure-port-number。 註冊您要從 Hostgator 收到的電子郵件將會指定該位址，以及 Nm-server-w15-cpanel-short 連結上也會有 [**裝載**] 頁面。）
    
    > [!IMPORTANT]
    > 若要讓 cPanel 與您的網域相關聯，要有一個 Hostgator 代管的帳戶。若要開始使用 Office 365，您可以從 Hostgator 購買代管帳戶或[重新委派您的名稱伺服器以指向 Office 365](change-nameservers-at-hostgator.md)。 
  
2. 在 **[控制台]** 頁面上，在 [**網域**] 區域中，選取**進階區域編輯器**。
    
3. 新增六筆 CNAME 記錄的第一筆。
    
    在 [**進階區域編輯器**] 頁面中**新增記錄**] 區域中，於新記錄的方塊中輸入或複製並貼下表中第一列的值。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**TTL**|**類型**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*。 (例如，autodiscover.fourthcoffee.com)。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*。 (例如，sip.fourthcoffee.com)。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com>  <br/> |
    |lyncdiscover. *domain_name*。 (例如，lyncdiscover.fourthcoffee.com)。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com>  <br/> |
    |enterpriseregistration. *domain_name*。 (例如，enterpriseregistration.fourthcoffee.com)。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net>  <br/> |
    |enterpriseenrollment. *domain_name*。 (例如，enterpriseregistration.fourthcoffee.com)。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. 選取 [**新增記錄**]。

5. 逐一新增其餘五筆 CNAME 記錄。
    
    在 [**新增記錄**] 區段中的使用中表格中下, 一列的值建立記錄，然後再次選擇 [**新增記錄**以完成該筆記錄。 
    
    重複這個程序，直到六筆 CNAME 記錄全部建立完畢。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. 而是，請將必要的 Office 365 值新增至目前的記錄，以便擁有包含這兩組值的單一 SPF 記錄。 需要範例？ 請查看這些[Office 365 的外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。 To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
> [!IMPORTANT]
> 執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Nm-server-w15-cpanel-short 地址應該看起來像這樣： https://YourSiteAddress:secure-port-number。 註冊您要從 Hostgator 收到的電子郵件將會指定該位址，以及 Nm-server-w15-cpanel-short 連結上也會有 [**裝載**] 頁面。）
    
    > [!IMPORTANT]
    > 若要讓 cPanel 與您的網域相關聯，要有一個 Hostgator 代管的帳戶。若要開始使用 Office 365，您可以從 Hostgator 購買代管帳戶或[重新委派您的名稱伺服器以指向 Office 365](change-nameservers-at-hostgator.md)。 
  
2. 在 **[控制台]** 頁面上，在 [**網域**] 區域中，選取**進階區域編輯器**。
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**TTL**|**類型**|**TXT Data**|
    |:-----|:-----|:-----|:-----|
    |使用您的*domain_name*。 (for example, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
  
4. 選取 [**新增記錄**]。
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>新增兩筆 Office 365 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> 執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Nm-server-w15-cpanel-short 地址應該看起來像這樣： https://YourSiteAddress:secure-port-number。 註冊您要從 Hostgator 收到的電子郵件將會指定該位址，以及 Nm-server-w15-cpanel-short 連結上也會有 [**裝載**] 頁面。）
    
    > [!IMPORTANT]
    > 若要讓 cPanel 與您的網域相關聯，要有一個 Hostgator 代管的帳戶。若要開始使用 Office 365，您可以從 Hostgator 購買代管帳戶或[重新委派您的名稱伺服器以指向 Office 365](change-nameservers-at-hostgator.md)。 
  
2. 在 **[控制台]** 頁面上，在 [**網域**] 區域中，選取**進階區域編輯器**。

    
3. 新增兩筆 SRV 記錄中的第一筆。
    
    在 [**進階 DNS 區域編輯器**] 頁面中**新增記錄**] 區域中，於新記錄的方塊中輸入或複製並貼下表中第一列的值。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**TTL**|**類型**|**優先順序**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls。 *domain_name*。 (例如 _sip._tls.fourthcoffee.com)。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com>  <br/> |
    |_sipfederationtls._tcp。 *domain_name*。 (例如，_sipfederationtls._tcp.fourthcoffee.com)。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com>  <br/> |
   

4. 選取 [**新增記錄**]。

  
5. 新增另一筆 SRV 記錄。
    
    在 [**新增記錄**] 區段中的使用中表格中下, 一列的值建立記錄，然後再次選擇 [**新增記錄**以完成該筆記錄。 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果您遇到與郵件流程或其他問題新增 DNS 記錄之後，請參閱[尋找並修正新增網域或 Office 365 中的 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
