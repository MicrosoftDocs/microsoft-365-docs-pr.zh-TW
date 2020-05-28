---
title: 使用任何網域註冊機構變更名稱伺服器以設定 Microsoft 365
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
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 瞭解如何在 Microsoft 365 中新增及設定您的網域，如此一來，諸如電子郵件和商務用 Skype Online 等服務也會使用您自己的功能變數名稱。
ms.openlocfilehash: 16e8699c1c8588a4368f04078fea44c165c13e29
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399989"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="dfb37-103">使用任何網域註冊機構變更名稱伺服器以設定 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dfb37-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="dfb37-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="dfb37-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="dfb37-105">請先檢查[[設定您的網域（主機專用指示）](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) ]，以查看是否有註冊機構的指示。</span><span class="sxs-lookup"><span data-stu-id="dfb37-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="dfb37-106">請遵循下列指示，在 Microsoft 365 中新增及設定您的網域，這樣服務（例如電子郵件和商務用 Skype Online）將使用您自己的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="dfb37-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="dfb37-107">若要這麼做，您將會驗證您的網域，然後將網域的名稱伺服器變更為 Microsoft 365，這樣就能為您設定正確的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="dfb37-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="dfb37-108">如果下列語句描述您的情況，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dfb37-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="dfb37-109">您有自己的網域，且想要將其設定為與 Microsoft 365 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="dfb37-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="dfb37-110">您希望 Microsoft 365 為您管理您的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="dfb37-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="dfb37-111">如果您想要的話，也可以[管理自己的 DNS 記錄](../setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="dfb37-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="dfb37-112">新增 TXT 或 MX 記錄以進行驗證</span><span class="sxs-lookup"><span data-stu-id="dfb37-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="dfb37-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="dfb37-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="dfb37-p103">您只能建立這些記錄的其中一種。TXT 是慣用的記錄類型，但部分 DNS 主機服務提供者不支援，在這種情況下，您可以改為建立 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="dfb37-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="dfb37-p104">在您將自己的網域用於 Microsoft 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="dfb37-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dfb37-p105">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="dfb37-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="dfb37-120">在 DNS 主機服務提供者的網站上，找出您可以建立新記錄的區域</span><span class="sxs-lookup"><span data-stu-id="dfb37-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="dfb37-121">登入您 DNS 主機服務提供者的網站。</span><span class="sxs-lookup"><span data-stu-id="dfb37-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="dfb37-122">選擇您的網域。</span><span class="sxs-lookup"><span data-stu-id="dfb37-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="dfb37-123">找出可編輯網域 DNS 記錄的頁面。</span><span class="sxs-lookup"><span data-stu-id="dfb37-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="dfb37-124">建立記錄</span><span class="sxs-lookup"><span data-stu-id="dfb37-124">Create the record</span></span>

<span data-ttu-id="dfb37-125">請根據您要建立 TXT 記錄還是 MX 記錄而定，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="dfb37-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="dfb37-126">**如果您建立 TXT 記錄，請使用以下值：**</span><span class="sxs-lookup"><span data-stu-id="dfb37-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dfb37-127">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="dfb37-127">**Record Type**</span></span> <br/> |<span data-ttu-id="dfb37-128">**Alias** (別名) 或 **Host Name** (主機名稱)</span><span class="sxs-lookup"><span data-stu-id="dfb37-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="dfb37-129">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="dfb37-129">**Value**</span></span> <br/> |<span data-ttu-id="dfb37-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dfb37-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="dfb37-131">TXT</span><span class="sxs-lookup"><span data-stu-id="dfb37-131">TXT</span></span>  <br/> |<span data-ttu-id="dfb37-132">請執行下列其中一項操作：輸入 **@** ，或是保留欄位空白，或輸入您的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="dfb37-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="dfb37-133">> [!NOTE]> 不同的 DNS 主機對此欄位有不同的要求。</span><span class="sxs-lookup"><span data-stu-id="dfb37-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="dfb37-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="dfb37-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="dfb37-135">> [!NOTE]> 這是範例。</span><span class="sxs-lookup"><span data-stu-id="dfb37-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="dfb37-136">在這裡請使用您自己的 [目的地或指向位址]\*\*\*\* 值，請參閱 Microsoft 365 表格。</span><span class="sxs-lookup"><span data-stu-id="dfb37-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="dfb37-137">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="dfb37-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="dfb37-138">將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 ( **60** )、秒數 ( **3600** ) 等。</span><span class="sxs-lookup"><span data-stu-id="dfb37-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="dfb37-139">**如果您建立 MX 記錄，請使用以下值：**</span><span class="sxs-lookup"><span data-stu-id="dfb37-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dfb37-140">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="dfb37-140">**Record Type**</span></span>|<span data-ttu-id="dfb37-141">**Alias** (別名) 或 **Host Name** (主機名稱)</span><span class="sxs-lookup"><span data-stu-id="dfb37-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="dfb37-142">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="dfb37-142">**Value**</span></span>|<span data-ttu-id="dfb37-143">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="dfb37-143">**Priority**</span></span>|<span data-ttu-id="dfb37-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dfb37-144">**TTL**</span></span>|
|<span data-ttu-id="dfb37-145">MX</span><span class="sxs-lookup"><span data-stu-id="dfb37-145">MX</span></span>|<span data-ttu-id="dfb37-146">輸入 **@** 或您的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="dfb37-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="dfb37-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span><span class="sxs-lookup"><span data-stu-id="dfb37-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="dfb37-148">在這裡請使用您自己的 [目的地或指向位址]\*\*\*\* 值，請參閱 Microsoft 365 表格。</span><span class="sxs-lookup"><span data-stu-id="dfb37-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="dfb37-149">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="dfb37-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="dfb37-150">針對 **[Priority]** (優先順序)，為避免跟用於郵件流程的 MX 記錄發生衝突，請使用比任一現有 MX 記錄更低的優先順序。</span><span class="sxs-lookup"><span data-stu-id="dfb37-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="dfb37-151">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](../setup/domains-faq.md#what-is-mx-priority)</span><span class="sxs-lookup"><span data-stu-id="dfb37-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="dfb37-152">將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 ( **60** )、秒數 ( **3600** ) 等。</span><span class="sxs-lookup"><span data-stu-id="dfb37-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="dfb37-153">儲存記錄</span><span class="sxs-lookup"><span data-stu-id="dfb37-153">Save the record</span></span>

<span data-ttu-id="dfb37-154">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 365 並要求 Microsoft 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="dfb37-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="dfb37-155">在 Microsoft 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="dfb37-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="dfb37-156">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="dfb37-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="dfb37-157">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="dfb37-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="dfb37-158">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="dfb37-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="dfb37-159">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="dfb37-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="dfb37-p109">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dfb37-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="dfb37-163">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="dfb37-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="dfb37-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="dfb37-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="dfb37-165">當您在 Microsoft 365 中取得「網域安裝精靈」的最後一個步驟時，還剩下一個工作。</span><span class="sxs-lookup"><span data-stu-id="dfb37-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="dfb37-166">若要使用 Microsoft 365 服務（例如電子郵件）來設定您的網域，您可以在您的網域註冊機構變更網域的名稱伺服器（或 NS）記錄，以指向 Microsoft 365 主要和次要名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="dfb37-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="dfb37-167">然後，由於 Microsoft 365 會主控您的 DNS，因此會自動為您設定服務所需的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="dfb37-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="dfb37-168">您可以遵循以下步驟 (網域註冊機構可能會在他們網站上的說明內容中提供)，自行更新名稱伺服器記錄。</span><span class="sxs-lookup"><span data-stu-id="dfb37-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="dfb37-169">如果您不熟悉 DNS，請連絡網域註冊機構的支援人員。</span><span class="sxs-lookup"><span data-stu-id="dfb37-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="dfb37-170">若要自行在網域註冊機構的網站變更您網域的名稱伺服器，請遵循這些步驟：</span><span class="sxs-lookup"><span data-stu-id="dfb37-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="dfb37-171">在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="dfb37-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="dfb37-172">建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，以符合下列值：</span><span class="sxs-lookup"><span data-stu-id="dfb37-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="dfb37-173">第一個名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="dfb37-173">First nameserver</span></span>  <br/> |<span data-ttu-id="dfb37-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dfb37-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="dfb37-175">Second nameserver (第二個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="dfb37-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="dfb37-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dfb37-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="dfb37-177">您應該使用至少兩個名稱伺服器記錄。</span><span class="sxs-lookup"><span data-stu-id="dfb37-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="dfb37-178">如果有列出任何其他名稱伺服器，您可以將其刪除，或將其變更為**ns3.bdm.microsoftonline.com**和**ns4.bdm.microsoftonline.com**。</span><span class="sxs-lookup"><span data-stu-id="dfb37-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="dfb37-179">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="dfb37-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="dfb37-180">當您將網域的 NS 記錄變更為指向 Microsoft 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。</span><span class="sxs-lookup"><span data-stu-id="dfb37-180">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="dfb37-181">如果您跳過精靈的任一步驟 (例如新增電子郵件地址)，或者如果您將網域用於部落格、購物車或其他服務，就必須額外採取其他步驟才行。</span><span class="sxs-lookup"><span data-stu-id="dfb37-181">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="dfb37-182">否則這項變更可能會使服務停擺 (例如，無法存取電子郵件或是您的目前網站)。</span><span class="sxs-lookup"><span data-stu-id="dfb37-182">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="dfb37-183">在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="dfb37-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="dfb37-184">建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，以符合下列值：</span><span class="sxs-lookup"><span data-stu-id="dfb37-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="dfb37-185">第一個名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="dfb37-185">First nameserver</span></span>  <br/> |<span data-ttu-id="dfb37-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="dfb37-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="dfb37-187">Second nameserver (第二個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="dfb37-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="dfb37-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="dfb37-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="dfb37-189">您應該使用至少兩個名稱伺服器記錄。</span><span class="sxs-lookup"><span data-stu-id="dfb37-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="dfb37-190">如果有列出任何其他名稱伺服器，您可以將其刪除，或將其變更為**ns3.dns.partner.microsoftonline.cn**和**ns4.dns.partner.microsoftonline.cn**。</span><span class="sxs-lookup"><span data-stu-id="dfb37-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="dfb37-191">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="dfb37-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="dfb37-192">當您變更網域的 NS 記錄，使其指向由世紀名稱伺服器運作的 Office 365 時，所有目前與您網域相關聯的服務都會受到影響。</span><span class="sxs-lookup"><span data-stu-id="dfb37-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="dfb37-193">如果您跳過精靈的任一步驟 (例如新增電子郵件地址)，或者如果您將網域用於部落格、購物車或其他服務，就必須額外採取其他步驟才行。</span><span class="sxs-lookup"><span data-stu-id="dfb37-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="dfb37-194">否則這項變更可能會使服務停擺 (例如，無法存取電子郵件或是您的目前網站)。</span><span class="sxs-lookup"><span data-stu-id="dfb37-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="dfb37-195">舉例來說，如果要主控電子郵件和網站，必須另外執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dfb37-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="dfb37-196">變更您的 NS 記錄之前，請先將使用您網域的所有電子郵件地址移至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="dfb37-196">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="dfb37-197">您要新增一個目前搭配網站位址 (例如 www.fourthcoffee.com) 使用的網域嗎？</span><span class="sxs-lookup"><span data-stu-id="dfb37-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="dfb37-198">您可以採取下列步驟，當您新增網域以保留網站主控位置的網站，讓使用者在您變更網域的 NS 記錄，以指向 Microsoft 365 之後仍可進入網站。</span><span class="sxs-lookup"><span data-stu-id="dfb37-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="dfb37-199">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="dfb37-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="dfb37-200">在 [網域] 頁面上，選取網域。</span><span class="sxs-lookup"><span data-stu-id="dfb37-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="dfb37-201">在 [ **DNS 設定**] 底下，選取 [**自訂記錄**]，然後選擇 [**新增自訂記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dfb37-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="dfb37-202">選取您要新增的 DNS 記錄類型，然後輸入新記錄的資訊。</span><span class="sxs-lookup"><span data-stu-id="dfb37-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="dfb37-203">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dfb37-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dfb37-204">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="dfb37-204">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="dfb37-205">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="dfb37-205">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  

