---
title: 在 Register365 建立 Office 365 的 DNS 記錄
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 商務用 Skype 線上商務和 register365 其他服務的 DNS 記錄。
ms.openlocfilehash: 7f9398e14ea5280948829b263d4cd66d61fab682
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362848"
---
# <a name="create-dns-records-at-register365-for-office-365"></a><span data-ttu-id="dc653-103">在 Register365 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="dc653-103">Create DNS records at Register365 for Office 365</span></span>

 <span data-ttu-id="dc653-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="dc653-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="dc653-105">如果 Register365 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="dc653-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="dc653-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="dc653-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="dc653-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="dc653-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="dc653-108">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="dc653-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="dc653-109">新增 Office 365 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="dc653-109">Add the six CNAME records that are required for Office 365</span></span>](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="dc653-110">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="dc653-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="dc653-111">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="dc653-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="dc653-112">在 Office 365 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="dc653-112">After you add these records at Office 365, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="dc653-113">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="dc653-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="dc653-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dc653-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="dc653-117">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="dc653-117">Add a TXT record for verification</span></span>
<span data-ttu-id="dc653-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="dc653-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="dc653-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="dc653-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc653-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="dc653-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="dc653-p104">首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dc653-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="dc653-126">在 [**儀表板**] 頁面上，尋找您要更新的網域名稱，然後從下拉式清單中選擇 [ **DNS 設定**。</span><span class="sxs-lookup"><span data-stu-id="dc653-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="dc653-127">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-127">(You may have to scroll down.)</span></span>
    
    ![選取清單中的 [DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="dc653-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="dc653-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="dc653-130">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="dc653-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="dc653-131">(如果您需要新增一列，請選取 [**新增 a/cname 記錄 （+）**)。</span><span class="sxs-lookup"><span data-stu-id="dc653-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="dc653-132">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="dc653-133">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="dc653-133">**Host name**</span></span>|<span data-ttu-id="dc653-134">**類型**</span><span class="sxs-lookup"><span data-stu-id="dc653-134">**Type**</span></span>|<span data-ttu-id="dc653-135">**結果**</span><span class="sxs-lookup"><span data-stu-id="dc653-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="dc653-136">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="dc653-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="dc653-137">TXT</span><span class="sxs-lookup"><span data-stu-id="dc653-137">TXT</span></span>  <br/> |<span data-ttu-id="dc653-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="dc653-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="dc653-139">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="dc653-139">**Note:** This is an example.</span></span> <span data-ttu-id="dc653-140">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="dc653-140">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="dc653-141">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="dc653-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![在 [新增/修改 DNS 區域] 頁面上輸入值](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="dc653-143">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc653-143">Select **Save**.</span></span>
    
    <span data-ttu-id="dc653-144">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-144">(You may have to scroll down.)</span></span>
    
    ![選取 [儲存]](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="dc653-146">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="dc653-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="dc653-147">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="dc653-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="dc653-148">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="dc653-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="dc653-149">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="dc653-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="dc653-150">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="dc653-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="dc653-151">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="dc653-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="dc653-152">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="dc653-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="dc653-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dc653-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="dc653-156">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="dc653-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="dc653-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="dc653-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="dc653-p107">首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dc653-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="dc653-161">在 [**儀表板**] 頁面上，尋找您要更新的網域名稱，然後從下拉式清單中選擇 [ **DNS 設定**。</span><span class="sxs-lookup"><span data-stu-id="dc653-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="dc653-162">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-162">(You may have to scroll down.)</span></span>
    
    ![選取清單中的 [DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="dc653-164">在 [**新增/修改 DNS 區域**] 頁面中**的郵件交換記錄**] 區段中，於新記錄的方塊中輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dc653-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="dc653-165">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="dc653-166">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="dc653-166">**Host name**</span></span>|<span data-ttu-id="dc653-167">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="dc653-167">**Priority**</span></span>|<span data-ttu-id="dc653-168">**結果**</span><span class="sxs-lookup"><span data-stu-id="dc653-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="dc653-169">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="dc653-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="dc653-170">1</span><span class="sxs-lookup"><span data-stu-id="dc653-170">1</span></span>  <br/> <span data-ttu-id="dc653-171">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc653-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="dc653-172">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dc653-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="dc653-173">**附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="dc653-173">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="dc653-174">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="dc653-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![在 [新增/修改 DNS 區域] 頁面上輸入值](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="dc653-176">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc653-176">Select **Save**.</span></span>
    
    <span data-ttu-id="dc653-177">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-177">(You may have to scroll down.)</span></span>
    
    ![選取 [儲存]](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="dc653-179">如果 [ **Mail exchange records** ] 區段中有任何其他 MX 記錄，刪除每個選取它，然後按鍵盤上的**Delete**鍵。</span><span class="sxs-lookup"><span data-stu-id="dc653-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="dc653-181">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc653-181">Select **Save**.</span></span>
    
    <span data-ttu-id="dc653-182">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-182">(You may have to scroll down.)</span></span>
    
    ![選取 [儲存]](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="dc653-184">新增 Office 365 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="dc653-184">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="dc653-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="dc653-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="dc653-p109">首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dc653-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="dc653-189">在 [**儀表板**] 頁面上，尋找您要更新的網域名稱，然後從下拉式清單中選擇 [ **DNS 設定**。</span><span class="sxs-lookup"><span data-stu-id="dc653-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="dc653-190">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-190">(You may have to scroll down.)</span></span>
    
    ![選取清單中的 [DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="dc653-192">在 [**新增/修改 DNS 區域**] 頁面中 **，CNAME、 AAAA、 TXT 及 NS 記錄**] 區段中，於新記錄的方塊中輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dc653-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="dc653-193">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="dc653-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="dc653-194">(如果您需要新增一列，請選取 [**新增 a/cname 記錄 （+）**)。</span><span class="sxs-lookup"><span data-stu-id="dc653-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="dc653-195">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="dc653-196">主機名稱 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="dc653-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="dc653-197">類型 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="dc653-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="dc653-198">結果 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="dc653-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="dc653-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="dc653-199">autodiscover</span></span>  <br/> |<span data-ttu-id="dc653-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc653-200">CNAME</span></span>  <br/> |<span data-ttu-id="dc653-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dc653-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="dc653-202">sip</span><span class="sxs-lookup"><span data-stu-id="dc653-202">sip</span></span>  <br/> |<span data-ttu-id="dc653-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc653-203">CNAME</span></span>  <br/> |<span data-ttu-id="dc653-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dc653-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="dc653-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="dc653-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="dc653-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc653-206">CNAME</span></span>  <br/> |<span data-ttu-id="dc653-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dc653-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="dc653-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="dc653-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="dc653-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc653-209">CNAME</span></span>  <br/> |<span data-ttu-id="dc653-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="dc653-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="dc653-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="dc653-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="dc653-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc653-212">CNAME</span></span>  <br/> |<span data-ttu-id="dc653-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dc653-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![在 [新增/修改 DNS 區域] 頁面上輸入值](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="dc653-215">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc653-215">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="dc653-217">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="dc653-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="dc653-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="dc653-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc653-219">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="dc653-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="dc653-220">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="dc653-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="dc653-221">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="dc653-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="dc653-222">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="dc653-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="dc653-p111">首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dc653-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="dc653-226">在 [**儀表板**] 頁面上，尋找您要更新的網域名稱，然後從下拉式清單中選擇 [ **DNS 設定**。</span><span class="sxs-lookup"><span data-stu-id="dc653-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="dc653-227">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-227">(You may have to scroll down.)</span></span>
    
    ![選取清單中的 [DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="dc653-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="dc653-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="dc653-230">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="dc653-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="dc653-231">(如果您需要新增一列，請選取 [**新增 a/cname 記錄 （+）**)。</span><span class="sxs-lookup"><span data-stu-id="dc653-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="dc653-232">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="dc653-233">**主機名稱**</span><span class="sxs-lookup"><span data-stu-id="dc653-233">**Host name**</span></span>|<span data-ttu-id="dc653-234">**類型**</span><span class="sxs-lookup"><span data-stu-id="dc653-234">**Type**</span></span>|<span data-ttu-id="dc653-235">**結果**</span><span class="sxs-lookup"><span data-stu-id="dc653-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="dc653-236">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="dc653-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="dc653-237">TXT</span><span class="sxs-lookup"><span data-stu-id="dc653-237">TXT</span></span>  <br/> |<span data-ttu-id="dc653-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="dc653-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="dc653-239">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="dc653-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![在 [新增/修改 DNS 區域] 頁面上輸入值](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="dc653-241">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc653-241">Select **Save**.</span></span>
    
    <span data-ttu-id="dc653-242">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-242">(You may have to scroll down.)</span></span>
    
    ![選取 [儲存]](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="dc653-244">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="dc653-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="dc653-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="dc653-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="dc653-p112">首先請用[這個連結](https://admin.register365.com/dns/)移至 Register365 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dc653-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![[控制台] 登入頁面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="dc653-249">在 [**儀表板**] 頁面上，尋找您要更新的網域名稱，然後從下拉式清單中選擇 [ **DNS 設定**。</span><span class="sxs-lookup"><span data-stu-id="dc653-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="dc653-250">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-250">(You may have to scroll down.)</span></span>
    
    ![選取清單中的 [DNS 設定](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="dc653-252">在 [**新增/修改 DNS 區域**] 頁面中**服務記錄**] 區段中，於新記錄的方塊中輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dc653-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="dc653-253">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="dc653-254">**名稱**</span><span class="sxs-lookup"><span data-stu-id="dc653-254">**Name**</span></span>|<span data-ttu-id="dc653-255">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="dc653-255">**Priority**</span></span>|<span data-ttu-id="dc653-256">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="dc653-256">**Weight**</span></span>|<span data-ttu-id="dc653-257">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="dc653-257">**Port**</span></span>|<span data-ttu-id="dc653-258">**結果**</span><span class="sxs-lookup"><span data-stu-id="dc653-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dc653-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="dc653-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="dc653-260">100</span><span class="sxs-lookup"><span data-stu-id="dc653-260">100</span></span>  <br/> |<span data-ttu-id="dc653-261">1</span><span class="sxs-lookup"><span data-stu-id="dc653-261">1</span></span>  <br/> |<span data-ttu-id="dc653-262">443</span><span class="sxs-lookup"><span data-stu-id="dc653-262">443</span></span>  <br/> |<span data-ttu-id="dc653-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dc653-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="dc653-264">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="dc653-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="dc653-265">100</span><span class="sxs-lookup"><span data-stu-id="dc653-265">100</span></span>  <br/> |<span data-ttu-id="dc653-266">1</span><span class="sxs-lookup"><span data-stu-id="dc653-266">1</span></span>  <br/> |<span data-ttu-id="dc653-267">5061</span><span class="sxs-lookup"><span data-stu-id="dc653-267">5061</span></span>  <br/> |<span data-ttu-id="dc653-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dc653-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![在 [服務記錄] 區段中輸入值](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="dc653-270">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc653-270">Select **Save**.</span></span>
    
    <span data-ttu-id="dc653-271">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dc653-271">(You may have to scroll down.)</span></span>
    
    ![選取 [儲存]](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="dc653-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dc653-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
