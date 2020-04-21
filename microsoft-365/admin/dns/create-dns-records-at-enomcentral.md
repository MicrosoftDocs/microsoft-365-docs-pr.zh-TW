---
title: 在 Microsoft 的 eNomCentral 建立 DNS 記錄
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以供 Microsoft eNomCentral。
ms.openlocfilehash: 33231896b69c0883bc9af3153fa57533096a1a0f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629572"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="d107d-103">在 Microsoft 的 eNomCentral 建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="d107d-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="d107d-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="d107d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d107d-105">如果 eNomCentral 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="d107d-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="d107d-106">在 eNomCentral 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="d107d-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="d107d-107">若要深入瞭解 Microsoft 的網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="d107d-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="d107d-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d107d-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d107d-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="d107d-111">Add a TXT record for verification</span></span>
<span data-ttu-id="d107d-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d107d-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d107d-113">在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="d107d-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="d107d-114">您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。</span><span class="sxs-lookup"><span data-stu-id="d107d-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d107d-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="d107d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="d107d-117">請依照下列步驟操作或[觀看影片 (0:46 從開始)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d107d-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d107d-p104">首先請用[這個連結](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)移至 eNom Central 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="d107d-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="d107d-121">在 [**我的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="d107d-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="d107d-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="d107d-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="d107d-125">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="d107d-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="d107d-126">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d107d-126">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="d107d-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="d107d-127">**Host Name**</span></span> <br/> |<span data-ttu-id="d107d-128">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="d107d-128">**Record Type**</span></span> <br/> |<span data-ttu-id="d107d-129">**Address**</span><span class="sxs-lookup"><span data-stu-id="d107d-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="d107d-130">TXT</span><span class="sxs-lookup"><span data-stu-id="d107d-130">TXT</span></span>  <br/> |<span data-ttu-id="d107d-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d107d-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d107d-132">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="d107d-132">**Note:** This is an example.</span></span> <span data-ttu-id="d107d-133">從表格中，使用您的特定**目的地或指向位址**值。</span><span class="sxs-lookup"><span data-stu-id="d107d-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="d107d-134">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="d107d-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="d107d-136">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d107d-136">Select **save**.</span></span>
    
    ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="d107d-138">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="d107d-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d107d-139">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 365，並要求 Microsoft 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="d107d-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="d107d-140">當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="d107d-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d107d-141">在 Microsoft 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="d107d-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d107d-142">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="d107d-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d107d-143">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="d107d-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d107d-144">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="d107d-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d107d-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d107d-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d107d-148">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d107d-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d107d-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d107d-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="d107d-150">請依照下列步驟操作或[觀看影片 (從 3:40 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d107d-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d107d-p107">首先請用[這個連結](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)移至 eNom Central 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="d107d-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="d107d-154">在 [**我的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="d107d-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="d107d-156">在 [**管理網域**] 下拉式清單中，選擇 [**電子郵件設定**]。</span><span class="sxs-lookup"><span data-stu-id="d107d-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="d107d-158">在 [**服務選擇**] 下拉式清單中，選擇 [**使用者] （MX）**。</span><span class="sxs-lookup"><span data-stu-id="d107d-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="d107d-160">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d107d-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="d107d-161">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="d107d-161">**Host Name**</span></span>|<span data-ttu-id="d107d-162">**Address**</span><span class="sxs-lookup"><span data-stu-id="d107d-162">**Address**</span></span>|<span data-ttu-id="d107d-163">**Pref**</span><span class="sxs-lookup"><span data-stu-id="d107d-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="d107d-164">*\<網域金鑰\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d107d-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="d107d-165">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="d107d-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="d107d-166">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="d107d-166">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="d107d-167">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="d107d-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d107d-168">10 </span><span class="sxs-lookup"><span data-stu-id="d107d-168">10</span></span>  <br/> <span data-ttu-id="d107d-169">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="d107d-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="d107d-171">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d107d-171">Select **save**.</span></span>
    
    ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="d107d-173">如果有任何其他現有的 MX 記錄，請選取其核取方塊來進行選取。</span><span class="sxs-lookup"><span data-stu-id="d107d-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="d107d-175">選取 [**刪除] 複選**框。</span><span class="sxs-lookup"><span data-stu-id="d107d-175">Select **delete checked**.</span></span>
    
    ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d107d-177">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="d107d-177">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="d107d-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d107d-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="d107d-179">請依照下列步驟操作或[觀看影片 (從 4:24 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d107d-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d107d-p109">首先請用[這個連結](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)移至 eNom Central 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="d107d-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="d107d-183">在 [**我的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="d107d-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="d107d-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="d107d-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="d107d-187">選取 [**新增列**]。</span><span class="sxs-lookup"><span data-stu-id="d107d-187">Select **new row**.</span></span>
    
    ![eNom-BP-Configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="d107d-189">在六筆新記錄的方塊中，輸入或複製並貼上下列的值。</span><span class="sxs-lookup"><span data-stu-id="d107d-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="d107d-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="d107d-190">**Host Name**</span></span>|<span data-ttu-id="d107d-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="d107d-191">**Record Type**</span></span>|<span data-ttu-id="d107d-192">**Address**</span><span class="sxs-lookup"><span data-stu-id="d107d-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d107d-193">autodiscover (自動探索)</span><span class="sxs-lookup"><span data-stu-id="d107d-193">autodiscover</span></span>  <br/> |<span data-ttu-id="d107d-194">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="d107d-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="d107d-195">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="d107d-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="d107d-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="d107d-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d107d-197">sip</span><span class="sxs-lookup"><span data-stu-id="d107d-197">sip</span></span>  <br/> |<span data-ttu-id="d107d-198">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="d107d-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="d107d-199">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="d107d-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d107d-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="d107d-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d107d-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d107d-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d107d-202">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="d107d-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="d107d-203">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="d107d-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d107d-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="d107d-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d107d-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d107d-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d107d-206">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="d107d-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="d107d-207">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="d107d-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="d107d-208">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="d107d-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d107d-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d107d-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d107d-210">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="d107d-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="d107d-211">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="d107d-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="d107d-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="d107d-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="d107d-214">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d107d-214">Select **save**.</span></span>
    
    ![eNom-BP-Configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d107d-216">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="d107d-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d107d-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d107d-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d107d-218">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="d107d-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d107d-219">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="d107d-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d107d-220">如果您已有網域的 SPF 記錄，請不要為 Microsoft 建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="d107d-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d107d-221">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="d107d-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="d107d-222">請依照下列步驟操作或[觀看影片 (從 5:12 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d107d-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d107d-p111">首先請用[這個連結](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)移至 eNom Central 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="d107d-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="d107d-226">在 [**我的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="d107d-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="d107d-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="d107d-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="d107d-230">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="d107d-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="d107d-231">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d107d-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d107d-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="d107d-232">**Host Name**</span></span>|<span data-ttu-id="d107d-233">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="d107d-233">**Record Type**</span></span>|<span data-ttu-id="d107d-234">**Address**</span><span class="sxs-lookup"><span data-stu-id="d107d-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d107d-235">TXT</span><span class="sxs-lookup"><span data-stu-id="d107d-235">TXT</span></span>  <br/> |<span data-ttu-id="d107d-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d107d-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="d107d-237">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="d107d-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="d107d-239">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d107d-239">Select **save**.</span></span>
    
    ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d107d-241">新增 Microsoft 所需的兩筆 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="d107d-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d107d-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d107d-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="d107d-243">請依照下列步驟操作或[觀看影片 (從 5:50 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d107d-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d107d-p112">首先請用[這個連結](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)移至 eNom Central 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="d107d-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="d107d-247">在 [**我的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="d107d-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="d107d-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="d107d-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="d107d-251">在 [**新增列**] 右邊，選取 [新增**SRV 或 SPF 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="d107d-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="d107d-253">在這兩筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="d107d-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="d107d-254">**Service** (服務)</span><span class="sxs-lookup"><span data-stu-id="d107d-254">**Service**</span></span>|<span data-ttu-id="d107d-255">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="d107d-255">**Protocol**</span></span>|<span data-ttu-id="d107d-256">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="d107d-256">**Priority**</span></span>|<span data-ttu-id="d107d-257">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="d107d-257">**Weight**</span></span>|<span data-ttu-id="d107d-258">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="d107d-258">**Port**</span></span>|<span data-ttu-id="d107d-259">**目標          (主機名稱)**</span><span class="sxs-lookup"><span data-stu-id="d107d-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d107d-260">_sip</span><span class="sxs-lookup"><span data-stu-id="d107d-260">_sip</span></span>  <br/> |<span data-ttu-id="d107d-261">_tls</span><span class="sxs-lookup"><span data-stu-id="d107d-261">_tls</span></span>  <br/> |<span data-ttu-id="d107d-262">100</span><span class="sxs-lookup"><span data-stu-id="d107d-262">100</span></span>  <br/> |<span data-ttu-id="d107d-263">1 </span><span class="sxs-lookup"><span data-stu-id="d107d-263">1</span></span>  <br/> |<span data-ttu-id="d107d-264">443</span><span class="sxs-lookup"><span data-stu-id="d107d-264">443</span></span>  <br/> |<span data-ttu-id="d107d-265">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="d107d-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d107d-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="d107d-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d107d-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="d107d-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="d107d-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="d107d-268">_tcp</span></span>  <br/> |<span data-ttu-id="d107d-269">100</span><span class="sxs-lookup"><span data-stu-id="d107d-269">100</span></span>  <br/> |<span data-ttu-id="d107d-270">1 </span><span class="sxs-lookup"><span data-stu-id="d107d-270">1</span></span>  <br/> |<span data-ttu-id="d107d-271">5061</span><span class="sxs-lookup"><span data-stu-id="d107d-271">5061</span></span>  <br/> |<span data-ttu-id="d107d-272">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="d107d-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="d107d-273">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="d107d-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="d107d-275">選取 [**儲存**]</span><span class="sxs-lookup"><span data-stu-id="d107d-275">Select **save**</span></span>
    
    ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="d107d-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d107d-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

