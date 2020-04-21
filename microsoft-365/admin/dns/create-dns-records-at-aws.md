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
ms.openlocfilehash: 086a5d7210d2c722aeda701dc62a699ca0eaec87
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629728"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="b6bf6-103">在 Microsoft 的 Amazon Web 服務（AWS）上建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="b6bf6-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="b6bf6-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b6bf6-105">如果 AWS 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="b6bf6-106">在 AWS 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="b6bf6-107">若要深入瞭解具有 Microsfot 之網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-107">To learn about webhosting and DNS for websites with Microsfot, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6bf6-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b6bf6-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b6bf6-109">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b6bf6-110">如果您在新增 DNS 記錄後遇到郵件流程或其他問題的問題，請參閱[尋找並修正新增您的網域或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b6bf6-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="b6bf6-111">Add a TXT record for verification</span></span>
<span data-ttu-id="b6bf6-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b6bf6-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b6bf6-113">在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="b6bf6-114">您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6bf6-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b6bf6-p104">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b6bf6-119">在 [**資源**] 頁面上，選取 [**主控區域**]。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="b6bf6-120">在 [主控區域 \* \*] 頁面上的 [**功能變數名稱**] 欄中，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="b6bf6-121">選取 [**建立記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="b6bf6-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b6bf6-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b6bf6-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="b6bf6-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="b6bf6-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="b6bf6-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b6bf6-126">**名稱**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-126">**Name**</span></span> <br/> |<span data-ttu-id="b6bf6-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-127">**Type**</span></span> <br/> |<span data-ttu-id="b6bf6-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-128">**Alias**</span></span> <br/> |<span data-ttu-id="b6bf6-129">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="b6bf6-130">**值**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-130">**Value**</span></span> <br/> |<span data-ttu-id="b6bf6-131">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="b6bf6-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="b6bf6-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b6bf6-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="b6bf6-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="b6bf6-134">否</span><span class="sxs-lookup"><span data-stu-id="b6bf6-134">No</span></span>  <br/> |<span data-ttu-id="b6bf6-135">300</span><span class="sxs-lookup"><span data-stu-id="b6bf6-135">300</span></span>  <br/> |<span data-ttu-id="b6bf6-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b6bf6-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="b6bf6-137">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-137">**Note:** This is an example.</span></span> <span data-ttu-id="b6bf6-138">從 Microsoft 365 的表格中，使用您的特定**目的地或指向位址**值。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-138">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="b6bf6-139">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="b6bf6-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b6bf6-140">簡易</span><span class="sxs-lookup"><span data-stu-id="b6bf6-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="b6bf6-141">選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="b6bf6-142">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b6bf6-143">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="b6bf6-144">當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b6bf6-145">在 Microsoft 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b6bf6-146">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b6bf6-147">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b6bf6-148">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b6bf6-149">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b6bf6-149">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b6bf6-150">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b6bf6-151">如果您在新增 DNS 記錄後遇到郵件流程或其他問題的問題，請參閱[尋找並修正新增您的網域或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-151">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="b6bf6-152">新增 MX 記錄，使您網域的電子郵件將會傳送至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b6bf6-152">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="b6bf6-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b6bf6-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="b6bf6-154">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-154">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="b6bf6-155">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-155">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b6bf6-156">在 [**資源**] 頁面上，選取 [**主控區域**]。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="b6bf6-157">在 [**主控區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="b6bf6-158">選取 [**建立記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="b6bf6-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b6bf6-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b6bf6-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="b6bf6-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="b6bf6-161">**名稱**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-161">**Name**</span></span>|<span data-ttu-id="b6bf6-162">**Type**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-162">**Type**</span></span>|<span data-ttu-id="b6bf6-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-163">**Alias**</span></span>|<span data-ttu-id="b6bf6-164">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="b6bf6-165">**值**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-165">**Value**</span></span>|<span data-ttu-id="b6bf6-166">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b6bf6-167">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="b6bf6-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b6bf6-168">MX - 郵件交換</span><span class="sxs-lookup"><span data-stu-id="b6bf6-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="b6bf6-169">否</span><span class="sxs-lookup"><span data-stu-id="b6bf6-169">No</span></span>  <br/> |<span data-ttu-id="b6bf6-170">300</span><span class="sxs-lookup"><span data-stu-id="b6bf6-170">300</span></span>  <br/> |<span data-ttu-id="b6bf6-171">0  *\<網域金鑰\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b6bf6-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="b6bf6-p109">0 是指 MX 優先順序值。將它新增到 MX 值的開頭，以空格分隔該值的其餘部分。  </span><span class="sxs-lookup"><span data-stu-id="b6bf6-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="b6bf6-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="b6bf6-175">**附注：** 從 Microsoft \<365 帳戶取得您的*網域金鑰*\> 。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-175">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="b6bf6-176">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="b6bf6-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b6bf6-177">簡易</span><span class="sxs-lookup"><span data-stu-id="b6bf6-177">Simple</span></span>  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="b6bf6-179">選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-179">Select **Create**.</span></span>
    
    ![AWS-BP-設定-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="b6bf6-181">如果有任何其他的 MX 記錄，請移除它們。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b6bf6-182">AWS 會將 MX 記錄儲存為一組可以包含多個記錄的集合。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="b6bf6-183">**不要**選取 [**刪除記錄集**]，因為這會刪除所有的 MX 記錄，包括剛才新增的記錄。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="b6bf6-184">請改為依照下列指示操作。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="b6bf6-185">首先，選取 MX 記錄集。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-設定-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="b6bf6-187">接下來，在 [**編輯記錄集**] 區域中，選取 [**值**] 方塊中的專案，然後按鍵盤上的**delete**鍵，以刪除每個過時的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-設定-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="b6bf6-189">選取 [**儲存記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-設定-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="b6bf6-191">新增 Microsoft 365 所需的五個 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="b6bf6-191">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="b6bf6-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b6bf6-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="b6bf6-193">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-193">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="b6bf6-194">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-194">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b6bf6-195">在 [**資源**] 頁面上，選取 [**主控區域**]。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="b6bf6-196">在 [**主控區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="b6bf6-197">選取 [**建立記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="b6bf6-198">新增第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="b6bf6-199">在 [**建立記錄集**] 區域的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="b6bf6-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="b6bf6-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="b6bf6-201">**名稱**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-201">**Name**</span></span>|<span data-ttu-id="b6bf6-202">**Type**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-202">**Type**</span></span>|<span data-ttu-id="b6bf6-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-203">**Alias**</span></span>|<span data-ttu-id="b6bf6-204">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="b6bf6-205">**值**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-205">**Value**</span></span>|<span data-ttu-id="b6bf6-206">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b6bf6-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b6bf6-207">autodiscover</span></span>  <br/> |<span data-ttu-id="b6bf6-208">CNAME - 正式名稱</span><span class="sxs-lookup"><span data-stu-id="b6bf6-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="b6bf6-209">無</span><span class="sxs-lookup"><span data-stu-id="b6bf6-209">No</span></span>  <br/> |<span data-ttu-id="b6bf6-210">300</span><span class="sxs-lookup"><span data-stu-id="b6bf6-210">300</span></span>  <br/> |<span data-ttu-id="b6bf6-211">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="b6bf6-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b6bf6-213">簡單</span><span class="sxs-lookup"><span data-stu-id="b6bf6-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="b6bf6-214">sip</span><span class="sxs-lookup"><span data-stu-id="b6bf6-214">sip</span></span>  <br/> |<span data-ttu-id="b6bf6-215">CNAME - 正式名稱</span><span class="sxs-lookup"><span data-stu-id="b6bf6-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="b6bf6-216">無</span><span class="sxs-lookup"><span data-stu-id="b6bf6-216">No</span></span>  <br/> |<span data-ttu-id="b6bf6-217">300</span><span class="sxs-lookup"><span data-stu-id="b6bf6-217">300</span></span>  <br/> |<span data-ttu-id="b6bf6-218">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b6bf6-219">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b6bf6-220">簡單</span><span class="sxs-lookup"><span data-stu-id="b6bf6-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="b6bf6-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b6bf6-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b6bf6-222">CNAME - 正式名稱</span><span class="sxs-lookup"><span data-stu-id="b6bf6-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="b6bf6-223">無</span><span class="sxs-lookup"><span data-stu-id="b6bf6-223">No</span></span>  <br/> |<span data-ttu-id="b6bf6-224">300</span><span class="sxs-lookup"><span data-stu-id="b6bf6-224">300</span></span>  <br/> |<span data-ttu-id="b6bf6-225">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b6bf6-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b6bf6-227">簡易</span><span class="sxs-lookup"><span data-stu-id="b6bf6-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="b6bf6-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b6bf6-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b6bf6-229">CNAME - 正式名稱</span><span class="sxs-lookup"><span data-stu-id="b6bf6-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="b6bf6-230">無</span><span class="sxs-lookup"><span data-stu-id="b6bf6-230">No</span></span>  <br/> |<span data-ttu-id="b6bf6-231">300</span><span class="sxs-lookup"><span data-stu-id="b6bf6-231">300</span></span>  <br/> |<span data-ttu-id="b6bf6-232">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="b6bf6-233">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b6bf6-234">簡單</span><span class="sxs-lookup"><span data-stu-id="b6bf6-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="b6bf6-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b6bf6-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b6bf6-236">CNAME - 正式名稱</span><span class="sxs-lookup"><span data-stu-id="b6bf6-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="b6bf6-237">否</span><span class="sxs-lookup"><span data-stu-id="b6bf6-237">No</span></span>  <br/> |<span data-ttu-id="b6bf6-238">300</span><span class="sxs-lookup"><span data-stu-id="b6bf6-238">300</span></span>  <br/> |<span data-ttu-id="b6bf6-239">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="b6bf6-240">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b6bf6-241">簡單</span><span class="sxs-lookup"><span data-stu-id="b6bf6-241">Simple</span></span>  <br/> |
   
    ![AWS-BP-Configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="b6bf6-243">選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-243">Select **Create**.</span></span>
    
    ![AWS-BP-設定-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="b6bf6-245">新增其他四筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="b6bf6-246">在 [**主控區域**] 頁面中，選取 [**建立記錄集**]，使用表格中下一列的值建立記錄，然後再選取 [**建立**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="b6bf6-247">重複此程式，直到您已建立全部五筆 CNAME 記錄為止。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b6bf6-248">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="b6bf6-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b6bf6-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b6bf6-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6bf6-250">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b6bf6-251">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b6bf6-252">如果您已有網域的 SPF 記錄，請不要為 Microsoft 建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-252">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b6bf6-253">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-253">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="b6bf6-254">需要範例？</span><span class="sxs-lookup"><span data-stu-id="b6bf6-254">Need examples?</span></span> <span data-ttu-id="b6bf6-255">請參閱[Microsoft 的這些外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-255">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="b6bf6-256">若要驗證您的 SPF 記錄，您可以使用其中一種[spf 驗證工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="b6bf6-257">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="b6bf6-258">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b6bf6-259">在 [**資源**] 頁面上，選取 [**主控區域**]。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="b6bf6-260">在 [**主控區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="b6bf6-261">選取**TXT**記錄集。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-設定-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="b6bf6-263">在 [**編輯記錄集**] 區域中，于現有記錄的 [**值：** ] 方塊中的目前專案的結尾，按下鍵盤上的 enter，以建立新行;然後，在該行（現有的值下方）輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-263">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table.</span></span> <span data-ttu-id="b6bf6-264">（您可以在表格下方的圖例中看到範例）。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-264">(You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="b6bf6-265">**價值：**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="b6bf6-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b6bf6-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b6bf6-p116">(系統會自動提供畫面上指示所需的引號。您不需要手動輸入。)  </span><span class="sxs-lookup"><span data-stu-id="b6bf6-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="b6bf6-269">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="b6bf6-271">選取 [**儲存記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-設定-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="b6bf6-273">新增 Microsoft 365 所需的兩筆 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="b6bf6-273">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="b6bf6-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b6bf6-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="b6bf6-275">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-275">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="b6bf6-276">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-276">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b6bf6-277">在 [**資源**] 頁面上，選取 [**主控區域**]。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="b6bf6-278">在 [**主控區域**] 頁面上的 [**功能變數名稱**] 欄中，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="b6bf6-279">選取 [**建立記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="b6bf6-280">新增第一筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="b6bf6-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="b6bf6-281">在 [**建立記錄集**] 區域的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="b6bf6-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="b6bf6-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="b6bf6-283">**名稱**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-283">**Name**</span></span>|<span data-ttu-id="b6bf6-284">**Type**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-284">**Type**</span></span>|<span data-ttu-id="b6bf6-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-285">**Alias**</span></span>|<span data-ttu-id="b6bf6-286">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="b6bf6-287">**值**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-287">**Value**</span></span>|<span data-ttu-id="b6bf6-288">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b6bf6-289">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="b6bf6-289">_sip._tls</span></span>|<span data-ttu-id="b6bf6-290">SRV - 服務定位器</span><span class="sxs-lookup"><span data-stu-id="b6bf6-290">SRV - Service locator</span></span>|<span data-ttu-id="b6bf6-291">無</span><span class="sxs-lookup"><span data-stu-id="b6bf6-291">No</span></span>|<span data-ttu-id="b6bf6-292">300</span><span class="sxs-lookup"><span data-stu-id="b6bf6-292">300</span></span>|<span data-ttu-id="b6bf6-293">100 1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="b6bf6-294">**此值必須以句點（.）結尾**></span><span class="sxs-lookup"><span data-stu-id="b6bf6-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="b6bf6-295">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="b6bf6-296">簡易</span><span class="sxs-lookup"><span data-stu-id="b6bf6-296">Simple</span></span>|
    |<span data-ttu-id="b6bf6-297">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="b6bf6-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="b6bf6-298">SRV - 服務定位器</span><span class="sxs-lookup"><span data-stu-id="b6bf6-298">SRV - Service locator</span></span>|<span data-ttu-id="b6bf6-299">無</span><span class="sxs-lookup"><span data-stu-id="b6bf6-299">No</span></span>|<span data-ttu-id="b6bf6-300">300</span><span class="sxs-lookup"><span data-stu-id="b6bf6-300">300</span></span>|<span data-ttu-id="b6bf6-301">100 1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="b6bf6-302">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b6bf6-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="b6bf6-303">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="b6bf6-304">簡單</span><span class="sxs-lookup"><span data-stu-id="b6bf6-304">Simple</span></span>|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="b6bf6-306">選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-306">Select **Create**.</span></span>
    
    ![AWS-BP-設定-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="b6bf6-308">新增另一筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="b6bf6-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="b6bf6-309">在 [**主控區域**] 頁面中，選取 [**建立記錄集**]，使用表格中下一列的值建立記錄，然後再選取 [**建立**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b6bf6-310">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b6bf6-310">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b6bf6-311">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b6bf6-312">如果您在新增 DNS 記錄後遇到郵件流程或其他問題的問題，請參閱[尋找並修正新增您的網域或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b6bf6-312">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
