---
title: 在 web.com 建立 Office 365 的 DNS 記錄
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
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Office 365 web.com。
ms.openlocfilehash: d5546b55392849aac9049613bd860f937ffb7618
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211071"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a><span data-ttu-id="c5a0b-103">在 web.com 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="c5a0b-103">Create DNS records at web.com for Office 365</span></span>

 <span data-ttu-id="c5a0b-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c5a0b-105">如果 web.com 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c5a0b-106">在 web.com 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-106">After you add these records at web.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="c5a0b-107">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="c5a0b-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="c5a0b-111">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="c5a0b-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="c5a0b-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="c5a0b-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5a0b-113">您必須在您購買及註冊網域的網域註冊機構中執行此程序。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="c5a0b-114">當您註冊 web.com 時，您會使用 web.com**安裝程式**來新增網域。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="c5a0b-115">若要在 Office 365 中驗證及建立網域的 DNS 記錄，您必須先在您的網域註冊機構中變更名稱伺服器，以使用 web .com 的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-115">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="c5a0b-116">若要自行在網域註冊機構網站變更自家網域的名稱伺服器，請遵循下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="c5a0b-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="c5a0b-117">在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="c5a0b-118">您可以使用下表中的值建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，使其符合這些值。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="c5a0b-119">First nameserver (第一個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="c5a0b-119">First nameserver</span></span>  <br/> |<span data-ttu-id="c5a0b-120">使用 web.com 提供的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="c5a0b-121">Second nameserver (第二個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="c5a0b-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="c5a0b-122">使用 web.com 提供的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="c5a0b-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="c5a0b-123">You should use at least two name server records.</span></span> <span data-ttu-id="c5a0b-124">如果有列出任何其他名稱伺服器，您應該將其刪除。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="c5a0b-125">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c5a0b-p103">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-p103">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c5a0b-128">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="c5a0b-128">Add a TXT record for verification</span></span>
