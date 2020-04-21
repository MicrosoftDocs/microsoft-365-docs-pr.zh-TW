---
title: 在123-reg.co.uk 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft 123-reg.co.uk。
ms.openlocfilehash: 887e7e6fc42fb55d4cc09ba66b68a2bb9702bbb9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629740"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="5d705-103">在123-reg.co.uk 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="5d705-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="5d705-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="5d705-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5d705-105">如果 123-reg.co.uk 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="5d705-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5d705-106">在123-reg.co.uk 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="5d705-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="5d705-107">若要深入瞭解 Microsoft 的網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="5d705-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d705-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="5d705-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="5d705-109">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="5d705-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="5d705-110">如果您在新增 DNS 記錄後遇到郵件流程或其他問題的問題，請參閱[尋找並修正新增您的網域或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="5d705-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5d705-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="5d705-111">Add a TXT record for verification</span></span>
<span data-ttu-id="5d705-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5d705-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5d705-113">在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="5d705-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="5d705-114">您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。</span><span class="sxs-lookup"><span data-stu-id="5d705-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d705-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="5d705-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5d705-p104">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="5d705-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5d705-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="5d705-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5d705-120">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="5d705-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="5d705-121">在 [**管理您的 DNS** ] 頁面上，選取 [**高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5d705-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="5d705-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5d705-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5d705-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5d705-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="5d705-124">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="5d705-124">**Hostname**</span></span> <br/> |<span data-ttu-id="5d705-125">**類型**</span><span class="sxs-lookup"><span data-stu-id="5d705-125">**Type**</span></span> <br/> |<span data-ttu-id="5d705-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="5d705-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="5d705-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="5d705-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="5d705-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5d705-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5d705-129">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="5d705-129">**Note:** This is an example.</span></span> <span data-ttu-id="5d705-130">從表格中，使用您的特定**目的地或指向位址**值。</span><span class="sxs-lookup"><span data-stu-id="5d705-130">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="5d705-131">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="5d705-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="5d705-132">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d705-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="5d705-133">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="5d705-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5d705-134">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。</span><span class="sxs-lookup"><span data-stu-id="5d705-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="5d705-135">當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="5d705-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5d705-136">在 Microsoft 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5d705-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5d705-137">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="5d705-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5d705-138">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="5d705-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5d705-139">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d705-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5d705-140">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="5d705-140">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="5d705-141">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="5d705-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="5d705-142">如果您在新增 DNS 記錄後遇到郵件流程或其他問題的問題，請參閱[尋找並修正新增您的網域或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="5d705-142">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5d705-143">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="5d705-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5d705-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5d705-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5d705-145">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="5d705-145">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="5d705-146">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="5d705-146">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5d705-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="5d705-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5d705-148">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="5d705-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="5d705-149">在 [**管理您的 DNS** ] 頁面上，選取 [**高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5d705-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="5d705-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5d705-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5d705-151">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5d705-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5d705-152">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="5d705-152">**Hostname**</span></span>|<span data-ttu-id="5d705-153">**類型**</span><span class="sxs-lookup"><span data-stu-id="5d705-153">**Type**</span></span>|<span data-ttu-id="5d705-154">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="5d705-154">**Priority**</span></span>|<span data-ttu-id="5d705-155">**Destination MX (目的地 MX)**</span><span class="sxs-lookup"><span data-stu-id="5d705-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5d705-156">MX</span><span class="sxs-lookup"><span data-stu-id="5d705-156">MX</span></span>  <br/> |<span data-ttu-id="5d705-157">1 </span><span class="sxs-lookup"><span data-stu-id="5d705-157">1</span></span>  <br/> <span data-ttu-id="5d705-158">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="5d705-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="5d705-159">*\<網域金鑰\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="5d705-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="5d705-160">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5d705-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="5d705-161">**附注：** 從您\<的 Microsoft 帳戶\>取得您的網域金鑰。</span><span class="sxs-lookup"><span data-stu-id="5d705-161">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="5d705-162">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="5d705-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![複製並貼上表格中的值](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="5d705-164">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d705-164">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="5d705-166">如果有任何其他的 MX 記錄，請選擇該記錄的**刪除（垃圾桶）** 圖示以逐一移除。</span><span class="sxs-lookup"><span data-stu-id="5d705-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![選取 [刪除] （垃圾桶圖示）](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5d705-168">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="5d705-168">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5d705-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5d705-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5d705-170">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="5d705-170">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="5d705-171">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="5d705-171">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5d705-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="5d705-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5d705-173">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="5d705-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="5d705-174">在 [**管理您的 DNS** ] 頁面上，選取 [**高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5d705-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="5d705-175">新增六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="5d705-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="5d705-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5d705-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5d705-177">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5d705-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5d705-178">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="5d705-178">**Hostname**</span></span>|<span data-ttu-id="5d705-179">**類型**</span><span class="sxs-lookup"><span data-stu-id="5d705-179">**Type**</span></span>|<span data-ttu-id="5d705-180">**Destination CNAME (目的地 CNAME)**</span><span class="sxs-lookup"><span data-stu-id="5d705-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5d705-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5d705-181">autodiscover</span></span>  <br/> |<span data-ttu-id="5d705-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="5d705-182">CNAME</span></span>  <br/> |<span data-ttu-id="5d705-183">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="5d705-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="5d705-184">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5d705-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5d705-185">sip</span><span class="sxs-lookup"><span data-stu-id="5d705-185">sip</span></span>  <br/> |<span data-ttu-id="5d705-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="5d705-186">CNAME</span></span>  <br/> |<span data-ttu-id="5d705-187">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="5d705-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5d705-188">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5d705-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5d705-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5d705-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5d705-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="5d705-190">CNAME</span></span>  <br/> |<span data-ttu-id="5d705-191">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="5d705-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5d705-192">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5d705-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5d705-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5d705-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5d705-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="5d705-194">CNAME</span></span>  <br/> |<span data-ttu-id="5d705-195">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="5d705-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="5d705-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5d705-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5d705-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5d705-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5d705-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="5d705-198">CNAME</span></span>  <br/> |<span data-ttu-id="5d705-199">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="5d705-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="5d705-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5d705-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![複製並貼上表格中的值](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="5d705-202">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d705-202">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="5d705-204">新增其他五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="5d705-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="5d705-205">在 [ **ADVANCED DNS** ] 區段中，使用表格中下一列的值建立記錄，然後再選取 [**新增**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="5d705-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="5d705-206">重複這個程序，直到六筆 CNAME 記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="5d705-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5d705-207">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="5d705-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5d705-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5d705-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d705-209">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="5d705-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5d705-210">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="5d705-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5d705-211">如果您已有網域的 SPF 記錄，請勿為 Microsfot 建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="5d705-211">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="5d705-212">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="5d705-212">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="5d705-213">需要範例？</span><span class="sxs-lookup"><span data-stu-id="5d705-213">Need examples?</span></span> <span data-ttu-id="5d705-214">請參閱[Microsoft 的這些外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="5d705-214">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="5d705-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="5d705-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="5d705-216">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="5d705-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="5d705-217">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="5d705-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5d705-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="5d705-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5d705-219">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="5d705-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="5d705-220">在 [**管理您的 DNS** ] 頁面上，選取 [**高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5d705-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="5d705-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5d705-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5d705-222">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5d705-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5d705-223">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="5d705-223">**Hostname**</span></span>|<span data-ttu-id="5d705-224">**類型**</span><span class="sxs-lookup"><span data-stu-id="5d705-224">**Type**</span></span>|<span data-ttu-id="5d705-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="5d705-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5d705-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="5d705-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="5d705-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5d705-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5d705-228">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="5d705-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="5d705-230">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d705-230">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5d705-232">新增 Microsoft 所需的兩筆 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="5d705-232">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5d705-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5d705-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5d705-234">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="5d705-234">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="5d705-235">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="5d705-235">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5d705-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="5d705-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5d705-237">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="5d705-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="5d705-238">在 [**管理您的 DNS** ] 頁面上，選取 [**高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5d705-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="5d705-239">新增兩筆 SRV 記錄的第一筆：</span><span class="sxs-lookup"><span data-stu-id="5d705-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="5d705-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5d705-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5d705-241">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5d705-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5d705-242">主機名稱</span><span class="sxs-lookup"><span data-stu-id="5d705-242">Hostname</span></span>|<span data-ttu-id="5d705-243">Type (類型)</span><span class="sxs-lookup"><span data-stu-id="5d705-243">Type</span></span>|<span data-ttu-id="5d705-244">Priority (優先順序)</span><span class="sxs-lookup"><span data-stu-id="5d705-244">Priority</span></span>|<span data-ttu-id="5d705-245">TTL</span><span class="sxs-lookup"><span data-stu-id="5d705-245">TTL</span></span>|<span data-ttu-id="5d705-246">Destination SRV (目的 SRV)</span><span class="sxs-lookup"><span data-stu-id="5d705-246">Destination SRV</span></span>|
    |<span data-ttu-id="5d705-247">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="5d705-247">_sip._tls</span></span>|<span data-ttu-id="5d705-248">SRV</span><span class="sxs-lookup"><span data-stu-id="5d705-248">SRV</span></span>|<span data-ttu-id="5d705-249">100</span><span class="sxs-lookup"><span data-stu-id="5d705-249">100</span></span>|<span data-ttu-id="5d705-250">3600</span><span class="sxs-lookup"><span data-stu-id="5d705-250">3600</span></span>|<span data-ttu-id="5d705-251">1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="5d705-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="5d705-252">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5d705-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="5d705-253">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="5d705-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="5d705-254">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="5d705-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="5d705-255">SRV</span><span class="sxs-lookup"><span data-stu-id="5d705-255">SRV</span></span>|<span data-ttu-id="5d705-256">100</span><span class="sxs-lookup"><span data-stu-id="5d705-256">100</span></span>|<span data-ttu-id="5d705-257">3600</span><span class="sxs-lookup"><span data-stu-id="5d705-257">3600</span></span>|<span data-ttu-id="5d705-258">1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="5d705-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="5d705-259">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5d705-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="5d705-260">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="5d705-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![複製並貼上表格中的值](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="5d705-262">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d705-262">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="5d705-264">新增另一筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="5d705-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="5d705-265">在 [ **ADVANCED DNS** ] 區段中，使用表格中第二列的值來建立記錄，然後再選取 [**新增**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="5d705-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="5d705-266">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="5d705-266">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="5d705-267">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="5d705-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="5d705-268">如果您在新增 DNS 記錄後遇到郵件流程或其他問題的問題，請參閱[尋找並修正新增您的網域或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="5d705-268">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
