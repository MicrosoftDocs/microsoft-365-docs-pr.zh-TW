---
title: DNS 基本知識
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: 了解網域及其相關聯的 DNS 記錄，協助您管理網域。
ms.openlocfilehash: 3f913a96395424e86d0d88dbb29bcb58a076ebb8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645356"
---
# <a name="dns-basics"></a><span data-ttu-id="976c7-103">DNS 基本知識</span><span class="sxs-lookup"><span data-stu-id="976c7-103">DNS basics</span></span>

 <span data-ttu-id="976c7-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="976c7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="976c7-105">網域名稱 (例如 contoso.com) 是由網域註冊機構和資料庫的全球系統管理。</span><span class="sxs-lookup"><span data-stu-id="976c7-105">Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases.</span></span> <span data-ttu-id="976c7-106">網域名稱系統 (DNS) 可提供人類看得懂的電腦主機名稱與網路設備所使用的 IP 位址之間的對應。</span><span class="sxs-lookup"><span data-stu-id="976c7-106">The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment.</span></span> <span data-ttu-id="976c7-107">了解 DNS 和網域註冊機構的基本概念有助於管理網域。</span><span class="sxs-lookup"><span data-stu-id="976c7-107">An understanding of DNS and domain registrar basics can help you manage domains.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="976c7-108">網域名稱 (例如 contoso.com) 是由網域註冊機構和資料庫的全球系統管理。</span><span class="sxs-lookup"><span data-stu-id="976c7-108">Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases.</span></span> <span data-ttu-id="976c7-109">網域名稱系統 (DNS) 可提供人類看得懂的電腦主機名稱與網路設備所使用的 IP 位址之間的對應。</span><span class="sxs-lookup"><span data-stu-id="976c7-109">The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment.</span></span> <span data-ttu-id="976c7-110">了解 DNS 和網域註冊機構的基本概念有助於管理網域。</span><span class="sxs-lookup"><span data-stu-id="976c7-110">An understanding of DNS and domain registrar basics can help you manage domains.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="976c7-111">網域名稱 (例如 contoso.com) 是由網域註冊機構和資料庫的全球系統管理。</span><span class="sxs-lookup"><span data-stu-id="976c7-111">Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases.</span></span> <span data-ttu-id="976c7-112">網域名稱系統 (DNS) 可提供人類看得懂的電腦主機名稱與網路設備所使用的 IP 位址之間的對應。</span><span class="sxs-lookup"><span data-stu-id="976c7-112">The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment.</span></span> <span data-ttu-id="976c7-113">瞭解 DNS 和網域註冊機構的基本概念，可協助系統管理員管理網域。</span><span class="sxs-lookup"><span data-stu-id="976c7-113">An understanding of DNS and domain registrar basics will help admins manage domains.</span></span>
  
::: moniker-end

## <a name="what-are-domain-names"></a><span data-ttu-id="976c7-114">什麼是網域名稱？</span><span class="sxs-lookup"><span data-stu-id="976c7-114">What are domain names?</span></span>

<span data-ttu-id="976c7-115">網域名稱是用於 URL 與電子郵件地址，包含不同的層級。</span><span class="sxs-lookup"><span data-stu-id="976c7-115">Domain names are used in URLs and email addresses, and they have different levels.</span></span> <span data-ttu-id="976c7-116">例如，mail.contoso.com 是一個網域名稱，包含下列三個層級：</span><span class="sxs-lookup"><span data-stu-id="976c7-116">For example, mail.contoso.com is a domain name with the following three levels:</span></span>
  
- <span data-ttu-id="976c7-117">**.com** 是頂層網域</span><span class="sxs-lookup"><span data-stu-id="976c7-117">**.com** is the top-level domain</span></span> 
    
- <span data-ttu-id="976c7-118">**contoso** 是第二層網域</span><span class="sxs-lookup"><span data-stu-id="976c7-118">**contoso** is the second-level domain</span></span> 
    
- <span data-ttu-id="976c7-119">**mail** 是第三層網域</span><span class="sxs-lookup"><span data-stu-id="976c7-119">**mail** is the third-level domain</span></span> 
    
<span data-ttu-id="976c7-120">為什麼要使用第三層網域？</span><span class="sxs-lookup"><span data-stu-id="976c7-120">Why use a third-level domain?</span></span> <span data-ttu-id="976c7-121">您可能會想要針對行銷或部落格使用不同的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="976c7-121">You might want to have different domain names for marketing or a blog.</span></span> <span data-ttu-id="976c7-122">例如，blog.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="976c7-122">For example, blog.contoso.com.</span></span> <span data-ttu-id="976c7-123">您通常會新增第二層網域 (例如 contoso.com) 以搭配 Microsoft 使用，但也可以視需要使用第三層網域。</span><span class="sxs-lookup"><span data-stu-id="976c7-123">You typically add a second-level domain, like contoso.com, to use with Microsoft but you can also use third-level domains if you like.</span></span>
  
