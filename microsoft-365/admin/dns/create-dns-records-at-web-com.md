---
title: 在 web.com 建立 Microsoft 的 DNS 記錄
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft web.com。
ms.openlocfilehash: a7567688ad9935b30c0749cb7aeffdbe128506ef
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048876"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="20f56-103">在 web.com 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="20f56-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="20f56-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="20f56-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="20f56-105">如果 web.com 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="20f56-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="20f56-106">在 web.com 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="20f56-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="20f56-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="20f56-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="20f56-110">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="20f56-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="20f56-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="20f56-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="20f56-112">您必須在您購買及註冊網域的網域註冊機構中執行此程序。</span><span class="sxs-lookup"><span data-stu-id="20f56-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="20f56-113">當您註冊 web.com 時，您會使用 web.com**安裝程式**來新增網域。</span><span class="sxs-lookup"><span data-stu-id="20f56-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="20f56-114">若要在 Microsoft 中驗證及建立網域的 DNS 記錄，您必須先在您的網域註冊機構中變更名稱伺服器，以使用 web.config 的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="20f56-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="20f56-115">若要自行在網域註冊機構網站變更自家網域的名稱伺服器，請遵循下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="20f56-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="20f56-116">在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="20f56-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="20f56-117">您可以使用下表中的值建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，使其符合這些值。</span><span class="sxs-lookup"><span data-stu-id="20f56-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="20f56-118">First nameserver (第一個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="20f56-118">First nameserver</span></span>  <br/> |<span data-ttu-id="20f56-119">使用 web.com 提供的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="20f56-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="20f56-120">Second nameserver (第二個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="20f56-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="20f56-121">使用 web.com 提供的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="20f56-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="20f56-122">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="20f56-122">You should use at least two name server records.</span></span> <span data-ttu-id="20f56-123">如果有列出任何其他名稱伺服器，您應該將其刪除。</span><span class="sxs-lookup"><span data-stu-id="20f56-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="20f56-124">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="20f56-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="20f56-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="20f56-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="20f56-126">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="20f56-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="20f56-127">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="20f56-127">Add a TXT record for verification</span></span>
<span data-ttu-id="20f56-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="20f56-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="20f56-p104">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="20f56-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20f56-p105">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="20f56-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="20f56-133">若要開始使用，請移至您的網域頁面 web.com，方法是使用[此連結](https://checkout.web.com/manage-it/index.jsp)。</span><span class="sxs-lookup"><span data-stu-id="20f56-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="20f56-134">先登入。</span><span class="sxs-lookup"><span data-stu-id="20f56-134">Log in first.</span></span>
  
2. <span data-ttu-id="20f56-135">在 [**帳戶管理員**] 頁面上，選取 [**我的網功能變數名稱稱**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="20f56-136">在 [\* \* Manage \* my domain \* \* \*] 底下，選取 [**編輯高級 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="20f56-137">在 [**網功能變數名稱稱**] 頁面的 [**文字（TXT 記錄）**] 下，按一下 [**編輯 TXT 記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="20f56-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="20f56-138">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="20f56-138">**Host**</span></span>|<span data-ttu-id="20f56-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20f56-139">**TTL**</span></span>|<span data-ttu-id="20f56-140">**Text**</span><span class="sxs-lookup"><span data-stu-id="20f56-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="20f56-141">3600</span><span class="sxs-lookup"><span data-stu-id="20f56-141">3600</span></span>  <br/> |<span data-ttu-id="20f56-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="20f56-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="20f56-143">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="20f56-143">**Note:** This is an example.</span></span> <span data-ttu-id="20f56-144">在這裡請使用您自己來自表格的 [目的地或指向位址]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="20f56-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="20f56-145">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="20f56-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="20f56-146">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="20f56-147">請等候幾分鐘，再驗證新的 TXT 記錄，讓您剛才建立的記錄可以在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="20f56-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="20f56-148">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="20f56-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="20f56-149">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="20f56-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="20f56-150">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="20f56-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="20f56-151">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="20f56-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="20f56-152">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="20f56-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="20f56-153">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="20f56-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="20f56-p108">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="20f56-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="20f56-157">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="20f56-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="20f56-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="20f56-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="20f56-159">若要開始使用，請移至您的網域頁面 web.com，方法是使用[此連結](https://checkout.web.com/manage-it/index.jsp)。</span><span class="sxs-lookup"><span data-stu-id="20f56-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="20f56-160">先登入。</span><span class="sxs-lookup"><span data-stu-id="20f56-160">Log in first.</span></span>
  
2. <span data-ttu-id="20f56-161">在 [**帳戶管理員**] 頁面上，選取 [**我的網功能變數名稱稱**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="20f56-162">在 [\* \* Manage \* my domain \* \* \*] 底下，選取 [**編輯高級 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="20f56-163">在 **[郵件伺服器（MX 記錄）**] 下，按一下 [**編輯 MX 記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="20f56-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="20f56-164">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="20f56-164">**Priority**</span></span>|<span data-ttu-id="20f56-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20f56-165">**TTL**</span></span>|<span data-ttu-id="20f56-166">**郵件伺服器**</span><span class="sxs-lookup"><span data-stu-id="20f56-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="20f56-167">1</span><span class="sxs-lookup"><span data-stu-id="20f56-167">1</span></span>  <br/> <span data-ttu-id="20f56-168">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="20f56-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="20f56-169">3600</span><span class="sxs-lookup"><span data-stu-id="20f56-169">3600</span></span>  <br/> |<span data-ttu-id="20f56-170">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="20f56-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="20f56-171">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="20f56-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="20f56-172">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="20f56-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="20f56-173">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20f56-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="20f56-174">如果 [ **Mx 記錄**] 區段中列出任何其他 MX 記錄，請選取 [**刪除**] 底下的記錄旁的核取方塊，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="20f56-175">在確認畫面上，選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="20f56-176">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="20f56-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="20f56-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="20f56-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="20f56-178">若要開始使用，請移至您的網域頁面 web.com，方法是使用[此連結](https://checkout.web.com/manage-it/index.jsp)。</span><span class="sxs-lookup"><span data-stu-id="20f56-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="20f56-179">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="20f56-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="20f56-180">在 [**帳戶管理員**] 頁面上，選取 [**我的網功能變數名稱稱**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="20f56-181">在 [\* \* Manage \* my domain \* \* \*] 底下，選取 [**編輯高級 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="20f56-182">新增六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="20f56-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="20f56-183">在 **[主機別名（CNAME 記錄）**] 下，按一下 [**編輯 CNAME 記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="20f56-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="20f56-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="20f56-184">**Alias**</span></span>|<span data-ttu-id="20f56-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20f56-185">**TTL**</span></span>|<span data-ttu-id="20f56-186">**參照的主機名稱**</span><span class="sxs-lookup"><span data-stu-id="20f56-186">**Refers to Host Name**</span></span>|<span data-ttu-id="20f56-187">**其他主機**</span><span class="sxs-lookup"><span data-stu-id="20f56-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="20f56-188">autodiscover (自動探索)</span><span class="sxs-lookup"><span data-stu-id="20f56-188">autodiscover</span></span>  <br/> |<span data-ttu-id="20f56-189">3600</span><span class="sxs-lookup"><span data-stu-id="20f56-189">3600</span></span>  <br/> |<span data-ttu-id="20f56-190">@ （無）</span><span class="sxs-lookup"><span data-stu-id="20f56-190">@ (none)</span></span>  <br/> |<span data-ttu-id="20f56-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="20f56-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="20f56-192">sip</span><span class="sxs-lookup"><span data-stu-id="20f56-192">sip</span></span>  <br/> |<span data-ttu-id="20f56-193">3600</span><span class="sxs-lookup"><span data-stu-id="20f56-193">3600</span></span>  <br/> |<span data-ttu-id="20f56-194">@ （無）</span><span class="sxs-lookup"><span data-stu-id="20f56-194">@ (none)</span></span>  <br/> |<span data-ttu-id="20f56-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="20f56-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="20f56-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="20f56-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="20f56-197">3600</span><span class="sxs-lookup"><span data-stu-id="20f56-197">3600</span></span>  <br/> |<span data-ttu-id="20f56-198">@ （無）</span><span class="sxs-lookup"><span data-stu-id="20f56-198">@ (none)</span></span>  <br/> | <span data-ttu-id="20f56-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="20f56-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="20f56-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="20f56-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="20f56-201">3600</span><span class="sxs-lookup"><span data-stu-id="20f56-201">3600</span></span>  <br/> |<span data-ttu-id="20f56-202">@ （無）</span><span class="sxs-lookup"><span data-stu-id="20f56-202">@ (none)</span></span>  <br/> |<span data-ttu-id="20f56-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="20f56-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="20f56-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="20f56-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="20f56-205">3600</span><span class="sxs-lookup"><span data-stu-id="20f56-205">3600</span></span>  <br/> |<span data-ttu-id="20f56-206">@ （無）</span><span class="sxs-lookup"><span data-stu-id="20f56-206">@ (none)</span></span>  <br/> |<span data-ttu-id="20f56-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20f56-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="20f56-208">msoid</span><span class="sxs-lookup"><span data-stu-id="20f56-208">msoid</span></span>  <br/> |<span data-ttu-id="20f56-209">3600</span><span class="sxs-lookup"><span data-stu-id="20f56-209">3600</span></span>  <br/> |<span data-ttu-id="20f56-210">@ （無）</span><span class="sxs-lookup"><span data-stu-id="20f56-210">@ (none)</span></span>  <br/> |<span data-ttu-id="20f56-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="20f56-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="20f56-212">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="20f56-213">逐一新增其餘五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="20f56-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="20f56-214">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="20f56-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="20f56-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="20f56-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="20f56-216">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="20f56-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="20f56-217">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="20f56-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="20f56-218">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="20f56-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="20f56-219">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="20f56-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="20f56-220">若要開始使用，請移至您的網域頁面 web.com，方法是使用[此連結](https://checkout.web.com/manage-it/index.jsp)。</span><span class="sxs-lookup"><span data-stu-id="20f56-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="20f56-221">先登入。</span><span class="sxs-lookup"><span data-stu-id="20f56-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="20f56-222">在 [**帳戶管理員**] 頁面上，選取 [**我的網功能變數名稱稱**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="20f56-223">在 [\* \* Manage \* my domain \* \* \*] 底下，選取 [**編輯高級 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="20f56-224">在 [**網功能變數名稱稱**] 頁面的 [**文字（TXT 記錄）**] 下，按一下 [**編輯 TXT 記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="20f56-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="20f56-225">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="20f56-225">**Host**</span></span>|<span data-ttu-id="20f56-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20f56-226">**TTL**</span></span>|<span data-ttu-id="20f56-227">**Text**</span><span class="sxs-lookup"><span data-stu-id="20f56-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="20f56-228">3600</span><span class="sxs-lookup"><span data-stu-id="20f56-228">3600</span></span>  <br/> |<span data-ttu-id="20f56-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="20f56-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="20f56-230">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="20f56-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="20f56-231">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-231">Select **Continue**.</span></span>

6. <span data-ttu-id="20f56-232">選取 [儲存變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20f56-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="20f56-233">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="20f56-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="20f56-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="20f56-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="20f56-235">請記住，web.com 可讓您使用此功能。</span><span class="sxs-lookup"><span data-stu-id="20f56-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="20f56-236">當您看到下列步驟與目前 web.com GUI （圖形使用者介面）之間的差異時，請利用[Web.com 社區](https://community.web.com.com/)。</span><span class="sxs-lookup"><span data-stu-id="20f56-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="20f56-237">若要開始使用，請移至您的網域頁面 web.com，方法是使用[此連結](https://checkout.web.com/manage-it/index.jsp)。</span><span class="sxs-lookup"><span data-stu-id="20f56-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="20f56-238">先登入。</span><span class="sxs-lookup"><span data-stu-id="20f56-238">Log in first.</span></span>
      
2. <span data-ttu-id="20f56-239">在 [**帳戶管理員**] 頁面上，選取 [**我的網功能變數名稱稱**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="20f56-240">在 [\* \* Manage \* my domain \* \* \*] 底下，選取 [**編輯高級 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="20f56-241">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="20f56-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="20f56-242">在 **[服務（SRV 記錄）**] 下，按一下 [**編輯 SRV 記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="20f56-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="20f56-243">**服務**</span><span class="sxs-lookup"><span data-stu-id="20f56-243">**Service**</span></span>|<span data-ttu-id="20f56-244">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="20f56-244">**Protocol**</span></span>|<span data-ttu-id="20f56-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="20f56-245">**TTL**</span></span>|<span data-ttu-id="20f56-246">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="20f56-246">**Priority**</span></span>|<span data-ttu-id="20f56-247">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="20f56-247">**Weight**</span></span>|<span data-ttu-id="20f56-248">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="20f56-248">**Port**</span></span>|<span data-ttu-id="20f56-249">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="20f56-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="20f56-250">_sip</span><span class="sxs-lookup"><span data-stu-id="20f56-250">_sip</span></span> |<span data-ttu-id="20f56-251">_tls</span><span class="sxs-lookup"><span data-stu-id="20f56-251">_tls</span></span> |<span data-ttu-id="20f56-252">3600</span><span class="sxs-lookup"><span data-stu-id="20f56-252">3600</span></span> | <span data-ttu-id="20f56-253">100</span><span class="sxs-lookup"><span data-stu-id="20f56-253">100</span></span>|<span data-ttu-id="20f56-254">1</span><span class="sxs-lookup"><span data-stu-id="20f56-254">1</span></span> |<span data-ttu-id="20f56-255">443</span><span class="sxs-lookup"><span data-stu-id="20f56-255">443</span></span> |<span data-ttu-id="20f56-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="20f56-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="20f56-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="20f56-257">_sipfederationtls</span></span> |<span data-ttu-id="20f56-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="20f56-258">_tcp</span></span> |<span data-ttu-id="20f56-259">3600</span><span class="sxs-lookup"><span data-stu-id="20f56-259">3600</span></span> |<span data-ttu-id="20f56-260">100</span><span class="sxs-lookup"><span data-stu-id="20f56-260">100</span></span> |<span data-ttu-id="20f56-261">1</span><span class="sxs-lookup"><span data-stu-id="20f56-261">1</span></span> |<span data-ttu-id="20f56-262">5061</span><span class="sxs-lookup"><span data-stu-id="20f56-262">5061</span></span> | <span data-ttu-id="20f56-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="20f56-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="20f56-264">從資料表的第二列中選擇值，以新增其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="20f56-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="20f56-265">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="20f56-265">Select **Continue**.</span></span>

7. <span data-ttu-id="20f56-266">選取 [儲存變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20f56-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="20f56-p116">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="20f56-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
