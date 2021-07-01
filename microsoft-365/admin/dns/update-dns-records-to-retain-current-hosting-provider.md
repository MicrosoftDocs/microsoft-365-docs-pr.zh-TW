---
title: 更新 DNS 記錄以便向目前的主機服務提供者保留網站
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: 瞭解如何將流量路由傳送至 Microsoft 所主控的現有公用網站（如果您已將 Microsoft 設定為管理自訂網域的 DNS 記錄）。
ms.openlocfilehash: d54aa4583862ce19907a3b8494a333bbb925e436
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228120"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>更新 DNS 記錄以便向目前的主機服務提供者保留網站

 [！附注]**如果您在 DNS 主機服務提供者管理您網域的 Microsoft 記錄**，您不需要擔心本主題中的步驟。 您的網站會留在原處，使用者仍然可以存取。 
  
 **如果 microsoft 管理您的 DNS 記錄**，若要將流量路由傳送至 microsoft 所主控的現有公用網站，將您的網域新增至 microsoft 之後，請執行下列操作： 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>更新 Microsoft 365 系統管理中心中的 DNS 記錄
1. 在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。

1. 在 [ **網域** ] 頁面上，選取網域，然後選擇 [ **DNS 記錄**]。

1. 選取 [ **+ Add record** ]，然後輸入下列內容： 
    
   - 輸入 **文字** ： **(位址)**
    
   - 針對 [ **主機名稱或別名**]，輸入下列專案： **@**
    
   - 在 [ **IP 位址**] 中，輸入目前主控 (之網站的靜態 IP 位址（例如，172.16.140.1) ）。 
    
   This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website. 
    
1. 選取 ****[儲存]。 
    
此外，您還可以建立 CNAME 記錄，協助客戶找到您的網站。
  
1. 選取 [ **+ Add record** ]，然後輸入下列內容： 
    
   - 輸入 **類型** ： **CNAME (別名)**
    
   - 針對 [ **主機名稱或別名**]，輸入下列： **www**
    
   - 在 [ **指向位址**] 中，為您的網站輸入完整功能變數名稱 (FQDN)  (例如，contoso.com) 。 
    
2. 選取 ****[儲存]。 
    
最後，請執行下列動作：
  
[更新您網域的 NS 記錄](../setup/add-domain.md) ，以指向 Microsoft。 
  
當 NS 記錄更新為指向 Microsoft 時，您的網域就會全部設定。 電子郵件會路由傳送至 Microsoft，而您的網站位址的流量將繼續前往您目前的網站主機。
