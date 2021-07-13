---
title: 使用任何網域註冊機構變更名稱伺服器以設定 Microsoft 365
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 瞭解如何在 Microsoft 365 中新增及設定您的網域，以便您的服務（如電子郵件和商務用 Skype 線上）使用您自己的功能變數名稱。
ms.openlocfilehash: c2de2d8b75aaf50bd1d19d3fd3b507fd476d4847
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393928"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="d1077-103">使用任何網域註冊機構變更名稱伺服器以設定 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d1077-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="d1077-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="d1077-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="d1077-105">請遵循下列指示，在 Microsoft 365 中新增及設定您的網域，這樣的服務（例如電子郵件和 Teams）會使用您自己的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="d1077-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="d1077-106">若要這麼做，您將會驗證您的網域，然後將網域的名稱伺服器變更為 Microsoft 365，這樣就能為您設定正確的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="d1077-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="d1077-107">如果下列語句描述您的情況，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d1077-107">Follow these steps if the following statements describe your situation:</span></span>

- <span data-ttu-id="d1077-108">您有自己的網域，且想要將其設定為搭配 Microsoft 365 使用。</span><span class="sxs-lookup"><span data-stu-id="d1077-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>

- <span data-ttu-id="d1077-109">您想要 Microsoft 365 管理您的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="d1077-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="d1077-110">如果您想要的話，也可以[管理自己的 DNS 記錄](../setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="d1077-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>

## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="d1077-111">新增 TXT 或 MX 記錄以進行驗證</span><span class="sxs-lookup"><span data-stu-id="d1077-111">Add a TXT or MX record for verification</span></span>

> [!NOTE]
> <span data-ttu-id="d1077-p103">您只能建立這些記錄的其中一種。TXT 是慣用的記錄類型，但部分 DNS 主機服務提供者不支援，在這種情況下，您可以改為建立 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="d1077-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span>

<span data-ttu-id="d1077-p104">在您將自己的網域用於 Microsoft 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="d1077-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="d1077-p105">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="d1077-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="d1077-118">在 DNS 主機服務提供者的網站上，找出您可以建立新記錄的區域</span><span class="sxs-lookup"><span data-stu-id="d1077-118">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="d1077-119">登入您 DNS 主機服務提供者的網站。</span><span class="sxs-lookup"><span data-stu-id="d1077-119">Sign in to your DNS hosting provider's website.</span></span>

2. <span data-ttu-id="d1077-120">選擇您的網域。</span><span class="sxs-lookup"><span data-stu-id="d1077-120">Choose your domain.</span></span>

3. <span data-ttu-id="d1077-121">找出可編輯網域 DNS 記錄的頁面。</span><span class="sxs-lookup"><span data-stu-id="d1077-121">Find the page where you can edit DNS records for your domain.</span></span>

### <a name="create-the-record"></a><span data-ttu-id="d1077-122">建立記錄</span><span class="sxs-lookup"><span data-stu-id="d1077-122">Create the record</span></span>

<span data-ttu-id="d1077-123">請根據您要建立 TXT 記錄還是 MX 記錄而定，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d1077-123">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>

<span data-ttu-id="d1077-124">**如果您建立 TXT 記錄，請使用以下值：**</span><span class="sxs-lookup"><span data-stu-id="d1077-124">**If you create a TXT record, use these values:**</span></span>

<br>

****

