---
title: 在 Register365 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Register365。
ms.openlocfilehash: 08db53df7510de76c6c5c33d2047cba4203324d8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629260"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a>在 Register365 建立 Microsoft 的 DNS 記錄

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果 Register365 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。 
  
以下是要新增的主要記錄。  
  
- [新增 TXT 記錄以供驗證](#add-a-txt-record-for-verification)
    
- [新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [新增 Microsoft 所需的六筆 CNAME 記錄](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [新增 SPF 的 TXT 記錄以協助防範垃圾郵件](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [新增 Microsoft 所需的兩筆 SRV 記錄](#add-the-two-srv-records-that-are-required-for-microsoft)
    
在 Microsoft 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。
  
若要深入瞭解 Microsoft 的網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。 您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. 在 [**儀表板**] 頁面上，找到您要更新的功能變數名稱，然後從下拉式清單中選擇 [ **DNS 設定**]。 
    
    (You may have to scroll down.)
    
    ![選取清單中的 DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    （如果您需要新增一列，請選取 **[新增 A/CNAME 記錄] （+）**。）
    
    (You may have to scroll down.)
    
    |**主機名稱**|**類型**|**結果**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 從表格中，使用您的特定**目的地或指向位址**值。           [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![在 [Add/Modify DNS 區域] 頁面上輸入值](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. 選取 **[儲存]**。
    
    (You may have to scroll down.)
    
    ![選取 [儲存]](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求記錄。
  
當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。
  
1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。
    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
    
  
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
    
  
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
    
    
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft
<a name="BKMK_add_MX"> </a>

1. 首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. 在 [**儀表板**] 頁面上，找到您要更新的功能變數名稱，然後從下拉式清單中選擇 [ **DNS 設定**]。 
    
    (You may have to scroll down.)
    
    ![選取清單中的 DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. 在 [ **ADD/MODIFY DNS 區域**] 頁面的 [**郵件交換記錄**] 區段中，于新記錄的方塊中，輸入或複製並貼上下表中的值。 
    
    (You may have to scroll down.)
    
    |**主機名稱**|**優先順序**|**結果**|
    |:-----|:-----|:-----|
    |(將此欄位保留空白。)  <br/> |1   <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<網域金鑰\>*  .mail.protection.outlook.com  <br/> **附注：** 從您的 Microsoft 帳戶取得您* \<的網域金鑰\> * 。  [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![在 [Add/Modify DNS 區域] 頁面上輸入值](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. 選取 **[儲存]**。
    
    (You may have to scroll down.)
    
    ![選取 [儲存]](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. 如果 [**郵件交換記錄**] 區段中有任何其他 MX 記錄，請選取它，然後按鍵盤上的**delete**鍵，逐一刪除。 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. 選取 **[儲存]**。
    
    (You may have to scroll down.)
    
    ![選取 [儲存]](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的六筆 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

1. 首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. 在 [**儀表板**] 頁面上，找到您要更新的功能變數名稱，然後從下拉式清單中選擇 [ **DNS 設定**]。 
    
    (You may have to scroll down.)
    
    ![選取清單中的 DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. 在 [ **ADD/MODIFY DNS 區域**] 頁面的 [ **A，CNAME，AAAA，TXT 和 NS 記錄**] 區段中，于新記錄的方塊中，輸入或複製並貼上下表中的值。 
    
    (Choose the **Type** value from the drop-down list.) 
    
    （如果您需要新增一列，請選取 **[新增 A/CNAME 記錄] （+）**。）
    
    (You may have to scroll down.)
    
    |主機名稱 * * * *|類型 * * * *|Result * * * *|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![在 [Add/Modify DNS 區域] 頁面上輸入值](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. 選取 **[儲存]**。
    
    ![選取 [儲存]](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果您已有網域的 SPF 記錄，請不要為 Microsoft 建立新的記錄。 請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。 
  
1. 首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. 在 [**儀表板**] 頁面上，找到您要更新的功能變數名稱，然後從下拉式清單中選擇 [ **DNS 設定**]。 
    
    (You may have to scroll down.)
    
    ![選取清單中的 DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    （如果您需要新增一列，請選取 **[新增 A/CNAME 記錄] （+）**。）
    
    (You may have to scroll down.)
    
    |**主機名稱**|**類型**|**結果**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
   
    ![在 [Add/Modify DNS 區域] 頁面上輸入值](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. 選取 **[儲存]**。
    
    (You may have to scroll down.)
    
    ![選取 [儲存]](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的兩筆 SRV 記錄
<a name="BKMK_add_SRV"> </a>

1. 首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. 在 [**儀表板**] 頁面上，找到您要更新的功能變數名稱，然後從下拉式清單中選擇 [ **DNS 設定**]。 
    
    (You may have to scroll down.)
    
    ![選取清單中的 DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. 在 [ **ADD/MODIFY DNS 區域**] 頁面上的 [**服務記錄**] 區段中，于新記錄的方塊中，輸入或複製並貼上下表中的值。 
    
    (You may have to scroll down.)
    
    |**Name** (名稱)|**Priority** (優先順序)|**Weight** (權數)|**Port** (連接埠)|**結果**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip。 _tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls。 _tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![在 [服務記錄] 區段中輸入值](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. 選取 **[儲存]**。
    
    (You may have to scroll down.)
    
    ![選取 [儲存]](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
