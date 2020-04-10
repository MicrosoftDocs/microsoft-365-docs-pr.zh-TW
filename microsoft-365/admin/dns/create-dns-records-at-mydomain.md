---
title: 在 MyDomain 建立 Office 365 的 DNS 記錄
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: 了解如何在 Office 365 的 [我的網域] 中驗證網域，並為電子郵件、商務用 Skype Online和其他服務設定 DNS 記錄。
ms.openlocfilehash: 1a75c2ab0077cac07781e5102c43e53ed965b1df
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211688"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a><span data-ttu-id="68f84-103">在 MyDomain 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="68f84-103">Create DNS records at MyDomain for Office 365</span></span>


  
 <span data-ttu-id="68f84-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="68f84-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="68f84-105">MyDomain 網站不支援 SRV 記錄，這表示有幾項商務用 Skype Online 和 Outlook Web App 功能將無法使用。</span><span class="sxs-lookup"><span data-stu-id="68f84-105">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="68f84-106">無論您使用哪一種 Office 365 方案，只要在 MyDomain 管理 DNS 記錄，都會受到[重大的服務限制](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)，建議您改換不同的 DNS 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="68f84-106">No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="68f84-107">儘管有這些服務限制，如果您仍選擇在 MyDomain 管理您的 Office 365 DNS 記錄，請按照本文中的步驟設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="68f84-107">If you choose to manage your own Office 365 DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="68f84-108">在 MyDomain 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="68f84-108">After you add these records at MyDomain, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="68f84-109">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="68f84-109">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="68f84-110">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="68f84-110">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="68f84-111">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="68f84-111">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="68f84-112">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="68f84-112">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="68f84-113">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="68f84-113">Add a TXT record for verification</span></span>
