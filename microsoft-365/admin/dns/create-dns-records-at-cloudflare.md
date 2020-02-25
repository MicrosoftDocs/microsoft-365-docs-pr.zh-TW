---
title: 在 Cloudflare 建立 Office 365 的 DNS 記錄
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 Skype for Business Online，並在 Cloudflare 其他服務的 DNS 記錄。
ms.openlocfilehash: efd7a4a41a0cc27c2a50da732d648c87c79c6ff7
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240382"
---
# <a name="create-dns-records-at-cloudflare-for-office-365"></a><span data-ttu-id="7f9f0-103">在 Cloudflare 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="7f9f0-103">Create DNS records at Cloudflare for Office 365</span></span>

 <span data-ttu-id="7f9f0-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7f9f0-105">如果 Cloudflare 是您 DNS 主機服務提供者，請遵循本篇文章以驗證您的網域和設定 DNS 記錄的電子郵件、 Skype for Business Online 等等中的步驟。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="7f9f0-106">在 Cloudflare 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-106">After you add these records at Cloudflare, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="7f9f0-107">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="7f9f0-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="7f9f0-111">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="7f9f0-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="7f9f0-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="7f9f0-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f9f0-113">您必須在您購買及註冊網域的網域註冊機構中執行此程序。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="7f9f0-114">當您註冊 Cloudflare 」 時，您可以新增網域使用 Cloudflare**安裝**程序。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="7f9f0-115">您新增的網域已購買從不同的網域註冊機構中;Cloudflare 並不提供網域註冊服務。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-115">The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services.</span></span> <span data-ttu-id="7f9f0-116">若要確認並在 Office 365 建立 DNS 記錄為您的網域，您需要變更的名稱伺服器，在您網域註冊機構，讓他們使用 Cloudflare 的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-116">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="7f9f0-117">若要自行在網域註冊機構網站變更自家網域的名稱伺服器，請遵循下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="7f9f0-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="7f9f0-118">在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="7f9f0-119">在下列表格中，使用的值來建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，使其符合這些值。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="7f9f0-120">First nameserver (第一個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="7f9f0-120">First nameserver</span></span>  <br/> |<span data-ttu-id="7f9f0-121">使用 Cloudflare 所提供的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="7f9f0-122">Second nameserver (第二個名稱伺服器)</span><span class="sxs-lookup"><span data-stu-id="7f9f0-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="7f9f0-123">使用 Cloudflare 所提供的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="7f9f0-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-124">You should use at least two name server records.</span></span> <span data-ttu-id="7f9f0-125">如果沒有列出任何其他名稱伺服器，您應該將予以刪除。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="7f9f0-126">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7f9f0-p104">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-p104">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7f9f0-129">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="7f9f0-129">Add a TXT record for verification</span></span>
