---
title: 運用任何網域註冊機構變更名稱伺服器以設定 Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 了解如何新增及設定 Office 365 中的網域，以便服務電子郵件與 Skype for Business Online 使用您自己的網域名稱。
ms.custom: okr_smb
ms.openlocfilehash: 3030fc33a6d528fd6cb4e97c27cdbb7c251e9a97
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251670"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a>運用任何網域註冊機構變更名稱伺服器以設定 Office 365

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
[設定您的網域 （主機專用指示）](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)先檢查以查看是否有您的註冊機構的指示。 
  
您可以依照這些指示，在 Office 365 新增並設定網域，好讓電子郵件和商務用 Skype Online 等服務能夠使用您自己的網域名稱。 做法是驗證您的網域，然後將網域的名稱伺服器改為 Office 365，以便設定正確的 DNS 記錄。 如果下列陳述式描述您的情況，請遵循下列步驟：
  
- 您有自己的網域，而且希望將它設定為搭配 Office 365 使用。
    
- 您要讓 Office 365 為您管理 DNS 記錄 (您可以視需要[管理自己的 DNS 記錄](../setup/add-domain.md))。
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>新增 TXT 或 MX 記錄以供驗證
<a name="BKMK_verify"> </a>

> [!NOTE]
> 您只能建立這些記錄的其中一種。TXT 是慣用的記錄類型，但部分 DNS 主機服務提供者不支援，在這種情況下，您可以改為建立 MX 記錄。 
  
在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。
  
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
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 ( **60** )、秒數 ( **3600** ) 等。  <br/> |
   
**如果您建立 MX 記錄，請使用以下值：**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Record Type** (記錄類型)|**Alias** (別名) 或 **Host Name** (主機名稱)|**Value** (值)|**Priority** (優先順序)|**TTL**|
|MX|輸入 **@** 或您的網域名稱。 |MS=ms *XXXXXXXX* > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |**優先順序**，以避免發生衝突，以用於郵件流程的 MX 記錄，使用比優先順序較低的優先順序的任何現有的 MX 記錄。 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](../setup/domains-faq.md#what-is-mx-priority) |將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 ( **60** )、秒數 ( **3600** ) 等。 |
   
### <a name="save-the-record"></a>儲存記錄

Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  

1. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。
    
2. 在 [**網域**] 頁面上，選取您要驗證的網域。 
    
  
3. 在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。
 
    
  
4. 在 [**驗證網域**] 頁面上，選取 [**驗證**]。
    
    
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>變更您網域的名稱伺服器 (NS) 記錄
<a name="BKMK_nameservers"> </a>

當您在 Office 365 中進行到網域設定精靈的最後一個步驟時，還剩下一項工作需要完成。若要搭配 Office 365 服務 (例如電子郵件) 設定網域，請在網域註冊機構，將網域的名稱伺服器 (或 NS) 記錄改為指向 Office 365 主要和次要名稱伺服器。由於 Office 365 負責主控您的 DNS，因此會自動為您設定服務所需的 DNS 記錄。 您可以遵循以下步驟自行更新名稱伺服器記錄 (網域註冊機構可能會在他們網站上的說明內容中提供步驟)。如果您不熟悉 DNS，請連絡網域註冊機構的支援人員。

::: moniker range="o365-worldwide"
  
若要自行在網域註冊機構的網站變更您網域的名稱伺服器，請遵循這些步驟：
  
1. 在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。
    
2. 建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，以符合下列值：
    
|||
|:-----|:-----|
|第一個名稱伺服器  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Second nameserver (第二個名稱伺服器)  <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > 您應該使用至少兩個名稱伺服器記錄。 如果沒有列出任何其他名稱伺服器，您可以刪除，或將它們變更為**ns3.bdm.microsoftonline.com**和**ns4.bdm.microsoftonline.com**。 
  
3. 儲存變更。
    
> [!CAUTION]
> 當您將網域的 NS 記錄改為指向 Office 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。如果您跳過精靈的任一步驟 (例如新增電子郵件地址)，或者如果您將網域用於部落格、購物車或其他服務，就必須額外採取其他步驟才行。否則這項變更可能會使服務停擺 (例如，無法存取電子郵件或是您的目前網站)。 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. 在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。
    
2. 建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，以符合下列值：
    
|||
|:-----|:-----|
|第一個名稱伺服器  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|Second nameserver (第二個名稱伺服器)  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > 您應該使用至少兩個名稱伺服器記錄。 如果沒有列出任何其他名稱伺服器，您可以刪除，或將它們變更為**ns3.dns.partner.microsoftonline.cn**和**ns4.dns.partner.microsoftonline.cn**。 
  
3. 儲存變更。
    
> [!CAUTION]
> 當您變更您網域的 NS 記錄改為指向 Office 365 operated by 21Vianet 名稱伺服器時，會影響所有目前與您的網域相關聯的服務。 如果您跳過精靈的任一步驟 (例如新增電子郵件地址)，或者如果您將網域用於部落格、購物車或其他服務，就必須額外採取其他步驟才行。 否則這項變更可能會使服務停擺 (例如，無法存取電子郵件或是您的目前網站)。 

::: moniker-end
  
舉例來說，如果要主控電子郵件和網站，必須另外執行下列步驟：
  
- 在變更名稱伺服器 (NS) 記錄之前，將所有使用您網域的電子郵件地址全部移到 Office 365。
    
- 您要新增一個目前搭配網站位址 (例如 www.fourthcoffee.com) 使用的網域嗎？ 當您新增網域，以保留其主控網站主控現在讓您變更網域的 NS 記錄改為指向 Office 365 之後人員還可以對網站取得的網站時，您可以採取以下步驟。

1. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。

3. 在 [網域] 頁面上，選取網域。

4. **DNS 設定**] 下選取 [**自訂記錄**，，，然後選擇 [**新增自訂記錄**。

5. 選取您想要新增的 DNS 記錄類型，然後輸入新記錄的資訊。

6. 選取 **[儲存]**。
    
> [!NOTE]
> 您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。 
  

