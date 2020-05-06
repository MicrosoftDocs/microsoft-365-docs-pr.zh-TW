---
title: 在 Cloudflare 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Cloudflare。
ms.openlocfilehash: 36578d8eed2c5630a9ce5abfb355983a26028888
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049068"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a>在 Cloudflare 建立 Microsoft 的 DNS 記錄

 若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。 
  
如果 Cloudflare 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。
  
在 Cloudflare 新增這些記錄之後，您的網域就會設定為與 Microsoft 365 服務搭配使用。
  
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>變更您網域的名稱伺服器 (NS) 記錄
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> 您必須在您購買及註冊網域的網域註冊機構中執行此程序。 
  
當您註冊 Cloudflare 時，您會使用 Cloudflare**安裝程式**來新增網域。 
  
您所新增的網域是從 Cloudflare 或個別網域註冊機構購買。 若要在 Microsoft 365 中驗證及建立網域的 DNS 記錄，您必須先在網域註冊機構變更名稱伺服器，以便使用 Cloudflare 的名稱伺服器。
  
若要自行在網域註冊機構網站變更自家網域的名稱伺服器，請遵循下列步驟進行：
  
1. 在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。
    
2. 您可以使用下表中的值建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，使其符合這些值。
    
    |||
    |:-----|:-----|
    |First nameserver (第一個名稱伺服器)  <br/> |使用 Cloudflare 提供的名稱伺服器值。  <br/> |
    |Second nameserver (第二個名稱伺服器)  <br/> |使用 Cloudflare 提供的名稱伺服器值。  <br/> |
   
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
  
1. 若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用[此連結](https://www.cloudflare.com/a/login)。 系統會提示您先登入。
  
2. 在**首頁**上，選取您要更新的網域。 
  
3. 在您網域的 [**一覽表**] 頁面上，選取 [ **DNS**]。

  
4. 在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取下表中的值。 
    
    |**類型**|**名稱**|**自動 TTL**|**內容**|
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 分鐘  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 在這裡請使用您自己來自表格的 [目的地或指向位址]**** 值。           [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. 選取 [儲存]****。
  
  
9. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並搜尋該記錄。
  
在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。
  
1. 在 Microsoft 系統管理中心中，移至 [設定]**** \> [網域]<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> 頁面。

    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
    
  
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
    
    
  
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
    
    
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft
<a name="BKMK_add_MX"> </a>

1. 若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用[此連結](https://www.cloudflare.com/a/login)。 系統會提示您先登入。
  
2. 在**首頁**上，選取您要更新的網域。 
  
3. 在您網域的 [**一覽表**] 頁面上，選取 [ **DNS**]。

  
4. 在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取下表中的值。 
    
    |**類型**|**名稱**|**郵件伺服器**|**Priority** (優先順序)|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<網域金鑰\>*  .mail.protection.outlook.com  <br/> **附注：** 從 Microsoft 365 帳戶取得您* \<的網域金鑰\> * 。   [How do I find this?](../get-help-with-domains/information-for-dns-records.md) |1  <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/>|30 分鐘  <br/> |
   

  
5. 選取 [儲存]****。
  
9. 如果 [ **Mx 記錄**] 區段中列出任何其他 MX 記錄，請選取**刪除（X）** 圖示加以刪除。 
  
10. 在確認對話方塊中，選取 [**刪除**] 以確認變更。 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>新增 Microsoft 所需的六筆 CNAME 記錄
<a name="BKMK_add_CNAME"> </a>

1. 若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用[此連結](https://www.cloudflare.com/a/login)。 系統會提示您先登入。
    
  
2. 在**首頁**上，選取您要更新的網域。 
  
3. 在您網域的 [**一覽表**] 頁面上，選取 [ **DNS**]。

  
4. 新增五筆 CNAME 記錄中的第一筆。
    
    在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取下表中的值。
    
    
    |**類型**|**Name** (名稱)|**Target** (目標)|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30 分鐘  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 分鐘  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 分鐘  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 分鐘  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 分鐘  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 分鐘  <br/> |
    
  
5. 選取 [ **DNS 流量**] 圖示（橙色雲端）以略過 Cloudflare 伺服器。
  
6. 選取 [儲存]****。
  
7. 逐一新增其餘五筆 CNAME 記錄。

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果網域已經有 SPF 記錄，請勿為 Microsoft 365 建立一個新的記錄。 而是，請將必要的 Microsoft 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。 
  
1. 若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用[此連結](https://www.cloudflare.com/a/login)。 系統會提示您先登入。
    
  
2. 在**首頁**上，選取您要更新的網域。 
  
3. 在您網域的 [**一覽表**] 頁面上，選取 [ **DNS**]。

  
4. 在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取下表中的值。  
    
    |**類型**|**名稱**|**TTL**|**內容**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 分鐘  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。   |

 
5. 選取 [儲存]****。
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>新增兩筆 Microsoft 所需的 SRV 記錄
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> 請記住，Cloudflare 可讓您使用此功能。 當您看到下列步驟與目前 Cloudflare GUI （圖形使用者介面）之間的差異時，請利用[Cloudflare 社區](https://community.cloudflare.com/)。 

1. 若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用[此連結](https://www.cloudflare.com/a/login)。 系統會提示您先登入。
      
2. 在**首頁**上，選取您要更新的網域。 
  
3. 在您網域的 [**一覽表**] 頁面上，選取 [ **DNS**]。
  
4. 新增兩筆 SRV 記錄中的第一筆。

    在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取下表中第一列的值。
        
    |**類型**|**服務**|**Protocol** (通訊協定)|**Name**|**TTL**|**Priority** (優先順序)|**Weight** (權數)|**Port** (連接埠)|**Target** (目標)|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |使用您的*domain_name*;例如，contoso.com  |30 分鐘 | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|使用您的*domain_name*;例如，contoso.com   |30 分鐘 |100 |1 |5061 | sipfed.online.lync.com |

  
5. 選取 [儲存]****。

  
6. 從資料表的第二列中選擇值，以新增其他 SRV 記錄。 

    
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
