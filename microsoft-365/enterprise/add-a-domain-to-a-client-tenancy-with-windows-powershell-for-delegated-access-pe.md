---
title: 使用適用于協力合作夥伴的 Windows PowerShell，新增網域至用戶端租使用者
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: 摘要：使用 Microsoft 365 PowerShell，將替代功能變數名稱新增至現有的客戶租使用者。
ms.openlocfilehash: 23137d2e2461e75a22d0403f9b8246a29e48019f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688833"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a><span data-ttu-id="21724-103">利用適用於委派存取權限 (DAP) 合作夥伴的 Windows PowerShell 新增用戶端租用網域</span><span class="sxs-lookup"><span data-stu-id="21724-103">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>

<span data-ttu-id="21724-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="21724-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="21724-105">您可以使用 microsoft 365 365 的 PowerShell 比使用 Microsoft 系統管理中心，以更快的速度建立與客戶的租用關聯的新網域。</span><span class="sxs-lookup"><span data-stu-id="21724-105">You can create and associate new domains with your customer's tenancy with PowerShell for Microsoft 365 faster than using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="21724-106">委派的存取權限 (DAP) 合作夥伴就是新聞訂閱方式和雲端解決方案提供者 (CSP) 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="21724-106">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="21724-107">他們通常是其他公司的網路或電信服務提供者。</span><span class="sxs-lookup"><span data-stu-id="21724-107">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="21724-108">他們會將 Microsoft 365 訂閱捆綁到其客戶的服務產品中。</span><span class="sxs-lookup"><span data-stu-id="21724-108">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="21724-109">當他們銷售 Microsoft 365 訂閱時，系統會自動授與 (AOBO 的「管理」) 許可權給客戶租用，讓他們能管理及報告客戶租用。</span><span class="sxs-lookup"><span data-stu-id="21724-109">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="21724-110">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="21724-110">What do you need to know before you begin?</span></span>

