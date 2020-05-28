---
title: 在 Microsoft 的懸停時建立 DNS 記錄
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以在 Microsoft 上懸停。
ms.openlocfilehash: 74662f37c3f72f02767f2434d9b251e3bd37ff1b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400422"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="ea15b-103">在 Microsoft 的懸停時建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="ea15b-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="ea15b-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="ea15b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ea15b-105">如果 Hover 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="ea15b-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="ea15b-106">在懸停新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ea15b-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="ea15b-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="ea15b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ea15b-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="ea15b-110">Add a TXT record for verification</span></span>
<span data-ttu-id="ea15b-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ea15b-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ea15b-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="ea15b-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ea15b-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="ea15b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="ea15b-116">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="ea15b-116">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ea15b-p104">首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="ea15b-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登入](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="ea15b-120">在 [**管理您的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="ea15b-120">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![選取網域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="ea15b-122">選取 [ **DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ea15b-122">Select the **DNS** tab.</span></span> 
    
    ![選取 [DNS] 索引標籤](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="ea15b-124">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ea15b-124">Select **Add New**.</span></span>
    
    ![選取 [新增]](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="ea15b-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ea15b-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="ea15b-127">主機名稱</span><span class="sxs-lookup"><span data-stu-id="ea15b-127">Hostname</span></span>  <br/> |<span data-ttu-id="ea15b-128">記錄類型</span><span class="sxs-lookup"><span data-stu-id="ea15b-128">Record Type</span></span>  <br/> |<span data-ttu-id="ea15b-129">值</span><span class="sxs-lookup"><span data-stu-id="ea15b-129">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="ea15b-130">TXT</span><span class="sxs-lookup"><span data-stu-id="ea15b-130">TXT</span></span>  <br/> |<span data-ttu-id="ea15b-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ea15b-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ea15b-132">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="ea15b-132">**Note:** This is an example.</span></span> <span data-ttu-id="ea15b-133">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="ea15b-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="ea15b-134">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="ea15b-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![輸入或複製並貼上 DNS 值](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="ea15b-136">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ea15b-136">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="ea15b-138">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="ea15b-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ea15b-139">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 365 並要求 Microsoft 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="ea15b-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="ea15b-140">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="ea15b-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ea15b-141">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ea15b-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ea15b-142">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="ea15b-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ea15b-143">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="ea15b-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ea15b-144">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="ea15b-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ea15b-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="ea15b-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ea15b-148">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="ea15b-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ea15b-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ea15b-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="ea15b-150">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="ea15b-150">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ea15b-p107">首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="ea15b-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登入](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="ea15b-154">在 [**管理您的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="ea15b-154">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![選取網域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="ea15b-156">選取 [ **DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ea15b-156">Select the **DNS** tab.</span></span> 
    
    ![選取 [DNS] 索引標籤](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="ea15b-158">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ea15b-158">Select **Add New**.</span></span>
    
    ![選取 [新增]](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="ea15b-160">在新記錄的方塊中，針對**記錄類型**選取 [ **MX** ]，然後輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="ea15b-160">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="ea15b-161">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="ea15b-161">**Hostname**</span></span>|<span data-ttu-id="ea15b-162">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="ea15b-162">**Record Type**</span></span>|<span data-ttu-id="ea15b-163">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="ea15b-163">**Priority**</span></span>|<span data-ttu-id="ea15b-164">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="ea15b-164">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="ea15b-165">MX</span><span class="sxs-lookup"><span data-stu-id="ea15b-165">MX</span></span>  <br/> |<span data-ttu-id="ea15b-166">0</span><span class="sxs-lookup"><span data-stu-id="ea15b-166">0</span></span>  <br/> <span data-ttu-id="ea15b-167">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="ea15b-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="ea15b-168">*\<domain-key\>*。 mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ea15b-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="ea15b-169">\**附注：\*\*\*\<domain-key\>* 從您的 Microsoft 帳戶取得。</span><span class="sxs-lookup"><span data-stu-id="ea15b-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="ea15b-170">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="ea15b-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![輸入或複製並貼上 DNS 值](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="ea15b-172">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ea15b-172">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="ea15b-174">如果有任何其他 MX 記錄，請使用下列兩個步驟的處理程序來逐一移除：</span><span class="sxs-lookup"><span data-stu-id="ea15b-174">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="ea15b-175">首先，上方您要移除的記錄，然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="ea15b-175">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![滑鼠移過並選取 [刪除]](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="ea15b-177">其次，選取 **[是]** 以確認每個刪除。</span><span class="sxs-lookup"><span data-stu-id="ea15b-177">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![選取 [是] 以確認刪除](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="ea15b-179">重複本處理程序，直到您已刪除所有 MX 記錄為止 (除了您稍早在本程序中新增的那一筆記錄以外)。</span><span class="sxs-lookup"><span data-stu-id="ea15b-179">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ea15b-180">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="ea15b-180">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ea15b-181"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ea15b-181"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="ea15b-182">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="ea15b-182">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ea15b-p109">首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="ea15b-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登入](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="ea15b-186">在 [**管理您的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="ea15b-186">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![選取網域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="ea15b-188">選取 [ **DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ea15b-188">Select the **DNS** tab.</span></span> 
    
    ![選取 [DNS] 索引標籤](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="ea15b-190">新增六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="ea15b-190">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="ea15b-191">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ea15b-191">Select **Add New**.</span></span>
    
    ![選取 [新增]](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="ea15b-193">在新記錄的空白方塊中，針對**記錄類型**選取 [ **CNAME** ]，然後輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="ea15b-193">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="ea15b-194">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="ea15b-194">**Hostname**</span></span>|<span data-ttu-id="ea15b-195">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="ea15b-195">**Record Type**</span></span>|<span data-ttu-id="ea15b-196">**Target Host (目標主機)**</span><span class="sxs-lookup"><span data-stu-id="ea15b-196">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ea15b-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ea15b-197">autodiscover</span></span>  <br/> |<span data-ttu-id="ea15b-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="ea15b-198">CNAME</span></span>  <br/> |<span data-ttu-id="ea15b-199">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ea15b-199">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="ea15b-200">sip</span><span class="sxs-lookup"><span data-stu-id="ea15b-200">sip</span></span>  <br/> |<span data-ttu-id="ea15b-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="ea15b-201">CNAME</span></span>  <br/> |<span data-ttu-id="ea15b-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ea15b-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ea15b-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ea15b-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ea15b-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="ea15b-204">CNAME</span></span>  <br/> |<span data-ttu-id="ea15b-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ea15b-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ea15b-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ea15b-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ea15b-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="ea15b-207">CNAME</span></span>  <br/> |<span data-ttu-id="ea15b-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ea15b-208">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="ea15b-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ea15b-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ea15b-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="ea15b-210">CNAME</span></span>  <br/> |<span data-ttu-id="ea15b-211">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ea15b-211">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![輸入或複製並貼上 DNS 值](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="ea15b-213">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ea15b-213">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="ea15b-215">按照前三個步驟分別將表格中其他五列的值新增至其他五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="ea15b-215">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ea15b-216">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="ea15b-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ea15b-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ea15b-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea15b-218">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="ea15b-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ea15b-219">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="ea15b-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ea15b-220">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="ea15b-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ea15b-221">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="ea15b-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="ea15b-222">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="ea15b-222">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ea15b-p111">首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="ea15b-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登入](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="ea15b-226">在 [**管理您的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="ea15b-226">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![選取網域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="ea15b-228">選取 [ **DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ea15b-228">Select the **DNS** tab.</span></span> 
    
    ![選取 [DNS] 索引標籤](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="ea15b-230">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ea15b-230">Select **Add New**.</span></span>
    
    ![選取 [新增]](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="ea15b-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ea15b-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="ea15b-233">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="ea15b-233">**Hostname**</span></span>|<span data-ttu-id="ea15b-234">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="ea15b-234">**Record Type**</span></span>|<span data-ttu-id="ea15b-235">**值**</span><span class="sxs-lookup"><span data-stu-id="ea15b-235">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="ea15b-236">TXT</span><span class="sxs-lookup"><span data-stu-id="ea15b-236">TXT</span></span>  <br/> |<span data-ttu-id="ea15b-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ea15b-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="ea15b-238">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="ea15b-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![輸入或複製並貼上 DNS 值](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="ea15b-240">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ea15b-240">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ea15b-242">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="ea15b-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ea15b-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ea15b-243"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="ea15b-244">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="ea15b-244">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ea15b-p112">首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="ea15b-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登入](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="ea15b-248">在 [**管理您的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="ea15b-248">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![選取網域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="ea15b-250">選取 [ **DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ea15b-250">Select the **DNS** tab.</span></span> 
    
    ![選取 [DNS] 索引標籤](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="ea15b-252">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="ea15b-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="ea15b-253">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ea15b-253">Select **Add New**.</span></span>
    
    ![選取 [新增]](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="ea15b-255">在新記錄的空白方塊中，為**記錄類型**選取 [ **SRV** ]，然後輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="ea15b-255">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="ea15b-256">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="ea15b-256">**Hostname**</span></span>|<span data-ttu-id="ea15b-257">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="ea15b-257">**Record Type**</span></span>|<span data-ttu-id="ea15b-258">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="ea15b-258">**Priority**</span></span>|<span data-ttu-id="ea15b-259">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="ea15b-259">**Weight**</span></span>|<span data-ttu-id="ea15b-260">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="ea15b-260">**Port**</span></span>|<span data-ttu-id="ea15b-261">**Target**</span><span class="sxs-lookup"><span data-stu-id="ea15b-261">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ea15b-262">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="ea15b-262">_sip._tls</span></span>  <br/> |<span data-ttu-id="ea15b-263">SRV</span><span class="sxs-lookup"><span data-stu-id="ea15b-263">SRV</span></span>  <br/> |<span data-ttu-id="ea15b-264">100</span><span class="sxs-lookup"><span data-stu-id="ea15b-264">100</span></span>  <br/> |<span data-ttu-id="ea15b-265">1 </span><span class="sxs-lookup"><span data-stu-id="ea15b-265">1</span></span>  <br/> |<span data-ttu-id="ea15b-266">443</span><span class="sxs-lookup"><span data-stu-id="ea15b-266">443</span></span>  <br/> |<span data-ttu-id="ea15b-267">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ea15b-267">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ea15b-268">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="ea15b-268">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="ea15b-269">SRV</span><span class="sxs-lookup"><span data-stu-id="ea15b-269">SRV</span></span>  <br/> |<span data-ttu-id="ea15b-270">100</span><span class="sxs-lookup"><span data-stu-id="ea15b-270">100</span></span>  <br/> |<span data-ttu-id="ea15b-271">1 </span><span class="sxs-lookup"><span data-stu-id="ea15b-271">1</span></span>  <br/> |<span data-ttu-id="ea15b-272">5061</span><span class="sxs-lookup"><span data-stu-id="ea15b-272">5061</span></span>  <br/> |<span data-ttu-id="ea15b-273">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ea15b-273">sipfed.online.lync.com</span></span>  <br/> |
   
    ![輸入或複製並貼上 DNS 值](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="ea15b-275">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ea15b-275">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="ea15b-277">使用前三個步驟和表格中第二列的值，新增其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="ea15b-277">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ea15b-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="ea15b-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
