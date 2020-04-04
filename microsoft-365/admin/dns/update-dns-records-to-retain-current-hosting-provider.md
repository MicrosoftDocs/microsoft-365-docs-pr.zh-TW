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
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="e9fd2-103">更新 DNS 記錄以便向目前的主機服務提供者保留網站</span><span class="sxs-lookup"><span data-stu-id="e9fd2-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="e9fd2-104">在**您的 DNS 主機服務提供者處管理網域的 Office 365 記錄**時，您不需要擔心本主題中的步驟。</span><span class="sxs-lookup"><span data-stu-id="e9fd2-104">**If you manage your domain's Office 365 records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="e9fd2-105">您的網站會留在原處，使用者仍然可以存取。</span><span class="sxs-lookup"><span data-stu-id="e9fd2-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="e9fd2-106">**如果 office 365 管理您的 DNS 記錄**，若要將流量路由傳送至 office 365 以外所主控的現有公用網站，請在將您的網域新增至 office 365 後，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e9fd2-106">**If Office 365 manages your DNS records**, to route traffic to an existing public website hosted outside of Office 365, after you add your domain to Office 365, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e9fd2-107">在 Microsoft 365 系統管理中心更新 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="e9fd2-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="e9fd2-108">在系統管理中心中，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e9fd2-108">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="e9fd2-109">在 [**網域**] 頁面的 [網域] 清單中，選取您要用於網站的網域，然後選取 [管理] 窗格中的 [ **DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="e9fd2-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="e9fd2-110">選取 [ **+ 新的自訂記錄**]，然後輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="e9fd2-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="e9fd2-111">針對**DNS**輸入： **A （位址）**</span><span class="sxs-lookup"><span data-stu-id="e9fd2-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="e9fd2-112">針對 [**主機名稱或別名**]，輸入下列專案：**@**</span><span class="sxs-lookup"><span data-stu-id="e9fd2-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="e9fd2-113">在 [ **IP 位址**] 中，輸入目前所主控之網站的靜態 IP 位址（例如，172.16.140.1）。</span><span class="sxs-lookup"><span data-stu-id="e9fd2-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="e9fd2-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span><span class="sxs-lookup"><span data-stu-id="e9fd2-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="e9fd2-116">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e9fd2-116">Select **Save**.</span></span> 
    
<span data-ttu-id="e9fd2-117">此外，您還可以建立 CNAME 記錄，協助客戶找到您的網站。</span><span class="sxs-lookup"><span data-stu-id="e9fd2-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="e9fd2-118">選取 [ **+ 新的自訂記錄**]，然後輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="e9fd2-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="e9fd2-119">針對**DNS 類型**輸入： **CNAME （別名）**</span><span class="sxs-lookup"><span data-stu-id="e9fd2-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="e9fd2-120">針對 [**主機名稱或別名**]，輸入下列： **www**</span><span class="sxs-lookup"><span data-stu-id="e9fd2-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="e9fd2-121">在 [**指向位址**] 中，輸入您網站的完整功能變數名稱（FQDN）（例如，contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="e9fd2-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="e9fd2-122">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e9fd2-122">Select **Save**.</span></span> 
    
<span data-ttu-id="e9fd2-123">最後，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e9fd2-123">Finally, do the following:</span></span>
  
<span data-ttu-id="e9fd2-124">[更新網域的 NS 記錄](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx)，使它指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e9fd2-124">[Update your domain's NS records](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) to point to Office 365.</span></span> 
  
<span data-ttu-id="e9fd2-p103">當 NS 記錄已更新成指向 Office 365 時，表示您的網域已經準備就緒。電子郵件會轉至 Office 365，而您網址的流量會繼續流向您目前的網站主機。</span><span class="sxs-lookup"><span data-stu-id="e9fd2-p103">When the NS records have been updated to point to Office 365, your domain is all set up. Email will be routed to Office 365, and traffic to your website address will continue to go to your current website host.</span></span>
 
