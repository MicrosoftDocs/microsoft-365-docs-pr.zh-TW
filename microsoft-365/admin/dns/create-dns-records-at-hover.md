---
title: 在 Hover 建立 Office 365 的 DNS 記錄
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: 了解如何驗證您的網域及設定電子郵件、 商務用 Skype 線上商務和其他服務 hover 運作的 Office 365 的 DNS 記錄。
ms.openlocfilehash: 54ff58963dcd66f692507f1d778fb9a8d24f82fa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240946"
---
# <a name="create-dns-records-at-hover-for-office-365"></a>在 Hover 建立 Office 365 的 DNS 記錄

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果 Hover 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。
     
在 Hover 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。
  
若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。
    
    ![登入](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. 在**管理您的網域**] 中，選取您想要編輯的網域名稱。
    
    ![選取網域](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. 選取 [ **DNS** ] 索引標籤。 
    
    ![選取 [DNS] 索引標籤](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. 選取 [**新增**]。
    
    ![選取 [新增](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
    ||||
    |:-----|:-----|:-----|
    |主機名稱  <br/> |記錄類型  <br/> |值  <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![輸入或複製並貼入 DNS 值](../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. 選取 **[儲存]**。
    
    ![選取 [儲存]](../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
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

請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。
    
    ![登入](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. 在**管理您的網域**] 中，選取您想要編輯的網域名稱。
    
    ![選取網域](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. 選取 [ **DNS** ] 索引標籤。 
    
    ![選取 [DNS] 索引標籤](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. 選取 [**新增**]。
    
    ![選取 [新增](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. 在新記錄方塊中，針對**記錄類型**]，選取 [ **MX** ，然後輸入或複製並貼上下表中的值。
    
    |**主機名稱**|**Record Type**|**優先順序**|**主機名稱**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |0  <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<網域金鑰\>*  .mail.protection.outlook.com  <br/> **附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![輸入或複製並貼入 DNS 值](../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. 選取 **[儲存]**。
    
    ![選取 [儲存]](../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. 如果有任何其他 MX 記錄，請使用下列兩個步驟的處理程序來逐一移除：
    
    首先，選取 [**刪除**] 將滑鼠移至您要移除的記錄。
    
    ![滑鼠移過，並選取 [刪除]](../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    其次，選取 **[是]** 以確認每個刪除。 
    
    ![選取 [是] 確認刪除](../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    重複本處理程序，直到您已刪除所有 MX 記錄為止 (除了您稍早在本程序中新增的那一筆記錄以外)。
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>新增 Office 365 所需的 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。
    
    ![登入](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. 在**管理您的網域**] 中，選取您想要編輯的網域名稱。
    
    ![選取網域](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. 選取 [ **DNS** ] 索引標籤。 
    
    ![選取 [DNS] 索引標籤](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. 新增六筆 CNAME 記錄的第一筆。
    
    選取 [**新增**]。
    
    ![選取 [新增](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. 在空白的新記錄方塊中，**記錄類型**，請選取 [ **CNAME** ，然後輸入或複製並貼下表中第一列的值。
    
    |**主機名稱**|**Record Type**|**Target Host (目標主機)**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com>  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com>  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net>  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![輸入或複製並貼入 DNS 值](../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. 選取 **[儲存]**。
    
    ![選取 [儲存]](../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. 按照前三個步驟分別將表格中其他五列的值新增至其他五筆 CNAME 記錄。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。
    
    ![登入](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. 在**管理您的網域**] 中，選取您想要編輯的網域名稱。
    
    ![選取網域](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. 選取 [ **DNS** ] 索引標籤。 
    
    ![選取 [DNS] 索引標籤](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. 選取 [**新增**]。
    
    ![選取 [新增](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
    |**主機名稱**|**Record Type**|**值**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
   
    ![輸入或複製並貼入 DNS 值](../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. 選取 **[儲存]**。
    
    ![選取 [儲存]](../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>新增兩筆 Office 365 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。
    
    ![登入](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. 在**管理您的網域**] 中，選取您想要編輯的網域名稱。
    
    ![選取網域](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. 選取 [ **DNS** ] 索引標籤。 
    
    ![選取 [DNS] 索引標籤](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. 新增兩筆 SRV 記錄中的第一筆。
    
    選取 [**新增**]。
    
    ![選取 [新增](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. 在空白的新記錄方塊中，針對**記錄類型**]，選取 [ **SRV** ，然後輸入或複製並貼下表中第一列的值。
    
    |**主機名稱**|**Record Type**|**優先順序**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com>  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com>  <br/> |
   
    ![輸入或複製並貼入 DNS 值](../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. 選取 **[儲存]**。
    
    ![選取 [儲存]](../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. 使用前三個步驟和表格中第二列的值，新增其他 SRV 記錄。
    
> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
