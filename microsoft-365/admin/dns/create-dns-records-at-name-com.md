---
title: 在 name.com 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft name.com。
ms.openlocfilehash: ce465e06b3bc18c824d741ee4cba4b9f4f410d90
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645884"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a>在 name.com 建立 Microsoft 的 DNS 記錄

 若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。 
  
如果 name.com 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。
  
在 name.com 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。

  
> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. 在 [ **我的網域**] 底下，選取您要修改的網功能變數名稱稱。
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. 在 [ **詳細資料** ] 欄中，選取 [ **DNS 記錄**]。 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. 在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。
    
    (從下拉式清單中選擇 [Type] (類型) 值。) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**類型** <br/> |**主機** <br/> |**答案** <br/> |**TTL** <br/> |
    |TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。           [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          |使用預設值 (300)。  <br/> |
   
    ![Name-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. 選取 [ **新增記錄**]。
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。
  
在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。
  
1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。
    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
    
  
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
    
  
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
    
    
  
> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft
<a name="BKMK_add_MX"> </a>

1. 首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. 在 [ **我的網域**] 底下，選取您要修改的網功能變數名稱稱。
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. 在 [ **詳細資料** ] 欄中，選取 [ **DNS 記錄**]。 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. 在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。
    
    (從下拉式清單中選擇 [Type] (類型) 值。) 
    
    |**類型**|**主機**|**答案**|**TTL**|**Prio (優先順序)**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(將此欄位保留空白。)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **附注：***\<domain-key\>* 從您的 Microsoft 帳戶取得。           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |使用預設值 (300)。  <br/> |0  <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |
   
   ![Name-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. 選取 [ **新增記錄**]。
    
    ![名稱-BP-設定-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. 如果有任何其他 MX 記錄，請透過下列雙步驟程序刪除每個記錄︰
    
    針對其他每個 MX 記錄，請選取 [**動作**] 欄中的 [**刪除**]。 
    
    ![名稱-BP-設定-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    若要確認每個刪除，請再次選取 [**動作**] 欄中的 [**刪除**]。 
    
    ![名稱-BP-設定-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    重複此進行雙步驟程序，直到您刪除其他 MX 記錄為止。
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

1. 首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. 在 [ **我的網域**] 底下，選取您要修改的網功能變數名稱稱。
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. 在 [ **詳細資料** ] 欄中，選取 [ **DNS 記錄**]。 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. 新增第一筆 CNAME 記錄。
    
    在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。
    
    (從下拉式清單中選擇 [Type] (類型) 值。) 
    
    |**類型**|**主機**|**答案**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |使用預設值 (300)。  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |使用預設值 (300)。  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |使用預設值 (300)。  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |使用預設值 (300)。  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |使用預設值 (300)。  <br/> |
   
   ![Name-BP-Configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. 選取 [ **Add record** ] （新增）以新增第一筆記錄。 
    
    ![名稱-BP-設定-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. 新增第二筆 CNAME 記錄。
    
    使用上表中第二列的值，然後選取 [ **新增記錄** ] 以新增第二筆記錄。 
    
    以此類推，使用表格中第三、四、五、六列的值新增其他記錄。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。 請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。 
  
1. 首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. 在 [ **我的網域**] 底下，選取您要修改的網功能變數名稱稱。

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. 在 [ **詳細資料** ] 欄中，選取 [ **DNS 記錄**]。 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. 在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。
    
    (從下拉式清單中選擇 [Type] (類型) 值。) 
    
    |**類型**|**主機**|**答案**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |Use the default value (300).  <br/> |
   
   ![Name-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. 選取 [ **新增記錄**]。
    
    ![名稱-BP-設定-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>新增兩筆 Microsoft 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

1. 首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. 在 [ **我的網域**] 底下，選取您要修改的網功能變數名稱稱。
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. 在 [ **詳細資料** ] 欄中，選取 [ **DNS 記錄 +**]。 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. 新增第一筆 SRV 記錄：
    
    在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。
    
    (從下拉式清單中選擇 [Type] (類型) 值。) 
    
    |**Type**|**服務**|**Weight**|**TTL**|**Prio (優先順序)**|**Protocol** (通訊協定)|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|sip|1 |使用預設值 (300)。|100|tls|443|sipdir.online.lync.com <br> **注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
    |SRV|sipfederationtls|1 |使用預設值 (300)。|100|tcp|5061|sipfed.online.lync.com <br>**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
   
   ![Name-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. 選取 [ **新增記錄**]。

    ![名稱-BP-設定-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. 新增第二筆 SRV 記錄：

使用上表中的下一列的值，然後選取 [ **新增記錄** ] 以新增第二筆記錄。

>[!NOTE]
>DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。
