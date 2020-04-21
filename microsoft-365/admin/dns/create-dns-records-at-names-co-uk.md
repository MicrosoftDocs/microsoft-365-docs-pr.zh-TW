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
ms.openlocfilehash: 2552017e06001c0b28605558b823fdb4c670ef8c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629320"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="57215-103">在 Names.co.uk 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="57215-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="57215-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="57215-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="57215-105">如果 Names.co.uk 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="57215-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="57215-106">在 Names.co.uk 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="57215-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="57215-107">若要深入瞭解 Microsoft 的網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="57215-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="57215-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="57215-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="57215-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="57215-111">Add a TXT record for verification</span></span>
<span data-ttu-id="57215-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="57215-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="57215-113">在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="57215-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="57215-114">您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。</span><span class="sxs-lookup"><span data-stu-id="57215-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="57215-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="57215-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="57215-p104">首先請用[這個連結](https://account.names.co.uk/dashboard#/)移至 Names.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="57215-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="57215-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="57215-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="57215-121">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-121">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="57215-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="57215-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="57215-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="57215-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="57215-125">（如果您需要新增一列，請選取 **[新增 A/CNAME 記錄] （+）**。）</span><span class="sxs-lookup"><span data-stu-id="57215-125">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="57215-126">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-126">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="57215-127">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="57215-127">**Host name**</span></span>|<span data-ttu-id="57215-128">**類型**</span><span class="sxs-lookup"><span data-stu-id="57215-128">**Type**</span></span>|<span data-ttu-id="57215-129">**結果**</span><span class="sxs-lookup"><span data-stu-id="57215-129">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="57215-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="57215-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="57215-131">TXT</span><span class="sxs-lookup"><span data-stu-id="57215-131">TXT</span></span>  <br/> |<span data-ttu-id="57215-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="57215-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="57215-133">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="57215-133">**Note:** This is an example.</span></span> <span data-ttu-id="57215-134">從表格中，使用您的特定**目的地或指向位址**值。</span><span class="sxs-lookup"><span data-stu-id="57215-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="57215-135">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="57215-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="57215-137">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="57215-137">Select **Save**.</span></span>
    
    <span data-ttu-id="57215-138">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-138">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="57215-140">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="57215-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="57215-141">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求記錄。</span><span class="sxs-lookup"><span data-stu-id="57215-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="57215-142">當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="57215-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="57215-143">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="57215-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="57215-144">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="57215-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="57215-145">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="57215-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="57215-146">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="57215-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="57215-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="57215-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="57215-150">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="57215-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="57215-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="57215-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="57215-p107">首先請用[這個連結](https://account.names.co.uk/dashboard#/)移至 Names.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="57215-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="57215-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="57215-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="57215-156">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-156">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="57215-158">在 [ **ADD/MODIFY DNS 區域**] 頁面的 [**郵件交換記錄**] 區段中，于新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="57215-158">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="57215-159">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-159">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="57215-160">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="57215-160">**Host name**</span></span>|<span data-ttu-id="57215-161">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="57215-161">**Priority**</span></span>|<span data-ttu-id="57215-162">**結果**</span><span class="sxs-lookup"><span data-stu-id="57215-162">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="57215-163">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="57215-163">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="57215-164">1 </span><span class="sxs-lookup"><span data-stu-id="57215-164">1</span></span>  <br/> <span data-ttu-id="57215-165">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="57215-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="57215-166">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="57215-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="57215-167">> [!NOTE]> 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="57215-167">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="57215-168">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="57215-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="57215-170">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="57215-170">Select **Save**.</span></span>
    
    <span data-ttu-id="57215-171">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-171">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="57215-173">如果 [**郵件交換記錄**] 區段中列出任何其他 MX 記錄，請選取它，然後按鍵盤上的**delete**鍵，逐一刪除。</span><span class="sxs-lookup"><span data-stu-id="57215-173">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="57215-175">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="57215-175">Select **Save**.</span></span>
    
    <span data-ttu-id="57215-176">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-176">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="57215-178">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="57215-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="57215-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="57215-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="57215-p109">首先請用[這個連結](https://account.names.co.uk/dashboard#/)移至 Names.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="57215-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="57215-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="57215-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="57215-184">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-184">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="57215-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="57215-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="57215-187">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="57215-187">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="57215-188">（如果您需要新增一列，請選取 **[新增 A/CNAME 記錄] （+）**。）</span><span class="sxs-lookup"><span data-stu-id="57215-188">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="57215-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-189">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="57215-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="57215-190">**Host Name**</span></span>|<span data-ttu-id="57215-191">**類型**</span><span class="sxs-lookup"><span data-stu-id="57215-191">**Type**</span></span>|<span data-ttu-id="57215-192">**結果**</span><span class="sxs-lookup"><span data-stu-id="57215-192">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="57215-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="57215-193">autodiscover</span></span>  <br/> |<span data-ttu-id="57215-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="57215-194">CNAME</span></span>  <br/> |<span data-ttu-id="57215-195">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="57215-195">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="57215-196">sip</span><span class="sxs-lookup"><span data-stu-id="57215-196">sip</span></span>  <br/> |<span data-ttu-id="57215-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="57215-197">CNAME</span></span>  <br/> |<span data-ttu-id="57215-198">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="57215-198">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="57215-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="57215-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="57215-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="57215-200">CNAME</span></span>  <br/> |<span data-ttu-id="57215-201">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="57215-201">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="57215-202">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="57215-202">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="57215-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="57215-203">CNAME</span></span>  <br/> |<span data-ttu-id="57215-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="57215-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="57215-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="57215-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="57215-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="57215-206">CNAME</span></span>  <br/> |<span data-ttu-id="57215-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="57215-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="57215-209">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="57215-209">Select **Save**.</span></span>
    
    ![NamesUK-BP-Configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="57215-211">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="57215-211">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="57215-212"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="57215-212"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="57215-213">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="57215-213">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="57215-214">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="57215-214">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="57215-215">如果您已有網域的 SPF 記錄，請不要為 Microsoft 建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="57215-215">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="57215-216">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="57215-216">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="57215-p111">首先請用[這個連結](https://account.names.co.uk/dashboard#/)移至 Names.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="57215-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="57215-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="57215-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="57215-221">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-221">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="57215-223">在 [**帳戶的 DNS 區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要更新的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="57215-223">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="57215-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="57215-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="57215-226">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="57215-226">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="57215-227">（如果您需要新增一列，請選取 **[新增 A/CNAME 記錄] （+）**。）</span><span class="sxs-lookup"><span data-stu-id="57215-227">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="57215-228">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-228">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="57215-229">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="57215-229">**Host name**</span></span>|<span data-ttu-id="57215-230">**類型**</span><span class="sxs-lookup"><span data-stu-id="57215-230">**Type**</span></span>|<span data-ttu-id="57215-231">**結果**</span><span class="sxs-lookup"><span data-stu-id="57215-231">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="57215-232">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="57215-232">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="57215-233">TXT</span><span class="sxs-lookup"><span data-stu-id="57215-233">TXT</span></span>  <br/> |<span data-ttu-id="57215-234">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="57215-234">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="57215-235">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="57215-235">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="57215-237">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="57215-237">Select **Save**.</span></span>
    
    <span data-ttu-id="57215-238">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="57215-238">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="57215-240">新增 Microsoft 所需的兩筆 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="57215-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="57215-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="57215-241"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="57215-p112">首先請用[這個連結](https://account.names.co.uk/dashboard#/)移至 Names.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="57215-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="57215-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="57215-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="57215-246">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-246">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="57215-248">在 [ **ADD/MODIFY DNS 區域**] 頁面的 [**服務記錄**] 區段中，于新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="57215-248">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="57215-249">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="57215-249">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="57215-250">**Name** (名稱)</span><span class="sxs-lookup"><span data-stu-id="57215-250">**Name**</span></span>|<span data-ttu-id="57215-251">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="57215-251">**Priority**</span></span>|<span data-ttu-id="57215-252">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="57215-252">**Weight**</span></span>|<span data-ttu-id="57215-253">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="57215-253">**Port**</span></span>|<span data-ttu-id="57215-254">**結果**</span><span class="sxs-lookup"><span data-stu-id="57215-254">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="57215-255">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="57215-255">_sip._tls</span></span>  <br/> |<span data-ttu-id="57215-256">100</span><span class="sxs-lookup"><span data-stu-id="57215-256">100</span></span>  <br/> |<span data-ttu-id="57215-257">1 </span><span class="sxs-lookup"><span data-stu-id="57215-257">1</span></span>  <br/> |<span data-ttu-id="57215-258">443</span><span class="sxs-lookup"><span data-stu-id="57215-258">443</span></span>  <br/> |<span data-ttu-id="57215-259">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="57215-259">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="57215-260">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="57215-260">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="57215-261">100</span><span class="sxs-lookup"><span data-stu-id="57215-261">100</span></span>  <br/> |<span data-ttu-id="57215-262">1 </span><span class="sxs-lookup"><span data-stu-id="57215-262">1</span></span>  <br/> |<span data-ttu-id="57215-263">5061</span><span class="sxs-lookup"><span data-stu-id="57215-263">5061</span></span>  <br/> |<span data-ttu-id="57215-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="57215-264">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="57215-266">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="57215-266">Select **Save**.</span></span>
    
    <span data-ttu-id="57215-267">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="57215-267">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="57215-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="57215-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
