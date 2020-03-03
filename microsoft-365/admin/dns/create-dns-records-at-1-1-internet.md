---
title: 在 1 建立 DNS 記錄&1 IONOS 運作的 Office 365
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: 了解如何驗證您的網域及設定電子郵件、 Skype for Business Online，與其他服務的 DNS 記錄，在 1&1 IONOS 運作的 Office 365。
ms.openlocfilehash: d4ff6bea0d96402c34b1d1ae302510a6e718c38d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352054"
---
# <a name="create-dns-records-at-11-ionos-for-office-365"></a><span data-ttu-id="d1572-103">在 1 建立 DNS 記錄&1 IONOS 運作的 Office 365</span><span class="sxs-lookup"><span data-stu-id="d1572-103">Create DNS records at 1&1 IONOS for Office 365</span></span>

 <span data-ttu-id="d1572-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="d1572-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="d1572-105">請注意該 1&1 IONOS 不允許網域同時有 MX 記錄和頂層自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="d1572-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="d1572-106">這會限制您可設定 Exchange Online for Office 365 的方式。</span><span class="sxs-lookup"><span data-stu-id="d1572-106">This limits the ways in which you can configure Exchange Online for Office 365.</span></span> <span data-ttu-id="d1572-107">沒有因應措施，但建議採用它**僅限**如果您已在 1 建立子網域的經驗&1 IONOS。</span><span class="sxs-lookup"><span data-stu-id="d1572-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="d1572-108">如果您選擇此[服務限制](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)儘管 1 管理自己的 Office 365 DNS 記錄 >&1 IONOS，請依照本文中若要確認您的網域和設定 DNS 記錄的電子郵件、 Skype for Business Online，依此類推。</span><span class="sxs-lookup"><span data-stu-id="d1572-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Office 365 DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="d1572-109">在 1 新增這些記錄之後&1 IONOS，您的網域就會設定為搭配 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="d1572-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="d1572-110">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="d1572-110">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1572-111">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d1572-111">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d1572-112">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="d1572-112">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d1572-113">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d1572-113">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d1572-114">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="d1572-114">Add a TXT record for verification</span></span>

