---
title: 在 123-reg.co.uk 建立 Office 365 的 DNS 記錄
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 商務用 Skype 線上商務和 123-reg.co.uk 其他服務的 DNS 記錄。
ms.openlocfilehash: acbc0f1c8a7eb7dcbe5f274d0f2c8b2c403e7de0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239911"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a>在 123-reg.co.uk 建立 Office 365 的 DNS 記錄

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果 123-reg.co.uk 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。
  
在 123-reg.co.uk 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。
  
若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果您遇到與郵件流程或其他問題新增 DNS 記錄之後，請參閱[尋找並修正新增網域或 Office 365 中的 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。系統會提示您先登入。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 [**管理 DNS** ] 頁面上，選取 [**進階 DNS** ] 索引標籤。 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**主機名稱** <br/> |**類型** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. 選取 **[新增]**。
    
7. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
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

1. 首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。 系統會提示您先登入。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 [**管理 DNS** ] 頁面上，選取 [**進階 DNS** ] 索引標籤。 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**主機名稱**|**類型**|**優先順序**|**Destination MX (目的地 MX)**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<網域金鑰\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **附註：** 取得您\<網域金鑰\>從您的 Office 365 帳戶。 [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![複製並貼上資料表中的值](../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. 選取 **[新增]**。
    
    ![選取 [新增]](../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. 如果有任何其他 MX 記錄，移除每個選擇該記錄的**刪除 （垃圾桶）** 圖示。 
    
    ![選取 [刪除 （垃圾桶可圖示）](../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>新增 Office 365 所需的六筆 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

1. 首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。 系統會提示您先登入。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 [**管理 DNS** ] 頁面上，選取 [**進階 DNS** ] 索引標籤。 
    
5. 新增六筆 CNAME 記錄的第一筆。
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**主機名稱**|**類型**|**Destination CNAME (目的地 CNAME)**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net>。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![複製並貼上表格中的值](../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. 選取 **[新增]**。
    
    ![選取 [新增]](../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. 新增其他五筆 CNAME 記錄。
    
    在 [**進階 DNS** ] 區段中，在表格中，使用 [下一步] 列中的值建立記錄，然後再次選擇 [**新增**] 以完成該筆記錄。 
    
    重複這個程序，直到六筆 CNAME 記錄全部建立完畢。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? 請查看這些[Office 365 的外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。 To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. 首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。 系統會提示您先登入。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 [**管理 DNS** ] 頁面上，選取 [**進階 DNS** ] 索引標籤。 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**主機名稱**|**類型**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
   
    ![123Reg-DYN-BP-CONFIGURE-1-設定-4-1](../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. 選取 **[新增]**。
    
    ![選取 [新增]](../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>新增兩筆 Office 365 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

1. 首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。 系統會提示您先登入。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 [**管理 DNS** ] 頁面上，選取 [**進階 DNS** ] 索引標籤。 
    
5. 新增兩筆 SRV 記錄的第一筆：
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |主機名稱|Type (類型)|Priority (優先順序)|TTL|Destination SRV (目的 SRV)|
    |_sip._tls|SRV|100|3600|1 443 sipdir.online.lync.com>。 **This value MUST end with a period (.)**<br> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
    |_sipfederationtls._tcp|SRV|100|3600|1 5061 sipfed.online.lync.com>。 **This value MUST end with a period (.)** <br> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
   
    ![複製並貼上表格中的值](../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. 選取 **[新增]**。
    
    ![選取 [新增]](../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. 新增另一筆 SRV 記錄：
    
    在 [**進階 DNS** ] 區段中，在表格中，使用第二列的值來建立記錄，然後再次選擇 [**新增**] 以完成該筆記錄。 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果您遇到與郵件流程或其他問題新增 DNS 記錄之後，請參閱[尋找並修正新增網域或 Office 365 中的 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