|<span data-ttu-id="d1077-125">記錄類型</span><span class="sxs-lookup"><span data-stu-id="d1077-125">Record type</span></span>|<span data-ttu-id="d1077-126">別名或主機名稱</span><span class="sxs-lookup"><span data-stu-id="d1077-126">Alias or host name</span></span>|<span data-ttu-id="d1077-127">值</span><span class="sxs-lookup"><span data-stu-id="d1077-127">Value</span></span>|<span data-ttu-id="d1077-128">TTL</span><span class="sxs-lookup"><span data-stu-id="d1077-128">TTL</span></span>|
|---|---|---|---|
|<span data-ttu-id="d1077-129">TXT</span><span class="sxs-lookup"><span data-stu-id="d1077-129">TXT</span></span>|<span data-ttu-id="d1077-130">請執行下列其中一項操作：輸入 **@** ，或是保留欄位空白，或輸入您的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="d1077-130">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <p> <span data-ttu-id="d1077-131">**附注**：不同的 DNS 主機對此欄位具有不同的需求。</span><span class="sxs-lookup"><span data-stu-id="d1077-131">**Note**: Different DNS hosts have different requirements for this field.</span></span>|<span data-ttu-id="d1077-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d1077-132">MS=ms *XXXXXXXX*</span></span> <p> <span data-ttu-id="d1077-133">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="d1077-133">**Note:** This is an example.</span></span> <span data-ttu-id="d1077-134">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Microsoft 365 表格。</span><span class="sxs-lookup"><span data-stu-id="d1077-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="d1077-135">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="d1077-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="d1077-136">將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 ( **60** )、秒數 ( **3600** ) 等。</span><span class="sxs-lookup"><span data-stu-id="d1077-136">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>|
|||||

<span data-ttu-id="d1077-137">**如果您建立 MX 記錄，請使用以下值：**</span><span class="sxs-lookup"><span data-stu-id="d1077-137">**If you create an MX record, use these values:**</span></span>

<br>

****

|<span data-ttu-id="d1077-138">記錄類型</span><span class="sxs-lookup"><span data-stu-id="d1077-138">Record type</span></span>|<span data-ttu-id="d1077-139">別名或主機名稱</span><span class="sxs-lookup"><span data-stu-id="d1077-139">Alias or host name</span></span>|<span data-ttu-id="d1077-140">Value (值)</span><span class="sxs-lookup"><span data-stu-id="d1077-140">Value</span></span>|<span data-ttu-id="d1077-141">Priority (優先順序)</span><span class="sxs-lookup"><span data-stu-id="d1077-141">Priority</span></span>|<span data-ttu-id="d1077-142">TTL</span><span class="sxs-lookup"><span data-stu-id="d1077-142">TTL</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="d1077-143">MX</span><span class="sxs-lookup"><span data-stu-id="d1077-143">MX</span></span>|<span data-ttu-id="d1077-144">輸入 **@** 或您的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="d1077-144">Type either **@** or your domain name.</span></span> |<span data-ttu-id="d1077-145">MS= ms *Xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx* **附注：** 這是一個範例。</span><span class="sxs-lookup"><span data-stu-id="d1077-145">MS=ms *XXXXXXXX* **Note:** This is an example.</span></span> <span data-ttu-id="d1077-146">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Microsoft 365 表格。</span><span class="sxs-lookup"><span data-stu-id="d1077-146">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="d1077-147">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="d1077-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="d1077-148">針對 **[Priority]** (優先順序)，為避免跟用於郵件流程的 MX 記錄發生衝突，請使用比任一現有 MX 記錄更低的優先順序。</span><span class="sxs-lookup"><span data-stu-id="d1077-148">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="d1077-149">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="d1077-149">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span>|<span data-ttu-id="d1077-150">將此值設為 **1 hour** (1 小時)，或設為等同的分鐘數 ( **60** )、秒數 ( **3600** ) 等。</span><span class="sxs-lookup"><span data-stu-id="d1077-150">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>|
||||||

### <a name="save-the-record"></a><span data-ttu-id="d1077-151">儲存記錄</span><span class="sxs-lookup"><span data-stu-id="d1077-151">Save the record</span></span>

<span data-ttu-id="d1077-152">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 365 並要求 Microsoft 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="d1077-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>

<span data-ttu-id="d1077-153">在 Microsoft 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="d1077-153">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="d1077-154">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="d1077-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="d1077-155">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="d1077-155">On the **Domains** page, select the domain that you are verifying.</span></span>

