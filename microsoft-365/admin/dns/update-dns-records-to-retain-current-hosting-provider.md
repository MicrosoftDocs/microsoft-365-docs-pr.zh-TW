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
description: 了解如何將流量路由至 Office 365 外部架設的現有公用網站，如果您已經設定 Office 365 來管理您的自訂網域的 DNS 記錄。
ms.openlocfilehash: b92e778fb2fe0353a0d1d6bf83a4c617ab4541e2
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362408"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>更新 DNS 記錄以便向目前的主機服務提供者保留網站

 **如果您管理網域的 Office 365 記錄，在您 DNS 主機服務提供者**，您不需要擔心這個主題中的步驟。 您的網站會留在原處，使用者仍然可以存取。 
  
 **如果 Office 365 管理您的 DNS 記錄**，以將流量路由傳送至您新增網域至 Office 365 之後，Office 365 外部架設的現有公用網站執行下列動作： 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心中的更新 DNS 記錄
1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

2. 在 [**網域**] 頁面清單中的網域] 中，選取您正在使用您的網站，，然後選取 [管理] 窗格中的 [ **DNS 設定**的網域。 
    
3. 選取 [ **+ 新增自訂記錄**，並輸入下列項目： 
    
  - 針對 [ **DNS 類型**]，輸入： **A （位址）**
    
  - **主機名稱或別名**，請輸入下列命令：**@**
    
  - **IP 位址**] 中，輸入您它目前主控 （例如，172.16.140.1） 的網站的靜態 IP 位址。 
    
    This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website. 
    
3. 選取 [儲存]****。 
    
此外，您還可以建立 CNAME 記錄，協助客戶找到您的網站。
  
1. 選取 [ **+ 新增自訂記錄**，並輸入下列項目： 
    
  - 針對 [ **DNS 類型**]，輸入： **CNAME （別名）**
    
  - **主機名稱或別名**，請輸入下列命令： **www**
    
  - **指向位址**，輸入您的網站 (例如，contoso.com) 的完整的網域名稱 (FQDN)。 
    
2. 選取 [儲存]****。 
    
最後，請執行下列動作：
  
[更新網域的 NS 記錄](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx)，使它指向 Office 365。 
  
當 NS 記錄已更新成指向 Office 365 時，表示您的網域已經準備就緒。電子郵件會轉至 Office 365，而您網址的流量會繼續流向您目前的網站主機。
 
