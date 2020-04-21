---
title: 在 Wix 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Wix。
ms.openlocfilehash: 2cbc4887f276e63f09b433225e09315c227c961c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629236"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="34dbf-103">在 Wix 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="34dbf-103">Create DNS records at Wix for Microsoft</span></span>

 <span data-ttu-id="34dbf-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="34dbf-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="34dbf-105">如果 Wix 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="34dbf-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="34dbf-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="34dbf-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="34dbf-107">[新增 TXT 記錄以供驗證](#add-a-txt-record-for-verification)。</span><span class="sxs-lookup"><span data-stu-id="34dbf-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="34dbf-108">[新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="34dbf-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="34dbf-109">[新增 Microsoft 所需的五個 CNAME 記錄](#add-the-five-cname-records-that-are-required-for-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="34dbf-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="34dbf-110">[新增 SPF 的 TXT 記錄，以協助防止電子郵件垃圾](#add-a-txt-record-for-spf-to-help-prevent-email-spam)郵件。</span><span class="sxs-lookup"><span data-stu-id="34dbf-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="34dbf-111">[新增 Microsoft 所需的兩筆 SRV 記錄](#add-the-two-srv-records-that-are-required-for-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="34dbf-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="34dbf-112">在 Wix 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="34dbf-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="34dbf-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="34dbf-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="34dbf-116">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="34dbf-116">Add a TXT record for verification</span></span>
<span data-ttu-id="34dbf-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="34dbf-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="34dbf-118">在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="34dbf-118">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="34dbf-119">您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。</span><span class="sxs-lookup"><span data-stu-id="34dbf-119">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34dbf-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="34dbf-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="34dbf-122">若要開始使用，請移至您的網域頁面 Wix，方法是使用[此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="34dbf-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="34dbf-123">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="34dbf-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="34dbf-124">在 [**我的網域**] 頁面上，選取 [**高級**] 區域中的 [**編輯 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="34dbf-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="34dbf-125">在 DNS 編輯器的 [ **TXT （文字）** ] 列中，選取 [ **+ 新增其他**]。</span><span class="sxs-lookup"><span data-stu-id="34dbf-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="34dbf-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="34dbf-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="34dbf-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="34dbf-127">**Host Name**</span></span> <br/> |<span data-ttu-id="34dbf-128">**TXT Value** (TXT 值)</span><span class="sxs-lookup"><span data-stu-id="34dbf-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="34dbf-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34dbf-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="34dbf-130">自動填入</span><span class="sxs-lookup"><span data-stu-id="34dbf-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="34dbf-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="34dbf-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="34dbf-132">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="34dbf-132">**Note:** This is an example.</span></span> <span data-ttu-id="34dbf-133">從表格中，使用您的特定**目的地或指向位址**值。</span><span class="sxs-lookup"><span data-stu-id="34dbf-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="34dbf-134">如何找到這項資訊？</span><span class="sxs-lookup"><span data-stu-id="34dbf-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="34dbf-135">1 Hour</span><span class="sxs-lookup"><span data-stu-id="34dbf-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="34dbf-136">選取 [DNS 編輯器] 頂端的 [**儲存 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="34dbf-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="34dbf-137">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="34dbf-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="34dbf-138">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求記錄。</span><span class="sxs-lookup"><span data-stu-id="34dbf-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="34dbf-139">當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="34dbf-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="34dbf-140">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="34dbf-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="34dbf-141">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="34dbf-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="34dbf-142">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="34dbf-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="34dbf-143">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="34dbf-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="34dbf-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="34dbf-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="34dbf-147">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="34dbf-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="34dbf-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="34dbf-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="34dbf-149">若要開始使用，請移至您的網域頁面 Wix，方法是使用[此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="34dbf-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="34dbf-150">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="34dbf-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="34dbf-151">在 [**我的網域**] 頁面上的 [**信箱**] 區域中，選取 [**設定您的 MX 記錄**] 連結。</span><span class="sxs-lookup"><span data-stu-id="34dbf-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="34dbf-152">從**您的電子郵件提供者**下拉式清單中選擇 [**其他**]。</span><span class="sxs-lookup"><span data-stu-id="34dbf-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="34dbf-153">選取 [ **+ 另外新增**]。</span><span class="sxs-lookup"><span data-stu-id="34dbf-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="34dbf-154">在新記錄的方塊中，輸入或複製並貼上下清單格中的值：</span><span class="sxs-lookup"><span data-stu-id="34dbf-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="34dbf-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="34dbf-155">**Host Name**</span></span>|<span data-ttu-id="34dbf-156">**Points to** (指向)</span><span class="sxs-lookup"><span data-stu-id="34dbf-156">**Points to**</span></span>|<span data-ttu-id="34dbf-157">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="34dbf-157">**Priority**</span></span>|<span data-ttu-id="34dbf-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34dbf-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="34dbf-159">自動填入</span><span class="sxs-lookup"><span data-stu-id="34dbf-159">Automatically populated</span></span> <br/> | <span data-ttu-id="34dbf-160">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="34dbf-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="34dbf-161">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="34dbf-161">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="34dbf-162">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="34dbf-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="34dbf-163">0</span><span class="sxs-lookup"><span data-stu-id="34dbf-163">0</span></span>  <br/> <span data-ttu-id="34dbf-164">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span><span class="sxs-lookup"><span data-stu-id="34dbf-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span></span> | <span data-ttu-id="34dbf-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="34dbf-165">1 Hour</span></span>|
   
6. <span data-ttu-id="34dbf-166">如果有列出任何其他的 MX 記錄，請將其全部刪除。</span><span class="sxs-lookup"><span data-stu-id="34dbf-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="34dbf-167">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34dbf-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="34dbf-168">在 [確認] 對話方塊中，選取 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="34dbf-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="34dbf-169">新增 Microsoft 所需的五個 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="34dbf-169">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="34dbf-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="34dbf-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="34dbf-171">若要開始使用，請移至您的網域頁面 Wix，方法是使用[此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="34dbf-171">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="34dbf-172">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="34dbf-172">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="34dbf-173">在 [**我的網域**] 頁面上，選取 [**高級**] 區域中的 [**編輯 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="34dbf-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="34dbf-174">針對每個 CNAME 記錄，在 DNS 編輯器的 [ **CNAME （別名）** ] 列中，選取 [ **+ 新增其他**]。</span><span class="sxs-lookup"><span data-stu-id="34dbf-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="34dbf-175">在新記錄的方塊中，輸入或複製並貼上下清單格中的值：</span><span class="sxs-lookup"><span data-stu-id="34dbf-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="34dbf-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="34dbf-176">**Host Name**</span></span>|<span data-ttu-id="34dbf-177">**Points to** (指向)</span><span class="sxs-lookup"><span data-stu-id="34dbf-177">**Points to**</span></span>|<span data-ttu-id="34dbf-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34dbf-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34dbf-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="34dbf-179">autodiscover</span></span>  <br/> |<span data-ttu-id="34dbf-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="34dbf-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="34dbf-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="34dbf-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="34dbf-182">sip</span><span class="sxs-lookup"><span data-stu-id="34dbf-182">sip</span></span>  <br/> |<span data-ttu-id="34dbf-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="34dbf-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="34dbf-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="34dbf-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="34dbf-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="34dbf-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="34dbf-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="34dbf-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="34dbf-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="34dbf-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="34dbf-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="34dbf-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="34dbf-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="34dbf-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="34dbf-190">1 小時</span><span class="sxs-lookup"><span data-stu-id="34dbf-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="34dbf-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="34dbf-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="34dbf-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="34dbf-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="34dbf-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="34dbf-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="34dbf-194">選取 [DNS 編輯器] 頂端的 [**儲存 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="34dbf-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="34dbf-195">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="34dbf-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="34dbf-196">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="34dbf-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="34dbf-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="34dbf-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="34dbf-198">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="34dbf-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="34dbf-199">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="34dbf-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="34dbf-200">如果您已有網域的 SPF 記錄，請不要為 Microsoft 建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="34dbf-200">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="34dbf-201">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="34dbf-201">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="34dbf-202">若要開始使用，請移至您的網域頁面 Wix，方法是使用[此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="34dbf-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="34dbf-203">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="34dbf-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="34dbf-204">在 [**我的網域**] 頁面上，選取 [**高級**] 區域中的 [**編輯 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="34dbf-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="34dbf-205">在 DNS 編輯器的 [ **TXT （文字）** ] 列中，選取 [ **+ 新增其他**]。</span><span class="sxs-lookup"><span data-stu-id="34dbf-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="34dbf-206">在新記錄的方塊中，輸入或複製並貼上下清單格中的值：</span><span class="sxs-lookup"><span data-stu-id="34dbf-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="34dbf-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="34dbf-207">**Host Name**</span></span>|<span data-ttu-id="34dbf-208">**TXT Value** (TXT 值)</span><span class="sxs-lookup"><span data-stu-id="34dbf-208">**TXT Value**</span></span>|<span data-ttu-id="34dbf-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34dbf-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34dbf-210">[保留此空白]</span><span class="sxs-lookup"><span data-stu-id="34dbf-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="34dbf-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="34dbf-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="34dbf-212">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="34dbf-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="34dbf-213">TXT</span><span class="sxs-lookup"><span data-stu-id="34dbf-213">TXT</span></span>  <br/> | <span data-ttu-id="34dbf-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="34dbf-214">1 Hour</span></span> |
   
5. <span data-ttu-id="34dbf-215">選取 [DNS 編輯器] 頂端的 [**儲存 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="34dbf-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="34dbf-216">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="34dbf-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="34dbf-217">新增 Microsoft 所需的兩筆 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="34dbf-217">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="34dbf-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="34dbf-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="34dbf-219">若要開始使用，請移至您的網域頁面 Wix，方法是使用[此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="34dbf-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="34dbf-220">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="34dbf-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="34dbf-221">在 [**我的網域**] 頁面上，選取 [**高級**] 區域中的 [**編輯 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="34dbf-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="34dbf-222">在 DNS 編輯器的 [ **SRV** ] 列中，選取 [ **+ 另外新增**]。</span><span class="sxs-lookup"><span data-stu-id="34dbf-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="34dbf-223">在新記錄的方塊中，輸入或複製並貼上下清單格中的值：</span><span class="sxs-lookup"><span data-stu-id="34dbf-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="34dbf-224">**Service** (服務)</span><span class="sxs-lookup"><span data-stu-id="34dbf-224">**Service**</span></span>|<span data-ttu-id="34dbf-225">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="34dbf-225">**Protocol**</span></span>|<span data-ttu-id="34dbf-226">**Name** (名稱)</span><span class="sxs-lookup"><span data-stu-id="34dbf-226">**Name**</span></span>|<span data-ttu-id="34dbf-227">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="34dbf-227">**Weight**</span></span>|<span data-ttu-id="34dbf-228">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="34dbf-228">**Port**</span></span>|<span data-ttu-id="34dbf-229">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="34dbf-229">**Target**</span></span>|<span data-ttu-id="34dbf-230">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="34dbf-230">**Priority**</span></span>|<span data-ttu-id="34dbf-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="34dbf-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="34dbf-232">sip</span><span class="sxs-lookup"><span data-stu-id="34dbf-232">sip</span></span>  |<span data-ttu-id="34dbf-233">tls</span><span class="sxs-lookup"><span data-stu-id="34dbf-233">tls</span></span>  |<span data-ttu-id="34dbf-234">自動填入</span><span class="sxs-lookup"><span data-stu-id="34dbf-234">Automatically populated</span></span> |<span data-ttu-id="34dbf-235">1 </span><span class="sxs-lookup"><span data-stu-id="34dbf-235">1</span></span>  |<span data-ttu-id="34dbf-236">443</span><span class="sxs-lookup"><span data-stu-id="34dbf-236">443</span></span>   |<span data-ttu-id="34dbf-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="34dbf-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="34dbf-238">100</span><span class="sxs-lookup"><span data-stu-id="34dbf-238">100</span></span> |<span data-ttu-id="34dbf-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="34dbf-239">1 Hour</span></span> |
|<span data-ttu-id="34dbf-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="34dbf-240">sipfed</span></span>|<span data-ttu-id="34dbf-241">tcp</span><span class="sxs-lookup"><span data-stu-id="34dbf-241">tcp</span></span> |<span data-ttu-id="34dbf-242">自動填入</span><span class="sxs-lookup"><span data-stu-id="34dbf-242">Automatically populated</span></span>|<span data-ttu-id="34dbf-243">1 </span><span class="sxs-lookup"><span data-stu-id="34dbf-243">1</span></span> |<span data-ttu-id="34dbf-244">5061</span><span class="sxs-lookup"><span data-stu-id="34dbf-244">5061</span></span> |<span data-ttu-id="34dbf-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="34dbf-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="34dbf-246">100</span><span class="sxs-lookup"><span data-stu-id="34dbf-246">100</span></span> | <span data-ttu-id="34dbf-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="34dbf-247">1 Hour</span></span> |
   
5. <span data-ttu-id="34dbf-248">選取 [DNS 編輯器] 頂端的 [**儲存 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="34dbf-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="34dbf-249">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="34dbf-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="34dbf-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="34dbf-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

