---
title: 在 Microsoft 的古怪網域建立 DNS 記錄
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft 用的網域。
ms.openlocfilehash: 5a5a0f4c92e14bdfd6c54249cd66c9e88abee075
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939328"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="1face-103">在 Microsoft 的古怪網域建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="1face-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="1face-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="1face-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1face-105">如果 Crazy Domains 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="1face-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="1face-106">在您的網域新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="1face-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="1face-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1face-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1face-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="1face-110">Add a TXT record for verification</span></span>
<span data-ttu-id="1face-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1face-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1face-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="1face-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1face-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="1face-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="1face-p104">首先請用[這個連結](https://manage.crazydomains.com/members/domains/)移至 Crazy Domains 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1face-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="1face-119">在 [**我的帳戶**] 區段中，選取 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="1face-119">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="1face-121">在 [**網功能變數名稱稱**] 頁面上的 [**網域**] 區段中，選取您要更新的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="1face-121">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="1face-123">在 [ **DNS 設定**] 區段中，選取下拉式清單圖示。</span><span class="sxs-lookup"><span data-stu-id="1face-123">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="1face-125">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="1face-125">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="1face-127">Choose **TXT Record** from the **Add Record** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1face-127">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verify-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="1face-129">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1face-129">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="1face-131">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="1face-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="1face-132">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="1face-132">**Sub Domain**</span></span>|<span data-ttu-id="1face-133">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="1face-133">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1face-134">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1face-134">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1face-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1face-135">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1face-136">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="1face-136">**Note:** This is an example.</span></span> <span data-ttu-id="1face-137">在這裡請使用您自己來自表格的 [目的地或指向位址]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="1face-137">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="1face-138">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="1face-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="1face-140">選取 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="1face-140">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="1face-142">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="1face-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1face-143">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="1face-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="1face-144">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="1face-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1face-145">在 Microsoft 系統管理中心中，移至 [設定]\*\*\*\* \> [網域]<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="1face-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1face-146">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="1face-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1face-147">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="1face-147">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1face-148">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="1face-148">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1face-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1face-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1face-152">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="1face-152">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1face-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1face-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="1face-p107">首先請用[這個連結](https://manage.crazydomains.com/members/domains/)移至 Crazy Domains 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1face-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="1face-157">在 [**我的帳戶**] 區段中，選取 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="1face-157">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="1face-159">在 [**網功能變數名稱稱**] 頁面上的 [**網域**] 區段中，選取您要更新的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="1face-159">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="1face-161">在 [ **DNS 設定**] 區段中，選取下拉式清單圖示。</span><span class="sxs-lookup"><span data-stu-id="1face-161">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="1face-163">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="1face-163">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="1face-165">從 [**新增記錄：** ] 下拉式清單中，選擇 [ **MX 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="1face-165">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="1face-167">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1face-167">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="1face-169">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="1face-169">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="1face-170">（從下拉式清單中選擇 [**優先順序**] 值。）</span><span class="sxs-lookup"><span data-stu-id="1face-170">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1face-171">**Mail For Zone (區域郵件)**</span><span class="sxs-lookup"><span data-stu-id="1face-171">**Mail For Zone**</span></span>|<span data-ttu-id="1face-172">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="1face-172">**Priority**</span></span>|<span data-ttu-id="1face-173">**Assigned To Server (指派給伺服器)**</span><span class="sxs-lookup"><span data-stu-id="1face-173">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1face-174">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="1face-174">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1face-175">1 </span><span class="sxs-lookup"><span data-stu-id="1face-175">1</span></span>  <br/> <span data-ttu-id="1face-176">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="1face-176">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="1face-177">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1face-177">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="1face-178">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="1face-178">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="1face-179">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="1face-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-Configure-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="1face-181">選取 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="1face-181">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="1face-183">如果 [ **Mx 記錄**] 區段中列出任何其他 MX 記錄，請針對其中一個記錄選取 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="1face-183">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="1face-185">選取 [刪除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1face-185">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="1face-187">選取 [**更新**] 以確認刪除。</span><span class="sxs-lookup"><span data-stu-id="1face-187">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="1face-189">使用相同方法移除清單中其他所有 MX 記錄，直到只剩下您先前在本程序中新增的記錄為止。</span><span class="sxs-lookup"><span data-stu-id="1face-189">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1face-190">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="1face-190">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1face-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1face-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="1face-p109">首先請用[這個連結](https://manage.crazydomains.com/members/domains/)移至 Crazy Domains 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1face-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="1face-195">在 [**我的帳戶**] 區段中，選取 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="1face-195">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="1face-197">在 [**網功能變數名稱稱**] 頁面上的 [**網域**] 區段中，選取您要更新的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="1face-197">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="1face-199">在 [ **DNS 設定**] 區段中，選取下拉式清單圖示。</span><span class="sxs-lookup"><span data-stu-id="1face-199">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="1face-201">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="1face-201">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="1face-203">從 [**新增記錄：** ] 下拉式清單中，選擇 [ **CNAME 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="1face-203">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="1face-205">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1face-205">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="1face-207">新增六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="1face-207">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="1face-208">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="1face-208">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="1face-209">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="1face-209">**Sub Domain**</span></span>|<span data-ttu-id="1face-210">**Alias for (別名)**</span><span class="sxs-lookup"><span data-stu-id="1face-210">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1face-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1face-211">autodiscover</span></span>  <br/> |<span data-ttu-id="1face-212">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1face-212">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="1face-213">sip</span><span class="sxs-lookup"><span data-stu-id="1face-213">sip</span></span>  <br/> |<span data-ttu-id="1face-214">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1face-214">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1face-215">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1face-215">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1face-216">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1face-216">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1face-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1face-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1face-218">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1face-218">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="1face-219">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1face-219">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1face-220">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1face-220">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Configure-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="1face-222">選取 [**新增 CNAME 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="1face-222">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="1face-224">新增第二筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="1face-224">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="1face-225">在新記錄的方塊中，使用表格中下一列的值，然後再選取 [**新增 CNAME 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="1face-225">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="1face-226">重複這個程序，直到六筆 CNAME 記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="1face-226">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="1face-227">選取 [**更新**] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="1face-227">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Configure-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1face-229">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="1face-229">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1face-230"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1face-230"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1face-231">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="1face-231">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1face-232">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="1face-232">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1face-233">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="1face-233">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1face-234">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="1face-234">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="1face-p111">首先請用[這個連結](https://manage.crazydomains.com/members/domains/)移至 Crazy Domains 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1face-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="1face-238">在 [**我的帳戶**] 區段中，選取 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="1face-238">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="1face-240">在 [**網功能變數名稱稱**] 頁面上的 [**網域**] 區段中，選取您要更新的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="1face-240">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="1face-242">在 [ **DNS 設定**] 區段中，選取下拉式清單圖示。</span><span class="sxs-lookup"><span data-stu-id="1face-242">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="1face-244">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="1face-244">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="1face-246">從 [**新增記錄：** ] 下拉式清單中選擇 [ **TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="1face-246">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="1face-248">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1face-248">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="1face-250">在新記錄的方塊中，輸入或貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="1face-250">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="1face-251">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="1face-251">**Sub Domain**</span></span>|<span data-ttu-id="1face-252">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="1face-252">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1face-253">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="1face-253">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1face-254">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1face-254">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1face-255">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="1face-255">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-Configure-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="1face-257">選取 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="1face-257">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1face-259">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="1face-259">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1face-260"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1face-260"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="1face-p112">首先請用[這個連結](https://manage.crazydomains.com/members/domains/)移至 Crazy Domains 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1face-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="1face-264">在 [**我的帳戶**] 區段中，選取 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="1face-264">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="1face-266">在 [**網功能變數名稱稱**] 頁面上的 [**網域**] 區段中，選取您要更新的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="1face-266">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="1face-268">在 [ **DNS 設定**] 區段中，選取下拉式清單圖示。</span><span class="sxs-lookup"><span data-stu-id="1face-268">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="1face-270">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="1face-270">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="1face-272">從 [**新增記錄：** ] 下拉式清單中選擇 [ **SRV 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="1face-272">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="1face-274">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1face-274">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="1face-276">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="1face-276">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="1face-277">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="1face-277">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="1face-278">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="1face-278">**Record Type**</span></span>|<span data-ttu-id="1face-279">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="1face-279">**Sub Domain**</span></span>|<span data-ttu-id="1face-280">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="1face-280">**Priority**</span></span>|<span data-ttu-id="1face-281">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="1face-281">**Weight**</span></span>|<span data-ttu-id="1face-282">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="1face-282">**Port**</span></span>|<span data-ttu-id="1face-283">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="1face-283">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1face-284">SRV Record (SRV 記錄)</span><span class="sxs-lookup"><span data-stu-id="1face-284">SRV Record</span></span>  <br/> |<span data-ttu-id="1face-285">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="1face-285">_sip._tls</span></span>  <br/> |<span data-ttu-id="1face-286">100</span><span class="sxs-lookup"><span data-stu-id="1face-286">100</span></span>  <br/> |<span data-ttu-id="1face-287">1 </span><span class="sxs-lookup"><span data-stu-id="1face-287">1</span></span>  <br/> |<span data-ttu-id="1face-288">443</span><span class="sxs-lookup"><span data-stu-id="1face-288">443</span></span>  <br/> |<span data-ttu-id="1face-289">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1face-289">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1face-290">SRV Record (SRV 記錄)</span><span class="sxs-lookup"><span data-stu-id="1face-290">SRV Record</span></span>  <br/> |<span data-ttu-id="1face-291">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="1face-291">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="1face-292">100</span><span class="sxs-lookup"><span data-stu-id="1face-292">100</span></span>  <br/> |<span data-ttu-id="1face-293">1 </span><span class="sxs-lookup"><span data-stu-id="1face-293">1</span></span>  <br/> |<span data-ttu-id="1face-294">5061</span><span class="sxs-lookup"><span data-stu-id="1face-294">5061</span></span>  <br/> |<span data-ttu-id="1face-295">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1face-295">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Configure-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="1face-297">選取 [**新增 SRV 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="1face-297">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="1face-299">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1face-299">Add the other SRV record.</span></span>
    
    <span data-ttu-id="1face-300">在新記錄的方塊中，使用下表第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="1face-300">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="1face-301">選取 [**更新**] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="1face-301">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="1face-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1face-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
