---
title: 在 Dreamhost 建立 Office 365 的 DNS 記錄
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Office 365 Dreamhost。
ms.openlocfilehash: 1997af6e14dcb6a118dfcc3558037ed56d07ea87
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211784"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a><span data-ttu-id="40bb9-103">在 Dreamhost 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="40bb9-103">Create DNS records at Dreamhost for Office 365</span></span>

 <span data-ttu-id="40bb9-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="40bb9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="40bb9-105">如果 DreamHost 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、Lync 等等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="40bb9-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="40bb9-106">在 DreamHost 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="40bb9-106">After you add these records at DreamHost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="40bb9-107">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="40bb9-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="40bb9-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="40bb9-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="40bb9-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="40bb9-111">Add a TXT record for verification</span></span>
<span data-ttu-id="40bb9-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="40bb9-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="40bb9-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="40bb9-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40bb9-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="40bb9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="40bb9-117">若要開始使用，請移至您的網域頁面 DreamHost，方法是使用[此連結](https://panel.dreamhost.com/)。</span><span class="sxs-lookup"><span data-stu-id="40bb9-117">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="40bb9-118">系統會提示您登入。</span><span class="sxs-lookup"><span data-stu-id="40bb9-118">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="40bb9-120">在 [**儀表板**] 頁面上，選取 [**網域**]，然後**管理網域**。</span><span class="sxs-lookup"><span data-stu-id="40bb9-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="40bb9-122">在 [**管理網域**] 頁面上的 [**網域**] 區段中，選取您要編輯之網域的 [ **DNS** ]。</span><span class="sxs-lookup"><span data-stu-id="40bb9-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="40bb9-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="40bb9-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="40bb9-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="40bb9-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="40bb9-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="40bb9-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="40bb9-127">**名稱**</span><span class="sxs-lookup"><span data-stu-id="40bb9-127">**Name**</span></span>|<span data-ttu-id="40bb9-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="40bb9-128">**Type**</span></span>|<span data-ttu-id="40bb9-129">**Value**</span><span class="sxs-lookup"><span data-stu-id="40bb9-129">**Value**</span></span>|<span data-ttu-id="40bb9-130">**Comment**</span><span class="sxs-lookup"><span data-stu-id="40bb9-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="40bb9-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="40bb9-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="40bb9-132">TXT</span><span class="sxs-lookup"><span data-stu-id="40bb9-132">TXT</span></span>  <br/> |<span data-ttu-id="40bb9-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="40bb9-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="40bb9-134">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="40bb9-134">**Note:** This is an example.</span></span> <span data-ttu-id="40bb9-135">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="40bb9-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="40bb9-136">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="40bb9-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="40bb9-137">（此欄位是選用的。）</span><span class="sxs-lookup"><span data-stu-id="40bb9-137">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="40bb9-139">選取 [**立即加入記錄！** ]</span><span class="sxs-lookup"><span data-stu-id="40bb9-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="40bb9-141">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="40bb9-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="40bb9-142">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="40bb9-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="40bb9-143">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="40bb9-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="40bb9-144">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="40bb9-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="40bb9-145">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="40bb9-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="40bb9-146">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="40bb9-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="40bb9-147">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="40bb9-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="40bb9-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="40bb9-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="40bb9-151">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="40bb9-151">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="40bb9-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="40bb9-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="40bb9-153">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="40bb9-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="40bb9-154">若要開始使用，請移至您的網域頁面 DreamHost，方法是使用[此連結](https://panel.dreamhost.com/)。</span><span class="sxs-lookup"><span data-stu-id="40bb9-154">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="40bb9-155">系統會提示您登入。</span><span class="sxs-lookup"><span data-stu-id="40bb9-155">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="40bb9-157">在 [**儀表板**] 頁面上，選取 [**郵件**]，然後選取 [**自訂 MX**]。</span><span class="sxs-lookup"><span data-stu-id="40bb9-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="40bb9-159">在 [**管理郵件傳遞**] 區段的 [**動作**] 欄中，針對您要編輯的網域，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="40bb9-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="40bb9-161">在 [**自訂 MX 記錄**] 區段的新記錄方塊中，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="40bb9-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="40bb9-162">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="40bb9-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="40bb9-163">（如果有任何其他現有的 MX 記錄，請將這些記錄標示為待刪除。）</span><span class="sxs-lookup"><span data-stu-id="40bb9-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="40bb9-164">**MX 記錄（必要）**</span><span class="sxs-lookup"><span data-stu-id="40bb9-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="40bb9-165">0  *\<網域金鑰\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="40bb9-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="40bb9-166">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="40bb9-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="40bb9-p108">0 是指 MX 優先順序值。請將它新增到 MX 值的開頭，並以空格分隔該值的其餘部分。  </span><span class="sxs-lookup"><span data-stu-id="40bb9-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="40bb9-169">**附注：** 從您的 Office 365 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="40bb9-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="40bb9-170">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="40bb9-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-BP-Configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="40bb9-172">選取 [**變更這個網域立即使用自訂的 MX 記錄！** ]</span><span class="sxs-lookup"><span data-stu-id="40bb9-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="40bb9-174">如果有任何其他現有的 MX 記錄，請選取該專案，然後按下鍵盤上的**delete**鍵，以刪除每一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="40bb9-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="40bb9-176">如果您已刪除任何記錄，請選取 [**立即更新您的自訂 MX 記錄！** ]。</span><span class="sxs-lookup"><span data-stu-id="40bb9-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="40bb9-178">新增 Office 365 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="40bb9-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="40bb9-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="40bb9-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="40bb9-180">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="40bb9-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="40bb9-181">若要開始使用，請移至您的網域頁面 DreamHost，方法是使用[此連結](https://panel.dreamhost.com/)。</span><span class="sxs-lookup"><span data-stu-id="40bb9-181">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="40bb9-182">系統會提示您登入。</span><span class="sxs-lookup"><span data-stu-id="40bb9-182">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="40bb9-184">在 [**儀表板**] 頁面上，選取 [**網域**]，然後**管理網域**。</span><span class="sxs-lookup"><span data-stu-id="40bb9-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="40bb9-186">在 [**管理網域**] 頁面上的 [**網域**] 區段中，選取您要編輯之網域的 [ **DNS** ]。</span><span class="sxs-lookup"><span data-stu-id="40bb9-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="40bb9-188">在 [新增**自訂 DNS 記錄**] 區段的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="40bb9-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="40bb9-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="40bb9-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="40bb9-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="40bb9-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="40bb9-191">**名稱**</span><span class="sxs-lookup"><span data-stu-id="40bb9-191">**Name**</span></span>|<span data-ttu-id="40bb9-192">**Type**</span><span class="sxs-lookup"><span data-stu-id="40bb9-192">**Type**</span></span>|<span data-ttu-id="40bb9-193">**Value**</span><span class="sxs-lookup"><span data-stu-id="40bb9-193">**Value**</span></span>|<span data-ttu-id="40bb9-194">**Comment**</span><span class="sxs-lookup"><span data-stu-id="40bb9-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="40bb9-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="40bb9-195">autodiscover</span></span>  <br/> |<span data-ttu-id="40bb9-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="40bb9-196">CNAME</span></span>  <br/> |<span data-ttu-id="40bb9-197">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="40bb9-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="40bb9-198">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="40bb9-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="40bb9-199">（此欄位是選用的。）</span><span class="sxs-lookup"><span data-stu-id="40bb9-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="40bb9-200">sip</span><span class="sxs-lookup"><span data-stu-id="40bb9-200">sip</span></span>  <br/> |<span data-ttu-id="40bb9-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="40bb9-201">CNAME</span></span>  <br/> |<span data-ttu-id="40bb9-202">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="40bb9-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="40bb9-203">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="40bb9-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="40bb9-204">（此欄位是選用的。）</span><span class="sxs-lookup"><span data-stu-id="40bb9-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="40bb9-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="40bb9-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="40bb9-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="40bb9-206">CNAME</span></span>  <br/> |<span data-ttu-id="40bb9-207">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="40bb9-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="40bb9-208">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="40bb9-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="40bb9-209">（此欄位是選用的。）</span><span class="sxs-lookup"><span data-stu-id="40bb9-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="40bb9-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="40bb9-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="40bb9-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="40bb9-211">CNAME</span></span>  <br/> |<span data-ttu-id="40bb9-212">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="40bb9-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="40bb9-213">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="40bb9-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="40bb9-214">（此欄位是選用的。）</span><span class="sxs-lookup"><span data-stu-id="40bb9-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="40bb9-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="40bb9-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="40bb9-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="40bb9-216">CNAME</span></span>  <br/> |<span data-ttu-id="40bb9-217">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="40bb9-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="40bb9-218">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="40bb9-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="40bb9-219">（此欄位是選用的。）</span><span class="sxs-lookup"><span data-stu-id="40bb9-219">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-Configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="40bb9-221">選取 [**立即加入記錄！** ]</span><span class="sxs-lookup"><span data-stu-id="40bb9-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="40bb9-223">使用前兩個步驟和表格中其他五列的值，新增其餘五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="40bb9-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="40bb9-224">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="40bb9-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="40bb9-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="40bb9-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="40bb9-226">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="40bb9-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="40bb9-227">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="40bb9-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="40bb9-228">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="40bb9-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="40bb9-229">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="40bb9-229">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="40bb9-230">請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="40bb9-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="40bb9-231">若要開始使用，請移至您的網域頁面 DreamHost，方法是使用[此連結](https://panel.dreamhost.com/)。</span><span class="sxs-lookup"><span data-stu-id="40bb9-231">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="40bb9-232">系統會提示您登入。</span><span class="sxs-lookup"><span data-stu-id="40bb9-232">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="40bb9-234">在 [**儀表板**] 頁面上，選取 [**網域**]，然後**管理網域**。</span><span class="sxs-lookup"><span data-stu-id="40bb9-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="40bb9-236">在 [**管理網域**] 頁面上的 [**網域**] 區段中，選取您要編輯之網域的 [ **DNS** ]。</span><span class="sxs-lookup"><span data-stu-id="40bb9-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="40bb9-238">在 [新增**自訂 DNS 記錄**] 區段的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="40bb9-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="40bb9-239">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="40bb9-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="40bb9-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="40bb9-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="40bb9-241">**名稱**</span><span class="sxs-lookup"><span data-stu-id="40bb9-241">**Name**</span></span>|<span data-ttu-id="40bb9-242">**Type**</span><span class="sxs-lookup"><span data-stu-id="40bb9-242">**Type**</span></span>|<span data-ttu-id="40bb9-243">**Value**</span><span class="sxs-lookup"><span data-stu-id="40bb9-243">**Value**</span></span>|<span data-ttu-id="40bb9-244">**Comment**</span><span class="sxs-lookup"><span data-stu-id="40bb9-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="40bb9-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="40bb9-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="40bb9-246">TXT</span><span class="sxs-lookup"><span data-stu-id="40bb9-246">TXT</span></span>  <br/> |<span data-ttu-id="40bb9-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="40bb9-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="40bb9-248">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="40bb9-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="40bb9-249">（此欄位是選用的。）</span><span class="sxs-lookup"><span data-stu-id="40bb9-249">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="40bb9-251">選取 [**立即加入記錄！** ]</span><span class="sxs-lookup"><span data-stu-id="40bb9-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="40bb9-253">使用前面的兩個步驟和表格中第二列的值，新增其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="40bb9-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="40bb9-254">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="40bb9-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="40bb9-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="40bb9-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="40bb9-256">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="40bb9-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="40bb9-257">若要開始使用，請移至您的網域頁面 DreamHost，方法是使用[此連結](https://panel.dreamhost.com/)。</span><span class="sxs-lookup"><span data-stu-id="40bb9-257">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="40bb9-258">系統會提示您登入。</span><span class="sxs-lookup"><span data-stu-id="40bb9-258">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="40bb9-260">在 [**儀表板**] 頁面上，選取 [**網域**]，然後**管理網域**。</span><span class="sxs-lookup"><span data-stu-id="40bb9-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="40bb9-262">在 [**管理網域**] 頁面上的 [**網域**] 區段中，選取您要編輯之網域的 [ **DNS** ]。</span><span class="sxs-lookup"><span data-stu-id="40bb9-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="40bb9-264">在 [新增**自訂 DNS 記錄**] 區段的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="40bb9-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="40bb9-265">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="40bb9-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="40bb9-266">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="40bb9-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="40bb9-267">**名稱**</span><span class="sxs-lookup"><span data-stu-id="40bb9-267">**Name**</span></span>|<span data-ttu-id="40bb9-268">**Type**</span><span class="sxs-lookup"><span data-stu-id="40bb9-268">**Type**</span></span>|<span data-ttu-id="40bb9-269">**Value**</span><span class="sxs-lookup"><span data-stu-id="40bb9-269">**Value**</span></span>|<span data-ttu-id="40bb9-270">**Comment**</span><span class="sxs-lookup"><span data-stu-id="40bb9-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="40bb9-271">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="40bb9-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="40bb9-272">SRV</span><span class="sxs-lookup"><span data-stu-id="40bb9-272">SRV</span></span>  <br/> |<span data-ttu-id="40bb9-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="40bb9-273">100 1 443</span></span>  <br/> <span data-ttu-id="40bb9-274">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="40bb9-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="40bb9-275">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="40bb9-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="40bb9-276">（此欄位是選用的。）</span><span class="sxs-lookup"><span data-stu-id="40bb9-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="40bb9-277">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="40bb9-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="40bb9-278">SRV</span><span class="sxs-lookup"><span data-stu-id="40bb9-278">SRV</span></span>  <br/> |<span data-ttu-id="40bb9-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="40bb9-279">100 1 5061</span></span>  <br/> <span data-ttu-id="40bb9-280">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="40bb9-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="40bb9-281">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="40bb9-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="40bb9-282">（此欄位是選用的。）</span><span class="sxs-lookup"><span data-stu-id="40bb9-282">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-Configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="40bb9-284">選取 [**立即加入記錄！**]。</span><span class="sxs-lookup"><span data-stu-id="40bb9-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="40bb9-286">使用前面的兩個步驟和表格中第二列的值，新增其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="40bb9-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="40bb9-p114">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="40bb9-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