<span data-ttu-id="d1572-p103">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="d1572-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1572-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="d1572-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="d1572-119">請依照下列步驟操作或[觀看影片 (從 0:42 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d1572-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d1572-120">若要開始，移至您的網域頁面 1&1 IONOS 藉由使用[此連結](https://my.1and1.com/)。</span><span class="sxs-lookup"><span data-stu-id="d1572-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="d1572-121">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="d1572-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="d1572-122">選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="d1572-123">在 [**網域中心**] 頁面上，尋找您要更新的網域，然後選取該網域的**Panel** ( **v**) 控制項。</span><span class="sxs-lookup"><span data-stu-id="d1572-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="d1572-124">在 [**網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="d1572-125">在 [ **TXT 和 SRV 記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="d1572-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d1572-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d1572-127">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d1572-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="d1572-128">**類型**</span><span class="sxs-lookup"><span data-stu-id="d1572-128">**Type**</span></span> <br/> |<span data-ttu-id="d1572-129">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="d1572-129">**Prefix**</span></span> <br/> |<span data-ttu-id="d1572-130">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="d1572-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="d1572-131">TXT</span><span class="sxs-lookup"><span data-stu-id="d1572-131">TXT</span></span>  <br/> |<span data-ttu-id="d1572-132">（將此欄位保留空白）</span><span class="sxs-lookup"><span data-stu-id="d1572-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="d1572-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d1572-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d1572-134">附註： 這是範例。</span><span class="sxs-lookup"><span data-stu-id="d1572-134">NOTE: This is an example.</span></span> <span data-ttu-id="d1572-135">在這裡請使用您自己的 **[目的地或指向位址]** 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="d1572-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="d1572-136">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="d1572-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="d1572-137">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d1572-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="d1572-138">選取 [**儲存**一次。</span><span class="sxs-lookup"><span data-stu-id="d1572-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="d1572-139">在 [**編輯 DNS 設定**] 對話方塊中，選取 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="d1572-140">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="d1572-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d1572-141">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="d1572-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="d1572-142">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="d1572-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d1572-143">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="d1572-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d1572-144">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="d1572-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d1572-145">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="d1572-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d1572-146">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d1572-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d1572-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d1572-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d1572-148">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="d1572-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d1572-149">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d1572-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="d1572-150">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="d1572-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="d1572-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d1572-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="d1572-152">請依照下列步驟操作或[觀看影片 (從 3:22 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d1572-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1572-153">如果您已 1und1.de 註冊，[在此登入](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="d1572-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="d1572-154">若要開始，移至您的網域頁面 1&1 IONOS 藉由使用[此連結](https://my.1and1.com/)。</span><span class="sxs-lookup"><span data-stu-id="d1572-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="d1572-155">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="d1572-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="d1572-156">選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="d1572-157">在 [**網域中心**] 頁面上，尋找您要更新的網域，然後選取該網域的**Panel** ( **v**) 控制項。</span><span class="sxs-lookup"><span data-stu-id="d1572-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="d1572-158">在 [**網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="d1572-159">在 [ **MX 記錄**] 區段中 \* \* 郵件交換程式 （MX 記錄） \* \*] 區域中，選取**其他郵件伺服器**。</span><span class="sxs-lookup"><span data-stu-id="d1572-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="d1572-160">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d1572-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="d1572-161">![1&amp;1-DYN-BP-CONFIGURE-1-設定-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="d1572-162">如果沒有列出任何 MX 記錄，逐一刪除選取的記錄，然後按鍵盤上的**Delete**鍵。</span><span class="sxs-lookup"><span data-stu-id="d1572-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="d1572-163">(如果未列出 MX 記錄，請繼續下一個步驟)。</span><span class="sxs-lookup"><span data-stu-id="d1572-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="d1572-164">![1&amp;1-DYN-BP-CONFIGURE-1-設定-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="d1572-165">在 [ **MX 1** ] 記錄的方塊，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="d1572-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="d1572-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="d1572-166">**MX 1**</span></span>|<span data-ttu-id="d1572-167">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="d1572-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="d1572-168">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d1572-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="d1572-169">附註： 取得您\<網域金鑰\>從您的 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="d1572-169">NOTE: Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="d1572-170">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="d1572-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d1572-171">10 </span><span class="sxs-lookup"><span data-stu-id="d1572-171">10</span></span>  <br/> <span data-ttu-id="d1572-172">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1572-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1 到 1-設定 2 和 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="d1572-174">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d1572-174">Select **Save**.</span></span><br/><span data-ttu-id="d1572-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d1572-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="d1572-176">![1&amp;1-DYN-BP-CONFIGURE-1-設定-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="d1572-177">在 [**編輯 DNS 設定**] 對話方塊中，選取 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="d1572-178">![在 [編輯 DNS 設定] 對話方塊中選取 [是]](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-178">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="d1572-179">新增 Office 365 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="d1572-179">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="d1572-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d1572-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="d1572-181">1&1 IONOS 需要因應措施，以便您可以使用 MX 記錄搭配 CNAME 記錄，所需的 Office 365 電子郵件服務。</span><span class="sxs-lookup"><span data-stu-id="d1572-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Office 365 email services.</span></span> <span data-ttu-id="d1572-182">此因應措施要求您建立一組子網域 1&1 IONOS，然後將它們指派給 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="d1572-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d1572-183">請確認您至少有兩個可用的子網域，才能開始進行此程序。</span><span class="sxs-lookup"><span data-stu-id="d1572-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="d1572-184">建議您使用此解決方案只有當您已在 1 建立子網域的經驗&1 IONOS。</span><span class="sxs-lookup"><span data-stu-id="d1572-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="d1572-185">基本 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="d1572-185">Basic CNAME records</span></span>

<span data-ttu-id="d1572-186">請按照下列步驟操作或[觀看影片 (從 3:57 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d1572-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1572-187">如果您已 1und1.de 註冊，[在此登入](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="d1572-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="d1572-188">若要開始，移至您的網域頁面 1&1 IONOS 藉由使用[此連結](https://my.1and1.com/)。</span><span class="sxs-lookup"><span data-stu-id="d1572-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="d1572-189">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="d1572-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="d1572-190">選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="d1572-191">在 [**網域中心**] 頁面上，尋找您要更新的網域，然後選取**管理子網域**。</span><span class="sxs-lookup"><span data-stu-id="d1572-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="d1572-192">![1&amp;1-DYN-BP-CONFIGURE-1-設定-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="d1572-193">現在您將建立兩個子網域，並為每個設定**別名**值。</span><span class="sxs-lookup"><span data-stu-id="d1572-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="d1572-194">(這是必要的因為 1&1 IONOS 支援只有一個頂層 CNAME 記錄，但 Office 365 需要多筆 CNAME 記錄。)</span><span class="sxs-lookup"><span data-stu-id="d1572-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Office 365 requires several CNAME records.)</span></span><br/><span data-ttu-id="d1572-195">首先，建立自動探索子網域。</span><span class="sxs-lookup"><span data-stu-id="d1572-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="d1572-196">在 [ **Subdomain Overview** ] 區段中，選取 [ **Create Subdomain**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-設定-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="d1572-198">在 [新的子網域的 [ **Create Subdomain** ] 方塊中，輸入或複製並貼上只**建立子網域**值從下表。</span><span class="sxs-lookup"><span data-stu-id="d1572-198">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table.</span></span> <span data-ttu-id="d1572-199">（您將在後續步驟中新增**別名**值）。</span><span class="sxs-lookup"><span data-stu-id="d1572-199">(You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="d1572-200">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="d1572-200">**Create Subdomain**</span></span>|<span data-ttu-id="d1572-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d1572-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d1572-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d1572-202">autodiscover</span></span>  <br/> |<span data-ttu-id="d1572-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d1572-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-DYN-BP-CONFIGURE-1-設定-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="d1572-205">選取 [**建立子網域**。</span><span class="sxs-lookup"><span data-stu-id="d1572-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="d1572-206">![1&amp;1-DYN-BP-CONFIGURE-1-設定-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="d1572-207">在 [ **Subdomain Overview** ] 區段中，尋找您剛才建立的**autodiscover**子網域，然後選擇該子網域的 [ **Panel (v)** 控制項。</span><span class="sxs-lookup"><span data-stu-id="d1572-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="d1572-208">![1&amp;1-DYN-BP-CONFIGURE-1-設定-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="d1572-209">在**子網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="d1572-210">![1&amp;1-DYN-BP-CONFIGURE-1-設定-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="d1572-211">在 [ **A/aaaa 記錄 （IP 位址）** ] 區段中的**IP 位址 （A 記錄）** 區域中，選取 [ **CNAME**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="d1572-212">![1&amp;1-DYN-BP-CONFIGURE-1-設定-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="d1572-213">在 [**的別名：** 方塊，輸入或複製並貼上使用的**別名**值從下表。</span><span class="sxs-lookup"><span data-stu-id="d1572-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="d1572-214">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="d1572-214">**Create Subdomain**</span></span>|<span data-ttu-id="d1572-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d1572-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d1572-216">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d1572-216">autodiscover</span></span>  <br/> |<span data-ttu-id="d1572-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d1572-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-DYN-BP-CONFIGURE-1-設定-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="d1572-219">選取**我知道**免責聲明的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d1572-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="d1572-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="d1572-221">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d1572-221">Select **Save**.</span></span><br/><span data-ttu-id="d1572-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="d1572-223">額外 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="d1572-223">Additional CNAME records</span></span>

<span data-ttu-id="d1572-p114">下列程序中產生的額外 CNAME 記錄會啟用商務用 Skype Online 服務。您會採用與您已經建立兩筆 CNAME 記錄時所採用的相同步驟。</span><span class="sxs-lookup"><span data-stu-id="d1572-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="d1572-226">建立第三個子網域 (Lyncdiscover)。</span><span class="sxs-lookup"><span data-stu-id="d1572-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="d1572-227">在 [ **Subdomain Overview** ] 區段中，選取 [ **Create Subdomain**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="d1572-228">在 [新的子網域的 [ **Create Subdomain** ] 方塊中，輸入或複製並貼上只**建立子網域**值從下表。</span><span class="sxs-lookup"><span data-stu-id="d1572-228">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table.</span></span> <span data-ttu-id="d1572-229">（您將在後續步驟中新增**別名**值）。</span><span class="sxs-lookup"><span data-stu-id="d1572-229">(You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="d1572-230">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="d1572-230">**Create Subdomain**</span></span>|<span data-ttu-id="d1572-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d1572-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d1572-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d1572-232">lyncdiscover</span></span>   |<span data-ttu-id="d1572-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d1572-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="d1572-234">選取 [**建立子網域**。</span><span class="sxs-lookup"><span data-stu-id="d1572-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="d1572-235">在 [**網域中心**] 頁面上，選取 [**管理子網域**。</span><span class="sxs-lookup"><span data-stu-id="d1572-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="d1572-236">在 [ **Subdomain Overview** ] 區段中，尋找您剛才建立的**lyncdiscover**子網域，然後選擇該子網域的 [ **Panel (v)** 控制項。</span><span class="sxs-lookup"><span data-stu-id="d1572-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="d1572-237">在**子網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="d1572-238">在 [ **A/aaaa 記錄 （IP 位址）** ] 區段中 \* \* IP 位址 （A 記錄） \* \*] 區域中，選取 [ **CNAME**。</span><span class="sxs-lookup"><span data-stu-id="d1572-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="d1572-239">在 [**的別名：** 方塊，輸入或複製並貼上使用的**別名**值從下表。</span><span class="sxs-lookup"><span data-stu-id="d1572-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="d1572-240">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="d1572-240">**Create Subdomain**</span></span>|<span data-ttu-id="d1572-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d1572-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d1572-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d1572-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d1572-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d1572-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="d1572-244">選取 [**我已經知道**免責聲明] 核取方塊，然後選取 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="d1572-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="d1572-245">在 [**編輯 DNS 設定**] 對話方塊中，選取 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="d1572-246">建立第四個子網域 (SIP)：</span><span class="sxs-lookup"><span data-stu-id="d1572-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="d1572-247">在 [ **Subdomain Overview** ] 區段中，選取 [ **Create Subdomain**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="d1572-248">在 [新的子網域的 [ **Create Subdomain** ] 方塊中，輸入或複製並貼上只**建立子網域**值從下表。</span><span class="sxs-lookup"><span data-stu-id="d1572-248">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table.</span></span> <span data-ttu-id="d1572-249">（您將在後續步驟中新增**別名**值）。</span><span class="sxs-lookup"><span data-stu-id="d1572-249">(You'll add the **Alias** value in a later step.)</span></span> <br/>
    
    |<span data-ttu-id="d1572-250">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="d1572-250">**Create Subdomain**</span></span>|<span data-ttu-id="d1572-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d1572-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d1572-252">sip</span><span class="sxs-lookup"><span data-stu-id="d1572-252">sip</span></span>  <br/> |<span data-ttu-id="d1572-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d1572-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="d1572-254">選取 [**建立子網域**。</span><span class="sxs-lookup"><span data-stu-id="d1572-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="d1572-255">在 [**網域中心**] 頁面上，選取 [**管理子網域**。</span><span class="sxs-lookup"><span data-stu-id="d1572-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="d1572-256">在 [ **Subdomain Overview** ] 區段中，尋找您剛才建立的**sip**子網域，然後選擇該子網域的 [ **Panel (v)** 控制項。</span><span class="sxs-lookup"><span data-stu-id="d1572-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="d1572-257">在**子網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="d1572-258">在 [ **A/aaaa 記錄 （IP 位址）** ] 區段中 \* \* IP 位址 （A 記錄） \* \*] 區域中，選取 [ **CNAME**。</span><span class="sxs-lookup"><span data-stu-id="d1572-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="d1572-259">在 [**的別名：** 方塊，輸入或複製並貼上使用的**別名**值從下表。</span><span class="sxs-lookup"><span data-stu-id="d1572-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="d1572-260">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="d1572-260">**Create Subdomain**</span></span>|<span data-ttu-id="d1572-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d1572-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d1572-262">sip</span><span class="sxs-lookup"><span data-stu-id="d1572-262">sip</span></span>  <br/> |<span data-ttu-id="d1572-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d1572-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="d1572-264">選取 [**我已經知道**免責聲明] 核取方塊，然後選取 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="d1572-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="d1572-265">在 [**編輯 DNS 設定**] 對話方塊中，選取 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="d1572-266">MDM 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="d1572-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1572-267">請按照您針對其他四筆 CNAME 記錄所進行的程序執行，但提供下表的值。</span><span class="sxs-lookup"><span data-stu-id="d1572-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="d1572-268">**建立子網域**</span><span class="sxs-lookup"><span data-stu-id="d1572-268">**Create Subdomain**</span></span>|<span data-ttu-id="d1572-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d1572-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d1572-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d1572-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d1572-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d1572-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="d1572-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d1572-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d1572-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d1572-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d1572-274">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="d1572-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1572-275">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="d1572-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d1572-276">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="d1572-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d1572-277">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="d1572-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="d1572-278">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="d1572-278">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="d1572-279">需要範例？</span><span class="sxs-lookup"><span data-stu-id="d1572-279">Need examples?</span></span> <span data-ttu-id="d1572-280">請參閱這些 [Office 365 的外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)。</span><span class="sxs-lookup"><span data-stu-id="d1572-280">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="d1572-281">若要驗證您的 SPF 記錄，您可以使用其中一種[SPF 驗證工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="d1572-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="d1572-282">請依照下列步驟操作或[觀看影片 (從 5:09 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d1572-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1572-283">如果您已 1und1.de 註冊，[在此登入](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="d1572-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="d1572-284">若要開始，移至您的網域頁面 1&1 IONOS 藉由使用[此連結](https://my.1and1.com/)。</span><span class="sxs-lookup"><span data-stu-id="d1572-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="d1572-285">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="d1572-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="d1572-286">選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="d1572-287">在 [**網域中心**] 頁面上，尋找您要更新的網域，然後選取該網域的**Panel** (**v**) 控制項。</span><span class="sxs-lookup"><span data-stu-id="d1572-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="d1572-288">在 [**網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="d1572-289">在 [ **TXT 和 SRV 記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="d1572-290">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d1572-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="d1572-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d1572-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="d1572-292">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d1572-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="d1572-293">**類型**</span><span class="sxs-lookup"><span data-stu-id="d1572-293">**Type**</span></span>|<span data-ttu-id="d1572-294">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="d1572-294">**Prefix**</span></span>|<span data-ttu-id="d1572-295">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="d1572-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d1572-296">TXT</span><span class="sxs-lookup"><span data-stu-id="d1572-296">TXT</span></span>  <br/> |<span data-ttu-id="d1572-297">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d1572-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d1572-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d1572-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d1572-299">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="d1572-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT 記錄](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="d1572-301">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d1572-301">Select **Save**.</span></span><br/><span data-ttu-id="d1572-302">![新增記錄](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="d1572-303">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d1572-303">Select **Save**.</span></span><br/><span data-ttu-id="d1572-304">![儲存記錄](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="d1572-305">在 [**編輯 DNS 設定**] 對話方塊中，選取 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="d1572-306">![在 [編輯 DNS 設定] 對話方塊中選取 [是]](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-306">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="d1572-307">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="d1572-307">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="d1572-308">請依照下列步驟操作或[觀看影片 (從 5:51 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d1572-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1572-309">如果您已 1und1.de 註冊，[在此登入](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="d1572-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="d1572-310">若要開始，移至您的網域頁面 1&1 IONOS 藉由使用[此連結](https://my.1and1.com/)。</span><span class="sxs-lookup"><span data-stu-id="d1572-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="d1572-311">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="d1572-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="d1572-312">選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="d1572-313">在 [**網域中心**] 頁面上，尋找您要更新的網域，然後選取該網域的**Panel** ( **v**) 控制項。</span><span class="sxs-lookup"><span data-stu-id="d1572-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="d1572-314">在 [**網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="d1572-315">在 [ **TXT 和 SRV 記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="d1572-316">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="d1572-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="d1572-317">在 [**新增記錄**] 區域中，於新記錄的方塊中輸入或複製並貼下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="d1572-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="d1572-318">（從下拉式清單選擇 [**類型**] 和 [ **TTL**值）。</span><span class="sxs-lookup"><span data-stu-id="d1572-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d1572-319">**類型**</span><span class="sxs-lookup"><span data-stu-id="d1572-319">**Type**</span></span>|<span data-ttu-id="d1572-320">**Service** (服務)</span><span class="sxs-lookup"><span data-stu-id="d1572-320">**Service**</span></span>|<span data-ttu-id="d1572-321">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="d1572-321">**Protocol**</span></span>|<span data-ttu-id="d1572-322">**名稱**</span><span class="sxs-lookup"><span data-stu-id="d1572-322">**Name**</span></span>|<span data-ttu-id="d1572-323">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="d1572-323">**Host**</span></span>|<span data-ttu-id="d1572-324">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="d1572-324">**Priority**</span></span>|<span data-ttu-id="d1572-325">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="d1572-325">**Weight**</span></span>|<span data-ttu-id="d1572-326">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="d1572-326">**Port**</span></span>|<span data-ttu-id="d1572-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d1572-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d1572-328">SRV</span><span class="sxs-lookup"><span data-stu-id="d1572-328">SRV</span></span>  <br/> |<span data-ttu-id="d1572-329">sip</span><span class="sxs-lookup"><span data-stu-id="d1572-329">sip</span></span>  <br/> |<span data-ttu-id="d1572-330">tls</span><span class="sxs-lookup"><span data-stu-id="d1572-330">tls</span></span>  <br/> |<span data-ttu-id="d1572-331">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d1572-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d1572-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d1572-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="d1572-333">100</span><span class="sxs-lookup"><span data-stu-id="d1572-333">100</span></span>  <br/> |<span data-ttu-id="d1572-334">1</span><span class="sxs-lookup"><span data-stu-id="d1572-334">1</span></span>  <br/> |<span data-ttu-id="d1572-335">443</span><span class="sxs-lookup"><span data-stu-id="d1572-335">443</span></span>  <br/> |<span data-ttu-id="d1572-336">3600 (1 小時)</span><span class="sxs-lookup"><span data-stu-id="d1572-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="d1572-337">SRV</span><span class="sxs-lookup"><span data-stu-id="d1572-337">SRV</span></span>  <br/> |<span data-ttu-id="d1572-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="d1572-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="d1572-339">tcp</span><span class="sxs-lookup"><span data-stu-id="d1572-339">tcp</span></span>  <br/> |<span data-ttu-id="d1572-340">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="d1572-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d1572-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d1572-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="d1572-342">100</span><span class="sxs-lookup"><span data-stu-id="d1572-342">100</span></span>  <br/> |<span data-ttu-id="d1572-343">1</span><span class="sxs-lookup"><span data-stu-id="d1572-343">1</span></span>  <br/> |<span data-ttu-id="d1572-344">5061</span><span class="sxs-lookup"><span data-stu-id="d1572-344">5061</span></span>  <br/> |<span data-ttu-id="d1572-345">3600 (1 小時)</span><span class="sxs-lookup"><span data-stu-id="d1572-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-DYN-BP-CONFIGURE-1-設定-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="d1572-347">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d1572-347">Select **Save**.</span></span> <br/><span data-ttu-id="d1572-348">![1&amp;1-DYN-BP-CONFIGURE-1-設定-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="d1572-349">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d1572-349">Select **Save**.</span></span> <br/><span data-ttu-id="d1572-350">![1&amp;1-DYN-BP-CONFIGURE-1-設定-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="d1572-351">在 [**編輯 DNS 設定**] 對話方塊中，選取 [**是**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="d1572-352">![在 [編輯 DNS 設定] 對話方塊中選取 [是]](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="d1572-352">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="d1572-353">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="d1572-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="d1572-354">在 [ **TXT 和 SRV 記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="d1572-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="d1572-355">在 [**新增記錄**] 區域中，在表格中，使用另一列的值建立記錄，然後再次選擇 [ **Add**、**儲存**及 **[是]** 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="d1572-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d1572-356">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d1572-356">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d1572-357">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="d1572-357">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d1572-358">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d1572-358">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
