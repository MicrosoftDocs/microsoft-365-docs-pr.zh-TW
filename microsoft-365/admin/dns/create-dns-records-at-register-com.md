---
title: 在 Register.com 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Register.com。
ms.openlocfilehash: 7a11fa248f2602eb02fe1242234d26584bd33fd2
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780322"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a>在 Register.com 建立 Microsoft 的 DNS 記錄

 若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。 
  
如果 Register.com 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。
  
以下是要新增的主要記錄。 請依照下列步驟操作或[觀看影片](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4)。
  
- [在 Register.com 新增 TXT 記錄以驗證您擁有該網域](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [新增 Microsoft 所需的 CNAME 記錄](#add-the-cname-records-that-are-required-for-microsoft)
    
- [新增 SPF 的 TXT 記錄以協助防範垃圾郵件](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [新增兩筆 Microsoft 所需的 SRV 記錄](#add-the-two-srv-records-that-are-required-for-microsoft)
    
在 Register.com 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a>在 Register.com 新增 TXT 記錄以驗證您擁有該網域
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
請依照下列步驟操作或[觀看影片 (從 0:44 處開始)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4)。
  
1. 首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。 系統會提示您先登入。
    
2. Select **Domains**.
    
3. 選取 [**管理**]。
    
4. 尋找包含您要修改的功能變數名稱的列;然後在該資料列中，選取 [**管理**]。
    
5. 向下滾動至 [**高級技術設定**] 區段，然後選取 [**編輯 TXT 記錄（SPF）**]。
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |||
    |:-----|:-----|
    |**Host Name** <br/> |**TXT Record** <br/> |
    |@  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。 [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          |
   
7. 選取 [**繼續**]。
    
8. 在下一個頁面上，選取 [**繼續**]，以確認您的變更。 
    
9. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。
  
在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。
  
1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。
    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft
<a name="BKMK_add_MX"> </a>

請依照下列步驟操作或[觀看影片 (從 3:32 處開始)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4)。
  
1. 首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。 系統會提示您先登入。
    
2. Select **Domains**.
    
3. 選取 [**管理**]。
    
4. 尋找包含您要修改的功能變數名稱的列;然後在該資料列中，選取 [**管理**]。
    
5. 流覽至 [**高級技術設定**] 區段，然後選取 [**編輯郵件交換器記錄**]。
    
    ![選取 [編輯郵件交換器] 記錄](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. 在新記錄的方塊中，輸入或複製並貼上下表中的值。
    
    （從下拉式清單中選擇 [**優先順序**] 值。） 
    
    |主機名稱 * * * *|優先順序 * * * *|郵件伺服器 * * * *|
    |:-----|:-----|:-----|
    |@  <br/> |High (高)  <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*。 mail.protection.outlook.com  <br/>  <br/>**附注：**\<*domain-key*\>從您的 Microsoft 帳戶取得。 <br> [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![複製並貼上表格中的值](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. 如果已經列出任何其他 MX 記錄，請逐一選取要刪除的記錄。
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. 選取 [**繼續**]。
    
    ![選取 [繼續]](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. 在下一個頁面上，選取 [**繼續**] 以確認並儲存您的變更。 
    
    ![選取 [繼續]](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

請依照下列步驟操作或[觀看影片 (從 4:23 處開始)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4)。
  
1. 首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。 系統會提示您先登入。
    
2. Select **Domains**.
    
3. 選取 [**管理**]。
    
4. 尋找包含您要修改的功能變數名稱的列;然後在該資料列中，選取 [**管理**]。
    
5. 流覽至 [**高級技術設定**] 區段，然後選取 [**編輯網域別名記錄**]。
    
    ![選取 [編輯網域別名記錄]](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. 選取 [**新增更多網域別名**]。
    
    ![選取 [新增更多網域別名]](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. 新增所需的 CNAME 記錄。
    
    在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。
    
    |第一個欄位（未標記） * * * *|指向 * * * *|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/>  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com <br/>  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/>  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/>  <br/> |
   
     ![複製並貼上表格中的 DNS 值](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. 當您已新增所需的所有 CNAME 記錄後，請選取 [**繼續**]。
    
    ![選取 [繼續]](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. 在下一個頁面上，選取 [**繼續**] 以確認並儲存您的變更。 
    
    ![選取 [繼續]](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。 而是，請將必要的 Microsoft 值新增到目前的記錄，以便擁有包含這兩組值的單一 SPF 記錄。  
  
請依照下列步驟操作或[觀看影片 (從 5:12 處開始)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4)。
  
1. 首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。 系統會提示您先登入。
    
2. Select **Domains**.
    
3. 選取 [**管理**]。
    
4. 尋找包含您要修改的功能變數名稱的列;然後在該資料列中，選取 [**管理**]。
    
5. 滾動至 [**高級技術設定**] 區段，然後選取 **[編輯 TXT 記錄（SPF）**]。
    
    ![選取 [編輯 TXT 記錄（SPF）]](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. 在新記錄的方塊中，輸入或複製並貼上下表中的值。
    
    |主機名稱 * * * *|TXT 記錄 * * * *|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。  |
   
     ![複製並貼上表格中的值](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. 選取 [**繼續**]。
    
    ![選取 [繼續]](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. 在下一個頁面上，選取 [**繼續**] 以確認並儲存您的變更。 
    
    ![選取 [繼續]](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>新增兩筆 Microsoft 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

請依照下列步驟操作或[觀看影片 (從 5:55 處開始)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4)。
  
1. To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.
    
2. Select **Domains**.
    
3. 選取 [**管理**]。
    
4. 尋找包含您要修改的功能變數名稱的列;然後在該資料列中，選取 [**管理**]。
    
5. 滾動至 [**高級技術設定**] 區段，然後選取 [**編輯 SRV 記錄**]。
    
    ![選取 [編輯 SRV 記錄]](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. 新增兩筆 SRV 記錄的第一筆：
    
    在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。
    
    （從下拉式清單中選擇 [**優先順序**] 值。） 
    
    |服務 * * * *|Proto * * * *|****名稱****|優先順序 * * * *|體重 * * * *|埠 * * * *|目標 * * * *|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |High (高)  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |High (高)  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/>  <br/> |
   
    ![複製並貼上表格中的值](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. 選取 [**新增更多 SRV 記錄**]。
    
    ![選取 [新增更多 SRV 記錄]](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. 新增第二筆 SRV 記錄：
    
    在第二筆記錄的方塊中，輸入或複製並貼上表格中第二列的值。
    
9. 當您新增這兩個 SRV 記錄時，請選取 [**繼續**]。
    
    ![選取 [繼續]](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. 在下一個頁面上，選取 [**繼續**] 以確認並儲存您的變更。 
    
    ![選取 [繼續]](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。 
  
