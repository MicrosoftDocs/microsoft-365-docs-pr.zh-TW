---
title: 在 Microsoft 的 Amazon Web 服務（AWS）上建立 DNS 記錄
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以用於 Microsoft 的 Amazon Web 服務（AWS）。
ms.openlocfilehash: 1ce4d47dce2fce177efafade49b78ea706cf14e2
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919536"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="878a1-103">在 Microsoft 的 Amazon Web 服務（AWS）上建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="878a1-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="878a1-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="878a1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="878a1-105">如果 AWS 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="878a1-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="878a1-106">在 AWS 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="878a1-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="878a1-107">若要深入瞭解具有 Microsfot 之網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="878a1-107">To learn about webhosting and DNS for websites with Microsfot, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="878a1-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="878a1-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="878a1-109">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="878a1-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="878a1-110">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="878a1-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="878a1-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="878a1-111">Add a TXT record for verification</span></span>
<span data-ttu-id="878a1-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="878a1-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="878a1-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="878a1-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="878a1-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="878a1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="878a1-p104">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="878a1-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="878a1-119">在 [**資源**] 頁面上，選取 [**主控區域**]。</span><span class="sxs-lookup"><span data-stu-id="878a1-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="878a1-120">在 [**主控區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="878a1-120">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="878a1-121">選取 [**建立記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="878a1-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="878a1-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="878a1-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="878a1-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="878a1-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="878a1-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="878a1-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="878a1-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="878a1-126">**Name**</span></span> <br/> |<span data-ttu-id="878a1-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="878a1-127">**Type**</span></span> <br/> |<span data-ttu-id="878a1-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="878a1-128">**Alias**</span></span> <br/> |<span data-ttu-id="878a1-129">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="878a1-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="878a1-130">**值**</span><span class="sxs-lookup"><span data-stu-id="878a1-130">**Value**</span></span> <br/> |<span data-ttu-id="878a1-131">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="878a1-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="878a1-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="878a1-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="878a1-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="878a1-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="878a1-134">否</span><span class="sxs-lookup"><span data-stu-id="878a1-134">No</span></span>  <br/> |<span data-ttu-id="878a1-135">300</span><span class="sxs-lookup"><span data-stu-id="878a1-135">300</span></span>  <br/> |<span data-ttu-id="878a1-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="878a1-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="878a1-137">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="878a1-137">**Note:** This is an example.</span></span> <span data-ttu-id="878a1-138">在這裡請使用您自己的 [目的地或指向位址]\*\*\*\* 值，請參閱 Microsoft 365 表格。</span><span class="sxs-lookup"><span data-stu-id="878a1-138">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="878a1-139">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="878a1-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="878a1-140">簡易</span><span class="sxs-lookup"><span data-stu-id="878a1-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="878a1-141">選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="878a1-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="878a1-142">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="878a1-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="878a1-143">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。</span><span class="sxs-lookup"><span data-stu-id="878a1-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="878a1-144">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="878a1-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="878a1-145">在 Microsoft 系統管理中心中，移至 [設定]\*\*\*\* \> [網域]<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="878a1-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="878a1-146">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="878a1-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="878a1-147">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="878a1-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="878a1-148">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="878a1-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="878a1-149">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="878a1-149">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="878a1-150">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="878a1-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="878a1-151">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="878a1-151">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="878a1-152">新增 MX 記錄，使您網域的電子郵件將會傳送至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="878a1-152">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="878a1-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="878a1-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="878a1-154">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="878a1-154">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="878a1-155">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="878a1-155">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="878a1-156">在 [**資源**] 頁面上，選取 [**主控區域**]。</span><span class="sxs-lookup"><span data-stu-id="878a1-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="878a1-157">在 [**主控區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="878a1-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="878a1-158">選取 [**建立記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="878a1-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="878a1-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="878a1-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="878a1-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="878a1-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="878a1-161">**Name**</span><span class="sxs-lookup"><span data-stu-id="878a1-161">**Name**</span></span>|<span data-ttu-id="878a1-162">**Type**</span><span class="sxs-lookup"><span data-stu-id="878a1-162">**Type**</span></span>|<span data-ttu-id="878a1-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="878a1-163">**Alias**</span></span>|<span data-ttu-id="878a1-164">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="878a1-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="878a1-165">**值**</span><span class="sxs-lookup"><span data-stu-id="878a1-165">**Value**</span></span>|<span data-ttu-id="878a1-166">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="878a1-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="878a1-167">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="878a1-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="878a1-168">MX - 郵件交換</span><span class="sxs-lookup"><span data-stu-id="878a1-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="878a1-169">否</span><span class="sxs-lookup"><span data-stu-id="878a1-169">No</span></span>  <br/> |<span data-ttu-id="878a1-170">300</span><span class="sxs-lookup"><span data-stu-id="878a1-170">300</span></span>  <br/> |<span data-ttu-id="878a1-171">0  *\<網域金鑰\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="878a1-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="878a1-p109">0 是指 MX 優先順序值。將它新增到 MX 值的開頭，以空格分隔該值的其餘部分。  </span><span class="sxs-lookup"><span data-stu-id="878a1-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="878a1-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="878a1-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="878a1-175">**附注：** 從 Microsoft \<365 帳戶取得您的*網域金鑰*\> 。</span><span class="sxs-lookup"><span data-stu-id="878a1-175">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="878a1-176">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="878a1-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="878a1-177">簡易</span><span class="sxs-lookup"><span data-stu-id="878a1-177">Simple</span></span>  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="878a1-179">選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="878a1-179">Select **Create**.</span></span>
    
    ![AWS-BP-設定-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="878a1-181">如果有任何其他的 MX 記錄，請移除它們。</span><span class="sxs-lookup"><span data-stu-id="878a1-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="878a1-182">AWS 會將 MX 記錄儲存為一組可以包含多個記錄的集合。</span><span class="sxs-lookup"><span data-stu-id="878a1-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="878a1-183">**不要**選取 [**刪除記錄集**]，因為這會刪除所有的 MX 記錄，包括剛才新增的記錄。</span><span class="sxs-lookup"><span data-stu-id="878a1-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="878a1-184">請改為依照下列指示操作。</span><span class="sxs-lookup"><span data-stu-id="878a1-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="878a1-185">首先，選取 MX 記錄集。</span><span class="sxs-lookup"><span data-stu-id="878a1-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-設定-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="878a1-187">接下來，在 [**編輯記錄集**] 區域中，選取 [**值**] 方塊中的專案，然後按鍵盤上的**delete**鍵，以刪除每個過時的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="878a1-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-設定-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="878a1-189">選取 [**儲存記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="878a1-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-設定-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="878a1-191">新增 Microsoft 365 所需的五個 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="878a1-191">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="878a1-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="878a1-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="878a1-193">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="878a1-193">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="878a1-194">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="878a1-194">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="878a1-195">在 [**資源**] 頁面上，選取 [**主控區域**]。</span><span class="sxs-lookup"><span data-stu-id="878a1-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="878a1-196">在 [**主控區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="878a1-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="878a1-197">選取 [**建立記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="878a1-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="878a1-198">新增第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="878a1-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="878a1-199">在 [**建立記錄集**] 區域的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="878a1-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="878a1-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="878a1-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="878a1-201">**Name**</span><span class="sxs-lookup"><span data-stu-id="878a1-201">**Name**</span></span>|<span data-ttu-id="878a1-202">**Type**</span><span class="sxs-lookup"><span data-stu-id="878a1-202">**Type**</span></span>|<span data-ttu-id="878a1-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="878a1-203">**Alias**</span></span>|<span data-ttu-id="878a1-204">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="878a1-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="878a1-205">**值**</span><span class="sxs-lookup"><span data-stu-id="878a1-205">**Value**</span></span>|<span data-ttu-id="878a1-206">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="878a1-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="878a1-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="878a1-207">autodiscover</span></span>  <br/> |<span data-ttu-id="878a1-208">CNAME - 正式名稱</span><span class="sxs-lookup"><span data-stu-id="878a1-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="878a1-209">無</span><span class="sxs-lookup"><span data-stu-id="878a1-209">No</span></span>  <br/> |<span data-ttu-id="878a1-210">300</span><span class="sxs-lookup"><span data-stu-id="878a1-210">300</span></span>  <br/> |<span data-ttu-id="878a1-211">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="878a1-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="878a1-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="878a1-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="878a1-213">簡單</span><span class="sxs-lookup"><span data-stu-id="878a1-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="878a1-214">sip</span><span class="sxs-lookup"><span data-stu-id="878a1-214">sip</span></span>  <br/> |<span data-ttu-id="878a1-215">CNAME - 正式名稱</span><span class="sxs-lookup"><span data-stu-id="878a1-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="878a1-216">無</span><span class="sxs-lookup"><span data-stu-id="878a1-216">No</span></span>  <br/> |<span data-ttu-id="878a1-217">300</span><span class="sxs-lookup"><span data-stu-id="878a1-217">300</span></span>  <br/> |<span data-ttu-id="878a1-218">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="878a1-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="878a1-219">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="878a1-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="878a1-220">簡單</span><span class="sxs-lookup"><span data-stu-id="878a1-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="878a1-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="878a1-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="878a1-222">CNAME - 正式名稱</span><span class="sxs-lookup"><span data-stu-id="878a1-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="878a1-223">無</span><span class="sxs-lookup"><span data-stu-id="878a1-223">No</span></span>  <br/> |<span data-ttu-id="878a1-224">300</span><span class="sxs-lookup"><span data-stu-id="878a1-224">300</span></span>  <br/> |<span data-ttu-id="878a1-225">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="878a1-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="878a1-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="878a1-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="878a1-227">簡單</span><span class="sxs-lookup"><span data-stu-id="878a1-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="878a1-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="878a1-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="878a1-229">CNAME - 正式名稱</span><span class="sxs-lookup"><span data-stu-id="878a1-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="878a1-230">無</span><span class="sxs-lookup"><span data-stu-id="878a1-230">No</span></span>  <br/> |<span data-ttu-id="878a1-231">300</span><span class="sxs-lookup"><span data-stu-id="878a1-231">300</span></span>  <br/> |<span data-ttu-id="878a1-232">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="878a1-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="878a1-233">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="878a1-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="878a1-234">簡易</span><span class="sxs-lookup"><span data-stu-id="878a1-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="878a1-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="878a1-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="878a1-236">CNAME - 正式名稱</span><span class="sxs-lookup"><span data-stu-id="878a1-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="878a1-237">無</span><span class="sxs-lookup"><span data-stu-id="878a1-237">No</span></span>  <br/> |<span data-ttu-id="878a1-238">300</span><span class="sxs-lookup"><span data-stu-id="878a1-238">300</span></span>  <br/> |<span data-ttu-id="878a1-239">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="878a1-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="878a1-240">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="878a1-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="878a1-241">簡單</span><span class="sxs-lookup"><span data-stu-id="878a1-241">Simple</span></span>  <br/> |
   
    ![AWS-BP-Configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="878a1-243">選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="878a1-243">Select **Create**.</span></span>
    
    ![AWS-BP-設定-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="878a1-245">新增其他四筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="878a1-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="878a1-246">在 [**主控區域**] 頁面中，選取 [**建立記錄集**]，使用表格中下一列的值建立記錄，然後再選取 [**建立**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="878a1-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="878a1-247">重複此程式，直到您已建立全部五筆 CNAME 記錄為止。</span><span class="sxs-lookup"><span data-stu-id="878a1-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="878a1-248">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="878a1-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="878a1-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="878a1-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="878a1-250">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="878a1-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="878a1-251">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="878a1-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="878a1-252">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="878a1-252">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="878a1-253">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="878a1-253">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="878a1-254">需要範例？</span><span class="sxs-lookup"><span data-stu-id="878a1-254">Need examples?</span></span> <span data-ttu-id="878a1-255">請參閱這些 [Microsoft 的外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)。</span><span class="sxs-lookup"><span data-stu-id="878a1-255">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="878a1-256">若要驗證您的 SPF 記錄，您可以使用其中一種[spf 驗證工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="878a1-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="878a1-257">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="878a1-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="878a1-258">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="878a1-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="878a1-259">在 [**資源**] 頁面上，選取 [**主控區域**]。</span><span class="sxs-lookup"><span data-stu-id="878a1-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="878a1-260">在 [**主控區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="878a1-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="878a1-261">選取**TXT**記錄集。</span><span class="sxs-lookup"><span data-stu-id="878a1-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-設定-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="878a1-263">在 [**編輯記錄集**] 區域中，于現有記錄的 [**值：** ] 方塊中的目前專案的結尾，按下鍵盤上的 enter，以建立新行;然後，在該行（現有的值下方）輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="878a1-263">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table.</span></span> <span data-ttu-id="878a1-264">（您可以在表格下方的圖例中看到範例）。</span><span class="sxs-lookup"><span data-stu-id="878a1-264">(You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="878a1-265">**價值：**</span><span class="sxs-lookup"><span data-stu-id="878a1-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="878a1-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="878a1-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="878a1-p116">(系統會自動提供畫面上指示所需的引號。您不需要手動輸入。)  </span><span class="sxs-lookup"><span data-stu-id="878a1-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="878a1-269">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="878a1-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="878a1-271">選取 [**儲存記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="878a1-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-設定-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="878a1-273">新增 Microsoft 365 所需的兩筆 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="878a1-273">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="878a1-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="878a1-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="878a1-275">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="878a1-275">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="878a1-276">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="878a1-276">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="878a1-277">在 [**資源**] 頁面上，選取 [**主控區域**]。</span><span class="sxs-lookup"><span data-stu-id="878a1-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="878a1-278">在 [**主控區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="878a1-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="878a1-279">選取 [**建立記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="878a1-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="878a1-280">新增第一筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="878a1-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="878a1-281">在 [**建立記錄集**] 區域的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="878a1-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="878a1-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="878a1-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="878a1-283">**Name**</span><span class="sxs-lookup"><span data-stu-id="878a1-283">**Name**</span></span>|<span data-ttu-id="878a1-284">**Type**</span><span class="sxs-lookup"><span data-stu-id="878a1-284">**Type**</span></span>|<span data-ttu-id="878a1-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="878a1-285">**Alias**</span></span>|<span data-ttu-id="878a1-286">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="878a1-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="878a1-287">**值**</span><span class="sxs-lookup"><span data-stu-id="878a1-287">**Value**</span></span>|<span data-ttu-id="878a1-288">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="878a1-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="878a1-289">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="878a1-289">_sip._tls</span></span>|<span data-ttu-id="878a1-290">SRV - 服務定位器</span><span class="sxs-lookup"><span data-stu-id="878a1-290">SRV - Service locator</span></span>|<span data-ttu-id="878a1-291">無</span><span class="sxs-lookup"><span data-stu-id="878a1-291">No</span></span>|<span data-ttu-id="878a1-292">300</span><span class="sxs-lookup"><span data-stu-id="878a1-292">300</span></span>|<span data-ttu-id="878a1-293">100 1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="878a1-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="878a1-294">**此值必須以句點（.）結尾**></span><span class="sxs-lookup"><span data-stu-id="878a1-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="878a1-295">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="878a1-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="878a1-296">簡易</span><span class="sxs-lookup"><span data-stu-id="878a1-296">Simple</span></span>|
    |<span data-ttu-id="878a1-297">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="878a1-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="878a1-298">SRV - 服務定位器</span><span class="sxs-lookup"><span data-stu-id="878a1-298">SRV - Service locator</span></span>|<span data-ttu-id="878a1-299">無</span><span class="sxs-lookup"><span data-stu-id="878a1-299">No</span></span>|<span data-ttu-id="878a1-300">300</span><span class="sxs-lookup"><span data-stu-id="878a1-300">300</span></span>|<span data-ttu-id="878a1-301">100 1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="878a1-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="878a1-302">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="878a1-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="878a1-303">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="878a1-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="878a1-304">簡單</span><span class="sxs-lookup"><span data-stu-id="878a1-304">Simple</span></span>|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="878a1-306">選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="878a1-306">Select **Create**.</span></span>
    
    ![AWS-BP-設定-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="878a1-308">新增另一筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="878a1-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="878a1-309">在 [**主控區域**] 頁面中，選取 [**建立記錄集**]，使用表格中下一列的值建立記錄，然後再選取 [**建立**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="878a1-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="878a1-310">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="878a1-310">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="878a1-311">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="878a1-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="878a1-312">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="878a1-312">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
