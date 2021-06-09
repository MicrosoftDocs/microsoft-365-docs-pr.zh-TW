---
title: 使用任何網域註冊機構變更名稱伺服器以設定 Microsoft 365
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 瞭解如何在 Microsoft 365 中新增及設定您的網域，以便您的服務（如電子郵件和商務用 Skype 線上）使用您自己的功能變數名稱。
ms.openlocfilehash: 7f1ade6cb3013126fb011fe9232b3b4c2e9a82d4
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683124"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>使用任何網域註冊機構變更名稱伺服器以設定 Microsoft 365

 若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。 
  
請遵循下列指示，在 Microsoft 365 中新增及設定您的網域，這樣的服務（例如電子郵件和 Teams）會使用您自己的功能變數名稱。 若要這麼做，您將會驗證您的網域，然後將網域的名稱伺服器變更為 Microsoft 365，這樣就能為您設定正確的 DNS 記錄。 如果下列語句描述您的情況，請遵循下列步驟：
  
- 您有自己的網域，且想要將其設定為搭配 Microsoft 365 使用。
    
- 您想要 Microsoft 365 管理您的 DNS 記錄。 如果您想要的話，也可以[管理自己的 DNS 記錄](../setup/add-domain.md)。
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>新增 TXT 或 MX 記錄以進行驗證

> [!NOTE]
> 您只能建立這些記錄的其中一種。TXT 是慣用的記錄類型，但部分 DNS 主機服務提供者不支援，在這種情況下，您可以改為建立 MX 記錄。 
  
在您將自己的網域用於 Microsoft 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>在 DNS 主機服務提供者的網站上，找出您可以建立新記錄的區域

1. 登入您 DNS 主機服務提供者的網站。
    
2. 選擇您的網域。
    
3. 找出可編輯網域 DNS 記錄的頁面。
    
### <a name="create-the-record"></a>建立記錄

請根據您要建立 TXT 記錄還是 MX 記錄而定，執行下列其中一項操作：
  
**如果您建立 TXT 記錄，請使用以下值：**
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型) <br/> |**Alias** (別名) 或 **Host Name** (主機名稱) <br/> |**Value** (值) <br/> |**TTL** <br/> |
|TXT  <br/> |請執行下列其中一項操作：輸入 **@** ，或是保留欄位空白，或輸入您的網域名稱。  <br/> > [!NOTE]> 不同的 DNS 主機對此欄位有不同的要求。           
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> 這是範例。 在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Microsoft 365 表格。           [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          |將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 ( **60** )、秒數 ( **3600** ) 等。  <br/> |
   
**如果您建立 MX 記錄，請使用以下值：**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型)|**Alias** (別名) 或 **Host Name** (主機名稱)|**Value** (值)|**Priority** (優先順序)|**TTL**|
|MX|輸入 **@** 或您的網域名稱。 |MS=ms *XXXXXXXX* > [!NOTE]> This is an example. 在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Microsoft 365 表格。           [如何找到呢？](../get-help-with-domains/information-for-dns-records.md)          |針對 **[Priority]** (優先順序)，為避免跟用於郵件流程的 MX 記錄發生衝突，請使用比任一現有 MX 記錄更低的優先順序。 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](../setup/domains-faq.yml) |將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 ( **60** )、秒數 ( **3600** ) 等。 |
   
### <a name="save-the-record"></a>儲存記錄

現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 365 並要求 Microsoft 365 尋找該記錄。
  
在 Microsoft 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。
  

1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。
    
2. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
  
3. 在 **[設定]** 頁面上，選取 **[開始設定]**。
 
  
4. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>變更您網域的名稱伺服器 (NS) 記錄

當您在 Microsoft 365 中取得網域安裝精靈的最後一個步驟時，您會有一個剩餘的任務。 若要使用 Microsoft 365 服務（例如電子郵件）來設定網域，您可以在網域註冊機構中變更網域的名稱伺服器 (或 NS) 記錄，以指向 Microsoft 365 的主要和次要名稱伺服器。 然後，因為 Microsoft 365 主控您的 DNS，所以會為您自動設定服務所需的 dns 記錄。 您可以遵循以下步驟 (網域註冊機構可能會在他們網站上的說明內容中提供)，自行更新名稱伺服器記錄。 如果您不熟悉 DNS，請連絡網域註冊機構的支援人員。

::: moniker range="o365-worldwide"
  
若要自行在網域註冊機構的網站變更您網域的名稱伺服器，請遵循這些步驟：
  
1. 在網域註冊機構網站上尋找區域，您可以在其中變更您網域的名稱伺服器，或是您可以使用自訂名稱伺服器的區域。
    
2. 建立名稱伺服器記錄，或編輯現有的名稱伺服器記錄，使其符合下列值：
    
