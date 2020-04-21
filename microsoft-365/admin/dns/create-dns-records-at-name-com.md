---
title: 在 name.com 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft name.com。
ms.openlocfilehash: 8b23ab4d324b5e6d023f10f8f1d11d95d3c579ba
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629344"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="047e7-103">在 name.com 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="047e7-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="047e7-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="047e7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="047e7-105">如果 name.com 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="047e7-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="047e7-106">在 name.com 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="047e7-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="047e7-107">若要深入瞭解 Microsoft 的網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="047e7-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="047e7-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="047e7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="047e7-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="047e7-111">Add a TXT record for verification</span></span>
<span data-ttu-id="047e7-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="047e7-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="047e7-113">在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="047e7-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="047e7-114">您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。</span><span class="sxs-lookup"><span data-stu-id="047e7-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="047e7-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="047e7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="047e7-p104">首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="047e7-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="047e7-120">在 [**我的網域**] 底下，選取您要修改的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="047e7-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="047e7-122">在 [**詳細資料**] 欄中，選取 [\* DNS 記錄] \* \*。</span><span class="sxs-lookup"><span data-stu-id="047e7-122">In the **Details** column, select \*\* DNS Records \*\*.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="047e7-124">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="047e7-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="047e7-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="047e7-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="047e7-126">**類型**</span><span class="sxs-lookup"><span data-stu-id="047e7-126">**Type**</span></span> <br/> |<span data-ttu-id="047e7-127">**主機**</span><span class="sxs-lookup"><span data-stu-id="047e7-127">**Host**</span></span> <br/> |<span data-ttu-id="047e7-128">**答案**</span><span class="sxs-lookup"><span data-stu-id="047e7-128">**Answer**</span></span> <br/> |<span data-ttu-id="047e7-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="047e7-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="047e7-130">TXT</span><span class="sxs-lookup"><span data-stu-id="047e7-130">TXT</span></span>  <br/> |<span data-ttu-id="047e7-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="047e7-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="047e7-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="047e7-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="047e7-133">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="047e7-133">**Note:** This is an example.</span></span> <span data-ttu-id="047e7-134">從表格中，使用您的特定**目的地或指向位址**值。</span><span class="sxs-lookup"><span data-stu-id="047e7-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="047e7-135">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="047e7-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="047e7-136">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="047e7-136">Use the default value (300).</span></span>  <br/> |
   
    ![Name-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="047e7-138">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="047e7-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="047e7-140">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="047e7-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="047e7-141">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求記錄。</span><span class="sxs-lookup"><span data-stu-id="047e7-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="047e7-142">當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="047e7-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="047e7-143">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="047e7-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="047e7-144">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="047e7-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="047e7-145">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="047e7-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="047e7-146">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="047e7-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="047e7-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="047e7-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="047e7-150">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="047e7-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="047e7-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="047e7-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="047e7-p107">首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="047e7-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="047e7-155">在 [**我的網域**] 底下，選取您要修改的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="047e7-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="047e7-157">在 [**詳細資料**] 欄中，選取 [ **DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="047e7-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="047e7-159">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="047e7-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="047e7-160">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="047e7-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="047e7-161">**類型**</span><span class="sxs-lookup"><span data-stu-id="047e7-161">**Type**</span></span>|<span data-ttu-id="047e7-162">**主機**</span><span class="sxs-lookup"><span data-stu-id="047e7-162">**Host**</span></span>|<span data-ttu-id="047e7-163">**答案**</span><span class="sxs-lookup"><span data-stu-id="047e7-163">**Answer**</span></span>|<span data-ttu-id="047e7-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="047e7-164">**TTL**</span></span>|<span data-ttu-id="047e7-165">**Prio (優先順序)**</span><span class="sxs-lookup"><span data-stu-id="047e7-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="047e7-166">MX</span><span class="sxs-lookup"><span data-stu-id="047e7-166">MX</span></span>  <br/> |<span data-ttu-id="047e7-167">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="047e7-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="047e7-168">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="047e7-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="047e7-169">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="047e7-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="047e7-170">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="047e7-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="047e7-171">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="047e7-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="047e7-172">0</span><span class="sxs-lookup"><span data-stu-id="047e7-172">0</span></span>  <br/> <span data-ttu-id="047e7-173">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="047e7-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Name-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="047e7-175">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="047e7-175">Select **Add Record**.</span></span>
    
    ![名稱-BP-設定-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="047e7-177">如果有任何其他 MX 記錄，請透過下列雙步驟程序刪除每個記錄︰</span><span class="sxs-lookup"><span data-stu-id="047e7-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="047e7-178">針對其他每個 MX 記錄，請選取 [**動作**] 欄中的 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="047e7-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![名稱-BP-設定-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="047e7-180">若要確認每個刪除，請再次選取 [**動作**] 欄中的 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="047e7-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![名稱-BP-設定-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="047e7-182">重複此進行雙步驟程序，直到您刪除其他 MX 記錄為止。</span><span class="sxs-lookup"><span data-stu-id="047e7-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="047e7-183">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="047e7-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="047e7-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="047e7-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="047e7-p109">首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="047e7-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="047e7-188">在 [**我的網域**] 底下，選取您要修改的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="047e7-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="047e7-190">在 [**詳細資料**] 欄中，選取 [ **DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="047e7-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="047e7-192">新增第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="047e7-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="047e7-193">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="047e7-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="047e7-194">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="047e7-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="047e7-195">**類型**</span><span class="sxs-lookup"><span data-stu-id="047e7-195">**Type**</span></span>|<span data-ttu-id="047e7-196">**主機**</span><span class="sxs-lookup"><span data-stu-id="047e7-196">**Host**</span></span>|<span data-ttu-id="047e7-197">**答案**</span><span class="sxs-lookup"><span data-stu-id="047e7-197">**Answer**</span></span>|<span data-ttu-id="047e7-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="047e7-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="047e7-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="047e7-199">CNAME</span></span>  <br/> |<span data-ttu-id="047e7-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="047e7-200">autodiscover</span></span>  <br/> |<span data-ttu-id="047e7-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="047e7-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="047e7-202">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="047e7-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="047e7-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="047e7-203">CNAME</span></span>  <br/> |<span data-ttu-id="047e7-204">sip</span><span class="sxs-lookup"><span data-stu-id="047e7-204">sip</span></span>  <br/> |<span data-ttu-id="047e7-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="047e7-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="047e7-206">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="047e7-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="047e7-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="047e7-207">CNAME</span></span>  <br/> |<span data-ttu-id="047e7-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="047e7-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="047e7-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="047e7-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="047e7-210">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="047e7-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="047e7-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="047e7-211">CNAME</span></span>  <br/> |<span data-ttu-id="047e7-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="047e7-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="047e7-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="047e7-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="047e7-214">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="047e7-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="047e7-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="047e7-215">CNAME</span></span>  <br/> |<span data-ttu-id="047e7-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="047e7-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="047e7-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="047e7-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="047e7-218">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="047e7-218">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="047e7-220">選取 [ **Add record** ] （新增）以新增第一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="047e7-220">Select **Add Record** to add the first record.</span></span> 
    
    ![名稱-BP-設定-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="047e7-222">新增第二筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="047e7-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="047e7-223">使用上表中第二列的值，然後選取 [**新增記錄**] 以新增第二筆記錄。</span><span class="sxs-lookup"><span data-stu-id="047e7-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="047e7-224">以此類推，使用表格中第三、四、五、六列的值新增其他記錄。</span><span class="sxs-lookup"><span data-stu-id="047e7-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="047e7-225">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="047e7-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="047e7-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="047e7-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="047e7-227">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="047e7-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="047e7-228">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="047e7-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="047e7-229">如果您已有網域的 SPF 記錄，請不要為 Microsoft 建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="047e7-229">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="047e7-230">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="047e7-230">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="047e7-p111">首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="047e7-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="047e7-234">在 [**我的網域**] 底下，選取您要修改的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="047e7-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="047e7-236">在 [**詳細資料**] 欄中，選取 [ **DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="047e7-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="047e7-238">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="047e7-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="047e7-239">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="047e7-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="047e7-240">**類型**</span><span class="sxs-lookup"><span data-stu-id="047e7-240">**Type**</span></span>|<span data-ttu-id="047e7-241">**主機**</span><span class="sxs-lookup"><span data-stu-id="047e7-241">**Host**</span></span>|<span data-ttu-id="047e7-242">**答案**</span><span class="sxs-lookup"><span data-stu-id="047e7-242">**Answer**</span></span>|<span data-ttu-id="047e7-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="047e7-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="047e7-244">TXT</span><span class="sxs-lookup"><span data-stu-id="047e7-244">TXT</span></span>  <br/> |<span data-ttu-id="047e7-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="047e7-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="047e7-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="047e7-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="047e7-247">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="047e7-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="047e7-248">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="047e7-248">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="047e7-250">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="047e7-250">Select **Add Record**.</span></span>
    
    ![名稱-BP-設定-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="047e7-252">新增 Microsoft 所需的兩筆 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="047e7-252">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="047e7-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="047e7-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="047e7-p112">首先請用[這個連結](https://www.name.com/account/domain)移至 name.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="047e7-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="047e7-257">在 [**我的網域**] 底下，選取您要修改的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="047e7-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="047e7-259">在 [**詳細資料**] 欄中，選取 [ **DNS 記錄 +**]。</span><span class="sxs-lookup"><span data-stu-id="047e7-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="047e7-261">新增第一筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="047e7-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="047e7-262">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="047e7-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="047e7-263">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="047e7-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="047e7-264">**類型**</span><span class="sxs-lookup"><span data-stu-id="047e7-264">**Type**</span></span>|<span data-ttu-id="047e7-265">**Service** (服務)</span><span class="sxs-lookup"><span data-stu-id="047e7-265">**Service**</span></span>|<span data-ttu-id="047e7-266">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="047e7-266">**Weight**</span></span>|<span data-ttu-id="047e7-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="047e7-267">**TTL**</span></span>|<span data-ttu-id="047e7-268">**Prio (優先順序)**</span><span class="sxs-lookup"><span data-stu-id="047e7-268">**Prio**</span></span>|<span data-ttu-id="047e7-269">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="047e7-269">**Protocol**</span></span>|<span data-ttu-id="047e7-270">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="047e7-270">**Port**</span></span>|<span data-ttu-id="047e7-271">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="047e7-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="047e7-272">SRV</span><span class="sxs-lookup"><span data-stu-id="047e7-272">SRV</span></span>|<span data-ttu-id="047e7-273">sip</span><span class="sxs-lookup"><span data-stu-id="047e7-273">sip</span></span>|<span data-ttu-id="047e7-274">1 </span><span class="sxs-lookup"><span data-stu-id="047e7-274">1</span></span>|<span data-ttu-id="047e7-275">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="047e7-275">Use the default value (300).</span></span>|<span data-ttu-id="047e7-276">100</span><span class="sxs-lookup"><span data-stu-id="047e7-276">100</span></span>|<span data-ttu-id="047e7-277">tls</span><span class="sxs-lookup"><span data-stu-id="047e7-277">tls</span></span>|<span data-ttu-id="047e7-278">443</span><span class="sxs-lookup"><span data-stu-id="047e7-278">443</span></span>|<span data-ttu-id="047e7-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="047e7-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="047e7-280">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="047e7-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="047e7-281">SRV</span><span class="sxs-lookup"><span data-stu-id="047e7-281">SRV</span></span>|<span data-ttu-id="047e7-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="047e7-282">sipfederationtls</span></span>|<span data-ttu-id="047e7-283">1 </span><span class="sxs-lookup"><span data-stu-id="047e7-283">1</span></span>|<span data-ttu-id="047e7-284">使用預設值 (300)。</span><span class="sxs-lookup"><span data-stu-id="047e7-284">Use the default value (300).</span></span>|<span data-ttu-id="047e7-285">100</span><span class="sxs-lookup"><span data-stu-id="047e7-285">100</span></span>|<span data-ttu-id="047e7-286">tcp</span><span class="sxs-lookup"><span data-stu-id="047e7-286">tcp</span></span>|<span data-ttu-id="047e7-287">5061</span><span class="sxs-lookup"><span data-stu-id="047e7-287">5061</span></span>|<span data-ttu-id="047e7-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="047e7-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="047e7-289">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="047e7-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="047e7-291">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="047e7-291">Select **Add Record**.</span></span>

    ![名稱-BP-設定-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="047e7-293">新增第二筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="047e7-293">Add the second SRV record:</span></span>

<span data-ttu-id="047e7-294">使用上表中的下一列的值，然後選取 [**新增記錄**] 以新增第二筆記錄。</span><span class="sxs-lookup"><span data-stu-id="047e7-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="047e7-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="047e7-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
