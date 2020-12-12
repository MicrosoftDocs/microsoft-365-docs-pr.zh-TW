---
title: 使用網路解決方案變更名稱伺服器以設定 Microsoft
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: '若要讓 Microsoft 管理您的 DNS 記錄，請瞭解如何設定含網路方案的 Microsoft 自訂網域。 '
ms.openlocfilehash: 04817ca24b13b4c138986df3875b6d397100fffd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658425"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a><span data-ttu-id="ab36d-103">使用網路解決方案變更名稱伺服器以設定 Microsoft</span><span class="sxs-lookup"><span data-stu-id="ab36d-103">Change nameservers to set up Microsoft with Network Solutions</span></span>

 <span data-ttu-id="ab36d-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="ab36d-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="ab36d-105">如果您想讓 Microsoft 為您管理您的 DNS 記錄，請遵循下列指示。</span><span class="sxs-lookup"><span data-stu-id="ab36d-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="ab36d-106"> (如果您願意，您可以 [在 [網路解決方案] 中管理所有的 MICROSOFT DNS 記錄](create-dns-records-at-network-solutions.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="ab36d-106">(If you prefer, you can [manage all your Microsoft DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="ab36d-107">在 Network Solutions 新增 TXT 記錄以驗證您擁有該網域</span><span class="sxs-lookup"><span data-stu-id="ab36d-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="ab36d-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="ab36d-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ab36d-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="ab36d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="ab36d-112">請依照下列步驟操作或[觀看影片 (從 0:47 處開始)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261)。</span><span class="sxs-lookup"><span data-stu-id="ab36d-112">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