<span data-ttu-id="21724-111">本主題中的程式需要使用 PowerShell 連接至 [Microsoft 365](connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="21724-111">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="21724-112">您也需要合作夥伴租用戶系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="21724-112">You also need your partner tenant administrator credentials.</span></span>
  
<span data-ttu-id="21724-113">您也需要下列資訊︰</span><span class="sxs-lookup"><span data-stu-id="21724-113">You also need the following information:</span></span>
  
- <span data-ttu-id="21724-114">您需要客戶要求的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="21724-114">You need the fully qualified domain name (FQDN) that your customer wants.</span></span>
    
- <span data-ttu-id="21724-115">您需要客戶的 **TenantId** 。</span><span class="sxs-lookup"><span data-stu-id="21724-115">You need the customer's **TenantId**.</span></span>
    
- <span data-ttu-id="21724-p102">FQDN 必須是已向網際網路網域名稱服務 (DNS) 註冊機構註冊的名稱 (如 GoDaddy)。如需公開註冊網域名稱的詳細資訊，請參閱[如何購買網域名稱](https://go.microsoft.com/fwlink/p/?LinkId=532541)。</span><span class="sxs-lookup"><span data-stu-id="21724-p102">The FQDN must be registered with an Internet domain name service (DNS) registrar, such as GoDaddy. For more information on how to publically register a domain name, see [How to buy a domain name](https://go.microsoft.com/fwlink/p/?LinkId=532541).</span></span>
    
- <span data-ttu-id="21724-118">您需要知道如何為 DNS 註冊機構將 TXT 記錄新增至已註冊的 DNS 區域。</span><span class="sxs-lookup"><span data-stu-id="21724-118">You need to know how to add a TXT record to the registered DNS zone for your DNS registrar.</span></span> <span data-ttu-id="21724-119">如需如何新增 TXT 記錄的詳細資訊，請參閱 [ADD DNS record to connect domain](https://go.microsoft.com/fwlink/p/?LinkId=532542)。</span><span class="sxs-lookup"><span data-stu-id="21724-119">For more information on how to add a TXT record, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span></span> <span data-ttu-id="21724-120">如果這些程序不適用，您將需要尋找適合 DNS 註冊機構的程序。</span><span class="sxs-lookup"><span data-stu-id="21724-120">If those procedures don't work for you, you will need to find the procedures for your DNS registrar.</span></span>
    
## <a name="create-domains"></a><span data-ttu-id="21724-121">建立網域</span><span class="sxs-lookup"><span data-stu-id="21724-121">Create domains</span></span>

 <span data-ttu-id="21724-p104">客戶可能會要求您建立額外的網域來與租用相關聯，因為他們不希望預設的<網域>.onmicrosoft.com網域成為向全世界代表公司身分的主要網域。此程序會引導您完成與客戶租用相關聯之新網域的建立步驟。</span><span class="sxs-lookup"><span data-stu-id="21724-p104">Your customers will likely ask you to create additional domains to associate with their tenancy because they don't want the default <domain>.onmicrosoft.com domain to be the primary one that represents their corporate identities to the world. This procedure walks you through creating a new domain associated with your customer's tenancy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="21724-124">若要執行這些作業，您必須在 Microsoft 365 系統管理中心的系統管理員帳戶詳細資料中，將您登入的夥伴管理員帳戶設為「 **完全管理** 」，以取得 **您支援之公司的系統管理許可權** 。</span><span class="sxs-lookup"><span data-stu-id="21724-124">To perform some of these operations, the partner administrator account you sign in with must be set to **Full administration** for the **Assign administrative access to companies you support** setting found in the details of the admin account in the Microsoft 365 admin center.</span></span> <span data-ttu-id="21724-125">如需管理夥伴系統管理員角色的詳細資訊，請參閱 [合作夥伴：提供委派的管理](https://go.microsoft.com/fwlink/p/?LinkId=532435)。</span><span class="sxs-lookup"><span data-stu-id="21724-125">For more information on managing partner administrator roles, see [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span></span> 
  
### <a name="create-the-domain-in-azure-active-directory"></a><span data-ttu-id="21724-126">在 Azure Active Directory 中建立網域</span><span class="sxs-lookup"><span data-stu-id="21724-126">Create the domain in Azure Active Directory</span></span>

<span data-ttu-id="21724-127">此命令會在 Azure Active Directory 中建立網域，但不會將新網域與公開註冊的網域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="21724-127">This command creates the domain in Azure Active Directory but does not associate it with the publicly registered domain.</span></span> <span data-ttu-id="21724-128">當您證明您擁有已公開註冊的網域給 Microsoft Microsoft 365 的企業時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="21724-128">That comes when you prove that you own the publicly registered domain to Microsoft Microsoft 365 for enterprises.</span></span>
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
><span data-ttu-id="21724-129">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="21724-129">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="21724-130">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="21724-130">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a><span data-ttu-id="21724-131">取得 TXT DNS 驗證記錄的資料</span><span class="sxs-lookup"><span data-stu-id="21724-131">Get the data for the DNS TXT verification record</span></span>

 <span data-ttu-id="21724-132">Microsoft 365 會產生您需要放入 DNS TXT 驗證記錄的特定資料。</span><span class="sxs-lookup"><span data-stu-id="21724-132">Microsoft 365 will generate the specific data that you need to place into the DNS TXT verification record.</span></span> <span data-ttu-id="21724-133">若要取得資料，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="21724-133">To get the data, run this command.</span></span>
  
```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

<span data-ttu-id="21724-134">這會產生與以下範例相似的輸出：</span><span class="sxs-lookup"><span data-stu-id="21724-134">This will give you output like:</span></span>
  
 `Label: domainname.com`
  
 `Text: MS=ms########`
  
 `Ttl: 3600`
  
> [!NOTE]
> <span data-ttu-id="21724-135">您需要這些文字才能在公開註冊的 DNS 區域中建立 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="21724-135">You will need this text to create the TXT record in the publicly registered DNS zone.</span></span> <span data-ttu-id="21724-136">請務必將其複製並儲存。</span><span class="sxs-lookup"><span data-stu-id="21724-136">Be sure to copy and save it.</span></span> 
  
### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a><span data-ttu-id="21724-137">將 TXT 記錄新增至公開註冊的 DNS 區域</span><span class="sxs-lookup"><span data-stu-id="21724-137">Add a TXT record to the publically registered DNS zone</span></span>

<span data-ttu-id="21724-138">在 Microsoft 365 開始接受導向至已公開登錄功能變數名稱的流量之前，您必須證明您擁有該網域的系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="21724-138">Before Microsoft 365 will start accepting traffic that is directed to the publicly registered domain name, you must prove that you own and have administrator permissions to the domain.</span></span> <span data-ttu-id="21724-139">您可以在網域中建立 TXT 記錄，藉此證明擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="21724-139">You prove you own the domain by creating a TXT record in the domain.</span></span> <span data-ttu-id="21724-140">TXT 記錄在網域中不具任何效果，因此當您建立網域擁有權之後即可予以刪除。</span><span class="sxs-lookup"><span data-stu-id="21724-140">A TXT record doesn't do anything in your domain, and it can be deleted after your ownership of the domain is established.</span></span> <span data-ttu-id="21724-141">若要建立 TXT 記錄，請遵循 [ [新增 DNS 記錄] 中的程式來連接您的網域](https://go.microsoft.com/fwlink/p/?LinkId=532542)。</span><span class="sxs-lookup"><span data-stu-id="21724-141">To create the TXT records, follow the procedures at [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span></span> <span data-ttu-id="21724-142">如果這些程序不適用，您將需要尋找適合 DNS 註冊機構的程序。</span><span class="sxs-lookup"><span data-stu-id="21724-142">If those procedures don't work for you , you need to find the procedures for your DNS registrar.</span></span>
  
<span data-ttu-id="21724-p111">透過 nslookup 確認成功建立 TXT 記錄。請遵循此語法。</span><span class="sxs-lookup"><span data-stu-id="21724-p111">Confirm the successful creation of the TXT record via nslookup. Follow this syntax.</span></span>
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

<span data-ttu-id="21724-145">這會產生與以下範例相似的輸出：</span><span class="sxs-lookup"><span data-stu-id="21724-145">This will give you output like:</span></span>
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a><span data-ttu-id="21724-146">在 Microsoft 365 中驗證網域擁有權</span><span class="sxs-lookup"><span data-stu-id="21724-146">Validate domain ownership in Microsoft 365</span></span>

<span data-ttu-id="21724-147">在此最後一個步驟中，您會驗證您擁有公開註冊網域的 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="21724-147">In this last step, you validate to Microsoft 365 that you own the publically registered domain.</span></span> <span data-ttu-id="21724-148">在此步驟之後，Microsoft 365 會開始接受路由傳送至新功能變數名稱的流量。</span><span class="sxs-lookup"><span data-stu-id="21724-148">After this step, Microsoft 365 will begin accepting traffic routed to the new domain name.</span></span> <span data-ttu-id="21724-149">若要完成網域建立和註冊程序，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="21724-149">To complete the domain creation and registration process, run this command.</span></span> 
  
```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="21724-150">此命令將不會傳回任何輸出，因此若要確認命令正常運作，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="21724-150">This command won't return any output, so to confirm that this worked, run this command.</span></span>
  
```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="21724-151">這會傳回與以下範例相似的內容：</span><span class="sxs-lookup"><span data-stu-id="21724-151">This will return something like this</span></span>

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

   
## <a name="see-also"></a><span data-ttu-id="21724-152">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21724-152">See also</span></span>

#### 

[<span data-ttu-id="21724-153">合作夥伴說明</span><span class="sxs-lookup"><span data-stu-id="21724-153">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)
