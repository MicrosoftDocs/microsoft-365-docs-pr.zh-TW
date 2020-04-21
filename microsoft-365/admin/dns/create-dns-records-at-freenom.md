---
title: 在 Freenom 建立 Microsoft 的 DNS 記錄
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Freenom。
ms.openlocfilehash: 828a1728606338017383857e4b59d6a62d087fc7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629560"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a>在 Freenom 建立 Microsoft 的 DNS 記錄

如果您找不到所需的專案，[請檢查網域常見問題](../setup/domains-faq.md)。 
  
> [!CAUTION]
> Freenom 網站不支援 SRV 記錄，這表示有幾部商務用 Skype Online 和 Outlook Web App 功能將無法運作。 不論使用哪一種 Microsoft 方案，都有重大的服務限制，您可能想要切換至不同的 DNS 主機服務提供者。 
  
不論服務限制，您可以選擇在 Freenom 管理您自己的 Microsoft DNS 記錄，請遵循本文中的步驟來驗證您的網域，並設定電子郵件和其他服務的 DNS 記錄。
  
若要深入瞭解 Microsoft 的網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。
  
> [!NOTE]
> DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="bkmk_txt"> </a>

在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。 您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。 You'll be prompted to log in.
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 選取 [**服務**]，然後選取 [**我的網域**]。
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 針對您要編輯的網域，選取 [**管理網域**]。
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 選取 [**管理 FREENOM DNS**]。
    
    ![Freenom 管理 Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. 在 [**新增記錄**] 底下的 [**類型**] 欄中，選擇功能表中的 [ **TXT** ]。 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. 在新記錄的方塊中，輸入或複製並貼上下表中的值。 
    
    |**名稱**|**Type**|**TTL**|**Target** (目標)|
    |:-----|:-----|:-----|:-----|
    |(保留空白)  <br/> |TXT  <br/> |3600（秒）  <br/> |MS=msXXXXXXXX  <br/> **附註：** 這是範例。 從表格中，使用您的特定**目的地或指向位址**值。           [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom 用於驗證的 TXT 值](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. 選取 [**儲存變更**]。
    
    ![Freenom TXT 記錄儲存變更](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求記錄。
  
當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。
  
1. 在 Microsoft 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。

    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
    
  
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
    
  
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
    
    
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft
<a name="bkmk_mx"> </a>

1. 若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。 You'll be prompted to log in.
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 選取 [**服務**]，然後選取 [**我的網域**]。
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 針對您要編輯的網域，選取 [**管理網域**]。
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 將您的網域的名稱設為預設的 Freenom 名稱伺服器。 選取 [**管理工具**]，然後選取 [**名稱伺服器**]。
    
    ![Freenom 名稱伺服器設定](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. 請確認已選取 [**使用預設名稱伺服器**]，然後選取 [**變更名稱伺服器**]。
    
    ![Freenom 變更名稱伺服器](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. 選取 [**管理 FREENOM DNS**]。
    
    ![Freenom select Manage Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. 在 [**新增記錄**] 底下的 [**類型**] 欄中，從功能表選擇 [ **MX** ]。 
    
    ![Freenom 新增記錄類型 MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. 在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。 
    
    |**名稱**|**Type**|**TTL**|**Target** (目標)|**優先順序**|
    |:-----|:-----|:-----|:-----|:-----|
    |(保留空白)  <br/> |MX (郵件交換程式)  <br/> |3600（秒）  <br/> |\<網域金鑰\>。 mail.protection.outlook.com  <br/> **附注：** 從您的 Microsoft 帳戶取得您* \<的網域金鑰\> * 。   [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9) <br/> |
   
   ![Freenom MX 記錄](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. 選取 [**儲存變更**]。
    
    ![Freenom MX 記錄儲存變更](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. 如果有任何其他 MX 記錄，請全部刪除。 針對每筆記錄，選取 [**刪除**]。 當郵件**確實要移除此專案時？** 隨即出現，請選取 **[確定]**。
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的 CNAME 記錄
<a name="bkmk_cname"> </a>

1. 若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。 You'll be prompted to log in.
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 選取 [**服務**]，然後選取 [**我的網域**]。
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 針對您要編輯的網域，選取 [**管理網域**]。
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 選取 [**管理 FREENOM DNS**]。
    
    ![Freenom select Manage Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. 在 [**新增記錄**] 底下的 [**類型**] 欄中，從功能表選擇 [ **CNAME** ]。 
    
    ![Freenom 新增記錄類型 CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. 建立第一筆 CNAME 記錄。 在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。 
    
    |**Name** (名稱)|**記錄類型**|**TTL**|**Target** (目標)|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600（秒）  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600（秒）  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600（秒）  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600（秒）  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600（秒）  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME 值](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. 選取 [**儲存變更**]。
    
    ![Freenom CNAME 儲存變更](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. 重複上述步驟，以建立其他五筆 CNAME 記錄。 
    
    針對每個記錄，輸入或複製並貼上表格中下一列的值，然後將其貼到該記錄的方塊中。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果您已有網域的 SPF 記錄，請不要為 Microsoft 建立新的記錄。 請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。 

1. 若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。 You'll be prompted to log in.
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. 選取 [**服務**]，然後選取 [**我的網域**]。
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 針對您要編輯的網域，選取 [**管理網域**]。
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. 選取 [**管理 FREENOM DNS**]。
    
    ![Freenom select Manage Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. 在 [**新增記錄**] 底下的 [**類型**] 欄中，選擇功能表中的 [ **TXT** ]。 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. In the boxes for the new record, type or copy and paste the following values. 
    
    |**Name** (名稱)|**記錄類型**|**TTL**|**Target** (目標)|
    |:-----|:-----|:-----|:-----|
    |(保留空白)  <br/> |TXT  <br/> |3600（秒）  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
   
    ![Freenom SPF 的 TXT 值](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. 選取 [**儲存變更**]。
    
    ![Freenom SPF 儲存變更的 TXT 記錄](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

