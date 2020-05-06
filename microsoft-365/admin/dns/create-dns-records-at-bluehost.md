---
title: 在 Bluehost 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Bluehost。
ms.openlocfilehash: c2aabd7a578ab792cfb341f67765fc3021038e44
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049092"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="110fb-103">在 Bluehost 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="110fb-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="110fb-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="110fb-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="110fb-105">如果 Bluehost 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="110fb-106">在 Bluehost 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="110fb-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="110fb-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="110fb-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="110fb-108">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="110fb-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="110fb-109">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="110fb-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="110fb-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="110fb-110">Add a TXT record for verification</span></span>
<span data-ttu-id="110fb-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="110fb-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="110fb-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="110fb-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="110fb-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="110fb-116">首先請用[這個連結](https://my.bluehost.com/cgi/dm)移至 Bluehost 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="110fb-116">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="110fb-117">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="110fb-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="110fb-118">在 [**網域**] 頁面的 [**網域**] 區域中，尋找您要變更之網域的列，然後選取該網域的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="110fb-118">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="110fb-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="110fb-119">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="110fb-120">在 [ ***domain_name*** ] 區域的 [ **DNS 區域編輯器**] 列中，選取 [**管理 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="110fb-120">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="110fb-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="110fb-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="110fb-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="110fb-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="110fb-123">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="110fb-123">**Host Record**</span></span> <br/> |<span data-ttu-id="110fb-124">**TTL**</span><span class="sxs-lookup"><span data-stu-id="110fb-124">**TTL**</span></span> <br/> |<span data-ttu-id="110fb-125">**類型**</span><span class="sxs-lookup"><span data-stu-id="110fb-125">**Type**</span></span> <br/> |<span data-ttu-id="110fb-126">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="110fb-126">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="110fb-127">14400</span><span class="sxs-lookup"><span data-stu-id="110fb-127">14400</span></span>  <br/> |<span data-ttu-id="110fb-128">TXT</span><span class="sxs-lookup"><span data-stu-id="110fb-128">TXT</span></span>  <br/> |<span data-ttu-id="110fb-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="110fb-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="110fb-130">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="110fb-130">**Note:** This is an example.</span></span> <span data-ttu-id="110fb-131">在這裡請使用您自己來自表格的 [目的地或指向位址]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="110fb-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="110fb-132">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="110fb-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="110fb-133">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="110fb-133">Select **add record**.</span></span>
    
