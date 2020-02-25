---
title: 在 web.com 為 Office 365 建立 DNS 記錄
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 商務用 Skype 線上商務和 web.com 在其他服務的 DNS 記錄。
ms.openlocfilehash: eb231f85e568e81a5e229f0533d8176feb590f48
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249453"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a>在 web.com 為 Office 365 建立 DNS 記錄

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果 web.com 是您 DNS 主機服務提供者，請遵循本篇文章以驗證您的網域和設定 DNS 記錄的電子郵件、 Skype for Business Online 等等中的步驟。
  
在 web.com 新增這些記錄之後，您的網域就是設定為搭配 Office 365 服務。
  
若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>變更您網域的名稱伺服器 (NS) 記錄
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> 您必須在您購買及註冊網域的網域註冊機構中執行此程序。 
  
當您註冊 web.com 」 時，您可以新增網域使用 web.com**安裝**程序。 
  
若要確認並在 Office 365 建立 DNS 記錄為您的網域，您需要變更的名稱伺服器，在您網域註冊機構，讓他們使用 web.com 的名稱伺服器。
  
若要自行在網域註冊機構網站變更自家網域的名稱伺服器，請遵循下列步驟進行：
  
1. 在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。
    
2. 在下列表格中，使用的值來建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，使其符合這些值。
    
    |||
    |:-----|:-----|
    |First nameserver (第一個名稱伺服器)  <br/> |使用 web.com 所提供的名稱伺服器值。  <br/> |
    |Second nameserver (第二個名稱伺服器)  <br/> |使用 web.com 所提供的名稱伺服器值。  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 如果沒有列出任何其他名稱伺服器，您應該將予以刪除。 
  
3. 儲存變更。
    
> [!NOTE]
> 您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 若要開始，使用[這個連結](https://checkout.web.com/manage-it/index.jsp)移至 web.com 上您的網域頁面。 登入。
  
2. 在 [**帳號管理員**] 頁面上，選取 [**我的網域名稱**。 
  
3. [* * 管理 * 我的網域 * * *，選取 [**編輯進階 DNS 記錄**。

  
4. 在**網域名稱**] 頁面的 [**文字 （TXT 記錄）**，按一下 [**編輯 TXT 記錄**，，然後選取值從下表。 
    
    |**Host (主機)**|**TTL**|**Text**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. 選取 [**繼續**]。
  
  
6. 請稍候幾分鐘，才確認您新增 TXT 記錄] 中，使您剛剛建立的記錄可以在網際網路上更新。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。

    
2. 在 [**網域**] 頁面上，選取您要驗證的網域。 
    
    
  
3. 在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。
    
    
  
4. 在 [**驗證網域**] 頁面上，選取 [**驗證**]。
    
    
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365
<a name="BKMK_add_MX"> </a>

1. 若要開始，使用[這個連結](https://checkout.web.com/manage-it/index.jsp)移至 web.com 上您的網域頁面。 登入。
  
2. 在 [**帳號管理員**] 頁面上，選取 [**我的網域名稱**。 
  
3. [* * 管理 * 我的網域 * * *，選取 [**編輯進階 DNS 記錄**。

4. **郵件伺服器 （MX 記錄）**] 下按一下 [**編輯 MX 記錄**，，然後選取值從下表。 
    
    |**Priority** (優先順序)|**TTL**|**郵件伺服器**|
    |:-----|:-----|:-----|
    |1  <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |3600  <br/> |*\<網域金鑰\>*  .mail.protection.outlook.com  <br/> **附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。   [How do I find this?](../get-help-with-domains/information-for-dns-records.md) |
   

5. 選取 **[儲存]**。
  
6. 如果有任何其他 MX 記錄列在 [ **MX 記錄**] 區段中，選取 [**刪除**的記錄旁的核取方塊，並選取 [**儲存**]。 
  
7. 在 [確認] 畫面中，選取 [**儲存變更**。 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>新增 Office 365 所需的六筆 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

1. 若要開始，使用[這個連結](https://checkout.web.com/manage-it/index.jsp)移至 web.com 上您的網域頁面。 You'll be prompted to log in first.
     
2. 在 [**帳號管理員**] 頁面上，選取 [**我的網域名稱**。 
  
3. [* * 管理 * 我的網域 * * *，選取 [**編輯進階 DNS 記錄**。

4. 新增六筆 CNAME 記錄的第一筆。
    
    在 [ **Host Aliases （CNAME 記錄）**] 下, 按一下 [**編輯 CNAME 記錄**，，然後選取值從下表。
    
    
    |**Alias**|**TTL**|**參照的主機名稱**|**其他主機**|
    |:-----|:-----|:-----|:-----|
    |autodiscover (自動探索)  <br/> |3600  <br/> |@ （無）  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ （無）  <br/> |sipdir.online.lync.com>  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ （無）  <br/> | webdir.online.lync.com>  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ （無）  <br/> |enterpriseregistration.windows.net>  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ （無）  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ （無）  <br/> |clientconfig.microsoftonline-p.net> qualified domain name  <br/> |
    
  
5. 選取 [**繼續**]。
  
6. 逐一新增其餘五筆 CNAME 記錄。

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
1. 若要開始，使用[這個連結](https://checkout.web.com/manage-it/index.jsp)移至 web.com 上您的網域頁面。 登入。
    
  
2. 在 [**帳號管理員**] 頁面上，選取 [**我的網域名稱**。 
  
3. [* * 管理 * 我的網域 * * *，選取 [**編輯進階 DNS 記錄**。

  
4. 在**網域名稱**] 頁面的 [**文字 （TXT 記錄）**，按一下 [**編輯 TXT 記錄**，，然後選取值從下表。   
    
    |**Host (主機)**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。   |

 
5. 選取 [**繼續**]。

6. 選取 [**儲存變更**。
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>新增兩筆 Office 365 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> 請記住，web.com 負責進行這項功能可用。 以防您看到下列步驟與目前 web.com GUI （圖形化使用者介面） 之間的差異，請利用[web.com 社群](https://community.web.com.com/)。 

1. 若要開始，使用[這個連結](https://checkout.web.com/manage-it/index.jsp)移至 web.com 上您的網域頁面。 登入。
      
2. 在 [**帳號管理員**] 頁面上，選取 [**我的網域名稱**。 
  
3. [* * 管理 * 我的網域 * * *，選取 [**編輯進階 DNS 記錄**。
  
4. 新增兩筆 SRV 記錄中的第一筆。

    在 [**服務 （SRV 記錄）**] 下按一下 [**編輯 SRV 記錄**，，然後選取值從下表。 
        
    |**服務**|**通訊協定**|**TTL**|**優先順序**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1 |443 |sipfed.online.lync.com>  |
    |_sipfederationtls |_tcp |3600 |100 |1 |5061 | sipfed.online.lync.com> |

  
5. 從表格中第二列中選擇值新增其他 SRV 記錄。 
  
6. 選取 [**繼續**]。

7. 選取 [**儲存變更**。

    
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
