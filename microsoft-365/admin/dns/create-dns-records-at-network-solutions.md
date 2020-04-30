---
title: 在 Microsoft 的網路解決方案中建立 DNS 記錄
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
description: 瞭解如何驗證您的網域，並在 Microsoft 的網路解決方案中設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄。
ms.openlocfilehash: f990e4311ef88022d7fec2e1b7c90b3d8d035448
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939140"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="fe4ca-103">在 Microsoft 的網路解決方案中建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="fe4ca-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="fe4ca-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fe4ca-105">如果 Network Solutions 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="fe4ca-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-106">These are the main records to add.</span></span> <span data-ttu-id="fe4ca-107">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="fe4ca-108">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="fe4ca-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="fe4ca-109">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="fe4ca-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="fe4ca-110">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="fe4ca-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="fe4ca-111">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="fe4ca-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="fe4ca-112">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="fe4ca-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="fe4ca-113">在 [網路方案] 中新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="fe4ca-p102">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fe4ca-117">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="fe4ca-117">Add a TXT record for verification</span></span>
<span data-ttu-id="fe4ca-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="fe4ca-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="fe4ca-p103">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe4ca-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="fe4ca-123">請依照下列步驟操作或[觀看影片 (從 0:47 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-123">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fe4ca-124">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-124">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="fe4ca-125">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-125">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fe4ca-126">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="fe4ca-128">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="fe4ca-130">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-130">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="fe4ca-132">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="fe4ca-133">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-133">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="fe4ca-135">向下滾動至 [**文字（TXT 記錄）** ] 區段，然後選取 [**編輯 TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![選取 [編輯 TXT 記錄]](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="fe4ca-137">In the boxes for the new record, type or copy and paste the values in the following table.</span><span class="sxs-lookup"><span data-stu-id="fe4ca-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="fe4ca-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-138">**Host**</span></span>|<span data-ttu-id="fe4ca-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-139">**TTL**</span></span>|<span data-ttu-id="fe4ca-140">**Text**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="fe4ca-141">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="fe4ca-142">3600</span><span class="sxs-lookup"><span data-stu-id="fe4ca-142">3600</span></span>  <br/> |<span data-ttu-id="fe4ca-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fe4ca-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="fe4ca-144">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-144">**Note:** This is an example.</span></span> <span data-ttu-id="fe4ca-145">在這裡請使用您自己來自表格的 [目的地或指向位址]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="fe4ca-146">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="fe4ca-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![在新記錄的方塊中輸入或貼上值](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="fe4ca-148">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-148">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="fe4ca-150">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-150">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="fe4ca-152">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fe4ca-153">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="fe4ca-154">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="fe4ca-155">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="fe4ca-156">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="fe4ca-157">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="fe4ca-158">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="fe4ca-p107">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="fe4ca-162">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="fe4ca-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="fe4ca-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="fe4ca-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="fe4ca-164">請依照下列步驟操作或[觀看影片 (從 3:51 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-164">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fe4ca-165">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-165">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="fe4ca-166">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-166">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fe4ca-167">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="fe4ca-169">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="fe4ca-171">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-171">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="fe4ca-173">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="fe4ca-174">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-174">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="fe4ca-176">向下滾動至 [**郵件伺服器（MX 記錄）** ] 區段，然後選取 [**編輯 MX 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![選取 [編輯 MX 記錄]](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="fe4ca-178">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="fe4ca-179">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-179">**Priority**</span></span>|<span data-ttu-id="fe4ca-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-180">**TTL**</span></span>|<span data-ttu-id="fe4ca-181">**Mail server (郵件伺服器)**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="fe4ca-182">10 </span><span class="sxs-lookup"><span data-stu-id="fe4ca-182">10</span></span>  <br/> <span data-ttu-id="fe4ca-183">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-183">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="fe4ca-184">3600</span><span class="sxs-lookup"><span data-stu-id="fe4ca-184">3600</span></span>  <br/> | <span data-ttu-id="fe4ca-185">*\<網域金鑰\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="fe4ca-186">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="fe4ca-187">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="fe4ca-188">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="fe4ca-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![在新記錄的方塊中輸入或貼上值](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="fe4ca-190">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-190">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="fe4ca-192">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-192">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="fe4ca-194">如果有任何其他 MX 記錄，請選取每一筆記錄的 [**刪除**] 以刪除所有記錄。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="fe4ca-196">選取所有選項時，請選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-196">When they are all selected, select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="fe4ca-198">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-198">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="fe4ca-200">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="fe4ca-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="fe4ca-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="fe4ca-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="fe4ca-202">請依照下列步驟操作或[觀看影片 (從 4:43 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-202">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fe4ca-203">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-203">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="fe4ca-204">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-204">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fe4ca-205">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="fe4ca-207">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="fe4ca-209">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-209">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="fe4ca-211">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="fe4ca-212">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-212">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="fe4ca-214">向下滾動至 [**主機別名（CNAME 記錄）** ] 區段，然後選取 [**編輯 CNAME 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![選取 [主機別名] 底下的 [編輯 CNAME 記錄]](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="fe4ca-216">在這四筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="fe4ca-217">**Alias**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-217">**Alias**</span></span>|<span data-ttu-id="fe4ca-218">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-218">**TTL**</span></span>|<span data-ttu-id="fe4ca-219">**參照的主機名稱**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-219">**Refers to Host Name**</span></span>|<span data-ttu-id="fe4ca-220">**其他主機（選取 [**其他主機**] 選項按鈕）**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fe4ca-221">autodiscover (自動探索)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-221">autodiscover</span></span>  <br/> |<span data-ttu-id="fe4ca-222">3600</span><span class="sxs-lookup"><span data-stu-id="fe4ca-222">3600</span></span>  <br/> |<span data-ttu-id="fe4ca-223">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-223">(No setting)</span></span>  <br/> |<span data-ttu-id="fe4ca-224">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="fe4ca-225">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fe4ca-226">sip</span><span class="sxs-lookup"><span data-stu-id="fe4ca-226">sip</span></span>  <br/> |<span data-ttu-id="fe4ca-227">3600</span><span class="sxs-lookup"><span data-stu-id="fe4ca-227">3600</span></span>  <br/> |<span data-ttu-id="fe4ca-228">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-228">(No setting)</span></span>  <br/> |<span data-ttu-id="fe4ca-229">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="fe4ca-230">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fe4ca-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="fe4ca-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="fe4ca-232">3600</span><span class="sxs-lookup"><span data-stu-id="fe4ca-232">3600</span></span>  <br/> |<span data-ttu-id="fe4ca-233">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-233">(No setting)</span></span>  <br/> |<span data-ttu-id="fe4ca-234">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="fe4ca-235">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fe4ca-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="fe4ca-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="fe4ca-237">3600</span><span class="sxs-lookup"><span data-stu-id="fe4ca-237">3600</span></span>  <br/> |<span data-ttu-id="fe4ca-238">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-238">(No setting)</span></span>  <br/> |<span data-ttu-id="fe4ca-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="fe4ca-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="fe4ca-240">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fe4ca-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="fe4ca-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="fe4ca-242">3600</span><span class="sxs-lookup"><span data-stu-id="fe4ca-242">3600</span></span>  <br/> |<span data-ttu-id="fe4ca-243">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-243">(No setting)</span></span>  <br/> |<span data-ttu-id="fe4ca-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fe4ca-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="fe4ca-245">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![輸入或貼上新記錄的值](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="fe4ca-247">當您已新增所需的所有 CNAME 記錄後，請選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="fe4ca-249">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-249">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="fe4ca-251">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="fe4ca-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="fe4ca-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="fe4ca-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe4ca-253">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="fe4ca-254">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="fe4ca-255">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="fe4ca-256">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="fe4ca-257">請依照下列步驟操作或[觀看影片 (從 5:35 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-257">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fe4ca-258">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-258">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="fe4ca-259">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-259">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fe4ca-260">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="fe4ca-262">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="fe4ca-264">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-264">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="fe4ca-266">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="fe4ca-267">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-267">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="fe4ca-269">向下滾動至 [**文字（TXT 記錄）** ] 區段，然後選取 [**編輯 TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![選取 [文字] 底下的 [編輯 TXT 記錄]](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="fe4ca-271">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="fe4ca-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="fe4ca-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-272">**Host**</span></span>|<span data-ttu-id="fe4ca-273">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-273">**TTL**</span></span>|<span data-ttu-id="fe4ca-274">**Text**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="fe4ca-275">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="fe4ca-276">3600</span><span class="sxs-lookup"><span data-stu-id="fe4ca-276">3600</span></span>  <br/> |<span data-ttu-id="fe4ca-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="fe4ca-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="fe4ca-278">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![輸入或貼上新記錄的值](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="fe4ca-280">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-280">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="fe4ca-282">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-282">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="fe4ca-284">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="fe4ca-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="fe4ca-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="fe4ca-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="fe4ca-286">請依照下列步驟操作或[觀看影片 (從 6:18 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-286">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="fe4ca-p113">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fe4ca-289">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="fe4ca-291">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="fe4ca-293">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-293">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="fe4ca-295">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="fe4ca-296">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-296">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="fe4ca-298">向下滾動至 [**服務（SRV 記錄）** ] 區段，然後選取 [**編輯 SRV 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![選取 [服務] 下的 [編輯 SRV 記錄]](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="fe4ca-300">在這兩筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="fe4ca-301">（從下拉式清單中選擇 [**服務**] 和 [**通訊協定**] 值。）</span><span class="sxs-lookup"><span data-stu-id="fe4ca-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="fe4ca-302">**Service** (服務)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-302">**Service**</span></span>|<span data-ttu-id="fe4ca-303">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-303">**Protocol**</span></span>|<span data-ttu-id="fe4ca-304">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-304">**TTL**</span></span>|<span data-ttu-id="fe4ca-305">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-305">**Priority**</span></span>|<span data-ttu-id="fe4ca-306">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-306">**Weight**</span></span>|<span data-ttu-id="fe4ca-307">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-307">**Port**</span></span>|<span data-ttu-id="fe4ca-308">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="fe4ca-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fe4ca-309">_sip</span><span class="sxs-lookup"><span data-stu-id="fe4ca-309">_sip</span></span>  <br/> |<span data-ttu-id="fe4ca-310">_tls</span><span class="sxs-lookup"><span data-stu-id="fe4ca-310">_tls</span></span>  <br/> |<span data-ttu-id="fe4ca-311">3600</span><span class="sxs-lookup"><span data-stu-id="fe4ca-311">3600</span></span>  <br/> |<span data-ttu-id="fe4ca-312">100</span><span class="sxs-lookup"><span data-stu-id="fe4ca-312">100</span></span>  <br/> |<span data-ttu-id="fe4ca-313">1 </span><span class="sxs-lookup"><span data-stu-id="fe4ca-313">1</span></span>  <br/> |<span data-ttu-id="fe4ca-314">443</span><span class="sxs-lookup"><span data-stu-id="fe4ca-314">443</span></span>  <br/> |<span data-ttu-id="fe4ca-315">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="fe4ca-316">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fe4ca-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="fe4ca-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="fe4ca-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="fe4ca-318">_tcp</span></span>  <br/> |<span data-ttu-id="fe4ca-319">3600</span><span class="sxs-lookup"><span data-stu-id="fe4ca-319">3600</span></span>  <br/> |<span data-ttu-id="fe4ca-320">100</span><span class="sxs-lookup"><span data-stu-id="fe4ca-320">100</span></span>  <br/> |<span data-ttu-id="fe4ca-321">1 </span><span class="sxs-lookup"><span data-stu-id="fe4ca-321">1</span></span>  <br/> |<span data-ttu-id="fe4ca-322">5061</span><span class="sxs-lookup"><span data-stu-id="fe4ca-322">5061</span></span>  <br/> |<span data-ttu-id="fe4ca-323">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="fe4ca-324">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="fe4ca-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![輸入或貼上新記錄的值](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="fe4ca-326">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-326">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="fe4ca-328">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-328">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="fe4ca-p114">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="fe4ca-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
