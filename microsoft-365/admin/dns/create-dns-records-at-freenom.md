---
title: 在 Freenom 建立 Office 365 的 DNS 記錄
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 Skype for Business Online，並在 Freenom 其他服務的 DNS 記錄。
ms.openlocfilehash: a1396964c7dc9c279589a6020e0c741fd0cb29d5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240795"
---
# <a name="create-dns-records-at-freenom-for-office-365"></a>在 Freenom 建立 Office 365 的 DNS 記錄

[檢查網域常見問題集](../setup/domains-faq.md)找不到您要尋找。 
  
> [!CAUTION]
> 在 Freenom 網站不支援 SRV 記錄，這表示幾個 Skype for Business Online 和 Outlook Web App 功能將無法運作。 不論您使用哪一個 Office 365 方案，有重大服務限制，以及您可能想要切換至不同的 DNS 主機服務提供者。 
  
儘管服務的限制，如果您選擇 [管理 Office 365 DNS 記錄，在 Freenom，請遵循本文以驗證您的網域及設定電子郵件和其他服務的 DNS 記錄中的步驟。
  
若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。
  
> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="bkmk_txt"> </a>

在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 若要開始，使用[此連結](https://my.freenom.com/)移至您在 Freenom 中的網域頁面。 You'll be prompted to log in.
    
    ![Freenom 登入](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 選取 [**服務**]，然後選取 [**我的網域**。
    
    ![Freenom 選取服務和我的網域](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 針對您想要編輯的網域，選取 [**管理網域**]。
    
    ![Freenom 選取 [管理網域](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 選取 [**管理 Freenom DNS**]。
    
    ![Freenom 管理 Freenom DNS](../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. [**新增記錄**，在 [**類型**] 欄中， **TXT**從功能表中選擇。 
    
    ![Freenom 新增記錄類型 TXT](../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Name**|**Type**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(保留空白)  <br/> |TXT  <br/> |3600 （秒）  <br/> |MS = msXXXXXXXX  <br/> **附註：** 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT 值，以供驗證](../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. 選取 [**儲存變更**。
    
    ![Freenom TXT 記錄儲存的變更](../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。

    
2. 在 [**網域**] 頁面上，選取您要驗證的網域。 
    
    
  
3. 在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。
    
    
  
4. 在 [**驗證網域**] 頁面上，選取 [**驗證**]。
    
    
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365
<a name="bkmk_mx"> </a>

1. 若要開始，使用[此連結](https://my.freenom.com/)移至您在 Freenom 中的網域頁面。 You'll be prompted to log in.
    
    ![Freenom 登入](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 選取 [**服務**]，然後選取 [**我的網域**。
    
    ![Freenom 選取服務和我的網域](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 針對您想要編輯的網域，選取 [**管理網域**]。
    
    ![Freenom 選取 [管理網域](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 設定您的網域名稱做為預設 Freenom 名稱伺服器。 選取 [**管理工具**]，然後選取 [**名稱伺服器**。
    
    ![Freenom 名稱伺服器設定](../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. 請確定已選取 [**使用預設名稱伺服器**，，然後選取 [**變更名稱伺服器**。
    
    ![Freenom 變更名稱伺服器](../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. 選取 [**管理 Freenom DNS**]。
    
    ![Freenom 選取管理 Freenom DNS](../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. [**新增記錄**，在 [**類型**] 欄中， **MX**從功能表中選擇。 
    
    ![Freenom 新增記錄類型 MX](../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. 在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。 
    
    |**Name**|**Type**|**TTL**|**Target**|**優先順序**|
    |:-----|:-----|:-----|:-----|:-----|
    |(保留空白)  <br/> |MX (郵件交換程式)  <br/> |3600 （秒）  <br/> |\<網域金鑰\>。 mail.protection.outlook.com  <br/> **附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。   [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9) <br/> |
   
   ![Freenom MX 記錄](../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. 選取 [**儲存變更**。
    
    ![Freenom MX 記錄儲存的變更](../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. 如果有任何其他 MX 記錄，請將它們全數刪除。 每一筆記錄中，選取 [**刪除**]。 當郵件**您真的要移除此項目？** 出現，請選取 **[確定]**。
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>新增 Office 365 所需的 CNAME 記錄
<a name="bkmk_cname"> </a>

1. 若要開始，使用[此連結](https://my.freenom.com/)移至您在 Freenom 中的網域頁面。 You'll be prompted to log in.
    
    ![Freenom 登入](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 選取 [**服務**]，然後選取 [**我的網域**。
    
    ![Freenom 選取服務和我的網域](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 針對您想要編輯的網域，選取 [**管理網域**]。
    
    ![Freenom 選取 [管理網域](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 選取 [**管理 Freenom DNS**]。
    
    ![Freenom 選取管理 Freenom DNS](../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. [**新增記錄**，在 [**類型**] 欄中， **CNAME**從功能表中選擇。 
    
    ![Freenom 新增記錄類型 CNAME](../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. 建立第一筆 CNAME 記錄。 在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。 
    
    |**Name**|**記錄類型**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 （秒）  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 （秒）  <br/> |sipdir.online.lync.com>  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 （秒）  <br/> |webdir.online.lync.com>  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 （秒）  <br/> |enterpriseregistration.windows.net>  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 （秒）  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME 值](../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. 選取 [**儲存變更**。
    
    ![儲存變更的 Freenom CNAME](../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. 重複上述步驟建立其他五筆 CNAME 記錄。 
    
    每一筆記錄，輸入或複製並貼入該記錄的方塊中的表格中下一列中的值。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 

1. 若要開始，使用[此連結](https://my.freenom.com/)移至您在 Freenom 中的網域頁面。 You'll be prompted to log in.
    
    ![Freenom 登入](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 選取 [**服務**]，然後選取 [**我的網域**。
    
    ![Freenom 選取服務和我的網域](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 針對您想要編輯的網域，選取 [**管理網域**]。
    
    ![Freenom 選取 [管理網域](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 選取 [**管理 Freenom DNS**]。
    
    ![Freenom 選取管理 Freenom DNS](../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. [**新增記錄**，在 [**類型**] 欄中， **TXT**從功能表中選擇。 
    
    ![Freenom 新增記錄類型 TXT](../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. In the boxes for the new record, type or copy and paste the following values. 
    
    |**Name**|**記錄類型**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(保留空白)  <br/> |TXT  <br/> |3600 （秒）  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
   
    ![Spf Freenom TXT 值](../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. 選取 [**儲存變更**。
    
    ![Freenom TXT 記錄以 SPF 儲存變更](../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