3. <span data-ttu-id="d1077-156">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="d1077-156">On the **Setup** page, select **Start setup**.</span></span>

4. <span data-ttu-id="d1077-157">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="d1077-157">On the **Verify domain** page, select **Verify**.</span></span>

> [!NOTE]
> <span data-ttu-id="d1077-p109">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d1077-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="d1077-161">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="d1077-161">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="d1077-162">當您在 Microsoft 365 中取得網域安裝精靈的最後一個步驟時，您會有一個剩餘的任務。</span><span class="sxs-lookup"><span data-stu-id="d1077-162">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="d1077-163">若要使用 Microsoft 365 服務（例如電子郵件）來設定網域，您可以在網域註冊機構中變更網域的名稱伺服器 (或 NS) 記錄，以指向 Microsoft 365 的主要和次要名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="d1077-163">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="d1077-164">然後，因為 Microsoft 365 主控您的 DNS，所以會為您自動設定服務所需的 dns 記錄。</span><span class="sxs-lookup"><span data-stu-id="d1077-164">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="d1077-165">您可以遵循以下步驟 (網域註冊機構可能會在他們網站上的說明內容中提供)，自行更新名稱伺服器記錄。</span><span class="sxs-lookup"><span data-stu-id="d1077-165">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="d1077-166">如果您不熟悉 DNS，請連絡網域註冊機構的支援人員。</span><span class="sxs-lookup"><span data-stu-id="d1077-166">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="d1077-167">若要自行在網域註冊機構的網站變更您網域的名稱伺服器，請遵循這些步驟：</span><span class="sxs-lookup"><span data-stu-id="d1077-167">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>

1. <span data-ttu-id="d1077-168">在網域註冊機構網站上尋找區域，您可以在其中變更您網域的名稱伺服器，或是您可以使用自訂名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="d1077-168">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>

2. <span data-ttu-id="d1077-169">建立名稱伺服器記錄，或編輯現有的名稱伺服器記錄，使其符合下列值：</span><span class="sxs-lookup"><span data-stu-id="d1077-169">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>

    - <span data-ttu-id="d1077-170">第一個名稱伺服器： ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d1077-170">First nameserver: ns1.bdm.microsoftonline.com</span></span>
    - <span data-ttu-id="d1077-171">第二個名稱伺服器： ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d1077-171">Second nameserver: ns2.bdm.microsoftonline.com</span></span>
    - <span data-ttu-id="d1077-172">協力廠商名稱： ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d1077-172">Third nameserver: ns3.bdm.microsoftonline.com</span></span>
    - <span data-ttu-id="d1077-173">第四名稱伺服器名稱： ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="d1077-173">Fourth nameserver: ns4.bdm.microsoftonline.com</span></span>

   > [!TIP]
   > <span data-ttu-id="d1077-174">最好新增四筆記錄，但如果您的註冊機構只支援二個，請新增 **ns1.bdm.microsoftonline.com** 及 **ns2.bdm.microsoftonline.com**。</span><span class="sxs-lookup"><span data-stu-id="d1077-174">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span>

3. <span data-ttu-id="d1077-175">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="d1077-175">Save your changes.</span></span>

> [!CAUTION]
> <span data-ttu-id="d1077-176">當您將網域的 NS 記錄變更為指向 Microsoft 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。</span><span class="sxs-lookup"><span data-stu-id="d1077-176">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="d1077-177">如果您跳過精靈的任一步驟 (例如新增電子郵件地址)，或者如果您將網域用於部落格、購物車或其他服務，就必須額外採取其他步驟才行。</span><span class="sxs-lookup"><span data-stu-id="d1077-177">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="d1077-178">否則這項變更可能會使服務停擺 (例如，無法存取電子郵件或是您的目前網站)。</span><span class="sxs-lookup"><span data-stu-id="d1077-178">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d1077-179">在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="d1077-179">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>

