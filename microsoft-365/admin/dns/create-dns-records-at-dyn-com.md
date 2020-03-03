---
title: 在 Dyn.com 建立 Office 365 的 DNS 記錄
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 商務用 Skype 線上商務和 dyn.com 其他服務的 DNS 記錄。
ms.openlocfilehash: a09ba409b1788432c5cd5c060252bb76b6903342
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349344"
---
# <a name="create-dns-records-at-dyncom-for-office-365"></a><span data-ttu-id="b56b9-103">在 Dyn.com 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="b56b9-103">Create DNS records at Dyn.com for Office 365</span></span>

 <span data-ttu-id="b56b9-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="b56b9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b56b9-105">如果 Dyn.com 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="b56b9-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="b56b9-106">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="b56b9-106">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b56b9-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b56b9-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b56b9-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="b56b9-110">Add a TXT record for verification</span></span>
<span data-ttu-id="b56b9-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b56b9-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="b56b9-p102">首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="b56b9-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="b56b9-115">在 [**層級服務**] 頁面上，選取您想要編輯的網域**Dyn 標準 DNS 服務**。</span><span class="sxs-lookup"><span data-stu-id="b56b9-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b56b9-116">在您網域的**DNS** ] 頁面上，選取 [**喜好設定**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="b56b9-117">選取 [**啟用專家介面**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="b56b9-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b56b9-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b56b9-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b56b9-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b56b9-120">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="b56b9-120">**Host**</span></span>|<span data-ttu-id="b56b9-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b56b9-121">**TTL**</span></span>|<span data-ttu-id="b56b9-122">**類型**</span><span class="sxs-lookup"><span data-stu-id="b56b9-122">**Type**</span></span>|<span data-ttu-id="b56b9-123">**資料**</span><span class="sxs-lookup"><span data-stu-id="b56b9-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b56b9-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="b56b9-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b56b9-125">600 個</span><span class="sxs-lookup"><span data-stu-id="b56b9-125">600</span></span>  <br/> |<span data-ttu-id="b56b9-126">TXT</span><span class="sxs-lookup"><span data-stu-id="b56b9-126">TXT</span></span>  <br/> |<span data-ttu-id="b56b9-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b56b9-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b56b9-128">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="b56b9-128">**Note:** This is an example.</span></span> <span data-ttu-id="b56b9-129">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="b56b9-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="b56b9-130">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="b56b9-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-DYN-BP-CONFIGURE-1-確認-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="b56b9-132">選取 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="b56b9-134">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="b56b9-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b56b9-135">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="b56b9-135">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="b56b9-136">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="b56b9-136">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b56b9-137">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="b56b9-137">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b56b9-138">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="b56b9-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b56b9-139">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="b56b9-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b56b9-140">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="b56b9-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b56b9-p104">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b56b9-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="b56b9-144">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="b56b9-144">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="b56b9-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b56b9-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="b56b9-p105">首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="b56b9-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="b56b9-149">在 [**層級服務**] 頁面上，選取您想要編輯的網域**Dyn 標準 DNS 服務**。</span><span class="sxs-lookup"><span data-stu-id="b56b9-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b56b9-150">在您網域的 DNS] 頁面上，選取 [**喜好設定**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="b56b9-151">選取 [**啟用專家介面**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="b56b9-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b56b9-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b56b9-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b56b9-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b56b9-154">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="b56b9-154">**Host**</span></span>|<span data-ttu-id="b56b9-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b56b9-155">**TTL**</span></span>|<span data-ttu-id="b56b9-156">**類型**</span><span class="sxs-lookup"><span data-stu-id="b56b9-156">**Type**</span></span>|<span data-ttu-id="b56b9-157">**資料**</span><span class="sxs-lookup"><span data-stu-id="b56b9-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b56b9-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="b56b9-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b56b9-159">600 個</span><span class="sxs-lookup"><span data-stu-id="b56b9-159">600</span></span>  <br/> |<span data-ttu-id="b56b9-160">MX</span><span class="sxs-lookup"><span data-stu-id="b56b9-160">MX</span></span>  <br/> |<span data-ttu-id="b56b9-161">10  *\<網域金鑰\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b56b9-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="b56b9-162">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b56b9-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="b56b9-163">**10**是指 MX 優先順序值。</span><span class="sxs-lookup"><span data-stu-id="b56b9-163">The **10** is the MX priority value.</span></span> <span data-ttu-id="b56b9-164">請將它新增到 MX 值的開頭，並以空格分隔該值的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="b56b9-164">Add it to the beginning of the MX value, separated from the remainder of the value by a space.</span></span>  <br/> <span data-ttu-id="b56b9-165">**附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="b56b9-165">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="b56b9-166">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="b56b9-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="b56b9-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="b56b9-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-DYN-BP-CONFIGURE-1-設定-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="b56b9-169">選取 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="b56b9-171">如果有任何其他 MX 記錄，請將它們移除藉由選取 [**刪除**] 欄中的每個核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b56b9-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="b56b9-173">選取 [**套用變更**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="b56b9-175">新增 Office 365 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="b56b9-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="b56b9-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b56b9-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="b56b9-p108">首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="b56b9-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="b56b9-180">在 [**層級服務**] 頁面上，選取您想要編輯的網域**Dyn 標準 DNS 服務**。</span><span class="sxs-lookup"><span data-stu-id="b56b9-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b56b9-181">在您網域的**DNS** ] 頁面上，選取 [**喜好設定**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="b56b9-182">選取 [**啟用專家介面**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="b56b9-183">新增六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="b56b9-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="b56b9-184">在 [ **Add DNS Record** ] 區段，於新記錄的方塊中輸入或複製並貼上下表第一列的值。</span><span class="sxs-lookup"><span data-stu-id="b56b9-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="b56b9-185">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b56b9-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b56b9-186">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="b56b9-186">**Host**</span></span>|<span data-ttu-id="b56b9-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b56b9-187">**TTL**</span></span>|<span data-ttu-id="b56b9-188">**類型**</span><span class="sxs-lookup"><span data-stu-id="b56b9-188">**Type**</span></span>|<span data-ttu-id="b56b9-189">**資料**</span><span class="sxs-lookup"><span data-stu-id="b56b9-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b56b9-190">autodiscover (自動探索)</span><span class="sxs-lookup"><span data-stu-id="b56b9-190">autodiscover</span></span>  <br/> |<span data-ttu-id="b56b9-191">600 個</span><span class="sxs-lookup"><span data-stu-id="b56b9-191">600</span></span>  <br/> |<span data-ttu-id="b56b9-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="b56b9-192">CNAME</span></span>  <br/> |<span data-ttu-id="b56b9-193">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="b56b9-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="b56b9-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b56b9-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b56b9-195">sip</span><span class="sxs-lookup"><span data-stu-id="b56b9-195">sip</span></span>  <br/> |<span data-ttu-id="b56b9-196">600 個</span><span class="sxs-lookup"><span data-stu-id="b56b9-196">600</span></span>  <br/> |<span data-ttu-id="b56b9-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="b56b9-197">CNAME</span></span>  <br/> |<span data-ttu-id="b56b9-198">sipdir.online.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="b56b9-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b56b9-199">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b56b9-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b56b9-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b56b9-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b56b9-201">600 個</span><span class="sxs-lookup"><span data-stu-id="b56b9-201">600</span></span>  <br/> |<span data-ttu-id="b56b9-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="b56b9-202">CNAME</span></span>  <br/> |<span data-ttu-id="b56b9-203">webdir.online.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="b56b9-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b56b9-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b56b9-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b56b9-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b56b9-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b56b9-206">600 個</span><span class="sxs-lookup"><span data-stu-id="b56b9-206">600</span></span>  <br/> |<span data-ttu-id="b56b9-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="b56b9-207">CNAME</span></span>  <br/> |<span data-ttu-id="b56b9-208">enterpriseregistration.windows.net>。</span><span class="sxs-lookup"><span data-stu-id="b56b9-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="b56b9-209">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b56b9-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b56b9-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b56b9-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b56b9-211">600 個</span><span class="sxs-lookup"><span data-stu-id="b56b9-211">600</span></span>  <br/> |<span data-ttu-id="b56b9-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="b56b9-212">CNAME</span></span>  <br/> |<span data-ttu-id="b56b9-213">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="b56b9-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="b56b9-214">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b56b9-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-DYN-BP-CONFIGURE-1-設定-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="b56b9-216">選取 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="b56b9-218">新增剩餘的五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="b56b9-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="b56b9-219">在 [ **Add DNS Record** ] 區段中，在表格中，使用下一列的值來建立記錄，然後再次選擇 [**建立記錄**，以完成該筆記錄。</span><span class="sxs-lookup"><span data-stu-id="b56b9-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="b56b9-220">重複這個程序，直到六筆 CNAME 記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="b56b9-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b56b9-221">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="b56b9-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b56b9-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b56b9-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b56b9-223">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="b56b9-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b56b9-224">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="b56b9-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b56b9-225">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="b56b9-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="b56b9-226">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="b56b9-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="b56b9-p110">首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="b56b9-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="b56b9-230">在 [**層級服務**] 頁面上，選取您想要編輯的網域**Dyn 標準 DNS 服務**。</span><span class="sxs-lookup"><span data-stu-id="b56b9-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b56b9-231">在您網域的**DNS** ] 頁面上，選取 [**喜好設定**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="b56b9-232">選取 [**啟用專家介面**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="b56b9-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b56b9-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b56b9-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b56b9-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b56b9-235">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="b56b9-235">**Host**</span></span>|<span data-ttu-id="b56b9-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b56b9-236">**TTL**</span></span>|<span data-ttu-id="b56b9-237">**類型**</span><span class="sxs-lookup"><span data-stu-id="b56b9-237">**Type**</span></span>|<span data-ttu-id="b56b9-238">**資料**</span><span class="sxs-lookup"><span data-stu-id="b56b9-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b56b9-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="b56b9-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b56b9-240">600 個</span><span class="sxs-lookup"><span data-stu-id="b56b9-240">600</span></span>  <br/> |<span data-ttu-id="b56b9-241">TXT</span><span class="sxs-lookup"><span data-stu-id="b56b9-241">TXT</span></span>  <br/> |<span data-ttu-id="b56b9-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b56b9-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b56b9-243">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="b56b9-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-DYN-BP-CONFIGURE-1-設定-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="b56b9-245">選取 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-245">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="b56b9-247">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="b56b9-247">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="b56b9-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b56b9-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="b56b9-249">首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="b56b9-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="b56b9-250">系統會提示您先登入</span><span class="sxs-lookup"><span data-stu-id="b56b9-250">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="b56b9-252">在 [**層級服務**] 頁面上，選取您想要編輯的網域**Dyn 標準 DNS 服務**。</span><span class="sxs-lookup"><span data-stu-id="b56b9-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b56b9-253">在您網域的**DNS** ] 頁面上，選取 [**喜好設定**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="b56b9-254">選取 [**啟用專家介面**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="b56b9-255">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="b56b9-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="b56b9-256">在 [ **Add DNS Record** ] 區段，於新記錄的方塊中輸入或複製並貼上下表第一列的值。</span><span class="sxs-lookup"><span data-stu-id="b56b9-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="b56b9-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b56b9-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b56b9-258">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="b56b9-258">**Host**</span></span>|<span data-ttu-id="b56b9-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b56b9-259">**TTL**</span></span>|<span data-ttu-id="b56b9-260">**類型**</span><span class="sxs-lookup"><span data-stu-id="b56b9-260">**Type**</span></span>|<span data-ttu-id="b56b9-261">**資料**</span><span class="sxs-lookup"><span data-stu-id="b56b9-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b56b9-262">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="b56b9-262">_sip._tls</span></span>|<span data-ttu-id="b56b9-263">600 個</span><span class="sxs-lookup"><span data-stu-id="b56b9-263">600</span></span>|<span data-ttu-id="b56b9-264">SRV</span><span class="sxs-lookup"><span data-stu-id="b56b9-264">SRV</span></span>|<span data-ttu-id="b56b9-265">100 1 443 sipdir.online.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="b56b9-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="b56b9-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b56b9-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="b56b9-267">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="b56b9-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="b56b9-268">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="b56b9-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="b56b9-269">600 個</span><span class="sxs-lookup"><span data-stu-id="b56b9-269">600</span></span>|<span data-ttu-id="b56b9-270">SRV</span><span class="sxs-lookup"><span data-stu-id="b56b9-270">SRV</span></span>|<span data-ttu-id="b56b9-271">100 1 5061 sipfed.online.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="b56b9-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="b56b9-272">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b56b9-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="b56b9-273">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="b56b9-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-DYN-BP-CONFIGURE-1-設定-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="b56b9-275">選取 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="b56b9-275">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="b56b9-277">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="b56b9-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="b56b9-278">在 [ **Add DNS Record** ] 區段中的使用中表格中，第二列的值建立記錄，然後再次選擇 [**建立記錄**，以完成該筆記錄。</span><span class="sxs-lookup"><span data-stu-id="b56b9-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="b56b9-p114">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b56b9-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
