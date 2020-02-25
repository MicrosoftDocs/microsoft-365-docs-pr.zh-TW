---
title: 在 Wix 建立 DNS 記錄，Office 365
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 Skype for Business Online，並在 Wix 其他服務的 DNS 記錄。
ms.openlocfilehash: 43d2f2417153dd0c848c33736733237b1681c02c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239916"
---
# <a name="create-dns-records-at-wix-for-office-365"></a>在 Wix 建立 DNS 記錄，Office 365

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
如果 Wix 是您 DNS 主機服務提供者，請遵循本篇文章以驗證您的網域和設定 DNS 記錄的電子郵件、 Skype for Business Online 等等中的步驟。
  
以下是要新增的主要記錄。 
  
- [新增 TXT 記錄以供驗證](#add-a-txt-record-for-verification)。
    
- [新增 MX 記錄，讓您網域的電子郵件將送至 Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)。
    
- [新增第五筆 CNAME 記錄，所需的 Office 365](#add-the-five-cname-records-that-are-required-for-office-365)。
    
- [新增以協助防範垃圾郵件的 SPF TXT 記錄](#add-a-txt-record-for-spf-to-help-prevent-email-spam)。
    
- [新增兩個 SRV 記錄，所需的 Office 365](#add-the-two-srv-records-that-are-required-for-office-365)。
    
在 Wix 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務。
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>新增 TXT 記錄以供驗證
<a name="BKMK_txt"> </a>

在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。
  
> [!NOTE]
> 這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。 
  
1. 若要開始，使用[這個連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)移至您在 Wix 的網域頁面。 You'll be prompted to log in first.
    
2. 在 [**我的網域**] 頁面上，在 [**進階**] 區域中，選取 [**編輯 DNS** ] 按鈕。 
    
3. DNS 編輯器的 [ **TXT （文字）** 列中，選取 [ **+ 新增另一個**。 
    
4. In the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Host Name** <br/> |**TXT Value** <br/> |**TTL** <br/> |
|自動填入資料  <br/> |MS=ms *XXXXXXXX*  <br/> **附註：** 這是範例。 Use your specific **Destination or Points to Address** value here, from the table in Office 365.  [How do I find this?](../get-help-with-domains/information-for-dns-records.md)|1 Hour <br/> |          |
   
5. 選取頂端的 [DNS 編輯器**儲存 DNS** ] 按鈕。 
    
6. 繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。
    
2. 在 [**網域**] 頁面上，選取您要驗證的網域。 
  
  
3. 在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。
   
  
4. 在 [**驗證網域**] 頁面上，選取 [**驗證**]。
    
    
  
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365
<a name="BKMK_mx"> </a>

1. 若要開始，使用[這個連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)移至您在 Wix 的網域頁面。 You'll be prompted to log in first.
    
2. 在 [**我的網域**] 頁面上，在 [**信箱**] 區域中，選取 [**設定您的 MX 記錄**連結。 
    
3. 選擇 [**其他**從**您的電子郵件提供者**] 下拉式清單。 
    
4. 選取 [ **+ 新增其他**]。
    
5. 在新記錄方塊中，輸入或複製並貼上下表中的值：
    
|**Host Name**|**Points to **|**Priority** (優先順序)|**TTL**|
|:-----|:-----|:-----|:-----|
|自動填入資料 <br/> | *\<網域金鑰\>*  .mail.protection.outlook.com  <br/> **附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。   [How do I find this?](../get-help-with-domains/information-for-dns-records.md) |0  <br/> 如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83) | 1 Hour|
   
6. 如果沒有列出任何其他 MX 記錄，逐一刪除。 
    
7. 選取 [確定]****。
    
8. 在 [確認] 對話方塊中，選取 **[確定]**。
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>新增 Office 365 所需的五筆 CNAME 記錄
<a name="BKMK_cname"> </a>

1. 若要開始，使用[這個連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)移至您在 Wix 的網域頁面。 You'll be prompted to login first.
    
2. 在 [**我的網域**] 頁面上，在 [**進階**] 區域中，選取 [**編輯 DNS** ] 按鈕。 
    
3. 在每一筆 CNAME 記錄的 DNS 編輯器 [ **CNAME （別名）** ] 列中，選取 [ **+ 新增另一個**。 
    
4. 在新記錄方塊中，輸入或複製並貼上下表中的值：
    
|**Host Name**|**Points to **|**TTL**|
|:-----|:-----|:-----|
|autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 Hour  <br/> |
|sip  <br/> |sipdir.online.lync.com>  <br/> |1 Hour <br/> |
|lyncdiscover  <br/> |webdir.online.lync.com>   <br/> |1 Hour  <br/> |
|enterpriseregistration  <br/> |enterpriseregistration.windows.net>  <br/> |1 小時 <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Hour  <br/> |
   
5. 選取頂端的 [DNS 編輯器**儲存 DNS** ] 按鈕。 
    
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.  
  
1. 若要開始，使用[這個連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)移至您在 Wix 的網域頁面。 You'll be prompted to log in first.
    
2. 在 [**我的網域**] 頁面上，在 [**進階**] 區域中，選取 [**編輯 DNS** ] 按鈕。 
    
3. DNS 編輯器的 [ **TXT （文字）** 列中，選取 [ **+ 新增另一個**。 
    
4. 在新記錄方塊中，輸入或複製並貼上下表中的值：
    
|**Host Name**|**TXT Value**|**TTL**|
|:-----|:-----|:-----|
|[讓此值留成空白]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。<br/> |TXT  <br/> | 1 Hour |
   
5. 選取頂端的 [DNS 編輯器**儲存 DNS** ] 按鈕。 
    
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>新增兩筆 Office 365 所需的 SRV 記錄
<a name="BKMK_srv"> </a>

1. 若要開始，使用[這個連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)移至您在 Wix 的網域頁面。 You'll be prompted to log in first.
    
2. 在 [**我的網域**] 頁面上，在 [**進階**] 區域中，選取 [**編輯 DNS** ] 按鈕。 
    
3. 在 [DNS 編輯器] 的 [ **SRV** ] 列中，選取 [ **+ 新增另一個**。 
    
4. 在新記錄方塊中，輸入或複製並貼上下表中的值：
    
|**服務**|**通訊協定**|**Name**|**Weight**|**Port**|**Target**|**Priority** (優先順序)|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|sip  |tls  |自動填入資料 |1  |443   |sipdir.online.lync.com> |100 |1 Hour |
|sipfed|tcp |自動填入資料|1 |5061 |sipfed.online.lync.com>|100 | 1 Hour |
   
5. 選取頂端的 [DNS 編輯器**儲存 DNS** ] 按鈕。 
    
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
> [!NOTE]
>  DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。 
  