2. <span data-ttu-id="d1077-180">建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，以符合下列值：</span><span class="sxs-lookup"><span data-stu-id="d1077-180">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>

   - <span data-ttu-id="d1077-181">第一個名稱伺服器： ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="d1077-181">First nameserver: ns1.dns.partner.microsoftonline.cn</span></span>
   - <span data-ttu-id="d1077-182">第二個名稱伺服器： ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="d1077-182">Second nameserver: ns2.dns.partner.microsoftonline.cn</span></span>

   > [!TIP]
   > <span data-ttu-id="d1077-183">您應該使用至少兩個名稱伺服器記錄。</span><span class="sxs-lookup"><span data-stu-id="d1077-183">You should use at least two nameserver records.</span></span> <span data-ttu-id="d1077-184">如果有列出任何其他名稱伺服器，您可以將其刪除，或將其變更為 **ns3.dns.partner.microsoftonline.cn** 和 **ns4.dns.partner.microsoftonline.cn**。</span><span class="sxs-lookup"><span data-stu-id="d1077-184">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span>

3. <span data-ttu-id="d1077-185">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="d1077-185">Save your changes.</span></span>

> [!CAUTION]
> <span data-ttu-id="d1077-186">當您變更網域的 NS 記錄，使其指向由名稱伺服器（由您的網域所運作的 Office 365）時，所有目前與您網域相關聯的服務都會受到影響。</span><span class="sxs-lookup"><span data-stu-id="d1077-186">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="d1077-187">如果您跳過精靈的任一步驟 (例如新增電子郵件地址)，或者如果您將網域用於部落格、購物車或其他服務，就必須額外採取其他步驟才行。</span><span class="sxs-lookup"><span data-stu-id="d1077-187">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="d1077-188">否則這項變更可能會使服務停擺 (例如，無法存取電子郵件或是您的目前網站)。</span><span class="sxs-lookup"><span data-stu-id="d1077-188">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span>

::: moniker-end

<span data-ttu-id="d1077-189">舉例來說，如果要主控電子郵件和網站，必須另外執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d1077-189">For example, here are some additional steps that might be required for email and website hosting:</span></span>

- <span data-ttu-id="d1077-190">變更您的 NS 記錄之前，請將使用您網域的所有電子郵件地址移 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d1077-190">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>