<span data-ttu-id="7f9f0-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7f9f0-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7f9f0-p105">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-p105">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f9f0-p106">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7f9f0-135">若要開始，使用[這個連結](https://www.cloudflare.com/a/login)移至您在 Cloudflare 的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="7f9f0-136">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="7f9f0-137">在 [**首頁**] 頁面上，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="7f9f0-138">在您網域的 [**概觀**] 頁面上，選取 [ **DNS**。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="7f9f0-139">在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取值從下表。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="7f9f0-140">**類型**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-140">**Type**</span></span>|<span data-ttu-id="7f9f0-141">**名稱**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-141">**Name**</span></span>|<span data-ttu-id="7f9f0-142">**自動 TTL**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-142">**Automatic TTL**</span></span>|<span data-ttu-id="7f9f0-143">**內容**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="7f9f0-144">TXT</span><span class="sxs-lookup"><span data-stu-id="7f9f0-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="7f9f0-145">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="7f9f0-145">30 minutes</span></span>  <br/> |<span data-ttu-id="7f9f0-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7f9f0-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7f9f0-147">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-147">**Note:** This is an example.</span></span> <span data-ttu-id="7f9f0-148">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-148">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="7f9f0-149">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="7f9f0-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="7f9f0-150">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="7f9f0-151">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7f9f0-152">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-152">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="7f9f0-153">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-153">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7f9f0-154">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7f9f0-155">在 [**網域**] 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7f9f0-156">在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7f9f0-157">在 [**驗證網域**] 頁面上，選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7f9f0-p109">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="7f9f0-161">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="7f9f0-161">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="7f9f0-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7f9f0-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="7f9f0-163">若要開始，使用[這個連結](https://www.cloudflare.com/a/login)移至您在 Cloudflare 的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-163">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="7f9f0-164">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-164">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="7f9f0-165">在 [**首頁**] 頁面上，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="7f9f0-166">在您網域的 [**概觀**] 頁面上，選取 [ **DNS**。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="7f9f0-167">在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取值從下表。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="7f9f0-168">**類型**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-168">**Type**</span></span>|<span data-ttu-id="7f9f0-169">**名稱**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-169">**Name**</span></span>|<span data-ttu-id="7f9f0-170">**郵件伺服器**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-170">**Mail server**</span></span>|<span data-ttu-id="7f9f0-171">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="7f9f0-171">**Priority**</span></span>|<span data-ttu-id="7f9f0-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f9f0-173">MX</span><span class="sxs-lookup"><span data-stu-id="7f9f0-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="7f9f0-174">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7f9f0-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="7f9f0-175">**附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-175">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="7f9f0-176">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="7f9f0-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="7f9f0-177">1</span><span class="sxs-lookup"><span data-stu-id="7f9f0-177">1</span></span>  <br/> <span data-ttu-id="7f9f0-178">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="7f9f0-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="7f9f0-179">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="7f9f0-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="7f9f0-180">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="7f9f0-181">如果有任何其他 MX 記錄列在 [ **MX 記錄**] 區段中，請將它們刪除選取的**刪除 (X)** 圖示。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="7f9f0-182">在 [確認] 對話方塊中，選取 [**刪除**] 以確認您的變更。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="7f9f0-183">新增 Office 365 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="7f9f0-183">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="7f9f0-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7f9f0-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="7f9f0-185">若要開始，使用[這個連結](https://www.cloudflare.com/a/login)移至您在 Cloudflare 的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-185">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="7f9f0-186">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-186">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="7f9f0-187">在 [**首頁**] 頁面上，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="7f9f0-188">在您網域的 [**概觀**] 頁面上，選取 [ **DNS**。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="7f9f0-189">新增第一筆五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="7f9f0-190">在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取值從下表。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="7f9f0-191">**類型**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-191">**Type**</span></span>|<span data-ttu-id="7f9f0-192">**名稱**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-192">**Name**</span></span>|<span data-ttu-id="7f9f0-193">**Target**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-193">**Target**</span></span>|<span data-ttu-id="7f9f0-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f9f0-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f9f0-195">CNAME</span></span>  <br/> |<span data-ttu-id="7f9f0-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7f9f0-196">autodiscover</span></span>  <br/> |<span data-ttu-id="7f9f0-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7f9f0-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="7f9f0-198">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="7f9f0-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="7f9f0-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f9f0-199">CNAME</span></span>  <br/> |<span data-ttu-id="7f9f0-200">sip</span><span class="sxs-lookup"><span data-stu-id="7f9f0-200">sip</span></span>  <br/> |<span data-ttu-id="7f9f0-201">sipdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="7f9f0-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="7f9f0-202">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="7f9f0-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="7f9f0-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f9f0-203">CNAME</span></span>  <br/> |<span data-ttu-id="7f9f0-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7f9f0-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7f9f0-205">webdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="7f9f0-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="7f9f0-206">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="7f9f0-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="7f9f0-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f9f0-207">CNAME</span></span>  <br/> |<span data-ttu-id="7f9f0-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7f9f0-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7f9f0-209">enterpriseregistration.windows.net></span><span class="sxs-lookup"><span data-stu-id="7f9f0-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="7f9f0-210">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="7f9f0-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="7f9f0-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f9f0-211">CNAME</span></span>  <br/> |<span data-ttu-id="7f9f0-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7f9f0-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7f9f0-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7f9f0-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="7f9f0-214">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="7f9f0-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="7f9f0-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="7f9f0-215">CNAME</span></span>  <br/> |<span data-ttu-id="7f9f0-216">msoid</span><span class="sxs-lookup"><span data-stu-id="7f9f0-216">msoid</span></span>  <br/> |<span data-ttu-id="7f9f0-217">clientconfig.microsoftonline-p.net> qualified domain name</span><span class="sxs-lookup"><span data-stu-id="7f9f0-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="7f9f0-218">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="7f9f0-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="7f9f0-219">選取 [ **DNS 流量**] 圖示 （橘色雲端） 以略過 Cloudflare 伺服器。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="7f9f0-220">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="7f9f0-221">逐一新增其餘五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7f9f0-222">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="7f9f0-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7f9f0-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7f9f0-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f9f0-224">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7f9f0-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7f9f0-226">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-226">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="7f9f0-227">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-227">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="7f9f0-228">若要開始，使用[這個連結](https://www.cloudflare.com/a/login)移至您在 Cloudflare 的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="7f9f0-229">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="7f9f0-230">在 [**首頁**] 頁面上，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="7f9f0-231">在您網域的 [**概觀**] 頁面上，選取 [ **DNS**。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="7f9f0-232">在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取值從下表。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="7f9f0-233">**類型**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-233">**Type**</span></span>|<span data-ttu-id="7f9f0-234">**名稱**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-234">**Name**</span></span>|<span data-ttu-id="7f9f0-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-235">**TTL**</span></span>|<span data-ttu-id="7f9f0-236">**內容**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f9f0-237">TXT</span><span class="sxs-lookup"><span data-stu-id="7f9f0-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="7f9f0-238">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="7f9f0-238">30 minutes</span></span>  <br/> |<span data-ttu-id="7f9f0-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7f9f0-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7f9f0-240">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="7f9f0-241">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="7f9f0-242">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="7f9f0-242">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="7f9f0-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7f9f0-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f9f0-244">請記住 Cloudflare 負責可用這項功能。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="7f9f0-245">以防您看到下列步驟與目前 Cloudflare GUI(Graphical User Interface) 之間的差異，請利用[Cloudflare 社群](https://community.cloudflare.com/)。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-245">In case you see discrepancies between the steps below and the current Cloudflare GUI(Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="7f9f0-246">若要開始，使用[這個連結](https://www.cloudflare.com/a/login)移至您在 Cloudflare 的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="7f9f0-247">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="7f9f0-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="7f9f0-248">在 [**首頁**] 頁面上，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="7f9f0-249">在您網域的 [**概觀**] 頁面上，選取 [ **DNS**。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="7f9f0-250">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="7f9f0-251">在 [ **DNS 管理**] 頁面上，按一下 [**新增記錄**]，然後選取值從下表的第一列。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="7f9f0-252">**類型**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-252">**Type**</span></span>|<span data-ttu-id="7f9f0-253">**服務**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-253">**Service**</span></span>|<span data-ttu-id="7f9f0-254">**通訊協定**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-254">**Protocol**</span></span>|<span data-ttu-id="7f9f0-255">**Name**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-255">**Name**</span></span>|<span data-ttu-id="7f9f0-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-256">**TTL**</span></span>|<span data-ttu-id="7f9f0-257">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-257">**Priority**</span></span>|<span data-ttu-id="7f9f0-258">**Weight**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-258">**Weight**</span></span>|<span data-ttu-id="7f9f0-259">**Port**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-259">**Port**</span></span>|<span data-ttu-id="7f9f0-260">**Target**</span><span class="sxs-lookup"><span data-stu-id="7f9f0-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f9f0-261">SRV</span><span class="sxs-lookup"><span data-stu-id="7f9f0-261">SRV</span></span>|<span data-ttu-id="7f9f0-262">_sip</span><span class="sxs-lookup"><span data-stu-id="7f9f0-262">_sip</span></span> |<span data-ttu-id="7f9f0-263">TLS</span><span class="sxs-lookup"><span data-stu-id="7f9f0-263">TLS</span></span> |<span data-ttu-id="7f9f0-264">使用您的*domain_name*;例如，contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f9f0-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="7f9f0-265">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="7f9f0-265">30 minutes</span></span> | <span data-ttu-id="7f9f0-266">100</span><span class="sxs-lookup"><span data-stu-id="7f9f0-266">100</span></span>|<span data-ttu-id="7f9f0-267">1</span><span class="sxs-lookup"><span data-stu-id="7f9f0-267">1</span></span> |<span data-ttu-id="7f9f0-268">443</span><span class="sxs-lookup"><span data-stu-id="7f9f0-268">443</span></span> |<span data-ttu-id="7f9f0-269">sipfed.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="7f9f0-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="7f9f0-270">SRV</span><span class="sxs-lookup"><span data-stu-id="7f9f0-270">SRV</span></span>|<span data-ttu-id="7f9f0-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7f9f0-271">_sipfederationtls</span></span> | <span data-ttu-id="7f9f0-272">TCP</span><span class="sxs-lookup"><span data-stu-id="7f9f0-272">TCP</span></span>|<span data-ttu-id="7f9f0-273">使用您的*domain_name*;例如，contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f9f0-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="7f9f0-274">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="7f9f0-274">30 minutes</span></span> |<span data-ttu-id="7f9f0-275">100</span><span class="sxs-lookup"><span data-stu-id="7f9f0-275">100</span></span> |<span data-ttu-id="7f9f0-276">1</span><span class="sxs-lookup"><span data-stu-id="7f9f0-276">1</span></span> |<span data-ttu-id="7f9f0-277">5061</span><span class="sxs-lookup"><span data-stu-id="7f9f0-277">5061</span></span> | <span data-ttu-id="7f9f0-278">sipfed.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="7f9f0-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="7f9f0-279">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="7f9f0-280">從表格中第二列中選擇值新增其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="7f9f0-p117">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="7f9f0-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
