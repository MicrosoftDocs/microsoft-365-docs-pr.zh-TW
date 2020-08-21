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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: 找到您常見問題的答案以深入瞭解網域。
ms.openlocfilehash: fe602c45059be1b273b7ebe3a11cd91adf89a479
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845841"
---
# <a name="domains-faq"></a><span data-ttu-id="54955-103">網域常見問題集</span><span class="sxs-lookup"><span data-stu-id="54955-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="54955-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="54955-104">The admin center is changing.</span></span> <span data-ttu-id="54955-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="54955-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="54955-106">本文包含有關 Microsoft 365 中網域的常見問題解答。</span><span class="sxs-lookup"><span data-stu-id="54955-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="54955-107">如果您找不到問題的答案，請留言讓我們知道，我們會將它新增至清單。</span><span class="sxs-lookup"><span data-stu-id="54955-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="54955-108">本文內容</span><span class="sxs-lookup"><span data-stu-id="54955-108">In this article</span></span>

- [<span data-ttu-id="54955-109">什麼是 MX 優先順序？</span><span class="sxs-lookup"><span data-stu-id="54955-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="54955-110">如何驗證我的網域的 SPF 記錄？</span><span class="sxs-lookup"><span data-stu-id="54955-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="54955-111">何謂功能變數名稱？</span><span class="sxs-lookup"><span data-stu-id="54955-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="54955-112">如果我的 DNS 提供者不支援某些記錄類型，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="54955-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="54955-113">如何在 Microsoft 365 中設定或變更預設網域？</span><span class="sxs-lookup"><span data-stu-id="54955-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="54955-114">我可以將自訂子域或多個網域新增至 Microsoft 365 嗎？</span><span class="sxs-lookup"><span data-stu-id="54955-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="54955-115">如何將網域從 Microsoft 365 傳輸到另一部主機？</span><span class="sxs-lookup"><span data-stu-id="54955-115">How do I transfer a domain from Microsoft 365 to another host?</span></span>](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [<span data-ttu-id="54955-116">為什麼我有「onmicrosoft.com」網域？</span><span class="sxs-lookup"><span data-stu-id="54955-116">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="54955-117">為什麼我有「onmicrosoft.de」網域？</span><span class="sxs-lookup"><span data-stu-id="54955-117">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="54955-118">如何驗證我的非盈利性或教育狀態？</span><span class="sxs-lookup"><span data-stu-id="54955-118">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="54955-119">什麼是 MX 優先順序？</span><span class="sxs-lookup"><span data-stu-id="54955-119">What is MX priority?</span></span>

<span data-ttu-id="54955-120">郵件會以最低喜好設定值傳送到郵件 exchange 伺服器， (最高優先順序) ，所以您用來進行郵件路由的 MX 記錄應該會有最低的喜好設定值，通常是0或  *高*  優先順序。</span><span class="sxs-lookup"><span data-stu-id="54955-120">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="54955-121">當您建立 MX 記錄時，大部分的 DNS 主機服務提供者要求您設定偏好設定號碼。</span><span class="sxs-lookup"><span data-stu-id="54955-121">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="54955-122">某些標籤的方塊  *偏好*  ，有些標籤  *優先順序*  。</span><span class="sxs-lookup"><span data-stu-id="54955-122">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="54955-123">有些需要數位，有些會要求您選取 [  *低*  ]、[  *中*  ] 或 [  *高*  ]。</span><span class="sxs-lookup"><span data-stu-id="54955-123">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="54955-124">如果您只有一個 MX 記錄，則優先順序或喜好設定的任何值都很好。</span><span class="sxs-lookup"><span data-stu-id="54955-124">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="54955-125">如果您有一個以上的，請確定郵件路由的 MX 記錄的優先順序高於用於驗證您擁有該網域的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="54955-125">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="54955-126">如何驗證我的網域的 SPF 記錄？</span><span class="sxs-lookup"><span data-stu-id="54955-126">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="54955-127">您必須具有或建立  **一個 SPF 的 TXT 記錄**，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="54955-127">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="54955-128">如果您已經有 SPF 記錄，應將新的 Microsoft 365 值附加到它，而不是建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="54955-128">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="54955-129">在您新增或更新 Microsoft 電子郵件的 SPF 記錄之後，您應該檢查下列其中一項工具，確定語法是否正確：</span><span class="sxs-lookup"><span data-stu-id="54955-129">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="54955-130">SPF 記錄測試控管</span><span class="sxs-lookup"><span data-stu-id="54955-130">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="54955-131">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="54955-131">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="54955-132">挖出 web 介面</span><span class="sxs-lookup"><span data-stu-id="54955-132">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="54955-133">何謂功能變數名稱？</span><span class="sxs-lookup"><span data-stu-id="54955-133">What is a domain name?</span></span>

<span data-ttu-id="54955-134">網域是在電子郵件地址的 **@** 符號後，以及網址的 **www.**</span><span class="sxs-lookup"><span data-stu-id="54955-134">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="54955-135">後出現的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="54955-135">in web addresses.</span></span> <span data-ttu-id="54955-136">它通常採用組織名稱和標準 Internet 尾碼的形式，例如  *yourbusiness.com*  或  *stateuniversity.edu。*</span><span class="sxs-lookup"><span data-stu-id="54955-136">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="54955-137">使用自訂網域（例如「可信性\*\* \@ contoso.com\*\*」）與 Microsoft 365，可協助您建立品牌的信譽及認可。</span><span class="sxs-lookup"><span data-stu-id="54955-137">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="54955-138">您可以 [在 Microsoft 365 中購買網域，我們會自動加以設定](../get-help-with-domains/buy-a-domain-name.md)，或者您可以從網域註冊機構購買或為您提供自己的現有功能。</span><span class="sxs-lookup"><span data-stu-id="54955-138">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="54955-139">如果我的 DNS 提供者不支援某些記錄類型，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="54955-139">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="54955-140">如果您管理自己的 DNS 記錄，而且 DNS 主機不支援 Microsoft 365 所需的所有 DNS 記錄，有些 Microsoft 365 功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="54955-140">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="54955-141">建議您將網域轉接至支援所有必要 DNS 記錄的註冊機構。</span><span class="sxs-lookup"><span data-stu-id="54955-141">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="54955-142">支援所有必要 DNS 記錄的提供者：</span><span class="sxs-lookup"><span data-stu-id="54955-142">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="54955-143">Dynadot</span><span class="sxs-lookup"><span data-stu-id="54955-143">Dynadot</span></span>
    
- <span data-ttu-id="54955-144">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="54955-144">eNomCentral</span></span>
    
- <span data-ttu-id="54955-145">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="54955-145">Europe Registry</span></span>
    
- <span data-ttu-id="54955-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="54955-146">GoDaddy</span></span>
    
- <span data-ttu-id="54955-147">懸停</span><span class="sxs-lookup"><span data-stu-id="54955-147">Hover</span></span>
    
- <span data-ttu-id="54955-148">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="54955-148">MyHosting.com</span></span>
    
- <span data-ttu-id="54955-149">Name.com</span><span class="sxs-lookup"><span data-stu-id="54955-149">Name.com</span></span>
    
- <span data-ttu-id="54955-150">幾乎自由語音</span><span class="sxs-lookup"><span data-stu-id="54955-150">Nearly Free Speech</span></span>
    
- <span data-ttu-id="54955-151">Nettica</span><span class="sxs-lookup"><span data-stu-id="54955-151">Nettica</span></span>
    
- <span data-ttu-id="54955-152">網際網路資訊中心 (NIC)</span><span class="sxs-lookup"><span data-stu-id="54955-152">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="54955-153">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="54955-153">Network Solutions</span></span>
    
- <span data-ttu-id="54955-154">Register.com</span><span class="sxs-lookup"><span data-stu-id="54955-154">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="54955-155">如何在 Microsoft 365 中設定或變更預設網域？</span><span class="sxs-lookup"><span data-stu-id="54955-155">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="54955-156">您必須至少有一個自訂網域新增至 Microsoft 365，您才能選擇預設網域。</span><span class="sxs-lookup"><span data-stu-id="54955-156">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="54955-157">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="54955-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="54955-158">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="54955-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="54955-159">在系統管理中心中，移至 **[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="54955-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="54955-160">在 [ **網域** ] 頁面上，選取您要設定為新電子郵件地址的預設網域。</span><span class="sxs-lookup"><span data-stu-id="54955-160">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="54955-161">選取 [設定成預設值]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54955-161">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="54955-162">您無法變更  *onmicrosoft.com*  網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="54955-162">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="54955-163">您無法變更  *onmicrosoft.de*  網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="54955-163">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="54955-164">您無法變更  *partner.onmschina.cn*  網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="54955-164">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="54955-165">我可以將自訂子域或多個網域新增至 Microsoft 365 嗎？</span><span class="sxs-lookup"><span data-stu-id="54955-165">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="54955-166">是。</span><span class="sxs-lookup"><span data-stu-id="54955-166">Yes.</span></span> <span data-ttu-id="54955-167">若要新增子域，您必須在註冊機構網站上管理自己的 DNS 設定。</span><span class="sxs-lookup"><span data-stu-id="54955-167">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="54955-168">如果您要讓 Microsoft 使用 NS 記錄來管理您的 DNS 設定，或者您購買的是 Microsoft 的網域，您就無法新增子域。</span><span class="sxs-lookup"><span data-stu-id="54955-168">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="54955-169">是的！</span><span class="sxs-lookup"><span data-stu-id="54955-169">Yes!</span></span> <span data-ttu-id="54955-170">若要新增子域，您必須在註冊機構網站上管理自己的 DNS 設定。</span><span class="sxs-lookup"><span data-stu-id="54955-170">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="54955-171">如果您要讓 Microsoft 使用 NS 記錄來管理您的 DNS 設定，或者您購買的是 Microsoft 的網域，您就無法新增子域。</span><span class="sxs-lookup"><span data-stu-id="54955-171">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="54955-172">是的！</span><span class="sxs-lookup"><span data-stu-id="54955-172">Yes!</span></span> <span data-ttu-id="54955-173">若要新增子域，您必須在註冊機構網站上管理自己的 DNS 設定。</span><span class="sxs-lookup"><span data-stu-id="54955-173">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="54955-174">如果您是讓世紀以 NS 記錄來管理您的 DNS 設定，就無法新增子域。</span><span class="sxs-lookup"><span data-stu-id="54955-174">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="54955-175">一般來說，您最多可以將900個網域新增至您的 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="54955-175">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="54955-176">例如，您可以新增網域 contoso.com 及 contosomarketing.com，然後新增子域 www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com 等等。</span><span class="sxs-lookup"><span data-stu-id="54955-176">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="54955-177">當您新增子域時，會根據所驗證的父系網域，自動驗證。</span><span class="sxs-lookup"><span data-stu-id="54955-177">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="54955-178">當您將多個網域新增至 Microsoft 365 時，您可以在您已新增的任何網域上，主控任何服務 (例如電子郵件) ）。</span><span class="sxs-lookup"><span data-stu-id="54955-178">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="54955-179">*當您將電子郵件變更為 Microsoft 365 時，更新網域的 MX 記錄，所有傳送至該網域的電子郵件都會開始成為 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="54955-179">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="54955-180">如果您已將 contoso.com 網域新增至 Microsoft 365 訂閱，您也可以將子域 xyz.contoso.com 新增至其他 Microsoft 365 組織。</span><span class="sxs-lookup"><span data-stu-id="54955-180">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="54955-181">新增子域時，系統會提示您在 DNS 主機服務提供者中新增 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="54955-181">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a><span data-ttu-id="54955-182">如何將網域從 Microsoft 365 傳輸到另一部主機？</span><span class="sxs-lookup"><span data-stu-id="54955-182">How do I transfer a domain from Microsoft 365 to another host?</span></span>

<span data-ttu-id="54955-183">如需傳輸網域的程式，請參閱將 [網域從 Microsoft 轉接至其他主機](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host)。</span><span class="sxs-lookup"><span data-stu-id="54955-183">For the procedure to transfer a domain, see [Transfer a domain from Microsoft to another host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span></span>

## <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="54955-184">從我的自訂網域試驗 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="54955-184">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="54955-185">如需試用自自訂網域至 Microsoft 365 信箱的 Microsoft 365 電子郵件功能的程式，請參閱 [從我的自訂網域試用 microsoft 365](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain)。</span><span class="sxs-lookup"><span data-stu-id="54955-185">For the procedure to pilot Microsoft 365 email functionality from a custom domain to a Microsoft 365 mailbox, see [Pilot Microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="54955-186">為什麼我有「onmicrosoft.com」網域？</span><span class="sxs-lookup"><span data-stu-id="54955-186">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="54955-187">當您註冊服務時，Microsoft 365 會為您建立網域，例如 *contoso.onmicrosoft.com*。</span><span class="sxs-lookup"><span data-stu-id="54955-187">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="54955-188">您註冊時所建立的使用者識別碼包含網域，如 *alan@contoso.onmicrosoft.com*。</span><span class="sxs-lookup"><span data-stu-id="54955-188">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="54955-189">**如果您想要讓您的電子郵件看起來像是 *alan \@ contoso.com*：** [購買網域](../get-help-with-domains/buy-a-domain-name.md) ，或是只要您擁有現有的使用者和網域中的步驟，即可執行 [ [將您的使用者與網域新增至 Microsoft 365](add-domain.md) ]。</span><span class="sxs-lookup"><span data-stu-id="54955-189">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="54955-190">**您無法在註冊後重新命名 name.onmicrosoft.com17 網域。**</span><span class="sxs-lookup"><span data-stu-id="54955-190">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="54955-191">例如，如果您所選擇的初始網域是 fourthcoffee.onmicrosoft.com，您就無法將它變更為 fabrikam.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="54955-191">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="54955-192">若要使用不同的 onmicrosoft.com 網域，您必須開始使用 Microsoft 365 的新訂閱。</span><span class="sxs-lookup"><span data-stu-id="54955-192">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="54955-193">**您無法重新命名您的小組網站 URL。**</span><span class="sxs-lookup"><span data-stu-id="54955-193">**You can't rename your team site URL.**</span></span> <span data-ttu-id="54955-194">您的小組網站 URL 是以您的 onmicrosoft.com 功能變數名稱為基礎。</span><span class="sxs-lookup"><span data-stu-id="54955-194">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="54955-195">不幸的是，由於 SharePoint 線上架構的運作方式，您無法重新命名小組網站。</span><span class="sxs-lookup"><span data-stu-id="54955-195">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="54955-196">**您無法移除您的 name.onmicrosoft.com17 網域。**</span><span class="sxs-lookup"><span data-stu-id="54955-196">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="54955-197">Microsoft 365 必須保留它，因為它是用於您訂閱的幕後。</span><span class="sxs-lookup"><span data-stu-id="54955-197">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="54955-198">不過，您不需要在新增自訂網域之後，自行使用網域。</span><span class="sxs-lookup"><span data-stu-id="54955-198">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="54955-199">您可以繼續使用初始 onmicrosoft.com 網域，即使是在您新增網域之後。</span><span class="sxs-lookup"><span data-stu-id="54955-199">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="54955-200">它仍適用于電子郵件和其他服務，所以是您的選擇。</span><span class="sxs-lookup"><span data-stu-id="54955-200">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="54955-201">為什麼我有「onmicrosoft.de」網域？</span><span class="sxs-lookup"><span data-stu-id="54955-201">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="54955-202">當您註冊服務時，Microsoft 365 會為您建立網域，例如 *contoso.onmicrosoft.de*。</span><span class="sxs-lookup"><span data-stu-id="54955-202">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="54955-203">您註冊時所建立的使用者識別碼包含網域，如 *alan@contoso.onmicrosoft.de*。</span><span class="sxs-lookup"><span data-stu-id="54955-203">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="54955-204">**如果您想要讓您的電子郵件看起來像是 *alan@contoso.de*：** [購買網域](../get-help-with-domains/buy-a-domain-name.md) ，或是只要 [將您的使用者與網域新增至 Microsoft 365](add-domain.md) ，便執行步驟。</span><span class="sxs-lookup"><span data-stu-id="54955-204">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="54955-205">**您無法在註冊後重新命名 name.onmicrosoft.com17 網域。**</span><span class="sxs-lookup"><span data-stu-id="54955-205">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="54955-206">例如，如果您所選擇的初始網域是 fourthcoffee.onmicrosoft.de，您就無法將它變更為 fabrikam.onmicrosoft.de。</span><span class="sxs-lookup"><span data-stu-id="54955-206">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="54955-207">若要使用不同的 onmicrosoft.de 網域，您必須開始使用 Microsoft 365 的新訂閱。</span><span class="sxs-lookup"><span data-stu-id="54955-207">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="54955-208">**您無法重新命名您的小組網站 URL。**</span><span class="sxs-lookup"><span data-stu-id="54955-208">**You can't rename your team site URL.**</span></span> <span data-ttu-id="54955-209">您的小組網站 URL 是以您的 onmicrosoft.de 功能變數名稱為基礎。不幸的是，由於 SharePoint 線上架構的運作方式，您無法重新命名小組網站。</span><span class="sxs-lookup"><span data-stu-id="54955-209">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="54955-210">**您無法移除您的 name.onmicrosoft.com17 網域。**</span><span class="sxs-lookup"><span data-stu-id="54955-210">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="54955-211">Microsoft 365 必須保留它，因為它是用於您訂閱的幕後。</span><span class="sxs-lookup"><span data-stu-id="54955-211">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="54955-212">不過，您不需要在新增自訂網域之後，自行使用網域。</span><span class="sxs-lookup"><span data-stu-id="54955-212">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="54955-213">您可以繼續使用初始 onmicrosoft.de 網域，即使是在您新增網域之後。</span><span class="sxs-lookup"><span data-stu-id="54955-213">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="54955-214">它仍適用于電子郵件和其他服務，所以是您的選擇。</span><span class="sxs-lookup"><span data-stu-id="54955-214">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="54955-215">如何驗證我的非盈利性或教育狀態？</span><span class="sxs-lookup"><span data-stu-id="54955-215">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="54955-216">在系統[管理中心](https://docs.microsoft.com/microsoft-365/admin/admin-home)選取 [**安裝**] 以啟動嚮導。</span><span class="sxs-lookup"><span data-stu-id="54955-216">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="54955-217"> (請務必先登入 Microsoft 365。 ) </span><span class="sxs-lookup"><span data-stu-id="54955-217">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="54955-218">若要成為您的學校系統管理員，請在 Microsoft 365 中選取 [  **成為系統管理員** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="54955-218">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="54955-219">系統會提示您在網域的 DNS 主機網站上新增 TXT DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="54955-219">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="54955-220">為什麼？</span><span class="sxs-lookup"><span data-stu-id="54955-220">Why?</span></span> <span data-ttu-id="54955-221">由於是在 DNS 主機登入，並為您的網域新增記錄，因此您可以向 Microsoft 365 證明您擁有該功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="54955-221">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="54955-222">在您新增記錄後，您會回到 Microsoft 365 入口網站，並確認您已新增該記錄，所以 Microsoft 365 可以進行檢查。</span><span class="sxs-lookup"><span data-stu-id="54955-222">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="54955-223">是否有非贏利且想要取得 Microsoft 365？</span><span class="sxs-lookup"><span data-stu-id="54955-223">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="54955-224">[請確定您的組織符合資格](https://www.microsoft.com/en-us/nonprofits/eligibility) ，然後註冊服務。</span><span class="sxs-lookup"><span data-stu-id="54955-224">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="54955-225">想要深入瞭解如何成為您的學校管理員？</span><span class="sxs-lookup"><span data-stu-id="54955-225">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="54955-226">[深入瞭解](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。</span><span class="sxs-lookup"><span data-stu-id="54955-226">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>