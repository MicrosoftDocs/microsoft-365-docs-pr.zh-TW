---
title: 在任一 DNS 主機服務提供者建立 DNS 記錄
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7b7b075d-79f9-4e37-8a9e-fb60c1d95166
description: 了解如何在 Microsoft 365 的任一 DNS 主機服務提供者上驗證您的網域並建立 DNS 記錄。
ms.custom: okr_smb
ms.openlocfilehash: 85392bfbd19072d582e7c2db7ce3a8c7bf466176
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628491"
---
# <a name="create-dns-records-at-any-dns-hosting-provider"></a>在任一 DNS 主機服務提供者建立 DNS 記錄

 若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。 
  
查看我們的[特定主機指示](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) 來尋找您的主機，並遵循步驟來新增您需要的所有記錄。 
  
如果您不知道您網域的 DNS 主機提供者或網域註冊機構，請參閱[尋找您的網域註冊機構或 DNS 主機服務提供者](../get-help-with-domains/find-your-domain-registrar.md)。
  
若要自行設定記錄，以下是必須新增的記錄。 請注意，您的驗證記錄和 MX 記錄對您的網域來說是唯一的。 若要進行設定，您必須為網域取得和使用特定的「權杖」值。 下列步驟說明如何執行這項作業。
  
> [!IMPORTANT]
> 對於每個 DNS 主機來說，在建立每種類型的 DNS 記錄時，在其上輸入或貼上資訊的方塊或 *[欄位]* 的確切名稱都不同。 您的 DNS 主機在其網站上可能提供說明，協助您將此處所述的指示對應到網站上的確切欄位。 請記得在[建立 Microsoft 365 的 DNS 記錄](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx)中查看我們是否提供您 DNS 主機的逐步指示。 > 某些 DNS 主機不會讓您建立所有需要的記錄類型，而這會導致 Microsoft 365 的[服務限制](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) (部分機器翻譯)。 例如，如果您的網域主機不支援 SRV、TXT 或 CNAME 記錄，建議您[將網域移轉](../get-help-with-domains/buy-a-domain-name.md)至支援所有必要記錄的 DNS 主機。 建議您將網域移轉至 GoDaddy，以獲得快速且自動化的 Microsoft 365 設定程序。 
  
> [!NOTE]
> 通常需要幾分鐘，DNS 變更才會生效。 然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。 在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正變更網域名稱或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md) (部分機器翻譯)。 
  
## <a name="add-a-txt-or-mx-record-for-verification"></a>新增 TXT 或 MX 記錄以進行驗證
<a name="BKMK_verify"> </a>

> [!NOTE]
> 您只能建立這些記錄的其中一種。TXT 是慣用的記錄類型，但部分 DNS 主機服務提供者不支援，在這種情況下，您可以改為建立 MX 記錄。 
  
在您將自己的網域用於 Microsoft 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
 **在 DNS 主機服務提供者的網站上，找出您可以建立新記錄的區域。**
  
1. 登入您 DNS 主機服務提供者的網站。
    
2. 選擇您的網域。
    
3. 找出可編輯網域 DNS 記錄的頁面。
    
 **建立記錄。**
  
1. 請根據您要建立 TXT 記錄還是 MX 記錄而定，執行下列其中一項操作：
    
  - **如果您建立 TXT 記錄，請使用以下值：**
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型)|**Alias** (別名) 或 **Host Name** (主機名稱)|**Value** (值)|**TTL**|
|TXT|請執行下列其中一項操作：輸入 **@** ，或是保留欄位空白，或輸入您的網域名稱。  <br/> **附註：** 不同的 DNS 主機對此欄位有不同的要求。 |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 在這裡請使用您自己的 [目的地或指向位址]**** 值，請參閱 Microsoft 365 表格。  <br/>        [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)     <br/>     |將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 ( **60** )、秒數 ( **3600** ) 等。  |
   
  - **如果您建立 MX 記錄，請使用以下值：**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型)|**Alias** (別名) 或 **Host Name** (主機名稱)|**Value** (值)|**Priority** (優先順序)|**TTL**|
