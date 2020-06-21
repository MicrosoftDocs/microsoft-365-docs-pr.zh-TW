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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以供 Microsoft eNomCentral。
ms.openlocfilehash: c964729c052f5c0b61441f14ce15a167caa06b72
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780394"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="a988b-103">在 Microsoft 的 eNomCentral 建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="a988b-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="a988b-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="a988b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a988b-105">如果 eNomCentral 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="a988b-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a988b-106">在 eNomCentral 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="a988b-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="a988b-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a988b-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a988b-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a988b-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a988b-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a988b-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a988b-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="a988b-110">Add a TXT record for verification</span></span>
<span data-ttu-id="a988b-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a988b-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a988b-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="a988b-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="a988b-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="a988b-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a988b-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="a988b-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="a988b-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="a988b-115">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a988b-116">請依照下列步驟操作或[觀看影片 (0:46 從開始)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="a988b-116">Follow the steps below or [watch the video (start at 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="a988b-117">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="a988b-117">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="a988b-118">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="a988b-118">You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="a988b-120">在 [**我的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="a988b-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="a988b-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="a988b-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="a988b-124">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a988b-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a988b-125">從下拉式清單中選擇 [**記錄類型**] 值。</span><span class="sxs-lookup"><span data-stu-id="a988b-125">Choose the **Record Type** value from the drop-down list.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="a988b-126">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="a988b-126">**Host Name**</span></span> <br/> |<span data-ttu-id="a988b-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a988b-127">**Record Type**</span></span> <br/> |<span data-ttu-id="a988b-128">**Address**</span><span class="sxs-lookup"><span data-stu-id="a988b-128">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="a988b-129">TXT</span><span class="sxs-lookup"><span data-stu-id="a988b-129">TXT</span></span>  <br/> |<span data-ttu-id="a988b-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a988b-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a988b-131">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="a988b-131">**Note:** This is an example.</span></span> <span data-ttu-id="a988b-132">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="a988b-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a988b-133">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="a988b-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="a988b-135">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a988b-135">Select **save**.</span></span>
    
    ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="a988b-137">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="a988b-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a988b-138">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 365 並要求 Microsoft 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="a988b-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="a988b-139">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="a988b-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a988b-140">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="a988b-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a988b-141">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="a988b-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a988b-142">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="a988b-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a988b-143">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="a988b-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a988b-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a988b-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a988b-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a988b-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a988b-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a988b-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a988b-147">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="a988b-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a988b-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a988b-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="a988b-149">請依照下列步驟操作或[觀看影片 (從 3:40 處開始)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="a988b-149">Follow the steps below or [watch the video (start at 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="a988b-150">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="a988b-150">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="a988b-151">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="a988b-151">You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="a988b-153">在 [**我的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="a988b-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="a988b-155">在 [**管理網域**] 下拉式清單中，選擇 [**電子郵件設定**]。</span><span class="sxs-lookup"><span data-stu-id="a988b-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="a988b-157">在 [**服務選擇**] 下拉式清單中，選擇 [**使用者] （MX）**。</span><span class="sxs-lookup"><span data-stu-id="a988b-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="a988b-159">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a988b-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a988b-160">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="a988b-160">**Host Name**</span></span>|<span data-ttu-id="a988b-161">**Address**</span><span class="sxs-lookup"><span data-stu-id="a988b-161">**Address**</span></span>|<span data-ttu-id="a988b-162">**Pref**</span><span class="sxs-lookup"><span data-stu-id="a988b-162">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="a988b-163">*\<domain-key\>* mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="a988b-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="a988b-164">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a988b-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="a988b-165">\**附注：\*\*\*\<domain-key\>* 從您的 Microsoft 帳戶取得。</span><span class="sxs-lookup"><span data-stu-id="a988b-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="a988b-166">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="a988b-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a988b-167">10 </span><span class="sxs-lookup"><span data-stu-id="a988b-167">10</span></span>  <br/> <span data-ttu-id="a988b-168">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="a988b-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
       
   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="a988b-170">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a988b-170">Select **save**.</span></span>
    
    ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="a988b-172">如果有任何其他現有的 MX 記錄，請選取其核取方塊來進行選取。</span><span class="sxs-lookup"><span data-stu-id="a988b-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="a988b-174">選取 [**刪除] 複選**框。</span><span class="sxs-lookup"><span data-stu-id="a988b-174">Select **delete checked**.</span></span>
    
    ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a988b-176">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="a988b-176">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="a988b-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a988b-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="a988b-178">請依照下列步驟操作或[觀看影片 (從 4:24 處開始)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="a988b-178">Follow the steps below or [watch the video (start at 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="a988b-179">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="a988b-179">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="a988b-180">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="a988b-180">You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="a988b-182">在 [**我的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="a988b-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="a988b-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="a988b-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="a988b-186">選取 [**新增列**]。</span><span class="sxs-lookup"><span data-stu-id="a988b-186">Select **new row**.</span></span>
    
    ![eNom-BP-Configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="a988b-188">在六筆新記錄的方塊中，輸入或複製並貼上下列的值。</span><span class="sxs-lookup"><span data-stu-id="a988b-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
<span data-ttu-id="a988b-189">從下拉式清單中選擇 [**記錄類型**] 值。</span><span class="sxs-lookup"><span data-stu-id="a988b-189">Choose the **Record Type** value from the drop-down list.</span></span>
        
    |<span data-ttu-id="a988b-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="a988b-190">**Host Name**</span></span>|<span data-ttu-id="a988b-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a988b-191">**Record Type**</span></span>|<span data-ttu-id="a988b-192">**Address**</span><span class="sxs-lookup"><span data-stu-id="a988b-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a988b-193">autodiscover (自動探索)</span><span class="sxs-lookup"><span data-stu-id="a988b-193">autodiscover</span></span>  <br/> |<span data-ttu-id="a988b-194">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="a988b-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="a988b-195">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="a988b-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="a988b-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a988b-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a988b-197">sip</span><span class="sxs-lookup"><span data-stu-id="a988b-197">sip</span></span>  <br/> |<span data-ttu-id="a988b-198">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="a988b-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="a988b-199">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="a988b-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a988b-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a988b-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a988b-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a988b-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a988b-202">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="a988b-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="a988b-203">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="a988b-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a988b-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a988b-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a988b-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a988b-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a988b-206">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="a988b-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="a988b-207">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="a988b-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="a988b-208">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a988b-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a988b-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a988b-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a988b-210">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="a988b-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="a988b-211">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="a988b-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="a988b-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a988b-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="a988b-213">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a988b-213">Select **save**.</span></span>
    
    ![eNom-BP-Configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a988b-215">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="a988b-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a988b-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a988b-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a988b-217">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="a988b-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a988b-218">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="a988b-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a988b-219">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="a988b-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a988b-220">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="a988b-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="a988b-221">請依照下列步驟操作或[觀看影片 (從 5:12 處開始)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="a988b-221">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="a988b-222">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="a988b-222">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="a988b-223">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="a988b-223">You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="a988b-225">在 [**我的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="a988b-225">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="a988b-227">On the **Manage Domain** drop-down list, choose **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="a988b-227">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="a988b-229">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a988b-229">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
<span data-ttu-id="a988b-230">從下拉式清單中選擇 [**記錄類型**] 值。</span><span class="sxs-lookup"><span data-stu-id="a988b-230">Choose the **Record Type** value from the drop-down list.</span></span>
    
    |<span data-ttu-id="a988b-231">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="a988b-231">**Host Name**</span></span>|<span data-ttu-id="a988b-232">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="a988b-232">**Record Type**</span></span>|<span data-ttu-id="a988b-233">**Address**</span><span class="sxs-lookup"><span data-stu-id="a988b-233">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a988b-234">TXT</span><span class="sxs-lookup"><span data-stu-id="a988b-234">TXT</span></span>  <br/> |<span data-ttu-id="a988b-235">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a988b-235">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="a988b-236">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="a988b-236">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="a988b-238">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a988b-238">Select **save**.</span></span>
    
    ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a988b-240">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="a988b-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a988b-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a988b-241"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="a988b-242">請依照下列步驟操作或[觀看影片 (從 5:50 處開始)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="a988b-242">Follow the steps below or [watch the video (start at 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="a988b-243">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="a988b-243">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="a988b-244">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="a988b-244">You'll be prompted to login.</span></span>
    
    ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="a988b-246">在 [**我的網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="a988b-246">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="a988b-248">On the **Manage Domain** drop-down list, choose **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="a988b-248">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="a988b-250">在 [**新增列**] 右邊，選取 [新增**SRV 或 SPF 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="a988b-250">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="a988b-252">在這兩筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a988b-252">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a988b-253">**服務**</span><span class="sxs-lookup"><span data-stu-id="a988b-253">**Service**</span></span>|<span data-ttu-id="a988b-254">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="a988b-254">**Protocol**</span></span>|<span data-ttu-id="a988b-255">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="a988b-255">**Priority**</span></span>|<span data-ttu-id="a988b-256">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="a988b-256">**Weight**</span></span>|<span data-ttu-id="a988b-257">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="a988b-257">**Port**</span></span>|<span data-ttu-id="a988b-258">**目標          (主機名稱)**</span><span class="sxs-lookup"><span data-stu-id="a988b-258">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a988b-259">_sip</span><span class="sxs-lookup"><span data-stu-id="a988b-259">_sip</span></span>  <br/> |<span data-ttu-id="a988b-260">_tls</span><span class="sxs-lookup"><span data-stu-id="a988b-260">_tls</span></span>  <br/> |<span data-ttu-id="a988b-261">100</span><span class="sxs-lookup"><span data-stu-id="a988b-261">100</span></span>  <br/> |<span data-ttu-id="a988b-262">1 </span><span class="sxs-lookup"><span data-stu-id="a988b-262">1</span></span>  <br/> |<span data-ttu-id="a988b-263">443</span><span class="sxs-lookup"><span data-stu-id="a988b-263">443</span></span>  <br/> |<span data-ttu-id="a988b-264">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="a988b-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a988b-265">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a988b-265">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a988b-266">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a988b-266">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="a988b-267">_tcp</span><span class="sxs-lookup"><span data-stu-id="a988b-267">_tcp</span></span>  <br/> |<span data-ttu-id="a988b-268">100</span><span class="sxs-lookup"><span data-stu-id="a988b-268">100</span></span>  <br/> |<span data-ttu-id="a988b-269">1 </span><span class="sxs-lookup"><span data-stu-id="a988b-269">1</span></span>  <br/> |<span data-ttu-id="a988b-270">5061</span><span class="sxs-lookup"><span data-stu-id="a988b-270">5061</span></span>  <br/> |<span data-ttu-id="a988b-271">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="a988b-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="a988b-272">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a988b-272">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="a988b-274">選取 [**儲存**]</span><span class="sxs-lookup"><span data-stu-id="a988b-274">Select **save**</span></span>
    
    ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="a988b-276">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a988b-276">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a988b-277">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a988b-277">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a988b-278">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a988b-278">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

