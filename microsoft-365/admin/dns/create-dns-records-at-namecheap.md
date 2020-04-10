---
title: 在 Namecheap 建立 Office 365 的 DNS 記錄
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Office 365 Namecheap。
ms.openlocfilehash: 29b1130b75af592594e2a963dbb6fa8d3f08ab30
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211676"
---
# <a name="create-dns-records-at-namecheap-for-office-365"></a><span data-ttu-id="e1c38-103">在 Namecheap 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="e1c38-103">Create DNS records at Namecheap for Office 365</span></span>

 <span data-ttu-id="e1c38-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="e1c38-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e1c38-105">如果 Namecheap 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1c38-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e1c38-106">在 Namecheap 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="e1c38-106">After you add these records at Namecheap, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1c38-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="e1c38-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e1c38-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="e1c38-110">Add a TXT record for verification</span></span>
<span data-ttu-id="e1c38-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e1c38-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e1c38-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="e1c38-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1c38-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="e1c38-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="e1c38-116">請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="e1c38-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="e1c38-117">若要開始使用，請移至您的網域頁面 Namecheap，方法是使用[此連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)。</span><span class="sxs-lookup"><span data-stu-id="e1c38-117">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="e1c38-118">系統會提示您登入並繼續。</span><span class="sxs-lookup"><span data-stu-id="e1c38-118">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="e1c38-120">在 [**登陸**] 頁面的 [**帳戶**] 下，從下拉式清單中選擇 [**網域清單**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="e1c38-122">在 [**網域清單**] 頁面上，尋找您要編輯的網功能變數名稱稱，然後選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="e1c38-124">選取 [ **ADVANCED DNS**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="e1c38-126">在 [**主機記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="e1c38-128">在 [**類型**] 下拉式清單中，選取 [ **TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1c38-129">當您選取 [**新增記錄**] 時，會自動顯示 [**類型**] 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="e1c38-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="e1c38-131">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="e1c38-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="e1c38-132">（從下拉式清單中選擇 [ **TTL** ] 值。）</span><span class="sxs-lookup"><span data-stu-id="e1c38-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e1c38-133">**類型**</span><span class="sxs-lookup"><span data-stu-id="e1c38-133">**Type**</span></span>|<span data-ttu-id="e1c38-134">**主機**</span><span class="sxs-lookup"><span data-stu-id="e1c38-134">**Host**</span></span>|<span data-ttu-id="e1c38-135">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="e1c38-135">**Value**</span></span>|<span data-ttu-id="e1c38-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1c38-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1c38-137">TXT</span><span class="sxs-lookup"><span data-stu-id="e1c38-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="e1c38-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e1c38-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="e1c38-139">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="e1c38-139">**Note:** This is an example.</span></span> <span data-ttu-id="e1c38-140">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="e1c38-140">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="e1c38-141">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="e1c38-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e1c38-142">30分鐘</span><span class="sxs-lookup"><span data-stu-id="e1c38-142">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="e1c38-144">選取 [**儲存變更**] （核取記號）控制。</span><span class="sxs-lookup"><span data-stu-id="e1c38-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="e1c38-146">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="e1c38-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e1c38-147">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="e1c38-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="e1c38-148">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="e1c38-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e1c38-149">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="e1c38-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="e1c38-150">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="e1c38-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e1c38-151">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="e1c38-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e1c38-152">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="e1c38-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="e1c38-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="e1c38-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="e1c38-156">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="e1c38-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="e1c38-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e1c38-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="e1c38-158">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="e1c38-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="e1c38-159">若要開始使用，請移至您的網域頁面 Namecheap，方法是使用[此連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)。</span><span class="sxs-lookup"><span data-stu-id="e1c38-159">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="e1c38-160">系統會提示您登入並繼續。</span><span class="sxs-lookup"><span data-stu-id="e1c38-160">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="e1c38-162">在 [**登陸**] 頁面的 [**帳戶**] 下，從下拉式清單中選擇 [**網域清單**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="e1c38-164">在 [**網域清單**] 頁面上，尋找您要編輯的網功能變數名稱稱，然後選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="e1c38-166">選取 [ **ADVANCED DNS**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="e1c38-168">在 [**郵件設定**] 區段中，從 [**電子郵件轉發**] 下拉式清單中選取 [**自訂 MX** ]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="e1c38-169">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e1c38-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-Configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="e1c38-171">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-BP-Configure-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="e1c38-173">在新記錄的方塊中，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="e1c38-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="e1c38-174">（[**優先順序**] 方塊是 [**值**] 方塊右側的未命名方塊。</span><span class="sxs-lookup"><span data-stu-id="e1c38-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="e1c38-175">從下拉式清單中選擇 [ **TTL** ] 值。</span><span class="sxs-lookup"><span data-stu-id="e1c38-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e1c38-176">**類型**</span><span class="sxs-lookup"><span data-stu-id="e1c38-176">**Type**</span></span>|<span data-ttu-id="e1c38-177">**主機**</span><span class="sxs-lookup"><span data-stu-id="e1c38-177">**Host**</span></span>|<span data-ttu-id="e1c38-178">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="e1c38-178">**Value**</span></span>|<span data-ttu-id="e1c38-179">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="e1c38-179">**Priority**</span></span>|<span data-ttu-id="e1c38-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1c38-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1c38-181">MX 記錄</span><span class="sxs-lookup"><span data-stu-id="e1c38-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="e1c38-182">\<*網域金鑰*\>。 mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e1c38-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="e1c38-183">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e1c38-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="e1c38-184">**附注：** 從您的 Office 365 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="e1c38-184">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="e1c38-185">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="e1c38-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e1c38-186">0</span><span class="sxs-lookup"><span data-stu-id="e1c38-186">0</span></span>  <br/> <span data-ttu-id="e1c38-187">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="e1c38-187">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="e1c38-188">30分鐘</span><span class="sxs-lookup"><span data-stu-id="e1c38-188">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="e1c38-190">選取 [**儲存變更**] （核取記號）控制。</span><span class="sxs-lookup"><span data-stu-id="e1c38-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="e1c38-192">如果有任何其他 MX 記錄，請使用下列兩個步驟的處理程序來逐一移除：</span><span class="sxs-lookup"><span data-stu-id="e1c38-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="e1c38-193">首先，針對您想要移除的記錄選取**刪除圖示**（垃圾桶）。</span><span class="sxs-lookup"><span data-stu-id="e1c38-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-Configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="e1c38-195">其次，選取 **[是]** 以確認刪除。</span><span class="sxs-lookup"><span data-stu-id="e1c38-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-Configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="e1c38-197">移除所有的 MX 記錄，除了您先前在此程式中新增的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1c38-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="e1c38-198">新增 Office 365 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="e1c38-198">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="e1c38-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e1c38-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="e1c38-200">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="e1c38-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="e1c38-201">若要開始使用，請移至您的網域頁面 Namecheap，方法是使用[此連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)。</span><span class="sxs-lookup"><span data-stu-id="e1c38-201">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="e1c38-202">系統會提示您登入並繼續。</span><span class="sxs-lookup"><span data-stu-id="e1c38-202">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="e1c38-204">在 [**登陸**] 頁面的 [**帳戶**] 下，從下拉式清單中選擇 [**網域清單**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="e1c38-206">在 [**網域清單**] 頁面上，尋找您要編輯的網功能變數名稱稱，然後選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="e1c38-208">選取 [ **ADVANCED DNS**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="e1c38-210">在 [**主機記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="e1c38-212">在 [**類型**] 下拉式清單中，選取 [ **CNAME 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1c38-213">當您選取 [**新增記錄**] 時，會自動顯示 [**類型**] 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="e1c38-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="e1c38-215">在新記錄的空白方塊中，針對**記錄類型**選取 [ **CNAME** ]，然後輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="e1c38-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="e1c38-216">**類型**</span><span class="sxs-lookup"><span data-stu-id="e1c38-216">**Type**</span></span>|<span data-ttu-id="e1c38-217">**主機**</span><span class="sxs-lookup"><span data-stu-id="e1c38-217">**Host**</span></span>|<span data-ttu-id="e1c38-218">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="e1c38-218">**Value**</span></span>|<span data-ttu-id="e1c38-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1c38-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1c38-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1c38-220">CNAME</span></span>  <br/> |<span data-ttu-id="e1c38-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e1c38-221">autodiscover</span></span>  <br/> |<span data-ttu-id="e1c38-222">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="e1c38-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="e1c38-223">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e1c38-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e1c38-224">3600</span><span class="sxs-lookup"><span data-stu-id="e1c38-224">3600</span></span>  <br/> |
    |<span data-ttu-id="e1c38-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1c38-225">CNAME</span></span>  <br/> |<span data-ttu-id="e1c38-226">sip</span><span class="sxs-lookup"><span data-stu-id="e1c38-226">sip</span></span>  <br/> |<span data-ttu-id="e1c38-227">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="e1c38-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e1c38-228">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e1c38-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e1c38-229">3600</span><span class="sxs-lookup"><span data-stu-id="e1c38-229">3600</span></span>  <br/> |
    |<span data-ttu-id="e1c38-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1c38-230">CNAME</span></span>  <br/> |<span data-ttu-id="e1c38-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e1c38-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e1c38-232">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="e1c38-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e1c38-233">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e1c38-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e1c38-234">3600</span><span class="sxs-lookup"><span data-stu-id="e1c38-234">3600</span></span>  <br/> |
    |<span data-ttu-id="e1c38-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1c38-235">CNAME</span></span>  <br/> |<span data-ttu-id="e1c38-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e1c38-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e1c38-237">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="e1c38-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="e1c38-238">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e1c38-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e1c38-239">3600</span><span class="sxs-lookup"><span data-stu-id="e1c38-239">3600</span></span>  <br/> |
    |<span data-ttu-id="e1c38-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1c38-240">CNAME</span></span>  <br/> |<span data-ttu-id="e1c38-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e1c38-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e1c38-242">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="e1c38-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="e1c38-243">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e1c38-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e1c38-244">3600</span><span class="sxs-lookup"><span data-stu-id="e1c38-244">3600</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="e1c38-246">選取 [**儲存變更**] （核取記號）控制。</span><span class="sxs-lookup"><span data-stu-id="e1c38-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="e1c38-248">使用上述四個步驟和表格中其他五列的值，新增其餘五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1c38-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e1c38-249">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="e1c38-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e1c38-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e1c38-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1c38-251">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1c38-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e1c38-252">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="e1c38-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e1c38-253">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="e1c38-253">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="e1c38-254">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1c38-254">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="e1c38-255">請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="e1c38-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="e1c38-256">若要開始使用，請移至您的網域頁面 Namecheap，方法是使用[此連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)。</span><span class="sxs-lookup"><span data-stu-id="e1c38-256">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="e1c38-257">系統會提示您登入並繼續。</span><span class="sxs-lookup"><span data-stu-id="e1c38-257">You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="e1c38-258">在 [**登陸**] 頁面的 [**帳戶**] 下，從下拉式清單中選擇 [**網域清單**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="e1c38-260">在 [**網域清單**] 頁面上，尋找您要編輯的網功能變數名稱稱，然後選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="e1c38-262">選取 [ **ADVANCED DNS**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="e1c38-264">在 [**主機記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="e1c38-266">在 [**類型**] 下拉式清單中，選取 [ **TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1c38-267">當您選取 [**新增記錄**] 時，會自動顯示 [**類型**] 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="e1c38-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="e1c38-269">在新記錄的方塊中，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="e1c38-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="e1c38-270">（從下拉式清單中選擇 [ **TTL** ] 值。）</span><span class="sxs-lookup"><span data-stu-id="e1c38-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e1c38-271">**類型**</span><span class="sxs-lookup"><span data-stu-id="e1c38-271">**Type**</span></span>|<span data-ttu-id="e1c38-272">**主機**</span><span class="sxs-lookup"><span data-stu-id="e1c38-272">**Host**</span></span>|<span data-ttu-id="e1c38-273">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="e1c38-273">**Value**</span></span>|<span data-ttu-id="e1c38-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1c38-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1c38-275">TXT</span><span class="sxs-lookup"><span data-stu-id="e1c38-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="e1c38-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e1c38-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e1c38-277">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="e1c38-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="e1c38-278">30分鐘</span><span class="sxs-lookup"><span data-stu-id="e1c38-278">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="e1c38-280">選取 [**儲存變更**] （核取記號）控制。</span><span class="sxs-lookup"><span data-stu-id="e1c38-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="e1c38-282">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="e1c38-282">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="e1c38-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e1c38-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="e1c38-284">若要開始使用，請移至您的網域頁面 Namecheap，方法是使用[此連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)。</span><span class="sxs-lookup"><span data-stu-id="e1c38-284">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="e1c38-285">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="e1c38-285">You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="e1c38-287">在 [**登陸**] 頁面的 [**帳戶**] 下，從下拉式清單中選擇 [**網域清單**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="e1c38-289">在 [**網域清單**] 頁面上，尋找您要編輯的網功能變數名稱稱，然後選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="e1c38-291">選取 [ **ADVANCED DNS**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="e1c38-293">在 [**主機記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="e1c38-295">在 [**類型**] 下拉式清單中，選取 [ **SRV 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1c38-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1c38-296">當您選取 [**新增記錄**] 時，會自動顯示 [**類型**] 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="e1c38-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="e1c38-298">在新記錄的空白方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="e1c38-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="e1c38-299">**服務**</span><span class="sxs-lookup"><span data-stu-id="e1c38-299">**Service**</span></span>|<span data-ttu-id="e1c38-300">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="e1c38-300">**Protocol**</span></span>|<span data-ttu-id="e1c38-301">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="e1c38-301">**Priority**</span></span>|<span data-ttu-id="e1c38-302">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="e1c38-302">**Weight**</span></span>|<span data-ttu-id="e1c38-303">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="e1c38-303">**Port**</span></span>|<span data-ttu-id="e1c38-304">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="e1c38-304">**Target**</span></span>|<span data-ttu-id="e1c38-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1c38-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1c38-306">_sip</span><span class="sxs-lookup"><span data-stu-id="e1c38-306">_sip</span></span>  <br/> |<span data-ttu-id="e1c38-307">_tls</span><span class="sxs-lookup"><span data-stu-id="e1c38-307">_tls</span></span>  <br/> |<span data-ttu-id="e1c38-308">100</span><span class="sxs-lookup"><span data-stu-id="e1c38-308">100</span></span>  <br/> |<span data-ttu-id="e1c38-309">1 </span><span class="sxs-lookup"><span data-stu-id="e1c38-309">1</span></span>  <br/> |<span data-ttu-id="e1c38-310">443</span><span class="sxs-lookup"><span data-stu-id="e1c38-310">443</span></span>  <br/> |<span data-ttu-id="e1c38-311">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="e1c38-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e1c38-312">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e1c38-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e1c38-313">30分鐘</span><span class="sxs-lookup"><span data-stu-id="e1c38-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="e1c38-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e1c38-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="e1c38-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="e1c38-315">_tcp</span></span>  <br/> |<span data-ttu-id="e1c38-316">100</span><span class="sxs-lookup"><span data-stu-id="e1c38-316">100</span></span>  <br/> |<span data-ttu-id="e1c38-317">1 </span><span class="sxs-lookup"><span data-stu-id="e1c38-317">1</span></span>  <br/> |<span data-ttu-id="e1c38-318">5061</span><span class="sxs-lookup"><span data-stu-id="e1c38-318">5061</span></span>  <br/> |<span data-ttu-id="e1c38-319">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="e1c38-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="e1c38-320">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e1c38-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e1c38-321">30分鐘</span><span class="sxs-lookup"><span data-stu-id="e1c38-321">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="e1c38-323">選取 [**儲存變更**] （核取記號）控制。</span><span class="sxs-lookup"><span data-stu-id="e1c38-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="e1c38-325">使用上述四個步驟和表格中第二列的值，新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1c38-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e1c38-p114">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="e1c38-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
