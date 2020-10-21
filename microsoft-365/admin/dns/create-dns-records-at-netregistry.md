---
title: 在 Netregistry 建立 Microsoft 的 DNS 記錄
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Netregistry。
ms.openlocfilehash: 016df6c61fd6934c1bc46b55c7e110d8442cf1d5
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645968"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="dc0d7-103">在 Netregistry 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="dc0d7-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="dc0d7-104">[檢查網域的常見問題集](../setup/domains-faq.md) ：供您在找不到所需功能時參考。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="dc0d7-105">如果 Netregistry 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="dc0d7-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="dc0d7-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="dc0d7-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="dc0d7-108">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="dc0d7-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="dc0d7-109">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="dc0d7-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="dc0d7-110">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="dc0d7-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="dc0d7-111">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="dc0d7-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="dc0d7-112">在 Netregistry 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="dc0d7-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="dc0d7-116">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="dc0d7-116">Add a TXT record for verification</span></span>
<span data-ttu-id="dc0d7-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="dc0d7-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="dc0d7-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc0d7-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="dc0d7-122">若要開始使用，請使用 [此連結](https://theconsole.netregistry.com.au/)移至 Netregistry 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-122">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="dc0d7-123">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="dc0d7-123">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="dc0d7-125">在您要管理的網域旁，選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-125">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="dc0d7-127">選取 [ **區域管理員**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-127">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="dc0d7-129">在 [ **新增區域記錄**] 底下的清單中，選擇 [ **TXT 記錄** ]，然後選取 [ **建立新的記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-129">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="dc0d7-131">您必須在 TXT 方塊中的專案前後使用引號。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-131">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="dc0d7-132">在 [ **新增 TXT 記錄** ] 表單中，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-132">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="dc0d7-133">**名稱**</span><span class="sxs-lookup"><span data-stu-id="dc0d7-133">**Name**</span></span>|<span data-ttu-id="dc0d7-134">\*\*TTL (秒) \*\*</span><span class="sxs-lookup"><span data-stu-id="dc0d7-134">**TTL (SEC)**</span></span>|<span data-ttu-id="dc0d7-135">\*\*TXT (指向 address 或 value) \*\*</span><span class="sxs-lookup"><span data-stu-id="dc0d7-135">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="dc0d7-136">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="dc0d7-136">(leave blank)</span></span>  <br/> |<span data-ttu-id="dc0d7-137">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-137">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="dc0d7-138">"MS=msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="dc0d7-138">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="dc0d7-139">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-139">**Note:** This is an example.</span></span> <span data-ttu-id="dc0d7-140">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="dc0d7-141">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="dc0d7-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="dc0d7-143">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-143">Select **Add record**.</span></span>
    
<span data-ttu-id="dc0d7-144">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="dc0d7-145">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="dc0d7-146">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="dc0d7-147">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="dc0d7-148">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="dc0d7-149">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="dc0d7-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="dc0d7-153">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="dc0d7-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="dc0d7-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="dc0d7-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="dc0d7-155">若要開始使用，請使用 [此連結](https://theconsole.netregistry.com.au/)移至 Netregistry 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-155">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="dc0d7-156">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="dc0d7-156">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="dc0d7-158">在您要管理的網域旁，選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-158">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="dc0d7-160">選取 [ **區域管理員**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-160">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="dc0d7-162">在 [ **目前區域記錄**] 底下，選取清單中每個 MX 記錄旁邊的 [ **移除** ]，以移除預設的 mx 記錄。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-162">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="dc0d7-164">在 [ **新增區域記錄**] 底下的清單中，選擇 [ **MX 記錄** ]，然後選取 [ **建立新的記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-164">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="dc0d7-166">在 [ **新增 MX 記錄** ] 表單中，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-166">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="dc0d7-167">**名稱**</span><span class="sxs-lookup"><span data-stu-id="dc0d7-167">**Name**</span></span>|<span data-ttu-id="dc0d7-168">\*\*TTL (秒) \*\*</span><span class="sxs-lookup"><span data-stu-id="dc0d7-168">**TTL (SEC)**</span></span>|<span data-ttu-id="dc0d7-169">\*\*Exchange (指向 address 或 value) \*\*</span><span class="sxs-lookup"><span data-stu-id="dc0d7-169">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="dc0d7-170">**主機是否已完全合格？**</span><span class="sxs-lookup"><span data-stu-id="dc0d7-170">**Is host fully qualified?**</span></span>|<span data-ttu-id="dc0d7-171">\*\*喜好設定 (優先順序) \*\*</span><span class="sxs-lookup"><span data-stu-id="dc0d7-171">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dc0d7-172">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="dc0d7-172">(leave blank)</span></span>  <br/> |<span data-ttu-id="dc0d7-173">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-173">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="dc0d7-174">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dc0d7-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="dc0d7-175">\**附注：\*\*\*\<domain-key\>* 從您的 Microsoft 帳戶取得。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="dc0d7-176">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="dc0d7-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="dc0d7-177"> (選取此核取方塊) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-177">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="dc0d7-178">10 </span><span class="sxs-lookup"><span data-stu-id="dc0d7-178">10</span></span>  <br/> <span data-ttu-id="dc0d7-179">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="dc0d7-179">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="dc0d7-181">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-181">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="dc0d7-183">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="dc0d7-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="dc0d7-184"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="dc0d7-184"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="dc0d7-185">若要開始使用，請使用 [此連結](https://theconsole.netregistry.com.au/)移至 Netregistry 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-185">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="dc0d7-186">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="dc0d7-186">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="dc0d7-188">在您要管理的網域旁，選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-188">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="dc0d7-190">選取 [ **區域管理員**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-190">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="dc0d7-192">在 [  **新增區域記錄**] 底下的清單中，選擇 [ **CNAME 記錄** ]，然後選取 [ **建立新的記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-192">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="dc0d7-194">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-194">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="dc0d7-195">**名稱**</span><span class="sxs-lookup"><span data-stu-id="dc0d7-195">**Name**</span></span>|<span data-ttu-id="dc0d7-196">**類型**</span><span class="sxs-lookup"><span data-stu-id="dc0d7-196">**Type**</span></span>|<span data-ttu-id="dc0d7-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dc0d7-197">**TTL**</span></span>|<span data-ttu-id="dc0d7-198">\*\*主機 (指向或位址值) \*\*</span><span class="sxs-lookup"><span data-stu-id="dc0d7-198">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dc0d7-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="dc0d7-199">autodiscover</span></span>  <br/> |<span data-ttu-id="dc0d7-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc0d7-200">CNAME</span></span>  <br/> |<span data-ttu-id="dc0d7-201">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-201">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="dc0d7-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dc0d7-202">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="dc0d7-203">sip</span><span class="sxs-lookup"><span data-stu-id="dc0d7-203">sip</span></span>  <br/> |<span data-ttu-id="dc0d7-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc0d7-204">CNAME</span></span>  <br/> |<span data-ttu-id="dc0d7-205">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-205">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="dc0d7-206">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dc0d7-206">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="dc0d7-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="dc0d7-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="dc0d7-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc0d7-208">CNAME</span></span>  <br/> |<span data-ttu-id="dc0d7-209">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-209">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="dc0d7-210">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dc0d7-210">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="dc0d7-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="dc0d7-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="dc0d7-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc0d7-212">CNAME</span></span>  <br/> |<span data-ttu-id="dc0d7-213">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="dc0d7-214">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="dc0d7-214">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="dc0d7-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="dc0d7-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="dc0d7-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc0d7-216">CNAME</span></span>  <br/> |<span data-ttu-id="dc0d7-217">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="dc0d7-218">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dc0d7-218">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="dc0d7-220">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-220">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="dc0d7-222">重複上述步驟，以建立其他五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-222">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="dc0d7-223">針對每個記錄，輸入或複製並貼上表格中下一列的值，然後將其貼到該記錄的方塊中。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-223">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="dc0d7-224">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="dc0d7-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="dc0d7-225"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="dc0d7-225"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc0d7-226">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="dc0d7-227">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="dc0d7-228">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="dc0d7-229">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="dc0d7-230">若要開始使用，請使用 [此連結](https://theconsole.netregistry.com.au/)移至 Netregistry 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-230">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="dc0d7-231">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="dc0d7-231">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="dc0d7-233">在您要管理的網域旁，選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-233">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="dc0d7-235">選取 [ **區域管理員**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-235">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="dc0d7-237">在 [ **新增區域記錄**] 底下的清單中，選擇 [ **TXT 記錄** ]，然後選取 [ **建立新的記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-237">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="dc0d7-239">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-239">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="dc0d7-240">您必須在 TXT 方塊中的專案前後使用引號。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-240">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="dc0d7-241">**名稱**</span><span class="sxs-lookup"><span data-stu-id="dc0d7-241">**Name**</span></span>|<span data-ttu-id="dc0d7-242">**類型**</span><span class="sxs-lookup"><span data-stu-id="dc0d7-242">**Type**</span></span>|<span data-ttu-id="dc0d7-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dc0d7-243">**TTL**</span></span>|<span data-ttu-id="dc0d7-244">\*\*TXT 資料 (目標) \*\*</span><span class="sxs-lookup"><span data-stu-id="dc0d7-244">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dc0d7-245">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="dc0d7-245">(leave blank)</span></span>  <br/> |<span data-ttu-id="dc0d7-246">TXT</span><span class="sxs-lookup"><span data-stu-id="dc0d7-246">TXT</span></span>  <br/> |<span data-ttu-id="dc0d7-247">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-247">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="dc0d7-248">"v = spf1 包含: spf.protection.outlook.com. .com-all"</span><span class="sxs-lookup"><span data-stu-id="dc0d7-248">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="dc0d7-249">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-249">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="dc0d7-251">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-251">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="dc0d7-253">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="dc0d7-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="dc0d7-254"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="dc0d7-254"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="dc0d7-255">若要開始使用，請使用 [此連結](https://theconsole.netregistry.com.au/)移至 Netregistry 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-255">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="dc0d7-256">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="dc0d7-256">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="dc0d7-258">在您要管理的網域旁，選取 [  **管理**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-258">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="dc0d7-260">選取 [ **區域管理員**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-260">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="dc0d7-262">在 [  **新增區域記錄**] 底下的清單中，選擇 [ **SRV 記錄** ]，然後選取 [ **建立新的記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-262">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="dc0d7-264">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-264">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dc0d7-265">Name 欄位是服務 (的組合，例如 _sip) 和通訊協定 (例如 _tls) 。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-265">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="dc0d7-266">**類型**</span><span class="sxs-lookup"><span data-stu-id="dc0d7-266">**Type**</span></span>|<span data-ttu-id="dc0d7-267">**名稱**</span><span class="sxs-lookup"><span data-stu-id="dc0d7-267">**Name**</span></span>|<span data-ttu-id="dc0d7-268">\*\*TTL (秒) \*\*</span><span class="sxs-lookup"><span data-stu-id="dc0d7-268">**TTL (SEC)**</span></span>|<span data-ttu-id="dc0d7-269">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="dc0d7-269">**Priority**</span></span>|<span data-ttu-id="dc0d7-270">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="dc0d7-270">**Weight**</span></span>|<span data-ttu-id="dc0d7-271">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="dc0d7-271">**Port**</span></span>|<span data-ttu-id="dc0d7-272">**Target**</span><span class="sxs-lookup"><span data-stu-id="dc0d7-272">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dc0d7-273">SRV (服務) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-273">SRV (service)</span></span>  <br/> |<span data-ttu-id="dc0d7-274">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="dc0d7-274">_sip._tls</span></span>  <br/> |<span data-ttu-id="dc0d7-275">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-275">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="dc0d7-276">100</span><span class="sxs-lookup"><span data-stu-id="dc0d7-276">100</span></span>  <br/> |<span data-ttu-id="dc0d7-277">1 </span><span class="sxs-lookup"><span data-stu-id="dc0d7-277">1</span></span>  <br/> |<span data-ttu-id="dc0d7-278">443</span><span class="sxs-lookup"><span data-stu-id="dc0d7-278">443</span></span>  <br/> |<span data-ttu-id="dc0d7-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dc0d7-279">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="dc0d7-280">SRV (服務) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-280">SRV (service)</span></span>  <br/> |<span data-ttu-id="dc0d7-281">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="dc0d7-281">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="dc0d7-282">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="dc0d7-282">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="dc0d7-283">100</span><span class="sxs-lookup"><span data-stu-id="dc0d7-283">100</span></span>  <br/> |<span data-ttu-id="dc0d7-284">1 </span><span class="sxs-lookup"><span data-stu-id="dc0d7-284">1</span></span>  <br/> |<span data-ttu-id="dc0d7-285">5061</span><span class="sxs-lookup"><span data-stu-id="dc0d7-285">5061</span></span>  <br/> |<span data-ttu-id="dc0d7-286">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dc0d7-286">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="dc0d7-288">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-288">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="dc0d7-290">重複上述步驟，以建立其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-290">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="dc0d7-291">在第二筆記錄的方塊中，輸入或複製並貼上表格中第二列的值。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-291">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dc0d7-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dc0d7-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

