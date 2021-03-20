---
title: 在 Wix 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Wix。
ms.openlocfilehash: 3ec2ea0dc24e1872ba22e591fae96b39a9a0deee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916103"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="c74ce-103">在 Wix 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="c74ce-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="c74ce-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="c74ce-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c74ce-105">如果 Wix 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="c74ce-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="c74ce-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="c74ce-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="c74ce-107">[新增 TXT 記錄以供驗證](#add-a-txt-record-for-verification)。</span><span class="sxs-lookup"><span data-stu-id="c74ce-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="c74ce-108">[新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="c74ce-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="c74ce-109">[新增 Microsoft 所需的五個 CNAME 記錄](#add-the-five-cname-records-that-are-required-for-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="c74ce-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="c74ce-110">[新增 SPF 的 TXT 記錄，以協助防止電子郵件垃圾](#add-a-txt-record-for-spf-to-help-prevent-email-spam)郵件。</span><span class="sxs-lookup"><span data-stu-id="c74ce-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="c74ce-111">[新增 Microsoft 所需的兩筆 SRV 記錄](#add-the-two-srv-records-that-are-required-for-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="c74ce-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="c74ce-112">在 Wix 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="c74ce-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="c74ce-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c74ce-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c74ce-116">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="c74ce-116">Add a TXT record for verification</span></span>
<span data-ttu-id="c74ce-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="c74ce-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="c74ce-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="c74ce-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c74ce-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="c74ce-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="c74ce-122">WIX 不支援子域的 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="c74ce-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="c74ce-123">若要開始使用，請移至您的網域頁面 Wix，方法是使用 [此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="c74ce-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c74ce-124">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="c74ce-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c74ce-125">在 [ **我的網域** ] 頁面上，選取 [ **高級** ] 區域中的 [ **編輯 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c74ce-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c74ce-126">在 DNS 編輯器的 [ **TXT (Text)** ] 列中，選取 [ **+ 新增其他**]。</span><span class="sxs-lookup"><span data-stu-id="c74ce-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="c74ce-127">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c74ce-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="c74ce-128">主機名稱</span><span class="sxs-lookup"><span data-stu-id="c74ce-128">Host Name</span></span> <br/> | <span data-ttu-id="c74ce-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="c74ce-129">TXT Value</span></span> <br/> | <span data-ttu-id="c74ce-130">TTL</span><span class="sxs-lookup"><span data-stu-id="c74ce-130">TTL</span></span> <br/> |
   |<span data-ttu-id="c74ce-131">自動填入</span><span class="sxs-lookup"><span data-stu-id="c74ce-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="c74ce-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c74ce-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c74ce-133">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="c74ce-133">**Note:** This is an example.</span></span> <span data-ttu-id="c74ce-134">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="c74ce-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="c74ce-135">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="c74ce-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="c74ce-136">1 小時</span><span class="sxs-lookup"><span data-stu-id="c74ce-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="c74ce-137">選取 [DNS 編輯器] 頂端的 [ **儲存 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c74ce-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c74ce-138">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="c74ce-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c74ce-139">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="c74ce-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="c74ce-140">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="c74ce-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c74ce-141">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c74ce-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c74ce-142">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="c74ce-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="c74ce-143">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="c74ce-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="c74ce-144">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="c74ce-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c74ce-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c74ce-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c74ce-148">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c74ce-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c74ce-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="c74ce-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="c74ce-150">若要開始使用，請移至您的網域頁面 Wix，方法是使用 [此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="c74ce-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c74ce-151">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="c74ce-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c74ce-152">在 [ **我的網域** ] 頁面上的 [ **信箱** ] 區域中，選取 [ **設定您的 MX 記錄** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="c74ce-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="c74ce-153">從 **您的電子郵件提供者** 下拉式清單中選擇 [**其他**]。</span><span class="sxs-lookup"><span data-stu-id="c74ce-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="c74ce-154">選取 [ **+ 另外新增**]。</span><span class="sxs-lookup"><span data-stu-id="c74ce-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="c74ce-155">在新記錄的方塊中，輸入或複製並貼上下清單格中的值：</span><span class="sxs-lookup"><span data-stu-id="c74ce-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c74ce-156">主機名稱</span><span class="sxs-lookup"><span data-stu-id="c74ce-156">Host Name</span></span> | <span data-ttu-id="c74ce-157">指向</span><span class="sxs-lookup"><span data-stu-id="c74ce-157">Points to</span></span> | <span data-ttu-id="c74ce-158">優先順序</span><span class="sxs-lookup"><span data-stu-id="c74ce-158">Priority</span></span> | <span data-ttu-id="c74ce-159">TTL</span><span class="sxs-lookup"><span data-stu-id="c74ce-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="c74ce-160">自動填入</span><span class="sxs-lookup"><span data-stu-id="c74ce-160">Automatically populated</span></span> <br/> | <span data-ttu-id="c74ce-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c74ce-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="c74ce-162">\**附注：\*\*\*\<domain-key\>* 從您的 Microsoft 帳戶取得。</span><span class="sxs-lookup"><span data-stu-id="c74ce-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="c74ce-163">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="c74ce-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="c74ce-164">0</span><span class="sxs-lookup"><span data-stu-id="c74ce-164">0</span></span>  <br/> <span data-ttu-id="c74ce-165">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="c74ce-165">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> | <span data-ttu-id="c74ce-166">1 小時</span><span class="sxs-lookup"><span data-stu-id="c74ce-166">1 Hour</span></span>|
   
6. <span data-ttu-id="c74ce-167">如果有列出任何其他的 MX 記錄，請將其全部刪除。</span><span class="sxs-lookup"><span data-stu-id="c74ce-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="c74ce-168">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="c74ce-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="c74ce-169">在 [確認] 對話方塊中，選取 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="c74ce-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c74ce-170">新增 Microsoft 所需的5筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="c74ce-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c74ce-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="c74ce-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="c74ce-172">若要開始使用，請移至您的網域頁面 Wix，方法是使用 [此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="c74ce-172">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c74ce-173">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="c74ce-173">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c74ce-174">在 [ **我的網域** ] 頁面上，選取 [ **高級** ] 區域中的 [ **編輯 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c74ce-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c74ce-175">在 [每個 CNAME 記錄的 DNS 編輯器] 的 [ **CNAME (別名)** 列中，選取 [ **+ 新增其他**]。</span><span class="sxs-lookup"><span data-stu-id="c74ce-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="c74ce-176">在新記錄的方塊中，輸入或複製並貼上下清單格中的值：</span><span class="sxs-lookup"><span data-stu-id="c74ce-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c74ce-177">主機名稱</span><span class="sxs-lookup"><span data-stu-id="c74ce-177">Host Name</span></span> | <span data-ttu-id="c74ce-178">Points to </span><span class="sxs-lookup"><span data-stu-id="c74ce-178">Points to</span></span> | <span data-ttu-id="c74ce-179">TTL</span><span class="sxs-lookup"><span data-stu-id="c74ce-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="c74ce-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c74ce-180">autodiscover</span></span>  <br/> |<span data-ttu-id="c74ce-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c74ce-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="c74ce-182">1 小時</span><span class="sxs-lookup"><span data-stu-id="c74ce-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="c74ce-183">sip</span><span class="sxs-lookup"><span data-stu-id="c74ce-183">sip</span></span>  <br/> |<span data-ttu-id="c74ce-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c74ce-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="c74ce-185">1 小時</span><span class="sxs-lookup"><span data-stu-id="c74ce-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="c74ce-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c74ce-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c74ce-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c74ce-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="c74ce-188">1 小時</span><span class="sxs-lookup"><span data-stu-id="c74ce-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="c74ce-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c74ce-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c74ce-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c74ce-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="c74ce-191">1 小時</span><span class="sxs-lookup"><span data-stu-id="c74ce-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="c74ce-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c74ce-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c74ce-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c74ce-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="c74ce-194">1 Hour</span><span class="sxs-lookup"><span data-stu-id="c74ce-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="c74ce-195">選取 [DNS 編輯器] 頂端的 [ **儲存 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c74ce-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c74ce-196">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="c74ce-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c74ce-197">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="c74ce-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c74ce-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="c74ce-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c74ce-199">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="c74ce-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c74ce-200">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="c74ce-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c74ce-201">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="c74ce-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c74ce-202">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="c74ce-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="c74ce-203">若要開始使用，請移至您的網域頁面 Wix，方法是使用 [此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="c74ce-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c74ce-204">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="c74ce-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c74ce-205">在 [ **我的網域** ] 頁面上，選取 [ **高級** ] 區域中的 [ **編輯 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c74ce-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c74ce-206">在 DNS 編輯器的 [ **TXT (Text)** ] 列中，選取 [ **+ 新增其他**]。</span><span class="sxs-lookup"><span data-stu-id="c74ce-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="c74ce-207">在新記錄的方塊中，輸入或複製並貼上下清單格中的值：</span><span class="sxs-lookup"><span data-stu-id="c74ce-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c74ce-208">主機名稱</span><span class="sxs-lookup"><span data-stu-id="c74ce-208">Host Name</span></span> | <span data-ttu-id="c74ce-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="c74ce-209">TXT Value</span></span> | <span data-ttu-id="c74ce-210">TTL</span><span class="sxs-lookup"><span data-stu-id="c74ce-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="c74ce-211">[保留此空白]</span><span class="sxs-lookup"><span data-stu-id="c74ce-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="c74ce-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c74ce-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c74ce-213">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="c74ce-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="c74ce-214">TXT</span><span class="sxs-lookup"><span data-stu-id="c74ce-214">TXT</span></span>  <br/> | <span data-ttu-id="c74ce-215">1 Hour</span><span class="sxs-lookup"><span data-stu-id="c74ce-215">1 Hour</span></span> |
   
5. <span data-ttu-id="c74ce-216">選取 [DNS 編輯器] 頂端的 [ **儲存 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c74ce-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c74ce-217">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="c74ce-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c74ce-218">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="c74ce-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c74ce-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="c74ce-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="c74ce-220">若要開始使用，請移至您的網域頁面 Wix，方法是使用 [此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="c74ce-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c74ce-221">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="c74ce-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c74ce-222">在 [ **我的網域** ] 頁面上，選取 [ **高級** ] 區域中的 [ **編輯 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c74ce-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c74ce-223">在 DNS 編輯器的 [ **SRV** ] 列中，選取 [ **+ 另外新增**]。</span><span class="sxs-lookup"><span data-stu-id="c74ce-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="c74ce-224">在新記錄的方塊中，輸入或複製並貼上下清單格中的值：</span><span class="sxs-lookup"><span data-stu-id="c74ce-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c74ce-225">Service (服務)</span><span class="sxs-lookup"><span data-stu-id="c74ce-225">Service</span></span> | <span data-ttu-id="c74ce-226">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="c74ce-226">Protocol</span></span> | <span data-ttu-id="c74ce-227">Name (名稱)</span><span class="sxs-lookup"><span data-stu-id="c74ce-227">Name</span></span> | <span data-ttu-id="c74ce-228">Weight (權數)</span><span class="sxs-lookup"><span data-stu-id="c74ce-228">Weight</span></span> | <span data-ttu-id="c74ce-229">Port (連接埠)</span><span class="sxs-lookup"><span data-stu-id="c74ce-229">Port</span></span> | <span data-ttu-id="c74ce-230">Target (目標)</span><span class="sxs-lookup"><span data-stu-id="c74ce-230">Target</span></span> | <span data-ttu-id="c74ce-231">Priority (優先順序)</span><span class="sxs-lookup"><span data-stu-id="c74ce-231">Priority</span></span> | <span data-ttu-id="c74ce-232">TTL</span><span class="sxs-lookup"><span data-stu-id="c74ce-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="c74ce-233">sip</span><span class="sxs-lookup"><span data-stu-id="c74ce-233">sip</span></span>  |<span data-ttu-id="c74ce-234">tls</span><span class="sxs-lookup"><span data-stu-id="c74ce-234">tls</span></span>  |<span data-ttu-id="c74ce-235">自動填入</span><span class="sxs-lookup"><span data-stu-id="c74ce-235">Automatically populated</span></span> |<span data-ttu-id="c74ce-236">1</span><span class="sxs-lookup"><span data-stu-id="c74ce-236">1</span></span>  |<span data-ttu-id="c74ce-237">443</span><span class="sxs-lookup"><span data-stu-id="c74ce-237">443</span></span>   |<span data-ttu-id="c74ce-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c74ce-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="c74ce-239">100</span><span class="sxs-lookup"><span data-stu-id="c74ce-239">100</span></span> |<span data-ttu-id="c74ce-240">1 Hour</span><span class="sxs-lookup"><span data-stu-id="c74ce-240">1 Hour</span></span> |
   |<span data-ttu-id="c74ce-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="c74ce-241">sipfed</span></span>|<span data-ttu-id="c74ce-242">tcp</span><span class="sxs-lookup"><span data-stu-id="c74ce-242">tcp</span></span> |<span data-ttu-id="c74ce-243">自動填入</span><span class="sxs-lookup"><span data-stu-id="c74ce-243">Automatically populated</span></span>|<span data-ttu-id="c74ce-244">1</span><span class="sxs-lookup"><span data-stu-id="c74ce-244">1</span></span> |<span data-ttu-id="c74ce-245">5061</span><span class="sxs-lookup"><span data-stu-id="c74ce-245">5061</span></span> |<span data-ttu-id="c74ce-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c74ce-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="c74ce-247">100</span><span class="sxs-lookup"><span data-stu-id="c74ce-247">100</span></span> | <span data-ttu-id="c74ce-248">1 Hour</span><span class="sxs-lookup"><span data-stu-id="c74ce-248">1 Hour</span></span> |
   
5. <span data-ttu-id="c74ce-249">選取 [DNS 編輯器] 頂端的 [ **儲存 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c74ce-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c74ce-250">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="c74ce-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c74ce-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c74ce-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
