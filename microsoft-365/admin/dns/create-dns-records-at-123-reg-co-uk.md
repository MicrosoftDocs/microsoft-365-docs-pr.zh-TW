---
title: 在 123-reg.co.uk 建立 Office 365 的 DNS 記錄
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
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Office 365 123-reg.co.uk。
ms.openlocfilehash: 521426f039ac02e8c4566f5901fee49679de4e70
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211856"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a><span data-ttu-id="8edd2-103">在 123-reg.co.uk 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="8edd2-103">Create DNS records at 123-reg.co.uk for Office 365</span></span>

 <span data-ttu-id="8edd2-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="8edd2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8edd2-105">如果 123-reg.co.uk 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="8edd2-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8edd2-106">在 123-reg.co.uk 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="8edd2-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="8edd2-107">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="8edd2-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8edd2-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8edd2-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8edd2-109">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="8edd2-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8edd2-110">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="8edd2-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8edd2-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="8edd2-111">Add a TXT record for verification</span></span>
<span data-ttu-id="8edd2-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8edd2-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8edd2-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="8edd2-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8edd2-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="8edd2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8edd2-p104">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="8edd2-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8edd2-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="8edd2-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="8edd2-120">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="8edd2-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="8edd2-121">在 [**管理您的 DNS** ] 頁面上，選取 [**高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8edd2-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="8edd2-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8edd2-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8edd2-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8edd2-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="8edd2-124">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="8edd2-124">**Hostname**</span></span> <br/> |<span data-ttu-id="8edd2-125">**類型**</span><span class="sxs-lookup"><span data-stu-id="8edd2-125">**Type**</span></span> <br/> |<span data-ttu-id="8edd2-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="8edd2-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="8edd2-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="8edd2-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="8edd2-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8edd2-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8edd2-129">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="8edd2-129">**Note:** This is an example.</span></span> <span data-ttu-id="8edd2-130">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="8edd2-130">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="8edd2-131">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="8edd2-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="8edd2-132">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8edd2-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="8edd2-133">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="8edd2-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8edd2-134">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="8edd2-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="8edd2-135">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="8edd2-135">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8edd2-136">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="8edd2-136">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8edd2-137">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="8edd2-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="8edd2-138">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="8edd2-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="8edd2-139">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8edd2-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8edd2-140">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8edd2-140">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8edd2-141">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="8edd2-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8edd2-142">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="8edd2-142">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="8edd2-143">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="8edd2-143">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="8edd2-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8edd2-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="8edd2-145">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="8edd2-145">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="8edd2-146">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="8edd2-146">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8edd2-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="8edd2-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="8edd2-148">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="8edd2-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="8edd2-149">在 [**管理您的 DNS** ] 頁面上，選取 [**高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8edd2-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="8edd2-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8edd2-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8edd2-151">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8edd2-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8edd2-152">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="8edd2-152">**Hostname**</span></span>|<span data-ttu-id="8edd2-153">**類型**</span><span class="sxs-lookup"><span data-stu-id="8edd2-153">**Type**</span></span>|<span data-ttu-id="8edd2-154">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="8edd2-154">**Priority**</span></span>|<span data-ttu-id="8edd2-155">**Destination MX (目的地 MX)**</span><span class="sxs-lookup"><span data-stu-id="8edd2-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8edd2-156">MX</span><span class="sxs-lookup"><span data-stu-id="8edd2-156">MX</span></span>  <br/> |<span data-ttu-id="8edd2-157">1 </span><span class="sxs-lookup"><span data-stu-id="8edd2-157">1</span></span>  <br/> <span data-ttu-id="8edd2-158">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="8edd2-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="8edd2-159">*\<網域金鑰\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8edd2-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="8edd2-160">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8edd2-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="8edd2-161">**注意：** 從您的 Office 365 帳戶取得您的\<網域金鑰\>。</span><span class="sxs-lookup"><span data-stu-id="8edd2-161">**Note:** Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="8edd2-162">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="8edd2-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![複製並貼上表格中的值](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="8edd2-164">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="8edd2-164">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="8edd2-166">如果有任何其他的 MX 記錄，請選擇該記錄的**刪除（垃圾桶）** 圖示以逐一移除。</span><span class="sxs-lookup"><span data-stu-id="8edd2-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![選取 [刪除] （垃圾桶圖示）](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="8edd2-168">新增 Office 365 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="8edd2-168">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="8edd2-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8edd2-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="8edd2-170">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="8edd2-170">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="8edd2-171">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="8edd2-171">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8edd2-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="8edd2-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="8edd2-173">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="8edd2-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="8edd2-174">在 [**管理您的 DNS** ] 頁面上，選取 [**高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8edd2-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="8edd2-175">新增六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="8edd2-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="8edd2-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8edd2-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8edd2-177">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8edd2-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8edd2-178">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="8edd2-178">**Hostname**</span></span>|<span data-ttu-id="8edd2-179">**類型**</span><span class="sxs-lookup"><span data-stu-id="8edd2-179">**Type**</span></span>|<span data-ttu-id="8edd2-180">**Destination CNAME (目的地 CNAME)**</span><span class="sxs-lookup"><span data-stu-id="8edd2-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8edd2-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8edd2-181">autodiscover</span></span>  <br/> |<span data-ttu-id="8edd2-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="8edd2-182">CNAME</span></span>  <br/> |<span data-ttu-id="8edd2-183">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="8edd2-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="8edd2-184">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8edd2-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8edd2-185">sip</span><span class="sxs-lookup"><span data-stu-id="8edd2-185">sip</span></span>  <br/> |<span data-ttu-id="8edd2-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="8edd2-186">CNAME</span></span>  <br/> |<span data-ttu-id="8edd2-187">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="8edd2-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8edd2-188">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8edd2-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8edd2-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8edd2-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8edd2-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="8edd2-190">CNAME</span></span>  <br/> |<span data-ttu-id="8edd2-191">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="8edd2-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8edd2-192">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8edd2-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8edd2-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8edd2-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8edd2-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="8edd2-194">CNAME</span></span>  <br/> |<span data-ttu-id="8edd2-195">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="8edd2-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="8edd2-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8edd2-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="8edd2-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8edd2-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8edd2-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="8edd2-198">CNAME</span></span>  <br/> |<span data-ttu-id="8edd2-199">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="8edd2-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="8edd2-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8edd2-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![複製並貼上表格中的值](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="8edd2-202">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="8edd2-202">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="8edd2-204">新增其他五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="8edd2-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="8edd2-205">在 [ **ADVANCED DNS** ] 區段中，使用表格中下一列的值建立記錄，然後再選取 [**新增**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="8edd2-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="8edd2-206">重複這個程序，直到六筆 CNAME 記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="8edd2-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8edd2-207">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="8edd2-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8edd2-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8edd2-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8edd2-209">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="8edd2-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8edd2-210">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="8edd2-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8edd2-211">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="8edd2-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="8edd2-212">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="8edd2-212">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="8edd2-213">需要範例？</span><span class="sxs-lookup"><span data-stu-id="8edd2-213">Need examples?</span></span> <span data-ttu-id="8edd2-214">請參閱這些 [Office 365 的外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="8edd2-214">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="8edd2-215">若要驗證您的 SPF 記錄，您可以使用其中一種 [SPF 驗證工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="8edd2-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="8edd2-216">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="8edd2-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="8edd2-217">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="8edd2-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8edd2-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="8edd2-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="8edd2-219">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="8edd2-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="8edd2-220">在 [**管理您的 DNS** ] 頁面上，選取 [**高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8edd2-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="8edd2-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8edd2-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8edd2-222">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8edd2-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8edd2-223">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="8edd2-223">**Hostname**</span></span>|<span data-ttu-id="8edd2-224">**類型**</span><span class="sxs-lookup"><span data-stu-id="8edd2-224">**Type**</span></span>|<span data-ttu-id="8edd2-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="8edd2-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8edd2-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="8edd2-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="8edd2-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8edd2-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8edd2-228">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="8edd2-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="8edd2-230">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="8edd2-230">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="8edd2-232">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="8edd2-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="8edd2-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8edd2-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="8edd2-234">首先請用[這個連結](https://www.123-reg.co.uk/secure/cpanel/domain/overview)移至 123-reg.co.uk 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="8edd2-234">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="8edd2-235">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="8edd2-235">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8edd2-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="8edd2-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="8edd2-237">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="8edd2-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="8edd2-238">在 [**管理您的 DNS** ] 頁面上，選取 [**高級 DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8edd2-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="8edd2-239">新增兩筆 SRV 記錄的第一筆：</span><span class="sxs-lookup"><span data-stu-id="8edd2-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="8edd2-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8edd2-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8edd2-241">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="8edd2-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8edd2-242">主機名稱</span><span class="sxs-lookup"><span data-stu-id="8edd2-242">Hostname</span></span>|<span data-ttu-id="8edd2-243">Type (類型)</span><span class="sxs-lookup"><span data-stu-id="8edd2-243">Type</span></span>|<span data-ttu-id="8edd2-244">Priority (優先順序)</span><span class="sxs-lookup"><span data-stu-id="8edd2-244">Priority</span></span>|<span data-ttu-id="8edd2-245">TTL</span><span class="sxs-lookup"><span data-stu-id="8edd2-245">TTL</span></span>|<span data-ttu-id="8edd2-246">Destination SRV (目的 SRV)</span><span class="sxs-lookup"><span data-stu-id="8edd2-246">Destination SRV</span></span>|
    |<span data-ttu-id="8edd2-247">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="8edd2-247">_sip._tls</span></span>|<span data-ttu-id="8edd2-248">SRV</span><span class="sxs-lookup"><span data-stu-id="8edd2-248">SRV</span></span>|<span data-ttu-id="8edd2-249">100</span><span class="sxs-lookup"><span data-stu-id="8edd2-249">100</span></span>|<span data-ttu-id="8edd2-250">3600</span><span class="sxs-lookup"><span data-stu-id="8edd2-250">3600</span></span>|<span data-ttu-id="8edd2-251">1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="8edd2-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="8edd2-252">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8edd2-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="8edd2-253">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="8edd2-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="8edd2-254">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="8edd2-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="8edd2-255">SRV</span><span class="sxs-lookup"><span data-stu-id="8edd2-255">SRV</span></span>|<span data-ttu-id="8edd2-256">100</span><span class="sxs-lookup"><span data-stu-id="8edd2-256">100</span></span>|<span data-ttu-id="8edd2-257">3600</span><span class="sxs-lookup"><span data-stu-id="8edd2-257">3600</span></span>|<span data-ttu-id="8edd2-258">1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="8edd2-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="8edd2-259">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="8edd2-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="8edd2-260">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="8edd2-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![複製並貼上表格中的值](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="8edd2-262">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="8edd2-262">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="8edd2-264">新增另一筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="8edd2-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="8edd2-265">在 [ **ADVANCED DNS** ] 區段中，使用表格中第二列的值來建立記錄，然後再選取 [**新增**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="8edd2-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8edd2-266">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="8edd2-266">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="8edd2-267">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="8edd2-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="8edd2-268">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="8edd2-268">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
