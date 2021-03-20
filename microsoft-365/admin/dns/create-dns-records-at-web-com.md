---
title: 在 web.com 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft web.com。
ms.openlocfilehash: b667b2e69822fcd69babda7790a6468b640b073b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909979"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a>在 web.com 建立 Microsoft 的 DNS 記錄

 若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。 
  
如果 web.com 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。
  
在 web.com 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。

  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>變更您網域的名稱伺服器 (NS) 記錄
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> 您必須在您購買及註冊網域的網域註冊機構中執行此程序。 
  
當您註冊 web.com 時，您會使用 web.com **安裝程式** 來新增網域。 
  
若要在 Microsoft 中驗證及建立網域的 DNS 記錄，您必須先在您的網域註冊機構中變更名稱伺服器，以使用 web.config 的名稱伺服器。
  
若要自行在網域註冊機構網站變更自家網域的名稱伺服器，請遵循下列步驟進行：
  
1. 在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。
    
2. 您可以使用下表中的值建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，使其符合這些值。
    
    |||
    |:-----|:-----|
    |First nameserver (第一個名稱伺服器)  <br/> |使用 web.com 提供的名稱伺服器值。  <br/> |
    |Second nameserver (第二個名稱伺服器)  <br/> |使用 web.com 提供的名稱伺服器值。  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. 如果有列出任何其他名稱伺服器，您應該將其刪除。 
  
3. 儲存變更。
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_verify"> </a>

在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 若要開始使用，請移至您的網域頁面 web.com，方法是使用 [此連結](https://checkout.web.com/manage-it/index.jsp)。 先登入。
  
2. 在 [ **帳戶管理員** ] 頁面上，選取 [ **我的網功能變數名稱稱**]。 
  
3. 在 [* * Manage * my domain * * *] 底下，選取 [ **編輯高級 DNS 記錄**]。

  
4. 在 [ **功能變數名稱** ] 頁面的 [ **文字 (TXT) 記錄**] 下，按一下 [ **編輯 TXT 記錄**]，然後選取下表中的值。 
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。           [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. 選取 [ **繼續**]。
  
  
6. 請等候幾分鐘，再驗證新的 TXT 記錄，讓您剛才建立的記錄可以在網際網路上更新。
    
現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。
  
在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。
  
1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
    
  
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
    
  
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
    
    
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft
<a name="BKMK_add_MX"> </a>

1. 若要開始使用，請移至您的網域頁面 web.com，方法是使用 [此連結](https://checkout.web.com/manage-it/index.jsp)。 先登入。
  
2. 在 [ **帳戶管理員** ] 頁面上，選取 [ **我的網功能變數名稱稱**]。 
  
3. 在 [* * Manage * my domain * * *] 底下，選取 [ **編輯高級 DNS 記錄**]。

4. 在 [ **郵件伺服器 (MX 記錄**] 底下) ，按一下 [ **編輯 MX 記錄**]，然後選取下表中的值。 
    
    |**Priority** (優先順序)|**TTL**|**郵件伺服器**|
    |:-----|:-----|:-----|
    |1  <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](../setup/domains-faq.yml) <br/> |3600  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **附注：***\<domain-key\>* 從您的 Microsoft 帳戶取得。   [如何找到呢？](../get-help-with-domains/information-for-dns-records.md) |
   

5. 選取 [儲存]。
  
6. 如果 [ **Mx 記錄** ] 區段中列出任何其他 MX 記錄，請選取 [ **刪除**] 底下的記錄旁的核取方塊，然後選取 [ **儲存**]。 
  
7. 在確認畫面上，選取 [ **儲存變更**]。 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的六筆 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

1. 若要開始使用，請移至您的網域頁面 web.com，方法是使用 [此連結](https://checkout.web.com/manage-it/index.jsp)。 系統會提示您先登入。
     
2. 在 [ **帳戶管理員** ] 頁面上，選取 [ **我的網功能變數名稱稱**]。 
  
3. 在 [* * Manage * my domain * * *] 底下，選取 [ **編輯高級 DNS 記錄**]。

4. 新增六筆 CNAME 記錄的第一筆。
    
    在 [ **主機別名] (CNAME 記錄)** 上，按一下 [ **編輯 CNAME 記錄**]，然後選取下表中的值。
    
    
    |**Alias**|**TTL**|**參照的主機名稱**|**其他主機**|
    |:-----|:-----|:-----|:-----|
    |autodiscover (自動探索)  <br/> |3600  <br/> |@ (無)   <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ (無)   <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ (無)   <br/> | webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ (無)   <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ (無)   <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ (無)   <br/> |clientconfig.microsoftonline-p.net  <br/> |
    
  
5. 選取 [ **繼續**]。
  
6. 逐一新增其餘五筆 CNAME 記錄。

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。 請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。 
  
1. 若要開始使用，請移至您的網域頁面 web.com，方法是使用 [此連結](https://checkout.web.com/manage-it/index.jsp)。 先登入。
    
  
2. 在 [ **帳戶管理員** ] 頁面上，選取 [ **我的網功能變數名稱稱**]。 
  
3. 在 [* * Manage * my domain * * *] 底下，選取 [ **編輯高級 DNS 記錄**]。

  
4. 在 [ **功能變數名稱** ] 頁面的 [ **文字 (TXT) 記錄**] 下，按一下 [ **編輯 TXT 記錄**]，然後選取下表中的值。   
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。   |

 
5. 選取 [ **繼續**]。

6. 選取 **[儲存變更]**。
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>新增兩筆 Microsoft 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> 請記住，web.com 可讓您使用此功能。 當您看到下列步驟與目前的 web.com GUI (圖形使用者介面) 時，請利用 [Web.com 社區](https://community.web.com.com/)。 

1. 若要開始使用，請移至您的網域頁面 web.com，方法是使用 [此連結](https://checkout.web.com/manage-it/index.jsp)。 先登入。
      
2. 在 [ **帳戶管理員** ] 頁面上，選取 [ **我的網功能變數名稱稱**]。 
  
3. 在 [* * Manage * my domain * * *] 底下，選取 [ **編輯高級 DNS 記錄**]。
  
4. 新增兩筆 SRV 記錄中的第一筆。

    在 [ **服務 (SRV 記錄])** 上，按一下 [ **編輯 srv 記錄**]，然後選取下表中的值。 
        
    |**服務**|**Protocol** (通訊協定)|**TTL**|**Priority** (優先順序)|**Weight** (權數)|**Port** (連接埠)|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1 |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1 |5061 | sipfed.online.lync.com |

  
5. 從資料表的第二列中選擇值，以新增其他 SRV 記錄。 
  
6. 選取 [ **繼續**]。

7. 選取 **[儲存變更]**。

    
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
