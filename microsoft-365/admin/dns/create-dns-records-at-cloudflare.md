---
title: 在 Cloudflare 建立 Office 365 的 DNS 記錄
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
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Office 365 Cloudflare。
ms.openlocfilehash: 8d64824f880bab9e6691ebf47c9508c555562fe4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211808"
---
# <a name="create-dns-records-at-cloudflare-for-office-365"></a><span data-ttu-id="828e5-103">在 Cloudflare 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="828e5-103">Create DNS records at Cloudflare for Office 365</span></span>

 <span data-ttu-id="828e5-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="828e5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="828e5-105">如果 Cloudflare 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="828e5-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="828e5-106">在 Cloudflare 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="828e5-106">After you add these records at Cloudflare, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="828e5-107">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="828e5-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="828e5-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="828e5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="828e5-111">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="828e5-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="828e5-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="828e5-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="828e5-113">您必須在您購買及註冊網域的網域註冊機構中執行此程序。</span><span class="sxs-lookup"><span data-stu-id="828e5-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="828e5-114">當您註冊 Cloudflare 時，您會使用 Cloudflare**安裝程式**來新增網域。</span><span class="sxs-lookup"><span data-stu-id="828e5-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="828e5-115">您新增的網域是從個別的網域註冊機構購買;Cloudflare 不提供網域註冊服務。</span><span class="sxs-lookup"><span data-stu-id="828e5-115">The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services.</span></span> <span data-ttu-id="828e5-116">若要在 Office 365 中驗證及建立網域的 DNS 記錄，您必須先在網域註冊機構變更名稱伺服器，以便使用 Cloudflare 的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="828e5-116">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="828e5-117">若要自行在網域註冊機構網站變更自家網域的名稱伺服器，請遵循下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="828e5-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="828e5-118">在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="828e5-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="828e5-119">您可以使用下表中的值建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，使其符合這些值。</span><span class="sxs-lookup"><span data-stu-id="828e5-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="828e5-120">First nameserver (第一個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="828e5-120">First nameserver</span></span>  <br/> |<span data-ttu-id="828e5-121">使用 Cloudflare 提供的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="828e5-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="828e5-122">Second nameserver (第二個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="828e5-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="828e5-123">使用 Cloudflare 提供的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="828e5-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="828e5-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="828e5-124">You should use at least two name server records.</span></span> <span data-ttu-id="828e5-125">如果有列出任何其他名稱伺服器，您應該將其刪除。</span><span class="sxs-lookup"><span data-stu-id="828e5-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="828e5-126">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="828e5-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="828e5-p104">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="828e5-p104">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="828e5-129">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="828e5-129">Add a TXT record for verification</span></span>
<span data-ttu-id="828e5-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="828e5-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="828e5-p105">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="828e5-p105">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="828e5-p106">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="828e5-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="828e5-135">若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用[此連結](https://www.cloudflare.com/a/login)。</span><span class="sxs-lookup"><span data-stu-id="828e5-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="828e5-136">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="828e5-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="828e5-137">在**首頁**上，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="828e5-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="828e5-138">在您網域的 [**一覽表**] 頁面上，選取 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="828e5-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="828e5-139">在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="828e5-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="828e5-140">**類型**</span><span class="sxs-lookup"><span data-stu-id="828e5-140">**Type**</span></span>|<span data-ttu-id="828e5-141">**名稱**</span><span class="sxs-lookup"><span data-stu-id="828e5-141">**Name**</span></span>|<span data-ttu-id="828e5-142">**自動 TTL**</span><span class="sxs-lookup"><span data-stu-id="828e5-142">**Automatic TTL**</span></span>|<span data-ttu-id="828e5-143">**內容**</span><span class="sxs-lookup"><span data-stu-id="828e5-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="828e5-144">TXT</span><span class="sxs-lookup"><span data-stu-id="828e5-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="828e5-145">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="828e5-145">30 minutes</span></span>  <br/> |<span data-ttu-id="828e5-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="828e5-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="828e5-147">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="828e5-147">**Note:** This is an example.</span></span> <span data-ttu-id="828e5-148">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="828e5-148">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="828e5-149">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="828e5-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="828e5-150">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="828e5-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="828e5-151">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="828e5-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="828e5-152">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="828e5-152">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="828e5-153">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="828e5-153">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="828e5-154">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="828e5-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="828e5-155">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="828e5-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="828e5-156">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="828e5-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="828e5-157">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="828e5-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="828e5-p109">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="828e5-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="828e5-161">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="828e5-161">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="828e5-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="828e5-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="828e5-163">若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用[此連結](https://www.cloudflare.com/a/login)。</span><span class="sxs-lookup"><span data-stu-id="828e5-163">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="828e5-164">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="828e5-164">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="828e5-165">在**首頁**上，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="828e5-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="828e5-166">在您網域的 [**一覽表**] 頁面上，選取 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="828e5-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="828e5-167">在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="828e5-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="828e5-168">**類型**</span><span class="sxs-lookup"><span data-stu-id="828e5-168">**Type**</span></span>|<span data-ttu-id="828e5-169">**名稱**</span><span class="sxs-lookup"><span data-stu-id="828e5-169">**Name**</span></span>|<span data-ttu-id="828e5-170">**郵件伺服器**</span><span class="sxs-lookup"><span data-stu-id="828e5-170">**Mail server**</span></span>|<span data-ttu-id="828e5-171">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="828e5-171">**Priority**</span></span>|<span data-ttu-id="828e5-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="828e5-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="828e5-173">MX</span><span class="sxs-lookup"><span data-stu-id="828e5-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="828e5-174">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="828e5-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="828e5-175">**附注：** 從您的 Office 365 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="828e5-175">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="828e5-176">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="828e5-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="828e5-177">1 </span><span class="sxs-lookup"><span data-stu-id="828e5-177">1</span></span>  <br/> <span data-ttu-id="828e5-178">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="828e5-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="828e5-179">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="828e5-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="828e5-180">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="828e5-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="828e5-181">如果 [ **Mx 記錄**] 區段中列出任何其他 MX 記錄，請選取**刪除（X）** 圖示加以刪除。</span><span class="sxs-lookup"><span data-stu-id="828e5-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="828e5-182">在確認對話方塊中，選取 [**刪除**] 以確認變更。</span><span class="sxs-lookup"><span data-stu-id="828e5-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="828e5-183">新增 Office 365 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="828e5-183">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="828e5-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="828e5-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="828e5-185">若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用[此連結](https://www.cloudflare.com/a/login)。</span><span class="sxs-lookup"><span data-stu-id="828e5-185">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="828e5-186">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="828e5-186">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="828e5-187">在**首頁**上，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="828e5-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="828e5-188">在您網域的 [**一覽表**] 頁面上，選取 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="828e5-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="828e5-189">新增五筆 CNAME 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="828e5-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="828e5-190">在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="828e5-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="828e5-191">**類型**</span><span class="sxs-lookup"><span data-stu-id="828e5-191">**Type**</span></span>|<span data-ttu-id="828e5-192">**Name** (名稱)</span><span class="sxs-lookup"><span data-stu-id="828e5-192">**Name**</span></span>|<span data-ttu-id="828e5-193">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="828e5-193">**Target**</span></span>|<span data-ttu-id="828e5-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="828e5-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="828e5-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="828e5-195">CNAME</span></span>  <br/> |<span data-ttu-id="828e5-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="828e5-196">autodiscover</span></span>  <br/> |<span data-ttu-id="828e5-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="828e5-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="828e5-198">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="828e5-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="828e5-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="828e5-199">CNAME</span></span>  <br/> |<span data-ttu-id="828e5-200">sip</span><span class="sxs-lookup"><span data-stu-id="828e5-200">sip</span></span>  <br/> |<span data-ttu-id="828e5-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="828e5-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="828e5-202">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="828e5-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="828e5-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="828e5-203">CNAME</span></span>  <br/> |<span data-ttu-id="828e5-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="828e5-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="828e5-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="828e5-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="828e5-206">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="828e5-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="828e5-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="828e5-207">CNAME</span></span>  <br/> |<span data-ttu-id="828e5-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="828e5-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="828e5-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="828e5-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="828e5-210">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="828e5-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="828e5-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="828e5-211">CNAME</span></span>  <br/> |<span data-ttu-id="828e5-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="828e5-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="828e5-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="828e5-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="828e5-214">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="828e5-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="828e5-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="828e5-215">CNAME</span></span>  <br/> |<span data-ttu-id="828e5-216">msoid</span><span class="sxs-lookup"><span data-stu-id="828e5-216">msoid</span></span>  <br/> |<span data-ttu-id="828e5-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="828e5-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="828e5-218">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="828e5-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="828e5-219">選取 [ **DNS 流量**] 圖示（橙色雲端）以略過 Cloudflare 伺服器。</span><span class="sxs-lookup"><span data-stu-id="828e5-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="828e5-220">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="828e5-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="828e5-221">逐一新增其餘五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="828e5-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="828e5-222">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="828e5-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="828e5-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="828e5-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="828e5-224">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="828e5-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="828e5-225">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="828e5-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="828e5-226">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="828e5-226">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="828e5-227">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="828e5-227">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="828e5-228">若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用[此連結](https://www.cloudflare.com/a/login)。</span><span class="sxs-lookup"><span data-stu-id="828e5-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="828e5-229">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="828e5-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="828e5-230">在**首頁**上，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="828e5-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="828e5-231">在您網域的 [**一覽表**] 頁面上，選取 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="828e5-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="828e5-232">在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="828e5-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="828e5-233">**類型**</span><span class="sxs-lookup"><span data-stu-id="828e5-233">**Type**</span></span>|<span data-ttu-id="828e5-234">**名稱**</span><span class="sxs-lookup"><span data-stu-id="828e5-234">**Name**</span></span>|<span data-ttu-id="828e5-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="828e5-235">**TTL**</span></span>|<span data-ttu-id="828e5-236">**內容**</span><span class="sxs-lookup"><span data-stu-id="828e5-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="828e5-237">TXT</span><span class="sxs-lookup"><span data-stu-id="828e5-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="828e5-238">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="828e5-238">30 minutes</span></span>  <br/> |<span data-ttu-id="828e5-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="828e5-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="828e5-240">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="828e5-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="828e5-241">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="828e5-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="828e5-242">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="828e5-242">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="828e5-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="828e5-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="828e5-244">請記住，Cloudflare 可讓您使用此功能。</span><span class="sxs-lookup"><span data-stu-id="828e5-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="828e5-245">當您看到下列步驟與目前 Cloudflare GUI （圖形使用者介面）之間的差異時，請利用[Cloudflare 社區](https://community.cloudflare.com/)。</span><span class="sxs-lookup"><span data-stu-id="828e5-245">In case you see discrepancies between the steps below and the current Cloudflare GUI(Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="828e5-246">若要開始使用，請移至您的網域頁面 Cloudflare，方法是使用[此連結](https://www.cloudflare.com/a/login)。</span><span class="sxs-lookup"><span data-stu-id="828e5-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="828e5-247">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="828e5-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="828e5-248">在**首頁**上，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="828e5-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="828e5-249">在您網域的 [**一覽表**] 頁面上，選取 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="828e5-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="828e5-250">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="828e5-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="828e5-251">在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="828e5-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="828e5-252">**類型**</span><span class="sxs-lookup"><span data-stu-id="828e5-252">**Type**</span></span>|<span data-ttu-id="828e5-253">**服務**</span><span class="sxs-lookup"><span data-stu-id="828e5-253">**Service**</span></span>|<span data-ttu-id="828e5-254">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="828e5-254">**Protocol**</span></span>|<span data-ttu-id="828e5-255">**名稱**</span><span class="sxs-lookup"><span data-stu-id="828e5-255">**Name**</span></span>|<span data-ttu-id="828e5-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="828e5-256">**TTL**</span></span>|<span data-ttu-id="828e5-257">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="828e5-257">**Priority**</span></span>|<span data-ttu-id="828e5-258">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="828e5-258">**Weight**</span></span>|<span data-ttu-id="828e5-259">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="828e5-259">**Port**</span></span>|<span data-ttu-id="828e5-260">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="828e5-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="828e5-261">SRV</span><span class="sxs-lookup"><span data-stu-id="828e5-261">SRV</span></span>|<span data-ttu-id="828e5-262">_sip</span><span class="sxs-lookup"><span data-stu-id="828e5-262">_sip</span></span> |<span data-ttu-id="828e5-263">TLS</span><span class="sxs-lookup"><span data-stu-id="828e5-263">TLS</span></span> |<span data-ttu-id="828e5-264">使用您的*domain_name*;例如，contoso.com</span><span class="sxs-lookup"><span data-stu-id="828e5-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="828e5-265">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="828e5-265">30 minutes</span></span> | <span data-ttu-id="828e5-266">100</span><span class="sxs-lookup"><span data-stu-id="828e5-266">100</span></span>|<span data-ttu-id="828e5-267">1 </span><span class="sxs-lookup"><span data-stu-id="828e5-267">1</span></span> |<span data-ttu-id="828e5-268">443</span><span class="sxs-lookup"><span data-stu-id="828e5-268">443</span></span> |<span data-ttu-id="828e5-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="828e5-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="828e5-270">SRV</span><span class="sxs-lookup"><span data-stu-id="828e5-270">SRV</span></span>|<span data-ttu-id="828e5-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="828e5-271">_sipfederationtls</span></span> | <span data-ttu-id="828e5-272">TCP</span><span class="sxs-lookup"><span data-stu-id="828e5-272">TCP</span></span>|<span data-ttu-id="828e5-273">使用您的*domain_name*;例如，contoso.com</span><span class="sxs-lookup"><span data-stu-id="828e5-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="828e5-274">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="828e5-274">30 minutes</span></span> |<span data-ttu-id="828e5-275">100</span><span class="sxs-lookup"><span data-stu-id="828e5-275">100</span></span> |<span data-ttu-id="828e5-276">1 </span><span class="sxs-lookup"><span data-stu-id="828e5-276">1</span></span> |<span data-ttu-id="828e5-277">5061</span><span class="sxs-lookup"><span data-stu-id="828e5-277">5061</span></span> | <span data-ttu-id="828e5-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="828e5-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="828e5-279">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="828e5-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="828e5-280">從資料表的第二列中選擇值，以新增其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="828e5-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="828e5-p117">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="828e5-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
