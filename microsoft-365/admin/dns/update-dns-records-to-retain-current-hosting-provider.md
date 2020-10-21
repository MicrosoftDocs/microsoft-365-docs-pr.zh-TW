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
ms.openlocfilehash: 5d2bf23d4052815fae210d0fdf6635288ff46b57
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645560"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="52d5e-103">更新 DNS 記錄以便向目前的主機服務提供者保留網站</span><span class="sxs-lookup"><span data-stu-id="52d5e-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="52d5e-104">[！附注]**如果您在 DNS 主機服務提供者管理您網域的 Microsoft 記錄**，您不需要擔心本主題中的步驟。</span><span class="sxs-lookup"><span data-stu-id="52d5e-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="52d5e-105">您的網站會留在原處，使用者仍然可以存取。</span><span class="sxs-lookup"><span data-stu-id="52d5e-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="52d5e-106">**如果 microsoft 管理您的 DNS 記錄**，若要將流量路由傳送至 microsoft 所主控的現有公用網站，將您的網域新增至 microsoft 之後，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="52d5e-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="52d5e-107">在 Microsoft 365 系統管理中心更新 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="52d5e-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="52d5e-108">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="52d5e-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="52d5e-109">在 [ **網域** ] 頁面上，選取網域，然後選擇 [ **DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="52d5e-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="52d5e-110">在 [ **DNS 設定**] 底下，選取 [ **自訂記錄**]。</span><span class="sxs-lookup"><span data-stu-id="52d5e-110">Under **DNS settings**, select **Custom Records**.</span></span>

4. <span data-ttu-id="52d5e-111">選取 [ **+ 新的自訂記錄** ]，然後輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="52d5e-111">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="52d5e-112">針對 **DNS** 輸入： \*\* (位址) \*\*</span><span class="sxs-lookup"><span data-stu-id="52d5e-112">For **DNS type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="52d5e-113">針對 [ **主機名稱或別名**]，輸入下列專案： **@**</span><span class="sxs-lookup"><span data-stu-id="52d5e-113">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="52d5e-114">在 [ **IP 位址**] 中，輸入目前主控 (之網站的靜態 IP 位址（例如，172.16.140.1) ）。</span><span class="sxs-lookup"><span data-stu-id="52d5e-114">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="52d5e-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span><span class="sxs-lookup"><span data-stu-id="52d5e-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
5. <span data-ttu-id="52d5e-117">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="52d5e-117">Select **Save**.</span></span> 
    
<span data-ttu-id="52d5e-118">此外，您還可以建立 CNAME 記錄，協助客戶找到您的網站。</span><span class="sxs-lookup"><span data-stu-id="52d5e-118">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="52d5e-119">選取 [ **+ 新的自訂記錄** ]，然後輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="52d5e-119">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="52d5e-120">針對 **DNS 類型** 輸入： \*\*CNAME (別名) \*\*</span><span class="sxs-lookup"><span data-stu-id="52d5e-120">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="52d5e-121">針對 [ **主機名稱或別名**]，輸入下列： **www**</span><span class="sxs-lookup"><span data-stu-id="52d5e-121">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="52d5e-122">在 [ **指向位址**] 中，為您的網站輸入完整功能變數名稱 (FQDN)  (例如，contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="52d5e-122">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="52d5e-123">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="52d5e-123">Select **Save**.</span></span> 
    
<span data-ttu-id="52d5e-124">最後，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="52d5e-124">Finally, do the following:</span></span>
  
<span data-ttu-id="52d5e-125">[更新您網域的 NS 記錄](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) ，以指向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="52d5e-125">[Update your domain's NS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to point to Microsoft.</span></span> 
  
<span data-ttu-id="52d5e-126">當 NS 記錄更新為指向 Microsoft 時，您的網域就會全部設定。</span><span class="sxs-lookup"><span data-stu-id="52d5e-126">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="52d5e-127">電子郵件會路由傳送至 Microsoft，而您的網站位址的流量將繼續前往您目前的網站主機。</span><span class="sxs-lookup"><span data-stu-id="52d5e-127">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
 
