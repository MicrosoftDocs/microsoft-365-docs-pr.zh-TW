---
title: 在 Namecheap 建立 Office 365 的 DNS 記錄
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 Skype for Business Online，並在 Namecheap 其他服務的 DNS 記錄。
ms.openlocfilehash: a913aa5f2d88be5bed246e813bebd590f401c07f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239800"
---
# <a name="create-dns-records-at-namecheap-for-office-365"></a>在 Namecheap 建立 Office 365 的 DNS 記錄

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果 Namecheap 是您 DNS 主機服務提供者，請遵循本篇文章以驗證您的網域和設定 DNS 記錄的電子郵件、 Skype for Business Online 等等中的步驟。
  
在 Namecheap 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務。
  
> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
請依照下列步驟操作。
  
1. 若要開始，使用[這個連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)移至您在 Namecheap 的網域頁面。 系統會提示您登入，並繼續。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. 在**登陸**頁面上，在 [**帳戶**] 下，從下拉式清單中選擇**網域清單**。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. 在 [**網域清單**] 頁面上，尋找您想要編輯的網域名稱，然後選取**管理**。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. 選取 [**進階 DNS**]。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. 在 [**主機記錄**] 區段中，選取 [**新增新的記錄**。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. 在 [**類型**下拉式清單，選取 [ **TXT 記錄**]。
    
    > [!NOTE]
    > 當您選取 [**新增新的記錄**會自動出現**類型**下拉式清單。 
  
    ![Namecheap-DYN-BP-CONFIGURE-1-確認-1-1](../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
    （從下拉式清單選擇 [ **TTL** ] 值）。 
    
    |**類型**|**主機**|**值**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/>**附註：** 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365.  [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |30 分鐘  <br/> |
       
    ![Namecheap-DYN-BP-CONFIGURE-1-確認-1-2](../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. 選取**儲存的變更**（核取記號） 的控制項。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-確認-1-3](../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。
    
2. 在 [**網域**] 頁面上，選取您要驗證的網域。 
    
    
  
3. 在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。
    
    
  
4. 在 [**驗證網域**] 頁面上，選取 [**驗證**]。
    
    
  
> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365
<a name="BKMK_add_MX"> </a>

請依照下列步驟進行。
  
1. 若要開始，使用[這個連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)移至您在 Namecheap 的網域頁面。 系統會提示您登入，並繼續。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. 在**登陸**頁面上，在 [**帳戶**] 下，從下拉式清單中選擇**網域清單**。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. 在 [**網域清單**] 頁面上，尋找您想要編輯的網域名稱，然後選取**管理**。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. 選取 [**進階 DNS**]。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. 在 [**郵件設定**] 區段中，從**電子郵件轉寄**] 下拉式清單中選取**自訂 MX** 。 
    
    (You may have to scroll down.)
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-2-1](../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. 選取 [**加入新的記錄**。
    
    ![Namecheap-BP-Configure-2-2-1](../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. 在新記錄方塊中，輸入或複製並貼上下表的值。
    
    （[**優先順序**] 方塊是未命名的方塊右邊的 [**值**] 方塊。 選擇 [ **TTL** ] 值從下拉式清單中。） 
    
    |**類型**|**主機**|**Value** (值)|**Priority** (優先順序)|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX 記錄  <br/> |@  <br/> |\<*網域金鑰*\>。 mail.protection.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> **附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。  [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |30 分鐘  <br/> |
       
    ![Namecheap-BP-Configure-2-2-2](../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. 選取**儲存的變更**（核取記號） 的控制項。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-2-3](../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. 如果有任何其他 MX 記錄，請使用下列兩個步驟的處理程序來逐一移除：
    
    首先，請選取 **[刪除] 圖示**（垃圾桶） 您想要移除的記錄。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-2-4](../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    其次，選取 **[是]** 確認刪除。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-2-5](../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    移除所有的 MX 記錄，除了您稍早在此程序中新增一個。

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>新增 Office 365 所需的六筆 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

請依照下列步驟進行。
  
1. 若要開始，使用[這個連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)移至您在 Namecheap 的網域頁面。 系統會提示您登入，並繼續。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. 在**登陸**頁面上，在 [**帳戶**] 下，從下拉式清單中選擇**網域清單**。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. 在 [**網域清單**] 頁面上，尋找您想要編輯的網域名稱，然後選取**管理**。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. 選取 [**進階 DNS**]。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. 在 [**主機記錄**] 區段中，選取 [**新增新的記錄**。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. 在 [**類型**下拉式清單，選取 [ **CNAME 記錄**。
    
    > [!NOTE]
    > 當您選取 [**新增新的記錄**會自動出現**類型**下拉式清單。 
  
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-3-1](../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. 在空白的新記錄方塊中，**記錄類型**，請選取 [ **CNAME** ，然後輸入或複製並貼下表中第一列的值。
    
    |**類型**|**主機**|**Value** (值)|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net>。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |
       
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-3-2](../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. 選取**儲存的變更**（核取記號） 的控制項。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-3-3](../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. 使用表格中的前四個步驟和其他五列的值，新增每個其他五筆 CNAME 記錄。

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 

請依照下列步驟操作。
  
1. 若要開始，使用[這個連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)移至您在 Namecheap 的網域頁面。 系統會提示您登入，並繼續。
    
2. 在**登陸**頁面上，在 [**帳戶**] 下，從下拉式清單中選擇**網域清單**。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. 在 [**網域清單**] 頁面上，尋找您想要編輯，然後選取 [**管理**網域的名稱。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. 選取 [**進階 DNS**]。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. 在 [**主機記錄**] 區段中，選取 [**新增新的記錄**。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. 在 [**類型**下拉式清單，選取 [ **TXT 記錄**]。
    
    > [!NOTE]
    > 當您選取 [**新增新的記錄**會自動出現**類型**下拉式清單。 
  
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-4-1](../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. 在新記錄方塊中，輸入或複製並貼上下表中的下列值。
    
    （從下拉式清單選擇 [ **TTL** ] 值）。 
    
    |**類型**|**主機**|**Value** (值)|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |30 分鐘  <br/> |
       
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-4-2](../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. 選取**儲存的變更**（核取記號） 的控制項。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-4-3](../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>新增兩筆 Office 365 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

1. 若要開始，使用[這個連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)移至您在 Namecheap 的網域頁面。 You'll be prompted to sign in.
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. 在**登陸**頁面上，在 [**帳戶**] 下，從下拉式清單中選擇**網域清單**。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. 在 [**網域清單**] 頁面上，尋找您想要編輯，然後選取 [**管理**網域的名稱。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. 選取 [**進階 DNS**]。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. 在 [**主機記錄**] 區段中，選取 [**新增新的記錄**。
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. 在 [**類型**下拉式清單，選取**一筆 SRV 記錄**。
    
    > [!NOTE]
    > 當您選取 [**新增新的記錄**會自動出現**類型**下拉式清單。 
  
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-5-1](../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. 在空白的新記錄方塊中，輸入或複製並貼下表中第一列的值。
    
    |**服務**|**通訊協定**|**優先順序**|**Weight**|**Port**|**Target**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com>。  <br/> **This value MUST end with a period (.)** <br/> |30 分鐘  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |30 分鐘  <br/> |
       
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-5-2](../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. 選取**儲存的變更**（核取記號） 的控制項。 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-5-3](../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. 使用表格中的前四個步驟和第二列中的值，新增其他 SRV 記錄。
    
> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  

  
