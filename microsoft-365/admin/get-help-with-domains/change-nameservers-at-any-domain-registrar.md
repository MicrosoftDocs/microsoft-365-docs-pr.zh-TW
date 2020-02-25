---
title: 運用任何網域註冊機構變更名稱伺服器以設定 Office 365
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
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 了解如何新增及設定 Office 365 中的網域，以便服務電子郵件與 Skype for Business Online 使用您自己的網域名稱。
ms.custom: okr_smb
ms.openlocfilehash: 3030fc33a6d528fd6cb4e97c27cdbb7c251e9a97
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251670"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a><span data-ttu-id="bc044-103">運用任何網域註冊機構變更名稱伺服器以設定 Office 365</span><span class="sxs-lookup"><span data-stu-id="bc044-103">Change nameservers to set up Office 365 with any domain registrar</span></span>

 <span data-ttu-id="bc044-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="bc044-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="bc044-105">[設定您的網域 （主機專用指示）](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)先檢查以查看是否有您的註冊機構的指示。</span><span class="sxs-lookup"><span data-stu-id="bc044-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="bc044-106">您可以依照這些指示，在 Office 365 新增並設定網域，好讓電子郵件和商務用 Skype Online 等服務能夠使用您自己的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="bc044-106">Follow these instructions to add and set up your domain in Office 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="bc044-107">做法是驗證您的網域，然後將網域的名稱伺服器改為 Office 365，以便設定正確的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="bc044-107">To do this, you'll verify your domain, and then change your domain's nameservers to Office 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="bc044-108">如果下列陳述式描述您的情況，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bc044-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="bc044-109">您有自己的網域，而且希望將它設定為搭配 Office 365 使用。</span><span class="sxs-lookup"><span data-stu-id="bc044-109">You have your own domain and want to set it up to work with Office 365.</span></span>
    