|MX|輸入 **@** 或您的網域名稱。 |MS=ms *XXXXXXXX* <br/> **附註：** 這是範例。 在這裡請使用您自己的 [目的地或指向位址]**** 值，請參閱 Microsoft 365 表格。    <br/>       [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)     <br/>     |針對 **[Priority]** (優先順序)，為避免跟用於郵件流程的 MX 記錄發生衝突，請使用比任一現有 MX 記錄更低的優先順序。 <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 ( **60** )、秒數 ( **3600** ) 等。 |
   
2. 儲存記錄。
    
現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 365 並要求 Microsoft 365 尋找該記錄。
  
在 Microsoft 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。
  
1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。
    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
  
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
       
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。   
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-mx-record-to-route-email"></a>新增 MX 記錄以路由傳送電子郵件
<a name="BKMK_add_MX"> </a>

新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft 365。  *更新網域的 MX 記錄時，使用您網域所有人的所有新電子郵件現在都會傳送至 Microsoft 365*。 您已收到的任何電子郵件將會保留在目前的電子郵件主機中，除非您決定[將電子郵件和連絡人移轉至 Microsoft 365](../setup/migrate-email-and-contacts-admin.md)。 
  
  
 **工作**
  
找出可建立您網域記錄的頁面。
  
1. 登入 DNS 主機的網站。
    
2. 選擇您的網域。
    
3. 找出可編輯網域 DNS 記錄的頁面。
    
::: moniker range="o365-worldwide"

您要新增的 MX 記錄包含一個類似 \<MX token\>.mail.protection.outlook.com 的值 (**[指向位址]** 值)，其中 \<MX token\> 值類似 MSxxxxxxx。 

::: moniker-end

::: moniker range="o365-germany"

您要新增的 MX 記錄包含一個類似 \<MX token\>.mail.protection.outlook.de 的值 (**[指向位址]** 值)，其中 \<MX token\> 值類似 MSxxxxxxx。 

::: moniker-end

1. 在您的 DNS 主機網站上，新增 MX 記錄。
    
    現在您將從 Microsoft 365 [取得 MX 記錄的資訊](../get-help-with-domains/information-for-dns-records.md)。 
    
2. 針對 MX 記錄 (於上述步驟中)，請複製 **[指向位址]** 值。 
    
    您將會在於 DNS 主機網站上建立的記錄中使用此值，如下一個步驟所述。
    
3. 在 DNS 主機網站上的新 MX 記錄中，確認以下欄位會精確地設定為下列值：
    
  - **Record Type** (記錄類型)：**MX**
    
  - **Priority** (優先順序)：將 MX 記錄的優先順序設為可用的最高值，通常是 **[0]**。
    
    如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)
    
  - **主機名稱**：**@**
    
  - **Points to address** (指向位址)：貼上您從 Microsoft 365 複製的 [指向位址]**** 值。 
    
  - **TTL**：將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 (**60**)、秒數 (**3600**) 等。 
    
4. 儲存記錄。
    
移除所有其他 MX 記錄。
  
如果此網域中有任何 MX 記錄會將電子郵件傳送至 Microsoft 365 以外的其他位置，請將這些記錄全部刪除。
  
## <a name="add-three-cname-records"></a>新增三筆 CNAME 記錄
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

請按照下列步驟新增 Microsoft 365 所需的三筆 CNAME 記錄。 如果 Microsoft 365 中列出其他 CNAME 記錄，也請同樣按照這裡顯示的一般步驟來新增這些記錄。
  
您將會在 DNS 主機網站上建立三筆新的 CNAME 記錄，通常是一次建立一筆。
  
1. 在每一筆新記錄的方塊中，輸入或複製並貼上下列值。 新增前三個新記錄後，請選擇建立另一個 CNAME 記錄。
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型) <br/> |**Host** (主機) <br/> |**Points to** (指向) <br/> |**TTL** <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 小時  <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 小時  <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 hour (1 小時)  <br/> |
   
   > [!NOTE]
   > **TTL**：將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 (**60**)、秒數 (**3600**) 等。這些記錄不適用於 Exchange、Lync 或商務用 Skype 混合式部署。 
  
2. 完成後，請儲存記錄。
    
::: moniker-end
::: moniker range="o365-germany"

請按照下列步驟新增 Microsoft 365 所需的三筆 CNAME 記錄。 如果 Microsoft 365 中列出其他 CNAME 記錄，也請同樣按照這裡顯示的一般步驟來新增這些記錄。
  
