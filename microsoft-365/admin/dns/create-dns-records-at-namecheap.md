---
title: 在 Namecheap 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Namecheap。
ms.openlocfilehash: 3de8c4fb7809423848564590193e00537362c034
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910147"
---
# <a name="create-dns-records-at-namecheap-for-microsoft"></a><span data-ttu-id="586ea-103">在 Namecheap 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="586ea-103">Create DNS records at Namecheap for Microsoft</span></span>

 <span data-ttu-id="586ea-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="586ea-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="586ea-105">如果 Namecheap 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="586ea-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="586ea-106">在 Namecheap 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="586ea-106">After you add these records at Namecheap, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="586ea-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="586ea-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="586ea-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="586ea-110">Add a TXT record for verification</span></span>
<span data-ttu-id="586ea-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="586ea-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="586ea-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="586ea-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="586ea-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="586ea-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="586ea-116">請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="586ea-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="586ea-117">若要開始使用，請移至您的網域頁面 Namecheap，方法是使用 [此連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)。</span><span class="sxs-lookup"><span data-stu-id="586ea-117">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="586ea-118">系統會提示您登入並繼續。</span><span class="sxs-lookup"><span data-stu-id="586ea-118">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="586ea-120">在 [ **登陸** ] 頁面的 [ **帳戶**] 下，從下拉式清單中選擇 [ **網域清單** ]。</span><span class="sxs-lookup"><span data-stu-id="586ea-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="586ea-122">在 [ **網域清單** ] 頁面上，尋找您要編輯的網功能變數名稱稱，然後選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="586ea-124">選取 [ **ADVANCED DNS**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="586ea-126">在 [ **主機記錄** ] 區段中，選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="586ea-128">在 [ **類型** ] 下拉式清單中，選取 [ **TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="586ea-129">當您選取 [**新增記錄**] 時，會自動顯示 [**類型**] 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="586ea-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="586ea-131">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="586ea-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="586ea-132"> (從下拉式清單中選取 [ **TTL** ] 值。 ) </span><span class="sxs-lookup"><span data-stu-id="586ea-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="586ea-133">**類型**</span><span class="sxs-lookup"><span data-stu-id="586ea-133">**Type**</span></span>|<span data-ttu-id="586ea-134">**主機**</span><span class="sxs-lookup"><span data-stu-id="586ea-134">**Host**</span></span>|<span data-ttu-id="586ea-135">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="586ea-135">**Value**</span></span>|<span data-ttu-id="586ea-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="586ea-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="586ea-137">TXT</span><span class="sxs-lookup"><span data-stu-id="586ea-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="586ea-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="586ea-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="586ea-139">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="586ea-139">**Note:** This is an example.</span></span> <span data-ttu-id="586ea-140">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="586ea-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="586ea-141">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="586ea-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="586ea-142">30分鐘</span><span class="sxs-lookup"><span data-stu-id="586ea-142">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="586ea-144">選取 [ **儲存變更** ] (核取記號) 控制項。</span><span class="sxs-lookup"><span data-stu-id="586ea-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="586ea-146">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="586ea-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="586ea-147">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="586ea-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="586ea-148">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="586ea-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="586ea-149">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="586ea-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="586ea-150">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="586ea-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="586ea-151">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="586ea-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="586ea-152">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="586ea-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="586ea-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="586ea-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="586ea-156">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="586ea-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="586ea-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="586ea-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="586ea-158">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="586ea-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="586ea-159">若要開始使用，請移至您的網域頁面 Namecheap，方法是使用 [此連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)。</span><span class="sxs-lookup"><span data-stu-id="586ea-159">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="586ea-160">系統會提示您登入並繼續。</span><span class="sxs-lookup"><span data-stu-id="586ea-160">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="586ea-162">在 [ **登陸** ] 頁面的 [ **帳戶**] 下，從下拉式清單中選擇 [ **網域清單** ]。</span><span class="sxs-lookup"><span data-stu-id="586ea-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="586ea-164">在 [ **網域清單** ] 頁面上，尋找您要編輯的網功能變數名稱稱，然後選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="586ea-166">選取 [ **ADVANCED DNS**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="586ea-168">在 [**郵件設定**] 區段中，從 [**電子郵件轉發**] 下拉式清單中選取 [**自訂 MX** ]。</span><span class="sxs-lookup"><span data-stu-id="586ea-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="586ea-169">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="586ea-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-Configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="586ea-171">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-BP-Configure-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="586ea-173">在新記錄的方塊中，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="586ea-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="586ea-174"> ([ **優先順序** ] 方塊是 [ **值** ] 方塊右側的未命名方塊。</span><span class="sxs-lookup"><span data-stu-id="586ea-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="586ea-175">從下拉式清單中選擇 [ **TTL** ] 值。 ) </span><span class="sxs-lookup"><span data-stu-id="586ea-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="586ea-176">**類型**</span><span class="sxs-lookup"><span data-stu-id="586ea-176">**Type**</span></span>|<span data-ttu-id="586ea-177">**主機**</span><span class="sxs-lookup"><span data-stu-id="586ea-177">**Host**</span></span>|<span data-ttu-id="586ea-178">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="586ea-178">**Value**</span></span>|<span data-ttu-id="586ea-179">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="586ea-179">**Priority**</span></span>|<span data-ttu-id="586ea-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="586ea-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="586ea-181">MX 記錄</span><span class="sxs-lookup"><span data-stu-id="586ea-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="586ea-182">\<*domain-key*\>mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="586ea-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="586ea-183">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="586ea-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="586ea-184">\**附注：\*\*\*\<domain-key\>* 從您的 Microsoft 帳戶取得。</span><span class="sxs-lookup"><span data-stu-id="586ea-184">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="586ea-185">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="586ea-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="586ea-186">0</span><span class="sxs-lookup"><span data-stu-id="586ea-186">0</span></span>  <br/> <span data-ttu-id="586ea-187">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="586ea-187">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="586ea-188">30分鐘</span><span class="sxs-lookup"><span data-stu-id="586ea-188">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="586ea-190">選取 [ **儲存變更** ] (核取記號) 控制項。</span><span class="sxs-lookup"><span data-stu-id="586ea-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="586ea-192">如果有任何其他 MX 記錄，請使用下列兩個步驟的處理程序來逐一移除：</span><span class="sxs-lookup"><span data-stu-id="586ea-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="586ea-193">首先，選取 [ **刪除] 圖示** (垃圾桶) 您要移除的記錄。</span><span class="sxs-lookup"><span data-stu-id="586ea-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-Configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="586ea-195">其次，選取 **[是]** 以確認刪除。</span><span class="sxs-lookup"><span data-stu-id="586ea-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-Configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="586ea-197">移除所有的 MX 記錄，除了您先前在此程式中新增的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="586ea-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="586ea-198">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="586ea-198">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="586ea-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="586ea-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="586ea-200">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="586ea-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="586ea-201">若要開始使用，請移至您的網域頁面 Namecheap，方法是使用 [此連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)。</span><span class="sxs-lookup"><span data-stu-id="586ea-201">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="586ea-202">系統會提示您登入並繼續。</span><span class="sxs-lookup"><span data-stu-id="586ea-202">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="586ea-204">在 [ **登陸** ] 頁面的 [ **帳戶**] 下，從下拉式清單中選擇 [ **網域清單** ]。</span><span class="sxs-lookup"><span data-stu-id="586ea-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="586ea-206">在 [ **網域清單** ] 頁面上，尋找您要編輯的網功能變數名稱稱，然後選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="586ea-208">選取 [ **ADVANCED DNS**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="586ea-210">在 [ **主機記錄** ] 區段中，選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="586ea-212">在 [ **類型** ] 下拉式清單中，選取 [ **CNAME 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="586ea-213">當您選取 [**新增記錄**] 時，會自動顯示 [**類型**] 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="586ea-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="586ea-215">在新記錄的空白方塊中，針對 **記錄類型** 選取 [ **CNAME** ]，然後輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="586ea-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="586ea-216">**類型**</span><span class="sxs-lookup"><span data-stu-id="586ea-216">**Type**</span></span>|<span data-ttu-id="586ea-217">**主機**</span><span class="sxs-lookup"><span data-stu-id="586ea-217">**Host**</span></span>|<span data-ttu-id="586ea-218">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="586ea-218">**Value**</span></span>|<span data-ttu-id="586ea-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="586ea-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="586ea-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="586ea-220">CNAME</span></span>  <br/> |<span data-ttu-id="586ea-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="586ea-221">autodiscover</span></span>  <br/> |<span data-ttu-id="586ea-222">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="586ea-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="586ea-223">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="586ea-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="586ea-224">3600</span><span class="sxs-lookup"><span data-stu-id="586ea-224">3600</span></span>  <br/> |
    |<span data-ttu-id="586ea-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="586ea-225">CNAME</span></span>  <br/> |<span data-ttu-id="586ea-226">sip</span><span class="sxs-lookup"><span data-stu-id="586ea-226">sip</span></span>  <br/> |<span data-ttu-id="586ea-227">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="586ea-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="586ea-228">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="586ea-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="586ea-229">3600</span><span class="sxs-lookup"><span data-stu-id="586ea-229">3600</span></span>  <br/> |
    |<span data-ttu-id="586ea-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="586ea-230">CNAME</span></span>  <br/> |<span data-ttu-id="586ea-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="586ea-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="586ea-232">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="586ea-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="586ea-233">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="586ea-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="586ea-234">3600</span><span class="sxs-lookup"><span data-stu-id="586ea-234">3600</span></span>  <br/> |
    |<span data-ttu-id="586ea-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="586ea-235">CNAME</span></span>  <br/> |<span data-ttu-id="586ea-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="586ea-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="586ea-237">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="586ea-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="586ea-238">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="586ea-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="586ea-239">3600</span><span class="sxs-lookup"><span data-stu-id="586ea-239">3600</span></span>  <br/> |
    |<span data-ttu-id="586ea-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="586ea-240">CNAME</span></span>  <br/> |<span data-ttu-id="586ea-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="586ea-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="586ea-242">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="586ea-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="586ea-243">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="586ea-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="586ea-244">3600</span><span class="sxs-lookup"><span data-stu-id="586ea-244">3600</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="586ea-246">選取 [ **儲存變更** ] (核取記號) 控制項。</span><span class="sxs-lookup"><span data-stu-id="586ea-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="586ea-248">使用上述四個步驟和表格中其他五列的值，新增其餘五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="586ea-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="586ea-249">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="586ea-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="586ea-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="586ea-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="586ea-251">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="586ea-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="586ea-252">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="586ea-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="586ea-253">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="586ea-253">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="586ea-254">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="586ea-254">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="586ea-255">請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="586ea-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="586ea-256">若要開始使用，請移至您的網域頁面 Namecheap，方法是使用 [此連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)。</span><span class="sxs-lookup"><span data-stu-id="586ea-256">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="586ea-257">系統會提示您登入並繼續。</span><span class="sxs-lookup"><span data-stu-id="586ea-257">You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="586ea-258">在 [ **登陸** ] 頁面的 [ **帳戶**] 下，從下拉式清單中選擇 [ **網域清單** ]。</span><span class="sxs-lookup"><span data-stu-id="586ea-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="586ea-260">在 [ **網域清單** ] 頁面上，尋找您要編輯的網功能變數名稱稱，然後選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="586ea-262">選取 [ **ADVANCED DNS**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="586ea-264">在 [ **主機記錄** ] 區段中，選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="586ea-266">在 [ **類型** ] 下拉式清單中，選取 [ **TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="586ea-267">當您選取 [**新增記錄**] 時，會自動顯示 [**類型**] 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="586ea-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="586ea-269">在新記錄的方塊中，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="586ea-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="586ea-270"> (從下拉式清單中選取 [ **TTL** ] 值。 ) </span><span class="sxs-lookup"><span data-stu-id="586ea-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="586ea-271">**類型**</span><span class="sxs-lookup"><span data-stu-id="586ea-271">**Type**</span></span>|<span data-ttu-id="586ea-272">**主機**</span><span class="sxs-lookup"><span data-stu-id="586ea-272">**Host**</span></span>|<span data-ttu-id="586ea-273">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="586ea-273">**Value**</span></span>|<span data-ttu-id="586ea-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="586ea-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="586ea-275">TXT</span><span class="sxs-lookup"><span data-stu-id="586ea-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="586ea-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="586ea-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="586ea-277">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="586ea-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="586ea-278">30分鐘</span><span class="sxs-lookup"><span data-stu-id="586ea-278">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="586ea-280">選取 [ **儲存變更** ] (核取記號) 控制項。</span><span class="sxs-lookup"><span data-stu-id="586ea-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="586ea-282">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="586ea-282">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="586ea-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="586ea-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="586ea-284">若要開始使用，請移至您的網域頁面 Namecheap，方法是使用 [此連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)。</span><span class="sxs-lookup"><span data-stu-id="586ea-284">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="586ea-285">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="586ea-285">You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="586ea-287">在 [ **登陸** ] 頁面的 [ **帳戶**] 下，從下拉式清單中選擇 [ **網域清單** ]。</span><span class="sxs-lookup"><span data-stu-id="586ea-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="586ea-289">在 [ **網域清單** ] 頁面上，尋找您要編輯的網功能變數名稱稱，然後選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="586ea-291">選取 [ **ADVANCED DNS**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="586ea-293">在 [ **主機記錄** ] 區段中，選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="586ea-295">在 [ **類型** ] 下拉式清單中，選取 [ **SRV 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="586ea-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="586ea-296">當您選取 [**新增記錄**] 時，會自動顯示 [**類型**] 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="586ea-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="586ea-298">在新記錄的空白方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="586ea-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="586ea-299">**服務**</span><span class="sxs-lookup"><span data-stu-id="586ea-299">**Service**</span></span>|<span data-ttu-id="586ea-300">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="586ea-300">**Protocol**</span></span>|<span data-ttu-id="586ea-301">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="586ea-301">**Priority**</span></span>|<span data-ttu-id="586ea-302">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="586ea-302">**Weight**</span></span>|<span data-ttu-id="586ea-303">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="586ea-303">**Port**</span></span>|<span data-ttu-id="586ea-304">**Target**</span><span class="sxs-lookup"><span data-stu-id="586ea-304">**Target**</span></span>|<span data-ttu-id="586ea-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="586ea-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="586ea-306">_sip</span><span class="sxs-lookup"><span data-stu-id="586ea-306">_sip</span></span>  <br/> |<span data-ttu-id="586ea-307">_tls</span><span class="sxs-lookup"><span data-stu-id="586ea-307">_tls</span></span>  <br/> |<span data-ttu-id="586ea-308">100</span><span class="sxs-lookup"><span data-stu-id="586ea-308">100</span></span>  <br/> |<span data-ttu-id="586ea-309">1</span><span class="sxs-lookup"><span data-stu-id="586ea-309">1</span></span>  <br/> |<span data-ttu-id="586ea-310">443</span><span class="sxs-lookup"><span data-stu-id="586ea-310">443</span></span>  <br/> |<span data-ttu-id="586ea-311">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="586ea-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="586ea-312">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="586ea-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="586ea-313">30分鐘</span><span class="sxs-lookup"><span data-stu-id="586ea-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="586ea-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="586ea-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="586ea-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="586ea-315">_tcp</span></span>  <br/> |<span data-ttu-id="586ea-316">100</span><span class="sxs-lookup"><span data-stu-id="586ea-316">100</span></span>  <br/> |<span data-ttu-id="586ea-317">1</span><span class="sxs-lookup"><span data-stu-id="586ea-317">1</span></span>  <br/> |<span data-ttu-id="586ea-318">5061</span><span class="sxs-lookup"><span data-stu-id="586ea-318">5061</span></span>  <br/> |<span data-ttu-id="586ea-319">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="586ea-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="586ea-320">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="586ea-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="586ea-321">30分鐘</span><span class="sxs-lookup"><span data-stu-id="586ea-321">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="586ea-323">選取 [ **儲存變更** ] (核取記號) 控制項。</span><span class="sxs-lookup"><span data-stu-id="586ea-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="586ea-325">使用上述四個步驟和表格中第二列的值，新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="586ea-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="586ea-p114">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="586ea-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

