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
ms.openlocfilehash: e7ce1dd633aa916643f3dcbf7900fa7831608e78
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629296"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="afcb0-103">在 Microsoft 的網路解決方案中建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="afcb0-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="afcb0-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="afcb0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="afcb0-105">如果 Network Solutions 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="afcb0-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="afcb0-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="afcb0-106">These are the main records to add.</span></span> <span data-ttu-id="afcb0-107">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="afcb0-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="afcb0-108">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="afcb0-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="afcb0-109">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="afcb0-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="afcb0-110">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="afcb0-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="afcb0-111">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="afcb0-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="afcb0-112">新增 Microsoft 所需的兩筆 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="afcb0-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="afcb0-113">在 [網路方案] 中新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="afcb0-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="afcb0-114">若要深入瞭解 Microsoft 的網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="afcb0-114">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="afcb0-p102">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="afcb0-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="afcb0-118">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="afcb0-118">Add a TXT record for verification</span></span>
<span data-ttu-id="afcb0-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="afcb0-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="afcb0-120">在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="afcb0-120">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="afcb0-121">您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。</span><span class="sxs-lookup"><span data-stu-id="afcb0-121">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="afcb0-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="afcb0-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="afcb0-124">請依照下列步驟操作或[觀看影片 (從 0:47 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="afcb0-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="afcb0-125">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="afcb0-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="afcb0-126">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="afcb0-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="afcb0-127">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="afcb0-129">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="afcb0-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="afcb0-131">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-131">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="afcb0-133">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="afcb0-134">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="afcb0-134">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="afcb0-136">向下滾動至 [**文字（TXT 記錄）** ] 區段，然後選取 [**編輯 TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![選取 [編輯 TXT 記錄]](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="afcb0-138">In the boxes for the new record, type or copy and paste the values in the following table.</span><span class="sxs-lookup"><span data-stu-id="afcb0-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="afcb0-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="afcb0-139">**Host**</span></span>|<span data-ttu-id="afcb0-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="afcb0-140">**TTL**</span></span>|<span data-ttu-id="afcb0-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="afcb0-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="afcb0-142">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="afcb0-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="afcb0-143">3600</span><span class="sxs-lookup"><span data-stu-id="afcb0-143">3600</span></span>  <br/> |<span data-ttu-id="afcb0-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="afcb0-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="afcb0-145">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="afcb0-145">**Note:** This is an example.</span></span> <span data-ttu-id="afcb0-146">從表格中，使用您的特定**目的地或指向位址**值。</span><span class="sxs-lookup"><span data-stu-id="afcb0-146">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="afcb0-147">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="afcb0-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![在新記錄的方塊中輸入或貼上值](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="afcb0-149">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-149">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="afcb0-151">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-151">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="afcb0-153">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="afcb0-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="afcb0-154">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求記錄。</span><span class="sxs-lookup"><span data-stu-id="afcb0-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="afcb0-155">當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="afcb0-155">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="afcb0-156">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="afcb0-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="afcb0-157">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="afcb0-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="afcb0-158">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="afcb0-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="afcb0-159">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="afcb0-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="afcb0-p107">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="afcb0-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="afcb0-163">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="afcb0-163">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="afcb0-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="afcb0-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="afcb0-165">請依照下列步驟操作或[觀看影片 (從 3:51 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="afcb0-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="afcb0-166">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="afcb0-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="afcb0-167">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="afcb0-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="afcb0-168">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="afcb0-170">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="afcb0-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="afcb0-172">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-172">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="afcb0-174">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="afcb0-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="afcb0-175">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="afcb0-177">向下滾動至 [**郵件伺服器（MX 記錄）** ] 區段，然後選取 [**編輯 MX 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![選取 [編輯 MX 記錄]](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="afcb0-179">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="afcb0-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="afcb0-180">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="afcb0-180">**Priority**</span></span>|<span data-ttu-id="afcb0-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="afcb0-181">**TTL**</span></span>|<span data-ttu-id="afcb0-182">**Mail server (郵件伺服器)**</span><span class="sxs-lookup"><span data-stu-id="afcb0-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="afcb0-183">10 </span><span class="sxs-lookup"><span data-stu-id="afcb0-183">10</span></span>  <br/> <span data-ttu-id="afcb0-184">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="afcb0-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="afcb0-185">3600</span><span class="sxs-lookup"><span data-stu-id="afcb0-185">3600</span></span>  <br/> | <span data-ttu-id="afcb0-186">*\<網域金鑰\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="afcb0-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="afcb0-187">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afcb0-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="afcb0-188">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="afcb0-188">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="afcb0-189">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="afcb0-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![在新記錄的方塊中輸入或貼上值](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="afcb0-191">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-191">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="afcb0-193">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-193">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="afcb0-195">如果有任何其他 MX 記錄，請選取每一筆記錄的 [**刪除**] 以刪除所有記錄。</span><span class="sxs-lookup"><span data-stu-id="afcb0-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="afcb0-197">選取所有選項時，請選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-197">When they are all selected, select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="afcb0-199">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-199">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="afcb0-201">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="afcb0-201">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="afcb0-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="afcb0-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="afcb0-203">請依照下列步驟操作或[觀看影片 (從 4:43 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="afcb0-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="afcb0-204">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="afcb0-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="afcb0-205">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="afcb0-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="afcb0-206">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="afcb0-208">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="afcb0-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="afcb0-210">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-210">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="afcb0-212">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="afcb0-213">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="afcb0-213">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="afcb0-215">向下滾動至 [**主機別名（CNAME 記錄）** ] 區段，然後選取 [**編輯 CNAME 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![選取 [主機別名] 底下的 [編輯 CNAME 記錄]](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="afcb0-217">在這四筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="afcb0-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="afcb0-218">**Alias**</span><span class="sxs-lookup"><span data-stu-id="afcb0-218">**Alias**</span></span>|<span data-ttu-id="afcb0-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="afcb0-219">**TTL**</span></span>|<span data-ttu-id="afcb0-220">**參照的主機名稱**</span><span class="sxs-lookup"><span data-stu-id="afcb0-220">**Refers to Host Name**</span></span>|<span data-ttu-id="afcb0-221">**其他主機（選取 [**其他主機**] 選項按鈕）**</span><span class="sxs-lookup"><span data-stu-id="afcb0-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="afcb0-222">autodiscover (自動探索)</span><span class="sxs-lookup"><span data-stu-id="afcb0-222">autodiscover</span></span>  <br/> |<span data-ttu-id="afcb0-223">3600</span><span class="sxs-lookup"><span data-stu-id="afcb0-223">3600</span></span>  <br/> |<span data-ttu-id="afcb0-224">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="afcb0-224">(No setting)</span></span>  <br/> |<span data-ttu-id="afcb0-225">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="afcb0-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="afcb0-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afcb0-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="afcb0-227">sip</span><span class="sxs-lookup"><span data-stu-id="afcb0-227">sip</span></span>  <br/> |<span data-ttu-id="afcb0-228">3600</span><span class="sxs-lookup"><span data-stu-id="afcb0-228">3600</span></span>  <br/> |<span data-ttu-id="afcb0-229">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="afcb0-229">(No setting)</span></span>  <br/> |<span data-ttu-id="afcb0-230">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="afcb0-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="afcb0-231">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afcb0-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="afcb0-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="afcb0-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="afcb0-233">3600</span><span class="sxs-lookup"><span data-stu-id="afcb0-233">3600</span></span>  <br/> |<span data-ttu-id="afcb0-234">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="afcb0-234">(No setting)</span></span>  <br/> |<span data-ttu-id="afcb0-235">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="afcb0-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="afcb0-236">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afcb0-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="afcb0-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="afcb0-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="afcb0-238">3600</span><span class="sxs-lookup"><span data-stu-id="afcb0-238">3600</span></span>  <br/> |<span data-ttu-id="afcb0-239">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="afcb0-239">(No setting)</span></span>  <br/> |<span data-ttu-id="afcb0-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="afcb0-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="afcb0-241">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afcb0-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="afcb0-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="afcb0-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="afcb0-243">3600</span><span class="sxs-lookup"><span data-stu-id="afcb0-243">3600</span></span>  <br/> |<span data-ttu-id="afcb0-244">(沒有設定)</span><span class="sxs-lookup"><span data-stu-id="afcb0-244">(No setting)</span></span>  <br/> |<span data-ttu-id="afcb0-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="afcb0-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="afcb0-246">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afcb0-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![輸入或貼上新記錄的值](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="afcb0-248">當您已新增所需的所有 CNAME 記錄後，請選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="afcb0-250">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-250">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="afcb0-252">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="afcb0-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="afcb0-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="afcb0-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="afcb0-254">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="afcb0-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="afcb0-255">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="afcb0-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="afcb0-256">如果您已有網域的 SPF 記錄，請不要為 Microsoft 建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="afcb0-256">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="afcb0-257">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="afcb0-257">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="afcb0-258">請依照下列步驟操作或[觀看影片 (從 5:35 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="afcb0-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="afcb0-259">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="afcb0-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="afcb0-260">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="afcb0-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="afcb0-261">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="afcb0-263">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="afcb0-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="afcb0-265">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-265">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="afcb0-267">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="afcb0-268">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="afcb0-268">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="afcb0-270">向下滾動至 [**文字（TXT 記錄）** ] 區段，然後選取 [**編輯 TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![選取 [文字] 底下的 [編輯 TXT 記錄]](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="afcb0-272">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="afcb0-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="afcb0-273">**Host**</span><span class="sxs-lookup"><span data-stu-id="afcb0-273">**Host**</span></span>|<span data-ttu-id="afcb0-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="afcb0-274">**TTL**</span></span>|<span data-ttu-id="afcb0-275">**Text**</span><span class="sxs-lookup"><span data-stu-id="afcb0-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="afcb0-276">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="afcb0-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="afcb0-277">3600</span><span class="sxs-lookup"><span data-stu-id="afcb0-277">3600</span></span>  <br/> |<span data-ttu-id="afcb0-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="afcb0-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="afcb0-279">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="afcb0-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![輸入或貼上新記錄的值](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="afcb0-281">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-281">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="afcb0-283">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-283">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="afcb0-285">新增 Microsoft 所需的兩筆 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="afcb0-285">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="afcb0-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="afcb0-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="afcb0-287">請依照下列步驟操作或[觀看影片 (從 6:18 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="afcb0-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="afcb0-p113">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="afcb0-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="afcb0-290">在您選取 [**登**入] 按鈕之前，請先在 [**登入：** ] 下拉式清單中選擇 [**管理我的功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="afcb0-292">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="afcb0-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="afcb0-294">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-294">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS]](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="afcb0-296">選取 [**管理 ADVANCED DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="afcb0-297">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="afcb0-297">(You may have to scroll down.)</span></span>
    
    ![選取 [管理 Advanced DNS 記錄]](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="afcb0-299">向下滾動至 [**服務（SRV 記錄）** ] 區段，然後選取 [**編輯 SRV 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![選取 [服務] 下的 [編輯 SRV 記錄]](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="afcb0-301">在這兩筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="afcb0-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="afcb0-302">（從下拉式清單中選擇 [**服務**] 和 [**通訊協定**] 值。）</span><span class="sxs-lookup"><span data-stu-id="afcb0-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="afcb0-303">**Service** (服務)</span><span class="sxs-lookup"><span data-stu-id="afcb0-303">**Service**</span></span>|<span data-ttu-id="afcb0-304">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="afcb0-304">**Protocol**</span></span>|<span data-ttu-id="afcb0-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="afcb0-305">**TTL**</span></span>|<span data-ttu-id="afcb0-306">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="afcb0-306">**Priority**</span></span>|<span data-ttu-id="afcb0-307">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="afcb0-307">**Weight**</span></span>|<span data-ttu-id="afcb0-308">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="afcb0-308">**Port**</span></span>|<span data-ttu-id="afcb0-309">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="afcb0-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="afcb0-310">_sip</span><span class="sxs-lookup"><span data-stu-id="afcb0-310">_sip</span></span>  <br/> |<span data-ttu-id="afcb0-311">_tls</span><span class="sxs-lookup"><span data-stu-id="afcb0-311">_tls</span></span>  <br/> |<span data-ttu-id="afcb0-312">3600</span><span class="sxs-lookup"><span data-stu-id="afcb0-312">3600</span></span>  <br/> |<span data-ttu-id="afcb0-313">100</span><span class="sxs-lookup"><span data-stu-id="afcb0-313">100</span></span>  <br/> |<span data-ttu-id="afcb0-314">1 </span><span class="sxs-lookup"><span data-stu-id="afcb0-314">1</span></span>  <br/> |<span data-ttu-id="afcb0-315">443</span><span class="sxs-lookup"><span data-stu-id="afcb0-315">443</span></span>  <br/> |<span data-ttu-id="afcb0-316">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="afcb0-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="afcb0-317">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afcb0-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="afcb0-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="afcb0-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="afcb0-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="afcb0-319">_tcp</span></span>  <br/> |<span data-ttu-id="afcb0-320">3600</span><span class="sxs-lookup"><span data-stu-id="afcb0-320">3600</span></span>  <br/> |<span data-ttu-id="afcb0-321">100</span><span class="sxs-lookup"><span data-stu-id="afcb0-321">100</span></span>  <br/> |<span data-ttu-id="afcb0-322">1 </span><span class="sxs-lookup"><span data-stu-id="afcb0-322">1</span></span>  <br/> |<span data-ttu-id="afcb0-323">5061</span><span class="sxs-lookup"><span data-stu-id="afcb0-323">5061</span></span>  <br/> |<span data-ttu-id="afcb0-324">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="afcb0-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="afcb0-325">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="afcb0-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![輸入或貼上新記錄的值](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="afcb0-327">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-327">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="afcb0-329">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="afcb0-329">Select **Save Changes**.</span></span>
    
    ![選取 [儲存變更]](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="afcb0-p114">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="afcb0-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
