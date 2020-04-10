---
title: 在 Wix 建立 Office 365 的 DNS 記錄
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
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Office 365 Wix。
ms.openlocfilehash: 8487c49e989bf2db345ae9e6d0e2970c5eb40cb6
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211059"
---
# <a name="create-dns-records-at-wix-for-office-365"></a><span data-ttu-id="1c071-103">在 Wix 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="1c071-103">Create DNS records at Wix for Office 365</span></span>

 <span data-ttu-id="1c071-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="1c071-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1c071-105">如果 Wix 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="1c071-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="1c071-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="1c071-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="1c071-107">[新增 TXT 記錄以供驗證](#add-a-txt-record-for-verification)。</span><span class="sxs-lookup"><span data-stu-id="1c071-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="1c071-108">[新增 MX 記錄，以便您網域的電子郵件將會傳送至 Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="1c071-108">[Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).</span></span>
    
- <span data-ttu-id="1c071-109">[新增 Office 365 所需的五個 CNAME 記錄](#add-the-five-cname-records-that-are-required-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="1c071-109">[Add the five CNAME records that are required for Office 365](#add-the-five-cname-records-that-are-required-for-office-365).</span></span>
    
- <span data-ttu-id="1c071-110">[新增 SPF 的 TXT 記錄，以協助防止電子郵件垃圾](#add-a-txt-record-for-spf-to-help-prevent-email-spam)郵件。</span><span class="sxs-lookup"><span data-stu-id="1c071-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="1c071-111">[新增 Office 365 所需的兩筆 SRV 記錄](#add-the-two-srv-records-that-are-required-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="1c071-111">[Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365).</span></span>
    
<span data-ttu-id="1c071-112">在 Wix 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="1c071-112">After you add these records at Wix, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="1c071-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1c071-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1c071-116">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="1c071-116">Add a TXT record for verification</span></span>
<span data-ttu-id="1c071-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="1c071-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="1c071-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="1c071-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c071-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="1c071-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="1c071-122">若要開始使用，請移至您的網域頁面 Wix，方法是使用[此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="1c071-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="1c071-123">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1c071-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1c071-124">在 [**我的網域**] 頁面上，選取 [**高級**] 區域中的 [**編輯 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1c071-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="1c071-125">在 DNS 編輯器的 [ **TXT （文字）** ] 列中，選取 [ **+ 新增其他**]。</span><span class="sxs-lookup"><span data-stu-id="1c071-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="1c071-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1c071-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="1c071-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="1c071-127">**Host Name**</span></span> <br/> |<span data-ttu-id="1c071-128">**TXT Value** (TXT 值)</span><span class="sxs-lookup"><span data-stu-id="1c071-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="1c071-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1c071-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="1c071-130">自動填入</span><span class="sxs-lookup"><span data-stu-id="1c071-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="1c071-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1c071-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1c071-132">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="1c071-132">**Note:** This is an example.</span></span> <span data-ttu-id="1c071-133">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="1c071-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="1c071-134">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="1c071-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="1c071-135">1 Hour</span><span class="sxs-lookup"><span data-stu-id="1c071-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="1c071-136">選取 [DNS 編輯器] 頂端的 [**儲存 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1c071-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="1c071-137">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="1c071-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1c071-138">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="1c071-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="1c071-139">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="1c071-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1c071-140">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="1c071-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="1c071-141">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="1c071-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="1c071-142">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="1c071-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="1c071-143">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="1c071-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1c071-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1c071-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="1c071-147">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="1c071-147">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="1c071-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="1c071-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="1c071-149">若要開始使用，請移至您的網域頁面 Wix，方法是使用[此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="1c071-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="1c071-150">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1c071-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1c071-151">在 [**我的網域**] 頁面上的 [**信箱**] 區域中，選取 [**設定您的 MX 記錄**] 連結。</span><span class="sxs-lookup"><span data-stu-id="1c071-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="1c071-152">從**您的電子郵件提供者**下拉式清單中選擇 [**其他**]。</span><span class="sxs-lookup"><span data-stu-id="1c071-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="1c071-153">選取 [ **+ 另外新增**]。</span><span class="sxs-lookup"><span data-stu-id="1c071-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="1c071-154">在新記錄的方塊中，輸入或複製並貼上下清單格中的值：</span><span class="sxs-lookup"><span data-stu-id="1c071-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="1c071-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="1c071-155">**Host Name**</span></span>|<span data-ttu-id="1c071-156">**Points to** (指向)</span><span class="sxs-lookup"><span data-stu-id="1c071-156">**Points to**</span></span>|<span data-ttu-id="1c071-157">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="1c071-157">**Priority**</span></span>|<span data-ttu-id="1c071-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1c071-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1c071-159">自動填入</span><span class="sxs-lookup"><span data-stu-id="1c071-159">Automatically populated</span></span> <br/> | <span data-ttu-id="1c071-160">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1c071-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="1c071-161">**附注：** 從您的 Office 365 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="1c071-161">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="1c071-162">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="1c071-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="1c071-163">0</span><span class="sxs-lookup"><span data-stu-id="1c071-163">0</span></span>  <br/> <span data-ttu-id="1c071-164">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span><span class="sxs-lookup"><span data-stu-id="1c071-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span></span> | <span data-ttu-id="1c071-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="1c071-165">1 Hour</span></span>|
   
6. <span data-ttu-id="1c071-166">如果有列出任何其他的 MX 記錄，請將其全部刪除。</span><span class="sxs-lookup"><span data-stu-id="1c071-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="1c071-167">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1c071-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="1c071-168">在 [確認] 對話方塊中，選取 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="1c071-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="1c071-169">新增 Office 365 所需的五個 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="1c071-169">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="1c071-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="1c071-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="1c071-171">若要開始使用，請移至您的網域頁面 Wix，方法是使用[此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="1c071-171">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="1c071-172">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="1c071-172">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="1c071-173">在 [**我的網域**] 頁面上，選取 [**高級**] 區域中的 [**編輯 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1c071-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="1c071-174">針對每個 CNAME 記錄，在 DNS 編輯器的 [ **CNAME （別名）** ] 列中，選取 [ **+ 新增其他**]。</span><span class="sxs-lookup"><span data-stu-id="1c071-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="1c071-175">在新記錄的方塊中，輸入或複製並貼上下清單格中的值：</span><span class="sxs-lookup"><span data-stu-id="1c071-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="1c071-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="1c071-176">**Host Name**</span></span>|<span data-ttu-id="1c071-177">**Points to** (指向)</span><span class="sxs-lookup"><span data-stu-id="1c071-177">**Points to**</span></span>|<span data-ttu-id="1c071-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1c071-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1c071-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1c071-179">autodiscover</span></span>  <br/> |<span data-ttu-id="1c071-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1c071-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="1c071-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="1c071-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="1c071-182">sip</span><span class="sxs-lookup"><span data-stu-id="1c071-182">sip</span></span>  <br/> |<span data-ttu-id="1c071-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1c071-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1c071-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="1c071-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="1c071-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1c071-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1c071-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1c071-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="1c071-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="1c071-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="1c071-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1c071-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1c071-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1c071-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="1c071-190">1 小時</span><span class="sxs-lookup"><span data-stu-id="1c071-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="1c071-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1c071-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1c071-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1c071-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="1c071-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="1c071-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="1c071-194">選取 [DNS 編輯器] 頂端的 [**儲存 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1c071-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="1c071-195">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="1c071-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1c071-196">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="1c071-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1c071-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="1c071-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c071-198">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="1c071-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1c071-199">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="1c071-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1c071-200">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="1c071-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="1c071-201">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="1c071-201">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="1c071-202">若要開始使用，請移至您的網域頁面 Wix，方法是使用[此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="1c071-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="1c071-203">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1c071-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1c071-204">在 [**我的網域**] 頁面上，選取 [**高級**] 區域中的 [**編輯 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1c071-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="1c071-205">在 DNS 編輯器的 [ **TXT （文字）** ] 列中，選取 [ **+ 新增其他**]。</span><span class="sxs-lookup"><span data-stu-id="1c071-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="1c071-206">在新記錄的方塊中，輸入或複製並貼上下清單格中的值：</span><span class="sxs-lookup"><span data-stu-id="1c071-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="1c071-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="1c071-207">**Host Name**</span></span>|<span data-ttu-id="1c071-208">**TXT Value** (TXT 值)</span><span class="sxs-lookup"><span data-stu-id="1c071-208">**TXT Value**</span></span>|<span data-ttu-id="1c071-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1c071-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1c071-210">[保留此空白]</span><span class="sxs-lookup"><span data-stu-id="1c071-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="1c071-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1c071-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1c071-212">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="1c071-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="1c071-213">TXT</span><span class="sxs-lookup"><span data-stu-id="1c071-213">TXT</span></span>  <br/> | <span data-ttu-id="1c071-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="1c071-214">1 Hour</span></span> |
   
5. <span data-ttu-id="1c071-215">選取 [DNS 編輯器] 頂端的 [**儲存 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1c071-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="1c071-216">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="1c071-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="1c071-217">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="1c071-217">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="1c071-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="1c071-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="1c071-219">若要開始使用，請移至您的網域頁面 Wix，方法是使用[此連結](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)。</span><span class="sxs-lookup"><span data-stu-id="1c071-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="1c071-220">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1c071-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1c071-221">在 [**我的網域**] 頁面上，選取 [**高級**] 區域中的 [**編輯 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1c071-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="1c071-222">在 DNS 編輯器的 [ **SRV** ] 列中，選取 [ **+ 另外新增**]。</span><span class="sxs-lookup"><span data-stu-id="1c071-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="1c071-223">在新記錄的方塊中，輸入或複製並貼上下清單格中的值：</span><span class="sxs-lookup"><span data-stu-id="1c071-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="1c071-224">**服務**</span><span class="sxs-lookup"><span data-stu-id="1c071-224">**Service**</span></span>|<span data-ttu-id="1c071-225">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="1c071-225">**Protocol**</span></span>|<span data-ttu-id="1c071-226">**名稱**</span><span class="sxs-lookup"><span data-stu-id="1c071-226">**Name**</span></span>|<span data-ttu-id="1c071-227">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="1c071-227">**Weight**</span></span>|<span data-ttu-id="1c071-228">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="1c071-228">**Port**</span></span>|<span data-ttu-id="1c071-229">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="1c071-229">**Target**</span></span>|<span data-ttu-id="1c071-230">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="1c071-230">**Priority**</span></span>|<span data-ttu-id="1c071-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1c071-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1c071-232">sip</span><span class="sxs-lookup"><span data-stu-id="1c071-232">sip</span></span>  |<span data-ttu-id="1c071-233">tls</span><span class="sxs-lookup"><span data-stu-id="1c071-233">tls</span></span>  |<span data-ttu-id="1c071-234">自動填入</span><span class="sxs-lookup"><span data-stu-id="1c071-234">Automatically populated</span></span> |<span data-ttu-id="1c071-235">1 </span><span class="sxs-lookup"><span data-stu-id="1c071-235">1</span></span>  |<span data-ttu-id="1c071-236">443</span><span class="sxs-lookup"><span data-stu-id="1c071-236">443</span></span>   |<span data-ttu-id="1c071-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1c071-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="1c071-238">100</span><span class="sxs-lookup"><span data-stu-id="1c071-238">100</span></span> |<span data-ttu-id="1c071-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="1c071-239">1 Hour</span></span> |
|<span data-ttu-id="1c071-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="1c071-240">sipfed</span></span>|<span data-ttu-id="1c071-241">tcp</span><span class="sxs-lookup"><span data-stu-id="1c071-241">tcp</span></span> |<span data-ttu-id="1c071-242">自動填入</span><span class="sxs-lookup"><span data-stu-id="1c071-242">Automatically populated</span></span>|<span data-ttu-id="1c071-243">1 </span><span class="sxs-lookup"><span data-stu-id="1c071-243">1</span></span> |<span data-ttu-id="1c071-244">5061</span><span class="sxs-lookup"><span data-stu-id="1c071-244">5061</span></span> |<span data-ttu-id="1c071-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1c071-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="1c071-246">100</span><span class="sxs-lookup"><span data-stu-id="1c071-246">100</span></span> | <span data-ttu-id="1c071-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="1c071-247">1 Hour</span></span> |
   
5. <span data-ttu-id="1c071-248">選取 [DNS 編輯器] 頂端的 [**儲存 DNS** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1c071-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="1c071-249">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="1c071-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="1c071-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1c071-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