1. <span data-ttu-id="ab36d-p104">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="ab36d-p104">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ab36d-115">在您選取 [**登** 入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="ab36d-117">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ab36d-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="ab36d-119">選取 [ **編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-119">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="ab36d-121">選取 [ **管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="ab36d-122">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="ab36d-122">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="ab36d-124">向下 **(TXT 記錄)** ] 區段中向下滾動至文字，然後選取 [ **編輯 TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![選取 [編輯 TXT 記錄]](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="ab36d-126">In the boxes for the new record, type or copy and paste the values in the following table.</span><span class="sxs-lookup"><span data-stu-id="ab36d-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="ab36d-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="ab36d-127">**Host**</span></span>|<span data-ttu-id="ab36d-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ab36d-128">**TTL**</span></span>|<span data-ttu-id="ab36d-129">**Text**</span><span class="sxs-lookup"><span data-stu-id="ab36d-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="ab36d-130">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="ab36d-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="ab36d-131">3600</span><span class="sxs-lookup"><span data-stu-id="ab36d-131">3600</span></span>  <br/> |<span data-ttu-id="ab36d-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ab36d-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ab36d-133">**請注意**：這是一個範例。</span><span class="sxs-lookup"><span data-stu-id="ab36d-133">**Note**: This is an example.</span></span> <span data-ttu-id="ab36d-134">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Microsoft 365 表格。</span><span class="sxs-lookup"><span data-stu-id="ab36d-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="ab36d-135">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="ab36d-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![在新記錄的方塊中輸入或貼上值](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="ab36d-137">選取 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-137">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="ab36d-139">選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-139">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="ab36d-141">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="ab36d-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ab36d-142">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 365 並要求 Microsoft 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="ab36d-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="ab36d-143">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="ab36d-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ab36d-144">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ab36d-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="ab36d-145">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="ab36d-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ab36d-146">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="ab36d-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ab36d-147">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="ab36d-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ab36d-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="ab36d-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="ab36d-151">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="ab36d-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="ab36d-152">若要使用 Microsoft 設定您的網域，請在您的網域註冊機構變更網域的 NS 記錄，以指向 Microsoft 主要和次要名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="ab36d-152">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="ab36d-153">這會將 Microsoft 設定為您為您更新網域的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="ab36d-153">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="ab36d-154">我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="ab36d-154">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ab36d-155">當您將網域的 NS 記錄變更為指向 Microsoft 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。</span><span class="sxs-lookup"><span data-stu-id="ab36d-155">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="ab36d-156">例如，所有傳送至您網域的電子郵件 (例如 rob@ *your_domain*  .com) 會在您進行此變更之後，從 Microsoft 開始。</span><span class="sxs-lookup"><span data-stu-id="ab36d-156">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
<span data-ttu-id="ab36d-157">準備好變更您的 NS 記錄，讓 Microsoft 能夠設定您的網域？</span><span class="sxs-lookup"><span data-stu-id="ab36d-157">Ready to change your NS records so Microsoft can set up your domain?</span></span> <span data-ttu-id="ab36d-158">請依照下列步驟操作或[觀看影片 (從 2:23 處開始)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261)。</span><span class="sxs-lookup"><span data-stu-id="ab36d-158">Follow the steps below or [watch the video (start at 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="ab36d-159">當您完成本節中的步驟之後，應該會列出的  *唯一*  名稱伺服器為下列四種： **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com** 和 **ns4.bdm.microsoftonline.com**。</span><span class="sxs-lookup"><span data-stu-id="ab36d-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="ab36d-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="ab36d-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="ab36d-161">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="ab36d-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="ab36d-162">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="ab36d-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ab36d-163">在您選取 [**登** 入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="ab36d-165">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ab36d-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="ab36d-167">選取 [ **編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-167">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="ab36d-169">選取 [ **移動 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-169">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="ab36d-171">請根據現在顯示頁面上是否列出名稱伺服器，來選擇下列兩個程序其中一項繼續︰</span><span class="sxs-lookup"><span data-stu-id="ab36d-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="ab36d-172">如果沒有列出 **任何** 名稱伺服器， [則未列出任何名稱伺服器](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="ab36d-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="ab36d-173">如果已 **列出名稱伺服器，** 如果已 [列出名稱伺服器](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="ab36d-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="ab36d-174">如果列表上「沒有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="ab36d-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="ab36d-175">在 [ **網域** ] 頁面上，選取 [ **指定功能變數名稱伺服器** ] 區段中的 [ **新增更多名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="ab36d-177">在 [ **功能變數名稱** ] 頁面上，輸入或複製並貼上下表中名稱伺服器的值。</span><span class="sxs-lookup"><span data-stu-id="ab36d-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="ab36d-178">**Name server 1 (名稱伺服器 1)**</span><span class="sxs-lookup"><span data-stu-id="ab36d-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="ab36d-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ab36d-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ab36d-180">**Name Server 2 (名稱伺服器 2)**</span><span class="sxs-lookup"><span data-stu-id="ab36d-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="ab36d-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ab36d-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ab36d-182">**Name Server 2 (名稱伺服器 2)**</span><span class="sxs-lookup"><span data-stu-id="ab36d-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="ab36d-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ab36d-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ab36d-184">**Name Server 2 (名稱伺服器 2)**</span><span class="sxs-lookup"><span data-stu-id="ab36d-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="ab36d-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ab36d-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-重新委派-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="ab36d-187">選取 [ **移動 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-187">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="ab36d-189">選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-189">Select **Save Changes**.</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="ab36d-191">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。</span><span class="sxs-lookup"><span data-stu-id="ab36d-191">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="ab36d-192">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ab36d-192">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="ab36d-193">如果列表上「有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="ab36d-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="ab36d-194">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span><span class="sxs-lookup"><span data-stu-id="ab36d-194">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span></span> <span data-ttu-id="ab36d-195"> (也就是說，  *只*  刪除所有  *未*  命名為 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com** 的目前名稱伺服器。 ) </span><span class="sxs-lookup"><span data-stu-id="ab36d-195">(That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="ab36d-196">如果有列出任何其他名稱伺服器，請選取它，然後按鍵盤上的 **delete** 鍵，逐一刪除。</span><span class="sxs-lookup"><span data-stu-id="ab36d-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![NetworkSolutions-BP-重新委派-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="ab36d-198">選取 [ **新增更多名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-198">Select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="ab36d-200">在 [ **功能變數名稱** ] 頁面上，輸入或複製並貼上下表中名稱伺服器的值。</span><span class="sxs-lookup"><span data-stu-id="ab36d-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="ab36d-201">**Name server 1 (名稱伺服器 1)**</span><span class="sxs-lookup"><span data-stu-id="ab36d-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="ab36d-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ab36d-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ab36d-203">**Name Server 2 (名稱伺服器 2)**</span><span class="sxs-lookup"><span data-stu-id="ab36d-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="ab36d-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ab36d-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ab36d-205">**Name Server 3 (名稱伺服器 3)**</span><span class="sxs-lookup"><span data-stu-id="ab36d-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="ab36d-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ab36d-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ab36d-207">**Name Server 4 (名稱伺服器 4)**</span><span class="sxs-lookup"><span data-stu-id="ab36d-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="ab36d-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ab36d-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-重新委派-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="ab36d-210">選取 [ **移動 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="ab36d-210">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="ab36d-212">選取 [ **儲存變更]。**</span><span class="sxs-lookup"><span data-stu-id="ab36d-212">Select **Save Changes.**</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="ab36d-214">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。</span><span class="sxs-lookup"><span data-stu-id="ab36d-214">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="ab36d-215">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ab36d-215">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