|||
|:-----|:-----|
|First nameserver (第一個名稱伺服器)  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Second nameserver (第二個名稱伺服器)  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|Third nameserver (第三個名稱伺服器)  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|Fourth nameserver (第四個名稱伺服器)  <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > 最好新增四筆記錄，但如果您的註冊機構只支援二個，請新增 **ns1.bdm.microsoftonline.com** 及 **ns2.bdm.microsoftonline.com**。 
  
3. 儲存變更。
    
> [!CAUTION]
> 當您將網域的 NS 記錄變更為指向 Microsoft 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。 如果您跳過精靈的任一步驟 (例如新增電子郵件地址)，或者如果您將網域用於部落格、購物車或其他服務，就必須額外採取其他步驟才行。 否則這項變更可能會使服務停擺 (例如，無法存取電子郵件或是您的目前網站)。 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. 在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。
    
2. 建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，以符合下列值：
    
|||
|:-----|:-----|
|第一個名稱伺服器  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|Second nameserver (第二個名稱伺服器)  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > 您應該使用至少兩個名稱伺服器記錄。 如果有列出任何其他名稱伺服器，您可以將其刪除，或將其變更為 **ns3.dns.partner.microsoftonline.cn** 和 **ns4.dns.partner.microsoftonline.cn**。 
  
3. 儲存變更。
    
> [!CAUTION]
> 當您變更網域的 NS 記錄，使其指向由名稱伺服器（由您的網域所運作的 Office 365）時，所有目前與您網域相關聯的服務都會受到影響。 如果您跳過精靈的任一步驟 (例如新增電子郵件地址)，或者如果您將網域用於部落格、購物車或其他服務，就必須額外採取其他步驟才行。 否則這項變更可能會使服務停擺 (例如，無法存取電子郵件或是您的目前網站)。 

::: moniker-end
  
舉例來說，如果要主控電子郵件和網站，必須另外執行下列步驟：
  
- 變更您的 NS 記錄之前，請將使用您網域的所有電子郵件地址移 Microsoft 365。
    
- 您要新增一個目前搭配網站位址 (例如 www.fourthcoffee.com) 使用的網域嗎？ 您可以採取下列步驟，當您新增網域以保留網站主控位置的網站，讓使用者在您變更網域的 NS 記錄，以指向 Microsoft 365 之後仍可進入網站。

1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

2. 在 [ **網域** ] 頁面上，選取網域。

3. 在 [網域詳細資料] 頁面上，選取 [ **DNS 記錄** ] 索引標籤。
 
4. 選取 [ **新增記錄**]。

5. 在 [ **新增自訂 DNS 記錄** ] 窗格中，從 [ **類型** ] 下拉式清單中選取 **(位址)**。

6. 在 [ **主機名稱或別名** ] 方塊中，輸入 **@** 。

7. 在 [ **IP 位址** ] 方塊中，輸入目前所主控之網站的靜態 IP 位址。 例如，172.16.140.1。
    
> [!IMPORTANT]
>  這必須是網站的 _靜態_ ip 位址，而非 _動態_ ip 位址。 若要確定您可以取得公用網站的靜態 IP 位址，請與主控網站的網站進行核對。
   
8. 如果您想要變更記錄的 TTL 設定，請從 [ **ttl** ] 下拉式清單中選取新的時間長度。 否則，請繼續進行步驟9。
    
9. 選取 ****[儲存]。 
    
此外，您還可以建立 CNAME 記錄，協助客戶找到您的網站。
  
1.  選取 [ **新增記錄**]。

3.  在 [ **新增自訂 DNS 記錄** ] 窗格中，從 [ **類型** ] 下拉式清單中選取 [ **CNAME (別名])**。
4.  在 [ **主機名稱或別名** ] 方塊中，輸入 **www**。
5.  在 [指向 **位址** ] 方塊中，為您的網站輸入 (FQDN) 的完整功能變數名稱。 例如， **contoso.com**。
6.  如果您想要變更記錄的 TTL 設定，請從 [ **ttl** ] 下拉式清單中選取新的時間長度。 否則，請繼續進行步驟6。
7.  選取 ****[儲存]。

在將名稱伺服器記錄更新為指向 Microsoft 之後，您的網域安裝已完成。 電子郵件會路由傳送至 Microsoft，而您的網站位址的流量仍會繼續前往您目前的網站主機。 '
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。 
  
## <a name="related-content"></a>相關內容

[新增 DNS 記錄以將您的網域](create-dns-records-at-any-dns-hosting-provider.md) (文章) \
[尋找並修正新增網域或 DNS 記錄之後所發生的問題](find-and-fix-issues.md) (文章)
[管理網域](index.yml) (連結頁面)
