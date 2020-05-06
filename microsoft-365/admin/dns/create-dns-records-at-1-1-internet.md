---
title: 在 1&1 IONOS 為 Microsoft 建立 DNS 記錄
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以 1&1 IONOS for Microsoft。
ms.openlocfilehash: 1c32e15be8bfdf9ea29647af511d0f8ff0ac0b57
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049140"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="e1727-103">在 1&1 IONOS 為 Microsoft 建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="e1727-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="e1727-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="e1727-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="e1727-105">請注意，1&1 IONOS 不允許網域同時具有 MX 記錄和最上層自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1727-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="e1727-106">這會限制您可為 Microsoft 設定 Exchange Online 的方式。</span><span class="sxs-lookup"><span data-stu-id="e1727-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="e1727-107">有一種解決方法，但只有在您已具備在 1&1 IONOS 建立子域的經驗時，**才**建議使用此方法。</span><span class="sxs-lookup"><span data-stu-id="e1727-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="e1727-108">> 如果此[服務限制](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)您選擇在 1&1 IONOS 管理您自己的 Microsoft DNS 記錄，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1727-108">> If despite this [service limitation](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="e1727-109">在 1&1 IONOS 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="e1727-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="e1727-110">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="e1727-110">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="e1727-111">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="e1727-111">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="e1727-112">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="e1727-112">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e1727-113">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="e1727-113">Add a TXT record for verification</span></span>

