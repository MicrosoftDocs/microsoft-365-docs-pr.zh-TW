---
title: 在 Microsoft 的 DNSMadeEasy 建立 DNS 記錄
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
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
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以供 Microsoft DNSMadeEasy。
ms.openlocfilehash: dde060b6e03eebb89029b742402558e95031b1d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629680"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a>在 Microsoft 的 DNSMadeEasy 建立 DNS 記錄

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果 DNSMadeEasy 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。
  
在 DNSMadeEasy 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。
  
若要深入瞭解 Microsoft 的網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。 如果您在新增 DNS 記錄後遇到郵件流程或其他問題的問題，請參閱[尋找並修正新增您的網域或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。 您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
> [!IMPORTANT]
> For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar. DNSMadeEasy does not offer domain registration services. Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership. 
  
1. 首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。 系統會提示您先登入。
    
2. 在 [**管理主控台**] 頁面上的 [**最近更新的網域**] 區域中，選取您要更新的網域。 
    
3. 在 [**受管理的 DNS** ] 頁面上的 [ **TXT 記錄**] 區域**+** 中，選取 [（新增）] 控制項（**新增**）。
    
    (You may have to scroll down.)
    
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    ||||
    |:-----|:-----|:-----|
    |**Name** <br/> |**值** <br/> |**TTL** <br/> |
    |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 從表格中，使用您的特定**目的地或指向位址**值。 [如何找到這項資訊？](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. 選取 [**提交**]。
    
6. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求記錄。
  
當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。
  
1. 在 Microsoft 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。

    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
4. 在 [驗證網域]**** 頁面上，選取 [驗證]****。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。 如果您在新增 DNS 記錄後遇到郵件流程或其他問題的問題，請參閱[尋找並修正新增您的網域或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft
<a name="BKMK_add_MX"> </a>

1. 首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。系統會提示您先登入。
    
2. 在 [**管理主控台**] 頁面上的 [**最近更新的網域**] 區域中，選取您要更新的網域。 
    
    在 [**管理主控台**] 頁面上的 [**最近更新的網域**] 區域中，選取您要更新的網域。 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. 在 [**受管理的 DNS** ] 頁面的 [ **MX 記錄**] 區域中，選取 [（**新增**）] **（+）** 控制項（新增）。
    
    (You may have to scroll down.)
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. 在 [新增**MX 記錄**] 區域的新記錄方塊中，輸入或複製並貼上下表中的值。 
    
    (You may have to scroll down.)
    
    |**名稱**|**伺服器**|**MX Level (MX 等級)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |(將此欄位保留空白。)  <br/> | *\<網域金鑰\>*  .mail.protection.outlook.com  <br/> **This value MUST end with a period (.)** <br/> **附注：** 從您\<的 Microsoft 帳戶取得您的*網域金鑰*\> 。 [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. 選取 [**提交**]。
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. 如果 [ **Mx 記錄**] 區段中列出任何其他 MX 記錄，請逐一選取所有的 mx 記錄加以刪除。 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. 選取所有記錄後，請選取 [**刪除選取**的]。
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. 在 [**刪除 MX 記錄**] 對話方塊中，選取 [**刪除**] 以確認您的變更。 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的五個 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

1. 首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。系統會提示您先登入。
    
2. 在 [**管理主控台**] 頁面上的 [**最近更新的網域**] 區域中，選取您要更新的網域。 
    
3. 在 [**受管理的 DNS** ] 頁面上的 [ **CNAME 記錄**] 區域中，選取 [（新增）] **（+）** 控制項（**新增**）。
    
    (您可能需要向下捲動。)
    
    ![DNSMadeEasy-BP-Configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. 新增五筆 CNAME 記錄中的第一筆。
    
    在 [新增**CNAME 記錄**] 區域的新記錄方塊中，輸入或複製並貼上下表中第一列的值。 
    
    |**Name** (名稱)|**Alias to (別名)**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. 選取 [**提交**]。
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. 新增其他四筆 CNAME 記錄。
    
    在 [CNAME record] （ **CNAME 記錄**）區段中，選取 **（+）** 控制項（**新增**），使用表格中下一列的值來建立記錄，然後再選取 [**提交**] 以完成記錄。 
    
    重複此程式，直到您已建立全部五筆 CNAME 記錄為止。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果您已有網域的 SPF 記錄，請不要為 Microsoft 建立新的記錄。 請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。 需要範例？ 請參閱[Microsoft 的這些外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)。 若要驗證您的 SPF 記錄，您可以使用其中一種[spf 驗證工具](../setup/domains-faq.md)。 
  
1. 首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。 系統會提示您先登入。
    
2. 在 [**管理主控台**] 頁面上的 [**最近更新的網域**] 區域中，選取您要更新的網域。 
    
3. 在 [**受管理的 DNS** ] 頁面的 [ **TXT 記錄**] 區域中，選取 [（**新增**）] **（+）** 控制項（新增）。
    
    (您可能需要向下捲動。)
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**名稱**|**值**|**TTL**|
    |:-----|:-----|:-----|
    |(將此欄位保留空白。)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. 選取 [**提交**]。
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的兩筆 SRV 記錄
<a name="BKMK_add_SRV"> </a>

1. 首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。系統會提示您先登入。
    
2. 在 [**管理主控台**] 頁面上的 [**最近更新的網域**] 區域中，選取您要更新的網域。 
    
3. 在 [**受管理的 DNS** ] 頁面的 [ **SRV 記錄**] 區域中，選取 [（**新增**）] **（+）** 控制項（新增）。
    
    (您可能需要向下捲動)
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. 新增兩筆 SRV 記錄中的第一筆。
    
    在 [ **ADD SRV** record] （新增 SRV 記錄）區域的新記錄方塊中，輸入或複製並貼上下表中第一列的值。 
    
    |**Name** (名稱)|**Priority** (優先順序)|**Weight** (權數)|**Port** (連接埠)|**Host**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip。 _tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |_sipfederationtls。 _tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. 選取 [**提交**]。
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. 新增另一筆 SRV 記錄。
    
    在 [ **SRV 記錄**] 區段中，選取 **（+）** 控制項（**新增），** 並使用表格中下一列的值來建立記錄，然後再選取 [**提交**] 以完成記錄。 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。 如果您在新增 DNS 記錄後遇到郵件流程或其他問題的問題，請參閱[尋找並修正新增您的網域或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  

