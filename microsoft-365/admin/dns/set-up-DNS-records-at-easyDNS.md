---
title: 在 easyDNS 建立 Office 365 的 DNS 記錄
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 Skype for Business Online，並在 easyDNS 其他服務的 DNS 記錄。
ms.openlocfilehash: f55f39f36b8abaee2d500c87ccf1e0089caecc9d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251724"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a>在 easyDNS 建立 Office 365 的 DNS 記錄

[檢查網域常見問題集](../setup/domains-faq.md)找不到您要尋找。 
  
您將需要將所有的下列 DNS 記錄，在您的註冊機構網站新增至郵件路由傳送至 Office 365，您的網域用於 Teams 與 Skype for Business，依此類推。
  
附註： SRV 記錄不目前在所有的 Dns 服務套件。 您可能需要升級至較高的服務層級與 easyDNS 新增所需的商務用 Office 365 Skype SRV 記錄。
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>驗證您擁有網域的 TXT 記錄

1. 移至 [[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)和記錄檔，使用您的認證。 
    
2. 在**所有網域**標題下，選取 [ **dns。**
    
3. [ **TXT 記錄**] 標題下，選取 [編輯] 按鈕 （扳手圖示）。 
    
4. 在 [文字] 欄位中輸入下列記錄：
    
    |**Host (主機)**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS = msXXXXXXXX （使用提供給您在系統管理中心的網域] 頁面上的參數值）  <br/> |
   
5. 選取 [**下一步**]。 
    
6. 請檢查以確認該記錄是正確的然後再選取 [ **CONFIRM**。 
    
7. 請稍候幾分鐘再繼續進行，以便您剛剛建立的記錄可以後於網際網路和 Office 365 所偵測到。
    
8. Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
    
9. 在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。
    
10. 在 [**網域**] 頁面上，選取您要驗證的網域。 
    
11. 在 [**安裝**] 頁面上，選取 [**啟動安裝程式。**
    
12. 在 [**驗證網域**] 頁面上，選取 [**驗證**]。 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a>新增 MX 記錄以將電子郵件路由傳送到 Office 365

1. 移至 [[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)和記錄檔，使用您的認證。 
    
2. 在**所有網域**標題下，選取 [ **dns。**
    
3. 在**MX 記錄**標題下，選取 [編輯] 按鈕 （扳手圖示）。 
    
4. 在 [文字] 欄位中輸入下列記錄：
    
    |**郵件的區域**|**郵件伺服器**|**依慣用順序排列**|
    |:-----|:-----|:-----|
    |@  <br/> |\<網域金鑰\>。 mail.protection.outlook.com (取得您\<網域金鑰\>從管理中心的網域] 頁面上的值)  <br/> |0  <br/> |
   
2. 如果您想要儲存備份的用途您其他的 MX 記錄，請將其複製下某處。 才可繼續，移除所有其他的 MX 記錄在這裡。
    
5. 選取 [**下一步**]。 
    
6. 請檢查以確認該記錄是正確的然後再選取 [ **CONFIRM**。 
    
## <a name="add-the-required-cname-records"></a>新增所需的 CNAME 記錄

1. 移至 [[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)和記錄檔，使用您的認證。 
    
2. 在**所有網域**標題下，選取 [ **dns。**
    
3. 在**CNAME/別名記錄**標題下，選取 [編輯] 按鈕 （扳手圖示）。 
    
4. 在 [文字] 欄位中輸入下列記錄：


    |**主應用程式**|**地址 (的結尾必須是 「。 」)**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com。  <br/> |
    |sip  <br/> |sipdir.online.lync.com>。  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com>。  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net>。  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> |
   
5. 選取 [**下一步**]。 
    
6. 請檢查以確認該記錄是正確的然後再選取 [ **CONFIRM**。 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>新增 SPF 的 TXT 記錄以協助防範垃圾郵件

1. 移至 [[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)和記錄檔，使用您的認證。 
    
2. 在**所有網域**標題下，選取 [ **dns。**
    
3. [ **TXT 記錄**] 標題下，選取 [編輯] 按鈕 （扳手圖示）。 
    
4. 在 [文字] 欄位中輸入下列記錄：
    
    |**Host (主機)**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. 選取 [**下一步**]。 
    
6. 請檢查以確認該記錄是正確的然後再選取 [ **CONFIRM**。 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>新增兩筆 Office 365 所需的 SRV 記錄

附註： SRV 記錄不目前在 easyDNS' 網域加上的服務層級。 您可能需要升級至較高的服務層級使用 Dns 來新增 SRV 記錄 
  
1. 移至 [[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)和記錄檔，使用您的認證。 
    
2. 在**所有網域**標題下，選取 [ **dns。**
    
3. 在**SRV 記錄**標題下，選取 [編輯] 按鈕 （扳手圖示）。 
    
4. 在 [文字] 欄位中輸入下列記錄：
    
    |**服務**|**通訊協定**|**主應用程式**|**PRI**|**WGT**|**連接埠**|**目標 (的結尾必須是 「。 」)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com>。  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> |1800  <br/> |
   
5. 選取 [**下一步**]。 
    
6. 請檢查以確認該記錄是正確的然後再選取 [ **CONFIRM**。 
    

