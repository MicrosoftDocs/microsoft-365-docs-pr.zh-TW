---
title: 網域常見問題集
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: 深入了解 Office 365 中的網域的常見問題集中尋找您的問題的答案。
ms.custom: okr_smb
ms.openlocfilehash: f3c72f1ce772e3021d79aa4568dbfdb700400803
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252379"
---
# <a name="domains-faq"></a><span data-ttu-id="edb59-103">網域常見問題集</span><span class="sxs-lookup"><span data-stu-id="edb59-103">Domains FAQ</span></span>

<span data-ttu-id="edb59-104">本文包含有關在 Office 365 中的網域的常見問題集解答。</span><span class="sxs-lookup"><span data-stu-id="edb59-104">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="edb59-105">如果您找不到問題的答案，請留言讓我們知道，我們會將它新增至清單。</span><span class="sxs-lookup"><span data-stu-id="edb59-105">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="edb59-106">什麼是 MX 優先順序？</span><span class="sxs-lookup"><span data-stu-id="edb59-106">What is MX priority?</span></span>

<span data-ttu-id="edb59-107">郵件傳遞到郵件 exchange 伺服器與最低的喜好設定編號 （最高優先順序），所以您使用的郵件路由 MX 記錄應具備的最低的喜好設定編號，通常是 0 或*高*優先順序。</span><span class="sxs-lookup"><span data-stu-id="edb59-107">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="edb59-108">當您建立 MX 記錄時，大部分的 DNS 主機服務提供者需要您設定喜好設定編號。</span><span class="sxs-lookup"><span data-stu-id="edb59-108">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="edb59-109">某些標籤] 方塊中的 [*喜好設定*中，並將一些標籤其*優先順序*。</span><span class="sxs-lookup"><span data-stu-id="edb59-109">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="edb59-110">某些需要一個數字，和某些要求您選取 [*低*、*中*或*高*。</span><span class="sxs-lookup"><span data-stu-id="edb59-110">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="edb59-111">如果您只有一個 MX 記錄，任何值會是好的優先順序或喜好設定。</span><span class="sxs-lookup"><span data-stu-id="edb59-111">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="edb59-112">如果您有多個的話，請確定郵件路由的 MX 記錄是一種可以用來驗證您擁有該網域的較高優先順序。</span><span class="sxs-lookup"><span data-stu-id="edb59-112">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="edb59-113">如何驗證我的網域的 SPF 記錄？</span><span class="sxs-lookup"><span data-stu-id="edb59-113">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="edb59-114">請務必您擁有或建立**只有一個 SPF TXT 記錄**。</span><span class="sxs-lookup"><span data-stu-id="edb59-114">It's important that you have or create **only one TXT record for SPF**.</span></span> <span data-ttu-id="edb59-115">如果您已經有 SPF 記錄，您應該附加到文件的新的 Office 365 值，而不是建立一個新。</span><span class="sxs-lookup"><span data-stu-id="edb59-115">If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="edb59-116">您已新增或更新您的 Office 365 電子郵件的 SPF 記錄之後，您應先確認語法不正確的其中一種工具：</span><span class="sxs-lookup"><span data-stu-id="edb59-116">After you've added or updated your SPF record for Office 365 email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="edb59-117">SPF 記錄測試工具</span><span class="sxs-lookup"><span data-stu-id="edb59-117">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="edb59-118">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="edb59-118">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="edb59-119">深入了 web 介面</span><span class="sxs-lookup"><span data-stu-id="edb59-119">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="edb59-120">Office 365 如何管理我的 DNS 記錄？</span><span class="sxs-lookup"><span data-stu-id="edb59-120">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="edb59-121">有兩個選項可使用 Office 365 的 DNS 管理：</span><span class="sxs-lookup"><span data-stu-id="edb59-121">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="edb59-122">變更名稱伺服器 (NS) 記錄，並再 Office 365 的所有特定服務的記錄，例如電子郵件的 MX 記錄設定。</span><span class="sxs-lookup"><span data-stu-id="edb59-122">You change your nameserver (NS) records, and then Office 365 takes care of all the service-specific records, like setting up your MX record for email.</span></span> <span data-ttu-id="edb59-123">**（建議使用）**</span><span class="sxs-lookup"><span data-stu-id="edb59-123">**(Recommended)**</span></span>
    
2. <span data-ttu-id="edb59-124">您的電子郵件和其他 Office 365 服務的 DNS 記錄在您的 DNS 主機將自己新增。</span><span class="sxs-lookup"><span data-stu-id="edb59-124">You add DNS records for email and other Office 365 services at your DNS host yourself.</span></span> <span data-ttu-id="edb59-125">**（專家只）**</span><span class="sxs-lookup"><span data-stu-id="edb59-125">**(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="edb59-126">Office 365 建立和主控的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="edb59-126">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="edb59-127">**優點**</span><span class="sxs-lookup"><span data-stu-id="edb59-127">**Advantages**</span></span> 
- <span data-ttu-id="edb59-128">您不必擔心犯錯在您輸入的 Office 365 服務的 DNS 記錄的值。</span><span class="sxs-lookup"><span data-stu-id="edb59-128">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="edb59-129">您選擇的網域註冊機構和 DNS 主機中有更大的彈性。</span><span class="sxs-lookup"><span data-stu-id="edb59-129">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="edb59-130">可讓您變更名稱伺服器記錄任何提供者將會運作，即使提供者不支援所有必要的記錄類型。</span><span class="sxs-lookup"><span data-stu-id="edb59-130">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="edb59-131">當 Office 365 會新增新的 DNS 記錄時，您不需要進行更新。</span><span class="sxs-lookup"><span data-stu-id="edb59-131">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="edb59-132">缺點</span><span class="sxs-lookup"><span data-stu-id="edb59-132">Disadvantages</span></span> 
- <span data-ttu-id="edb59-133">您無法變更您的 DNS 記錄到 Office 365 外部的主機電子郵件。</span><span class="sxs-lookup"><span data-stu-id="edb59-133">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="edb59-134">如果您已使用的公用網站與您的網域，請在其地址，例如 www.fourthcoffee.com，您必須將重新導向人員至該地址從 Office 365。</span><span class="sxs-lookup"><span data-stu-id="edb59-134">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="edb59-135">設定重新導向需要不一定容易取得的公用網站的靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="edb59-135">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="edb59-136">-如果您目前的網域註冊機構不允許您變更您的網域名稱伺服器記錄，您必須切換到不同的註冊機構，才能使用此 DNS 管理選項。</span><span class="sxs-lookup"><span data-stu-id="edb59-136">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="edb59-137">您的 DNS 記錄自行管理</span><span class="sxs-lookup"><span data-stu-id="edb59-137">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="edb59-138">優點</span><span class="sxs-lookup"><span data-stu-id="edb59-138">Advantages</span></span>
- <span data-ttu-id="edb59-139">您可以控制 Office 365 服務的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="edb59-139">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="edb59-140">如果您有一個公用網站與您的網域，其地址，例如 www.fourthcoffee.com，您不必擔心使用重新導向若要確保人員還是可以至您的網站後您設定 Office 365 中的網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-140">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="edb59-141">您有其他地方，例如與內部部署 Exchange server 的主機電子郵件的彈性。</span><span class="sxs-lookup"><span data-stu-id="edb59-141">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="edb59-142">缺點</span><span class="sxs-lookup"><span data-stu-id="edb59-142">Disadvantages</span></span>
<span data-ttu-id="edb59-143">您必須設定 Office 365 服務的 DNS 記錄自行 （除非您有 GoDaddy 網域）。</span><span class="sxs-lookup"><span data-stu-id="edb59-143">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="edb59-144">如果您目前的 DNS 主機不支援所有必要的記錄類型的 Office 365，某些 Office 365 的功能將無法使用，而且您可能需要切換至不同的 DNS 主機。</span><span class="sxs-lookup"><span data-stu-id="edb59-144">If your current DNS host doesn't support all of the required record types for Office 365, some Office 365 features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="edb59-145">當 Office 365 變更 DNS 記錄的需求，或新增新的服務時，您必須自行進行更新，在您的 DNS 主機。</span><span class="sxs-lookup"><span data-stu-id="edb59-145">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="edb59-146">什麼是網域名稱？</span><span class="sxs-lookup"><span data-stu-id="edb59-146">What is a domain name?</span></span>


<span data-ttu-id="edb59-147">網域是在電子郵件地址的 **@** 符號後，以及網址的 **www.**</span><span class="sxs-lookup"><span data-stu-id="edb59-147">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="edb59-148">後出現的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="edb59-148">in web addresses.</span></span> <span data-ttu-id="edb59-149">它通常採用的表單貴組織的名稱和標準網際網路尾碼組成，例如*yourbusiness.com*或*stateuniversity.edu。*</span><span class="sxs-lookup"><span data-stu-id="edb59-149">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="edb59-150">使用自訂的網域，例如 「**rob\@contoso.com**」 與 Office 365 可協助建立信譽及辨識您的品牌。</span><span class="sxs-lookup"><span data-stu-id="edb59-150">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="edb59-151">您可以[購買 Office 365 中的網域，我們將它自動設定](../get-help-with-domains/buy-a-domain-name.md)，或者您可以購買或帶您已擁有一個向網域註冊機構。</span><span class="sxs-lookup"><span data-stu-id="edb59-151">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="edb59-152">可以轉移我向 Microsoft 購買其他提供者的網域嗎？</span><span class="sxs-lookup"><span data-stu-id="edb59-152">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="edb59-153">是的但您無法 Office 365 網域轉移至另一個登錄器直到 60 天後您購買 Office 365。</span><span class="sxs-lookup"><span data-stu-id="edb59-153">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="edb59-154">請注意*Whois*查詢將會顯示為多西網域 LLC Office 365 購買的網域註冊機構。</span><span class="sxs-lookup"><span data-stu-id="edb59-154">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="edb59-155">不過，只有 Office 365 應該連絡有關您購買的 Office 365 的網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-155">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="edb59-156">請遵循下列步驟來取得 Office 365 程式碼，然後移至其他網域註冊機構的網站，以設定您的網域名稱傳送至該登錄器。</span><span class="sxs-lookup"><span data-stu-id="edb59-156">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>
  
1. <span data-ttu-id="edb59-157">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="edb59-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="edb59-158">如果您使用 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">的網域</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="edb59-158">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="edb59-159">如果您使用 21vianet 運作的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">的網域</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="edb59-159">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="edb59-160">在 [**網域**] 頁面上，選取您想要轉接至其他網域註冊機構，Office 365 網域，然後選取 [**網域傳輸** > **啟用網域傳輸**。</span><span class="sxs-lookup"><span data-stu-id="edb59-160">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="edb59-161">請依照下列步驟來準備轉移您的網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-161">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="edb59-162">取得程式碼之後，移至的網域註冊機構網站您想要用來管理您接下來的網域名稱，並遵循指示其轉送的網域 （在他們網站上的協助搜尋）。</span><span class="sxs-lookup"><span data-stu-id="edb59-162">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="edb59-163">如果您要一次，請參閱程式碼，在 Office 365 中的 [**網域設定**] 頁面上選取 [**網域傳輸時必須使用檢視授權程式碼**。</span><span class="sxs-lookup"><span data-stu-id="edb59-163">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="edb59-164">傳輸完成之後，您將會更新您的網域，在新的網域註冊機構。</span><span class="sxs-lookup"><span data-stu-id="edb59-164">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="edb59-165">若要完成程序，回到系統管理中心**的網域**] 頁面上，選取 [**完整網域傳送**。</span><span class="sxs-lookup"><span data-stu-id="edb59-165">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="edb59-166">*附註： 請注意，Office 365 購買網域是不合格的名稱伺服器變更或 Office 365 租用戶間轉送網域。 如果兩者所需，網域註冊必須轉接至另一個登錄器。*</span><span class="sxs-lookup"><span data-stu-id="edb59-166">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="edb59-167">如何變更我的 DNS 記錄在 Office 365 中的管理方式？</span><span class="sxs-lookup"><span data-stu-id="edb59-167">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="edb59-168">變更為外部 Office 365 的 DNS 主機的 DNS 管理</span><span class="sxs-lookup"><span data-stu-id="edb59-168">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="edb59-169">登入您的網域的網域註冊機構。</span><span class="sxs-lookup"><span data-stu-id="edb59-169">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="edb59-170">尋找您更新名稱伺服器記錄，其中的註冊機構的網站上的區域，並更新為指向您的網域的 DNS 主機的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="edb59-170">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host.</span></span> <span data-ttu-id="edb59-171">（的 DNS 主機通常是網域註冊機構）。</span><span class="sxs-lookup"><span data-stu-id="edb59-171">(The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="edb59-172">請依照下列連結，前往 [網域設定精靈：</span><span class="sxs-lookup"><span data-stu-id="edb59-172">Follow a link to go to the domains setup wizard:</span></span>
    
4. <span data-ttu-id="edb59-173">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="edb59-173">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="edb59-174">如果您使用 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">的網域</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="edb59-174">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="edb59-175">如果您使用 21vianet 運作的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">的網域</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="edb59-175">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
5. <span data-ttu-id="edb59-176">在 [**網域**] 頁面上選取的網域扣款，並選取 [ **DNS 管理**]。</span><span class="sxs-lookup"><span data-stu-id="edb59-176">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="edb59-177">在 [網域設定精靈，在 [**設定您的線上服務**] 頁面上，選取 [**我會管理自己的 DNS 記錄**，，然後選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="edb59-177">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="edb59-178">新增至您的註冊機構網站的 [**更新 DNS 設定**] 頁面上的精靈所建議之 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="edb59-178">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="edb59-179">您已新增記錄之後，回到 Office 365，並選取 [**驗證**。</span><span class="sxs-lookup"><span data-stu-id="edb59-179">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="edb59-180">將 DNS 管理變更為 Office 365</span><span class="sxs-lookup"><span data-stu-id="edb59-180">Change DNS management to Office 365</span></span>
  
1. <span data-ttu-id="edb59-181">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="edb59-181">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="edb59-182">如果您使用 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">的網域</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="edb59-182">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="edb59-183">如果您使用 21vianet 運作的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">的網域</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="edb59-183">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="edb59-184">在 [**網域**] 頁面上選取的網域扣款，並選取 [ **DNS 管理**]。</span><span class="sxs-lookup"><span data-stu-id="edb59-184">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="edb59-185">在 [網域設定精靈，在 [**設定您的線上服務**] 頁面上，選取 [ **Set up my 為我的線上服務。（建議使用）**，然後選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="edb59-185">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="edb59-186">如果您還沒有尚未驗證網域，請遵循先執行的步驟。</span><span class="sxs-lookup"><span data-stu-id="edb59-186">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="edb59-187">在 [ **Update DNS 設定**] 頁面中，我們會列出名稱伺服器的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="edb59-187">On the **Update DNS settings** page, we list the nameservers for Office 365.</span></span> <span data-ttu-id="edb59-188">移至您的網域的網域註冊機構，並更新至 Office 365 名稱伺服器的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="edb59-188">Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="edb59-189">之後您已更新名稱伺服器，**請等候至少一小時**。</span><span class="sxs-lookup"><span data-stu-id="edb59-189">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="edb59-190">然後，回到 [Office 365 中的精靈，選取 [**驗證**。</span><span class="sxs-lookup"><span data-stu-id="edb59-190">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="edb59-191">如果我的 DNS 提供者不支援某些記錄類型，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="edb59-191">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="edb59-192">如果您管理 DNS 記錄，而且您的 DNS 主機不支援 Office 365 所需的所有 DNS 記錄，某些 Office 365 功能將無法使用。</span><span class="sxs-lookup"><span data-stu-id="edb59-192">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work.</span></span> <span data-ttu-id="edb59-193">我們建議您將網域移轉到註冊機構的支援所有必要的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="edb59-193">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="edb59-194">支援所有必要的 DNS 記錄的提供者：</span><span class="sxs-lookup"><span data-stu-id="edb59-194">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="edb59-195">Dynadot</span><span class="sxs-lookup"><span data-stu-id="edb59-195">Dynadot</span></span>
    
- <span data-ttu-id="edb59-196">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="edb59-196">eNomCentral</span></span>
    
- <span data-ttu-id="edb59-197">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="edb59-197">Europe Registry</span></span>
    
- <span data-ttu-id="edb59-198">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="edb59-198">GoDaddy</span></span>
    
- <span data-ttu-id="edb59-199">將游標暫留</span><span class="sxs-lookup"><span data-stu-id="edb59-199">Hover</span></span>
    
- <span data-ttu-id="edb59-200">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="edb59-200">MyHosting.com</span></span>
    
- <span data-ttu-id="edb59-201">Name.com</span><span class="sxs-lookup"><span data-stu-id="edb59-201">Name.com</span></span>
    
- <span data-ttu-id="edb59-202">幾乎空閒語音</span><span class="sxs-lookup"><span data-stu-id="edb59-202">Nearly Free Speech</span></span>
    
- <span data-ttu-id="edb59-203">Nettica</span><span class="sxs-lookup"><span data-stu-id="edb59-203">Nettica</span></span>
    
- <span data-ttu-id="edb59-204">網際網路資訊中心 (NIC)</span><span class="sxs-lookup"><span data-stu-id="edb59-204">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="edb59-205">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="edb59-205">Network Solutions</span></span>
    
- <span data-ttu-id="edb59-206">Register.com</span><span class="sxs-lookup"><span data-stu-id="edb59-206">Register.com</span></span>
    
 <span data-ttu-id="edb59-207">**不支援如果 SRV 記錄**，Office 365 不的可用功能如下：</span><span class="sxs-lookup"><span data-stu-id="edb59-207">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="edb59-208">商務用 Skype 商務 Online IM 和目前狀態整合與 Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="edb59-208">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="edb59-209">外部通訊 （同盟） 與 Skype 商務 Online 其他組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="edb59-209">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="edb59-210">與 Skype for Business Online 使用者的公用網際網路連線能力 (PIC) 登入 Microsoft 帳戶 （以前稱為 Windows Live ID）。</span><span class="sxs-lookup"><span data-stu-id="edb59-210">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="edb59-211">**如果不支援多個 CNAME 記錄，** 您必須選擇商務用 Skype 的下列功能：</span><span class="sxs-lookup"><span data-stu-id="edb59-211">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="edb59-212">電子郵件桌面用戶端和行動用戶端可以使用自動探索來自動尋找 Exchange Online 服務，以便使用者可以登入，而不必輸入伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="edb59-212">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="edb59-213">Skype 商務 Online 桌面用戶端可用於自動探索自動尋找 Skype 商務 Online 服務，讓使用者可以登入，而不必輸入伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="edb59-213">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="edb59-214">Skype 商務 Online 行動用戶端可用於自動探索自動尋找 Skype 商務 Online 服務，讓使用者可以登入，而不必輸入伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="edb59-214">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
 <span data-ttu-id="edb59-215">**如果 SPF/TXT 記錄不受支援**，其他人可能無法使用您的網域來傳送垃圾郵件或其他惡意電子郵件。</span><span class="sxs-lookup"><span data-stu-id="edb59-215">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email.</span></span> <span data-ttu-id="edb59-216">SPF 記錄運作識別來自您網域傳送電子郵件會獲授權的伺服器。</span><span class="sxs-lookup"><span data-stu-id="edb59-216">SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="edb59-217">如何設定或變更 Office 365 中的預設網域？</span><span class="sxs-lookup"><span data-stu-id="edb59-217">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="edb59-218">您必須至少一個自訂的網域，您可以選擇預設網域之前，已新增至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="edb59-218">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>
  
1. <span data-ttu-id="edb59-219">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="edb59-219">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="edb59-220">如果您使用 Office 365 Germany，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">的網域</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="edb59-220">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="edb59-221">如果您使用 21vianet 運作的 Office 365，請移至此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">的網域</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="edb59-221">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="edb59-222">在 [**網域**] 頁面上，選取您想要設定為預設值為新的電子郵件地址的網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-222">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="edb59-223">選取 [**設成預設值**。</span><span class="sxs-lookup"><span data-stu-id="edb59-223">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="edb59-224">您無法變更自己的初始名稱 *。 onmicrosoft.com*網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-224">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="edb59-225">您無法變更自己的初始名稱 *。 onmicrosoft.de*網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-225">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="edb59-226">您無法變更自己的初始名稱 *。 partner.onmschina.cn*網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-226">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="edb59-227">新增自訂的子網域或多個網域到 Office 365？</span><span class="sxs-lookup"><span data-stu-id="edb59-227">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="edb59-228">Yes ！</span><span class="sxs-lookup"><span data-stu-id="edb59-228">Yes!</span></span> <span data-ttu-id="edb59-229">若要新增子網域，您必須管理自己的 DNS 設定，在您的註冊機構網站。</span><span class="sxs-lookup"><span data-stu-id="edb59-229">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="edb59-230">如果您要讓 Microsoft 管理您的 DNS 設定 NS 記錄，或如果您向 Microsoft 購買網域，您無法新增子網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-230">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="edb59-231">Yes ！</span><span class="sxs-lookup"><span data-stu-id="edb59-231">Yes!</span></span> <span data-ttu-id="edb59-232">若要新增子網域，您必須管理自己的 DNS 設定，在您的註冊機構網站。</span><span class="sxs-lookup"><span data-stu-id="edb59-232">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="edb59-233">如果您要讓 Microsoft 管理您的 DNS 設定 NS 記錄，或如果您向 Microsoft 購買網域，您無法新增子網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-233">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="edb59-234">Yes ！</span><span class="sxs-lookup"><span data-stu-id="edb59-234">Yes!</span></span> <span data-ttu-id="edb59-235">若要新增子網域，您必須管理自己的 DNS 設定，在您的註冊機構網站。</span><span class="sxs-lookup"><span data-stu-id="edb59-235">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="edb59-236">如果您要讓 21Vianet 管理您的 NS 記錄的 DNS 設定，您無法新增子網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-236">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="edb59-237">一般而言，您可以新增多達 900 個網域到 Office 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="edb59-237">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="edb59-238">例如，您無法新增網域 contoso.com 和 contosomarketing.com，，然後再新增子網域 www.contoso.com、 www.partners.contoso.com、 www.partners.marketing.contoso.com，依此類推。</span><span class="sxs-lookup"><span data-stu-id="edb59-238">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="edb59-239">當您新增子網域時，會自動驗證並已確認父系網域為基礎。</span><span class="sxs-lookup"><span data-stu-id="edb59-239">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="edb59-240">當您將多個網域新增至 Office 365 時，您可以在任何已新增的網域上裝載任何服務 （例如電子郵件）。</span><span class="sxs-lookup"><span data-stu-id="edb59-240">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="edb59-241">*當您變更您的電子郵件到 Office 365，藉由更新網域的 MX 記錄時，傳送至該網域的所有電子郵件都會開始送往 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="edb59-241">*When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="edb59-242">如果您已新增 contoso.com 網域至 Office 365 租用戶，您也可以新增子網域 xyz.contoso.com 到另一個 Office 365 租用戶。</span><span class="sxs-lookup"><span data-stu-id="edb59-242">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="edb59-243">當新增子網域，系統將提示您 DNS 主機服務提供者中新增 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="edb59-243">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="edb59-244">為什麼有 「 onmicrosoft.com"網域？</span><span class="sxs-lookup"><span data-stu-id="edb59-244">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="edb59-245">Office 365 網域為您建立，例如*contoso.onmicrosoft.com*，當您註冊的服務。</span><span class="sxs-lookup"><span data-stu-id="edb59-245">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="edb59-246">當您註冊您建立的使用者識別碼包含的網域，例如*alan@contoso.onmicrosoft.com*。</span><span class="sxs-lookup"><span data-stu-id="edb59-246">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="edb59-247">**如果您想要有您的電子郵件看起來像*alan\@contoso.com*:** [購買網域](../get-help-with-domains/buy-a-domain-name.md)，或如果您已擁有只是依照中[新增您的使用者與網域至 Office 365](add-domain.md)的步驟。</span><span class="sxs-lookup"><span data-stu-id="edb59-247">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="edb59-248">**您無法重新命名後的 onmicrosoft 網域註冊。**</span><span class="sxs-lookup"><span data-stu-id="edb59-248">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="edb59-249">例如，如果您選擇的初始網域 fourthcoffee.onmicrosoft.com，您無法變更其設為 fabrikam.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="edb59-249">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="edb59-250">若要使用不同的 onmicrosoft.com 網域，您必須使用 Office 365 中開始新的訂閱。</span><span class="sxs-lookup"><span data-stu-id="edb59-250">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="edb59-251">**您無法重新命名您的小組網站 URL。**</span><span class="sxs-lookup"><span data-stu-id="edb59-251">**You can't rename your team site URL.**</span></span> <span data-ttu-id="edb59-252">您的小組網站 URL 根據您的 onmicrosoft.com 網域名稱。</span><span class="sxs-lookup"><span data-stu-id="edb59-252">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="edb59-253">不幸的是，因為 SharePoint Online 的架構的運作方式，您無法重新命名小組網站。</span><span class="sxs-lookup"><span data-stu-id="edb59-253">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="edb59-254">**您無法移除 onmicrosoft 網域。**</span><span class="sxs-lookup"><span data-stu-id="edb59-254">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="edb59-255">Office 365 需要保留其周圍，因為它在幕後用於您的訂閱。</span><span class="sxs-lookup"><span data-stu-id="edb59-255">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="edb59-256">但您不需要使用網域自行後您已新增自訂的網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-256">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="edb59-257">您可以繼續使用初始的 onmicrosoft.com 網域即使之後新增您的網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-257">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="edb59-258">它仍適用於電子郵件和其他服務，因此您可以選擇。</span><span class="sxs-lookup"><span data-stu-id="edb59-258">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="edb59-259">為什麼有 「 onmicrosoft.de 」 網域？</span><span class="sxs-lookup"><span data-stu-id="edb59-259">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="edb59-260">Office 365 網域為您建立，例如*contoso.onmicrosoft.de*，當您註冊的服務。</span><span class="sxs-lookup"><span data-stu-id="edb59-260">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="edb59-261">當您註冊您建立的使用者識別碼包含的網域，例如*alan@contoso.onmicrosoft.de*。</span><span class="sxs-lookup"><span data-stu-id="edb59-261">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="edb59-262">**如果您想要有您的電子郵件看起來像*alan@contoso.de*:** [購買網域](../get-help-with-domains/buy-a-domain-name.md)，或如果您已擁有只是依照中[新增您的使用者與網域至 Office 365](add-domain.md)的步驟。</span><span class="sxs-lookup"><span data-stu-id="edb59-262">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="edb59-263">**您無法重新命名後的 onmicrosoft 網域註冊。**</span><span class="sxs-lookup"><span data-stu-id="edb59-263">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="edb59-264">例如，如果您選擇的初始網域 fourthcoffee.onmicrosoft.de，您無法變更它 fabrikam.onmicrosoft.de。</span><span class="sxs-lookup"><span data-stu-id="edb59-264">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="edb59-265">若要使用不同的 onmicrosoft.de 網域，您必須使用 Office 365 中開始新的訂閱。</span><span class="sxs-lookup"><span data-stu-id="edb59-265">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="edb59-266">**您無法重新命名您的小組網站 URL。**</span><span class="sxs-lookup"><span data-stu-id="edb59-266">**You can't rename your team site URL.**</span></span> <span data-ttu-id="edb59-267">您的小組網站 URL 根據您的 onmicrosoft.de 網域名稱。不幸的是，因為 SharePoint Online 的架構的運作方式，您無法重新命名小組網站。</span><span class="sxs-lookup"><span data-stu-id="edb59-267">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="edb59-268">**您無法移除 onmicrosoft 網域。**</span><span class="sxs-lookup"><span data-stu-id="edb59-268">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="edb59-269">Office 365 需要保留其周圍，因為它在幕後用於您的訂閱。</span><span class="sxs-lookup"><span data-stu-id="edb59-269">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="edb59-270">但您不需要使用網域自行後您已新增自訂的網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-270">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="edb59-271">您可以繼續使用初始 onmicrosoft.de 網域即使之後新增您的網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-271">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="edb59-272">它仍適用於電子郵件和其他服務，因此您可以選擇。</span><span class="sxs-lookup"><span data-stu-id="edb59-272">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="edb59-273">如何確認我非營利組織版或教育版的狀態？</span><span class="sxs-lookup"><span data-stu-id="edb59-273">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="edb59-274">在[系統管理中心](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx)來啟動精靈，請選取 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="edb59-274">Select **Setup** in the [admin center](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) to start the wizard.</span></span> <span data-ttu-id="edb59-275">（請務必先登入 Office 365）。</span><span class="sxs-lookup"><span data-stu-id="edb59-275">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="edb59-276">若要成為系統管理員為您的學校，選取 [**成為系統管理員**選項在 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="edb59-276">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="edb59-277">系統會提示您在您網域的 DNS 主機網站上新增 TXT DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="edb59-277">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="edb59-278">為什麼？</span><span class="sxs-lookup"><span data-stu-id="edb59-278">Why?</span></span> <span data-ttu-id="edb59-279">因為在 DNS 主機登入，並新增您的網域的記錄，您證明到 Office 365 您擁有的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="edb59-279">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="edb59-280">新增記錄之後，您會回到 Office 365 入口網站，並確認您已新增它，因此可以檢查 Office 365。</span><span class="sxs-lookup"><span data-stu-id="edb59-280">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="edb59-281">有非營利組織版，且想要取得 Office 365？</span><span class="sxs-lookup"><span data-stu-id="edb59-281">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="edb59-282">[請確定您的組織符合要求](https://www.microsoft.com/en-us/nonprofits/eligibility)，然後註冊服務。</span><span class="sxs-lookup"><span data-stu-id="edb59-282">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="edb59-283">想要深入了解成為您學校的系統管理員嗎？</span><span class="sxs-lookup"><span data-stu-id="edb59-283">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="edb59-284">[解它](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。</span><span class="sxs-lookup"><span data-stu-id="edb59-284">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="edb59-285">可以我試驗 Office 365 與幾電子郵件地址從我的自訂網域？</span><span class="sxs-lookup"><span data-stu-id="edb59-285">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="edb59-286">您可以但有一些限制：</span><span class="sxs-lookup"><span data-stu-id="edb59-286">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="edb59-287">您目前的電子郵件提供者必須提供電子郵件轉寄功能。</span><span class="sxs-lookup"><span data-stu-id="edb59-287">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="edb59-288">管理您的 Office 365 相關的 DNS 記錄，在 DNS 主機服務提供者，所需，而不是具有 Office 365 為您管理這些記錄。</span><span class="sxs-lookup"><span data-stu-id="edb59-288">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="edb59-289">若要了解這項功能的需要，請參閱新增網域至 Office 365 時您想要管理自己的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="edb59-289">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="edb59-290">某些 Office 365 的功能將無法使用：</span><span class="sxs-lookup"><span data-stu-id="edb59-290">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="edb59-291">使用者將無法看到其他電子郵件提供者上使用者的空閒/忙碌資訊。</span><span class="sxs-lookup"><span data-stu-id="edb59-291">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="edb59-292">系統管理員將無法從一個地方管理所有人的帳戶。</span><span class="sxs-lookup"><span data-stu-id="edb59-292">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="edb59-293">使用者可能無法使用 Office 365 垃圾郵件篩選</span><span class="sxs-lookup"><span data-stu-id="edb59-293">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="edb59-294">如何設定 Office 365 試驗部署</span><span class="sxs-lookup"><span data-stu-id="edb59-294">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="edb59-295">登入 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="edb59-295">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="edb59-296">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="edb59-296">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="edb59-297">移至 [**設定** \> **網域**。</span><span class="sxs-lookup"><span data-stu-id="edb59-297">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="edb59-298">驗證您擁有您想要使用的網域</span><span class="sxs-lookup"><span data-stu-id="edb59-298">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="edb59-299">在 [**網域**] 頁面上選取 [**新增網域**]。</span><span class="sxs-lookup"><span data-stu-id="edb59-299">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="edb59-300">在面板中，輸入網域，在此範例 cohowinery.com，，然後選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="edb59-300">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="edb59-301">在**驗證**網域] 頁面上，依照逐步指示。</span><span class="sxs-lookup"><span data-stu-id="edb59-301">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="edb59-302">在下拉式清單中，選取 [DNS 主機服務提供者，並遵循指示來顯示您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-302">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="edb59-303">選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="edb59-303">Select **Verify**.</span></span> <span data-ttu-id="edb59-304">花幾分鐘的時間和 72 小時，才會生效的 DNS 變更之間。</span><span class="sxs-lookup"><span data-stu-id="edb59-304">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="edb59-305">驗證成功時，系統會要求您修改您的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="edb59-305">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="edb59-306">標記為 Exchange Online 中共用的網域</span><span class="sxs-lookup"><span data-stu-id="edb59-306">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="edb59-307">移至**Exchange 系統管理中心**(EAC)。</span><span class="sxs-lookup"><span data-stu-id="edb59-307">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="edb59-308">在 [**郵件流程**] 區段中，選取 **[公認的網域**。</span><span class="sxs-lookup"><span data-stu-id="edb59-308">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="edb59-309">按兩下您要修改的網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-309">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="edb59-310">在開啟視窗中，選取 [**內部轉送**]。</span><span class="sxs-lookup"><span data-stu-id="edb59-310">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="edb59-311">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="edb59-311">Select **Save**.</span></span> <span data-ttu-id="edb59-312">此設定可能需要幾分鐘的時間才會生效。</span><span class="sxs-lookup"><span data-stu-id="edb59-312">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="edb59-313">（選用） 解除封鎖在現有的電子郵件伺服器</span><span class="sxs-lookup"><span data-stu-id="edb59-313">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="edb59-314">Office 365 會使用 Exchange Online Protection (EOP) 的垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="edb59-314">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="edb59-315">如果 EOP 偵測到大量垃圾郵件轉寄您目前的郵件伺服器，可能會封鎖，以防止轉寄功能無法運作。</span><span class="sxs-lookup"><span data-stu-id="edb59-315">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="edb59-316">如果您有自信與垃圾郵件保護您電子郵件提供者使用，您可以 whitelist 他們在 Office 365 中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="edb59-316">If you are confident with the spam protection your other email provider uses, you can whitelist their server in Office 365.</span></span> <span data-ttu-id="edb59-317">不過，這也可讓送達您原始的伺服器到 Office 365 信箱、 來自透過任何垃圾郵件，而且您將無法評估 Office 365 如何防止垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="edb59-317">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="edb59-318">移至 Exchange 系統管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="edb59-318">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="edb59-319">在 EAC 中，選取 [**保護**]，然後選取**連線篩選器**。</span><span class="sxs-lookup"><span data-stu-id="edb59-319">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="edb59-320">在**IP 允許清單**中，選取 [ **+**，並新增您可以從目前的電子郵件提供者取得的郵件伺服器 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="edb59-320">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="edb59-321">建立使用者帳戶，並設定主要 (回覆-to) 地址</span><span class="sxs-lookup"><span data-stu-id="edb59-321">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="edb59-322">移至 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="edb59-322">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="edb59-323">在左的導覽列中，選取 [**使用者** \> **作用中的使用者**。</span><span class="sxs-lookup"><span data-stu-id="edb59-323">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="edb59-324">建立使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="edb59-324">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="edb59-325">每個帳戶選取 **+ （新增）**，並填寫所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="edb59-325">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="edb59-326">若要保留使用者的電子郵件相同為它目前正被，**使用者名稱**] 欄位應完全使用者的現有電子郵件地址相同。</span><span class="sxs-lookup"><span data-stu-id="edb59-326">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="edb59-327">使用者名稱] 旁邊，從下拉式清單中選取您的自訂網域名稱。</span><span class="sxs-lookup"><span data-stu-id="edb59-327">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="edb59-328">選取 [**建立** \> **關閉**。</span><span class="sxs-lookup"><span data-stu-id="edb59-328">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="edb59-329">更新 DNS 主機服務提供者的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="edb59-329">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="edb59-330">登入您 DNS 主機服務提供者的網站，並遵循[Office 365 步驟任何 DNS 主機服務提供者處建立 DNS 記錄](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="edb59-330">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="edb59-331">**進行下列例外：**</span><span class="sxs-lookup"><span data-stu-id="edb59-331">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="edb59-332">請勿建立新的 MX 記錄或變更現有的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="edb59-332">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="edb59-333">如果您已為您舊的電子郵件提供者的寄件者原則架構 (SPF) 記錄，而不是建立新的 SPF (TXT) 記錄的 Exchange Online 中，剛加入 「 include: spf.protection.outlook.com 「 目前的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="edb59-333">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="edb59-334">例如，「 v = spf1 mx include:adatum.com include: spf.protection.outlook.com ~ 所有 」。</span><span class="sxs-lookup"><span data-stu-id="edb59-334">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="edb59-335">如果您不具備 SPF 記錄，修改，故 Office 365 所要包含您目前的電子郵件提供者，再加上 spf.protection.outlook.com 的網域。</span><span class="sxs-lookup"><span data-stu-id="edb59-335">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="edb59-336">這會授與來自這兩個電子郵件系統的外寄郵件。</span><span class="sxs-lookup"><span data-stu-id="edb59-336">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="edb59-337">設定在您目前的提供者的電子郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="edb59-337">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="edb59-338">在您目前的電子郵件提供者，設定為您的使用者轉接至您的 onmicrosoft.com 網域的電子郵件帳戶：</span><span class="sxs-lookup"><span data-stu-id="edb59-338">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="edb59-339">使用者 A 的信箱應轉寄給 usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="edb59-339">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="edb59-340">使用者 B 的信箱應轉寄給 userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="edb59-340">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="edb59-341">當您完成此步驟：</span><span class="sxs-lookup"><span data-stu-id="edb59-341">When you complete this step:</span></span>
        
    5. <span data-ttu-id="edb59-342">所有傳送到 usera@yourcompany.com 和 userb@yourcompany.com 郵件則可在 Office 365。</span><span class="sxs-lookup"><span data-stu-id="edb59-342">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="edb59-343">附註：</span><span class="sxs-lookup"><span data-stu-id="edb59-343">Notes:</span></span>
        
        - <span data-ttu-id="edb59-344">如需設定轉寄的確切步驟連絡您目前的電子郵件提供者。</span><span class="sxs-lookup"><span data-stu-id="edb59-344">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="edb59-345">您不需要保留在目前的電子郵件提供者的郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="edb59-345">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="edb59-346">大部分提供者轉寄電子郵件離開寄件者的回覆地址不變，以便回覆移至原始寄件者。</span><span class="sxs-lookup"><span data-stu-id="edb59-346">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="edb59-347">測試郵件流程</span><span class="sxs-lookup"><span data-stu-id="edb59-347">Test mail flow</span></span>
    
    1. <span data-ttu-id="edb59-348">登入 Outlook Web App 使用者 A 的認證。</span><span class="sxs-lookup"><span data-stu-id="edb59-348">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="edb59-349">執行下列測試：</span><span class="sxs-lookup"><span data-stu-id="edb59-349">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="edb59-350">測試本機的 Office 365 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="edb59-350">Test local Office 365 email.</span></span> <span data-ttu-id="edb59-351">例如，傳送電子郵件給使用者 b。應該會立即傳遞這封電子郵件。</span><span class="sxs-lookup"><span data-stu-id="edb59-351">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="edb59-352">在此案例中，郵件將不會路由傳送到原始的伺服器上的使用者 B 的信箱因為 Office 365 會為本機看到該信箱。</span><span class="sxs-lookup"><span data-stu-id="edb59-352">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="edb59-353">測試電子郵件給其他電子郵件系統上的任何人。</span><span class="sxs-lookup"><span data-stu-id="edb59-353">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="edb59-354">例如，傳送電子郵件給使用者 c。這封電子郵件應該傳遞至原始的郵件伺服器上的 C 使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="edb59-354">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="edb59-355">從外部的帳戶，或從其他電子郵件系統上的員工的電子郵件帳戶，請確認轉寄已正確設定，其他電子郵件系統上。</span><span class="sxs-lookup"><span data-stu-id="edb59-355">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="edb59-356">例如，從使用者 C origninal 伺服器帳戶或 Hotmail 帳戶，使用者傳送的電子郵件，並確認它送達使用者 A 的 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="edb59-356">For example, from User C's origninal server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="edb59-357">移動信箱內容</span><span class="sxs-lookup"><span data-stu-id="edb59-357">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="edb59-358">由於有移動，只有兩位使用者，因為使用者 A 和 B 使用者都使用 Outlook 已可以藉由開啟舊移動電子郵件。在 [新的 Outlook 設定檔並複製郵件、 行事曆項目、 連絡人、 等，從 Outlook 資料檔 (.pst) 匯入 Outlook 項目中所示的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="edb59-358">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="edb59-359">一旦組織中的 Office 365 信箱中的適當位置、 項目所有可從任何裝置，任何地方。</span><span class="sxs-lookup"><span data-stu-id="edb59-359">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="edb59-360">當涉及多個信箱時，或員工您尚未使用 Outlook，您可以使用可用的移轉工具在 Exchange 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="edb59-360">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="edb59-361">若要開始，移至 Exchange 系統管理中心，並按照指示中遷移電子郵件從 IMAP 伺服器至 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="edb59-361">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