<span data-ttu-id="68f84-114"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="68f84-114"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="68f84-p103">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="68f84-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68f84-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="68f84-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="68f84-p105">首先，請用[此連結](https://www.mydomain.com/controlpanel)移至您在 MyDomain 的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="68f84-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="68f84-121">在 [我的最愛]\*\*\*\* 區段中，選取 [網域中央]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-121">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="68f84-122">在 [網域]\*\*\*\* 下方，選取要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="68f84-122">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="68f84-123">在 [總覽]\*\*\*\* 區段，選取 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-123">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="68f84-124">從 [修改]\*\*\*\* 下拉式清單中，選擇 [TXT/SPF 記錄]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-124">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="68f84-125">在 [內容] 底下，於新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="68f84-125">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="68f84-126">**內容**</span><span class="sxs-lookup"><span data-stu-id="68f84-126">**Content**</span></span> <br/> |
    |<span data-ttu-id="68f84-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="68f84-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="68f84-128">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="68f84-128">**Note:** This is an example.</span></span> <span data-ttu-id="68f84-129">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="68f84-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="68f84-130">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="68f84-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="68f84-131">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-131">Select **Add**.</span></span>
    
8. <span data-ttu-id="68f84-132">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="68f84-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="68f84-133">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="68f84-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="68f84-134">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="68f84-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="68f84-135">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="68f84-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="68f84-136">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="68f84-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="68f84-137">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="68f84-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="68f84-138">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="68f84-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="68f84-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="68f84-140">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="68f84-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="68f84-141">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="68f84-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="68f84-142">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="68f84-142">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="68f84-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="68f84-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="68f84-p108">首先，請用[此連結](https://www.mydomain.com/controlpanel)移至您在 MyDomain 的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="68f84-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="68f84-146">在 [我的最愛]\*\*\*\* 區段中，選取 [網域中央]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="68f84-147">在 [網域]\*\*\*\* 下方，選取要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="68f84-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="68f84-148">在 [總覽]\*\*\*\* 區段，選取 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-148">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="68f84-149">在 [Modify] (修改)\*\*\*\* 下拉式清單中，選擇 [MX Record] (MX 記錄)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-149">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="68f84-151">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="68f84-151">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="68f84-152">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="68f84-152">**Priority**</span></span>|<span data-ttu-id="68f84-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="68f84-153">**Host**</span></span>|<span data-ttu-id="68f84-154">**Points to: (指向:)**</span><span class="sxs-lookup"><span data-stu-id="68f84-154">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="68f84-155">0</span><span class="sxs-lookup"><span data-stu-id="68f84-155">0</span></span>  <br/> <span data-ttu-id="68f84-156">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="68f84-156">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |@  <br/> | <span data-ttu-id="68f84-157">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="68f84-157">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="68f84-158">**注意：** 從您的 Office 365 帳戶取得您的\<*網域金鑰*\>。</span><span class="sxs-lookup"><span data-stu-id="68f84-158">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span><span data-ttu-id="68f84-159"> > [如何找到這項資訊？](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="68f84-159"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="68f84-161">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-161">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="68f84-163">如果有任何其他現有的 MX 記錄，請針對每一筆記錄，選取 [Actions] (動作)\*\*\*\* 欄中的 [Remove] (移除)\*\*\*\*，將它刪除。</span><span class="sxs-lookup"><span data-stu-id="68f84-163">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="68f84-165">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-165">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="68f84-167">新增 Office 365 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="68f84-167">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="68f84-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="68f84-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="68f84-p110">首先，請用[此連結](https://www.mydomain.com/controlpanel)移至您在 MyDomain 的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="68f84-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="68f84-171">在 [我的最愛]\*\*\*\* 區段中，選取 [網域中央]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-171">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="68f84-172">在 [網域]\*\*\*\* 下方，選取要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="68f84-172">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="68f84-173">在 [總覽]\*\*\*\* 區段，選取 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-173">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="68f84-174">在 [Modify] (修改)\*\*\*\* 下拉式清單中，選取 [CNAME Alias] (CNAME 別名)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-174">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="68f84-176">新增第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="68f84-176">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="68f84-177">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="68f84-177">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="68f84-178">**Host**</span><span class="sxs-lookup"><span data-stu-id="68f84-178">**Host**</span></span>|<span data-ttu-id="68f84-179">**Points to: (指向:)**</span><span class="sxs-lookup"><span data-stu-id="68f84-179">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="68f84-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="68f84-180">autodiscover</span></span>  <br/> |<span data-ttu-id="68f84-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="68f84-181">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="68f84-182">sip</span><span class="sxs-lookup"><span data-stu-id="68f84-182">sip</span></span>  <br/> |<span data-ttu-id="68f84-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="68f84-183">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="68f84-184">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="68f84-184">lyncdiscover</span></span>  <br/> |<span data-ttu-id="68f84-185">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="68f84-185">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="68f84-186">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="68f84-186">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="68f84-187">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="68f84-187">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="68f84-188">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="68f84-188">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="68f84-189">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="68f84-189">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="68f84-191">選取 [新增]\*\*\*\* 以新增第一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="68f84-191">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="68f84-193">新增第二筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="68f84-193">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="68f84-194">使用上表中第二列的值，然後選取 [新增]\*\*\*\* 以新增第二筆記錄。</span><span class="sxs-lookup"><span data-stu-id="68f84-194">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="68f84-195">以此類推，使用表格中第三、四、五、六列的值新增其他記錄。</span><span class="sxs-lookup"><span data-stu-id="68f84-195">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="68f84-196">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="68f84-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="68f84-197"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="68f84-197"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="68f84-198">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="68f84-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="68f84-199">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="68f84-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="68f84-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="68f84-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="68f84-201">而是，請將必要的 Office 365 值新增至目前的記錄，以便擁有包含這兩組值的單一 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="68f84-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="68f84-202">需要範例？</span><span class="sxs-lookup"><span data-stu-id="68f84-202">Need examples?</span></span> <span data-ttu-id="68f84-203">請參閱這些 [Office 365 的外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="68f84-203">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="68f84-204">若要驗證您的 SPF 記錄，您可以使用其中一種 [SPF 驗證工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="68f84-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="68f84-p112">首先，請用[此連結](https://www.mydomain.com/controlpanel)移至您在 MyDomain 的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="68f84-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="68f84-207">在 [我的最愛]\*\*\*\* 區段中，選取 [網域中央]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-207">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="68f84-208">在 [網域]\*\*\*\* 下方，選取要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="68f84-208">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="68f84-209">在 [總覽]\*\*\*\* 區段，選取 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-209">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="68f84-210">從 [修改]\*\*\*\* 下拉式清單中，選擇 [TXT/SPF 記錄]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-210">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="68f84-212">在 [內容] 底下，於新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="68f84-212">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="68f84-213">**內容**</span><span class="sxs-lookup"><span data-stu-id="68f84-213">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="68f84-214">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="68f84-214">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="68f84-215">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="68f84-215">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="68f84-217">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68f84-217">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="68f84-219">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="68f84-219">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="68f84-220"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="68f84-220"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="68f84-221">MyDomain 網站不支援 SRV 記錄，這表示有幾項商務用 Skype Online 和 Outlook Web App 功能將無法使用。</span><span class="sxs-lookup"><span data-stu-id="68f84-221">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="68f84-222">無論您使用哪一種 Office 365 方案，只要在 MyDomain 管理 DNS 記錄，都會受到[重大的服務限制](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)，建議您改換不同的 DNS 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="68f84-222">No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="68f84-223">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="68f84-223">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="68f84-224">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="68f84-224">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="68f84-225">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="68f84-225">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