您將會在 DNS 主機網站上建立三筆新的 CNAME 記錄，通常是一次建立一筆。
  
1. 在每一筆新記錄的方塊中，輸入或複製並貼上下列值。 新增前三個新記錄後，請選擇建立另一個 CNAME 記錄。
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型) <br/> |**Host** (主機) <br/> |**Points to** (指向) <br/> |**TTL** <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |autodiscover  <br/> |autodiscover-outlook.office.de  <br/> |1 小時  <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |lyncdiscover  <br/> |webdir.online.skype.de  <br/> |1 小時  <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |sip  <br/> |sipdir.online.lync.de  <br/> |1 hour (1 小時)  <br/> |
   
   > [!NOTE]
   > **TTL**：將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 (**60**)、秒數 (**3600**) 等。這些記錄不適用於 Exchange、Lync 或商務用 Skype 混合式部署。 
  
2. 完成後，請儲存記錄。
    
::: moniker-end

::: moniker range="o365-21vianet"

請按照下列步驟新增 Microsoft 365 所需的三筆 CNAME 記錄。 如果 Microsoft 365 中列出其他 CNAME 記錄，也請同樣按照這裡顯示的一般步驟來新增這些記錄。
  
您將會在 DNS 主機網站上建立三筆新的 CNAME 記錄，通常是一次建立一筆。
  
1. 在每一筆新記錄的方塊中，輸入或複製並貼上下列值。 新增前三個新記錄後，請選擇建立另一個 CNAME 記錄。
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型) <br/> |**Host** (主機) <br/> |**Points to** (指向) <br/> |**TTL** <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |autodiscover  <br/> |autodiscover.partner.outlook.cn  <br/> |1 小時  <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |lyncdiscover  <br/> |webdir.online.partner.lync.cn  <br/> |1 小時  <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |sip  <br/> |sipdir.online.partner.lync.cn  <br/> |1 hour (1 小時)  <br/> |
   
   > [!NOTE]
   > **TTL**：將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 (**60**)、秒數 (**3600**) 等。這些記錄不適用於 Exchange、Lync 或商務用 Skype 混合式部署。 
  
2. 完成後，請儲存記錄。
    
::: moniker-end

## <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft-365"></a>為 Microsoft 365 行動裝置管理 (MDM) 新增兩筆 CNAME 記錄
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> 如果您有 Microsoft 365 行動裝置管理 (MDM)，則您必須建立兩筆其他的 CNAME 記錄。 請按照您針對其他四筆 CNAME 記錄所進行的程序執行，但提供下表的值。 > (如果您沒有 MDM，可以跳過這個步驟。) 
  
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型) <br/> |**Host** (主機) <br/> |**Points to** (指向) <br/> |**TTL** <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 小時  <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 小時  <br/> |
   
::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> 如果您有 Microsoft 365 行動裝置管理 (MDM)，則您必須建立兩筆其他的 CNAME 記錄。 請按照您針對其他四筆 CNAME 記錄所進行的程序執行，但提供下表的值。 > (如果您沒有 MDM，可以跳過這個步驟。) 
  
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型) <br/> |**Host** (主機) <br/> |**Points to** (指向) <br/> |**TTL** <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |enterpriseregistration  <br/> |enterpriseregistration.microsoftonline.de  <br/> |1 小時  <br/> |
|CNAME (Alias) (CNAME (別名))  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 hour (1 小時)  <br/> |
   
::: moniker-end

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果網域已經有 SPF 記錄，請勿為 Microsoft 365 建立一個新的記錄。 而是，請將必要的 Microsoft 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。
  
在您的 DNS 主機網站上，編輯現有 SPF 記錄或建立 SPF 的新 TXT 記錄。
  
