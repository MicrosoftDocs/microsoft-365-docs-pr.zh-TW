---
title: 網域常見問題集
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
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: 在 FAQ 中尋找問題的答案以深入瞭解網域。
ms.custom: okr_smb
ms.openlocfilehash: 4ece90306f37b6f07e34ce93423a76f084d50b6f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627591"
---
# <a name="domains-faq"></a><span data-ttu-id="4324d-103">網域常見問題集</span><span class="sxs-lookup"><span data-stu-id="4324d-103">Domains FAQ</span></span>

<span data-ttu-id="4324d-104">本文包含有關 Office 365 中的網域的常見問題解答。</span><span class="sxs-lookup"><span data-stu-id="4324d-104">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="4324d-105">如果您找不到問題的答案，請留言讓我們知道，我們會將它新增至清單。</span><span class="sxs-lookup"><span data-stu-id="4324d-105">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="4324d-106">什麼是 MX 優先順序？</span><span class="sxs-lookup"><span data-stu-id="4324d-106">What is MX priority?</span></span>

<span data-ttu-id="4324d-107">郵件會以最低喜好設定值（最高優先順序）傳遞到郵件 exchange 伺服器，因此用於郵件路由的 MX 記錄應該具有最低的喜好設定值，通常是0或*高*優先順序。</span><span class="sxs-lookup"><span data-stu-id="4324d-107">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="4324d-108">當您建立 MX 記錄時，大部分的 DNS 主機服務提供者要求您設定偏好設定號碼。</span><span class="sxs-lookup"><span data-stu-id="4324d-108">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="4324d-109">某些標籤的方塊*偏好*，有些標籤*優先順序*。</span><span class="sxs-lookup"><span data-stu-id="4324d-109">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="4324d-110">有些需要數位，有些會要求您選取 [*低*]、[*中*] 或 [*高*]。</span><span class="sxs-lookup"><span data-stu-id="4324d-110">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="4324d-111">如果您只有一個 MX 記錄，則優先順序或喜好設定的任何值都很好。</span><span class="sxs-lookup"><span data-stu-id="4324d-111">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="4324d-112">如果您有一個以上的，請確定郵件路由的 MX 記錄的優先順序高於用於驗證您擁有該網域的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="4324d-112">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="4324d-113">如何驗證我的網域的 SPF 記錄？</span><span class="sxs-lookup"><span data-stu-id="4324d-113">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="4324d-114">您必須具有或建立**一個 SPF 的 TXT 記錄**，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="4324d-114">It's important that you have or create **only one TXT record for SPF**.</span></span> <span data-ttu-id="4324d-115">如果您已經有 SPF 記錄，您應該將新的 Office 365 值附加到它，而不是建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="4324d-115">If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="4324d-116">在您新增或更新 Microsoft 電子郵件的 SPF 記錄之後，您應該檢查下列其中一項工具，確定語法是否正確：</span><span class="sxs-lookup"><span data-stu-id="4324d-116">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="4324d-117">SPF 記錄測試控管</span><span class="sxs-lookup"><span data-stu-id="4324d-117">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="4324d-118">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="4324d-118">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="4324d-119">挖出 web 介面</span><span class="sxs-lookup"><span data-stu-id="4324d-119">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="4324d-120">Office 365 如何管理我的 DNS 記錄？</span><span class="sxs-lookup"><span data-stu-id="4324d-120">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="4324d-121">使用 Office 365 的 DNS 管理有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="4324d-121">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="4324d-122">您變更了名稱伺服器（NS）記錄，然後 Microsoft 會處理所有服務特有的記錄，例如設定電子郵件的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="4324d-122">You change your nameserver (NS) records, and then Microsoft takes care of all the service-specific records, like setting up your MX record for email.</span></span> <span data-ttu-id="4324d-123">**推薦**</span><span class="sxs-lookup"><span data-stu-id="4324d-123">**(Recommended)**</span></span>
    
