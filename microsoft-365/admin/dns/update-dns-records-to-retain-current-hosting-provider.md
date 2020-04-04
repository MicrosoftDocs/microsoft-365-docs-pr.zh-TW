---
title: 更新 DNS 記錄以便向目前的主機服務提供者保留網站
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: 瞭解如何將流量路由傳送至 Office 365 外部所主控的現有公用網站（如果您已將 Office 365 設定為管理自訂網域的 DNS 記錄）。
ms.openlocfilehash: 3e71925f9b50e5520bd383aa5318db513202f6ec
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142536"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>更新 DNS 記錄以便向目前的主機服務提供者保留網站

 在**您的 DNS 主機服務提供者處管理網域的 Office 365 記錄**時，您不需要擔心本主題中的步驟。 您的網站會留在原處，使用者仍然可以存取。 
  
 **如果 office 365 管理您的 DNS 記錄**，若要將流量路由傳送至 office 365 以外所主控的現有公用網站，請在將您的網域新增至 office 365 後，執行下列動作： 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心更新 DNS 記錄
1. 在系統管理中心中，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。

2. 在 [**網域**] 頁面的 [網域] 清單中，選取您要用於網站的網域，然後選取 [管理] 窗格中的 [ **DNS 設定**]。 
    
3. 選取 [ **+ 新的自訂記錄**]，然後輸入下列內容： 
    
  - 針對**DNS**輸入： **A （位址）**
    
  - 針對 [**主機名稱或別名**]，輸入下列專案：**@**
    
  - 在 [ **IP 位址**] 中，輸入目前所主控之網站的靜態 IP 位址（例如，172.16.140.1）。 
    
    This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website. 
    
3. 選取 [儲存]****。 
    
此外，您還可以建立 CNAME 記錄，協助客戶找到您的網站。
  
1. 選取 [ **+ 新的自訂記錄**]，然後輸入下列內容： 
    
  - 針對**DNS 類型**輸入： **CNAME （別名）**
    
  - 針對 [**主機名稱或別名**]，輸入下列： **www**
    
  - 在 [**指向位址**] 中，輸入您網站的完整功能變數名稱（FQDN）（例如，contoso.com）。 
    
2. 選取 [儲存]****。 
    
最後，請執行下列動作：
  
[更新網域的 NS 記錄](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx)，使它指向 Office 365。 
  
當 NS 記錄已更新成指向 Office 365 時，表示您的網域已經準備就緒。電子郵件會轉至 Office 365，而您網址的流量會繼續流向您目前的網站主機。
 
