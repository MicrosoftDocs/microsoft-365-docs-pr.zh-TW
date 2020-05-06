---
title: 在 Dyn.com 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Dyn.com。
ms.openlocfilehash: 9d419cc26688cdbda792c0aaaa116ee01534247a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049116"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="85d77-103">在 Dyn.com 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="85d77-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="85d77-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="85d77-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="85d77-105">如果 Dyn.com 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="85d77-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 

  
> [!NOTE]
>  <span data-ttu-id="85d77-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="85d77-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="85d77-109">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="85d77-109">Add a TXT record for verification</span></span>
<span data-ttu-id="85d77-110"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="85d77-110"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="85d77-p102">首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="85d77-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="85d77-114">在 [**區域等級服務**] 頁面上，針對您想要編輯的網域，選取 [ **Dyn Standard DNS 服務**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-114">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="85d77-115">在您網域的 [ **DNS** ] 頁面上，選取 [**喜好**設定]。</span><span class="sxs-lookup"><span data-stu-id="85d77-115">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="85d77-116">選取 [**啟用專家介面**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-116">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="85d77-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="85d77-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="85d77-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="85d77-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="85d77-119">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="85d77-119">**Host**</span></span>|<span data-ttu-id="85d77-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85d77-120">**TTL**</span></span>|<span data-ttu-id="85d77-121">**類型**</span><span class="sxs-lookup"><span data-stu-id="85d77-121">**Type**</span></span>|<span data-ttu-id="85d77-122">**資料**</span><span class="sxs-lookup"><span data-stu-id="85d77-122">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="85d77-123">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="85d77-123">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="85d77-124">600</span><span class="sxs-lookup"><span data-stu-id="85d77-124">600</span></span>  <br/> |<span data-ttu-id="85d77-125">TXT</span><span class="sxs-lookup"><span data-stu-id="85d77-125">TXT</span></span>  <br/> |<span data-ttu-id="85d77-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="85d77-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="85d77-127">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="85d77-127">**Note:** This is an example.</span></span> <span data-ttu-id="85d77-128">在這裡請使用您自己來自表格的 [目的地或指向位址]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="85d77-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="85d77-129">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="85d77-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="85d77-131">選取 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-131">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="85d77-133">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="85d77-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="85d77-134">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="85d77-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="85d77-135">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="85d77-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="85d77-136">在 Microsoft 系統管理中心中，移至 [設定]\*\*\*\* \> [網域]<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="85d77-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="85d77-137">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="85d77-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="85d77-138">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="85d77-138">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="85d77-139">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="85d77-139">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="85d77-p104">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="85d77-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="85d77-143">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="85d77-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="85d77-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="85d77-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="85d77-p105">首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="85d77-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="85d77-148">在 [**區域等級服務**] 頁面上，針對您想要編輯的網域，選取 [ **Dyn Standard DNS 服務**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-148">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="85d77-149">在您網域的 [DNS] 頁面上，選取 [**喜好**設定]。</span><span class="sxs-lookup"><span data-stu-id="85d77-149">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="85d77-150">選取 [**啟用專家介面**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-150">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="85d77-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="85d77-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="85d77-152">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="85d77-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="85d77-153">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="85d77-153">**Host**</span></span>|<span data-ttu-id="85d77-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85d77-154">**TTL**</span></span>|<span data-ttu-id="85d77-155">**類型**</span><span class="sxs-lookup"><span data-stu-id="85d77-155">**Type**</span></span>|<span data-ttu-id="85d77-156">**資料**</span><span class="sxs-lookup"><span data-stu-id="85d77-156">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="85d77-157">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="85d77-157">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="85d77-158">600</span><span class="sxs-lookup"><span data-stu-id="85d77-158">600</span></span>  <br/> |<span data-ttu-id="85d77-159">MX</span><span class="sxs-lookup"><span data-stu-id="85d77-159">MX</span></span>  <br/> |<span data-ttu-id="85d77-160">10  *\<網域金鑰\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="85d77-160">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="85d77-161">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="85d77-161">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="85d77-162">**10**是 MX 優先順序值。</span><span class="sxs-lookup"><span data-stu-id="85d77-162">The **10** is the MX priority value.</span></span> <span data-ttu-id="85d77-163">請將它新增到 MX 值的開頭，並以空格分隔該值的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="85d77-163">Add it to the beginning of the MX value, separated from the remainder of the value by a space.</span></span>  <br/> <span data-ttu-id="85d77-164">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="85d77-164">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="85d77-165">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="85d77-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="85d77-166">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="85d77-166">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![Dyn-BP-Configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="85d77-168">選取 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-168">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="85d77-170">如果有任何其他 MX 記錄，請選取 [**刪除**] 欄中的每一個核取方塊加以移除。</span><span class="sxs-lookup"><span data-stu-id="85d77-170">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="85d77-172">選取 [套用**變更**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-172">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="85d77-174">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="85d77-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="85d77-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="85d77-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="85d77-p108">首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="85d77-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="85d77-179">在 [**區域等級服務**] 頁面上，針對您想要編輯的網域，選取 [ **Dyn Standard DNS 服務**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-179">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="85d77-180">在您網域的 [ **DNS** ] 頁面上，選取 [**喜好**設定]。</span><span class="sxs-lookup"><span data-stu-id="85d77-180">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="85d77-181">選取 [**啟用專家介面**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-181">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="85d77-182">新增六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="85d77-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="85d77-183">在 [新增**DNS 記錄**] 區段的新記錄方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="85d77-183">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="85d77-184">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="85d77-184">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="85d77-185">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="85d77-185">**Host**</span></span>|<span data-ttu-id="85d77-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85d77-186">**TTL**</span></span>|<span data-ttu-id="85d77-187">**類型**</span><span class="sxs-lookup"><span data-stu-id="85d77-187">**Type**</span></span>|<span data-ttu-id="85d77-188">**資料**</span><span class="sxs-lookup"><span data-stu-id="85d77-188">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="85d77-189">autodiscover (自動探索)</span><span class="sxs-lookup"><span data-stu-id="85d77-189">autodiscover</span></span>  <br/> |<span data-ttu-id="85d77-190">600</span><span class="sxs-lookup"><span data-stu-id="85d77-190">600</span></span>  <br/> |<span data-ttu-id="85d77-191">CNAME</span><span class="sxs-lookup"><span data-stu-id="85d77-191">CNAME</span></span>  <br/> |<span data-ttu-id="85d77-192">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="85d77-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="85d77-193">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="85d77-193">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="85d77-194">sip</span><span class="sxs-lookup"><span data-stu-id="85d77-194">sip</span></span>  <br/> |<span data-ttu-id="85d77-195">600</span><span class="sxs-lookup"><span data-stu-id="85d77-195">600</span></span>  <br/> |<span data-ttu-id="85d77-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="85d77-196">CNAME</span></span>  <br/> |<span data-ttu-id="85d77-197">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="85d77-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="85d77-198">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="85d77-198">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="85d77-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="85d77-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="85d77-200">600</span><span class="sxs-lookup"><span data-stu-id="85d77-200">600</span></span>  <br/> |<span data-ttu-id="85d77-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="85d77-201">CNAME</span></span>  <br/> |<span data-ttu-id="85d77-202">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="85d77-202">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="85d77-203">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="85d77-203">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="85d77-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="85d77-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="85d77-205">600</span><span class="sxs-lookup"><span data-stu-id="85d77-205">600</span></span>  <br/> |<span data-ttu-id="85d77-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="85d77-206">CNAME</span></span>  <br/> |<span data-ttu-id="85d77-207">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="85d77-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="85d77-208">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="85d77-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="85d77-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="85d77-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="85d77-210">600</span><span class="sxs-lookup"><span data-stu-id="85d77-210">600</span></span>  <br/> |<span data-ttu-id="85d77-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="85d77-211">CNAME</span></span>  <br/> |<span data-ttu-id="85d77-212">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="85d77-212">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="85d77-213">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="85d77-213">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-Configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="85d77-215">選取 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-215">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="85d77-217">新增剩餘的五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="85d77-217">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="85d77-218">在 [**新增 DNS 記錄**] 區段中，使用表格中下一列的值來建立記錄，然後再選取 [**建立記錄**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="85d77-218">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="85d77-219">重複這個程序，直到六筆 CNAME 記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="85d77-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="85d77-220">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="85d77-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="85d77-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="85d77-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="85d77-222">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="85d77-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="85d77-223">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="85d77-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="85d77-224">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="85d77-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="85d77-225">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="85d77-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="85d77-p110">首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="85d77-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="85d77-229">在 [**區域等級服務**] 頁面上，針對您想要編輯的網域，選取 [ **Dyn Standard DNS 服務**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-229">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="85d77-230">在您網域的 [ **DNS** ] 頁面上，選取 [**喜好**設定]。</span><span class="sxs-lookup"><span data-stu-id="85d77-230">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="85d77-231">選取 [**啟用專家介面**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-231">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="85d77-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="85d77-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="85d77-233">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="85d77-233">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="85d77-234">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="85d77-234">**Host**</span></span>|<span data-ttu-id="85d77-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85d77-235">**TTL**</span></span>|<span data-ttu-id="85d77-236">**類型**</span><span class="sxs-lookup"><span data-stu-id="85d77-236">**Type**</span></span>|<span data-ttu-id="85d77-237">**資料**</span><span class="sxs-lookup"><span data-stu-id="85d77-237">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="85d77-238">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="85d77-238">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="85d77-239">600</span><span class="sxs-lookup"><span data-stu-id="85d77-239">600</span></span>  <br/> |<span data-ttu-id="85d77-240">TXT</span><span class="sxs-lookup"><span data-stu-id="85d77-240">TXT</span></span>  <br/> |<span data-ttu-id="85d77-241">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="85d77-241">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="85d77-242">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="85d77-242">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="85d77-244">選取 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-244">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="85d77-246">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="85d77-246">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="85d77-247"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="85d77-247"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="85d77-248">首先請用[這個連結](https://account.dyn.com/dns/)移至 Dyn.com 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="85d77-248">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="85d77-249">系統會提示您先登入</span><span class="sxs-lookup"><span data-stu-id="85d77-249">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="85d77-251">在 [**區域等級服務**] 頁面上，針對您想要編輯的網域，選取 [ **Dyn Standard DNS 服務**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-251">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="85d77-252">在您網域的 [ **DNS** ] 頁面上，選取 [**喜好**設定]。</span><span class="sxs-lookup"><span data-stu-id="85d77-252">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="85d77-253">選取 [**啟用專家介面**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-253">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="85d77-254">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="85d77-254">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="85d77-255">在 [新增**DNS 記錄**] 區段的新記錄方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="85d77-255">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="85d77-256">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="85d77-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="85d77-257">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="85d77-257">**Host**</span></span>|<span data-ttu-id="85d77-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="85d77-258">**TTL**</span></span>|<span data-ttu-id="85d77-259">**類型**</span><span class="sxs-lookup"><span data-stu-id="85d77-259">**Type**</span></span>|<span data-ttu-id="85d77-260">**資料**</span><span class="sxs-lookup"><span data-stu-id="85d77-260">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="85d77-261">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="85d77-261">_sip._tls</span></span>|<span data-ttu-id="85d77-262">600</span><span class="sxs-lookup"><span data-stu-id="85d77-262">600</span></span>|<span data-ttu-id="85d77-263">SRV</span><span class="sxs-lookup"><span data-stu-id="85d77-263">SRV</span></span>|<span data-ttu-id="85d77-264">100 1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="85d77-264">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="85d77-265">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="85d77-265">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="85d77-266">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="85d77-266">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="85d77-267">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="85d77-267">_sipfederationtls._tcp</span></span>|<span data-ttu-id="85d77-268">600</span><span class="sxs-lookup"><span data-stu-id="85d77-268">600</span></span>|<span data-ttu-id="85d77-269">SRV</span><span class="sxs-lookup"><span data-stu-id="85d77-269">SRV</span></span>|<span data-ttu-id="85d77-270">100 1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="85d77-270">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="85d77-271">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="85d77-271">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="85d77-272">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="85d77-272">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="85d77-274">選取 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="85d77-274">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="85d77-276">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="85d77-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="85d77-277">在 [**新增 DNS 記錄**] 區段中，使用表格中第二列的值來建立記錄，然後再選取 [**建立記錄**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="85d77-277">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="85d77-p114">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="85d77-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