<span data-ttu-id="c5a0b-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c5a0b-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c5a0b-p104">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c5a0b-p105">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c5a0b-134">若要開始使用，請移至您的網域頁面 web.com，方法是使用[此連結](https://checkout.web.com/manage-it/index.jsp)。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="c5a0b-135">先登入。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-135">Log in first.</span></span>
  
2. <span data-ttu-id="c5a0b-136">在 [**帳戶管理員**] 頁面上，選取 [**我的網功能變數名稱稱**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="c5a0b-137">在 [\* \* Manage \* my domain \* \* \*] 底下，選取 [**編輯高級 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="c5a0b-138">在 [**網功能變數名稱稱**] 頁面的 [**文字（TXT 記錄）**] 下，按一下 [**編輯 TXT 記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="c5a0b-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-139">**Host**</span></span>|<span data-ttu-id="c5a0b-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-140">**TTL**</span></span>|<span data-ttu-id="c5a0b-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="c5a0b-142">3600</span><span class="sxs-lookup"><span data-stu-id="c5a0b-142">3600</span></span>  <br/> |<span data-ttu-id="c5a0b-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c5a0b-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c5a0b-144">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-144">**Note:** This is an example.</span></span> <span data-ttu-id="c5a0b-145">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-145">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="c5a0b-146">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="c5a0b-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="c5a0b-147">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="c5a0b-148">請等候幾分鐘，再驗證新的 TXT 記錄，讓您剛才建立的記錄可以在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c5a0b-149">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="c5a0b-150">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-150">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c5a0b-151">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="c5a0b-152">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="c5a0b-153">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="c5a0b-154">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="c5a0b-p108">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="c5a0b-158">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="c5a0b-158">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="c5a0b-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c5a0b-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="c5a0b-160">若要開始使用，請移至您的網域頁面 web.com，方法是使用[此連結](https://checkout.web.com/manage-it/index.jsp)。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="c5a0b-161">先登入。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-161">Log in first.</span></span>
  
2. <span data-ttu-id="c5a0b-162">在 [**帳戶管理員**] 頁面上，選取 [**我的網功能變數名稱稱**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="c5a0b-163">在 [\* \* Manage \* my domain \* \* \*] 底下，選取 [**編輯高級 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="c5a0b-164">在 **[郵件伺服器（MX 記錄）**] 下，按一下 [**編輯 MX 記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="c5a0b-165">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="c5a0b-165">**Priority**</span></span>|<span data-ttu-id="c5a0b-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-166">**TTL**</span></span>|<span data-ttu-id="c5a0b-167">**郵件伺服器**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="c5a0b-168">1 </span><span class="sxs-lookup"><span data-stu-id="c5a0b-168">1</span></span>  <br/> <span data-ttu-id="c5a0b-169">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5a0b-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="c5a0b-170">3600</span><span class="sxs-lookup"><span data-stu-id="c5a0b-170">3600</span></span>  <br/> |<span data-ttu-id="c5a0b-171">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c5a0b-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="c5a0b-172">**附注：** 從您的 Office 365 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-172">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="c5a0b-173">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="c5a0b-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="c5a0b-174">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="c5a0b-175">如果 [ **Mx 記錄**] 區段中列出任何其他 MX 記錄，請選取 [**刪除**] 底下的記錄旁的核取方塊，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="c5a0b-176">在確認畫面上，選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="c5a0b-177">新增 Office 365 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="c5a0b-177">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="c5a0b-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c5a0b-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="c5a0b-179">若要開始使用，請移至您的網域頁面 web.com，方法是使用[此連結](https://checkout.web.com/manage-it/index.jsp)。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="c5a0b-180">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="c5a0b-181">在 [**帳戶管理員**] 頁面上，選取 [**我的網功能變數名稱稱**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="c5a0b-182">在 [\* \* Manage \* my domain \* \* \*] 底下，選取 [**編輯高級 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="c5a0b-183">新增六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="c5a0b-184">在 **[主機別名（CNAME 記錄）**] 下，按一下 [**編輯 CNAME 記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="c5a0b-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-185">**Alias**</span></span>|<span data-ttu-id="c5a0b-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-186">**TTL**</span></span>|<span data-ttu-id="c5a0b-187">**參照的主機名稱**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-187">**Refers to Host Name**</span></span>|<span data-ttu-id="c5a0b-188">**其他主機**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c5a0b-189">autodiscover (自動探索)</span><span class="sxs-lookup"><span data-stu-id="c5a0b-189">autodiscover</span></span>  <br/> |<span data-ttu-id="c5a0b-190">3600</span><span class="sxs-lookup"><span data-stu-id="c5a0b-190">3600</span></span>  <br/> |<span data-ttu-id="c5a0b-191">@ （無）</span><span class="sxs-lookup"><span data-stu-id="c5a0b-191">@ (none)</span></span>  <br/> |<span data-ttu-id="c5a0b-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c5a0b-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="c5a0b-193">sip</span><span class="sxs-lookup"><span data-stu-id="c5a0b-193">sip</span></span>  <br/> |<span data-ttu-id="c5a0b-194">3600</span><span class="sxs-lookup"><span data-stu-id="c5a0b-194">3600</span></span>  <br/> |<span data-ttu-id="c5a0b-195">@ （無）</span><span class="sxs-lookup"><span data-stu-id="c5a0b-195">@ (none)</span></span>  <br/> |<span data-ttu-id="c5a0b-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c5a0b-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="c5a0b-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c5a0b-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c5a0b-198">3600</span><span class="sxs-lookup"><span data-stu-id="c5a0b-198">3600</span></span>  <br/> |<span data-ttu-id="c5a0b-199">@ （無）</span><span class="sxs-lookup"><span data-stu-id="c5a0b-199">@ (none)</span></span>  <br/> | <span data-ttu-id="c5a0b-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c5a0b-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="c5a0b-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c5a0b-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c5a0b-202">3600</span><span class="sxs-lookup"><span data-stu-id="c5a0b-202">3600</span></span>  <br/> |<span data-ttu-id="c5a0b-203">@ （無）</span><span class="sxs-lookup"><span data-stu-id="c5a0b-203">@ (none)</span></span>  <br/> |<span data-ttu-id="c5a0b-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c5a0b-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="c5a0b-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c5a0b-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c5a0b-206">3600</span><span class="sxs-lookup"><span data-stu-id="c5a0b-206">3600</span></span>  <br/> |<span data-ttu-id="c5a0b-207">@ （無）</span><span class="sxs-lookup"><span data-stu-id="c5a0b-207">@ (none)</span></span>  <br/> |<span data-ttu-id="c5a0b-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c5a0b-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="c5a0b-209">msoid</span><span class="sxs-lookup"><span data-stu-id="c5a0b-209">msoid</span></span>  <br/> |<span data-ttu-id="c5a0b-210">3600</span><span class="sxs-lookup"><span data-stu-id="c5a0b-210">3600</span></span>  <br/> |<span data-ttu-id="c5a0b-211">@ （無）</span><span class="sxs-lookup"><span data-stu-id="c5a0b-211">@ (none)</span></span>  <br/> |<span data-ttu-id="c5a0b-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="c5a0b-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="c5a0b-213">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="c5a0b-214">逐一新增其餘五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c5a0b-215">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="c5a0b-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c5a0b-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c5a0b-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5a0b-217">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c5a0b-218">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c5a0b-219">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="c5a0b-220">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-220">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="c5a0b-221">若要開始使用，請移至您的網域頁面 web.com，方法是使用[此連結](https://checkout.web.com/manage-it/index.jsp)。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="c5a0b-222">先登入。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="c5a0b-223">在 [**帳戶管理員**] 頁面上，選取 [**我的網功能變數名稱稱**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="c5a0b-224">在 [\* \* Manage \* my domain \* \* \*] 底下，選取 [**編輯高級 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="c5a0b-225">在 [**網功能變數名稱稱**] 頁面的 [**文字（TXT 記錄）**] 下，按一下 [**編輯 TXT 記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="c5a0b-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-226">**Host**</span></span>|<span data-ttu-id="c5a0b-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-227">**TTL**</span></span>|<span data-ttu-id="c5a0b-228">**Text**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c5a0b-229">3600</span><span class="sxs-lookup"><span data-stu-id="c5a0b-229">3600</span></span>  <br/> |<span data-ttu-id="c5a0b-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c5a0b-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c5a0b-231">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="c5a0b-232">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-232">Select **Continue**.</span></span>

6. <span data-ttu-id="c5a0b-233">選取 [儲存變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="c5a0b-234">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="c5a0b-234">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="c5a0b-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c5a0b-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5a0b-236">請記住，web.com 可讓您使用此功能。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="c5a0b-237">當您看到下列步驟與目前 web.com GUI （圖形使用者介面）之間的差異時，請利用[Web.com 社區](https://community.web.com.com/)。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="c5a0b-238">若要開始使用，請移至您的網域頁面 web.com，方法是使用[此連結](https://checkout.web.com/manage-it/index.jsp)。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="c5a0b-239">先登入。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-239">Log in first.</span></span>
      
2. <span data-ttu-id="c5a0b-240">在 [**帳戶管理員**] 頁面上，選取 [**我的網功能變數名稱稱**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="c5a0b-241">在 [\* \* Manage \* my domain \* \* \*] 底下，選取 [**編輯高級 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="c5a0b-242">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="c5a0b-243">在 **[服務（SRV 記錄）**] 下，按一下 [**編輯 SRV 記錄**]，然後選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="c5a0b-244">**服務**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-244">**Service**</span></span>|<span data-ttu-id="c5a0b-245">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="c5a0b-245">**Protocol**</span></span>|<span data-ttu-id="c5a0b-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5a0b-246">**TTL**</span></span>|<span data-ttu-id="c5a0b-247">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="c5a0b-247">**Priority**</span></span>|<span data-ttu-id="c5a0b-248">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="c5a0b-248">**Weight**</span></span>|<span data-ttu-id="c5a0b-249">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="c5a0b-249">**Port**</span></span>|<span data-ttu-id="c5a0b-250">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="c5a0b-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c5a0b-251">_sip</span><span class="sxs-lookup"><span data-stu-id="c5a0b-251">_sip</span></span> |<span data-ttu-id="c5a0b-252">_tls</span><span class="sxs-lookup"><span data-stu-id="c5a0b-252">_tls</span></span> |<span data-ttu-id="c5a0b-253">3600</span><span class="sxs-lookup"><span data-stu-id="c5a0b-253">3600</span></span> | <span data-ttu-id="c5a0b-254">100</span><span class="sxs-lookup"><span data-stu-id="c5a0b-254">100</span></span>|<span data-ttu-id="c5a0b-255">1 </span><span class="sxs-lookup"><span data-stu-id="c5a0b-255">1</span></span> |<span data-ttu-id="c5a0b-256">443</span><span class="sxs-lookup"><span data-stu-id="c5a0b-256">443</span></span> |<span data-ttu-id="c5a0b-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c5a0b-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="c5a0b-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c5a0b-258">_sipfederationtls</span></span> |<span data-ttu-id="c5a0b-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="c5a0b-259">_tcp</span></span> |<span data-ttu-id="c5a0b-260">3600</span><span class="sxs-lookup"><span data-stu-id="c5a0b-260">3600</span></span> |<span data-ttu-id="c5a0b-261">100</span><span class="sxs-lookup"><span data-stu-id="c5a0b-261">100</span></span> |<span data-ttu-id="c5a0b-262">1 </span><span class="sxs-lookup"><span data-stu-id="c5a0b-262">1</span></span> |<span data-ttu-id="c5a0b-263">5061</span><span class="sxs-lookup"><span data-stu-id="c5a0b-263">5061</span></span> | <span data-ttu-id="c5a0b-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c5a0b-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="c5a0b-265">從資料表的第二列中選擇值，以新增其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="c5a0b-266">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-266">Select **Continue**.</span></span>

7. <span data-ttu-id="c5a0b-267">選取 [儲存變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="c5a0b-p116">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c5a0b-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
