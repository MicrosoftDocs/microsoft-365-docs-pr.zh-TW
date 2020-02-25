---
title: 在 DNSMadeEasy 建立 Office 365 的 DNS 記錄
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: 了解如何驗證您的網域和設定 Office 365 電子郵件、 Skype for Business Online，與其他服務在 DNSMadeEasy 的 DNS 記錄。
ms.openlocfilehash: 7b94b8d4b3a02a0f436ba2af314eece8b7606ec2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240722"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a>在 DNSMadeEasy 建立 Office 365 的 DNS 記錄

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果 DNSMadeEasy 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。
  
在 DNSMadeEasy 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。
  
若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果您遇到與郵件流程或其他問題新增 DNS 記錄之後，請參閱[尋找並修正新增網域或 Office 365 中的 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
> [!IMPORTANT]
> For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar. DNSMadeEasy does not offer domain registration services. Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership. 
  
1. 首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。 系統會提示您先登入。
    
2. 在 [**管理主控台**] 頁面上，在**最近更新的網域**] 區域中，選取您想要更新的網域。 
    
3. 在 [ **Managed DNS** ] 頁面的 [ **TXT 記錄**] 區域中，選取 [( **+**) 控制項 （**新增**）。
    
    (You may have to scroll down.)
    
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    ||||
    |:-----|:-----|:-----|
    |**Name** <br/> |**值** <br/> |**TTL** <br/> |
    |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. 選取 [**提交**]。
    
6. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
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

1. 首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。系統會提示您先登入。
    
2. 在 [**管理主控台**] 頁面上，在**最近更新的網域**] 區域中，選取您想要更新的網域。 
    
    在 [**管理主控台**] 頁面上，在**最近更新的網域**] 區域中，選取您想要更新的網域。 
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-1-2](../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. 在 [ **Managed DNS** ] 頁面上，在 [ **MX 記錄**] 區域中，選取 **（+）** 控制項 （**新增**）。
    
    (You may have to scroll down.)
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-2-1](../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. 在 [**新增 MX 記錄**] 區域中，於新記錄的方塊中輸入或複製並貼上下表中的值。 
    
    (You may have to scroll down.)
    
    |**名稱**|**伺服器**|**MX Level (MX 等級)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |(將此欄位保留空白。)  <br/> | *\<網域金鑰\>*  .mail.protection.outlook.com  <br/> **This value MUST end with a period (.)** <br/> **附註：** 取得您\<*網域金鑰*\>從您的 Office 365 帳戶。 [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |1800  <br/> |
   
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-2-2](../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. 選取 [**提交**]。
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-2-3](../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. 如果有任何其他 MX 記錄列在 [ **MX 記錄**] 區段中，請選取每個來刪除全部。 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. 選取所有記錄時，選取 [**刪除選取的**。
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. 在 [**刪除的 MX 記錄**] 對話方塊中，選取 [**刪除**] 以確認您的變更。 
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-2-5](../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>新增 Office 365 所需的五筆 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

1. 首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。系統會提示您先登入。
    
2. 在 [**管理主控台**] 頁面上，在**最近更新的網域**] 區域中，選取您想要更新的網域。 
    
3. 在 [ **Managed DNS** ] 頁面上**筆 CNAME 記錄**] 區域中，選取 **（+）** 控制項 （**新增**）。
    
    (您可能需要向下捲動。)
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-3-1](../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. 新增第一筆五筆 CNAME 記錄。
    
    在 [**新增 CNAME 記錄**] 區域中，於新記錄的方塊中輸入或複製並貼下表中第一列的值。 
    
    |**Name**|**Alias to (別名)**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net>。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-3-2](../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. 選取 [**提交**]。
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-3-3](../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. 新增每個其他四筆 CNAME 記錄。
    
    在 [ **CNAME 記錄**] 區段中，選擇 **（+）** 控制項 （**新增**） 在表格中，使用下一列的值來建立記錄，然後再次選擇 [**提交**]，以完成該筆記錄。 
    
    重複此程序，直到五筆 CNAME 記錄全部建立完畢。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? 請查看這些[Office 365 的外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)。 若要驗證您的 SPF 記錄，您可以使用其中一種[SPF 驗證工具](../setup/domains-faq.md)。 
  
1. 首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。 系統會提示您先登入。
    
2. 在 [**管理主控台**] 頁面上，在**最近更新的網域**] 區域中，選取您想要更新的網域。 
    
3. 在 [ **Managed DNS** ] 頁面上，在 [ **TXT 記錄**] 區域中，選取 **（+）** 控制項 （**新增**）。
    
    (您可能需要向下捲動。)
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-4-1](../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Name**|**值**|**TTL**|
    |:-----|:-----|:-----|
    |(將此欄位保留空白。)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |1800  <br/> |
   
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-4-2](../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. 選取 [**提交**]。
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-4-3](../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>新增兩筆 Office 365 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

1. 首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。系統會提示您先登入。
    
2. 在 [**管理主控台**] 頁面上，在**最近更新的網域**] 區域中，選取您想要更新的網域。 
    
3. 在 [ **Managed DNS** ] 頁面上**SRV 記錄**] 區域中，選取 **（+）** 控制項 （**新增**）。
    
    (您可能需要向下捲動)
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-5-1](../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. 新增兩筆 SRV 記錄中的第一筆。
    
    在 [**新增 SRV 記錄**] 區域中，於新記錄的方塊中輸入或複製並貼下表中第一列的值。 
    
    |**Name**|**優先順序**|**Weight**|**Port**|**Host (主機)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-5-2](../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. 選取 [**提交**]。
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-5-3](../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. 新增另一筆 SRV 記錄。
    
    在 [ **SRV 記錄**] 區段中，選擇 **（+）** 控制項 （**新增**） 在表格中，使用下一列的值來建立記錄，然後再次選擇 [**提交**]，以完成該筆記錄。 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果您遇到與郵件流程或其他問題新增 DNS 記錄之後，請參閱[尋找並修正新增網域或 Office 365 中的 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  