> [!IMPORTANT]
> SPF 是設計來協助防止詐騙，但是仍有 SPF 無法防護的詐騙技術。 為了防範這些技術，設定 SPF 之後，您也應該為 Microsoft 365 設定 DKIM 和 DMARC。 若要開始使用，請參閱[在 Microsoft 365 中使用 DKIM 驗證從您的網域傳送的外寄電子郵件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。 接下來，請參閱[在 Microsoft 365 中使用 DMARC 來驗證電子郵件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。 
  
1. 在每一筆新記錄的方塊中，輸入或複製並貼上下列適用於您的情況的一組值。
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型) <br/> |**Host** (主機) <br/> |**TXT Value** (TXT 值) <br/> |**TTL** <br/> |
|TXT (文字)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |1 hour (1 小時)  <br/> |
   
   **[TTL]**：將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 (**60**)、秒數 (**3600**) 等。 
    
2. 完成後，請儲存記錄。
    
3. 若要驗證 SPF 記錄，請使用其中一個 [SPF 驗證工具](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果網域已經有 SPF 記錄，請勿為 Microsoft 365 建立一個新的記錄。 而是，請將必要的 Microsoft 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。 
  
在您的 DNS 主機網站上，編輯現有 SPF 記錄或建立 SPF 的新 TXT 記錄。
  
> [!IMPORTANT]
> SPF 是設計來協助防止詐騙，但是仍有 SPF 無法防護的詐騙技術。 為了防範這些技術，設定 SPF 之後，您也應該為 Microsoft 365 設定 DKIM 和 DMARC。 若要開始使用，請參閱[在 Microsoft 365 中使用 DKIM 驗證從您的網域傳送的外寄電子郵件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。 接下來，請參閱[在 Microsoft 365 中使用 DMARC 來驗證電子郵件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。 
  
1. 在每一筆新記錄的方塊中，輸入或複製並貼上下列適用於您的情況的一組值。
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型)|**Host** (主機)|**TXT Value** (TXT 值)|**TTL**|
|TXT (文字)|@|v=spf1 include:spf.protection.outlook.de -all <br/>  建議您複製並貼上這個項目，好讓所有的間距保持正確。           |1 hour (1 小時)|
   
   **[TTL]**：將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 (**60**)、秒數 (**3600**) 等。 
    
2. 完成後，請儲存記錄。
    
3. 若要驗證 SPF 記錄，請使用其中一個 [SPF 驗證工具](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)
    
::: moniker-end

::: moniker range="o365-21vianet"

> [!IMPORTANT]
> 網域的 SPF 不得擁有一個以上的 TXT 記錄。 如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。 如果網域已經有 SPF 記錄，請勿為 Microsoft 365 建立一個新的記錄。 而是，請將必要的 Microsoft 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。 
  
在您的 DNS 主機網站上，編輯現有 SPF 記錄或建立 SPF 的新 TXT 記錄。
  
> [!IMPORTANT]
> SPF 是設計來協助防止詐騙，但是仍有 SPF 無法防護的詐騙技術。 為了防範這些技術，設定 SPF 之後，您也應該為 Microsoft 365 設定 DKIM 和 DMARC。 若要開始使用，請參閱[在 Microsoft 365 中使用 DKIM 驗證從您的網域傳送的外寄電子郵件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。 接下來，請參閱[在 Microsoft 365 中使用 DMARC 來驗證電子郵件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。 
  
1. 在每一筆新記錄的方塊中，輸入或複製並貼上下列適用於您的情況的一組值。
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型)|**Host** (主機)|**TXT Value** (TXT 值)|**TTL**|
|TXT (文字)|@|v=spf1 include:spf.protection.partner.outlook.cn -all> [!NOTE]> 建議您複製並貼上這個項目，好讓所有的間距保持正確。           |1 hour (1 小時)|
   
   **[TTL]**：將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 (**60**)、秒數 (**3600**) 等。 
    
2. 完成後，請儲存記錄。
    
3. 若要驗證 SPF 記錄，請使用其中一個 [SPF 驗證工具](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)
    
::: moniker-end

## <a name="add-two-srv-records"></a>新增兩筆 SRV 記錄
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

您將會在 DNS 主機網站上建立兩筆新的 SRV 記錄，通常是一次建立一筆。 也就是說，在網站新增第一個 SRV 記錄之後，選擇建立另一個 SRV 記錄。
  
1. 在每一筆新記錄的方塊中，輸入或複製並貼上下列值。 **(當您的 DNS 主機沒有所有這些內容做為個別欄位時，請參閱下列附註來建立 SRV 記錄。)**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型) <br/> |**Name** (名稱) <br/> |**Target** (目標) <br/> |**Protocol** (通訊協定) <br/> |**Service** (服務) <br/> |**Priority** (優先順序) <br/> |**Weight** (權數) <br/> |**Port** (連接埠) <br/> |**TTL** <br/> |
|SRV (Service) (SRV (服務))  <br/> |@  <br/> (如果不允許使用 @，則保留空白)  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 小時  <br/> |
|SRV (Service) (SRV (服務))  <br/> |@  <br/> (如果不允許使用 @，則保留空白)  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 小時  <br/> |
   
  > [!NOTE]
  >  **[Name]** (名稱)：如果您的 DNS 主機不允許將此設定為 **@**，請保留空白。 ** 只有當您的 DNS 主機的服務和通訊協定值有不同的欄位時，才能使用此方法。 否則，請參閱下列服務和通訊協定附註。 

>  **[Service]** (服務) 和 **[Protocol]** (通訊協定)：如果您的 DNS 主機不提供這些用於 SRV 記錄的欄位，您必須指定 **[Service]** (服務) 和 **[Protocol]** (通訊協定) 值做為記錄的 **[Name]** (名稱) 值。 (附註：視您的 DNS 主機而定，**[Name]** (名稱) 欄位可能會是其他名稱，例如：**[Host]** (主機)、**[Hostname]** (主機名稱) 或 **[Subdomain]** (子網域)。) 若要設定合併值，您需建立一個字串，並用點分隔值。  例如：**Name**: _sip._tls 

>  **[Priority]** (優先順序)、**[Weight]** (權重) 和 **[Port]** (連接埠)：如果您的 DNS 主機不提供這些用於 SRV 記錄的欄位，您必須將它們指定為記錄的 **[Target]** (目標) 值。 (附註：視您的 DNS 主機而定，**[Target]** (目標) 欄位可能會是其他名稱，例如：**[Content]** (內容)、**[IP Address]** (IP 位址) 或 **[Target Host]** (目標主機)。) 若要設定合併值，您需建立一個字串，並用空格和點結尾來分隔值。 這些值必須按照以下列順序：Priority、Weight、Port、Target。 例如：**[Target]** (目標)：100 1 443 sipdir.online.lync.com。 

>  **[Priority]** (優先順序)、**[Weight]** (權重) 和 **[Port]** (連接埠) 的變化：部分 DNS 主機會個別提供某些 (並非全部) 必要欄位。 針對這些 DNS 主機網站，請為記錄的 **[Target]** (目標)值依次指定未個別顯示為合併字串的值。 (附註：視您的 DNS 主機而定，**[Target]** (目標) 欄位可能會是其他名稱，例如：**[Content]** (內容)、**[IP Address]** (IP 位址) 或 **[Target Host]** (目標主機)。) 若要設定合併值，請為個別顯示的欄位建立一個字串，並用空格來分隔值。 這些值必須按照順序**，忽略具有個別欄位的值：Priority、Weight、Port、Target。 例如，如果 [Priority] (優先順序) 有個別的欄位，只要串連 [Weight] (權重)、[Port] (連接埠) 及 [Target] (目標) 值即可：**[Target]** (目標)：1 443 sipdir.online.lync.com 

> **[TTL]**：將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 (**60**)、秒數 (**3600**) 等。 
  
2. 完成後，請儲存記錄。
    
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
::: moniker-end


::: moniker range="o365-germany"

您將會在 DNS 主機網站上建立兩筆新的 SRV 記錄，通常是一次建立一筆。 也就是說，在網站新增第一個 SRV 記錄之後，選擇建立另一個 SRV 記錄。
  
1. 在每一筆新記錄的方塊中，輸入或複製並貼上下列值。 **(當您的 DNS 主機沒有所有這些內容做為個別欄位時，請參閱下列附註來建立 SRV 記錄。)**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型) <br/> |**Name** (名稱) <br/> |**Target** (目標) <br/> |**Protocol** (通訊協定) <br/> |**Service** (服務) <br/> |**Priority** (優先順序) <br/> |**Weight** (權數) <br/> |**Port** (連接埠) <br/> |**TTL** <br/> |
|SRV (Service) (SRV (服務))  <br/> |@  <br/> (如果不允許使用 @，則保留空白)  <br/> |sipdir.online.lync.de  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 小時  <br/> |
|SRV (Service) (SRV (服務))  <br/> |@  <br/> (如果不允許使用 @，則保留空白)  <br/> |sipfed.online.lync.de  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 小時  <br/> |
   
 > [!NOTE]
 >  **[Name]** (名稱)：如果您的 DNS 主機不允許將此設定為 **@**，請保留空白。 ** 只有當您的 DNS 主機的服務和通訊協定值有不同的欄位時，才能使用此方法。 否則，請參閱下列服務和通訊協定附註。 

>  **[Service]** (服務) 和 **[Protocol]** (通訊協定)：如果您的 DNS 主機不提供這些用於 SRV 記錄的欄位，您必須指定 **[Service]** (服務) 和 **[Protocol]** (通訊協定) 值做為記錄的 **[Name]** (名稱) 值。 (附註：視您的 DNS 主機而定，**[Name]** (名稱) 欄位可能會是其他名稱，例如：**[Host]** (主機)、**[Hostname]** (主機名稱) 或 **[Subdomain]** (子網域)。) 若要設定合併值，您需建立一個字串，並用點分隔值。 >  例如：**Name**: _sip._tls 

>  **[Priority]** (優先順序)、**[Weight]** (權重) 和 **[Port]** (連接埠)：如果您的 DNS 主機不提供這些用於 SRV 記錄的欄位，您必須將它們指定為記錄的 **[Target]** (目標) 值。 (附註：視您的 DNS 主機而定，**[Target]** (目標) 欄位可能會是其他名稱，例如：**[Content]** (內容)、**[IP Address]** (IP 位址) 或 **[Target Host]** (目標主機)。) 若要設定合併值，您需建立一個字串，並用空格和點結尾來分隔值。 這些值必須按照以下列順序：Priority、Weight、Port、Target。 >  例如：**[Target]** (目標)：100 1 443 sipdir.online.lync.com。 

>  **[Priority]** (優先順序)、**[Weight]** (權重) 和 **[Port]** (連接埠) 的變化：部分 DNS 主機會個別提供某些 (並非全部) 必要欄位。 針對這些 DNS 主機網站，請為記錄的 **[Target]** (目標)值依次指定未個別顯示為合併字串的值。 (附註：視您的 DNS 主機而定，**[Target]** (目標) 欄位可能會是其他名稱，例如：**[Content]** (內容)、**[IP Address]** (IP 位址) 或 **[Target Host]** (目標主機)。) 若要設定合併值，請為個別顯示的欄位建立一個字串，並用空格來分隔值。 這些值必須按照順序**，忽略具有個別欄位的值：Priority、Weight、Port、Target。 >  例如，如果 [Priority] (優先順序) 有個別的欄位，只要串連 [Weight] (權重)、[Port] (連接埠) 及 [Target] (目標) 值即可：**[Target]** (目標)：1 443 sipdir.online.lync.de 

>  **[TTL]**：將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 (**60**)、秒數 (**3600**) 等。 
  
2. 完成後，請儲存記錄。
    
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
::: moniker-end


::: moniker range="o365-21vianet"

您將會在 DNS 主機網站上建立兩筆新的 SRV 記錄，通常是一次建立一筆。 也就是說，在網站新增第一個 SRV 記錄之後，選擇建立另一個 SRV 記錄。
  
1. 在每一筆新記錄的方塊中，輸入或複製並貼上下列值。 **(當您的 DNS 主機沒有所有這些內容做為個別欄位時，請參閱下列附註來建立 SRV 記錄。)**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型) <br/> |**Name** (名稱) <br/> |**Target** (目標) <br/> |**Protocol** (通訊協定) <br/> |**Service** (服務) <br/> |**Priority** (優先順序) <br/> |**Weight** (權數) <br/> |**Port** (連接埠) <br/> |**TTL** <br/> |
|SRV (Service) (SRV (服務))  <br/> |@  <br/> (如果不允許使用 @，則保留空白)  <br/> |sipdir.online.partner.lync.cn  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 小時  <br/> |
|SRV (Service) (SRV (服務))  <br/> |@  <br/> (如果不允許使用 @，則保留空白)  <br/> |sipfed.online.partner.lync.cn  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 小時  <br/> |
   
 > [!NOTE]
 >  **[Name]** (名稱)：如果您的 DNS 主機不允許將此設定為 **@**，請保留空白。 ** 只有當您的 DNS 主機的服務和通訊協定值有不同的欄位時，才能使用此方法。 否則，請參閱下列服務和通訊協定附註。 

>  **[Service]** (服務) 和 **[Protocol]** (通訊協定)：如果您的 DNS 主機不提供這些用於 SRV 記錄的欄位，您必須指定 **[Service]** (服務) 和 **[Protocol]** (通訊協定) 值做為記錄的 **[Name]** (名稱) 值。 (附註：視您的 DNS 主機而定，**[Name]** (名稱) 欄位可能會是其他名稱，例如：**[Host]** (主機)、**[Hostname]** (主機名稱) 或 **[Subdomain]** (子網域)。) 若要設定合併值，您需建立一個字串，並用點分隔值。 >  例如：**Name**: _sip._tls 

>  **[Priority]** (優先順序)、**[Weight]** (權重) 和 **[Port]** (連接埠)：如果您的 DNS 主機不提供這些用於 SRV 記錄的欄位，您必須將它們指定為記錄的 **[Target]** (目標) 值。 (附註：視您的 DNS 主機而定，**[Target]** (目標) 欄位可能會是其他名稱，例如：**[Content]** (內容)、**[IP Address]** (IP 位址) 或 **[Target Host]** (目標主機)。) 若要設定合併值，您需建立一個字串，並用空格和點結尾來分隔值。 這些值必須按照以下列順序：Priority、Weight、Port、Target。 >  例如：**[Target]** (目標)：100 1 443 sipdir.online.partner.lync.cn。 

>  **[Priority]** (優先順序)、**[Weight]** (權重) 和 **[Port]** (連接埠) 的變化：部分 DNS 主機會個別提供某些 (並非全部) 必要欄位。 針對這些 DNS 主機網站，請為記錄的 **[Target]** (目標)值依次指定未個別顯示為合併字串的值。 (附註：視您的 DNS 主機而定，**[Target]** (目標) 欄位可能會是其他名稱，例如：**[Content]** (內容)、**[IP Address]** (IP 位址) 或 **[Target Host]** (目標主機)。) 若要設定合併值，請為個別顯示的欄位建立一個字串，並用空格來分隔值。 這些值必須按照順序**，忽略具有個別欄位的值：Priority、Weight、Port、Target。 >  例如，如果 [Priority] (優先順序) 有個別的欄位，只要串連 [Weight] (權重)、[Port] (連接埠) 及 [Target] (目標) 值即可：**[Target]** (目標)：1 443 sipdir.online.partner.lync.cn 

>  **[TTL]**：將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 (**60**)、秒數 (**3600**) 等。 
  
2. 完成後，請儲存記錄。
    
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
::: moniker-end

## <a name="more-about-updating-dns-records"></a>深入了解 DNS 記錄更新
<a name="BKMK_MoreAbout"> </a>

 **如果您知道如何在網域的 DNS 主機更新 DNS 記錄**，請使用 Microsoft 365 DNS 值來編輯網域 DNS 主機中的記錄，例如設定 MX 記錄或 SPF 記錄。 [遵循以下步驟](../get-help-with-domains/information-for-dns-records.md)，找到要使用的特定值，或者在逐步操作時在網域設定精靈中查看。
  
 **如果您需要一些協助以了解如何新增所需的 DNS 記錄**，請參閱[設定您的網域 (特定主機指示)](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions?view=o365-worldwide) (部分機器翻譯)，但是先[收集建立 Microsoft 365 DNS記錄所需的資訊](../get-help-with-domains/information-for-dns-records.md) (部分機器翻譯)。 然後使用本主題中的一般步驟來設定網域的 DNS 記錄，這樣您就可以將網域與 Microsoft 365 服務 (例如電子郵件) 搭配使用。
  
 **如果您的網站未搭配自訂網域**，您可以讓 Microsoft 365 來設定及管理網域的 DNS 記錄，而不是自行執行所有設定。 深入了解在 Microsoft 365 中[設定和管理自訂網域的 DNS 記錄的兩種選項](https://support.office.com/article/5980474a-097f-4f21-a864-21245314957f.aspx) (部分機器翻譯)。 
  

