---
title: 在 Register365 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Register365。
ms.openlocfilehash: 056d4dbf923c49b0586ed556f1844cd3b29abe75
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048888"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="0132e-103">在 Register365 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="0132e-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="0132e-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="0132e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0132e-105">如果 Register365 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="0132e-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="0132e-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="0132e-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="0132e-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="0132e-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="0132e-108">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="0132e-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="0132e-109">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="0132e-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="0132e-110">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="0132e-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="0132e-111">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="0132e-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="0132e-112">在 Microsoft 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="0132e-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="0132e-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="0132e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0132e-116">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="0132e-116">Add a TXT record for verification</span></span>
<span data-ttu-id="0132e-117"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0132e-117"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0132e-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="0132e-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0132e-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="0132e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0132e-p104">首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="0132e-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="0132e-125">在 [**儀表板**] 頁面上，找到您要更新的功能變數名稱，然後從下拉式清單中選擇 [ **DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="0132e-125">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="0132e-126">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-126">(You may have to scroll down.)</span></span>
    
    ![選取清單中的 DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="0132e-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0132e-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0132e-129">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0132e-129">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="0132e-130">（如果您需要新增一列，請選取 **[新增 A/CNAME 記錄] （+）**。）</span><span class="sxs-lookup"><span data-stu-id="0132e-130">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="0132e-131">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-131">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="0132e-132">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="0132e-132">**Host name**</span></span>|<span data-ttu-id="0132e-133">**類型**</span><span class="sxs-lookup"><span data-stu-id="0132e-133">**Type**</span></span>|<span data-ttu-id="0132e-134">**結果**</span><span class="sxs-lookup"><span data-stu-id="0132e-134">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="0132e-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="0132e-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="0132e-136">TXT</span><span class="sxs-lookup"><span data-stu-id="0132e-136">TXT</span></span>  <br/> |<span data-ttu-id="0132e-137">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0132e-137">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0132e-138">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="0132e-138">**Note:** This is an example.</span></span> <span data-ttu-id="0132e-139">在這裡請使用您自己來自表格的 [目的地或指向位址]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="0132e-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="0132e-140">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="0132e-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![在 [Add/Modify DNS 區域] 頁面上輸入值](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="0132e-142">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0132e-142">Select **Save**.</span></span>
    
    <span data-ttu-id="0132e-143">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-143">(You may have to scroll down.)</span></span>
    
    ![選取 [儲存]](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="0132e-145">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="0132e-145">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0132e-146">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="0132e-146">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="0132e-147">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="0132e-147">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0132e-148">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="0132e-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="0132e-149">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="0132e-149">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="0132e-150">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="0132e-150">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="0132e-151">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="0132e-151">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="0132e-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="0132e-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0132e-155">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="0132e-155">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0132e-156"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0132e-156"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="0132e-p107">首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="0132e-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="0132e-160">在 [**儀表板**] 頁面上，找到您要更新的功能變數名稱，然後從下拉式清單中選擇 [ **DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="0132e-160">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="0132e-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-161">(You may have to scroll down.)</span></span>
    
    ![選取清單中的 DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="0132e-163">在 [ **ADD/MODIFY DNS 區域**] 頁面的 [**郵件交換記錄**] 區段中，于新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="0132e-163">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0132e-164">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-164">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="0132e-165">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="0132e-165">**Host name**</span></span>|<span data-ttu-id="0132e-166">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="0132e-166">**Priority**</span></span>|<span data-ttu-id="0132e-167">**結果**</span><span class="sxs-lookup"><span data-stu-id="0132e-167">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="0132e-168">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="0132e-168">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="0132e-169">1</span><span class="sxs-lookup"><span data-stu-id="0132e-169">1</span></span>  <br/> <span data-ttu-id="0132e-170">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="0132e-170">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="0132e-171">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0132e-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="0132e-172">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="0132e-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="0132e-173">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="0132e-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![在 [Add/Modify DNS 區域] 頁面上輸入值](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="0132e-175">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0132e-175">Select **Save**.</span></span>
    
    <span data-ttu-id="0132e-176">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-176">(You may have to scroll down.)</span></span>
    
    ![選取 [儲存]](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="0132e-178">如果 [**郵件交換記錄**] 區段中有任何其他 MX 記錄，請選取它，然後按鍵盤上的**delete**鍵，逐一刪除。</span><span class="sxs-lookup"><span data-stu-id="0132e-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="0132e-180">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0132e-180">Select **Save**.</span></span>
    
    <span data-ttu-id="0132e-181">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-181">(You may have to scroll down.)</span></span>
    
    ![選取 [儲存]](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0132e-183">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="0132e-183">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0132e-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0132e-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="0132e-p109">首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="0132e-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="0132e-188">在 [**儀表板**] 頁面上，找到您要更新的功能變數名稱，然後從下拉式清單中選擇 [ **DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="0132e-188">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="0132e-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-189">(You may have to scroll down.)</span></span>
    
    ![選取清單中的 DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="0132e-191">在 [ **ADD/MODIFY DNS 區域**] 頁面的 [ **A，CNAME，AAAA，TXT 和 NS 記錄**] 區段中，于新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="0132e-191">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0132e-192">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0132e-192">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="0132e-193">（如果您需要新增一列，請選取 **[新增 A/CNAME 記錄] （+）**。）</span><span class="sxs-lookup"><span data-stu-id="0132e-193">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="0132e-194">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-194">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="0132e-195">主機名稱 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="0132e-195">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="0132e-196">類型 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="0132e-196">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="0132e-197">Result \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="0132e-197">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="0132e-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0132e-198">autodiscover</span></span>  <br/> |<span data-ttu-id="0132e-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="0132e-199">CNAME</span></span>  <br/> |<span data-ttu-id="0132e-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0132e-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="0132e-201">sip</span><span class="sxs-lookup"><span data-stu-id="0132e-201">sip</span></span>  <br/> |<span data-ttu-id="0132e-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="0132e-202">CNAME</span></span>  <br/> |<span data-ttu-id="0132e-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0132e-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0132e-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0132e-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0132e-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="0132e-205">CNAME</span></span>  <br/> |<span data-ttu-id="0132e-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0132e-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0132e-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0132e-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0132e-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="0132e-208">CNAME</span></span>  <br/> |<span data-ttu-id="0132e-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="0132e-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="0132e-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0132e-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0132e-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="0132e-211">CNAME</span></span>  <br/> |<span data-ttu-id="0132e-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0132e-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![在 [Add/Modify DNS 區域] 頁面上輸入值](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="0132e-214">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0132e-214">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0132e-216">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="0132e-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0132e-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0132e-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0132e-218">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="0132e-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0132e-219">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="0132e-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0132e-220">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="0132e-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0132e-221">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="0132e-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="0132e-p111">首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="0132e-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="0132e-225">在 [**儀表板**] 頁面上，找到您要更新的功能變數名稱，然後從下拉式清單中選擇 [ **DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="0132e-225">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="0132e-226">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-226">(You may have to scroll down.)</span></span>
    
    ![選取清單中的 DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="0132e-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0132e-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0132e-229">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0132e-229">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="0132e-230">（如果您需要新增一列，請選取 **[新增 A/CNAME 記錄] （+）**。）</span><span class="sxs-lookup"><span data-stu-id="0132e-230">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="0132e-231">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-231">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="0132e-232">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="0132e-232">**Host name**</span></span>|<span data-ttu-id="0132e-233">**類型**</span><span class="sxs-lookup"><span data-stu-id="0132e-233">**Type**</span></span>|<span data-ttu-id="0132e-234">**結果**</span><span class="sxs-lookup"><span data-stu-id="0132e-234">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="0132e-235">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="0132e-235">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="0132e-236">TXT</span><span class="sxs-lookup"><span data-stu-id="0132e-236">TXT</span></span>  <br/> |<span data-ttu-id="0132e-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0132e-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="0132e-238">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="0132e-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![在 [Add/Modify DNS 區域] 頁面上輸入值](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="0132e-240">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0132e-240">Select **Save**.</span></span>
    
    <span data-ttu-id="0132e-241">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-241">(You may have to scroll down.)</span></span>
    
    ![選取 [儲存]](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0132e-243">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="0132e-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="0132e-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0132e-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="0132e-p112">首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="0132e-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="0132e-248">在 [**儀表板**] 頁面上，找到您要更新的功能變數名稱，然後從下拉式清單中選擇 [ **DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="0132e-248">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="0132e-249">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-249">(You may have to scroll down.)</span></span>
    
    ![選取清單中的 DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="0132e-251">在 [ **ADD/MODIFY DNS 區域**] 頁面上的 [**服務記錄**] 區段中，于新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="0132e-251">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0132e-252">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-252">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="0132e-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="0132e-253">**Name**</span></span>|<span data-ttu-id="0132e-254">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="0132e-254">**Priority**</span></span>|<span data-ttu-id="0132e-255">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="0132e-255">**Weight**</span></span>|<span data-ttu-id="0132e-256">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="0132e-256">**Port**</span></span>|<span data-ttu-id="0132e-257">**結果**</span><span class="sxs-lookup"><span data-stu-id="0132e-257">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0132e-258">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="0132e-258">_sip._tls</span></span>  <br/> |<span data-ttu-id="0132e-259">100</span><span class="sxs-lookup"><span data-stu-id="0132e-259">100</span></span>  <br/> |<span data-ttu-id="0132e-260">1</span><span class="sxs-lookup"><span data-stu-id="0132e-260">1</span></span>  <br/> |<span data-ttu-id="0132e-261">443</span><span class="sxs-lookup"><span data-stu-id="0132e-261">443</span></span>  <br/> |<span data-ttu-id="0132e-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0132e-262">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0132e-263">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="0132e-263">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="0132e-264">100</span><span class="sxs-lookup"><span data-stu-id="0132e-264">100</span></span>  <br/> |<span data-ttu-id="0132e-265">1</span><span class="sxs-lookup"><span data-stu-id="0132e-265">1</span></span>  <br/> |<span data-ttu-id="0132e-266">5061</span><span class="sxs-lookup"><span data-stu-id="0132e-266">5061</span></span>  <br/> |<span data-ttu-id="0132e-267">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0132e-267">sipfed.online.lync.com</span></span>  <br/> |
   
    ![在 [服務記錄] 區段中輸入值](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="0132e-269">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0132e-269">Select **Save**.</span></span>
    
    <span data-ttu-id="0132e-270">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="0132e-270">(You may have to scroll down.)</span></span>
    
    ![選取 [儲存]](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="0132e-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="0132e-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
