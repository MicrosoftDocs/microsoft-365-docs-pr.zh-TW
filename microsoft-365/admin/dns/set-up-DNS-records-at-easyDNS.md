---
title: 在 Microsoft 的 easyDNS 建立 DNS 記錄
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以供 Microsoft easyDNS。
ms.openlocfilehash: 4909a02ec56fc9720a2636e822da0339e89bccf8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645548"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>在 Microsoft 的 easyDNS 建立 DNS 記錄

如果您找不到所需的專案，[請檢查網域常見問題](../setup/domains-faq.md)。 
  
您必須在您的註冊機構網站新增下列所有 DNS 記錄，以將郵件路由傳送至 Microsoft、將您的網域用於小組和商務用 Skype，等等。
  
附注： SRV 記錄目前無法在所有 easyDNS service 套件下使用。 您可能需要使用 easyDNS 升級至較高的服務層級，以新增商務用 Skype 所需的 SRV 記錄。
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>確認您擁有包含 TXT 記錄的網域

1. 移至 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 並以您的認證登入。 
    
2. 在 [ **所有網域** ] 標題下，選取 [ **dns]。**
    
3. 在 [ **TXT 記錄** ] 標題下，選取 [編輯] 按鈕 (扳手圖示) 。 
    
4. 在 [文字] 欄位中輸入下列記錄：
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS=msXXXXXXXX (使用您在系統管理中心的 [網域] 頁面上提供的值)   <br/> |
   
5. 選取 **[下一步]**。 
    
6. 請確認記錄是否正確，然後選取 [ **確認**]。 
    
7. 請等候幾分鐘，再繼續進行，這樣您剛才建立的記錄便可以傳播到網際網路，並由 Microsoft 偵測到。
    
8. 現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。
    
9. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。
    
10. 在 **[網域]** 頁面上，選取您要驗證的網域。 
    
11. 在 [ **安裝** ] 頁面上，選取 [ **啟動安裝程式]。**
    
12. 在 **[驗證網域]** 頁面上，選取 **[驗證]**。 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>新增 MX 記錄以將電子郵件路由傳送至 Microsoft

1. 移至 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 並以您的認證登入。 
    
2. 在 [ **所有網域** ] 標題下，選取 [ **dns]。**
    
3. 在 [ **MX 記錄** ] 標題下，選取 [編輯] 按鈕 (扳手圖示) 。 
    
4. 在 [文字] 欄位中輸入下列記錄：
    
    |**區域的郵件**|**郵件伺服器**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>mail.protection.outlook.com (\<domain-key\> 從系統管理中心的 [網域] 頁面取得您的價值)   <br/> |0  <br/> |
   
2. 如果您想要儲存其他的 MX 記錄以用於備份目的，請將其複製到某個地方。 在移動之前，請在這裡移除所有其他 MX 記錄。
    
5. 選取 **[下一步]**。 
    
6. 請確認記錄是否正確，然後選取 [ **確認**]。 
    
## <a name="add-the-required-cname-records"></a>新增必要的 CNAME 記錄

1. 移至 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 並以您的認證登入。 
    
2. 在 [ **所有網域** ] 標題下，選取 [ **dns]。**
    
3. 在 [ **CNAME/別名記錄** ] 標題下，選取 [編輯] 按鈕 (扳手圖示) 。 
    
4. 在 [文字] 欄位中輸入下列記錄：


    |**主機**|**Address (必須以 "." 結尾。) **|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. 選取 **[下一步]**。 
    
6. 請確認記錄是否正確，然後選取 [ **確認**]。 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件

1. 移至 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 並以您的認證登入。 
    
2. 在 [ **所有網域** ] 標題下，選取 [ **dns]。**
    
3. 在 [ **TXT 記錄** ] 標題下，選取 [編輯] 按鈕 (扳手圖示) 。 
    
4. 在 [文字] 欄位中輸入下列記錄：
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. 選取 **[下一步]**。 
    
6. 請確認記錄是否正確，然後選取 [ **確認**]。 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>新增兩筆 Microsoft 所需的 SRV 記錄

附注： SRV 記錄目前無法用於 easyDNS ' 網域加服務層級。 您可能需要使用 easyDNS 來新增 SRV 記錄，以升級至較高的服務層級 
  
1. 移至 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 並以您的認證登入。 
    
2. 在 [ **所有網域** ] 標題下，選取 [ **dns]。**
    
3. 在 [ **SRV 記錄** ] 標題下，選取 [編輯] 按鈕 (扳手圖示) 。 
    
4. 在 [文字] 欄位中輸入下列記錄：
    
    |**服務**|**原**|**主機**|**Pri**|**WGT**|**港口**|**目標 (必須以 "." 結尾) **|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> |1800  <br/> |
   
5. 選取 **[下一步]**。 
    
6. 請確認記錄是否正確，然後選取 [ **確認**]。 
    

