---
title: 在 Names.co.uk 建立 Microsoft 的 DNS 記錄
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Names.co.uk。
ms.openlocfilehash: 2df1a18f00fd7cd48b0d24860ddcf651c2fdac4e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048936"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="01099-103">在 Names.co.uk 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="01099-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="01099-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="01099-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="01099-105">如果 Names.co.uk 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="01099-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="01099-106">在 Names.co.uk 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="01099-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="01099-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="01099-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="01099-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="01099-110">Add a TXT record for verification</span></span>
<span data-ttu-id="01099-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="01099-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="01099-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="01099-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="01099-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="01099-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="01099-p104">首先請用[這個連結](https://account.names.co.uk/dashboard#/)移至 Names.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="01099-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="01099-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="01099-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="01099-120">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="01099-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="01099-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="01099-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="01099-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="01099-124">（如果您需要新增一列，請選取 **[新增 A/CNAME 記錄] （+）**。）</span><span class="sxs-lookup"><span data-stu-id="01099-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="01099-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="01099-126">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="01099-126">**Host name**</span></span>|<span data-ttu-id="01099-127">**類型**</span><span class="sxs-lookup"><span data-stu-id="01099-127">**Type**</span></span>|<span data-ttu-id="01099-128">**結果**</span><span class="sxs-lookup"><span data-stu-id="01099-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="01099-129">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="01099-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="01099-130">TXT</span><span class="sxs-lookup"><span data-stu-id="01099-130">TXT</span></span>  <br/> |<span data-ttu-id="01099-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="01099-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="01099-132">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="01099-132">**Note:** This is an example.</span></span> <span data-ttu-id="01099-133">在這裡請使用您自己來自表格的 [目的地或指向位址]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="01099-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="01099-134">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="01099-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="01099-136">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="01099-136">Select **Save**.</span></span>
    
    <span data-ttu-id="01099-137">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="01099-139">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="01099-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="01099-140">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="01099-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="01099-141">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="01099-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="01099-142">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="01099-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="01099-143">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="01099-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="01099-144">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="01099-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="01099-145">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="01099-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="01099-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="01099-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="01099-149">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="01099-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="01099-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="01099-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="01099-p107">首先請用[這個連結](https://account.names.co.uk/dashboard#/)移至 Names.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="01099-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="01099-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="01099-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="01099-155">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="01099-157">在 [ **ADD/MODIFY DNS 區域**] 頁面的 [**郵件交換記錄**] 區段中，于新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="01099-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="01099-158">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="01099-159">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="01099-159">**Host name**</span></span>|<span data-ttu-id="01099-160">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="01099-160">**Priority**</span></span>|<span data-ttu-id="01099-161">**結果**</span><span class="sxs-lookup"><span data-stu-id="01099-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="01099-162">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="01099-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="01099-163">1</span><span class="sxs-lookup"><span data-stu-id="01099-163">1</span></span>  <br/> <span data-ttu-id="01099-164">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="01099-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="01099-165">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="01099-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="01099-166">> [!NOTE]> 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="01099-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="01099-167">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="01099-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="01099-169">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="01099-169">Select **Save**.</span></span>
    
    <span data-ttu-id="01099-170">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="01099-172">如果 [**郵件交換記錄**] 區段中列出任何其他 MX 記錄，請選取它，然後按鍵盤上的**delete**鍵，逐一刪除。</span><span class="sxs-lookup"><span data-stu-id="01099-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="01099-174">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="01099-174">Select **Save**.</span></span>
    
    <span data-ttu-id="01099-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="01099-177">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="01099-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="01099-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="01099-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="01099-p109">首先請用[這個連結](https://account.names.co.uk/dashboard#/)移至 Names.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="01099-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="01099-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="01099-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="01099-183">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="01099-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="01099-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="01099-186">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="01099-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="01099-187">（如果您需要新增一列，請選取 **[新增 A/CNAME 記錄] （+）**。）</span><span class="sxs-lookup"><span data-stu-id="01099-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="01099-188">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="01099-189">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="01099-189">**Host Name**</span></span>|<span data-ttu-id="01099-190">**類型**</span><span class="sxs-lookup"><span data-stu-id="01099-190">**Type**</span></span>|<span data-ttu-id="01099-191">**結果**</span><span class="sxs-lookup"><span data-stu-id="01099-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="01099-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="01099-192">autodiscover</span></span>  <br/> |<span data-ttu-id="01099-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="01099-193">CNAME</span></span>  <br/> |<span data-ttu-id="01099-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="01099-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="01099-195">sip</span><span class="sxs-lookup"><span data-stu-id="01099-195">sip</span></span>  <br/> |<span data-ttu-id="01099-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="01099-196">CNAME</span></span>  <br/> |<span data-ttu-id="01099-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01099-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="01099-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="01099-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="01099-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="01099-199">CNAME</span></span>  <br/> |<span data-ttu-id="01099-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01099-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="01099-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="01099-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="01099-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="01099-202">CNAME</span></span>  <br/> |<span data-ttu-id="01099-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="01099-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="01099-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="01099-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="01099-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="01099-205">CNAME</span></span>  <br/> |<span data-ttu-id="01099-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="01099-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="01099-208">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="01099-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-Configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="01099-210">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="01099-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="01099-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="01099-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="01099-212">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="01099-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="01099-213">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="01099-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="01099-214">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="01099-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="01099-215">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="01099-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="01099-p111">首先請用[這個連結](https://account.names.co.uk/dashboard#/)移至 Names.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="01099-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="01099-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="01099-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="01099-220">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="01099-222">在 [**帳戶的 DNS 區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要更新的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="01099-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="01099-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="01099-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="01099-225">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="01099-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="01099-226">（如果您需要新增一列，請選取 **[新增 A/CNAME 記錄] （+）**。）</span><span class="sxs-lookup"><span data-stu-id="01099-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="01099-227">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="01099-228">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="01099-228">**Host name**</span></span>|<span data-ttu-id="01099-229">**類型**</span><span class="sxs-lookup"><span data-stu-id="01099-229">**Type**</span></span>|<span data-ttu-id="01099-230">**結果**</span><span class="sxs-lookup"><span data-stu-id="01099-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="01099-231">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="01099-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="01099-232">TXT</span><span class="sxs-lookup"><span data-stu-id="01099-232">TXT</span></span>  <br/> |<span data-ttu-id="01099-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="01099-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="01099-234">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="01099-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="01099-236">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="01099-236">Select **Save**.</span></span>
    
    <span data-ttu-id="01099-237">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="01099-239">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="01099-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="01099-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="01099-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="01099-p112">首先請用[這個連結](https://account.names.co.uk/dashboard#/)移至 Names.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="01099-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="01099-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="01099-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="01099-245">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="01099-247">在 [ **ADD/MODIFY DNS 區域**] 頁面的 [**服務記錄**] 區段中，于新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="01099-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="01099-248">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01099-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="01099-249">**Name**</span><span class="sxs-lookup"><span data-stu-id="01099-249">**Name**</span></span>|<span data-ttu-id="01099-250">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="01099-250">**Priority**</span></span>|<span data-ttu-id="01099-251">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="01099-251">**Weight**</span></span>|<span data-ttu-id="01099-252">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="01099-252">**Port**</span></span>|<span data-ttu-id="01099-253">**結果**</span><span class="sxs-lookup"><span data-stu-id="01099-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="01099-254">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="01099-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="01099-255">100</span><span class="sxs-lookup"><span data-stu-id="01099-255">100</span></span>  <br/> |<span data-ttu-id="01099-256">1</span><span class="sxs-lookup"><span data-stu-id="01099-256">1</span></span>  <br/> |<span data-ttu-id="01099-257">443</span><span class="sxs-lookup"><span data-stu-id="01099-257">443</span></span>  <br/> |<span data-ttu-id="01099-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01099-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="01099-259">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="01099-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="01099-260">100</span><span class="sxs-lookup"><span data-stu-id="01099-260">100</span></span>  <br/> |<span data-ttu-id="01099-261">1</span><span class="sxs-lookup"><span data-stu-id="01099-261">1</span></span>  <br/> |<span data-ttu-id="01099-262">5061</span><span class="sxs-lookup"><span data-stu-id="01099-262">5061</span></span>  <br/> |<span data-ttu-id="01099-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01099-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="01099-265">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="01099-265">Select **Save**.</span></span>
    
    <span data-ttu-id="01099-266">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="01099-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="01099-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="01099-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
