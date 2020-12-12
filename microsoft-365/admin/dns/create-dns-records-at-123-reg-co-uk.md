---
title: 在123-reg.co.uk 建立 Microsoft 的 DNS 記錄
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft 123-reg.co.uk。
ms.openlocfilehash: bde8003ad343680e8f499dd8ec1fb638f15080b1
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658312"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a>在123-reg.co.uk 建立 Microsoft 的 DNS 記錄

 若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。 
  
如果 123-reg.co.uk 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。
  
在123-reg.co.uk 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。
  
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。系統會提示您先登入。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 [ **管理您的 DNS** ] 頁面上，選取 [ **高級 DNS** ] 索引標籤。 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**主機 名** <br/> |**Type** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。 [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          |
   
6. 選取 **[新增]**。
    
7. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。
  
在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。
  
1. 在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft
<a name="BKMK_add_MX"> </a>

1. 首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。系統會提示您先登入。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 [ **管理您的 DNS** ] 頁面上，選取 [ **高級 DNS** ] 索引標籤。 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**主機 名**|**Type**|**優先順序**|**Destination MX (目的地 MX)**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1   <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*  mail.protection.outlook.com。  <br/> **此值必須以英文句點 (.) 結尾。** <br/> **注意：** 從您的 Microsoft 帳戶取得您的 \<domain-key\>。 [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![複製並貼上表格中的值](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. 選取 **[新增]**。
    
    ![選取 [新增]](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. 如果有任何其他 MX 記錄，請選擇 [ **刪除 (垃圾桶)** 該記錄的圖示來移除每個記錄。 
    
    ![選取 [刪除] (垃圾桶圖示) ](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的六筆 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

1. 首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。系統會提示您先登入。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 [ **管理您的 DNS** ] 頁面上，選取 [ **高級 DNS** ] 索引標籤。 
    
5. 新增六筆 CNAME 記錄的第一筆。
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**主機 名**|**Type**|**Destination CNAME (目的地 CNAME)**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **此值必須以英文句點 (.) 結尾。** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **此值必須以英文句點 (.) 結尾。** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **此值必須以英文句點 (.) 結尾。** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **此值必須以英文句點 (.) 結尾。** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **此值必須以英文句點 (.) 結尾。** <br/> |
   
    ![複製並貼上表格中的值](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. 選取 **[新增]**。
    
    ![選取 [新增]](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. 新增其他五筆 CNAME 記錄。
    
    在 [ **ADVANCED DNS** ] 區段中，使用表格中下一列的值建立記錄，然後再選取 [ **新增** ] 以完成記錄。 
    
    重複這個程序，直到六筆 CNAME 記錄全部建立完畢。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果您已有網域的 SPF 記錄，請勿為 Microsfot 建立新的記錄。 請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。 需要範例？ 請參閱這些 [Microsoft 的外部網域名稱系統記錄](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf)。 若要驗證您的 SPF 記錄，您可以使用其中一種 [SPF 驗證工具](../setup/domains-faq.yml)。 
  
1. 首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。 系統會提示您先登入。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 [ **管理您的 DNS** ] 頁面上，選取 [ **高級 DNS** ] 索引標籤。 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**主機 名**|**Type**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. 選取 **[新增]**。
    
    ![選取 [新增]](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>新增兩筆 Microsoft 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

1. 首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。系統會提示您先登入。
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. 在 [ **管理您的 DNS** ] 頁面上，選取 [ **高級 DNS** ] 索引標籤。 
    
5. 新增兩筆 SRV 記錄的第一筆：
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |主機名稱|Type (類型)|Priority (優先順序)|TTL|Destination SRV (目的 SRV)|
    |_sip._tls|SRV|100|3600|1 443 sipdir.online.lync.com。 **此值必須以英文句點 (.) 結尾。**<br> **注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
    |_sipfederationtls._tcp|SRV|100|3600|1 5061 sipfed.online.lync.com。 **此值必須以英文句點 (.) 結尾。** <br> **注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
   
    ![複製並貼上表格中的值](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. 選取 **[新增]**。
    
    ![選取 [新增]](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. 新增另一筆 SRV 記錄：
    
    在 [ **ADVANCED DNS** ] 區段中，使用表格中第二列的值來建立記錄，然後再選取 [ **新增** ] 以完成記錄。 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