<span data-ttu-id="976c7-124">若要深入了解如何將網域用於每種類型的產品，請參閱 [Microsoft 365 和 Office 365 平台網域服務說明](https://go.microsoft.com/fwlink/?LinkId=402693)。</span><span class="sxs-lookup"><span data-stu-id="976c7-124">Learn more about what you can do with domains for each type of offering in the [Microsoft 365 and Office 365 platform service description](https://go.microsoft.com/fwlink/?LinkId=402693).</span></span>
  
## <a name="understand-dns-record-types"></a><span data-ttu-id="976c7-125">了解 DNS 記錄類型</span><span class="sxs-lookup"><span data-stu-id="976c7-125">Understand DNS record types</span></span>

<span data-ttu-id="976c7-126">儲存在網域 DNS 主機的 DNS 記錄用於指引網域的流量。</span><span class="sxs-lookup"><span data-stu-id="976c7-126">DNS records stored at a DNS host for your domain are used to direct traffic for your domain.</span></span> <span data-ttu-id="976c7-127">下表說明經常使用的 DNS 記錄，以及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="976c7-127">The following table describes frequently used DNS records and how they're used.</span></span>
  
|<span data-ttu-id="976c7-128">**NS (名稱伺服器) 記錄**</span><span class="sxs-lookup"><span data-stu-id="976c7-128">**NS (nameserver) record**</span></span>|<span data-ttu-id="976c7-129">**可識別做為網域「授權名稱伺服器」的名稱伺服器。當您變更網域的名稱伺服器時，您會變更管理 DNS 記錄的位置，以及 DNS 系統尋找郵件伺服器等相關資訊的位置。Microsoft 擁有自己的名稱伺服器，您也可以決定繼續使用已經為您網域設定的名稱伺服器。**</span><span class="sxs-lookup"><span data-stu-id="976c7-129">**Identifies the name servers that are the "authoritative nameservers" for a domain. When you change the nameservers for your domain, you change where your DNS records are managed and where the DNS system looks for information about mail servers and so on. Microsoft has its own nameservers, or you may decide to keep using the nameservers that are already set up with your domain.**</span></span>|
|:-----|:-----|
|<span data-ttu-id="976c7-130">記錄 (位址記錄)</span><span class="sxs-lookup"><span data-stu-id="976c7-130">A record (address record)</span></span>  <br/> |<span data-ttu-id="976c7-131">建立網域名稱與特定 IP 位址之間的關聯。</span><span class="sxs-lookup"><span data-stu-id="976c7-131">Associates a domain name with an IP address.</span></span>  <br/> |
|<span data-ttu-id="976c7-132">CNAME (別名或正式名稱) 記錄</span><span class="sxs-lookup"><span data-stu-id="976c7-132">CNAME (alias or canonical) record</span></span>  <br/> |<span data-ttu-id="976c7-133">將網域重新導向至 DNS 系統中的另一個網域。</span><span class="sxs-lookup"><span data-stu-id="976c7-133">Redirects one domain to another in the DNS system.</span></span> <span data-ttu-id="976c7-134">當名稱伺服器尋找某個網域，並發現該網域有 CNAME 記錄時，該伺服器會以 CNAME 取代第一個網域名稱，然後再尋找新名稱。</span><span class="sxs-lookup"><span data-stu-id="976c7-134">When a name server looks up a domain and finds that it has a CNAME record, the server replaces the first domain name with the CNAME, and then looks up the new name.</span></span>  <br/> |
|<span data-ttu-id="976c7-135">MX (郵件交換程式) 記錄</span><span class="sxs-lookup"><span data-stu-id="976c7-135">MX (mail exchanger) record</span></span>  <br/> |<span data-ttu-id="976c7-136">指向電子郵件應該傳送的目標位置。</span><span class="sxs-lookup"><span data-stu-id="976c7-136">Points to where your email should be sent.</span></span> <span data-ttu-id="976c7-137">它也具有優先順序欄位，讓您可按照優先順序，將郵件傳送到不同的伺服器。</span><span class="sxs-lookup"><span data-stu-id="976c7-137">It also has a priority field so that you can send mail to different servers in a priority order.</span></span>  <br/> |
|<span data-ttu-id="976c7-138">SPF (寄件者原則架構) 記錄</span><span class="sxs-lookup"><span data-stu-id="976c7-138">SPF (sender policy framework) record</span></span>  <br/> |<span data-ttu-id="976c7-139">TXT 記錄，有助於防止電子郵件詐騙和網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="976c7-139">A TXT record that helps prevent email spoofing and phishing.</span></span>  <br/> |
|<span data-ttu-id="976c7-140">SRV (服務) 記錄</span><span class="sxs-lookup"><span data-stu-id="976c7-140">SRV (service) record</span></span>  <br/> |<span data-ttu-id="976c7-141">商務用 Skype Online 和 Exchange Online 會用來協調 Microsoft 服務之間的資訊流程。</span><span class="sxs-lookup"><span data-stu-id="976c7-141">Used by Skype for Business Online and Exchange Online to coordinate the flow of information between Microsoft services.</span></span> <span data-ttu-id="976c7-142">例如，必須具備 SRV 記錄才能查看 Outlook Web App 中的目前狀態，以及與其他公司中的人員使用商務用 Skype Online、Skype 或其他立即訊息工具。</span><span class="sxs-lookup"><span data-stu-id="976c7-142">For example, the SRV records are required to see presence in Outlook Web App, and to use Skype for Business Online, Skype, or other instant messaging tools with people in other companies.</span></span>  <br/> |
|<span data-ttu-id="976c7-143">TTL (存留時間)</span><span class="sxs-lookup"><span data-stu-id="976c7-143">TTL (time-to-live)</span></span>  <br/> |<span data-ttu-id="976c7-144">在名稱伺服器開始尋找更新版本前，保留 DNS 記錄的時間長度。</span><span class="sxs-lookup"><span data-stu-id="976c7-144">The amount of time that a nameserver keeps a DNS record before the server looks for an updated version.</span></span>  <br/> |
   
## <a name="how-does-dns-work"></a><span data-ttu-id="976c7-145">DNS 如何運作？</span><span class="sxs-lookup"><span data-stu-id="976c7-145">How does DNS work?</span></span>

<span data-ttu-id="976c7-146">透過 Microsoft 365 等雲端服務設定網域的程序包含為網域變更或新增 [DNS 記錄](dns-basics.md)的作業。</span><span class="sxs-lookup"><span data-stu-id="976c7-146">Part of setting up your domain with a cloud service like Microsoft 365 includes changing or adding [DNS records](dns-basics.md) for the domain.</span></span> <span data-ttu-id="976c7-147">由於網際網路是使用 DNS (網域名稱系統) 和網域名稱來傳送或尋找電子郵件及網站等項目，所以這些變更有其必要性。</span><span class="sxs-lookup"><span data-stu-id="976c7-147">These changes are required because of how the Internet works with the DNS, Domain Name System, and domain names, to know where to send or find things, like email and websites.</span></span> 
  
<span data-ttu-id="976c7-148">設定網際網路使用 DNS (或稱網域名稱系統)，可讓我們以熟悉的名稱 (例如 contoso.com) 尋找特定的網際網路位置。在熟悉的名稱背後，這些網際網路位置實際上是以一串難以記憶、名為 IP (網際網路通訊協定) 位址的數字所標示而成。</span><span class="sxs-lookup"><span data-stu-id="976c7-148">The Internet is set up to use DNS, or Domain Name System, which lets us use familiar names, like contoso.com, to locate specific Internet locations that are actually, under the covers, labeled with hard-to-remember numbers called IP (Internet Protocol) addresses.</span></span> <span data-ttu-id="976c7-149">IP 位址看起來像這樣：70.42.241.42。相較之下，使用網域名稱來識別電子郵件主機和網站等位置就容易多了。</span><span class="sxs-lookup"><span data-stu-id="976c7-149">IP addresses look something like 70.42.241.42, so you can see it's much easier to use a domain name to identify locations like email hosts and websites.</span></span>
  
<span data-ttu-id="976c7-150">簡而言之：DNS 記錄會告訴網際網路傳送電子郵件的位置 (例如 joe@contoso.com)，或尋找使用您的網域名稱的網站 (例如 www.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="976c7-150">So that's the short answer: DNS records tell the Internet where to send email (like joe@contoso.com) or find websites (like www.contoso.com) that use your domain name.</span></span> <span data-ttu-id="976c7-151">當您將適當的資訊儲存到正確的網域 DNS 記錄中時，DNS 系統會正確路由所有內容，例如，您的電子郵件會傳送至 Microsoft 365，而不是其他地方。</span><span class="sxs-lookup"><span data-stu-id="976c7-151">When you put the right information into the right DNS records for your domain, the DNS system routes everything correctly so your email, for example, arrives in Microsoft 365 instead of somewhere else.</span></span>
  
<span data-ttu-id="976c7-152">網域的 DNS 記錄在其他用途上也非常有用。</span><span class="sxs-lookup"><span data-stu-id="976c7-152">A domain's DNS records can be helpful in other ways, too.</span></span> <span data-ttu-id="976c7-153">例如 Exchange 會檢查 DNS 記錄，讓 Outlook 自動設定連線至正確的 Exchange 伺服器。</span><span class="sxs-lookup"><span data-stu-id="976c7-153">For example, Exchange checks a DNS record that lets Outlook automatically set up a connection to the right Exchange server.</span></span>
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a><span data-ttu-id="976c7-154">DNS 記錄可協助網際網路將電子郵件傳送到正確的地方</span><span class="sxs-lookup"><span data-stu-id="976c7-154">DNS records help the Internet send email to the right place</span></span>

<span data-ttu-id="976c7-155">如前述，DNS 主要是在引導網際網路流量，將好記的網域名稱對應到那些難記的 IP 位址上。</span><span class="sxs-lookup"><span data-stu-id="976c7-155">As you read above, DNS essentially directs traffic around the Internet, mapping friendly domain names to those hard-to-remember IP addresses.</span></span> <span data-ttu-id="976c7-156">稱為 MX 記錄的 DNS 記錄專門將電子郵件傳送到正確的主機。 </span><span class="sxs-lookup"><span data-stu-id="976c7-156">One DNS record, called the MX record, is specifically for sending email to the right host.</span></span>
  
<span data-ttu-id="976c7-157">DNS 記錄如同網域相關資訊的資料庫。</span><span class="sxs-lookup"><span data-stu-id="976c7-157">DNS records are like a database of information about your domain.</span></span> <span data-ttu-id="976c7-158">該記錄及其值會儲存在區域檔案中，其中包含網域的每一筆記錄清單及其值。</span><span class="sxs-lookup"><span data-stu-id="976c7-158">The records and their values are kept in something called a zone file, which includes a list of each record for your domain and what its value is.</span></span> <span data-ttu-id="976c7-159">網域註冊機構和其他 DNS 主機服務公司會在其網站上提供使用者介面，以便讓您編輯網域區域檔案中的記錄。</span><span class="sxs-lookup"><span data-stu-id="976c7-159">Domain registrars and other DNS hosting companies provide a UI on their websites so you can edit the records in your domain's zone file.</span></span> <span data-ttu-id="976c7-160">您可以在該介面更新網域的 MX 記錄，以將電子郵件傳送到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="976c7-160">And that's where you update the MX record for your domain, to send email messages to Microsoft 365.</span></span>
  
 <span data-ttu-id="976c7-161">*當您將電子郵件變更至 Microsoft 365 時，透過在下一步更新您的網域 MX 記錄，所有傳送至該網域的電子郵件都會開始送往 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="976c7-161">*When you change your email to Microsoft 365, by updating your domain's MX record in the next step, ALL email sent to that domain will start coming to Microsoft 365.*</span></span>  <span data-ttu-id="976c7-162">如果其他人使用您的網域傳送電子郵件，您必須為這些人個別設定 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="976c7-162">If other people use your domain for email, you must set up Microsoft 365 mailboxes for each of those people.</span></span> 
  
<span data-ttu-id="976c7-163">聽起來很複雜嗎？</span><span class="sxs-lookup"><span data-stu-id="976c7-163">Sound complicated?</span></span> <span data-ttu-id="976c7-164">確實，但我們會逐步引導您完成 Microsoft 的網域設定。</span><span class="sxs-lookup"><span data-stu-id="976c7-164">Well, it can be, but we walk you through each step in the Microsoft domain setup.</span></span>
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a><span data-ttu-id="976c7-165">DNS 也會告訴網際網路到哪裡尋找網站</span><span class="sxs-lookup"><span data-stu-id="976c7-165">DNS tells the Internet where to look for websites too</span></span>

<span data-ttu-id="976c7-166">輸入網址 (例如 www.contoso.com) 時，網際網路會先檢查其中一個 DNS 伺服器，尋找用於 (在本案例中) contoso.com 的名稱伺服器 (NS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="976c7-166">When you type in a website address, for example, www.contoso.com, the Internet first checks with one of the DNS servers for something called a name server (NS) record for (in this case) contoso.com.</span></span> <span data-ttu-id="976c7-167">NS 記錄會告訴網際網路應在何處尋找具有所有該網域的其他 DNS 記錄值的區域檔案。</span><span class="sxs-lookup"><span data-stu-id="976c7-167">The NS record tells the Internet where it should look for the zone file that has all the other DNS record values for that domain.</span></span> <span data-ttu-id="976c7-168">有許多彼此連線的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="976c7-168">There are lots of DNS servers, all connected to each other.</span></span> <span data-ttu-id="976c7-169">伺服器共同追蹤所有已註冊的網域名稱，這些網域名稱必須是唯一的，而且是網域區域檔案的所在位置。</span><span class="sxs-lookup"><span data-stu-id="976c7-169">The servers work together to keep track of all registered domain names, which have to be unique, and where the domain's zone files are.</span></span>
  
::: moniker range="o365-worldwide"

<span data-ttu-id="976c7-170">假設 contoso.com 的 NS 記錄為「godaddy.com」。</span><span class="sxs-lookup"><span data-stu-id="976c7-170">Let's say that the NS record for contoso.com says "godaddy.com."</span></span> <span data-ttu-id="976c7-171">現在，網際網路知道 GoDaddy.com 是尋找區域檔案的位置，區域檔案列出 contoso.com 的所有其他 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="976c7-171">Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com.</span></span> <span data-ttu-id="976c7-172">這些 DNS 記錄包含 MX 記錄，顯示傳送 contoso.com 電子郵件和其他記錄的位置。</span><span class="sxs-lookup"><span data-stu-id="976c7-172">Those DNS records include the MX record that says where to send emails for contoso.com and other records.</span></span> <span data-ttu-id="976c7-173">如果 MX 記錄具有值「send email to Microsoft 365」(但以技術詞彙描述)，表示所有傳送到 contoso.com 電子郵件地址 (例如 joe@contoso.com) 的電子郵件將傳送到該處。</span><span class="sxs-lookup"><span data-stu-id="976c7-173">If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent.</span></span> <span data-ttu-id="976c7-174">然後，只要該位置有一個名為「joe」的信箱，便會傳遞電子郵件。</span><span class="sxs-lookup"><span data-stu-id="976c7-174">Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="976c7-175">假設 contoso.com 的 NS 記錄為「godaddy.com」。</span><span class="sxs-lookup"><span data-stu-id="976c7-175">Let's say that the NS record for contoso.com says "godaddy.com."</span></span> <span data-ttu-id="976c7-176">現在，網際網路知道 GoDaddy.com 是尋找區域檔案的位置，區域檔案列出 contoso.com 的所有其他 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="976c7-176">Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com.</span></span> <span data-ttu-id="976c7-177">這些 DNS 記錄包含 MX 記錄，顯示傳送 contoso.com 電子郵件和其他記錄的位置。</span><span class="sxs-lookup"><span data-stu-id="976c7-177">Those DNS records include the MX record that says where to send emails for contoso.com and other records.</span></span> <span data-ttu-id="976c7-178">如果 MX 記錄具有值「send email to Microsoft 365」(但以技術詞彙描述)，表示所有傳送到 contoso.com 電子郵件地址 (例如 joe@contoso.com) 的電子郵件將傳送到該處。</span><span class="sxs-lookup"><span data-stu-id="976c7-178">If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent.</span></span> <span data-ttu-id="976c7-179">然後，只要該位置有一個名為「joe」的信箱，便會傳遞電子郵件。</span><span class="sxs-lookup"><span data-stu-id="976c7-179">Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="976c7-180">假設 contoso.com 的 NS 記錄為「hichina.com」。</span><span class="sxs-lookup"><span data-stu-id="976c7-180">Let's say that the NS record for contoso.com says "hichina.com."</span></span> <span data-ttu-id="976c7-181">現在，網際網路知道 hichina.com 是尋找區域檔案的位置，區域檔案列出 contoso.com 的所有其他 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="976c7-181">Now the Internet knows that hichina.com is where to look for the zone file listing all the other DNS records for contoso.com.</span></span> <span data-ttu-id="976c7-182">這些 DNS 記錄包含 MX 記錄，顯示傳送 contoso.com 電子郵件和其他記錄的位置。</span><span class="sxs-lookup"><span data-stu-id="976c7-182">Those DNS records include the MX record that says where to send emails for contoso.com and other records.</span></span> <span data-ttu-id="976c7-183">如果 MX 記錄具有值「send email to Microsoft 365」(但以技術詞彙描述)，表示所有傳送到 contoso.com 電子郵件地址 (例如 joe@contoso.com) 的電子郵件將傳送到該處。</span><span class="sxs-lookup"><span data-stu-id="976c7-183">If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent.</span></span> <span data-ttu-id="976c7-184">然後，只要該位置有一個名為「joe」的信箱，便會傳遞電子郵件。</span><span class="sxs-lookup"><span data-stu-id="976c7-184">Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.</span></span>

::: moniker-end

<span data-ttu-id="976c7-185">當您在網域設定步驟中設定網域時，系統會列出您必須輸入才能使用 Microsoft 365 的實際值。</span><span class="sxs-lookup"><span data-stu-id="976c7-185">The actual values that you must enter for all of this to work with Microsoft 365 are listed for you when you're setting up your domain, in the domain setup steps.</span></span> <span data-ttu-id="976c7-186">若要手動設定，請將值複製並貼到 DNS 主機上的正確 DNS 記錄 (MX 記錄、CNAME 記錄等)，這可能是網域註冊機構，但不一定。</span><span class="sxs-lookup"><span data-stu-id="976c7-186">If you're doing the set up manually, you copy and paste the values into the correct DNS records (MX record, CNAME records, and so on) at your DNS host, which might be your domain registrar but doesn't have to be.</span></span>
  
::: moniker range="o365-worldwide"

<span data-ttu-id="976c7-187">為什麼區域檔案可能位於網域註冊機構以外的其他位置？</span><span class="sxs-lookup"><span data-stu-id="976c7-187">Why might your domain's zone file be somewhere besides at your domain registrar?</span></span> <span data-ttu-id="976c7-188">您可能會在網域註冊機構 (例如 GoDaddy) 註冊您的網域名稱，但您的 DNS 記錄可能是由其他 DNS 主機服務公司或虛擬主機公司管理。</span><span class="sxs-lookup"><span data-stu-id="976c7-188">Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company.</span></span> <span data-ttu-id="976c7-189">網域的 NS 記錄會儲存該資訊，讓所有 DNS 伺服器知道尋找的位置。</span><span class="sxs-lookup"><span data-stu-id="976c7-189">The NS records for your domain store that information so all the DNS servers know where to look.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="976c7-190">為什麼區域檔案可能位於網域註冊機構以外的其他位置？</span><span class="sxs-lookup"><span data-stu-id="976c7-190">Why might your domain's zone file be somewhere besides at your domain registrar?</span></span> <span data-ttu-id="976c7-191">您可能會在網域註冊機構 (例如 GoDaddy) 註冊您的網域名稱，但您的 DNS 記錄可能是由其他 DNS 主機服務公司或虛擬主機公司管理。</span><span class="sxs-lookup"><span data-stu-id="976c7-191">Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company.</span></span> <span data-ttu-id="976c7-192">網域的 NS 記錄會儲存該資訊，讓所有 DNS 伺服器知道尋找的位置。</span><span class="sxs-lookup"><span data-stu-id="976c7-192">The NS records for your domain store that information so all the DNS servers know where to look.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="976c7-193">為什麼區域檔案可能位於網域註冊機構以外的其他位置？</span><span class="sxs-lookup"><span data-stu-id="976c7-193">Why might your domain's zone file be somewhere besides at your domain registrar?</span></span> <span data-ttu-id="976c7-194">您可能會在網域註冊機構 (例如 HiChina) 註冊您的網域名稱，但您的 DNS 記錄可能是由其他 DNS 主機服務公司或虛擬主機公司管理。</span><span class="sxs-lookup"><span data-stu-id="976c7-194">Well, you might register your domain name at a domain registrar like HiChina, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company.</span></span> <span data-ttu-id="976c7-195">網域的 NS 記錄會儲存該資訊，讓所有 DNS 伺服器知道尋找的位置。</span><span class="sxs-lookup"><span data-stu-id="976c7-195">The NS records for your domain store that information so all the DNS servers know where to look.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a><span data-ttu-id="976c7-196">為什麼要在 Microsoft 365 中新增網域？</span><span class="sxs-lookup"><span data-stu-id="976c7-196">Why add a domain in Microsoft 365?</span></span>


<span data-ttu-id="976c7-197">將自訂網域 (例如 fourthcoffee.com) 新增至 Microsoft 365 可讓您使用更簡短、更熟悉的電子郵件地址和該服務的 userID。</span><span class="sxs-lookup"><span data-stu-id="976c7-197">Adding a custom domain, like fourthcoffee.com, to Microsoft 365 lets you use a shorter, more familiar email address and userID with the service.</span></span> <span data-ttu-id="976c7-198">註冊 Microsoft 365 帳戶時，將會[提供一個網域供您使用](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)，但包括「onmicrosoft.com」。</span><span class="sxs-lookup"><span data-stu-id="976c7-198">You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Microsoft 365 account, but it includes "onmicrosoft.com."</span></span> <span data-ttu-id="976c7-199">如果計劃將 Microsoft 365 用於電子郵件，許多人偏好新增組織或商務網域。</span><span class="sxs-lookup"><span data-stu-id="976c7-199">Many people prefer to add their organization or business domain if they plan to use Microsoft 365 for email.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="976c7-200">如果您只是要下載並使用 Microsoft App (例如 Outlook 或 Word)，則無需新增網域：[在您的 PC 或 Mac 上安裝 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)。</span><span class="sxs-lookup"><span data-stu-id="976c7-200">If you just want to download and use Microsoft apps, like Outlook or Word, you don't need to add a domain: [Install Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> 
  
<span data-ttu-id="976c7-201">您可以在 Microsoft 365 中將網域名稱用於電子郵件、公用網站及立即訊息位址。</span><span class="sxs-lookup"><span data-stu-id="976c7-201">You can use your domain name in Microsoft 365 with your email, public website, and instant messaging address.</span></span>
  
- <span data-ttu-id="976c7-202">**電子郵件：** 您的網域名稱可讓您自訂電子郵件，因此您可以使用更簡短且易記的地址，而不是帳戶隨附的[初始 onmicrosoft.com 電子郵件地址](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)。</span><span class="sxs-lookup"><span data-stu-id="976c7-202">**Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account.</span></span> <span data-ttu-id="976c7-203">因此電子郵件地址 (也是用於登入 Microsoft 365 的公司帳戶) 可能是 joe@contoso.com，而不是 joe@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="976c7-203">So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Microsoft 365) could be joe@contoso.com.</span></span> 
    
- <span data-ttu-id="976c7-204">**網站：** 如果您的 Microsoft 365 訂閱包含 SharePoint Online 公用網站 (已不再提供購買)，您的公用網站會隨附像 contoso-public.sharepoint.com 這樣的初始位址。</span><span class="sxs-lookup"><span data-stu-id="976c7-204">**Website:** If you have an Microsoft 365 subscription that includes a SharePoint Online Public Website (no longer available for purchase), your public website comes with an initial address like this: contoso-public.sharepoint.com.</span></span> <span data-ttu-id="976c7-205">如果您是為企業設定網站，您可以使用自訂網域名稱，將網站位址重新命名為類似 www.contoso.com 這樣的位址。</span><span class="sxs-lookup"><span data-stu-id="976c7-205">If you set up your website for your business, you can use a custom domain name to rename the website address to something like www.contoso.com.</span></span> 
    
- <span data-ttu-id="976c7-206">**立即訊息：** 您也可以將商務用 Skype Online 位址自訂為使用您的網域名稱，讓組織內部人員使用更簡短易記的位址 (例如 joe@contoso.com)，在商務用 Skype Online 上彼此聯繫。</span><span class="sxs-lookup"><span data-stu-id="976c7-206">**Instant messaging:** Your Skype for Business Online address can also be customized to use your domain name, so people in your organization can connect with each other on Skype for Business Online by using a shorter, easier-to-remember address (like joe@contoso.com).</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a><span data-ttu-id="976c7-207">為什麼要在 Microsoft 365 中新增網域？</span><span class="sxs-lookup"><span data-stu-id="976c7-207">Why add a domain in Microsoft 365?</span></span>


<span data-ttu-id="976c7-208">將自訂網域 (例如 fourthcoffee.com) 新增至 Microsoft 365 可讓您使用更簡短、更熟悉的電子郵件地址和該服務的 userID。</span><span class="sxs-lookup"><span data-stu-id="976c7-208">Adding a custom domain, like fourthcoffee.com, to Microsoft 365 lets you use a shorter, more familiar email address and userID with the service.</span></span> <span data-ttu-id="976c7-209">註冊 Microsoft 365 帳戶時，將會[提供一個網域供您使用](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)，但包括「onmicrosoft.com」。</span><span class="sxs-lookup"><span data-stu-id="976c7-209">You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Microsoft 365 account, but it includes "onmicrosoft.com."</span></span> <span data-ttu-id="976c7-210">如果計劃將 Microsoft 365 用於電子郵件，許多人偏好新增組織或商務網域。</span><span class="sxs-lookup"><span data-stu-id="976c7-210">Many people prefer to add their organization or business domain if they plan to use Microsoft 365 for email.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="976c7-211">如果您只是要下載並使用 Microsoft 365 應用程式 (例如 Outlook 或 Word)，則無需新增網域：[在您的 PC 或 Mac 上安裝 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)。</span><span class="sxs-lookup"><span data-stu-id="976c7-211">If you just want to download and use Microsoft 365 apps, like Outlook or Word, you don't need to add a domain: [Install Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> 
  
<span data-ttu-id="976c7-212">您可以在 Microsoft 365 中將網域名稱用於電子郵件、公用網站及立即訊息位址。</span><span class="sxs-lookup"><span data-stu-id="976c7-212">You can use your domain name in Microsoft 365 with your email, public website, and instant messaging address.</span></span>
  
- <span data-ttu-id="976c7-213">**電子郵件：** 您的網域名稱可讓您自訂電子郵件，因此您可以使用更簡短且易記的地址，而不是帳戶隨附的[初始 onmicrosoft.com 電子郵件地址](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)。</span><span class="sxs-lookup"><span data-stu-id="976c7-213">**Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account.</span></span> <span data-ttu-id="976c7-214">因此電子郵件地址 (也是用於登入 Microsoft 365 的公司帳戶) 可能是 joe@contoso.com，而不是 joe@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="976c7-214">So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Microsoft 365) could be joe@contoso.com.</span></span> 
    
- <span data-ttu-id="976c7-215">**網站：** 如果您的訂閱包含 SharePoint Online 公用網站 (已不再提供購買)，您的公用網站會隨附像 contoso-public.sharepoint.com 這樣的初始位址。</span><span class="sxs-lookup"><span data-stu-id="976c7-215">**Website:** If you have a subscription that includes a SharePoint Online Public Website (no longer available for purchase), your public website comes with an initial address like this: contoso-public.sharepoint.com.</span></span> <span data-ttu-id="976c7-216">如果您是為企業設定網站，您可以使用自訂網域名稱，將網站位址重新命名為類似 www.contoso.com 這樣的位址。</span><span class="sxs-lookup"><span data-stu-id="976c7-216">If you set up your website for your business, you can use a custom domain name to rename the website address to something like www.contoso.com.</span></span> 
    
- <span data-ttu-id="976c7-217">**立即訊息：** 您也可以將商務用 Skype Online 位址自訂為使用您的網域名稱，讓組織內部人員使用更簡短易記的位址 (例如 joe@contoso.com)，在商務用 Skype Online 上彼此聯繫。</span><span class="sxs-lookup"><span data-stu-id="976c7-217">**Instant messaging:** Your Skype for Business Online address can also be customized to use your domain name, so people in your organization can connect with each other on Skype for Business Online by using a shorter, easier-to-remember address (like joe@contoso.com).</span></span> 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a><span data-ttu-id="976c7-218">Microsoft 365 所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="976c7-218">The DNS records required for Microsoft 365</span></span>

<span data-ttu-id="976c7-219">Microsoft 365 需要具備數種 DNS 記錄才能搭配您的網域使用。</span><span class="sxs-lookup"><span data-stu-id="976c7-219">There are a number of DNS records required for Microsoft 365 to work with your domain.</span></span> <span data-ttu-id="976c7-220">除了設定網域的 MX 記錄，讓電子郵件傳送到 Microsoft 365 之外，還有其他記錄可以協助您處理任務，像是確認 Outlook 可以自動連線到正確的 Exchange 伺服器、設定立即訊息，以及協助防堵垃圾郵件等。</span><span class="sxs-lookup"><span data-stu-id="976c7-220">In addition to setting up your domain's MX record so email will be sent to Microsoft 365, there are records to help with tasks like making sure Outlook can automatically connect to the right Exchange server, setting up instant messaging, and helping to prevent spam email.</span></span>
  
<span data-ttu-id="976c7-221">您可以[尋找值清單](information-for-dns-records.md)設定您的網域。</span><span class="sxs-lookup"><span data-stu-id="976c7-221">You can [find a list of values](information-for-dns-records.md) to set up your domain.</span></span> <span data-ttu-id="976c7-222">這些都包含在 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="976c7-222">They're included right in the Microsoft 365 admin center.</span></span> 
  
<span data-ttu-id="976c7-223">或者，如果您正在規劃部署，建議您檢閱 Microsoft 365 所需的所有 DNS 記錄清單、DNS 記錄的作用與範例值。</span><span class="sxs-lookup"><span data-stu-id="976c7-223">Or, if you're planning a deployment, you may want to review a list of all the DNS records required for Microsoft 365, what their function is, and example values.</span></span> <span data-ttu-id="976c7-224">請參閱 [Microsoft 365 的外部網域名稱系統記錄](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)。</span><span class="sxs-lookup"><span data-stu-id="976c7-224">Check out [External Domain Name System records for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span>
  
## <a name="how-can-i-learn-more"></a><span data-ttu-id="976c7-225">如何深入了解？</span><span class="sxs-lookup"><span data-stu-id="976c7-225">How can I learn more?</span></span>

<span data-ttu-id="976c7-226">請參閱下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="976c7-226">Check out one of the following:</span></span> 
  
- <span data-ttu-id="976c7-227">不確定網域的註冊位置？</span><span class="sxs-lookup"><span data-stu-id="976c7-227">Not sure where your domain is registered?</span></span> [<span data-ttu-id="976c7-228">協助您找到網域註冊機構。</span><span class="sxs-lookup"><span data-stu-id="976c7-228">Get help finding your domain registrar.</span></span>](find-your-domain-registrar.md)
- <span data-ttu-id="976c7-229">了解[為什麼您必須完成精靈中的步驟](../setup/add-domain.md)才能搭配 Microsoft 365 使用您的網域。</span><span class="sxs-lookup"><span data-stu-id="976c7-229">Find out [why you have to complete the wizard steps](../setup/add-domain.md) before you can use your domain with Microsoft 365.</span></span>
