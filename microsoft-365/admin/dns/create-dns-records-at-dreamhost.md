---
title: 在 Dreamhost 建立 Office 365 的 DNS 記錄
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 Skype for Business Online，並在 Dreamhost 其他服務的 DNS 記錄。
ms.openlocfilehash: f3f52e97fefece72dd96d9370e75e24fc4cebedf
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240751"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a>在 Dreamhost 建立 Office 365 的 DNS 記錄

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果 DreamHost 是您 DNS 主機服務提供者，請遵循本篇文章以驗證您的網域和設定 DNS 記錄的電子郵件、 Lync、 等等中的步驟。
 
在 DreamHost 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務。
  
若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。
  
> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 若要開始，使用[這個連結](https://panel.dreamhost.com/)移至您在 DreamHost 的網域頁面。 系統會提示您登入。
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 在**儀表板**頁面上，選取 [**網域**]，然後按一下 [**管理網域**]。
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. 在 [**管理網域**] 頁面上，在 [**網域**] 區段中，選取**DNS**針對您想要編輯的網域。 
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**Type**|**Value**|**Comment**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |（此欄位是選用的）。  <br/> |
   
   ![Dreamhost-DYN-BP-CONFIGURE-1-確認-1-1](../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. 選取 [**現在新增記錄 ！**
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-確認-1-2](../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
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

請依照下列步驟進行。
  
1. 若要開始，使用[這個連結](https://panel.dreamhost.com/)移至您在 DreamHost 的網域頁面。 系統會提示您登入。
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 在 [**儀表板**] 頁面上，選取**郵件**，然後**自訂 MX**。
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-2-1](../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. 在 [**管理郵件傳遞**] 區段中 [**動作**] 欄中，選取您想要編輯的網域的 [**編輯**]。 
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-2-2](../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. 在 [**自訂 MX 記錄**] 區段，於新記錄的方塊中輸入或複製並貼上下表中的下列值。 
    
    (You may have to scroll down.)
    
    （如果有任何其他現有的 MX 記錄，將標示要刪除的記錄）。
    
    |**MX 記錄 （必要）**|
    |:-----|
    |0  *\<網域金鑰\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> 0 是指 MX 優先順序值。請將它新增到 MX 值的開頭，並以空格分隔該值的其餘部分。  <br/> **附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-2-3](../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. 選取 [**變更此網域若要使用自訂 MX 記錄，現在 ！**
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-2-4](../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. 如果有任何其他現有的 MX 記錄，請選取項目，然後按鍵盤上的**Delete**鍵刪除每一筆記錄。 
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-2-5](../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. 如果您已刪除任何記錄，選取 [**立即更新您的自訂 MX 記錄 ！**
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-2-6](../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>新增 Office 365 所需的六筆 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

請依照下列步驟進行。
  
1. 若要開始，使用[這個連結](https://panel.dreamhost.com/)移至您在 DreamHost 的網域頁面。 系統會提示您登入。
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 在**儀表板**頁面上，選取 [**網域**]，然後按一下 [**管理網域**]。
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. 在 [**管理網域**] 頁面上，在 [**網域**] 區段中，選取**DNS**針對您想要編輯的網域。 
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. 在 [**新增自訂的 DNS 記錄**] 區段，於新記錄的方塊中輸入或複製並貼下表中第一列的值。 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**Type**|**Value**|**Comment**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |（此欄位是選用的）。  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |（此欄位是選用的）。  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |（此欄位是選用的）。  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net>。  <br/> **This value MUST end with a period (.)** <br/> |（此欄位是選用的）。  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **This value MUST end with a period (.)** <br/> |（此欄位是選用的）。  <br/> |
   
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-3-1](../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. 選取 [**現在新增記錄 ！**
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-3-2](../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. 使用表格中的前兩個步驟和其他五列的值，新增每個其他五筆 CNAME 記錄。

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.
  
請依照下列步驟操作。
  
1. 若要開始，使用[這個連結](https://panel.dreamhost.com/)移至您在 DreamHost 的網域頁面。 系統會提示您登入。
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 在**儀表板**頁面上，選取 [**網域**]，然後按一下 [**管理網域**]。
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. 在 [**管理網域**] 頁面上，在 [**網域**] 區段中，選取**DNS**針對您想要編輯的網域。 
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. 在 [**新增自訂的 DNS 記錄**] 區段，於新記錄的方塊中輸入或複製並貼下表中第一列的值。 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**Type**|**Value**|**Comment**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |（此欄位是選用的）。  <br/> |
   
   ![Dreamhost-DYN-BP-CONFIGURE-1-設定-4-1](../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. 選取 [**現在新增記錄 ！**
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-4-2](../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. 使用表格中的前兩個步驟和第二列中的值，新增其他 SRV 記錄。
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>新增兩筆 Office 365 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

請依照下列步驟進行。
  
1. 若要開始，使用[這個連結](https://panel.dreamhost.com/)移至您在 DreamHost 的網域頁面。 系統會提示您登入。
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. 在**儀表板**頁面上，選取 [**網域**]，然後按一下 [**管理網域**]。
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. 在 [**管理網域**] 頁面上，在 [**網域**] 區段中，選取**DNS**針對您想要編輯的網域。 
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. 在 [**新增自訂的 DNS 記錄**] 區段，於新記錄的方塊中輸入或複製並貼下表中第一列的值。 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**Type**|**Value**|**Comment**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV  <br/> |100 1 443  <br/> sipdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |（此欄位是選用的）。  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV  <br/> |100 1 5061  <br/> sipfed.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |（此欄位是選用的）。  <br/> |
   
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-5-1](../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. 選取 [**現在新增記錄 ！**。
    
    ![Dreamhost-DYN-BP-CONFIGURE-1-設定-5-2](../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. 使用表格中的前兩個步驟和第二列中的值，新增其他 SRV 記錄。
    
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 

  
