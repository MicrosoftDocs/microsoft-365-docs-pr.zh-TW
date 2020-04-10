---
title: 在 Network Solutions 建立 Office 365 的DNS 記錄
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以用於 Office 365 的網路解決方案。
ms.openlocfilehash: 6bbe954f763e0cb06e9bf32b991e60da34393c57
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211119"
---
# <a name="create-dns-records-at-network-solutions-for-office-365"></a><span data-ttu-id="75152-103">在 Network Solutions 建立 Office 365 的DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="75152-103">Create DNS records at Network Solutions for Office 365</span></span>

 <span data-ttu-id="75152-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="75152-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="75152-105">如果 Network Solutions 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="75152-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="75152-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="75152-106">These are the main records to add.</span></span> <span data-ttu-id="75152-107">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="75152-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="75152-108">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="75152-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="75152-109">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="75152-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="75152-110">新增 Office 365 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="75152-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="75152-111">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="75152-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="75152-112">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="75152-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="75152-113">在 Network Solutions 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="75152-113">After you add these records at Network Solutions, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="75152-114">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="75152-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="75152-p102">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="75152-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="75152-118">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="75152-118">Add a TXT record for verification</span></span>
<span data-ttu-id="75152-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="75152-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="75152-p103">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="75152-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="75152-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="75152-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="75152-124">請依照下列步驟操作或[觀看影片 (從 0:47 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="75152-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="75152-125">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="75152-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="75152-126">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="75152-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="75152-127">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="75152-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="75152-129">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="75152-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="75152-131">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="75152-131">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="75152-133">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="75152-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="75152-134">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="75152-134">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="75152-136">向下滾動至 [**文字（TXT 記錄）** ] 區段，然後選取 [**編輯 TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="75152-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![選取 [編輯 TXT 記錄]](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="75152-138">In the boxes for the new record, type or copy and paste the values in the following table.</span><span class="sxs-lookup"><span data-stu-id="75152-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="75152-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="75152-139">**Host**</span></span>|<span data-ttu-id="75152-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75152-140">**TTL**</span></span>|<span data-ttu-id="75152-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="75152-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="75152-142">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="75152-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="75152-143">3600</span><span class="sxs-lookup"><span data-stu-id="75152-143">3600</span></span>  <br/> |<span data-ttu-id="75152-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="75152-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="75152-145">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="75152-145">**Note:** This is an example.</span></span> <span data-ttu-id="75152-146">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="75152-146">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="75152-147">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="75152-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![在新記錄的方塊中輸入或貼上值](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="75152-149">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="75152-149">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="75152-151">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="75152-151">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="75152-153">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="75152-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="75152-154">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="75152-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="75152-155">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="75152-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="75152-156">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="75152-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="75152-157">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="75152-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="75152-158">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="75152-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="75152-159">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="75152-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="75152-p107">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="75152-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="75152-163">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="75152-163">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="75152-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="75152-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="75152-165">請依照下列步驟操作或[觀看影片 (從 3:51 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="75152-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="75152-166">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="75152-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="75152-167">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="75152-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="75152-168">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="75152-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="75152-170">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="75152-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="75152-172">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="75152-172">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="75152-174">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="75152-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="75152-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="75152-175">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="75152-177">向下滾動至 [**郵件伺服器（MX 記錄）** ] 區段，然後選取 [**編輯 MX 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="75152-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![選取 [編輯 MX 記錄]](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="75152-179">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="75152-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="75152-180">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="75152-180">**Priority**</span></span>|<span data-ttu-id="75152-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75152-181">**TTL**</span></span>|<span data-ttu-id="75152-182">**Mail server (郵件伺服器)**</span><span class="sxs-lookup"><span data-stu-id="75152-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="75152-183">10 </span><span class="sxs-lookup"><span data-stu-id="75152-183">10</span></span>  <br/> <span data-ttu-id="75152-184">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="75152-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="75152-185">3600</span><span class="sxs-lookup"><span data-stu-id="75152-185">3600</span></span>  <br/> | <span data-ttu-id="75152-186">*\<網域金鑰\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="75152-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="75152-187">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="75152-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="75152-188">**附注：** 從您的 Office 365 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="75152-188">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span> [<span data-ttu-id="75152-189">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="75152-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![在新記錄的方塊中輸入或貼上值](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="75152-191">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="75152-191">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="75152-193">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="75152-193">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="75152-195">如果有任何其他 MX 記錄，請選取每一筆記錄的 [**刪除**] 以刪除所有記錄。</span><span class="sxs-lookup"><span data-stu-id="75152-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="75152-197">選取所有選項時，請選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="75152-197">When they are all selected, select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="75152-199">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="75152-199">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="75152-201">新增 Office 365 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="75152-201">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="75152-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="75152-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="75152-203">請依照下列步驟操作或[觀看影片 (從 4:43 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="75152-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="75152-204">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="75152-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="75152-205">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="75152-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="75152-206">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="75152-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="75152-208">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="75152-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="75152-210">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="75152-210">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="75152-212">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="75152-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="75152-213">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="75152-213">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="75152-215">向下滾動至 [**主機別名（CNAME 記錄）** ] 區段，然後選取 [**編輯 CNAME 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="75152-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![選取 [主機別名] 底下的 [編輯 CNAME 記錄]](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="75152-217">在這四筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="75152-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="75152-218">**Alias**</span><span class="sxs-lookup"><span data-stu-id="75152-218">**Alias**</span></span>|<span data-ttu-id="75152-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75152-219">**TTL**</span></span>|<span data-ttu-id="75152-220">**參照的主機名稱**</span><span class="sxs-lookup"><span data-stu-id="75152-220">**Refers to Host Name**</span></span>|<span data-ttu-id="75152-221">**其他主機（選取 [**其他主機**] 選項按鈕）**</span><span class="sxs-lookup"><span data-stu-id="75152-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="75152-222">autodiscover (自動探索)</span><span class="sxs-lookup"><span data-stu-id="75152-222">autodiscover</span></span>  <br/> |<span data-ttu-id="75152-223">3600</span><span class="sxs-lookup"><span data-stu-id="75152-223">3600</span></span>  <br/> |<span data-ttu-id="75152-224">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="75152-224">(No setting)</span></span>  <br/> |<span data-ttu-id="75152-225">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="75152-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="75152-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="75152-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="75152-227">sip</span><span class="sxs-lookup"><span data-stu-id="75152-227">sip</span></span>  <br/> |<span data-ttu-id="75152-228">3600</span><span class="sxs-lookup"><span data-stu-id="75152-228">3600</span></span>  <br/> |<span data-ttu-id="75152-229">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="75152-229">(No setting)</span></span>  <br/> |<span data-ttu-id="75152-230">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="75152-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="75152-231">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="75152-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="75152-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="75152-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="75152-233">3600</span><span class="sxs-lookup"><span data-stu-id="75152-233">3600</span></span>  <br/> |<span data-ttu-id="75152-234">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="75152-234">(No setting)</span></span>  <br/> |<span data-ttu-id="75152-235">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="75152-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="75152-236">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="75152-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="75152-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="75152-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="75152-238">3600</span><span class="sxs-lookup"><span data-stu-id="75152-238">3600</span></span>  <br/> |<span data-ttu-id="75152-239">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="75152-239">(No setting)</span></span>  <br/> |<span data-ttu-id="75152-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="75152-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="75152-241">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="75152-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="75152-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="75152-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="75152-243">3600</span><span class="sxs-lookup"><span data-stu-id="75152-243">3600</span></span>  <br/> |<span data-ttu-id="75152-244">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="75152-244">(No setting)</span></span>  <br/> |<span data-ttu-id="75152-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="75152-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="75152-246">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="75152-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![輸入或貼上新記錄的值](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="75152-248">當您已新增所需的所有 CNAME 記錄後，請選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="75152-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="75152-250">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="75152-250">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="75152-252">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="75152-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="75152-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="75152-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="75152-254">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="75152-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="75152-255">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="75152-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="75152-256">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="75152-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="75152-257">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="75152-257">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="75152-258">請依照下列步驟操作或[觀看影片 (從 5:35 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="75152-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="75152-259">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="75152-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="75152-260">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="75152-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="75152-261">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="75152-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="75152-263">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="75152-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="75152-265">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="75152-265">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="75152-267">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="75152-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="75152-268">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="75152-268">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="75152-270">向下滾動至 [**文字（TXT 記錄）** ] 區段，然後選取 [**編輯 TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="75152-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![選取 [文字] 底下的 [編輯 TXT 記錄]](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="75152-272">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="75152-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="75152-273">**Host**</span><span class="sxs-lookup"><span data-stu-id="75152-273">**Host**</span></span>|<span data-ttu-id="75152-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75152-274">**TTL**</span></span>|<span data-ttu-id="75152-275">**Text**</span><span class="sxs-lookup"><span data-stu-id="75152-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="75152-276">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="75152-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="75152-277">3600</span><span class="sxs-lookup"><span data-stu-id="75152-277">3600</span></span>  <br/> |<span data-ttu-id="75152-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="75152-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="75152-279">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="75152-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![輸入或貼上新記錄的值](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="75152-281">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="75152-281">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="75152-283">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="75152-283">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="75152-285">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="75152-285">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="75152-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="75152-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="75152-287">請依照下列步驟操作或[觀看影片 (從 6:18 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="75152-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="75152-p113">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="75152-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="75152-290">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="75152-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="75152-292">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="75152-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="75152-294">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="75152-294">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="75152-296">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="75152-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="75152-297">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="75152-297">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="75152-299">向下滾動至 [**服務（SRV 記錄）** ] 區段，然後選取 [**編輯 SRV 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="75152-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![選取 [服務] 下的 [編輯 SRV 記錄]](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="75152-301">在這兩筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="75152-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="75152-302">（從下拉式清單中選擇 [**服務**] 和 [**通訊協定**] 值。）</span><span class="sxs-lookup"><span data-stu-id="75152-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="75152-303">**服務**</span><span class="sxs-lookup"><span data-stu-id="75152-303">**Service**</span></span>|<span data-ttu-id="75152-304">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="75152-304">**Protocol**</span></span>|<span data-ttu-id="75152-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75152-305">**TTL**</span></span>|<span data-ttu-id="75152-306">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="75152-306">**Priority**</span></span>|<span data-ttu-id="75152-307">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="75152-307">**Weight**</span></span>|<span data-ttu-id="75152-308">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="75152-308">**Port**</span></span>|<span data-ttu-id="75152-309">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="75152-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="75152-310">_sip</span><span class="sxs-lookup"><span data-stu-id="75152-310">_sip</span></span>  <br/> |<span data-ttu-id="75152-311">_tls</span><span class="sxs-lookup"><span data-stu-id="75152-311">_tls</span></span>  <br/> |<span data-ttu-id="75152-312">3600</span><span class="sxs-lookup"><span data-stu-id="75152-312">3600</span></span>  <br/> |<span data-ttu-id="75152-313">100</span><span class="sxs-lookup"><span data-stu-id="75152-313">100</span></span>  <br/> |<span data-ttu-id="75152-314">1 </span><span class="sxs-lookup"><span data-stu-id="75152-314">1</span></span>  <br/> |<span data-ttu-id="75152-315">443</span><span class="sxs-lookup"><span data-stu-id="75152-315">443</span></span>  <br/> |<span data-ttu-id="75152-316">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="75152-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="75152-317">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="75152-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="75152-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="75152-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="75152-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="75152-319">_tcp</span></span>  <br/> |<span data-ttu-id="75152-320">3600</span><span class="sxs-lookup"><span data-stu-id="75152-320">3600</span></span>  <br/> |<span data-ttu-id="75152-321">100</span><span class="sxs-lookup"><span data-stu-id="75152-321">100</span></span>  <br/> |<span data-ttu-id="75152-322">1 </span><span class="sxs-lookup"><span data-stu-id="75152-322">1</span></span>  <br/> |<span data-ttu-id="75152-323">5061</span><span class="sxs-lookup"><span data-stu-id="75152-323">5061</span></span>  <br/> |<span data-ttu-id="75152-324">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="75152-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="75152-325">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="75152-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![輸入或貼上新記錄的值](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="75152-327">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="75152-327">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="75152-329">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="75152-329">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="75152-p114">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="75152-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
