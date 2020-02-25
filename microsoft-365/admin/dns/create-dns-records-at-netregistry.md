---
title: 在 Netregistry 建立 Office 365 的 DNS 記錄
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 Skype for Business Online，並在 Netregistry 其他服務的 DNS 記錄。
ms.openlocfilehash: de4e16fa20f950edef8d30b4c6d02214e3753b9c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251550"
---
# <a name="create-dns-records-at-netregistry-for-office-365"></a>在 Netregistry 建立 Office 365 的 DNS 記錄

[檢查網域的常見問題集](../setup/domains-faq.md) ：供您在找不到所需功能時參考。 
  
如果 Netregistry 是您 DNS 主機服務提供者，請遵循本篇文章以驗證您的網域和設定 DNS 記錄的電子郵件、 Skype for Business Online 等等中的步驟。
  
以下是要新增的主要記錄。
  
- [新增 TXT 記錄以供驗證](#add-a-txt-record-for-verification)
    
- [新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [新增 Office 365 所需的 CNAME 記錄](#add-the-cname-records-that-are-required-for-office-365)
    
- [新增 SPF 的 TXT 記錄以協助防範垃圾郵件](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [新增兩筆 Office 365 所需的 SRV 記錄](#add-the-two-srv-records-that-are-required-for-office-365)
    
在 Netregistry 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務。
  
若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。
  
> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="bkmk_txt"> </a>

在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 若要開始，使用[此連結](https://theconsole.netregistry.com.au/)移至您在 Netregistry 中的網域頁面。 You'll be prompted to log in.
    
    ![Netregistry_login](../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. 您想要管理的網域旁, 選取 [**管理**]。
    
    ![Netregistry_Manage](../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. 選取**區域管理員**]。
    
    ![Netregistry_selectZoneManager](../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. 在 [**新增區域記錄**] 從清單中，選擇 [ **TXT 記錄**，然後選取 [**建立新的記錄**。
    
    ![Netregistry_TXT_select](../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > 您必須使用引號之前和之後 [TXT] 方塊中的項目。 
  
    在**新的 TXT 記錄**表單中，輸入或複製並貼上下表中的值。 
    
    |**Name**|**TTL （秒）**|**TXT （指向位址] 或 [值）**|
    |:-----|:-----|:-----|
    |(保留空白)  <br/> |3600 （秒）  <br/> |"MS = msXXXXXXXX 」  <br/> **附註：** 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. 選取 [**新增記錄**]。
    
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

1. 若要開始，使用[此連結](https://theconsole.netregistry.com.au/)移至您在 Netregistry 中的網域頁面。 You'll be prompted to log in.
    
    ![Netregistry_login](../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. 您想要管理的網域旁, 選取 [**管理**]。
    
    ![Netregistry_Manage](../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. 選取**區域管理員**]。
    
    ![Netregistry_selectZoneManager](../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. 在**目前區域記錄**，移除預設的 MX 記錄所選取清單中每一個 MX 記錄旁的 [**移除**。 
    
    ![Netregistry_MX_remove](../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. 在 [**新增區域記錄**] 從清單中，選擇 [ **MX 記錄**，然後選取 [**建立新的記錄**。
    
    ![Netregistry_MX_select](../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. 在**新的 MX 記錄**表單中，輸入或複製並貼上下表中的值。 
    
    |**Name**|**TTL （秒）**|**Exchange （指向位址] 或 [值）**|**為主機的完整？**|**喜好設定 （優先順序）**|
    |:-----|:-----|:-----|:-----|:-----|
    |(保留空白)  <br/> |3600 （秒）  <br/> | *\<網域金鑰\>*  .mail.protection.outlook.com  <br/> **附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。  [How do I find this?](../get-help-with-domains/information-for-dns-records.md)      |（選取這個核取方塊）  <br/> |10   <br/> For more information about priority, see What is MX priority?  <br/> |
       
    ![Netregistry_MX_values](../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. 選取 [**新增記錄**]。
    
    ![Netregistry_MX_values_AddRecord](../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>新增 Office 365 所需的 CNAME 記錄
<a name="bkmk_cname"> </a>

1. 若要開始，使用[此連結](https://theconsole.netregistry.com.au/)移至您在 Netregistry 中的網域頁面。 You'll be prompted to log in.
    
    ![Netregistry_login](../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. 您想要管理的網域旁, 選取 [**管理**]。
    
    ![Netregistry_Manage](../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. 選取**區域管理員**]。
    
    ![Netregistry_selectZoneManager](../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. 在 [**新增區域記錄**] 從清單中，選擇 [ **CNAME 記錄**，然後選取 [**建立新的記錄**。
    
    ![Netregistry_CNAME_CreateNewRecord](../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |**Name**|**Type**|**TTL**|**主機 （以點為單位或位址] 值）**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 （秒）  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 （秒）  <br/> |sipdir.online.lync.com>  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 （秒）  <br/> |webdir.online.lync.com>  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 （秒）  <br/> |enterpriseregistration.windows.net>  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 （秒）  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![Netregistry_CNAME_values](../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. 選取 [**新增記錄**]。
    
    ![Netregistry_CNAME_values_AddRecord](../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. 重複上述步驟建立其他五筆 CNAME 記錄。
    
    每一筆記錄，輸入或複製並貼入該記錄的方塊中的表格中下一列中的值。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.
  
1. 若要開始，使用[此連結](https://theconsole.netregistry.com.au/)移至您在 Netregistry 中的網域頁面。 You'll be prompted to log in.
    
    ![Netregistry_login](../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. 您想要管理的網域旁, 選取 [**管理**]。
    
    ![Netregistry_Manage](../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. 選取**區域管理員**]。
    
    ![Netregistry_selectZoneManager](../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. 在 [**新增區域記錄**] 從清單中，選擇 [ **TXT 記錄**，然後選取 [**建立新的記錄**。
    
    ![Netregistry_TXT_select](../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table. 
    
    > [!NOTE]
    > 您必須使用引號之前和之後 [TXT] 方塊中的項目。 
  
    |**Name**|**Type**|**TTL**|**TXT Data （目標）**|
    |:-----|:-----|:-----|:-----|
    |(保留空白)  <br/> |TXT  <br/> |3600 （秒）  <br/> |「 v = spf1 include: spf.protection.outlook.com-所有 」  <br/> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
   
    ![Netregistry_SPF TXTvalues](../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. 選取 [**新增記錄**]。
    
    ![Netregistry_SPF TXTvalues_AddRecord](../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>新增兩筆 Office 365 所需的 SRV 記錄
<a name="bkmk_srv"> </a>

1. 若要開始，使用[此連結](https://theconsole.netregistry.com.au/)移至您在 Netregistry 中的網域頁面。 You'll be prompted to log in.
    
    ![Netregistry_login](../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. 您想要管理的網域旁, 選取 [**管理**]。
    
    ![Netregistry_Manage](../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. 選取**區域管理員**]。
    
    ![Netregistry_selectZoneManager](../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. 在 [**新增區域記錄**] 從清單中，選擇 [ **SRV 記錄**，然後選取 [**建立新的記錄**。
    
    ![Netregistry_SRV_select](../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
    > [!NOTE]
    > [名稱] 欄位是服務 (例如，_sip) 和通訊協定 (例如，_tls) 的組合。 
  
    |**類型**|**名稱**|**TTL （秒）**|**優先順序**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV （服務）  <br/> |_sip._tls  <br/> |3600 （秒）  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com>  <br/> |
    |SRV （服務）  <br/> |_sipfederationtls._tcp  <br/> |3600 （秒）  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com>  <br/> |
       
    ![Netregistry_SRV_values](../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. 選取 [**新增記錄**]。
    
    ![Netregistry_SRV_values_AddRecord](../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. 重複上述步驟建立其他 SRV 記錄。
    
    在第二筆記錄的方塊中，輸入或複製並貼上表格中第二列的值。
    
> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  

