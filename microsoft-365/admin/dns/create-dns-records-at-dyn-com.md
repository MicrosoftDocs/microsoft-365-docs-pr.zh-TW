---
title: 在 Dyn.com 建立 Office 365 的 DNS 記錄
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 商務用 Skype 線上商務和 dyn.com 其他服務的 DNS 記錄。
ms.openlocfilehash: d4471ec84555efb349cc1e42d5048ebf044735e5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240750"
---
# <a name="create-dns-records-at-dyncom-for-office-365"></a>在 Dyn.com 建立 Office 365 的 DNS 記錄

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果 Dyn.com 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。
 
若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

1. 首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。系統會提示您先登入。
    
    ![Dyn-BP-Configure-1-1](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. 在 [**層級服務**] 頁面上，選取您想要編輯的網域**Dyn 標準 DNS 服務**。 
    
3. 在您網域的**DNS** ] 頁面上，選取 [**喜好設定**]。
    
4. 選取 [**啟用專家介面**]。
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host (主機)**|**TTL**|**類型**|**資料**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600 個  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-DYN-BP-CONFIGURE-1-確認-1-1](../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. 選取 [**建立記錄**]。
    
    ![Dyn-BP-Verify-1-2](../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
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

1. 首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。系統會提示您先登入。
    
    ![Dyn-BP-Configure-1-1](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. 在 [**層級服務**] 頁面上，選取您想要編輯的網域**Dyn 標準 DNS 服務**。 
    
3. 在您網域的 DNS] 頁面上，選取 [**喜好設定**]。
    
4. 選取 [**啟用專家介面**]。
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host (主機)**|**TTL**|**類型**|**資料**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600 個  <br/> |MX  <br/> |10  *\<網域金鑰\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **10**是指 MX 優先順序值。 請將它新增到 MX 值的開頭，並以空格分隔該值的其餘部分。  <br/> **附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)      <br>    For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
    ![Dyn-DYN-BP-CONFIGURE-1-設定-2-1](../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. 選取 [**建立記錄**]。
    
    ![Dyn-BP-Configure-2-2](../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. 如果有任何其他 MX 記錄，請將它們移除藉由選取 [**刪除**] 欄中的每個核取方塊。 
    
    ![Dyn-BP-Configure-2-3](../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. 選取 [**套用變更**]。
    
    ![Dyn-BP-Configure-2-4](../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>新增 Office 365 所需的六筆 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

1. 首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。系統會提示您先登入。
    
    ![Dyn-BP-Configure-1-1](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. 在 [**層級服務**] 頁面上，選取您想要編輯的網域**Dyn 標準 DNS 服務**。 
    
3. 在您網域的**DNS** ] 頁面上，選取 [**喜好設定**]。
    
4. 選取 [**啟用專家介面**]。
    
5. 新增六筆 CNAME 記錄的第一筆。
    
    在 [ **Add DNS Record** ] 區段，於新記錄的方塊中輸入或複製並貼上下表第一列的值。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host (主機)**|**TTL**|**類型**|**資料**|
    |:-----|:-----|:-----|:-----|
    |autodiscover (自動探索)  <br/> |600 個  <br/> |CNAME  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |600 個  <br/> |CNAME  <br/> |sipdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |600 個  <br/> |CNAME  <br/> |webdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |600 個  <br/> |CNAME  <br/> |enterpriseregistration.windows.net>。  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |600 個  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![Dyn-DYN-BP-CONFIGURE-1-設定-3-1](../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. 選取 [**建立記錄**]。
    
    ![Dyn-BP-Configure-3-2](../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. 新增剩餘的五筆 CNAME 記錄。
    
    在 [ **Add DNS Record** ] 區段中，在表格中，使用下一列的值來建立記錄，然後再次選擇 [**建立記錄**，以完成該筆記錄。 
    
    重複這個程序，直到六筆 CNAME 記錄全部建立完畢。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.
  
1. 首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。系統會提示您先登入。
    
    ![Dyn-BP-Configure-1-1](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. 在 [**層級服務**] 頁面上，選取您想要編輯的網域**Dyn 標準 DNS 服務**。 
    
3. 在您網域的**DNS** ] 頁面上，選取 [**喜好設定**]。
    
4. 選取 [**啟用專家介面**]。
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host (主機)**|**TTL**|**類型**|**資料**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600 個  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
   
    ![Dyn-DYN-BP-CONFIGURE-1-設定-4-1](../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. 選取 [**建立記錄**]。
    
    ![Dyn-BP-Configure-4-2](../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>新增兩筆 Office 365 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

1. 首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。 系統會提示您先登入 
    
    ![Dyn-BP-Configure-1-1](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. 在 [**層級服務**] 頁面上，選取您想要編輯的網域**Dyn 標準 DNS 服務**。 
    
3. 在您網域的**DNS** ] 頁面上，選取 [**喜好設定**]。
    
4. 選取 [**啟用專家介面**]。
    
5. 新增兩筆 SRV 記錄中的第一筆。
    
    在 [ **Add DNS Record** ] 區段，於新記錄的方塊中輸入或複製並貼上下表第一列的值。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host (主機)**|**TTL**|**類型**|**資料**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|600 個|SRV|100 1 443 sipdir.online.lync.com>。 **This value MUST end with a period (.)**<br>**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
    |_sipfederationtls._tcp|600 個|SRV|100 1 5061 sipfed.online.lync.com>。 **This value MUST end with a period (.)**<br> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
   
    ![Dyn-DYN-BP-CONFIGURE-1-設定-5-1](../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. 選取 [**建立記錄**]。
    
    ![Dyn-BP-Configure-5-2](../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. 新增另一筆 SRV 記錄。
    
    在 [ **Add DNS Record** ] 區段中的使用中表格中，第二列的值建立記錄，然後再次選擇 [**建立記錄**，以完成該筆記錄。 
    
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
