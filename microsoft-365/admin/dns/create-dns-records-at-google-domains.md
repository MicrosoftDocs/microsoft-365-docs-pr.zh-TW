---
title: 在 Google Domains 建立 Microsoft 的 DNS 記錄
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: 了解如何在 Microsoft 的 Google Domains 中驗證網域，並為電子郵件、Lync 和其他服務設定 DNS 記錄。
ms.openlocfilehash: e6b1dd1eb90957a4e7fe22bd4b66ac87b2a51d09
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400446"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a>在 Google Domains 建立 Microsoft 的 DNS 記錄

 若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。 
  
如果 Google Domains 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與 Lync 等項目的 DNS 記錄。
  
在 Google Domains 新增這些記錄之後，您的網域就會設定為搭配 Microsoft 服務使用。
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Microsoft 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
1. 選取 **[登入]**。
    
2. 輸入您的登入認證，然後再次選取 **[登入]**。
    
2. 在 **[我的網域]** 頁面上，找到您要與 Microsoft 搭配使用的網域，然後選取其旁邊的 **[管理]** 連結。 在左側瀏覽窗格中，選取 **[DNS]**。
    
3. 在 [自訂資源記錄]  區段，於新記錄的方塊中，輸入或複製並貼上下表中的值。 
    
    (您可能需要向下捲動。)
    
    (從下拉式清單中選擇 [Type] (類型) 值。) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**類型** <br/> |**TTL** <br/> |**資料** <br/> |
    |@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。 [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          |
   
4. 選取 **[新增]**。
    
5. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。
  
在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。
  
1. 在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
2. 選取 **[登入]**。
    
3. 輸入您的登入認證，然後再次選取 **[登入]**。
4. 在 **[網域]** 頁面中的 **[網域]** 章節，針對您想要編輯的網域，選取 **[設定 DNS]**。
    
    > [!IMPORTANT]
    > 如果您擁有 G Suite 電子郵件帳戶，則必須先刪除與該帳戶相關聯的 MX 記錄。 G Suite 的 MX 記錄會使您無法新增其他 MX 記錄，包括 Microsoft 所需的記錄。 請注意，刪除 G Suite 記錄並不會刪除您的 G Suite 帳戶。 若要刪除您的 G Suite MX 記錄，請依照下列步驟操作。 
  
5. 在 **[綜合記錄]** 章節的 **[G 套件]** 區域，選取 **[刪除]**。
    
    (您可能需要向下捲動。)
    
    ![選取 [綜合記錄] 章節中的 [刪除]。](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. 選取 **[刪除]**。
    
    ![選取 [刪除]](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. 在 [自訂資源記錄]  區段，於新記錄的方塊中，輸入或複製並貼上下表中的值。 
    
    (您可能需要向下捲動。)
    
    (從下拉式清單中選擇 [Type] (類型) 值。) 
    
    |**Name**|**類型**|**TTL**|**資料**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **此值必須以英文句點 (.) 結尾。** <br/> **0** 是指 MX 優先順序值。 請將它新增到 MX 值的開頭，並以空格分隔該值的其餘部分。  <br/> **注意：** 從您的 Microsoft 帳戶取得您的 \<*domain-key*\>。  [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |
   
    ![在 [自訂資源記錄] 區段中輸入或貼上值](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. 選取 **[新增]**。
    
    ![選取 [新增]](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. 如果有任何其他的自訂 MX 記錄，請移除它們。
    
1. 選取 [MX 記錄] 列中的 **[編輯]**。 
    
    ![選取 [MX 記錄] 列中的 [編輯]。](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. 針對其他各筆自訂 MX 記錄，選取 **[資料]** 方塊中的項目，然後按下鍵盤上的 **[刪除]** 鍵來刪除該記錄。 
    
    繼續作業，直到刪除其他各筆 MX 記錄的 **[資料]** 項目為止。 
    
    ![刪除 [資料] 方塊中的專案](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. 當您刪除每一筆其他 MX 記錄的 **[資料]** 項目後，選取 **[儲存]** 以儲存您的變更。 
    
    ![選取 [儲存]。](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的5筆 CNAME 記錄

1. 若要開始使用，請移至您的 [Google 網域頁面] （https://domains.google.com/registrar) 並登入。
    
2. 在 **[網域]** 頁面中的 **[網域]** 章節，針對您想要編輯的網域，選取 **[設定 DNS]**。 
    
3. 新增第一筆 CNAME 記錄。
    
    在 [Custom resource records] (自訂資源記錄)**** 區段，於新記錄的方塊中輸入或複製貼上下表中第一列的值。 
    
    (您可能需要向下捲動。)
    
    (從下拉式清單中選擇 [Type] (類型) 值。) 
    
    |**Name**|**類型**|**TTL**|**資料**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H  <br/> |autodiscover.outlook.com.  <br/> **此值必須以英文句點 (.) 結尾。** <br/> |
    |sip  <br/> |CNAME  <br/> |1H  <br/> |sipdir.online.lync.com.  <br/> **此值必須以英文句點 (.) 結尾。** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H  <br/> |webdir.online.lync.com.  <br/> **此值必須以英文句點 (.) 結尾。** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H  <br/> |enterpriseregistration.windows.net.  <br/> **此值必須以英文句點 (.) 結尾。** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **此值必須以英文句點 (.) 結尾。** <br/> |
   
    ![在 [自訂資源記錄] 區段中輸入或貼上值](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. 選取 **[新增]**。
    
    ![選取 [新增]](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. 新增其他四筆 CNAME 記錄。
    
    在 **[自訂資源記錄]** 區段中，使用表格中下一列的值來建立記錄，然後再選取一次 **[新增]** 以完成該筆記錄。 
    
    重複這個程序，直到所有要求的 CNAME 記錄全部建立完畢。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。 而是，請將必要的 Microsoft 值新增到目前的記錄，以便擁有包含這兩組值的單一 SPF 記錄。 需要範例？ 請參閱這些 [Microsoft 的外部網域名稱系統記錄](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords)。 若要驗證您的 SPF 記錄，您可以使用其中一種 [SPF 驗證工具](../setup/domains-faq.md)。 
  
1. To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
1. 選取 **[登入]**。
    
2. 輸入您的登入認證，然後再次選取 **[登入]**。
    
3. 在 **[網域]** 頁面中的 **[網域]** 章節，針對您想要編輯的網域，選取 **[設定 DNS]**。 
    
4. 在 **[自訂資源記錄]** 區段中的 TXT記錄列上，選取 **[編輯]**。 
    
    > [!IMPORTANT]
    > Google Domains 會將 TXT 記錄儲存為一組可包含多個記錄的集合。 當您有至少一個其他的 TXT 記錄時 (例如用於驗證網域的 TXT 記錄)，您必須新增 TXT 新記錄到該記錄集。 任何嘗試輸入額外 TXT 記錄做為不同項目，會導致 **「重複記錄」** 錯誤訊息。 
  
    ![選取 TXT 記錄列中的 [編輯]](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. 選取 **[+]** 控制項。  
    
    ![選取加號控制項](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. 在新記錄的方塊中，輸入或複製並貼上下表中的值。
    
    (您可能需要向下捲動。)
    
    |**資料**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > 建議您複製並貼上這個項目，好讓所有的間距保持正確。           
   
   ![在 [自訂資源記錄] 區段中輸入或貼上值](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. 選取 **[儲存]**。
    
    ![選取 [儲存]。](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>新增兩筆 Microsoft 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
2. 選取 **[登入]**。
    
3. 輸入您的登入認證，然後再次選取 **[登入]**。
    
4. 在 **[網域]** 頁面中的 **[網域]** 章節，針對您想要編輯的網域，選取 **[設定 DNS]**。 
    
5. 新增第一筆 SRV 記錄。
    
    在 [自訂資源記錄]  區段，於新記錄的方塊中，輸入或複製並貼上下表中的值。 
    
    (您可能需要向下捲動。)
    
    (從下拉式清單中選擇 [Type] (類型) 值。) 
    
    |**Name**|**類型**|**TTL**|**資料**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|SRV|1H|100 1 443 sipdir.online.lync.com. **此值必須以英文句點 (.) 結尾** **注意:** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |
    |_sipfederationtls._tcp|SRV|1H|100 1 5061 sipfed.online.lync.com. **此值必須以英文句點 (.) 結尾。**

    建議您複製並貼上這個項目，好讓所有的間距保持正確。       
   
    ![在 [自訂資源記錄] 區段中輸入或貼上值](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. 選取 **[新增]**。
    
    ![選取 [新增]](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. 新增另一筆 SRV 記錄。
    
    在 **[自訂資源記錄]** 區段中，使用表格中第二列的值來建立記錄，然後再選取一次 **[新增]** 以完成該筆記錄。 
    
    > [!NOTE]
    > Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
