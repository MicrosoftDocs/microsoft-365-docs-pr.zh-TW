---
title: 在123-reg.co.uk 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft 123-reg.co.uk。
ms.openlocfilehash: 3c9af6909f37082a63170adac94ac3d92b717ad1
ms.sourcegitcommit: bf9e0091e5bdc78d9b23be64583eb816bb059eb2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2021
ms.locfileid: "50758901"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="1ceb0-103">在123-reg.co.uk 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="1ceb0-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="1ceb0-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1ceb0-105">如果 123-reg.co.uk 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="1ceb0-106">在123-reg.co.uk 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="1ceb0-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1ceb0-108">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1ceb0-109">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1ceb0-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="1ceb0-110">Add a TXT record for verification</span></span>
<span data-ttu-id="1ceb0-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1ceb0-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1ceb0-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ceb0-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="1ceb0-p104">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1ceb0-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1ceb0-119">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="1ceb0-120">在 [ **管理您的 DNS** ] 頁面上，選取 [ **高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="1ceb0-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1ceb0-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1ceb0-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="1ceb0-123">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-123">**Hostname**</span></span> <br/> |<span data-ttu-id="1ceb0-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-124">**Type**</span></span> <br/> |<span data-ttu-id="1ceb0-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="1ceb0-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="1ceb0-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="1ceb0-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1ceb0-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1ceb0-128">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-128">**Note:** This is an example.</span></span> <span data-ttu-id="1ceb0-129">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="1ceb0-130">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="1ceb0-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="1ceb0-131">選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="1ceb0-132">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1ceb0-133">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="1ceb0-134">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1ceb0-135">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1ceb0-136">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="1ceb0-137">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="1ceb0-138">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1ceb0-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1ceb0-140">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1ceb0-141">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1ceb0-142">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="1ceb0-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1ceb0-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1ceb0-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="1ceb0-p107">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1ceb0-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1ceb0-147">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="1ceb0-148">在 [ **管理您的 DNS** ] 頁面上，選取 [ **高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="1ceb0-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1ceb0-150">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1ceb0-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1ceb0-151">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-151">**Hostname**</span></span>|<span data-ttu-id="1ceb0-152">**Type**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-152">**Type**</span></span>|<span data-ttu-id="1ceb0-153">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-153">**Priority**</span></span>|<span data-ttu-id="1ceb0-154">**Destination MX (目的地 MX)**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="1ceb0-155">MX</span><span class="sxs-lookup"><span data-stu-id="1ceb0-155">MX</span></span>  <br/> |<span data-ttu-id="1ceb0-156">1</span><span class="sxs-lookup"><span data-stu-id="1ceb0-156">1</span></span>  <br/> <span data-ttu-id="1ceb0-157">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="1ceb0-157">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="1ceb0-158">*\<domain-key\>*  mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="1ceb0-159">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="1ceb0-160">**注意：** 從您的 Microsoft 帳戶取得您的 \<domain-key\>。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="1ceb0-161">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="1ceb0-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![複製並貼上表格中的值](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="1ceb0-163">選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-163">Select **Add**.</span></span>
    
    ![已選取 [新增] 按鈕之對話方塊的螢幕擷取畫面](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="1ceb0-165">如果有任何其他 MX 記錄，請選擇 [ **刪除 (垃圾桶)** 該記錄的圖示來移除每個記錄。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![選取 [刪除] (垃圾桶圖示) ](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1ceb0-167">新增 Microsoft 所需的5筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="1ceb0-167">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1ceb0-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1ceb0-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="1ceb0-p109">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1ceb0-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1ceb0-172">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="1ceb0-173">在 [ **管理您的 DNS** ] 頁面上，選取 [ **高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="1ceb0-174">新增五筆 CNAME 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-174">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="1ceb0-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1ceb0-176">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1ceb0-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1ceb0-177">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-177">**Hostname**</span></span>|<span data-ttu-id="1ceb0-178">**Type**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-178">**Type**</span></span>|<span data-ttu-id="1ceb0-179">**Destination CNAME (目的地 CNAME)**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1ceb0-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1ceb0-180">autodiscover</span></span>  <br/> |<span data-ttu-id="1ceb0-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="1ceb0-181">CNAME</span></span>  <br/> |<span data-ttu-id="1ceb0-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="1ceb0-183">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1ceb0-184">sip</span><span class="sxs-lookup"><span data-stu-id="1ceb0-184">sip</span></span>  <br/> |<span data-ttu-id="1ceb0-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="1ceb0-185">CNAME</span></span>  <br/> |<span data-ttu-id="1ceb0-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1ceb0-187">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1ceb0-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1ceb0-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1ceb0-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="1ceb0-189">CNAME</span></span>  <br/> |<span data-ttu-id="1ceb0-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1ceb0-191">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1ceb0-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1ceb0-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1ceb0-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="1ceb0-193">CNAME</span></span>  <br/> |<span data-ttu-id="1ceb0-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="1ceb0-195">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1ceb0-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1ceb0-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1ceb0-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="1ceb0-197">CNAME</span></span>  <br/> |<span data-ttu-id="1ceb0-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="1ceb0-199">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![使用目的 CNAME 複製及貼上的螢幕擷取畫面](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="1ceb0-201">選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-201">Select **Add**.</span></span>
    
    ![新增目的地 CNAME 的螢幕擷取畫面](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="1ceb0-203">新增其他四筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-203">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="1ceb0-204">在 [ **ADVANCED DNS** ] 區段中，使用表格中下一列的值建立記錄，然後再選取 [ **新增** ] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="1ceb0-205">重複此程式，直到您已建立全部五筆 CNAME 記錄為止。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-205">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1ceb0-206">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="1ceb0-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1ceb0-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1ceb0-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ceb0-208">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1ceb0-209">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1ceb0-210">如果您已有網域的 SPF 記錄，請勿為 Microsfot 建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-210">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="1ceb0-211">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="1ceb0-212">需要範例？</span><span class="sxs-lookup"><span data-stu-id="1ceb0-212">Need examples?</span></span> <span data-ttu-id="1ceb0-213">請參閱這些 [Microsoft 的外部網域名稱系統記錄](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf)。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-213">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span></span> <span data-ttu-id="1ceb0-214">若要驗證您的 SPF 記錄，您可以使用其中一種 [SPF 驗證工具](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="1ceb0-215">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="1ceb0-216">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1ceb0-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1ceb0-218">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="1ceb0-219">在 [ **管理您的 DNS** ] 頁面上，選取 [ **高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="1ceb0-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1ceb0-221">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1ceb0-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1ceb0-222">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-222">**Hostname**</span></span>|<span data-ttu-id="1ceb0-223">**Type**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-223">**Type**</span></span>|<span data-ttu-id="1ceb0-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="1ceb0-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="1ceb0-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="1ceb0-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1ceb0-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1ceb0-227">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="1ceb0-229">選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-229">Select **Add**.</span></span>
    
    ![具有目的地 TXT/SPF 的螢幕擷取畫面](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1ceb0-231">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="1ceb0-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1ceb0-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1ceb0-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="1ceb0-p112">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1ceb0-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1ceb0-236">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="1ceb0-237">在 [ **管理您的 DNS** ] 頁面上，選取 [ **高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="1ceb0-238">新增兩筆 SRV 記錄的第一筆：</span><span class="sxs-lookup"><span data-stu-id="1ceb0-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="1ceb0-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1ceb0-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1ceb0-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1ceb0-241">主機名稱</span><span class="sxs-lookup"><span data-stu-id="1ceb0-241">Hostname</span></span>|<span data-ttu-id="1ceb0-242">Type (類型)</span><span class="sxs-lookup"><span data-stu-id="1ceb0-242">Type</span></span>|<span data-ttu-id="1ceb0-243">Priority (優先順序)</span><span class="sxs-lookup"><span data-stu-id="1ceb0-243">Priority</span></span>|<span data-ttu-id="1ceb0-244">TTL</span><span class="sxs-lookup"><span data-stu-id="1ceb0-244">TTL</span></span>|<span data-ttu-id="1ceb0-245">Destination SRV (目的 SRV)</span><span class="sxs-lookup"><span data-stu-id="1ceb0-245">Destination SRV</span></span>|
    |<span data-ttu-id="1ceb0-246">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="1ceb0-246">_sip._tls</span></span>|<span data-ttu-id="1ceb0-247">SRV</span><span class="sxs-lookup"><span data-stu-id="1ceb0-247">SRV</span></span>|<span data-ttu-id="1ceb0-248">100</span><span class="sxs-lookup"><span data-stu-id="1ceb0-248">100</span></span>|<span data-ttu-id="1ceb0-249">3600</span><span class="sxs-lookup"><span data-stu-id="1ceb0-249">3600</span></span>|<span data-ttu-id="1ceb0-250">1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="1ceb0-251">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="1ceb0-252">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="1ceb0-253">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="1ceb0-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="1ceb0-254">SRV</span><span class="sxs-lookup"><span data-stu-id="1ceb0-254">SRV</span></span>|<span data-ttu-id="1ceb0-255">100</span><span class="sxs-lookup"><span data-stu-id="1ceb0-255">100</span></span>|<span data-ttu-id="1ceb0-256">3600</span><span class="sxs-lookup"><span data-stu-id="1ceb0-256">3600</span></span>|<span data-ttu-id="1ceb0-257">1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="1ceb0-258">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1ceb0-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="1ceb0-259">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![使用表格中的 DNS 值的螢幕擷取畫面](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="1ceb0-261">選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-261">Select **Add**.</span></span>
    
    ![新增目的地 SRV 的螢幕擷取畫面](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="1ceb0-263">新增另一筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="1ceb0-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="1ceb0-264">在 [ **ADVANCED DNS** ] 區段中，使用表格中第二列的值來建立記錄，然後再選取 [ **新增** ] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1ceb0-265">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1ceb0-265">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1ceb0-266">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-266">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1ceb0-267">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1ceb0-267">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
