---
title: 在 MyDomain 建立 Microsoft 的 DNS 記錄
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: 了解如何在 Microsoft 的 [我的網域] 中驗證網域，並為電子郵件、商務用 Skype Online和其他服務設定 DNS 記錄。
ms.openlocfilehash: 1e7f9c5705e535c1558273be5bfdc99841e0ea4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910159"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a><span data-ttu-id="48e72-103">在 MyDomain 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="48e72-103">Create DNS records at MyDomain for Microsoft</span></span>


  
 <span data-ttu-id="48e72-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="48e72-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="48e72-105">MyDomain 網站不支援 SRV 記錄，這表示有幾項商務用 Skype Online 和 Outlook Web App 功能將無法使用。</span><span class="sxs-lookup"><span data-stu-id="48e72-105">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="48e72-106">無論您使用哪一種 Microsoft 方案，只要在 MyDomain 管理 DNS 記錄，都會受到[重大的服務限制](../setup/domains-faq.yml) (部分機器翻譯)，建議您改換不同的 DNS 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="48e72-106">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](../setup/domains-faq.yml), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="48e72-107">儘管有這些服務限制，如果您仍選擇在 MyDomain 管理您的 Microsoft DNS 記錄，請按照本文中的步驟設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="48e72-107">If you choose to manage your own Microsoft DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="48e72-108">在 MyDomain 新增這些記錄之後，您的網域就會設定為搭配 Microsoft 服務使用。</span><span class="sxs-lookup"><span data-stu-id="48e72-108">After you add these records at MyDomain, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="48e72-109">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="48e72-109">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="48e72-110">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="48e72-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="48e72-111">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="48e72-111">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="48e72-112">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="48e72-112">Add a TXT record for verification</span></span>
<span data-ttu-id="48e72-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="48e72-113"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="48e72-p103">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="48e72-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48e72-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="48e72-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="48e72-p105">首先，請用[此連結](https://www.mydomain.com/controlpanel)移至您在 MyDomain 的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="48e72-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="48e72-120">在 **[我的最愛]** 區段中，選取 **[網域中央]**。</span><span class="sxs-lookup"><span data-stu-id="48e72-120">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="48e72-121">在 **[網域]** 下方，選取要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="48e72-121">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="48e72-122">在 **[總覽]** 區段，選取 **[DNS]**。</span><span class="sxs-lookup"><span data-stu-id="48e72-122">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="48e72-123">從 **[修改]** 下拉式清單中，選擇 **[TXT/SPF 記錄]**。</span><span class="sxs-lookup"><span data-stu-id="48e72-123">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="48e72-124">在 **[內容]** 底下，於新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="48e72-124">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="48e72-125">**內容**</span><span class="sxs-lookup"><span data-stu-id="48e72-125">**Content**</span></span> <br/> |
    |<span data-ttu-id="48e72-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="48e72-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="48e72-127">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="48e72-127">**Note:** This is an example.</span></span> <span data-ttu-id="48e72-128">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="48e72-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="48e72-129">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="48e72-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="48e72-130">選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="48e72-130">Select **Add**.</span></span>
    