6. <span data-ttu-id="110fb-134">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="110fb-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="110fb-135">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="110fb-136">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="110fb-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="110fb-137">在 Microsoft 系統管理中心中，移至 [設定]\*\*\*\* \> [網域]<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="110fb-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="110fb-138">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="110fb-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="110fb-139">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="110fb-139">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="110fb-140">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="110fb-140">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="110fb-141">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="110fb-141">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="110fb-142">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="110fb-142">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="110fb-143">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="110fb-143">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="110fb-144">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="110fb-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="110fb-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="110fb-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="110fb-146">首先請用[這個連結](https://my.bluehost.com/cgi/dm)移至 Bluehost 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="110fb-146">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="110fb-147">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="110fb-147">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="110fb-148">在 [**網域**] 頁面的 [**網域**] 區域中，尋找您要變更之網域的列，然後選取該網域的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="110fb-148">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="110fb-149">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="110fb-149">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="110fb-150">在 [ ***domain_name*** ] 區域的 [ **DNS 區域編輯器**] 列中，選取 [**管理 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="110fb-150">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="110fb-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="110fb-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="110fb-152">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="110fb-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="110fb-153">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="110fb-153">**Host Record**</span></span>|<span data-ttu-id="110fb-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="110fb-154">**TTL**</span></span>|<span data-ttu-id="110fb-155">**類型**</span><span class="sxs-lookup"><span data-stu-id="110fb-155">**Type**</span></span>|<span data-ttu-id="110fb-156">**指向**</span><span class="sxs-lookup"><span data-stu-id="110fb-156">**Points To**</span></span>|<span data-ttu-id="110fb-157">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="110fb-157">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="110fb-158">14400</span><span class="sxs-lookup"><span data-stu-id="110fb-158">14400</span></span>  <br/> |<span data-ttu-id="110fb-159">MX</span><span class="sxs-lookup"><span data-stu-id="110fb-159">MX</span></span>  <br/> | <span data-ttu-id="110fb-160">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="110fb-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="110fb-161">**注意：** 從您的 Microsoft 帳戶取得您的\<*網域金鑰*\>。</span><span class="sxs-lookup"><span data-stu-id="110fb-161">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="110fb-162">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="110fb-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="110fb-163">0</span><span class="sxs-lookup"><span data-stu-id="110fb-163">0</span></span>  <br/> <span data-ttu-id="110fb-164">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="110fb-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![從下拉式清單中選擇 [類型]](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="110fb-166">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="110fb-166">Select **add record**.</span></span>
    
    ![選取 [新增記錄]](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="110fb-168">如果**mx （郵件交換器）** 區段中有任何其他 MX 記錄，請將其刪除。</span><span class="sxs-lookup"><span data-stu-id="110fb-168">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="110fb-169">若為其他其中一個 MX 記錄，請選取 [**刪除]。**</span><span class="sxs-lookup"><span data-stu-id="110fb-169">For one of the other MX records, select **Delete.**</span></span>
    
    ![針對每個額外的 MX 記錄選取 [刪除]](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="110fb-171">在 [確認] 對話方塊中，選取 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="110fb-171">In the confirmation dialog box, select **OK**.</span></span>
    
    ![選取 [確定]](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="110fb-173">使用相同的程序，刪除所列出的任何其他 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-173">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="110fb-174">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="110fb-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="110fb-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="110fb-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="110fb-176">首先請用[這個連結](https://my.bluehost.com/cgi/dm)移至 Bluehost 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="110fb-176">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="110fb-177">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="110fb-177">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="110fb-178">在 [**網域**] 頁面的 [**網域**] 區域中，尋找您要變更之網域的列，然後選取該網域的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="110fb-178">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="110fb-179">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="110fb-179">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="110fb-180">在 [ ***domain_name*** ] 區域的 [ **DNS 區域編輯器**] 列中，選取 [**管理 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="110fb-180">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="110fb-181">在 [ **A （主機）** 記錄] 區段中，找到**自動**探索記錄的列，然後針對該列選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="110fb-181">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="110fb-182">在新增 Microsoft 所需的**自動**探索記錄之前，您必須*先*刪除現有的**自動**探索記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-182">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="110fb-183">Bluehost 不允許您同時維護兩個**自動**探索記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![選取 [刪除]](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="110fb-185">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="110fb-185">Select **OK**.</span></span>
    
    ![選取 [確定]](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="110fb-187">建立六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="110fb-187">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="110fb-188">在 [ **DNS 區域編輯器**] 頁面的 [**新增 DNS 記錄**] 區域，于新記錄的方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="110fb-188">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="110fb-189">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="110fb-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="110fb-190">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="110fb-190">**Host Record**</span></span>|<span data-ttu-id="110fb-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="110fb-191">**TTL**</span></span>|<span data-ttu-id="110fb-192">**類型**</span><span class="sxs-lookup"><span data-stu-id="110fb-192">**Type**</span></span>|<span data-ttu-id="110fb-193">**指向**</span><span class="sxs-lookup"><span data-stu-id="110fb-193">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="110fb-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="110fb-194">autodiscover</span></span>  <br/> |<span data-ttu-id="110fb-195">14400</span><span class="sxs-lookup"><span data-stu-id="110fb-195">14400</span></span>  <br/> |<span data-ttu-id="110fb-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="110fb-196">CNAME</span></span>  <br/> |<span data-ttu-id="110fb-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="110fb-197">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="110fb-198">sip</span><span class="sxs-lookup"><span data-stu-id="110fb-198">sip</span></span>  <br/> |<span data-ttu-id="110fb-199">14400</span><span class="sxs-lookup"><span data-stu-id="110fb-199">14400</span></span>  <br/> |<span data-ttu-id="110fb-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="110fb-200">CNAME</span></span>  <br/> |<span data-ttu-id="110fb-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="110fb-201">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="110fb-202">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="110fb-202">lyncdiscover</span></span>  <br/> |<span data-ttu-id="110fb-203">14400</span><span class="sxs-lookup"><span data-stu-id="110fb-203">14400</span></span>  <br/> |<span data-ttu-id="110fb-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="110fb-204">CNAME</span></span>  <br/> |<span data-ttu-id="110fb-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="110fb-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="110fb-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="110fb-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="110fb-207">14400</span><span class="sxs-lookup"><span data-stu-id="110fb-207">14400</span></span>  <br/> |<span data-ttu-id="110fb-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="110fb-208">CNAME</span></span>  <br/> |<span data-ttu-id="110fb-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="110fb-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="110fb-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="110fb-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="110fb-211">14400</span><span class="sxs-lookup"><span data-stu-id="110fb-211">14400</span></span>  <br/> |<span data-ttu-id="110fb-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="110fb-212">CNAME</span></span>  <br/> |<span data-ttu-id="110fb-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="110fb-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![建立第一個 CNAME 記錄](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="110fb-215">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="110fb-215">Select **add record**.</span></span>
    
    ![選取 [新增記錄]](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="110fb-217">逐一新增其餘五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-217">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="110fb-218">仍然在 [**新增 DNS 記錄**] 區段中，使用表格中下一列的值來建立記錄，然後再選取 [**新增記錄**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-218">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="110fb-219">重複這個程序，直到六筆 CNAME 記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="110fb-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="110fb-220">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="110fb-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="110fb-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="110fb-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="110fb-222">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="110fb-223">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="110fb-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="110fb-224">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="110fb-225">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="110fb-226">需要範例？</span><span class="sxs-lookup"><span data-stu-id="110fb-226">Need examples?</span></span> <span data-ttu-id="110fb-227">請參閱這些 [Microsoft 的外部網域名稱系統記錄](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)。</span><span class="sxs-lookup"><span data-stu-id="110fb-227">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="110fb-228">若要驗證您的 SPF 記錄，您可以使用其中一種[spf 驗證工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="110fb-228">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="110fb-229">首先請用[這個連結](https://my.bluehost.com/cgi/dm)移至 Bluehost 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="110fb-229">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="110fb-230">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="110fb-230">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="110fb-231">在 [**網域**] 頁面的 [**網域**] 區域中，尋找您要變更之網域的列，然後選取該網域的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="110fb-231">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="110fb-232">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="110fb-232">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="110fb-233">在 [ ***domain_name*** ] 區域的 [ **DNS 區域編輯器**] 列中，選取 [**管理 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="110fb-233">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="110fb-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="110fb-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="110fb-235">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="110fb-235">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="110fb-236">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="110fb-236">**Host Record**</span></span>|<span data-ttu-id="110fb-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="110fb-237">**TTL**</span></span>|<span data-ttu-id="110fb-238">**類型**</span><span class="sxs-lookup"><span data-stu-id="110fb-238">**Type**</span></span>|<span data-ttu-id="110fb-239">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="110fb-239">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="110fb-240">14400</span><span class="sxs-lookup"><span data-stu-id="110fb-240">14400</span></span>  <br/> |<span data-ttu-id="110fb-241">TXT</span><span class="sxs-lookup"><span data-stu-id="110fb-241">TXT</span></span>  <br/> |<span data-ttu-id="110fb-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="110fb-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="110fb-243">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="110fb-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![複製 TXT 值](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="110fb-245">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="110fb-245">Select **add record**.</span></span>
    
    ![選取 [新增記錄]](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="110fb-247">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="110fb-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="110fb-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="110fb-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="110fb-249">首先請用[這個連結](https://my.bluehost.com/cgi/dm)移至 Bluehost 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="110fb-249">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="110fb-250">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="110fb-250">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="110fb-251">在 [**網域**] 頁面的 [**網域**] 區域中，尋找您要變更之網域的列，然後選取該網域的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="110fb-251">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="110fb-252">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="110fb-252">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="110fb-253">在 [ ***domain_name*** ] 區域的 [ **DNS 區域編輯器**] 列中，選取 [**管理 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="110fb-253">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="110fb-254">建立兩筆 SRV 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="110fb-254">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="110fb-255">在 [ **DNS 區域編輯器**] 頁面的 [**新增 DNS 記錄**] 區域，于新記錄的方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="110fb-255">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="110fb-256">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="110fb-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="110fb-257">**服務**</span><span class="sxs-lookup"><span data-stu-id="110fb-257">**Service**</span></span>|<span data-ttu-id="110fb-258">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="110fb-258">**Protocol**</span></span>|<span data-ttu-id="110fb-259">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="110fb-259">**Host**</span></span>|<span data-ttu-id="110fb-260">**TTL**</span><span class="sxs-lookup"><span data-stu-id="110fb-260">**TTL**</span></span>|<span data-ttu-id="110fb-261">**類型**</span><span class="sxs-lookup"><span data-stu-id="110fb-261">**Type**</span></span>|<span data-ttu-id="110fb-262">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="110fb-262">**Priority**</span></span>|<span data-ttu-id="110fb-263">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="110fb-263">**Weight**</span></span>|<span data-ttu-id="110fb-264">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="110fb-264">**Port**</span></span>|<span data-ttu-id="110fb-265">**指向**</span><span class="sxs-lookup"><span data-stu-id="110fb-265">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="110fb-266">_sip</span><span class="sxs-lookup"><span data-stu-id="110fb-266">_sip</span></span>  <br/> |<span data-ttu-id="110fb-267">_tls</span><span class="sxs-lookup"><span data-stu-id="110fb-267">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="110fb-268">14400</span><span class="sxs-lookup"><span data-stu-id="110fb-268">14400</span></span>  <br/> |<span data-ttu-id="110fb-269">SRV</span><span class="sxs-lookup"><span data-stu-id="110fb-269">SRV</span></span>  <br/> |<span data-ttu-id="110fb-270">100</span><span class="sxs-lookup"><span data-stu-id="110fb-270">100</span></span>  <br/> |<span data-ttu-id="110fb-271">1</span><span class="sxs-lookup"><span data-stu-id="110fb-271">1</span></span>  <br/> |<span data-ttu-id="110fb-272">443</span><span class="sxs-lookup"><span data-stu-id="110fb-272">443</span></span>  <br/> |<span data-ttu-id="110fb-273">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="110fb-273">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="110fb-274">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="110fb-274">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="110fb-275">_tcp</span><span class="sxs-lookup"><span data-stu-id="110fb-275">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="110fb-276">14400</span><span class="sxs-lookup"><span data-stu-id="110fb-276">14400</span></span>  <br/> |<span data-ttu-id="110fb-277">SRV</span><span class="sxs-lookup"><span data-stu-id="110fb-277">SRV</span></span>  <br/> |<span data-ttu-id="110fb-278">100</span><span class="sxs-lookup"><span data-stu-id="110fb-278">100</span></span>  <br/> |<span data-ttu-id="110fb-279">1</span><span class="sxs-lookup"><span data-stu-id="110fb-279">1</span></span>  <br/> |<span data-ttu-id="110fb-280">5061</span><span class="sxs-lookup"><span data-stu-id="110fb-280">5061</span></span>  <br/> |<span data-ttu-id="110fb-281">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="110fb-281">sipfed.online.lync.com</span></span>  <br/> |
   
    ![複製新記錄的值](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="110fb-283">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="110fb-283">Select **add record**.</span></span>
    
    ![選取 [新增記錄]](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="110fb-285">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-285">Add the other SRV record.</span></span>
    
    <span data-ttu-id="110fb-286">仍然在 [**新增 DNS 記錄**] 區段中，使用資料表中另一列的值來建立記錄，然後再選取 [**新增記錄**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="110fb-286">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="110fb-287">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="110fb-287">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="110fb-288">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="110fb-288">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="110fb-289">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="110fb-289">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

