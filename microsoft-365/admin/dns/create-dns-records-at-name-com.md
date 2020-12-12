---
title: 在 name.com 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft name.com。
ms.openlocfilehash: 2330755412abfe262ac79c4acbfc12e33af76fe2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657824"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="4aa83-103">在 name.com 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="4aa83-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="4aa83-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="4aa83-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4aa83-105">如果 name.com 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="4aa83-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="4aa83-106">在 name.com 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4aa83-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
> <span data-ttu-id="4aa83-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4aa83-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4aa83-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="4aa83-110">Add a TXT record for verification</span></span>
<span data-ttu-id="4aa83-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4aa83-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4aa83-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="4aa83-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4aa83-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="4aa83-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4aa83-p104">首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="4aa83-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4aa83-119">在 [ **我的網域**] 底下，選取您要修改的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="4aa83-119">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4aa83-121">在 [ **詳細資料** ] 欄中，選取 [ **DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="4aa83-121">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4aa83-123">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="4aa83-123">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="4aa83-124">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="4aa83-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4aa83-125">**類型**</span><span class="sxs-lookup"><span data-stu-id="4aa83-125">**Type**</span></span> <br/> |<span data-ttu-id="4aa83-126">**主機**</span><span class="sxs-lookup"><span data-stu-id="4aa83-126">**Host**</span></span> <br/> |<span data-ttu-id="4aa83-127">**答案**</span><span class="sxs-lookup"><span data-stu-id="4aa83-127">**Answer**</span></span> <br/> |<span data-ttu-id="4aa83-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4aa83-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="4aa83-129">TXT</span><span class="sxs-lookup"><span data-stu-id="4aa83-129">TXT</span></span>  <br/> |<span data-ttu-id="4aa83-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="4aa83-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4aa83-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4aa83-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4aa83-132">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="4aa83-132">**Note:** This is an example.</span></span> <span data-ttu-id="4aa83-133">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="4aa83-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="4aa83-134">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="4aa83-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="4aa83-135">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="4aa83-135">Use the default value (300).</span></span>  <br/> |
   
    ![Name-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="4aa83-137">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="4aa83-137">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="4aa83-139">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="4aa83-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4aa83-140">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="4aa83-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="4aa83-141">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="4aa83-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4aa83-142">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4aa83-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="4aa83-143">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="4aa83-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4aa83-144">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="4aa83-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="4aa83-145">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="4aa83-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="4aa83-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4aa83-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="4aa83-149">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="4aa83-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="4aa83-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4aa83-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="4aa83-p107">首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="4aa83-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4aa83-154">在 [ **我的網域**] 底下，選取您要修改的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="4aa83-154">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4aa83-156">在 [ **詳細資料** ] 欄中，選取 [ **DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="4aa83-156">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4aa83-158">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="4aa83-158">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="4aa83-159">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="4aa83-159">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4aa83-160">**類型**</span><span class="sxs-lookup"><span data-stu-id="4aa83-160">**Type**</span></span>|<span data-ttu-id="4aa83-161">**主機**</span><span class="sxs-lookup"><span data-stu-id="4aa83-161">**Host**</span></span>|<span data-ttu-id="4aa83-162">**答案**</span><span class="sxs-lookup"><span data-stu-id="4aa83-162">**Answer**</span></span>|<span data-ttu-id="4aa83-163">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4aa83-163">**TTL**</span></span>|<span data-ttu-id="4aa83-164">**Prio (優先順序)**</span><span class="sxs-lookup"><span data-stu-id="4aa83-164">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4aa83-165">MX</span><span class="sxs-lookup"><span data-stu-id="4aa83-165">MX</span></span>  <br/> |<span data-ttu-id="4aa83-166">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="4aa83-166">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="4aa83-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4aa83-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="4aa83-168">\**附注：\*\*\*\<domain-key\>* 從您的 Microsoft 帳戶取得。</span><span class="sxs-lookup"><span data-stu-id="4aa83-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="4aa83-169">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="4aa83-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="4aa83-170">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="4aa83-170">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="4aa83-171">0</span><span class="sxs-lookup"><span data-stu-id="4aa83-171">0</span></span>  <br/> <span data-ttu-id="4aa83-172">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="4aa83-172">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Name-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="4aa83-174">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="4aa83-174">Select **Add Record**.</span></span>
    
    ![名稱-BP-設定-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="4aa83-176">如果有任何其他 MX 記錄，請透過下列雙步驟程序刪除每個記錄︰</span><span class="sxs-lookup"><span data-stu-id="4aa83-176">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="4aa83-177">針對其他每個 MX 記錄，請選取 [**動作**] 欄中的 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="4aa83-177">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![名稱-BP-設定-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="4aa83-179">若要確認每個刪除，請再次選取 [**動作**] 欄中的 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="4aa83-179">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![名稱-BP-設定-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="4aa83-181">重複此進行雙步驟程序，直到您刪除其他 MX 記錄為止。</span><span class="sxs-lookup"><span data-stu-id="4aa83-181">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="4aa83-182">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="4aa83-182">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="4aa83-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4aa83-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="4aa83-p109">首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="4aa83-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4aa83-187">在 [ **我的網域**] 底下，選取您要修改的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="4aa83-187">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4aa83-189">在 [ **詳細資料** ] 欄中，選取 [ **DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="4aa83-189">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4aa83-191">新增第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="4aa83-191">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="4aa83-192">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="4aa83-192">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="4aa83-193">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="4aa83-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4aa83-194">**類型**</span><span class="sxs-lookup"><span data-stu-id="4aa83-194">**Type**</span></span>|<span data-ttu-id="4aa83-195">**主機**</span><span class="sxs-lookup"><span data-stu-id="4aa83-195">**Host**</span></span>|<span data-ttu-id="4aa83-196">**答案**</span><span class="sxs-lookup"><span data-stu-id="4aa83-196">**Answer**</span></span>|<span data-ttu-id="4aa83-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4aa83-197">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4aa83-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="4aa83-198">CNAME</span></span>  <br/> |<span data-ttu-id="4aa83-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4aa83-199">autodiscover</span></span>  <br/> |<span data-ttu-id="4aa83-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4aa83-200">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="4aa83-201">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="4aa83-201">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="4aa83-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="4aa83-202">CNAME</span></span>  <br/> |<span data-ttu-id="4aa83-203">sip</span><span class="sxs-lookup"><span data-stu-id="4aa83-203">sip</span></span>  <br/> |<span data-ttu-id="4aa83-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4aa83-204">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="4aa83-205">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="4aa83-205">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="4aa83-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="4aa83-206">CNAME</span></span>  <br/> |<span data-ttu-id="4aa83-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4aa83-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4aa83-208">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4aa83-208">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="4aa83-209">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="4aa83-209">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="4aa83-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="4aa83-210">CNAME</span></span>  <br/> |<span data-ttu-id="4aa83-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4aa83-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4aa83-212">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4aa83-212">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="4aa83-213">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="4aa83-213">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="4aa83-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="4aa83-214">CNAME</span></span>  <br/> |<span data-ttu-id="4aa83-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4aa83-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4aa83-216">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4aa83-216">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="4aa83-217">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="4aa83-217">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="4aa83-219">選取 [ **Add record** ] （新增）以新增第一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="4aa83-219">Select **Add Record** to add the first record.</span></span> 
    
    ![名稱-BP-設定-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="4aa83-221">新增第二筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="4aa83-221">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="4aa83-222">使用上表中第二列的值，然後選取 [ **新增記錄** ] 以新增第二筆記錄。</span><span class="sxs-lookup"><span data-stu-id="4aa83-222">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="4aa83-223">以此類推，使用表格中第三、四、五、六列的值新增其他記錄。</span><span class="sxs-lookup"><span data-stu-id="4aa83-223">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4aa83-224">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="4aa83-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4aa83-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4aa83-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4aa83-226">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="4aa83-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4aa83-227">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="4aa83-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4aa83-228">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="4aa83-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="4aa83-229">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="4aa83-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="4aa83-p111">首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="4aa83-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4aa83-233">在 [ **我的網域**] 底下，選取您要修改的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="4aa83-233">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4aa83-235">在 [ **詳細資料** ] 欄中，選取 [ **DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="4aa83-235">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4aa83-237">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="4aa83-237">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="4aa83-238">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="4aa83-238">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4aa83-239">**類型**</span><span class="sxs-lookup"><span data-stu-id="4aa83-239">**Type**</span></span>|<span data-ttu-id="4aa83-240">**主機**</span><span class="sxs-lookup"><span data-stu-id="4aa83-240">**Host**</span></span>|<span data-ttu-id="4aa83-241">**答案**</span><span class="sxs-lookup"><span data-stu-id="4aa83-241">**Answer**</span></span>|<span data-ttu-id="4aa83-242">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4aa83-242">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4aa83-243">TXT</span><span class="sxs-lookup"><span data-stu-id="4aa83-243">TXT</span></span>  <br/> |<span data-ttu-id="4aa83-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="4aa83-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4aa83-245">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4aa83-245">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4aa83-246">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="4aa83-246">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="4aa83-247">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="4aa83-247">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="4aa83-249">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="4aa83-249">Select **Add Record**.</span></span>
    
    ![名稱-BP-設定-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="4aa83-251">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="4aa83-251">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="4aa83-252"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4aa83-252"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="4aa83-p112">首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="4aa83-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4aa83-256">在 [ **我的網域**] 底下，選取您要修改的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="4aa83-256">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4aa83-258">在 [ **詳細資料** ] 欄中，選取 [ **DNS 記錄 +**]。</span><span class="sxs-lookup"><span data-stu-id="4aa83-258">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4aa83-260">新增第一筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="4aa83-260">Add the first SRV record:</span></span>
    
    <span data-ttu-id="4aa83-261">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="4aa83-261">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="4aa83-262">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="4aa83-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4aa83-263">**Type**</span><span class="sxs-lookup"><span data-stu-id="4aa83-263">**Type**</span></span>|<span data-ttu-id="4aa83-264">**服務**</span><span class="sxs-lookup"><span data-stu-id="4aa83-264">**Service**</span></span>|<span data-ttu-id="4aa83-265">**Weight**</span><span class="sxs-lookup"><span data-stu-id="4aa83-265">**Weight**</span></span>|<span data-ttu-id="4aa83-266">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4aa83-266">**TTL**</span></span>|<span data-ttu-id="4aa83-267">**Prio (優先順序)**</span><span class="sxs-lookup"><span data-stu-id="4aa83-267">**Prio**</span></span>|<span data-ttu-id="4aa83-268">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="4aa83-268">**Protocol**</span></span>|<span data-ttu-id="4aa83-269">**Port**</span><span class="sxs-lookup"><span data-stu-id="4aa83-269">**Port**</span></span>|<span data-ttu-id="4aa83-270">**Target**</span><span class="sxs-lookup"><span data-stu-id="4aa83-270">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4aa83-271">SRV</span><span class="sxs-lookup"><span data-stu-id="4aa83-271">SRV</span></span>|<span data-ttu-id="4aa83-272">sip</span><span class="sxs-lookup"><span data-stu-id="4aa83-272">sip</span></span>|<span data-ttu-id="4aa83-273">1 </span><span class="sxs-lookup"><span data-stu-id="4aa83-273">1</span></span>|<span data-ttu-id="4aa83-274">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="4aa83-274">Use the default value (300).</span></span>|<span data-ttu-id="4aa83-275">100</span><span class="sxs-lookup"><span data-stu-id="4aa83-275">100</span></span>|<span data-ttu-id="4aa83-276">tls</span><span class="sxs-lookup"><span data-stu-id="4aa83-276">tls</span></span>|<span data-ttu-id="4aa83-277">443</span><span class="sxs-lookup"><span data-stu-id="4aa83-277">443</span></span>|<span data-ttu-id="4aa83-278">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4aa83-278">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="4aa83-279">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="4aa83-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="4aa83-280">SRV</span><span class="sxs-lookup"><span data-stu-id="4aa83-280">SRV</span></span>|<span data-ttu-id="4aa83-281">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="4aa83-281">sipfederationtls</span></span>|<span data-ttu-id="4aa83-282">1 </span><span class="sxs-lookup"><span data-stu-id="4aa83-282">1</span></span>|<span data-ttu-id="4aa83-283">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="4aa83-283">Use the default value (300).</span></span>|<span data-ttu-id="4aa83-284">100</span><span class="sxs-lookup"><span data-stu-id="4aa83-284">100</span></span>|<span data-ttu-id="4aa83-285">tcp</span><span class="sxs-lookup"><span data-stu-id="4aa83-285">tcp</span></span>|<span data-ttu-id="4aa83-286">5061</span><span class="sxs-lookup"><span data-stu-id="4aa83-286">5061</span></span>|<span data-ttu-id="4aa83-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4aa83-287">sipfed.online.lync.com</span></span> <br><span data-ttu-id="4aa83-288">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="4aa83-288">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="4aa83-290">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="4aa83-290">Select **Add Record**.</span></span>

    ![名稱-BP-設定-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="4aa83-292">新增第二筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="4aa83-292">Add the second SRV record:</span></span>

<span data-ttu-id="4aa83-293">使用上表中的下一列的值，然後選取 [ **新增記錄** ] 以新增第二筆記錄。</span><span class="sxs-lookup"><span data-stu-id="4aa83-293">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="4aa83-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4aa83-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
