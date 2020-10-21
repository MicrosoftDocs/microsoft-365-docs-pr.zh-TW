---
title: 在 Cloudflare 建立 Microsoft 的 DNS 記錄
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
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Cloudflare。
ms.openlocfilehash: 301ed156584d9a9a2b84b88db7d6969ade5b34a2
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646148"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="dffec-103">在 Cloudflare 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="dffec-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="dffec-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="dffec-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="dffec-105">如果 Cloudflare 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="dffec-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="dffec-106">在 Cloudflare 新增這些記錄之後，您的網域就會設定為與 Microsoft 365 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="dffec-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="dffec-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dffec-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="dffec-110">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="dffec-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="dffec-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="dffec-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="dffec-112">您必須在您購買及註冊網域的網域註冊機構中執行此程序。</span><span class="sxs-lookup"><span data-stu-id="dffec-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="dffec-113">當您註冊 Cloudflare 時，您會使用 Cloudflare **安裝程式** 來新增網域。</span><span class="sxs-lookup"><span data-stu-id="dffec-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="dffec-114">您所新增的網域是從 Cloudflare 或個別網域註冊機構購買。</span><span class="sxs-lookup"><span data-stu-id="dffec-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="dffec-115">若要在 Microsoft 365 中驗證及建立網域的 DNS 記錄，您必須先在網域註冊機構變更名稱伺服器，以便使用 Cloudflare 的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="dffec-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="dffec-116">若要自行在網域註冊機構網站變更自家網域的名稱伺服器，請遵循下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="dffec-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="dffec-117">在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="dffec-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="dffec-118">您可以使用下表中的值建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，使其符合這些值。</span><span class="sxs-lookup"><span data-stu-id="dffec-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="dffec-119">First nameserver (第一個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="dffec-119">First nameserver</span></span>  <br/> |<span data-ttu-id="dffec-120">使用 Cloudflare 提供的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="dffec-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="dffec-121">Second nameserver (第二個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="dffec-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="dffec-122">使用 Cloudflare 提供的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="dffec-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="dffec-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="dffec-123">You should use at least two name server records.</span></span> <span data-ttu-id="dffec-124">如果有列出任何其他名稱伺服器，您應該將其刪除。</span><span class="sxs-lookup"><span data-stu-id="dffec-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="dffec-125">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="dffec-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dffec-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="dffec-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="dffec-127">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="dffec-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="dffec-128">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="dffec-128">Add a TXT record for verification</span></span>
<span data-ttu-id="dffec-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="dffec-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="dffec-p105">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="dffec-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dffec-p106">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="dffec-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="dffec-134">若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用 [此連結](https://www.cloudflare.com/a/login)。</span><span class="sxs-lookup"><span data-stu-id="dffec-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="dffec-135">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dffec-135">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="dffec-136">在 **首頁** 上，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="dffec-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="dffec-137">在您網域的 [ **一覽表** ] 頁面上，選取 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="dffec-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="dffec-138">在 [ **DNS 管理** ] 頁面上，按一下 [ **新增記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dffec-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="dffec-139">**類型**</span><span class="sxs-lookup"><span data-stu-id="dffec-139">**Type**</span></span>|<span data-ttu-id="dffec-140">**名稱**</span><span class="sxs-lookup"><span data-stu-id="dffec-140">**Name**</span></span>|<span data-ttu-id="dffec-141">**自動 TTL**</span><span class="sxs-lookup"><span data-stu-id="dffec-141">**Automatic TTL**</span></span>|<span data-ttu-id="dffec-142">**內容**</span><span class="sxs-lookup"><span data-stu-id="dffec-142">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="dffec-143">TXT</span><span class="sxs-lookup"><span data-stu-id="dffec-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="dffec-144">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="dffec-144">30 minutes</span></span>  <br/> |<span data-ttu-id="dffec-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="dffec-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="dffec-146">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="dffec-146">**Note:** This is an example.</span></span> <span data-ttu-id="dffec-147">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="dffec-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="dffec-148">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="dffec-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="dffec-149">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="dffec-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="dffec-150">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="dffec-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="dffec-151">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並搜尋該記錄。</span><span class="sxs-lookup"><span data-stu-id="dffec-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="dffec-152">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="dffec-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="dffec-153">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="dffec-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="dffec-154">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="dffec-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="dffec-155">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="dffec-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="dffec-156">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="dffec-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="dffec-p109">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dffec-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="dffec-160">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="dffec-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="dffec-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="dffec-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="dffec-162">若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用 [此連結](https://www.cloudflare.com/a/login)。</span><span class="sxs-lookup"><span data-stu-id="dffec-162">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="dffec-163">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dffec-163">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="dffec-164">在 **首頁** 上，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="dffec-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="dffec-165">在您網域的 [ **一覽表** ] 頁面上，選取 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="dffec-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="dffec-166">在 [ **DNS 管理** ] 頁面上，按一下 [ **新增記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dffec-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="dffec-167">**類型**</span><span class="sxs-lookup"><span data-stu-id="dffec-167">**Type**</span></span>|<span data-ttu-id="dffec-168">**名稱**</span><span class="sxs-lookup"><span data-stu-id="dffec-168">**Name**</span></span>|<span data-ttu-id="dffec-169">**郵件伺服器**</span><span class="sxs-lookup"><span data-stu-id="dffec-169">**Mail server**</span></span>|<span data-ttu-id="dffec-170">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="dffec-170">**Priority**</span></span>|<span data-ttu-id="dffec-171">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dffec-171">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dffec-172">MX</span><span class="sxs-lookup"><span data-stu-id="dffec-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="dffec-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dffec-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="dffec-174">\**附注：\*\*\*\<domain-key\>* 從您的 Microsoft 365 帳戶取得。</span><span class="sxs-lookup"><span data-stu-id="dffec-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="dffec-175">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="dffec-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="dffec-176">1 </span><span class="sxs-lookup"><span data-stu-id="dffec-176">1</span></span>  <br/> <span data-ttu-id="dffec-177">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="dffec-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="dffec-178">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="dffec-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="dffec-179">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="dffec-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="dffec-180">如果 [ **Mx 記錄** ] 區段中列出任何其他 MX 記錄，請選取 [ \*\*刪除 (X]) \*\* 圖示加以刪除。</span><span class="sxs-lookup"><span data-stu-id="dffec-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="dffec-181">在確認對話方塊中，選取 [ **刪除** ] 以確認變更。</span><span class="sxs-lookup"><span data-stu-id="dffec-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="dffec-182">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="dffec-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="dffec-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="dffec-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="dffec-184">若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用 [此連結](https://www.cloudflare.com/a/login)。</span><span class="sxs-lookup"><span data-stu-id="dffec-184">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="dffec-185">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dffec-185">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="dffec-186">在 **首頁** 上，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="dffec-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="dffec-187">在您網域的 [ **一覽表** ] 頁面上，選取 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="dffec-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="dffec-188">新增五筆 CNAME 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="dffec-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="dffec-189">在 [ **DNS 管理** ] 頁面上，按一下 [ **新增記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dffec-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="dffec-190">**類型**</span><span class="sxs-lookup"><span data-stu-id="dffec-190">**Type**</span></span>|<span data-ttu-id="dffec-191">**Name** (名稱)</span><span class="sxs-lookup"><span data-stu-id="dffec-191">**Name**</span></span>|<span data-ttu-id="dffec-192">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="dffec-192">**Target**</span></span>|<span data-ttu-id="dffec-193">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dffec-193">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dffec-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="dffec-194">CNAME</span></span>  <br/> |<span data-ttu-id="dffec-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="dffec-195">autodiscover</span></span>  <br/> |<span data-ttu-id="dffec-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dffec-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="dffec-197">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="dffec-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="dffec-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="dffec-198">CNAME</span></span>  <br/> |<span data-ttu-id="dffec-199">sip</span><span class="sxs-lookup"><span data-stu-id="dffec-199">sip</span></span>  <br/> |<span data-ttu-id="dffec-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dffec-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="dffec-201">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="dffec-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="dffec-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="dffec-202">CNAME</span></span>  <br/> |<span data-ttu-id="dffec-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="dffec-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="dffec-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dffec-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="dffec-205">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="dffec-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="dffec-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="dffec-206">CNAME</span></span>  <br/> |<span data-ttu-id="dffec-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="dffec-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="dffec-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="dffec-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="dffec-209">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="dffec-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="dffec-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="dffec-210">CNAME</span></span>  <br/> |<span data-ttu-id="dffec-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="dffec-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="dffec-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dffec-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="dffec-213">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="dffec-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="dffec-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="dffec-214">CNAME</span></span>  <br/> |<span data-ttu-id="dffec-215">msoid</span><span class="sxs-lookup"><span data-stu-id="dffec-215">msoid</span></span>  <br/> |<span data-ttu-id="dffec-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="dffec-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="dffec-217">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="dffec-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="dffec-218">選取 [ **DNS 流量** ] 圖示 (橙色雲端) 略過 Cloudflare server。</span><span class="sxs-lookup"><span data-stu-id="dffec-218">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="dffec-219">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="dffec-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="dffec-220">逐一新增其餘五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="dffec-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="dffec-221">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="dffec-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="dffec-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="dffec-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="dffec-223">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="dffec-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="dffec-224">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="dffec-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="dffec-225">如果網域已經有 SPF 記錄，請勿為 Microsoft 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="dffec-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="dffec-226">而是，請將必要的 Microsoft 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="dffec-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="dffec-227">若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用 [此連結](https://www.cloudflare.com/a/login)。</span><span class="sxs-lookup"><span data-stu-id="dffec-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="dffec-228">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dffec-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="dffec-229">在 **首頁** 上，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="dffec-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="dffec-230">在您網域的 [ **一覽表** ] 頁面上，選取 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="dffec-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="dffec-231">在 [ **DNS 管理** ] 頁面上，按一下 [ **新增記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dffec-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="dffec-232">**類型**</span><span class="sxs-lookup"><span data-stu-id="dffec-232">**Type**</span></span>|<span data-ttu-id="dffec-233">**名稱**</span><span class="sxs-lookup"><span data-stu-id="dffec-233">**Name**</span></span>|<span data-ttu-id="dffec-234">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dffec-234">**TTL**</span></span>|<span data-ttu-id="dffec-235">**內容**</span><span class="sxs-lookup"><span data-stu-id="dffec-235">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dffec-236">TXT</span><span class="sxs-lookup"><span data-stu-id="dffec-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="dffec-237">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="dffec-237">30 minutes</span></span>  <br/> |<span data-ttu-id="dffec-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="dffec-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="dffec-239">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="dffec-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="dffec-240">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="dffec-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="dffec-241">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="dffec-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="dffec-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="dffec-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="dffec-243">請記住，Cloudflare 可讓您使用此功能。</span><span class="sxs-lookup"><span data-stu-id="dffec-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="dffec-244">當您看到下列步驟與目前的 Cloudflare GUI (圖形使用者介面) 時，請利用 [Cloudflare 社區](https://community.cloudflare.com/)。</span><span class="sxs-lookup"><span data-stu-id="dffec-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="dffec-245">若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用 [此連結](https://www.cloudflare.com/a/login)。</span><span class="sxs-lookup"><span data-stu-id="dffec-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="dffec-246">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dffec-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="dffec-247">在 **首頁** 上，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="dffec-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="dffec-248">在您網域的 [ **一覽表** ] 頁面上，選取 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="dffec-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="dffec-249">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="dffec-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="dffec-250">在 [ **DNS 管理** ] 頁面上，按一下 [ **新增記錄**]，然後選取下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="dffec-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="dffec-251">**Type**</span><span class="sxs-lookup"><span data-stu-id="dffec-251">**Type**</span></span>|<span data-ttu-id="dffec-252">**服務**</span><span class="sxs-lookup"><span data-stu-id="dffec-252">**Service**</span></span>|<span data-ttu-id="dffec-253">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="dffec-253">**Protocol**</span></span>|<span data-ttu-id="dffec-254">**名稱**</span><span class="sxs-lookup"><span data-stu-id="dffec-254">**Name**</span></span>|<span data-ttu-id="dffec-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dffec-255">**TTL**</span></span>|<span data-ttu-id="dffec-256">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="dffec-256">**Priority**</span></span>|<span data-ttu-id="dffec-257">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="dffec-257">**Weight**</span></span>|<span data-ttu-id="dffec-258">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="dffec-258">**Port**</span></span>|<span data-ttu-id="dffec-259">**Target**</span><span class="sxs-lookup"><span data-stu-id="dffec-259">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dffec-260">SRV</span><span class="sxs-lookup"><span data-stu-id="dffec-260">SRV</span></span>|<span data-ttu-id="dffec-261">_sip</span><span class="sxs-lookup"><span data-stu-id="dffec-261">_sip</span></span> |<span data-ttu-id="dffec-262">TLS</span><span class="sxs-lookup"><span data-stu-id="dffec-262">TLS</span></span> |<span data-ttu-id="dffec-263">使用您的 *domain_name*;例如，contoso.com</span><span class="sxs-lookup"><span data-stu-id="dffec-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="dffec-264">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="dffec-264">30 minutes</span></span> | <span data-ttu-id="dffec-265">100</span><span class="sxs-lookup"><span data-stu-id="dffec-265">100</span></span>|<span data-ttu-id="dffec-266">1 </span><span class="sxs-lookup"><span data-stu-id="dffec-266">1</span></span> |<span data-ttu-id="dffec-267">443</span><span class="sxs-lookup"><span data-stu-id="dffec-267">443</span></span> |<span data-ttu-id="dffec-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dffec-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="dffec-269">SRV</span><span class="sxs-lookup"><span data-stu-id="dffec-269">SRV</span></span>|<span data-ttu-id="dffec-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="dffec-270">_sipfederationtls</span></span> | <span data-ttu-id="dffec-271">TCP</span><span class="sxs-lookup"><span data-stu-id="dffec-271">TCP</span></span>|<span data-ttu-id="dffec-272">使用您的 *domain_name*;例如，contoso.com</span><span class="sxs-lookup"><span data-stu-id="dffec-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="dffec-273">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="dffec-273">30 minutes</span></span> |<span data-ttu-id="dffec-274">100</span><span class="sxs-lookup"><span data-stu-id="dffec-274">100</span></span> |<span data-ttu-id="dffec-275">1 </span><span class="sxs-lookup"><span data-stu-id="dffec-275">1</span></span> |<span data-ttu-id="dffec-276">5061</span><span class="sxs-lookup"><span data-stu-id="dffec-276">5061</span></span> | <span data-ttu-id="dffec-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dffec-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="dffec-278">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="dffec-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="dffec-279">從資料表的第二列中選擇值，以新增其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="dffec-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="dffec-p117">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dffec-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