<span data-ttu-id="e1727-p103">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="e1727-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1727-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="e1727-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="e1727-118">請依照下列步驟操作或[觀看影片 (從 0:42 處開始)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。</span><span class="sxs-lookup"><span data-stu-id="e1727-118">Follow the steps below or [watch the video (start at 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
1. <span data-ttu-id="e1727-119">若要開始使用，請移至您的網域頁面，1&1 IONOS，方法是使用[此連結](https://my.1and1.com/)。</span><span class="sxs-lookup"><span data-stu-id="e1727-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e1727-120">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1727-120">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e1727-121">選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-121">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e1727-122">在 [**網域中心**] 頁面上，找到您要更新的網域，然後選取該網域的 [**面板**] （ **v**）控制。</span><span class="sxs-lookup"><span data-stu-id="e1727-122">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e1727-123">在 [**網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-123">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e1727-124">在 [ **TXT 和 SRV 記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-124">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="e1727-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e1727-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e1727-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e1727-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="e1727-127">**類型**</span><span class="sxs-lookup"><span data-stu-id="e1727-127">**Type**</span></span> <br/> |<span data-ttu-id="e1727-128">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="e1727-128">**Prefix**</span></span> <br/> |<span data-ttu-id="e1727-129">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="e1727-129">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="e1727-130">TXT</span><span class="sxs-lookup"><span data-stu-id="e1727-130">TXT</span></span>  <br/> |<span data-ttu-id="e1727-131">（將此欄位保留空白）</span><span class="sxs-lookup"><span data-stu-id="e1727-131">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="e1727-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e1727-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e1727-133">請注意：這是一個範例。</span><span class="sxs-lookup"><span data-stu-id="e1727-133">NOTE: This is an example.</span></span> <span data-ttu-id="e1727-134">在這裡請使用您自己來自表格的 [目的地或指向位址]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="e1727-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="e1727-135">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="e1727-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="e1727-136">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1727-136">Select **Save**.</span></span>
    
8. <span data-ttu-id="e1727-137">再次選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-137">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="e1727-138">在 [**編輯 DNS 設定**] 對話方塊中，選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="e1727-138">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="e1727-139">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="e1727-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e1727-140">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 365 並要求 Microsoft 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="e1727-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="e1727-141">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="e1727-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e1727-142">在 Microsoft 系統管理中心中，移至 [設定]\*\*\*\* \> [網域]<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="e1727-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e1727-143">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="e1727-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e1727-144">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="e1727-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e1727-145">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1727-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e1727-146">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="e1727-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="e1727-147">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="e1727-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="e1727-148">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="e1727-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e1727-149">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="e1727-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e1727-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e1727-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="e1727-151">請依照下列步驟操作或[觀看影片 (從 3:22 處開始)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。</span><span class="sxs-lookup"><span data-stu-id="e1727-151">Follow the steps below or [watch the video (start at 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1727-152">如果您已登錄1und1.de，請[在這裡登入](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="e1727-152">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e1727-153">若要開始使用，請移至您的網域頁面，1&1 IONOS，方法是使用[此連結](https://my.1and1.com/)。</span><span class="sxs-lookup"><span data-stu-id="e1727-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e1727-154">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1727-154">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e1727-155">選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-155">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e1727-156">在 [**網域中心**] 頁面上，找到您要更新的網域，然後選取該網域的 [**面板**] （ **v**）控制。</span><span class="sxs-lookup"><span data-stu-id="e1727-156">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e1727-157">在 [**網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-157">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e1727-158">在 [ **MX 記錄**] 區段的 [**郵件交換器（MX 記錄）** ] 區域中，選取 [**其他郵件伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-158">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="e1727-159">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e1727-159">(You may have to scroll down.)</span></span><br/><span data-ttu-id="e1727-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="e1727-161">如果已列出任何 MX 記錄，請選取該記錄，然後按下鍵盤上的**delete**鍵，以刪除每一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="e1727-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="e1727-162">(如果未列出 MX 記錄，請繼續下一個步驟)。</span><span class="sxs-lookup"><span data-stu-id="e1727-162">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="e1727-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="e1727-164">在 [ **MX 1** ] 記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="e1727-164">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="e1727-165">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="e1727-165">**MX 1**</span></span>|<span data-ttu-id="e1727-166">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="e1727-166">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="e1727-167">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e1727-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="e1727-168">注意：請從\<您的 Microsoft\>帳戶取得您的網域金鑰。</span><span class="sxs-lookup"><span data-stu-id="e1727-168">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="e1727-169">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="e1727-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e1727-170">10 </span><span class="sxs-lookup"><span data-stu-id="e1727-170">10</span></span>  <br/> <span data-ttu-id="e1727-171">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="e1727-171">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | 
    
    ![1和 1-設定2和3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="e1727-173">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1727-173">Select **Save**.</span></span><br/><span data-ttu-id="e1727-174">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e1727-174">(You may have to scroll down.)</span></span><br/><span data-ttu-id="e1727-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="e1727-176">在 [**編輯 DNS 設定**] 對話方塊中，選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="e1727-176">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="e1727-177">![在 [編輯 DNS 設定] 對話方塊中選取 [是]](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-177">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e1727-178">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="e1727-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e1727-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e1727-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="e1727-180">1&1 IONOS 需要一種方法，讓您可以使用 MX 記錄，以及 Microsoft 電子郵件服務所需的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1727-180">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="e1727-181">此項變通方法需要您在 1&1 IONOS，建立一組子域，並將它們指派給 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1727-181">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e1727-182">請確認您至少有兩個可用的子網域，才能開始進行此程序。</span><span class="sxs-lookup"><span data-stu-id="e1727-182">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="e1727-183">只有在您已有在 1&1 IONOS 建立子域的經驗時，才建議使用此解決方案。</span><span class="sxs-lookup"><span data-stu-id="e1727-183">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="e1727-184">基本 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="e1727-184">Basic CNAME records</span></span>

<span data-ttu-id="e1727-185">請按照下列步驟操作或[觀看影片 (從 3:57 處開始)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。</span><span class="sxs-lookup"><span data-stu-id="e1727-185">Follow the steps below or [watch the video (start at 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1727-186">如果您已登錄1und1.de，請[在這裡登入](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="e1727-186">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e1727-187">若要開始使用，請移至您的網域頁面，1&1 IONOS，方法是使用[此連結](https://my.1and1.com/)。</span><span class="sxs-lookup"><span data-stu-id="e1727-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e1727-188">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1727-188">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e1727-189">選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-189">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e1727-190">在 [**網域中心**] 頁面上，尋找您要更新的網域，然後選取 [**管理子域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-190">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="e1727-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="e1727-192">現在您會建立兩個子域，並為每個子域設定一個**別名**值。</span><span class="sxs-lookup"><span data-stu-id="e1727-192">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="e1727-193">（這是必要的，因為 1&1 IONOS 只支援一個最上層 CNAME 記錄，但 Microsoft 需要多個 CNAME 記錄。）</span><span class="sxs-lookup"><span data-stu-id="e1727-193">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="e1727-194">首先，建立自動探索子網域。</span><span class="sxs-lookup"><span data-stu-id="e1727-194">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="e1727-195">在 [**子域一覽**] 區段中，選取 [**建立子域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-195">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-設定-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="e1727-197">在 [**建立**新子域的子域] 方塊中，輸入或複製並貼上下清單格中的 [**建立子域**] 值。</span><span class="sxs-lookup"><span data-stu-id="e1727-197">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table.</span></span> <span data-ttu-id="e1727-198">（您將在稍後的步驟中新增**別名**值。）</span><span class="sxs-lookup"><span data-stu-id="e1727-198">(You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="e1727-199">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="e1727-199">**Create Subdomain**</span></span>|<span data-ttu-id="e1727-200">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e1727-200">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e1727-201">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e1727-201">autodiscover</span></span>  <br/> |<span data-ttu-id="e1727-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e1727-202">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="e1727-204">選取 [**建立子域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-204">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="e1727-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="e1727-206">在 [**子域一覽**] 區段中，找出您剛剛建立的**自動**探索子域，然後選取該子域的 [**面板] （v）** 控制。</span><span class="sxs-lookup"><span data-stu-id="e1727-206">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="e1727-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="e1727-208">在 [**子域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-208">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="e1727-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="e1727-210">在 [ **A/AAAA 記錄（IP 位址）** ] 區段的 [ **IP 位址（A 記錄）** ] 區域中，選取 [ **CNAME**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-210">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="e1727-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="e1727-212">在 [**別名：** ] 方塊中，只輸入或複製並貼上下清單格中的**別名**值。</span><span class="sxs-lookup"><span data-stu-id="e1727-212">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="e1727-213">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="e1727-213">**Create Subdomain**</span></span>|<span data-ttu-id="e1727-214">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e1727-214">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e1727-215">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e1727-215">autodiscover</span></span>  <br/> |<span data-ttu-id="e1727-216">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e1727-216">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="e1727-218">選取 [**我的感知**免責聲明] 的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e1727-218">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="e1727-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="e1727-220">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1727-220">Select **Save**.</span></span><br/><span data-ttu-id="e1727-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="e1727-222">額外 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="e1727-222">Additional CNAME records</span></span>

<span data-ttu-id="e1727-p114">下列程序中產生的額外 CNAME 記錄會啟用商務用 Skype Online 服務。您會採用與您已經建立兩筆 CNAME 記錄時所採用的相同步驟。</span><span class="sxs-lookup"><span data-stu-id="e1727-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="e1727-225">建立第三個子網域 (Lyncdiscover)。</span><span class="sxs-lookup"><span data-stu-id="e1727-225">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="e1727-226">在 [**子域一覽**] 區段中，選取 [**建立子域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-226">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="e1727-227">在 [**建立**新子域的子域] 方塊中，輸入或複製並貼上下清單格中的 [**建立子域**] 值。</span><span class="sxs-lookup"><span data-stu-id="e1727-227">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table.</span></span> <span data-ttu-id="e1727-228">（您將在稍後的步驟中新增**別名**值。）</span><span class="sxs-lookup"><span data-stu-id="e1727-228">(You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="e1727-229">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="e1727-229">**Create Subdomain**</span></span>|<span data-ttu-id="e1727-230">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e1727-230">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e1727-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e1727-231">lyncdiscover</span></span>   |<span data-ttu-id="e1727-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1727-232">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="e1727-233">選取 [**建立子域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-233">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="e1727-234">在 [**網域中心**] 頁面上，選取 [**管理子域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-234">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="e1727-235">在 [**子域一覽**] 區段中，尋找您剛才建立的**lyncdiscover**子域，然後選取該子域的 [**面板] （v）** 控制。</span><span class="sxs-lookup"><span data-stu-id="e1727-235">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="e1727-236">在 [**子域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-236">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="e1727-237">在 [ **A/AAAA 記錄（IP 位址）** ] 區段的 [ **IP 位址（A 記錄）** ] 區域中，選取 [ **CNAME**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-237">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="e1727-238">在 [**別名：** ] 方塊中，只輸入或複製並貼上下清單格中的**別名**值。</span><span class="sxs-lookup"><span data-stu-id="e1727-238">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="e1727-239">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="e1727-239">**Create Subdomain**</span></span>|<span data-ttu-id="e1727-240">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e1727-240">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e1727-241">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e1727-241">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e1727-242">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1727-242">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="e1727-243">選取 [**我的感知**免責聲明] 的核取方塊，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-243">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="e1727-244">在 [**編輯 DNS 設定**] 對話方塊中，選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="e1727-244">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="e1727-245">建立第四個子網域 (SIP)：</span><span class="sxs-lookup"><span data-stu-id="e1727-245">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="e1727-246">在 [**子域一覽**] 區段中，選取 [**建立子域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-246">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="e1727-247">在 [**建立**新子域的子域] 方塊中，輸入或複製並貼上下清單格中的 [**建立子域**] 值。</span><span class="sxs-lookup"><span data-stu-id="e1727-247">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table.</span></span> <span data-ttu-id="e1727-248">（您將在稍後的步驟中新增**別名**值。）</span><span class="sxs-lookup"><span data-stu-id="e1727-248">(You'll add the **Alias** value in a later step.)</span></span> <br/>
    
    |<span data-ttu-id="e1727-249">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="e1727-249">**Create Subdomain**</span></span>|<span data-ttu-id="e1727-250">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e1727-250">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e1727-251">sip</span><span class="sxs-lookup"><span data-stu-id="e1727-251">sip</span></span>  <br/> |<span data-ttu-id="e1727-252">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1727-252">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="e1727-253">選取 [**建立子域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-253">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="e1727-254">在 [**網域中心**] 頁面上，選取 [**管理子域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-254">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="e1727-255">在 [**子域一覽**] 區段中，尋找您剛才建立的**sip**子域，然後為該子域選取**面板（v）** 控制。</span><span class="sxs-lookup"><span data-stu-id="e1727-255">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="e1727-256">在 [**子域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-256">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="e1727-257">在 [ **A/AAAA 記錄（IP 位址）** ] 區段的 [ **IP 位址（A 記錄）** ] 區域中，選取 [ **CNAME**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-257">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="e1727-258">在 [**別名：** ] 方塊中，只輸入或複製並貼上下清單格中的**別名**值。</span><span class="sxs-lookup"><span data-stu-id="e1727-258">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="e1727-259">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="e1727-259">**Create Subdomain**</span></span>|<span data-ttu-id="e1727-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e1727-260">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e1727-261">sip</span><span class="sxs-lookup"><span data-stu-id="e1727-261">sip</span></span>  <br/> |<span data-ttu-id="e1727-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1727-262">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="e1727-263">選取 [**我的感知**免責聲明] 的核取方塊，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-263">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="e1727-264">在 [**編輯 DNS 設定**] 對話方塊中，選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="e1727-264">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="e1727-265">MDM 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="e1727-265">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1727-266">請按照您針對其他四筆 CNAME 記錄所進行的程序執行，但提供下表的值。</span><span class="sxs-lookup"><span data-stu-id="e1727-266">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="e1727-267">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="e1727-267">**Create Subdomain**</span></span>|<span data-ttu-id="e1727-268">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e1727-268">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1727-269">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e1727-269">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e1727-270">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e1727-270">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="e1727-271">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e1727-271">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e1727-272">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e1727-272">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e1727-273">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="e1727-273">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1727-274">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1727-274">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e1727-275">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="e1727-275">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e1727-276">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="e1727-276">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e1727-277">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1727-277">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="e1727-278">需要範例？</span><span class="sxs-lookup"><span data-stu-id="e1727-278">Need examples?</span></span> <span data-ttu-id="e1727-279">請參閱這些 [Microsoft 的外部網域名稱系統記錄](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)。</span><span class="sxs-lookup"><span data-stu-id="e1727-279">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="e1727-280">若要驗證您的 SPF 記錄，您可以使用其中一種[spf 驗證工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="e1727-280">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="e1727-281">請依照下列步驟操作或[觀看影片 (從 5:09 處開始)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。</span><span class="sxs-lookup"><span data-stu-id="e1727-281">Follow the steps below or [watch the video (start at 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1727-282">如果您已登錄1und1.de，請[在這裡登入](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="e1727-282">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e1727-283">若要開始使用，請移至您的網域頁面，1&1 IONOS，方法是使用[此連結](https://my.1and1.com/)。</span><span class="sxs-lookup"><span data-stu-id="e1727-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e1727-284">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1727-284">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e1727-285">選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-285">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e1727-286">在 [**網域中心**] 頁面上，找到您要更新的網域，然後選取該網域的 [**面板**] （**v**）控制。</span><span class="sxs-lookup"><span data-stu-id="e1727-286">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e1727-287">在 [**網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-287">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e1727-288">在 [ **TXT 和 SRV 記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-288">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="e1727-289">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e1727-289">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="e1727-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e1727-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="e1727-291">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e1727-291">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="e1727-292">**類型**</span><span class="sxs-lookup"><span data-stu-id="e1727-292">**Type**</span></span>|<span data-ttu-id="e1727-293">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="e1727-293">**Prefix**</span></span>|<span data-ttu-id="e1727-294">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="e1727-294">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="e1727-295">TXT</span><span class="sxs-lookup"><span data-stu-id="e1727-295">TXT</span></span>  <br/> |<span data-ttu-id="e1727-296">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="e1727-296">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e1727-297">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e1727-297">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e1727-298">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="e1727-298">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT 記錄](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="e1727-300">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1727-300">Select **Save**.</span></span><br/><span data-ttu-id="e1727-301">![新增記錄](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="e1727-302">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1727-302">Select **Save**.</span></span><br/><span data-ttu-id="e1727-303">![儲存記錄](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="e1727-304">在 [**編輯 DNS 設定**] 對話方塊中，選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="e1727-304">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="e1727-305">![在 [編輯 DNS 設定] 對話方塊中選取 [是]](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-305">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e1727-306">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="e1727-306">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="e1727-307">請依照下列步驟操作或[觀看影片 (從 5:51 處開始)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。</span><span class="sxs-lookup"><span data-stu-id="e1727-307">Follow the steps below or [watch the video (start at 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1727-308">如果您已登錄1und1.de，請[在這裡登入](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="e1727-308">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="e1727-309">若要開始使用，請移至您的網域頁面，1&1 IONOS，方法是使用[此連結](https://my.1and1.com/)。</span><span class="sxs-lookup"><span data-stu-id="e1727-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="e1727-310">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e1727-310">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e1727-311">選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-311">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="e1727-312">在 [**網域中心**] 頁面上，找到您要更新的網域，然後選取該網域的 [**面板**] （ **v**）控制。</span><span class="sxs-lookup"><span data-stu-id="e1727-312">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="e1727-313">在 [**網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-313">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="e1727-314">在 [ **TXT 和 SRV 記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-314">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="e1727-315">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="e1727-315">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="e1727-316">在 [ **Add Record** ] （新增記錄）區域的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="e1727-316">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="e1727-317">（從下拉式清單中選擇 [**類型**] 和 [ **TTL** ] 值。）</span><span class="sxs-lookup"><span data-stu-id="e1727-317">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e1727-318">**類型**</span><span class="sxs-lookup"><span data-stu-id="e1727-318">**Type**</span></span>|<span data-ttu-id="e1727-319">**服務**</span><span class="sxs-lookup"><span data-stu-id="e1727-319">**Service**</span></span>|<span data-ttu-id="e1727-320">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="e1727-320">**Protocol**</span></span>|<span data-ttu-id="e1727-321">**Name**</span><span class="sxs-lookup"><span data-stu-id="e1727-321">**Name**</span></span>|<span data-ttu-id="e1727-322">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="e1727-322">**Host**</span></span>|<span data-ttu-id="e1727-323">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="e1727-323">**Priority**</span></span>|<span data-ttu-id="e1727-324">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="e1727-324">**Weight**</span></span>|<span data-ttu-id="e1727-325">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="e1727-325">**Port**</span></span>|<span data-ttu-id="e1727-326">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1727-326">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1727-327">SRV</span><span class="sxs-lookup"><span data-stu-id="e1727-327">SRV</span></span>  <br/> |<span data-ttu-id="e1727-328">sip</span><span class="sxs-lookup"><span data-stu-id="e1727-328">sip</span></span>  <br/> |<span data-ttu-id="e1727-329">tls</span><span class="sxs-lookup"><span data-stu-id="e1727-329">tls</span></span>  <br/> |<span data-ttu-id="e1727-330">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="e1727-330">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e1727-331">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1727-331">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="e1727-332">100</span><span class="sxs-lookup"><span data-stu-id="e1727-332">100</span></span>  <br/> |<span data-ttu-id="e1727-333">1</span><span class="sxs-lookup"><span data-stu-id="e1727-333">1</span></span>  <br/> |<span data-ttu-id="e1727-334">443</span><span class="sxs-lookup"><span data-stu-id="e1727-334">443</span></span>  <br/> |<span data-ttu-id="e1727-335">3600 (1 小時)</span><span class="sxs-lookup"><span data-stu-id="e1727-335">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="e1727-336">SRV</span><span class="sxs-lookup"><span data-stu-id="e1727-336">SRV</span></span>  <br/> |<span data-ttu-id="e1727-337">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e1727-337">sipfederationtls</span></span>  <br/> |<span data-ttu-id="e1727-338">tcp</span><span class="sxs-lookup"><span data-stu-id="e1727-338">tcp</span></span>  <br/> |<span data-ttu-id="e1727-339">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="e1727-339">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="e1727-340">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1727-340">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="e1727-341">100</span><span class="sxs-lookup"><span data-stu-id="e1727-341">100</span></span>  <br/> |<span data-ttu-id="e1727-342">1</span><span class="sxs-lookup"><span data-stu-id="e1727-342">1</span></span>  <br/> |<span data-ttu-id="e1727-343">5061</span><span class="sxs-lookup"><span data-stu-id="e1727-343">5061</span></span>  <br/> |<span data-ttu-id="e1727-344">3600 (1 小時)</span><span class="sxs-lookup"><span data-stu-id="e1727-344">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="e1727-346">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1727-346">Select **Save**.</span></span> <br/><span data-ttu-id="e1727-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="e1727-348">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1727-348">Select **Save**.</span></span> <br/><span data-ttu-id="e1727-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="e1727-350">在 [**編輯 DNS 設定**] 對話方塊中，選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="e1727-350">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="e1727-351">![在 [編輯 DNS 設定] 對話方塊中選取 [是]](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="e1727-351">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="e1727-352">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="e1727-352">Add the other SRV record.</span></span> <br/><span data-ttu-id="e1727-353">在 [ **TXT 和 SRV 記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e1727-353">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="e1727-354">在 [**新增記錄**] 區域中，使用表格中另一列的值建立記錄，然後再選取 [**新增**]、[**儲存** **] 及 [是]** 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="e1727-354">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e1727-355">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="e1727-355">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="e1727-356">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="e1727-356">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="e1727-357">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="e1727-357">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