- <span data-ttu-id="bc044-p102">您要讓 Office 365 為您管理 DNS 記錄 (您可以視需要[管理自己的 DNS 記錄](../setup/add-domain.md))。</span><span class="sxs-lookup"><span data-stu-id="bc044-p102">You want Office 365 to manage your DNS records for you. (If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="bc044-112">新增 TXT 或 MX 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="bc044-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="bc044-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="bc044-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="bc044-p103">您只能建立這些記錄的其中一種。TXT 是慣用的記錄類型，但部分 DNS 主機服務提供者不支援，在這種情況下，您可以改為建立 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="bc044-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="bc044-p104">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="bc044-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bc044-p105">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="bc044-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="bc044-120">在 DNS 主機服務提供者的網站上，找出您可以建立新記錄的區域</span><span class="sxs-lookup"><span data-stu-id="bc044-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="bc044-121">登入您 DNS 主機服務提供者的網站。</span><span class="sxs-lookup"><span data-stu-id="bc044-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="bc044-122">選擇您的網域。</span><span class="sxs-lookup"><span data-stu-id="bc044-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="bc044-123">找出可編輯網域 DNS 記錄的頁面。</span><span class="sxs-lookup"><span data-stu-id="bc044-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="bc044-124">建立記錄</span><span class="sxs-lookup"><span data-stu-id="bc044-124">Create the record</span></span>

<span data-ttu-id="bc044-125">請根據您要建立 TXT 記錄還是 MX 記錄而定，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="bc044-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="bc044-126">**如果您建立 TXT 記錄，請使用以下值：**</span><span class="sxs-lookup"><span data-stu-id="bc044-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bc044-127">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="bc044-127">**Record Type**</span></span> <br/> |<span data-ttu-id="bc044-128">**Alias** (別名) 或 **Host Name** (主機名稱)</span><span class="sxs-lookup"><span data-stu-id="bc044-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="bc044-129">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="bc044-129">**Value**</span></span> <br/> |<span data-ttu-id="bc044-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bc044-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="bc044-131">TXT</span><span class="sxs-lookup"><span data-stu-id="bc044-131">TXT</span></span>  <br/> |<span data-ttu-id="bc044-132">請執行下列其中一項操作：輸入 **@** ，或是保留欄位空白，或輸入您的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="bc044-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="bc044-133">> [!NOTE]> 不同的 DNS 主機對此欄位有不同的要求。</span><span class="sxs-lookup"><span data-stu-id="bc044-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="bc044-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="bc044-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="bc044-p106">> [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="bc044-p106">> [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="bc044-138">將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 ( **60** )、秒數 ( **3600** ) 等。</span><span class="sxs-lookup"><span data-stu-id="bc044-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="bc044-139">**如果您建立 MX 記錄，請使用以下值：**</span><span class="sxs-lookup"><span data-stu-id="bc044-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bc044-140">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="bc044-140">**Record Type**</span></span>|<span data-ttu-id="bc044-141">**Alias** (別名) 或 **Host Name** (主機名稱)</span><span class="sxs-lookup"><span data-stu-id="bc044-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="bc044-142">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="bc044-142">**Value**</span></span>|<span data-ttu-id="bc044-143">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="bc044-143">**Priority**</span></span>|<span data-ttu-id="bc044-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bc044-144">**TTL**</span></span>|
|<span data-ttu-id="bc044-145">MX</span><span class="sxs-lookup"><span data-stu-id="bc044-145">MX</span></span>|<span data-ttu-id="bc044-146">輸入 **@** 或您的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="bc044-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="bc044-p107">MS=ms *XXXXXXXX* > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="bc044-p107">MS=ms *XXXXXXXX* > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="bc044-150">**優先順序**，以避免發生衝突，以用於郵件流程的 MX 記錄，使用比優先順序較低的優先順序的任何現有的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="bc044-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="bc044-151">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](../setup/domains-faq.md#what-is-mx-priority)</span><span class="sxs-lookup"><span data-stu-id="bc044-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="bc044-152">將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 ( **60** )、秒數 ( **3600** ) 等。</span><span class="sxs-lookup"><span data-stu-id="bc044-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="bc044-153">儲存記錄</span><span class="sxs-lookup"><span data-stu-id="bc044-153">Save the record</span></span>

<span data-ttu-id="bc044-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="bc044-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="bc044-155">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="bc044-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="bc044-156">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="bc044-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="bc044-157">在 [**網域**] 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="bc044-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="bc044-158">在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="bc044-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="bc044-159">在 [**驗證網域**] 頁面上，選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="bc044-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="bc044-p109">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="bc044-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="bc044-163">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="bc044-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="bc044-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="bc044-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="bc044-p110">當您在 Office 365 中進行到網域設定精靈的最後一個步驟時，還剩下一項工作需要完成。若要搭配 Office 365 服務 (例如電子郵件) 設定網域，請在網域註冊機構，將網域的名稱伺服器 (或 NS) 記錄改為指向 Office 365 主要和次要名稱伺服器。由於 Office 365 負責主控您的 DNS，因此會自動為您設定服務所需的 DNS 記錄。 您可以遵循以下步驟自行更新名稱伺服器記錄 (網域註冊機構可能會在他們網站上的說明內容中提供步驟)。如果您不熟悉 DNS，請連絡網域註冊機構的支援人員。</span><span class="sxs-lookup"><span data-stu-id="bc044-p110">When you get to the last step of the domains setup wizard in Office 365, you have one task remaining. To set up your domain with Office 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Office 365 primary and secondary nameservers. Then, because Office 365 hosts your DNS, the required DNS records for your services are set up automatically for you. You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website. If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="bc044-170">若要自行在網域註冊機構的網站變更您網域的名稱伺服器，請遵循這些步驟：</span><span class="sxs-lookup"><span data-stu-id="bc044-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="bc044-171">在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="bc044-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="bc044-172">建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，以符合下列值：</span><span class="sxs-lookup"><span data-stu-id="bc044-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="bc044-173">第一個名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="bc044-173">First nameserver</span></span>  <br/> |<span data-ttu-id="bc044-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bc044-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="bc044-175">Second nameserver (第二個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="bc044-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="bc044-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="bc044-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="bc044-177">您應該使用至少兩個名稱伺服器記錄。</span><span class="sxs-lookup"><span data-stu-id="bc044-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="bc044-178">如果沒有列出任何其他名稱伺服器，您可以刪除，或將它們變更為**ns3.bdm.microsoftonline.com**和**ns4.bdm.microsoftonline.com**。</span><span class="sxs-lookup"><span data-stu-id="bc044-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="bc044-179">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="bc044-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="bc044-p112">當您將網域的 NS 記錄改為指向 Office 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。如果您跳過精靈的任一步驟 (例如新增電子郵件地址)，或者如果您將網域用於部落格、購物車或其他服務，就必須額外採取其他步驟才行。否則這項變更可能會使服務停擺 (例如，無法存取電子郵件或是您的目前網站)。</span><span class="sxs-lookup"><span data-stu-id="bc044-p112">When you change your domain's NS records to point to the Office 365 nameservers, all the services that are currently associated with your domain are affected. If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required. Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="bc044-183">在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="bc044-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="bc044-184">建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，以符合下列值：</span><span class="sxs-lookup"><span data-stu-id="bc044-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="bc044-185">第一個名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="bc044-185">First nameserver</span></span>  <br/> |<span data-ttu-id="bc044-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="bc044-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="bc044-187">Second nameserver (第二個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="bc044-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="bc044-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="bc044-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="bc044-189">您應該使用至少兩個名稱伺服器記錄。</span><span class="sxs-lookup"><span data-stu-id="bc044-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="bc044-190">如果沒有列出任何其他名稱伺服器，您可以刪除，或將它們變更為**ns3.dns.partner.microsoftonline.cn**和**ns4.dns.partner.microsoftonline.cn**。</span><span class="sxs-lookup"><span data-stu-id="bc044-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="bc044-191">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="bc044-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="bc044-192">當您變更您網域的 NS 記錄改為指向 Office 365 operated by 21Vianet 名稱伺服器時，會影響所有目前與您的網域相關聯的服務。</span><span class="sxs-lookup"><span data-stu-id="bc044-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="bc044-193">如果您跳過精靈的任一步驟 (例如新增電子郵件地址)，或者如果您將網域用於部落格、購物車或其他服務，就必須額外採取其他步驟才行。</span><span class="sxs-lookup"><span data-stu-id="bc044-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="bc044-194">否則這項變更可能會使服務停擺 (例如，無法存取電子郵件或是您的目前網站)。</span><span class="sxs-lookup"><span data-stu-id="bc044-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="bc044-195">舉例來說，如果要主控電子郵件和網站，必須另外執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bc044-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="bc044-196">在變更名稱伺服器 (NS) 記錄之前，將所有使用您網域的電子郵件地址全部移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="bc044-196">Move all email addresses that use your domain to Office 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="bc044-197">您要新增一個目前搭配網站位址 (例如 www.fourthcoffee.com) 使用的網域嗎？</span><span class="sxs-lookup"><span data-stu-id="bc044-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="bc044-198">當您新增網域，以保留其主控網站主控現在讓您變更網域的 NS 記錄改為指向 Office 365 之後人員還可以對網站取得的網站時，您可以採取以下步驟。</span><span class="sxs-lookup"><span data-stu-id="bc044-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Office 365.</span></span>

1. <span data-ttu-id="bc044-199">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="bc044-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="bc044-200">在 [網域] 頁面上，選取網域。</span><span class="sxs-lookup"><span data-stu-id="bc044-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="bc044-201">**DNS 設定**] 下選取 [**自訂記錄**，，，然後選擇 [**新增自訂記錄**。</span><span class="sxs-lookup"><span data-stu-id="bc044-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="bc044-202">選取您想要新增的 DNS 記錄類型，然後輸入新記錄的資訊。</span><span class="sxs-lookup"><span data-stu-id="bc044-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="bc044-203">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="bc044-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bc044-p116">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="bc044-p116">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  