- <span data-ttu-id="d1077-191">您要新增一個目前搭配網站位址 (例如 www.fourthcoffee.com) 使用的網域嗎？</span><span class="sxs-lookup"><span data-stu-id="d1077-191">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="d1077-192">您可以採取下列步驟，當您新增網域以保留網站主控位置的網站，讓使用者在您變更網域的 NS 記錄，以指向 Microsoft 365 之後仍可進入網站。</span><span class="sxs-lookup"><span data-stu-id="d1077-192">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="d1077-193">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="d1077-193">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="d1077-194">在 [ **網域** ] 頁面上，選取網域。</span><span class="sxs-lookup"><span data-stu-id="d1077-194">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="d1077-195">在 [網域詳細資料] 頁面上，選取 [ **DNS 記錄** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d1077-195">On the domain details page, select the **DNS records** tab.</span></span>

4. <span data-ttu-id="d1077-196">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="d1077-196">Select **Add record**.</span></span>

5. <span data-ttu-id="d1077-197">在 [ **新增自訂 DNS 記錄** ] 窗格中，從 [ **類型** ] 下拉式清單中選取 **(位址)**。</span><span class="sxs-lookup"><span data-stu-id="d1077-197">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="d1077-198">在 [ **主機名稱或別名** ] 方塊中，輸入 **@** 。</span><span class="sxs-lookup"><span data-stu-id="d1077-198">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="d1077-199">在 [ **IP 位址** ] 方塊中，輸入目前所主控之網站的靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d1077-199">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="d1077-200">例如，172.16.140.1。</span><span class="sxs-lookup"><span data-stu-id="d1077-200">For example, 172.16.140.1.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="d1077-201">這必須是網站的 _靜態_ ip 位址，而非 _動態_ ip 位址。</span><span class="sxs-lookup"><span data-stu-id="d1077-201">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="d1077-202">若要確定您可以取得公用網站的靜態 IP 位址，請與主控網站的網站進行核對。</span><span class="sxs-lookup"><span data-stu-id="d1077-202">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>

8. <span data-ttu-id="d1077-203">如果您想要變更記錄的 TTL 設定，請從 [ **ttl** ] 下拉式清單中選取新的時間長度。</span><span class="sxs-lookup"><span data-stu-id="d1077-203">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="d1077-204">否則，請繼續進行步驟9。</span><span class="sxs-lookup"><span data-stu-id="d1077-204">Otherwise, continue to step 9.</span></span>

9. <span data-ttu-id="d1077-205">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="d1077-205">Select **Save**.</span></span>

<span data-ttu-id="d1077-206">此外，您還可以建立 CNAME 記錄，協助客戶找到您的網站。</span><span class="sxs-lookup"><span data-stu-id="d1077-206">In addition, you can create a CNAME record to help customers find your website.</span></span>

1. <span data-ttu-id="d1077-207">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="d1077-207">Select **Add record**.</span></span>
2. <span data-ttu-id="d1077-208">在 [ **新增自訂 DNS 記錄** ] 窗格中，從 [ **類型** ] 下拉式清單中選取 [ **CNAME (別名])**。</span><span class="sxs-lookup"><span data-stu-id="d1077-208">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
3. <span data-ttu-id="d1077-209">在 [ **主機名稱或別名** ] 方塊中，輸入 **www**。</span><span class="sxs-lookup"><span data-stu-id="d1077-209">In the **Host name or Alias** box, type **www**.</span></span>
4. <span data-ttu-id="d1077-210">在 [指向 **位址** ] 方塊中，為您的網站輸入 (FQDN) 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="d1077-210">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="d1077-211">例如， **5om**。</span><span class="sxs-lookup"><span data-stu-id="d1077-211">For example, **contoso.5om**.</span></span>
5. <span data-ttu-id="d1077-212">如果您想要變更記錄的 TTL 設定，請從 [ **ttl** ] 下拉式清單中選取新的時間長度。</span><span class="sxs-lookup"><span data-stu-id="d1077-212">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="d1077-213">否則，請繼續進行步驟6。</span><span class="sxs-lookup"><span data-stu-id="d1077-213">Otherwise, continue to step 6.</span></span>
6. <span data-ttu-id="d1077-214">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="d1077-214">Select **Save**.</span></span>

<span data-ttu-id="d1077-215">在將名稱伺服器記錄更新為指向 Microsoft 之後，您的網域安裝已完成。</span><span class="sxs-lookup"><span data-stu-id="d1077-215">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="d1077-216">電子郵件會路由傳送至 Microsoft，而您的網站位址的流量仍會繼續前往您目前的網站主機。 '</span><span class="sxs-lookup"><span data-stu-id="d1077-216">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>

> [!NOTE]
> <span data-ttu-id="d1077-217">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="d1077-217">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="d1077-218">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="d1077-218">Then your Microsoft email and other services will be all set to work with your domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="d1077-219">相關內容</span><span class="sxs-lookup"><span data-stu-id="d1077-219">Related content</span></span>

<span data-ttu-id="d1077-220">[新增 DNS 記錄以將您的網域](create-dns-records-at-any-dns-hosting-provider.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="d1077-220">[Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="d1077-221">[尋找並修正新增網域或 DNS 記錄之後所發生的問題](find-and-fix-issues.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="d1077-221">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)\</span></span>
<span data-ttu-id="d1077-222">[管理網域](index.yml) (連結頁面)</span><span class="sxs-lookup"><span data-stu-id="d1077-222">[Manage domains](index.yml) (link page)</span></span>
