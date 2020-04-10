---
title: 在 Hover 建立 Office 365 的 DNS 記錄
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以便在 Office 365 上懸停。
ms.openlocfilehash: 7884038dcd1ebc7b13bbed44d98f0d5172015cc1
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211700"
---
# <a name="create-dns-records-at-hover-for-office-365"></a><span data-ttu-id="dca40-103">在 Hover 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="dca40-103">Create DNS records at Hover for Office 365</span></span>

 <span data-ttu-id="dca40-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="dca40-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="dca40-105">如果 Hover 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="dca40-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="dca40-106">在 Hover 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="dca40-106">After you add these records at Hover, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="dca40-107">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="dca40-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="dca40-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dca40-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="dca40-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="dca40-111">Add a TXT record for verification</span></span>
<span data-ttu-id="dca40-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="dca40-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="dca40-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="dca40-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dca40-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="dca40-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="dca40-117">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="dca40-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="dca40-p104">首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dca40-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登入](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="dca40-121">在 [**管理您的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="dca40-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![選取網域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="dca40-123">選取 [ **DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dca40-123">Select the **DNS** tab.</span></span> 
    
    ![選取 [DNS] 索引標籤](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="dca40-125">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dca40-125">Select **Add New**.</span></span>
    
    ![選取 [新增]](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="dca40-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="dca40-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="dca40-128">主機名稱</span><span class="sxs-lookup"><span data-stu-id="dca40-128">Hostname</span></span>  <br/> |<span data-ttu-id="dca40-129">記錄類型</span><span class="sxs-lookup"><span data-stu-id="dca40-129">Record Type</span></span>  <br/> |<span data-ttu-id="dca40-130">值</span><span class="sxs-lookup"><span data-stu-id="dca40-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="dca40-131">TXT</span><span class="sxs-lookup"><span data-stu-id="dca40-131">TXT</span></span>  <br/> |<span data-ttu-id="dca40-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="dca40-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="dca40-133">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="dca40-133">**Note:** This is an example.</span></span> <span data-ttu-id="dca40-134">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="dca40-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="dca40-135">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="dca40-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![輸入或複製並貼上 DNS 值](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="dca40-137">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="dca40-137">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="dca40-139">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="dca40-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="dca40-140">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="dca40-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="dca40-141">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="dca40-141">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="dca40-142">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="dca40-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="dca40-143">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="dca40-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="dca40-144">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="dca40-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="dca40-145">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="dca40-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="dca40-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dca40-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="dca40-149">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="dca40-149">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="dca40-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="dca40-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="dca40-151">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="dca40-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="dca40-p107">首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dca40-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登入](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="dca40-155">在 [**管理您的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="dca40-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![選取網域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="dca40-157">選取 [ **DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dca40-157">Select the **DNS** tab.</span></span> 
    
    ![選取 [DNS] 索引標籤](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="dca40-159">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dca40-159">Select **Add New**.</span></span>
    
    ![選取 [新增]](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="dca40-161">在新記錄的方塊中，針對**記錄類型**選取 [ **MX** ]，然後輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="dca40-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="dca40-162">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="dca40-162">**Hostname**</span></span>|<span data-ttu-id="dca40-163">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="dca40-163">**Record Type**</span></span>|<span data-ttu-id="dca40-164">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="dca40-164">**Priority**</span></span>|<span data-ttu-id="dca40-165">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="dca40-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="dca40-166">MX</span><span class="sxs-lookup"><span data-stu-id="dca40-166">MX</span></span>  <br/> |<span data-ttu-id="dca40-167">0</span><span class="sxs-lookup"><span data-stu-id="dca40-167">0</span></span>  <br/> <span data-ttu-id="dca40-168">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="dca40-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="dca40-169">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dca40-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="dca40-170">**附注：** 從您的 Office 365 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="dca40-170">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="dca40-171">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="dca40-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![輸入或複製並貼上 DNS 值](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="dca40-173">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="dca40-173">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="dca40-175">如果有任何其他 MX 記錄，請使用下列兩個步驟的處理程序來逐一移除：</span><span class="sxs-lookup"><span data-stu-id="dca40-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="dca40-176">首先，上方您要移除的記錄，然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="dca40-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![滑鼠移過並選取 [刪除]](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="dca40-178">其次，選取 **[是]** 以確認每個刪除。</span><span class="sxs-lookup"><span data-stu-id="dca40-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![選取 [是] 以確認刪除](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="dca40-180">重複本處理程序，直到您已刪除所有 MX 記錄為止 (除了您稍早在本程序中新增的那一筆記錄以外)。</span><span class="sxs-lookup"><span data-stu-id="dca40-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="dca40-181">新增 Office 365 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="dca40-181">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="dca40-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="dca40-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="dca40-183">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="dca40-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="dca40-p109">首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dca40-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登入](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="dca40-187">在 [**管理您的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="dca40-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![選取網域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="dca40-189">選取 [ **DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dca40-189">Select the **DNS** tab.</span></span> 
    
    ![選取 [DNS] 索引標籤](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="dca40-191">新增六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="dca40-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="dca40-192">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dca40-192">Select **Add New**.</span></span>
    
    ![選取 [新增]](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="dca40-194">在新記錄的空白方塊中，針對**記錄類型**選取 [ **CNAME** ]，然後輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="dca40-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="dca40-195">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="dca40-195">**Hostname**</span></span>|<span data-ttu-id="dca40-196">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="dca40-196">**Record Type**</span></span>|<span data-ttu-id="dca40-197">**Target Host (目標主機)**</span><span class="sxs-lookup"><span data-stu-id="dca40-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="dca40-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="dca40-198">autodiscover</span></span>  <br/> |<span data-ttu-id="dca40-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="dca40-199">CNAME</span></span>  <br/> |<span data-ttu-id="dca40-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dca40-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="dca40-201">sip</span><span class="sxs-lookup"><span data-stu-id="dca40-201">sip</span></span>  <br/> |<span data-ttu-id="dca40-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="dca40-202">CNAME</span></span>  <br/> |<span data-ttu-id="dca40-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dca40-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="dca40-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="dca40-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="dca40-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="dca40-205">CNAME</span></span>  <br/> |<span data-ttu-id="dca40-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dca40-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="dca40-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="dca40-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="dca40-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="dca40-208">CNAME</span></span>  <br/> |<span data-ttu-id="dca40-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="dca40-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="dca40-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="dca40-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="dca40-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="dca40-211">CNAME</span></span>  <br/> |<span data-ttu-id="dca40-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dca40-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![輸入或複製並貼上 DNS 值](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="dca40-214">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="dca40-214">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="dca40-216">按照前三個步驟分別將表格中其他五列的值新增至其他五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="dca40-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="dca40-217">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="dca40-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="dca40-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="dca40-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="dca40-219">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="dca40-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="dca40-220">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="dca40-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="dca40-221">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="dca40-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="dca40-222">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="dca40-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="dca40-223">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="dca40-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="dca40-p111">首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dca40-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登入](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="dca40-227">在 [**管理您的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="dca40-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![選取網域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="dca40-229">選取 [ **DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dca40-229">Select the **DNS** tab.</span></span> 
    
    ![選取 [DNS] 索引標籤](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="dca40-231">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dca40-231">Select **Add New**.</span></span>
    
    ![選取 [新增]](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="dca40-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="dca40-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="dca40-234">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="dca40-234">**Hostname**</span></span>|<span data-ttu-id="dca40-235">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="dca40-235">**Record Type**</span></span>|<span data-ttu-id="dca40-236">**值**</span><span class="sxs-lookup"><span data-stu-id="dca40-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="dca40-237">TXT</span><span class="sxs-lookup"><span data-stu-id="dca40-237">TXT</span></span>  <br/> |<span data-ttu-id="dca40-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="dca40-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="dca40-239">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="dca40-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![輸入或複製並貼上 DNS 值](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="dca40-241">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="dca40-241">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="dca40-243">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="dca40-243">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="dca40-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="dca40-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="dca40-245">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="dca40-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="dca40-p112">首先請用[這個連結](https://www.hover.com/domains)移至 Hover 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dca40-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登入](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="dca40-249">在 [**管理您的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="dca40-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![選取網域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="dca40-251">選取 [ **DNS** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dca40-251">Select the **DNS** tab.</span></span> 
    
    ![選取 [DNS] 索引標籤](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="dca40-253">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="dca40-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="dca40-254">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dca40-254">Select **Add New**.</span></span>
    
    ![選取 [新增]](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="dca40-256">在新記錄的空白方塊中，為**記錄類型**選取 [ **SRV** ]，然後輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="dca40-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="dca40-257">**主機 名**</span><span class="sxs-lookup"><span data-stu-id="dca40-257">**Hostname**</span></span>|<span data-ttu-id="dca40-258">**Record Type** (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="dca40-258">**Record Type**</span></span>|<span data-ttu-id="dca40-259">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="dca40-259">**Priority**</span></span>|<span data-ttu-id="dca40-260">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="dca40-260">**Weight**</span></span>|<span data-ttu-id="dca40-261">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="dca40-261">**Port**</span></span>|<span data-ttu-id="dca40-262">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="dca40-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dca40-263">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="dca40-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="dca40-264">SRV</span><span class="sxs-lookup"><span data-stu-id="dca40-264">SRV</span></span>  <br/> |<span data-ttu-id="dca40-265">100</span><span class="sxs-lookup"><span data-stu-id="dca40-265">100</span></span>  <br/> |<span data-ttu-id="dca40-266">1 </span><span class="sxs-lookup"><span data-stu-id="dca40-266">1</span></span>  <br/> |<span data-ttu-id="dca40-267">443</span><span class="sxs-lookup"><span data-stu-id="dca40-267">443</span></span>  <br/> |<span data-ttu-id="dca40-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dca40-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="dca40-269">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="dca40-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="dca40-270">SRV</span><span class="sxs-lookup"><span data-stu-id="dca40-270">SRV</span></span>  <br/> |<span data-ttu-id="dca40-271">100</span><span class="sxs-lookup"><span data-stu-id="dca40-271">100</span></span>  <br/> |<span data-ttu-id="dca40-272">1 </span><span class="sxs-lookup"><span data-stu-id="dca40-272">1</span></span>  <br/> |<span data-ttu-id="dca40-273">5061</span><span class="sxs-lookup"><span data-stu-id="dca40-273">5061</span></span>  <br/> |<span data-ttu-id="dca40-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dca40-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![輸入或複製並貼上 DNS 值](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="dca40-276">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="dca40-276">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="dca40-278">使用前三個步驟和表格中第二列的值，新增其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="dca40-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dca40-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dca40-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