8. <span data-ttu-id="48e72-131">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="48e72-131">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="48e72-132">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="48e72-132">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="48e72-133">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="48e72-133">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="48e72-134">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="48e72-134">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="48e72-135">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="48e72-135">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="48e72-136">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="48e72-136">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="48e72-137">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="48e72-137">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="48e72-138">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="48e72-138">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="48e72-139">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="48e72-139">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="48e72-140">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="48e72-140">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="48e72-141">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="48e72-141">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="48e72-142"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="48e72-142"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="48e72-p108">首先，請用[此連結](https://www.mydomain.com/controlpanel)移至您在 MyDomain 的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="48e72-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="48e72-145">在 **[我的最愛]** 區段中，選取 **[網域中央]**。</span><span class="sxs-lookup"><span data-stu-id="48e72-145">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="48e72-146">在 **[網域]** 下方，選取要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="48e72-146">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="48e72-147">在 **[總覽]** 區段，選取 **[DNS]**。</span><span class="sxs-lookup"><span data-stu-id="48e72-147">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="48e72-148">在 **[Modify] (修改)** 下拉式清單中，選擇 **[MX Record] (MX 記錄)**。</span><span class="sxs-lookup"><span data-stu-id="48e72-148">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="48e72-150">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="48e72-150">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="48e72-151">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="48e72-151">**Priority**</span></span>|<span data-ttu-id="48e72-152">**Host**</span><span class="sxs-lookup"><span data-stu-id="48e72-152">**Host**</span></span>|<span data-ttu-id="48e72-153">**Points to: (指向:)**</span><span class="sxs-lookup"><span data-stu-id="48e72-153">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="48e72-154">0</span><span class="sxs-lookup"><span data-stu-id="48e72-154">0</span></span>  <br/> <span data-ttu-id="48e72-155">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="48e72-155">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |@  <br/> | <span data-ttu-id="48e72-156">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="48e72-156">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="48e72-157">**注意：** 從您的 Microsoft 帳戶取得您的 \<*domain-key*\>。</span><span class="sxs-lookup"><span data-stu-id="48e72-157">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span><span data-ttu-id="48e72-158"> > [如何找到這項資訊？](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="48e72-158"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="48e72-160">選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="48e72-160">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="48e72-162">如果有任何其他現有的 MX 記錄，請針對每一筆記錄，選取 **[Actions] (動作)** 欄中的 **[Remove] (移除)**，將它刪除。</span><span class="sxs-lookup"><span data-stu-id="48e72-162">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="48e72-164">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="48e72-164">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="48e72-166">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="48e72-166">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="48e72-167"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="48e72-167"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="48e72-p110">首先，請用[此連結](https://www.mydomain.com/controlpanel)移至您在 MyDomain 的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="48e72-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="48e72-170">在 **[我的最愛]** 區段中，選取 **[網域中央]**。</span><span class="sxs-lookup"><span data-stu-id="48e72-170">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="48e72-171">在 **[網域]** 下方，選取要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="48e72-171">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="48e72-172">在 **[總覽]** 區段，選取 **[DNS]**。</span><span class="sxs-lookup"><span data-stu-id="48e72-172">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="48e72-173">在 **[Modify] (修改)** 下拉式清單中，選取 **[CNAME Alias] (CNAME 別名)**。</span><span class="sxs-lookup"><span data-stu-id="48e72-173">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="48e72-175">新增第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="48e72-175">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="48e72-176">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="48e72-176">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="48e72-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="48e72-177">**Host**</span></span>|<span data-ttu-id="48e72-178">**Points to: (指向:)**</span><span class="sxs-lookup"><span data-stu-id="48e72-178">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="48e72-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="48e72-179">autodiscover</span></span>  <br/> |<span data-ttu-id="48e72-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="48e72-180">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="48e72-181">sip</span><span class="sxs-lookup"><span data-stu-id="48e72-181">sip</span></span>  <br/> |<span data-ttu-id="48e72-182">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="48e72-182">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="48e72-183">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="48e72-183">lyncdiscover</span></span>  <br/> |<span data-ttu-id="48e72-184">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="48e72-184">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="48e72-185">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="48e72-185">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="48e72-186">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="48e72-186">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="48e72-187">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="48e72-187">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="48e72-188">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="48e72-188">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="48e72-190">選取 **[新增]** 以新增第一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="48e72-190">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="48e72-192">新增第二筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="48e72-192">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="48e72-193">使用上表中第二列的值，然後選取 **[新增]** 以新增第二筆記錄。</span><span class="sxs-lookup"><span data-stu-id="48e72-193">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="48e72-194">以此類推，使用表格中第三、四、五、六列的值新增其他記錄。</span><span class="sxs-lookup"><span data-stu-id="48e72-194">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="48e72-195">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="48e72-195">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="48e72-196"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="48e72-196"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="48e72-197">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="48e72-197">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="48e72-198">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="48e72-198">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="48e72-199">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="48e72-199">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="48e72-200">而是，請將必要的 Microsoft 值新增到目前的記錄，以便擁有包含這兩組值的單一 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="48e72-200">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="48e72-201">需要範例？</span><span class="sxs-lookup"><span data-stu-id="48e72-201">Need examples?</span></span> <span data-ttu-id="48e72-202">請參閱這些 [Microsoft 的外部網域名稱系統記錄](../../enterprise/external-domain-name-system-records.md#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="48e72-202">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md#bkmk_spfrecords).</span></span> <span data-ttu-id="48e72-203">若要驗證您的 SPF 記錄，您可以使用其中一種 [SPF 驗證工具](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="48e72-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="48e72-p112">首先，請用[此連結](https://www.mydomain.com/controlpanel)移至您在 MyDomain 的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="48e72-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="48e72-206">在 **[我的最愛]** 區段中，選取 **[網域中央]**。</span><span class="sxs-lookup"><span data-stu-id="48e72-206">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="48e72-207">在 **[網域]** 下方，選取要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="48e72-207">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="48e72-208">在 **[總覽]** 區段，選取 **[DNS]**。</span><span class="sxs-lookup"><span data-stu-id="48e72-208">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="48e72-209">從 **[修改]** 下拉式清單中，選擇 **[TXT/SPF 記錄]**。</span><span class="sxs-lookup"><span data-stu-id="48e72-209">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="48e72-211">在 **[內容]** 底下，於新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="48e72-211">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="48e72-212">**內容**</span><span class="sxs-lookup"><span data-stu-id="48e72-212">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="48e72-213">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="48e72-213">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="48e72-214">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="48e72-214">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="48e72-216">選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="48e72-216">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="48e72-218">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="48e72-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="48e72-219"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="48e72-219"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="48e72-220">MyDomain 網站不支援 SRV 記錄，這表示有幾項商務用 Skype Online 和 Outlook Web App 功能將無法使用。</span><span class="sxs-lookup"><span data-stu-id="48e72-220">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="48e72-221">無論您使用哪一種 Microsoft 方案，只要在 MyDomain 管理 DNS 記錄，都會受到[重大的服務限制](../setup/domains-faq.yml) (部分機器翻譯)，建議您改換不同的 DNS 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="48e72-221">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](../setup/domains-faq.yml), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="48e72-222">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="48e72-222">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="48e72-223">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="48e72-223">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="48e72-224">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="48e72-224">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
