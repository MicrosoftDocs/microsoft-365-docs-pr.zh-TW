---
title: 在 Dreamhost 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Dreamhost。
ms.openlocfilehash: 2faf7cae1fd9a0f9308e303c0588958e56b223e1
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658120"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a><span data-ttu-id="4fdbf-103">在 Dreamhost 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="4fdbf-103">Create DNS records at Dreamhost for Microsoft</span></span>

 <span data-ttu-id="4fdbf-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4fdbf-105">如果 DreamHost 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、Lync 等等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="4fdbf-106">在 DreamHost 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-106">After you add these records at DreamHost, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="4fdbf-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4fdbf-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="4fdbf-110">Add a TXT record for verification</span></span>
<span data-ttu-id="4fdbf-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4fdbf-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4fdbf-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4fdbf-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4fdbf-116">若要開始使用，請移至您的網域頁面 DreamHost，方法是使用 [此連結](https://panel.dreamhost.com/)。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-116">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="4fdbf-117">系統會提示您登入。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-117">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="4fdbf-119">在 [ **儀表板** ] 頁面上，選取 [ **網域**]，然後 **管理網域**。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-119">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="4fdbf-121">在 [ **管理網域** ] 頁面上的 [ **網域** ] 區段中，選取您要編輯之網域的 [ **DNS** ]。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-121">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="4fdbf-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4fdbf-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4fdbf-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="4fdbf-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="4fdbf-125">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="4fdbf-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4fdbf-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-126">**Name**</span></span>|<span data-ttu-id="4fdbf-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-127">**Type**</span></span>|<span data-ttu-id="4fdbf-128">**Value**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-128">**Value**</span></span>|<span data-ttu-id="4fdbf-129">**Comment**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-129">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4fdbf-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="4fdbf-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4fdbf-131">TXT</span><span class="sxs-lookup"><span data-stu-id="4fdbf-131">TXT</span></span>  <br/> |<span data-ttu-id="4fdbf-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4fdbf-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4fdbf-133">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-133">**Note:** This is an example.</span></span> <span data-ttu-id="4fdbf-134">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="4fdbf-135">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="4fdbf-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="4fdbf-136"> (此欄位是選用的。 ) </span><span class="sxs-lookup"><span data-stu-id="4fdbf-136">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="4fdbf-138">選取 [**立即加入記錄！** ]</span><span class="sxs-lookup"><span data-stu-id="4fdbf-138">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="4fdbf-140">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4fdbf-141">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="4fdbf-142">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4fdbf-143">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4fdbf-144">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4fdbf-145">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="4fdbf-146">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="4fdbf-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="4fdbf-150">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="4fdbf-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="4fdbf-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4fdbf-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="4fdbf-152">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-152">Follow the steps below.</span></span>
  
1. <span data-ttu-id="4fdbf-153">若要開始使用，請移至您的網域頁面 DreamHost，方法是使用 [此連結](https://panel.dreamhost.com/)。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-153">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="4fdbf-154">系統會提示您登入。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-154">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="4fdbf-156">在 [ **儀表板** ] 頁面上，選取 [ **郵件**]，然後選取 [ **自訂 MX**]。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-156">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="4fdbf-158">在 [ **管理郵件傳遞** ] 區段的 [ **動作** ] 欄中，針對您要編輯的網域，選取 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-158">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="4fdbf-160">在 [ **自訂 MX 記錄** ] 區段的新記錄方塊中，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-160">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="4fdbf-161">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="4fdbf-161">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="4fdbf-162"> (如果有任何其他現有的 MX 記錄，請將這些記錄標示為待刪除。 ) </span><span class="sxs-lookup"><span data-stu-id="4fdbf-162">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="4fdbf-163">**(必要的 MX 記錄)**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-163">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="4fdbf-164">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="4fdbf-164">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="4fdbf-165">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="4fdbf-p108">0 是指 MX 優先順序值。請將它新增到 MX 值的開頭，並以空格分隔該值的其餘部分。  </span><span class="sxs-lookup"><span data-stu-id="4fdbf-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="4fdbf-168">\**附注：\*\*\*\<domain-key\>* 從您的 Microsoft 帳戶取得。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="4fdbf-169">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="4fdbf-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-BP-Configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="4fdbf-171">選取 [**變更這個網域立即使用自訂的 MX 記錄！** ]</span><span class="sxs-lookup"><span data-stu-id="4fdbf-171">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="4fdbf-173">如果有任何其他現有的 MX 記錄，請選取該專案，然後按下鍵盤上的 **delete** 鍵，以刪除每一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-173">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="4fdbf-175">如果您已刪除任何記錄，請選取 [**立即更新您的自訂 MX 記錄！** ]。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-175">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="4fdbf-177">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="4fdbf-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="4fdbf-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4fdbf-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="4fdbf-179">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-179">Follow the steps below.</span></span>
  
1. <span data-ttu-id="4fdbf-180">若要開始使用，請移至您的網域頁面 DreamHost，方法是使用 [此連結](https://panel.dreamhost.com/)。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-180">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="4fdbf-181">系統會提示您登入。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-181">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="4fdbf-183">在 [ **儀表板** ] 頁面上，選取 [ **網域**]，然後 **管理網域**。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-183">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="4fdbf-185">在 [ **管理網域** ] 頁面上的 [ **網域** ] 區段中，選取您要編輯之網域的 [ **DNS** ]。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-185">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="4fdbf-187">在 [新增 **自訂 DNS 記錄** ] 區段的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-187">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="4fdbf-188">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="4fdbf-188">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="4fdbf-189">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="4fdbf-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4fdbf-190">**Name**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-190">**Name**</span></span>|<span data-ttu-id="4fdbf-191">**Type**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-191">**Type**</span></span>|<span data-ttu-id="4fdbf-192">**Value**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-192">**Value**</span></span>|<span data-ttu-id="4fdbf-193">**Comment**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-193">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4fdbf-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4fdbf-194">autodiscover</span></span>  <br/> |<span data-ttu-id="4fdbf-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="4fdbf-195">CNAME</span></span>  <br/> |<span data-ttu-id="4fdbf-196">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="4fdbf-196">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="4fdbf-197">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4fdbf-198"> (此欄位是選用的。 ) </span><span class="sxs-lookup"><span data-stu-id="4fdbf-198">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="4fdbf-199">sip</span><span class="sxs-lookup"><span data-stu-id="4fdbf-199">sip</span></span>  <br/> |<span data-ttu-id="4fdbf-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="4fdbf-200">CNAME</span></span>  <br/> |<span data-ttu-id="4fdbf-201">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4fdbf-201">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="4fdbf-202">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4fdbf-203"> (此欄位是選用的。 ) </span><span class="sxs-lookup"><span data-stu-id="4fdbf-203">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="4fdbf-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4fdbf-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4fdbf-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="4fdbf-205">CNAME</span></span>  <br/> |<span data-ttu-id="4fdbf-206">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4fdbf-206">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="4fdbf-207">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4fdbf-208"> (此欄位是選用的。 ) </span><span class="sxs-lookup"><span data-stu-id="4fdbf-208">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="4fdbf-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4fdbf-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4fdbf-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="4fdbf-210">CNAME</span></span>  <br/> |<span data-ttu-id="4fdbf-211">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="4fdbf-211">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="4fdbf-212">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4fdbf-213"> (此欄位是選用的。 ) </span><span class="sxs-lookup"><span data-stu-id="4fdbf-213">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="4fdbf-214">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4fdbf-214">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4fdbf-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="4fdbf-215">CNAME</span></span>  <br/> |<span data-ttu-id="4fdbf-216">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4fdbf-216">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="4fdbf-217">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-217">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4fdbf-218"> (此欄位是選用的。 ) </span><span class="sxs-lookup"><span data-stu-id="4fdbf-218">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-Configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="4fdbf-220">選取 [**立即加入記錄！** ]</span><span class="sxs-lookup"><span data-stu-id="4fdbf-220">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="4fdbf-222">使用前兩個步驟和表格中其他五列的值，新增其餘五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-222">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4fdbf-223">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="4fdbf-223">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4fdbf-224"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4fdbf-224"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4fdbf-225">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-225">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4fdbf-226">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-226">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4fdbf-227">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-227">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="4fdbf-228">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-228">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="4fdbf-229">請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-229">Follow the steps below.</span></span>
  
1. <span data-ttu-id="4fdbf-230">若要開始使用，請移至您的網域頁面 DreamHost，方法是使用 [此連結](https://panel.dreamhost.com/)。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-230">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="4fdbf-231">系統會提示您登入。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-231">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="4fdbf-233">在 [ **儀表板** ] 頁面上，選取 [ **網域**]，然後 **管理網域**。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-233">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="4fdbf-235">在 [ **管理網域** ] 頁面上的 [ **網域** ] 區段中，選取您要編輯之網域的 [ **DNS** ]。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-235">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="4fdbf-237">在 [新增 **自訂 DNS 記錄** ] 區段的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-237">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="4fdbf-238">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="4fdbf-238">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="4fdbf-239">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="4fdbf-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4fdbf-240">**Name**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-240">**Name**</span></span>|<span data-ttu-id="4fdbf-241">**Type**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-241">**Type**</span></span>|<span data-ttu-id="4fdbf-242">**Value**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-242">**Value**</span></span>|<span data-ttu-id="4fdbf-243">**Comment**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-243">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4fdbf-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="4fdbf-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4fdbf-245">TXT</span><span class="sxs-lookup"><span data-stu-id="4fdbf-245">TXT</span></span>  <br/> |<span data-ttu-id="4fdbf-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4fdbf-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4fdbf-247">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="4fdbf-248"> (此欄位是選用的。 ) </span><span class="sxs-lookup"><span data-stu-id="4fdbf-248">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-BP-Configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="4fdbf-250">選取 [**立即加入記錄！** ]</span><span class="sxs-lookup"><span data-stu-id="4fdbf-250">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="4fdbf-252">使用前面的兩個步驟和表格中第二列的值，新增其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-252">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="4fdbf-253">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="4fdbf-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="4fdbf-254"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4fdbf-254"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="4fdbf-255">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="4fdbf-256">若要開始使用，請移至您的網域頁面 DreamHost，方法是使用 [此連結](https://panel.dreamhost.com/)。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-256">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="4fdbf-257">系統會提示您登入。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-257">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="4fdbf-259">在 [ **儀表板** ] 頁面上，選取 [ **網域**]，然後 **管理網域**。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-259">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="4fdbf-261">在 [ **管理網域** ] 頁面上的 [ **網域** ] 區段中，選取您要編輯之網域的 [ **DNS** ]。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-261">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="4fdbf-263">在 [新增 **自訂 DNS 記錄** ] 區段的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-263">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="4fdbf-264">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="4fdbf-264">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="4fdbf-265">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="4fdbf-265">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4fdbf-266">**Name**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-266">**Name**</span></span>|<span data-ttu-id="4fdbf-267">**Type**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-267">**Type**</span></span>|<span data-ttu-id="4fdbf-268">**Value**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-268">**Value**</span></span>|<span data-ttu-id="4fdbf-269">**Comment**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-269">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4fdbf-270">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="4fdbf-270">_sip._tls</span></span>  <br/> |<span data-ttu-id="4fdbf-271">SRV</span><span class="sxs-lookup"><span data-stu-id="4fdbf-271">SRV</span></span>  <br/> |<span data-ttu-id="4fdbf-272">100 1 443</span><span class="sxs-lookup"><span data-stu-id="4fdbf-272">100 1 443</span></span>  <br/> <span data-ttu-id="4fdbf-273">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4fdbf-273">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="4fdbf-274">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-274">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4fdbf-275"> (此欄位是選用的。 ) </span><span class="sxs-lookup"><span data-stu-id="4fdbf-275">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="4fdbf-276">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="4fdbf-276">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="4fdbf-277">SRV</span><span class="sxs-lookup"><span data-stu-id="4fdbf-277">SRV</span></span>  <br/> |<span data-ttu-id="4fdbf-278">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="4fdbf-278">100 1 5061</span></span>  <br/> <span data-ttu-id="4fdbf-279">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-279">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="4fdbf-280">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="4fdbf-280">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="4fdbf-281"> (此欄位是選用的。 ) </span><span class="sxs-lookup"><span data-stu-id="4fdbf-281">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-BP-Configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="4fdbf-283">選取 [ **立即加入記錄！**]。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-283">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="4fdbf-285">使用前面的兩個步驟和表格中第二列的值，新增其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-285">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="4fdbf-p114">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4fdbf-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