2. <span data-ttu-id="4324d-124">您可以在 DNS 主機自行新增電子郵件和其他 Office 365 服務的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="4324d-124">You add DNS records for email and other Office 365 services at your DNS host yourself.</span></span> <span data-ttu-id="4324d-125">**（僅限專家）**</span><span class="sxs-lookup"><span data-stu-id="4324d-125">**(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="4324d-126">Office 365 會建立及裝載 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="4324d-126">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="4324d-127">**優點**</span><span class="sxs-lookup"><span data-stu-id="4324d-127">**Advantages**</span></span> 
- <span data-ttu-id="4324d-128">您不需要擔心您為 Office 365 服務的 DNS 記錄輸入的值錯誤。</span><span class="sxs-lookup"><span data-stu-id="4324d-128">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="4324d-129">您選擇的網域註冊機構和 DNS 主機具有較大的彈性。</span><span class="sxs-lookup"><span data-stu-id="4324d-129">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="4324d-130">任何可讓您變更名稱伺服器記錄的提供者都會運作，即使提供者不支援所有必要的記錄類型。</span><span class="sxs-lookup"><span data-stu-id="4324d-130">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="4324d-131">當 Office 365 新增 DNS 記錄時，您不需要進行更新。</span><span class="sxs-lookup"><span data-stu-id="4324d-131">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="4324d-132">缺點</span><span class="sxs-lookup"><span data-stu-id="4324d-132">Disadvantages</span></span> 
- <span data-ttu-id="4324d-133">您無法變更您的 DNS 記錄以主控 Office 365 以外的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="4324d-133">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="4324d-134">如果您已在網域上使用公用網站的位址（如 www.fourthcoffee.com），您必須將人員重新導向至 Office 365 的該位址。</span><span class="sxs-lookup"><span data-stu-id="4324d-134">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="4324d-135">設定重新導向需要靜態 IP 位址，但不一定能輕易用於公用網站。</span><span class="sxs-lookup"><span data-stu-id="4324d-135">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="4324d-136">-如果您目前的網域註冊機構不允許您變更網域的名稱伺服器記錄，您必須切換至不同的註冊機構，才能使用此 DNS 管理選項。</span><span class="sxs-lookup"><span data-stu-id="4324d-136">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="4324d-137">您自行管理 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="4324d-137">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="4324d-138">優點</span><span class="sxs-lookup"><span data-stu-id="4324d-138">Advantages</span></span>
- <span data-ttu-id="4324d-139">您可以控制 Office 365 服務的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="4324d-139">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="4324d-140">如果您擁有網域的公用網站的位址（如 www.fourthcoffee.com），您不需要擔心在您設定 Office 365 中的網域後，使用者仍可進入您的網站。</span><span class="sxs-lookup"><span data-stu-id="4324d-140">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="4324d-141">您可以靈活地在其他地方主控電子郵件，例如使用內部部署 Exchange 伺服器。</span><span class="sxs-lookup"><span data-stu-id="4324d-141">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="4324d-142">缺點</span><span class="sxs-lookup"><span data-stu-id="4324d-142">Disadvantages</span></span>
<span data-ttu-id="4324d-143">您必須自行設定 Office 365 服務的 DNS 記錄（除非您有 GoDaddy 網域）。</span><span class="sxs-lookup"><span data-stu-id="4324d-143">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="4324d-144">如果目前的 DNS 主機不支援 Microsoft 365 的所有必要記錄類型，有些功能將無法使用，您可能需要切換至不同的 DNS 主機。</span><span class="sxs-lookup"><span data-stu-id="4324d-144">If your current DNS host doesn't support all of the required record types for Microsoft 365, some features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="4324d-145">當 Office 365 變更 DNS 記錄的需求，或加入新的服務時，您必須自行在您的 DNS 主機上進行更新。</span><span class="sxs-lookup"><span data-stu-id="4324d-145">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="4324d-146">何謂功能變數名稱？</span><span class="sxs-lookup"><span data-stu-id="4324d-146">What is a domain name?</span></span>


<span data-ttu-id="4324d-147">網域是在電子郵件地址的 **@** 符號後，以及網址的 **www.**</span><span class="sxs-lookup"><span data-stu-id="4324d-147">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="4324d-148">後出現的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="4324d-148">in web addresses.</span></span> <span data-ttu-id="4324d-149">它通常採用組織名稱和標準 Internet 尾碼的形式，例如*yourbusiness.com*或*stateuniversity.edu。*</span><span class="sxs-lookup"><span data-stu-id="4324d-149">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="4324d-150">使用自訂網域（例如「可信性**\@contoso.com**」）與 Office 365，可協助您建立品牌的信譽及認可。</span><span class="sxs-lookup"><span data-stu-id="4324d-150">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="4324d-151">您可以[在 Office 365 購買網域，我們會自動加以設定](../get-help-with-domains/buy-a-domain-name.md)，或者您可以從網域註冊機構購買或為您提供自己的現有功能。</span><span class="sxs-lookup"><span data-stu-id="4324d-151">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="4324d-152">我可以將從 Microsoft 購買的網域轉移至其他提供者嗎？</span><span class="sxs-lookup"><span data-stu-id="4324d-152">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="4324d-153">是的，但是您無法將 Office 365 網域轉接至其他註冊機構，直到您購買 Office 365 的60天之後。</span><span class="sxs-lookup"><span data-stu-id="4324d-153">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="4324d-154">請注意， *Whois*查詢會將 Office 365 購買的網域註冊機構顯示為通配的 WEST 網域 LLC。</span><span class="sxs-lookup"><span data-stu-id="4324d-154">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="4324d-155">不過，請只針對您的 Office 365 購買的網域，請與 Office 365 取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="4324d-155">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="4324d-156">請遵循下列步驟，取得 Office 365 的程式碼，然後移至另一個網域註冊機構的網站，設定將您的功能變數名稱轉移到該註冊機構。</span><span class="sxs-lookup"><span data-stu-id="4324d-156">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4324d-157">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4324d-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4324d-158">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4324d-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4324d-159">在系統管理中心中，移至 [**設定** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">授權</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4324d-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="4324d-160">在 [**網域**] 頁面上，選取您要傳送至其他網域註冊機構的 Office 365 網域，然後選取 [**網域傳輸** > **啟用網域傳輸**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-160">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="4324d-161">遵循步驟來準備轉移您的網域。</span><span class="sxs-lookup"><span data-stu-id="4324d-161">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="4324d-162">在您取得程式碼之後，請移至網域註冊機構的網站，以供您用來管理功能變數名稱的位置，並遵循傳送網域（搜尋其網站上的說明）的指導。</span><span class="sxs-lookup"><span data-stu-id="4324d-162">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="4324d-163">如果您需要重新查看此程式碼，請在 Office 365 的 [**網域設定**] 頁面上，選取 [ **View the domain transfer 的授權碼**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-163">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="4324d-164">完成傳輸後，您將會在新的網域註冊機構中更新您的網域。</span><span class="sxs-lookup"><span data-stu-id="4324d-164">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="4324d-165">若要完成此程式，請回到管理中心的 [**網域**] 頁面，並選取 [**完整網域傳輸**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-165">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="4324d-166">*附注：請注意，Office 365 購買的網域不適用於名稱伺服器變更，或無法在 Office 365 承租人間傳輸網域。 若有任何一項是必要的，則必須將網域註冊轉給另一個註冊機構。*</span><span class="sxs-lookup"><span data-stu-id="4324d-166">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="4324d-167">如何變更我的 DNS 記錄在 Office 365 中的管理方式？</span><span class="sxs-lookup"><span data-stu-id="4324d-167">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="4324d-168">將 DNS 管理變更為 Office 365 以外的 DNS 主機</span><span class="sxs-lookup"><span data-stu-id="4324d-168">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="4324d-169">登入網域的網域註冊機構。</span><span class="sxs-lookup"><span data-stu-id="4324d-169">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="4324d-170">在註冊機構網站上尋找您更新名稱伺服器記錄的區域，並更新名稱伺服器以指向您網域的 DNS 主機。</span><span class="sxs-lookup"><span data-stu-id="4324d-170">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host.</span></span> <span data-ttu-id="4324d-171">（DNS 主機通常是網域註冊機構。）</span><span class="sxs-lookup"><span data-stu-id="4324d-171">(The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="4324d-172">遵循連結移至網域安裝精靈：</span><span class="sxs-lookup"><span data-stu-id="4324d-172">Follow a link to go to the domains setup wizard:</span></span>

::: moniker range="o365-worldwide"

4. <span data-ttu-id="4324d-173">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4324d-173">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

4. <span data-ttu-id="4324d-174">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4324d-174">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

4. <span data-ttu-id="4324d-175">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4324d-175">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
5. <span data-ttu-id="4324d-176">在 [**網域**] 頁面上，選取您要切換的網域，然後選取 [ **DNS 管理**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-176">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="4324d-177">在 [網域安裝精靈] 中，在 [**設定您的線上服務**] 頁面上，選取 [**我要管理自己的 DNS 記錄**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4324d-177">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="4324d-178">在 [**更新 dns 設定**] 頁面上，將嚮導建議的 DNS 記錄新增至您的註冊機構網站。</span><span class="sxs-lookup"><span data-stu-id="4324d-178">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="4324d-179">在您新增記錄後，請回到 Office 365 並選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-179">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="4324d-180">將 DNS 管理變更為 Office 365</span><span class="sxs-lookup"><span data-stu-id="4324d-180">Change DNS management to Office 365</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4324d-181">在系統管理中心中，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4324d-181">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page..</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4324d-182">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4324d-182">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4324d-183">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4324d-183">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="4324d-184">在 [**網域**] 頁面上，選取您要切換的網域，然後選取 [ **DNS 管理**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-184">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="4324d-185">在 [網域安裝精靈] 中，在 [**設定您的線上服務**] 頁面上，選取 [**設定我的線上服務給我]。（建議）**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4324d-185">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="4324d-186">如果您還沒有驗證網域，請遵循執行第一步的步驟。</span><span class="sxs-lookup"><span data-stu-id="4324d-186">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="4324d-187">在 [**更新 DNS 設定**] 頁面上，列出 Office 365 的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="4324d-187">On the **Update DNS settings** page, we list the nameservers for Office 365.</span></span> <span data-ttu-id="4324d-188">移至網域的網域註冊機構，並將名稱伺服器更新為 Office 365 名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="4324d-188">Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="4324d-189">更新名稱伺服器後，請**至少等候一小時**。</span><span class="sxs-lookup"><span data-stu-id="4324d-189">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="4324d-190">然後，回到 Office 365 的嚮導中，選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-190">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="4324d-191">如果我的 DNS 提供者不支援某些記錄類型，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="4324d-191">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="4324d-192">如果您管理自己的 DNS 記錄，而且 DNS 主機不支援 Office 365 所需的所有 DNS 記錄，有些 Office 365 功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="4324d-192">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work.</span></span> <span data-ttu-id="4324d-193">建議您將網域轉接至支援所有必要 DNS 記錄的註冊機構。</span><span class="sxs-lookup"><span data-stu-id="4324d-193">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="4324d-194">支援所有必要 DNS 記錄的提供者：</span><span class="sxs-lookup"><span data-stu-id="4324d-194">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="4324d-195">Dynadot</span><span class="sxs-lookup"><span data-stu-id="4324d-195">Dynadot</span></span>
    
- <span data-ttu-id="4324d-196">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="4324d-196">eNomCentral</span></span>
    
- <span data-ttu-id="4324d-197">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="4324d-197">Europe Registry</span></span>
    
- <span data-ttu-id="4324d-198">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="4324d-198">GoDaddy</span></span>
    
- <span data-ttu-id="4324d-199">懸停</span><span class="sxs-lookup"><span data-stu-id="4324d-199">Hover</span></span>
    
- <span data-ttu-id="4324d-200">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="4324d-200">MyHosting.com</span></span>
    
- <span data-ttu-id="4324d-201">Name.com</span><span class="sxs-lookup"><span data-stu-id="4324d-201">Name.com</span></span>
    
- <span data-ttu-id="4324d-202">幾乎自由語音</span><span class="sxs-lookup"><span data-stu-id="4324d-202">Nearly Free Speech</span></span>
    
- <span data-ttu-id="4324d-203">Nettica</span><span class="sxs-lookup"><span data-stu-id="4324d-203">Nettica</span></span>
    
- <span data-ttu-id="4324d-204">網際網路資訊中心 (NIC)</span><span class="sxs-lookup"><span data-stu-id="4324d-204">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="4324d-205">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="4324d-205">Network Solutions</span></span>
    
- <span data-ttu-id="4324d-206">Register.com</span><span class="sxs-lookup"><span data-stu-id="4324d-206">Register.com</span></span>
    
 <span data-ttu-id="4324d-207">**如果不支援 SRV 記錄**，則無法使用下列 Office 365 功能：</span><span class="sxs-lookup"><span data-stu-id="4324d-207">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="4324d-208">商務用 Skype Online IM 和目前狀態與 Outlook Web App 的整合</span><span class="sxs-lookup"><span data-stu-id="4324d-208">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="4324d-209">與其他組織中商務用 Skype Online 使用者的外部通訊（同盟）。</span><span class="sxs-lookup"><span data-stu-id="4324d-209">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="4324d-210">公用網際網路連線（PIC）與商務用 Skype Online 使用者使用 Microsoft 帳戶登入（以前稱為 Windows Live ID）。</span><span class="sxs-lookup"><span data-stu-id="4324d-210">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="4324d-211">**如果不支援多個 CNAME 記錄，** 您必須為商務用 Skype Online 選擇下列功能：</span><span class="sxs-lookup"><span data-stu-id="4324d-211">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="4324d-212">電子郵件桌面用戶端和行動用戶端可以使用自動探索自動尋找 Exchange Online 服務，讓使用者不必輸入伺服器名稱即可登入。</span><span class="sxs-lookup"><span data-stu-id="4324d-212">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="4324d-213">商務用 skype Online 桌面用戶端可以使用自動探索，自動尋找商務用 Skype Online 服務，讓使用者不必輸入伺服器名稱即可登入。</span><span class="sxs-lookup"><span data-stu-id="4324d-213">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="4324d-214">商務用 skype Online 行動用戶端可以使用自動探索，自動尋找商務用 Skype Online 服務，讓使用者不必輸入伺服器名稱即可登入。</span><span class="sxs-lookup"><span data-stu-id="4324d-214">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
 <span data-ttu-id="4324d-215">**如果不支援 SPF/TXT 記錄**，其他人可能會使用您的網域來傳送垃圾郵件或其他惡意的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="4324d-215">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email.</span></span> <span data-ttu-id="4324d-216">SPF 記錄會透過識別從您的網域傳送電子郵件的授權伺服器運作。</span><span class="sxs-lookup"><span data-stu-id="4324d-216">SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="4324d-217">如何在 Office 365 中設定或變更預設網域？</span><span class="sxs-lookup"><span data-stu-id="4324d-217">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="4324d-218">您必須至少有一個自訂網域新增至 Office 365，您才能選擇預設網域。</span><span class="sxs-lookup"><span data-stu-id="4324d-218">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4324d-219">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4324d-219">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4324d-220">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4324d-220">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4324d-221">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4324d-221">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="4324d-222">在 [**網域**] 頁面上，選取您要設定為新電子郵件地址的預設網域。</span><span class="sxs-lookup"><span data-stu-id="4324d-222">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="4324d-223">選取 [設定成預設值]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4324d-223">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="4324d-224">您無法變更*onmicrosoft.com*網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="4324d-224">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="4324d-225">您無法變更*onmicrosoft.de*網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="4324d-225">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="4324d-226">您無法變更*partner.onmschina.cn*網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="4324d-226">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="4324d-227">我可以將自訂子域或多個網域新增至 Office 365 嗎？</span><span class="sxs-lookup"><span data-stu-id="4324d-227">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="4324d-228">是的！</span><span class="sxs-lookup"><span data-stu-id="4324d-228">Yes!</span></span> <span data-ttu-id="4324d-229">若要新增子域，您必須在註冊機構網站上管理自己的 DNS 設定。</span><span class="sxs-lookup"><span data-stu-id="4324d-229">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="4324d-230">如果您要讓 Microsoft 使用 NS 記錄來管理您的 DNS 設定，或者您購買的是 Microsoft 的網域，您就無法新增子域。</span><span class="sxs-lookup"><span data-stu-id="4324d-230">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="4324d-231">是的！</span><span class="sxs-lookup"><span data-stu-id="4324d-231">Yes!</span></span> <span data-ttu-id="4324d-232">若要新增子域，您必須在註冊機構網站上管理自己的 DNS 設定。</span><span class="sxs-lookup"><span data-stu-id="4324d-232">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="4324d-233">如果您要讓 Microsoft 使用 NS 記錄來管理您的 DNS 設定，或者您購買的是 Microsoft 的網域，您就無法新增子域。</span><span class="sxs-lookup"><span data-stu-id="4324d-233">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="4324d-234">是的！</span><span class="sxs-lookup"><span data-stu-id="4324d-234">Yes!</span></span> <span data-ttu-id="4324d-235">若要新增子域，您必須在註冊機構網站上管理自己的 DNS 設定。</span><span class="sxs-lookup"><span data-stu-id="4324d-235">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="4324d-236">如果您是讓世紀以 NS 記錄來管理您的 DNS 設定，就無法新增子域。</span><span class="sxs-lookup"><span data-stu-id="4324d-236">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="4324d-237">一般來說，您最多可以將900個網域新增至 Office 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="4324d-237">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="4324d-238">例如，您可以新增網域 contoso.com 及 contosomarketing.com，然後新增子域 www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com 等等。</span><span class="sxs-lookup"><span data-stu-id="4324d-238">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="4324d-239">當您新增子域時，會根據所驗證的父系網域，自動驗證。</span><span class="sxs-lookup"><span data-stu-id="4324d-239">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="4324d-240">當您將多個網域新增至 Office 365 時，您可以在您已新增的任何網域上裝載任何服務（如電子郵件）。</span><span class="sxs-lookup"><span data-stu-id="4324d-240">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="4324d-241">*當您將電子郵件變更為 Office 365 時，更新網域的 MX 記錄，所有傳送至該網域的電子郵件都會開始進入 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="4324d-241">*When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="4324d-242">如果您已將 contoso.com 網域新增至 Office 365 租使用者，您也可以將子域 xyz.contoso.com 新增至另一個 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="4324d-242">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="4324d-243">新增子域時，系統會提示您在 DNS 主機服務提供者中新增 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="4324d-243">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="4324d-244">為什麼我有「onmicrosoft.com」網域？</span><span class="sxs-lookup"><span data-stu-id="4324d-244">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="4324d-245">當您註冊服務時，Office 365 會為您建立網域，例如*contoso.onmicrosoft.com*。</span><span class="sxs-lookup"><span data-stu-id="4324d-245">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="4324d-246">您註冊時所建立的使用者識別碼包含網域，如*alan@contoso.onmicrosoft.com*。</span><span class="sxs-lookup"><span data-stu-id="4324d-246">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="4324d-247">**如果您想要讓您的電子郵件看起來像是*alan\@contoso.com*：** [購買網域，](../get-help-with-domains/buy-a-domain-name.md)或是只要您已擁有您的使用者和網域，請依照將您的[使用者與網域新增至 Office 365](add-domain.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="4324d-247">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="4324d-248">**您無法在註冊後重新命名 name.onmicrosoft.com17 網域。**</span><span class="sxs-lookup"><span data-stu-id="4324d-248">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="4324d-249">例如，如果您所選擇的初始網域是 fourthcoffee.onmicrosoft.com，您就無法將它變更為 fabrikam.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="4324d-249">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="4324d-250">若要使用不同的 onmicrosoft.com 網域，您必須開始使用 Office 365 的新訂閱。</span><span class="sxs-lookup"><span data-stu-id="4324d-250">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="4324d-251">**您無法重新命名您的小組網站 URL。**</span><span class="sxs-lookup"><span data-stu-id="4324d-251">**You can't rename your team site URL.**</span></span> <span data-ttu-id="4324d-252">您的小組網站 URL 是以您的 onmicrosoft.com 功能變數名稱為基礎。</span><span class="sxs-lookup"><span data-stu-id="4324d-252">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="4324d-253">不幸的是，由於 SharePoint 線上架構的運作方式，您無法重新命名小組網站。</span><span class="sxs-lookup"><span data-stu-id="4324d-253">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="4324d-254">**您無法移除您的 name.onmicrosoft.com17 網域。**</span><span class="sxs-lookup"><span data-stu-id="4324d-254">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="4324d-255">Office 365 需要保留它，因為它是用於您訂閱的幕後。</span><span class="sxs-lookup"><span data-stu-id="4324d-255">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="4324d-256">不過，您不需要在新增自訂網域之後，自行使用網域。</span><span class="sxs-lookup"><span data-stu-id="4324d-256">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="4324d-257">您可以繼續使用初始 onmicrosoft.com 網域，即使是在您新增網域之後。</span><span class="sxs-lookup"><span data-stu-id="4324d-257">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="4324d-258">它仍適用于電子郵件和其他服務，所以是您的選擇。</span><span class="sxs-lookup"><span data-stu-id="4324d-258">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="4324d-259">為什麼我有「onmicrosoft.de」網域？</span><span class="sxs-lookup"><span data-stu-id="4324d-259">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="4324d-260">當您註冊服務時，Office 365 會為您建立網域，例如*contoso.onmicrosoft.de*。</span><span class="sxs-lookup"><span data-stu-id="4324d-260">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="4324d-261">您註冊時所建立的使用者識別碼包含網域，如*alan@contoso.onmicrosoft.de*。</span><span class="sxs-lookup"><span data-stu-id="4324d-261">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="4324d-262">**如果您想要讓您的電子郵件看起來像是*alan@contoso.de*：** [購買網域](../get-help-with-domains/buy-a-domain-name.md)，或是只要[將您的使用者與網域新增至 Office 365](add-domain.md) ，也請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="4324d-262">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="4324d-263">**您無法在註冊後重新命名 name.onmicrosoft.com17 網域。**</span><span class="sxs-lookup"><span data-stu-id="4324d-263">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="4324d-264">例如，如果您所選擇的初始網域是 fourthcoffee.onmicrosoft.de，您就無法將它變更為 fabrikam.onmicrosoft.de。</span><span class="sxs-lookup"><span data-stu-id="4324d-264">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="4324d-265">若要使用不同的 onmicrosoft.de 網域，您必須開始使用 Office 365 的新訂閱。</span><span class="sxs-lookup"><span data-stu-id="4324d-265">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="4324d-266">**您無法重新命名您的小組網站 URL。**</span><span class="sxs-lookup"><span data-stu-id="4324d-266">**You can't rename your team site URL.**</span></span> <span data-ttu-id="4324d-267">您的小組網站 URL 是以您的 onmicrosoft.de 功能變數名稱為基礎。不幸的是，由於 SharePoint 線上架構的運作方式，您無法重新命名小組網站。</span><span class="sxs-lookup"><span data-stu-id="4324d-267">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="4324d-268">**您無法移除您的 name.onmicrosoft.com17 網域。**</span><span class="sxs-lookup"><span data-stu-id="4324d-268">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="4324d-269">Office 365 需要保留它，因為它是用於您訂閱的幕後。</span><span class="sxs-lookup"><span data-stu-id="4324d-269">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="4324d-270">不過，您不需要在新增自訂網域之後，自行使用網域。</span><span class="sxs-lookup"><span data-stu-id="4324d-270">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="4324d-271">您可以繼續使用初始 onmicrosoft.de 網域，即使是在您新增網域之後。</span><span class="sxs-lookup"><span data-stu-id="4324d-271">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="4324d-272">它仍適用于電子郵件和其他服務，所以是您的選擇。</span><span class="sxs-lookup"><span data-stu-id="4324d-272">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="4324d-273">如何驗證我的非盈利性或教育狀態？</span><span class="sxs-lookup"><span data-stu-id="4324d-273">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="4324d-274">在系統[管理中心](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx)選取 [**安裝**] 以啟動嚮導。</span><span class="sxs-lookup"><span data-stu-id="4324d-274">Select **Setup** in the [admin center](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) to start the wizard.</span></span> <span data-ttu-id="4324d-275">（請務必先登入 Office 365。）</span><span class="sxs-lookup"><span data-stu-id="4324d-275">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="4324d-276">若要成為 school 的系統管理員，請選取 [成為 Office 365 的系統**管理員**] 選項。</span><span class="sxs-lookup"><span data-stu-id="4324d-276">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="4324d-277">系統會提示您在網域的 DNS 主機網站上新增 TXT DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="4324d-277">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="4324d-278">為什麼？</span><span class="sxs-lookup"><span data-stu-id="4324d-278">Why?</span></span> <span data-ttu-id="4324d-279">由於是在 DNS 主機登入，並為您的網域新增記錄，因此您可以為 Office 365 證明您擁有該功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="4324d-279">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="4324d-280">在您新增記錄後，您會回到 Office 365 入口網站，並確認您已新增該記錄，因此 Office 365 可以進行檢查。</span><span class="sxs-lookup"><span data-stu-id="4324d-280">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="4324d-281">是否有非贏利且想要取得 Office 365？</span><span class="sxs-lookup"><span data-stu-id="4324d-281">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="4324d-282">[請確定您的組織符合資格](https://www.microsoft.com/en-us/nonprofits/eligibility)，然後註冊服務。</span><span class="sxs-lookup"><span data-stu-id="4324d-282">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="4324d-283">想要深入瞭解如何成為您的學校管理員？</span><span class="sxs-lookup"><span data-stu-id="4324d-283">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="4324d-284">[深入瞭解](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。</span><span class="sxs-lookup"><span data-stu-id="4324d-284">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="4324d-285">我可以使用來自自訂網域的一些電子郵件地址試驗 Office 365 嗎？</span><span class="sxs-lookup"><span data-stu-id="4324d-285">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="4324d-286">您可以，但有一些限制：</span><span class="sxs-lookup"><span data-stu-id="4324d-286">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="4324d-287">您目前的電子郵件提供者必須提供電子郵件轉接功能。</span><span class="sxs-lookup"><span data-stu-id="4324d-287">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="4324d-288">您需要在您的 DNS 主機服務提供者管理與 Office 365 相關的 DNS 記錄，而不是讓 Office 365 為您管理這些記錄。</span><span class="sxs-lookup"><span data-stu-id="4324d-288">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="4324d-289">若要瞭解這需要做什麼，請參閱將您的網域新增至 Office 365，以管理您自己的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="4324d-289">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="4324d-290">有些 Office 365 功能無法使用：</span><span class="sxs-lookup"><span data-stu-id="4324d-290">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="4324d-291">使用者將無法查看位於其他電子郵件提供者上之使用者的空閒/忙碌資訊。</span><span class="sxs-lookup"><span data-stu-id="4324d-291">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="4324d-292">系統管理員無法從單一位置管理所有人的帳戶。</span><span class="sxs-lookup"><span data-stu-id="4324d-292">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="4324d-293">使用者可能無法使用 Office 365 垃圾郵件篩選</span><span class="sxs-lookup"><span data-stu-id="4324d-293">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="4324d-294">如何設定 Office 365 試驗</span><span class="sxs-lookup"><span data-stu-id="4324d-294">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="4324d-295">登入 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="4324d-295">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="4324d-296">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4324d-296">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="4324d-297">移至 [**設定** \> ] [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-297">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="4324d-298">確認您擁有要使用的網域</span><span class="sxs-lookup"><span data-stu-id="4324d-298">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="4324d-299">在 [**網域**] 頁面上，選取 [**新增網域**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-299">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="4324d-300">在面板中，輸入網域，在此範例中 cohowinery.com，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4324d-300">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="4324d-301">在 [**驗證**網域] 頁面上，遵循逐步指示。</span><span class="sxs-lookup"><span data-stu-id="4324d-301">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="4324d-302">在下拉式清單中，選取您的 DNS 主機服務提供者，然後依照指示，顯示您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="4324d-302">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="4324d-303">選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-303">Select **Verify**.</span></span> <span data-ttu-id="4324d-304">DNS 變更會在幾分鐘和72小時之間生效。</span><span class="sxs-lookup"><span data-stu-id="4324d-304">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="4324d-305">驗證成功時，系統會要求您修改您的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="4324d-305">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="4324d-306">在 Exchange Online 中將網域標示為「共用」</span><span class="sxs-lookup"><span data-stu-id="4324d-306">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="4324d-307">移至**Exchange 系統管理中心**（EAC）。</span><span class="sxs-lookup"><span data-stu-id="4324d-307">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="4324d-308">在 [**郵件流程**] 區段中，選取 [**公認的網域**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-308">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="4324d-309">按兩下您要修改的網域。</span><span class="sxs-lookup"><span data-stu-id="4324d-309">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="4324d-310">在開啟的視窗中，選取 [**內部轉送**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-310">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="4324d-311">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="4324d-311">Select **Save**.</span></span> <span data-ttu-id="4324d-312">此設定可能需要幾分鐘才會生效。</span><span class="sxs-lookup"><span data-stu-id="4324d-312">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="4324d-313">（選用）解除封鎖現有的電子郵件伺服器</span><span class="sxs-lookup"><span data-stu-id="4324d-313">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="4324d-314">Office 365 使用 Exchange Online Protection （EOP）進行垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="4324d-314">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="4324d-315">如果 EOP 偵測到您目前的郵件伺服器轉寄大量的垃圾郵件，可能會封鎖垃圾郵件，這樣會使轉接無法運作。</span><span class="sxs-lookup"><span data-stu-id="4324d-315">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="4324d-316">如果您確信其他電子郵件提供者所用的垃圾郵件保護，您可以在 Office 365 中白名單其伺服器。</span><span class="sxs-lookup"><span data-stu-id="4324d-316">If you are confident with the spam protection your other email provider uses, you can whitelist their server in Office 365.</span></span> <span data-ttu-id="4324d-317">不過，這也會讓透過您原始伺服器到達的任何垃圾郵件都進入 Office 365 信箱，而且您將無法評估 Office 365 如何防止垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="4324d-317">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="4324d-318">移至 Exchange 系統管理中心（EAC）。</span><span class="sxs-lookup"><span data-stu-id="4324d-318">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="4324d-319">在 EAC 中，選取 [**保護**]，然後選取 [連線**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-319">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="4324d-320">在 [ **IP 允許] 清單**中**+**，選取，並新增您可以從目前的電子郵件提供者取得的郵件伺服器 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4324d-320">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="4324d-321">建立使用者帳戶並設定主要（回復）位址</span><span class="sxs-lookup"><span data-stu-id="4324d-321">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="4324d-322">移至 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="4324d-322">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="4324d-323">在左導覽列中，選取 [**使用者** \>作用中**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-323">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="4324d-324">建立使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4324d-324">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="4324d-325">針對每個帳戶選取 **[+] （新增）**，並填寫必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="4324d-325">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="4324d-326">若要讓使用者的電子郵件與其目前相同，[**使用者名稱**] 欄位應該與使用者的現有電子郵件地址完全相同。</span><span class="sxs-lookup"><span data-stu-id="4324d-326">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="4324d-327">在 [使用者名稱] 旁，從下拉式清單中選取您的自訂功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="4324d-327">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="4324d-328">選取 [**建立** \> **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="4324d-328">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="4324d-329">在您的 DNS 主機服務提供者更新 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="4324d-329">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="4324d-330">登入您的 DNS 主機服務提供者的網站，並遵循在[任何 dns 主機服務提供者上為 Office 365 步驟建立 dns 記錄](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="4324d-330">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="4324d-331">**請進行下列例外狀況：**</span><span class="sxs-lookup"><span data-stu-id="4324d-331">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="4324d-332">請勿建立新的 MX 記錄或變更現有的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="4324d-332">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="4324d-333">如果您先前的電子郵件提供者已具備寄件者原則架構（SPF）記錄，而不是為 Exchange Online 建立新的 SPF （TXT）記錄，請直接在目前的 TXT 記錄中新增「包含: spf.protection.outlook.com .com」。</span><span class="sxs-lookup"><span data-stu-id="4324d-333">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="4324d-334">例如，"v = spf1 mx 包含:adatum 包含: spf.protection.outlook.com. .com ~ all"。</span><span class="sxs-lookup"><span data-stu-id="4324d-334">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="4324d-335">如果您還沒有 SPF 記錄，請修改 Office 365 建議的一個，以包含目前電子郵件提供者的網域，加上 spf.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="4324d-335">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="4324d-336">這會從兩個電子郵件系統中授權外寄郵件。</span><span class="sxs-lookup"><span data-stu-id="4324d-336">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="4324d-337">在您目前的提供者設定電子郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="4324d-337">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="4324d-338">在您目前的電子郵件提供者中，將您的使用者電子郵件帳戶的轉寄功能設定為您的 onmicrosoft.com 網域：</span><span class="sxs-lookup"><span data-stu-id="4324d-338">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="4324d-339">使用者 A 的信箱應該轉寄至 usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4324d-339">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="4324d-340">使用者 B 的信箱應該轉寄至 userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4324d-340">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="4324d-341">當您完成此步驟：</span><span class="sxs-lookup"><span data-stu-id="4324d-341">When you complete this step:</span></span>
        
    5. <span data-ttu-id="4324d-342">所有傳送至 usera@yourcompany.com 和 userb@yourcompany.com 的郵件都會出現在 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4324d-342">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="4324d-343">附註：</span><span class="sxs-lookup"><span data-stu-id="4324d-343">Notes:</span></span>
        
        - <span data-ttu-id="4324d-344">如需設定轉接的確切步驟，請與您目前的電子郵件提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="4324d-344">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="4324d-345">您不需要在目前的電子郵件提供者中保留郵件複本。</span><span class="sxs-lookup"><span data-stu-id="4324d-345">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="4324d-346">大部分提供者會轉寄電子郵件，讓寄件者的回復位址保持不變，因此回復會移至原始寄件者。</span><span class="sxs-lookup"><span data-stu-id="4324d-346">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="4324d-347">測試郵件流程</span><span class="sxs-lookup"><span data-stu-id="4324d-347">Test mail flow</span></span>
    
    1. <span data-ttu-id="4324d-348">使用使用者 A 的認證登入 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="4324d-348">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="4324d-349">請執行下列測試：</span><span class="sxs-lookup"><span data-stu-id="4324d-349">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="4324d-350">測試本機 Microsoft 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="4324d-350">Test local Microsoft email.</span></span> <span data-ttu-id="4324d-351">例如，傳送電子郵件給使用者 B。這封電子郵件應該會立即傳遞。</span><span class="sxs-lookup"><span data-stu-id="4324d-351">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="4324d-352">在此情況下，郵件將不會路由傳送至原始伺服器上的使用者 B 信箱，因為 Office 365 會將信箱視為本機。</span><span class="sxs-lookup"><span data-stu-id="4324d-352">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="4324d-353">測試電子郵件給其他電子郵件系統上的某人。</span><span class="sxs-lookup"><span data-stu-id="4324d-353">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="4324d-354">例如，傳送電子郵件給使用者 C。這封電子郵件應該傳送至原始郵件伺服器上的使用者 C 信箱。</span><span class="sxs-lookup"><span data-stu-id="4324d-354">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="4324d-355">從外部帳戶，或是從其他電子郵件系統上某員工的電子郵件帳戶，確認已在其他電子郵件系統上正確設定轉寄功能。</span><span class="sxs-lookup"><span data-stu-id="4324d-355">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="4324d-356">例如，從使用者 C 的 origninal server 帳戶或 Hotmail 帳戶傳送使用者 A 電子郵件，並確認其送達使用者 A 的 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="4324d-356">For example, from User C's origninal server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="4324d-357">移動信箱內容</span><span class="sxs-lookup"><span data-stu-id="4324d-357">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="4324d-358">由於只有兩位使用者可以移動，而且由於使用者 A 和使用者 B 都使用 Outlook，因此可以開啟舊的電子郵件來移動電子郵件。PST 檔案，並複製郵件、行事曆專案、連絡人等，如從 Outlook 資料檔（.pst）匯入 Outlook 專案中所示。</span><span class="sxs-lookup"><span data-stu-id="4324d-358">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="4324d-359">在 Office 365 信箱中的適當位置進行組織時，這些專案就可以從任何裝置從任何地方存取。</span><span class="sxs-lookup"><span data-stu-id="4324d-359">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="4324d-360">當涉及更多信箱，或如果員工尚未使用 Outlook，您可以使用 Exchange 系統管理中心提供的遷移工具。</span><span class="sxs-lookup"><span data-stu-id="4324d-360">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="4324d-361">若要開始使用，請移至 Exchange 系統管理中心，並遵循將電子郵件從 IMAP 伺服器遷移至 Exchange Online 信箱的指示。</span><span class="sxs-lookup"><span data-stu-id="4324d-361">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
