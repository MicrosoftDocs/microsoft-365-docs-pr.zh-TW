---
title: 在 Netregistry 建立 Office 365 的 DNS 記錄
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 Skype for Business Online，並在 Netregistry 其他服務的 DNS 記錄。
ms.openlocfilehash: 91f802afccd337a97b23ca514c9d9921595abcd1
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42348814"
---
# <a name="create-dns-records-at-netregistry-for-office-365"></a><span data-ttu-id="9b81d-103">在 Netregistry 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="9b81d-103">Create DNS records at Netregistry for Office 365</span></span>

<span data-ttu-id="9b81d-104">[檢查網域的常見問題集](../setup/domains-faq.md) ：供您在找不到所需功能時參考。</span><span class="sxs-lookup"><span data-stu-id="9b81d-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9b81d-105">如果 Netregistry 是您 DNS 主機服務提供者，請遵循本篇文章以驗證您的網域和設定 DNS 記錄的電子郵件、 Skype for Business Online 等等中的步驟。</span><span class="sxs-lookup"><span data-stu-id="9b81d-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9b81d-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="9b81d-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="9b81d-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="9b81d-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="9b81d-108">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="9b81d-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [<span data-ttu-id="9b81d-109">新增 Office 365 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="9b81d-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="9b81d-110">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="9b81d-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="9b81d-111">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="9b81d-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="9b81d-112">在 Netregistry 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="9b81d-112">After you add these records at Netregistry, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="9b81d-113">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9b81d-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b81d-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9b81d-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9b81d-117">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="9b81d-117">Add a TXT record for verification</span></span>
<span data-ttu-id="9b81d-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="9b81d-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="9b81d-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="9b81d-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b81d-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="9b81d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9b81d-123">若要開始，使用[此連結](https://theconsole.netregistry.com.au/)移至您在 Netregistry 中的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="9b81d-123">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="9b81d-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="9b81d-124">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="9b81d-126">您想要管理的網域旁, 選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-126">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="9b81d-128">選取**區域管理員**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-128">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="9b81d-130">在 [**新增區域記錄**] 從清單中，選擇 [ **TXT 記錄**，然後選取 [**建立新的記錄**。</span><span class="sxs-lookup"><span data-stu-id="9b81d-130">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="9b81d-132">您必須使用引號之前和之後 [TXT] 方塊中的項目。</span><span class="sxs-lookup"><span data-stu-id="9b81d-132">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="9b81d-133">在**新的 TXT 記錄**表單中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="9b81d-133">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="9b81d-134">**名稱**</span><span class="sxs-lookup"><span data-stu-id="9b81d-134">**Name**</span></span>|<span data-ttu-id="9b81d-135">**TTL （秒）**</span><span class="sxs-lookup"><span data-stu-id="9b81d-135">**TTL (SEC)**</span></span>|<span data-ttu-id="9b81d-136">**TXT （指向位址] 或 [值）**</span><span class="sxs-lookup"><span data-stu-id="9b81d-136">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9b81d-137">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="9b81d-137">(leave blank)</span></span>  <br/> |<span data-ttu-id="9b81d-138">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="9b81d-138">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9b81d-139">"MS = msXXXXXXXX 」</span><span class="sxs-lookup"><span data-stu-id="9b81d-139">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="9b81d-140">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="9b81d-140">**Note:** This is an example.</span></span> <span data-ttu-id="9b81d-141">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="9b81d-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="9b81d-142">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="9b81d-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="9b81d-144">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-144">Select **Add record**.</span></span>
    
<span data-ttu-id="9b81d-145">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="9b81d-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="9b81d-146">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="9b81d-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9b81d-147">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="9b81d-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9b81d-148">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="9b81d-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9b81d-149">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="9b81d-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9b81d-150">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="9b81d-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9b81d-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9b81d-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="9b81d-154">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="9b81d-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="9b81d-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="9b81d-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="9b81d-156">若要開始，使用[此連結](https://theconsole.netregistry.com.au/)移至您在 Netregistry 中的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="9b81d-156">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="9b81d-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="9b81d-157">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="9b81d-159">您想要管理的網域旁, 選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-159">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="9b81d-161">選取**區域管理員**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-161">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="9b81d-163">在**目前區域記錄**，移除預設的 MX 記錄所選取清單中每一個 MX 記錄旁的 [**移除**。</span><span class="sxs-lookup"><span data-stu-id="9b81d-163">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="9b81d-165">在 [**新增區域記錄**] 從清單中，選擇 [ **MX 記錄**，然後選取 [**建立新的記錄**。</span><span class="sxs-lookup"><span data-stu-id="9b81d-165">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="9b81d-167">在**新的 MX 記錄**表單中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="9b81d-167">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="9b81d-168">**名稱**</span><span class="sxs-lookup"><span data-stu-id="9b81d-168">**Name**</span></span>|<span data-ttu-id="9b81d-169">**TTL （秒）**</span><span class="sxs-lookup"><span data-stu-id="9b81d-169">**TTL (SEC)**</span></span>|<span data-ttu-id="9b81d-170">**Exchange （指向位址] 或 [值）**</span><span class="sxs-lookup"><span data-stu-id="9b81d-170">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="9b81d-171">**為主機的完整？**</span><span class="sxs-lookup"><span data-stu-id="9b81d-171">**Is host fully qualified?**</span></span>|<span data-ttu-id="9b81d-172">**喜好設定 （優先順序）**</span><span class="sxs-lookup"><span data-stu-id="9b81d-172">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b81d-173">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="9b81d-173">(leave blank)</span></span>  <br/> |<span data-ttu-id="9b81d-174">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="9b81d-174">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="9b81d-175">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9b81d-175">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9b81d-176">**附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="9b81d-176">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="9b81d-177">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="9b81d-177">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="9b81d-178">（選取這個核取方塊）</span><span class="sxs-lookup"><span data-stu-id="9b81d-178">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="9b81d-179">10 </span><span class="sxs-lookup"><span data-stu-id="9b81d-179">10</span></span>  <br/> <span data-ttu-id="9b81d-180">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="9b81d-180">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="9b81d-182">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-182">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="9b81d-184">新增 Office 365 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="9b81d-184">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="9b81d-185"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="9b81d-185"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="9b81d-186">若要開始，使用[此連結](https://theconsole.netregistry.com.au/)移至您在 Netregistry 中的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="9b81d-186">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="9b81d-187">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="9b81d-187">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="9b81d-189">您想要管理的網域旁, 選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-189">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="9b81d-191">選取**區域管理員**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-191">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="9b81d-193">在 [**新增區域記錄**] 從清單中，選擇 [ **CNAME 記錄**，然後選取 [**建立新的記錄**。</span><span class="sxs-lookup"><span data-stu-id="9b81d-193">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="9b81d-195">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="9b81d-195">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="9b81d-196">**名稱**</span><span class="sxs-lookup"><span data-stu-id="9b81d-196">**Name**</span></span>|<span data-ttu-id="9b81d-197">**Type**</span><span class="sxs-lookup"><span data-stu-id="9b81d-197">**Type**</span></span>|<span data-ttu-id="9b81d-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b81d-198">**TTL**</span></span>|<span data-ttu-id="9b81d-199">**主機 （以點為單位或位址] 值）**</span><span class="sxs-lookup"><span data-stu-id="9b81d-199">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b81d-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9b81d-200">autodiscover</span></span>  <br/> |<span data-ttu-id="9b81d-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b81d-201">CNAME</span></span>  <br/> |<span data-ttu-id="9b81d-202">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="9b81d-202">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9b81d-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9b81d-203">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="9b81d-204">sip</span><span class="sxs-lookup"><span data-stu-id="9b81d-204">sip</span></span>  <br/> |<span data-ttu-id="9b81d-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b81d-205">CNAME</span></span>  <br/> |<span data-ttu-id="9b81d-206">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="9b81d-206">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9b81d-207">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b81d-207">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9b81d-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9b81d-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9b81d-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b81d-209">CNAME</span></span>  <br/> |<span data-ttu-id="9b81d-210">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="9b81d-210">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9b81d-211">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b81d-211">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9b81d-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9b81d-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9b81d-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b81d-213">CNAME</span></span>  <br/> |<span data-ttu-id="9b81d-214">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="9b81d-214">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9b81d-215">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9b81d-215">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="9b81d-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9b81d-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9b81d-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b81d-217">CNAME</span></span>  <br/> |<span data-ttu-id="9b81d-218">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="9b81d-218">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9b81d-219">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9b81d-219">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="9b81d-221">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-221">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="9b81d-223">重複上述步驟建立其他五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="9b81d-223">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="9b81d-224">每一筆記錄，輸入或複製並貼入該記錄的方塊中的表格中下一列中的值。</span><span class="sxs-lookup"><span data-stu-id="9b81d-224">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9b81d-225">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="9b81d-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9b81d-226"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="9b81d-226"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b81d-227">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="9b81d-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9b81d-228">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="9b81d-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9b81d-229">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="9b81d-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="9b81d-230">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="9b81d-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="9b81d-231">若要開始，使用[此連結](https://theconsole.netregistry.com.au/)移至您在 Netregistry 中的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="9b81d-231">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="9b81d-232">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="9b81d-232">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="9b81d-234">您想要管理的網域旁, 選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-234">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="9b81d-236">選取**區域管理員**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-236">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="9b81d-238">在 [**新增區域記錄**] 從清單中，選擇 [ **TXT 記錄**，然後選取 [**建立新的記錄**。</span><span class="sxs-lookup"><span data-stu-id="9b81d-238">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="9b81d-240">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="9b81d-240">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9b81d-241">您必須使用引號之前和之後 [TXT] 方塊中的項目。</span><span class="sxs-lookup"><span data-stu-id="9b81d-241">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="9b81d-242">**名稱**</span><span class="sxs-lookup"><span data-stu-id="9b81d-242">**Name**</span></span>|<span data-ttu-id="9b81d-243">**Type**</span><span class="sxs-lookup"><span data-stu-id="9b81d-243">**Type**</span></span>|<span data-ttu-id="9b81d-244">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b81d-244">**TTL**</span></span>|<span data-ttu-id="9b81d-245">**TXT Data （目標）**</span><span class="sxs-lookup"><span data-stu-id="9b81d-245">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b81d-246">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="9b81d-246">(leave blank)</span></span>  <br/> |<span data-ttu-id="9b81d-247">TXT</span><span class="sxs-lookup"><span data-stu-id="9b81d-247">TXT</span></span>  <br/> |<span data-ttu-id="9b81d-248">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="9b81d-248">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9b81d-249">「 v = spf1 include: spf.protection.outlook.com-所有 」</span><span class="sxs-lookup"><span data-stu-id="9b81d-249">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="9b81d-250">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="9b81d-250">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="9b81d-252">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-252">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="9b81d-254">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="9b81d-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="9b81d-255"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="9b81d-255"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="9b81d-256">若要開始，使用[此連結](https://theconsole.netregistry.com.au/)移至您在 Netregistry 中的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="9b81d-256">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="9b81d-257">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="9b81d-257">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="9b81d-259">您想要管理的網域旁, 選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-259">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="9b81d-261">選取**區域管理員**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-261">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="9b81d-263">在 [**新增區域記錄**] 從清單中，選擇 [ **SRV 記錄**，然後選取 [**建立新的記錄**。</span><span class="sxs-lookup"><span data-stu-id="9b81d-263">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="9b81d-265">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="9b81d-265">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9b81d-266">[名稱] 欄位是服務 (例如，_sip) 和通訊協定 (例如，_tls) 的組合。</span><span class="sxs-lookup"><span data-stu-id="9b81d-266">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="9b81d-267">**類型**</span><span class="sxs-lookup"><span data-stu-id="9b81d-267">**Type**</span></span>|<span data-ttu-id="9b81d-268">**名稱**</span><span class="sxs-lookup"><span data-stu-id="9b81d-268">**Name**</span></span>|<span data-ttu-id="9b81d-269">**TTL （秒）**</span><span class="sxs-lookup"><span data-stu-id="9b81d-269">**TTL (SEC)**</span></span>|<span data-ttu-id="9b81d-270">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="9b81d-270">**Priority**</span></span>|<span data-ttu-id="9b81d-271">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="9b81d-271">**Weight**</span></span>|<span data-ttu-id="9b81d-272">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="9b81d-272">**Port**</span></span>|<span data-ttu-id="9b81d-273">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="9b81d-273">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b81d-274">SRV （服務）</span><span class="sxs-lookup"><span data-stu-id="9b81d-274">SRV (service)</span></span>  <br/> |<span data-ttu-id="9b81d-275">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="9b81d-275">_sip._tls</span></span>  <br/> |<span data-ttu-id="9b81d-276">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="9b81d-276">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9b81d-277">100</span><span class="sxs-lookup"><span data-stu-id="9b81d-277">100</span></span>  <br/> |<span data-ttu-id="9b81d-278">1</span><span class="sxs-lookup"><span data-stu-id="9b81d-278">1</span></span>  <br/> |<span data-ttu-id="9b81d-279">443</span><span class="sxs-lookup"><span data-stu-id="9b81d-279">443</span></span>  <br/> |<span data-ttu-id="9b81d-280">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b81d-280">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9b81d-281">SRV （服務）</span><span class="sxs-lookup"><span data-stu-id="9b81d-281">SRV (service)</span></span>  <br/> |<span data-ttu-id="9b81d-282">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="9b81d-282">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="9b81d-283">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="9b81d-283">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="9b81d-284">100</span><span class="sxs-lookup"><span data-stu-id="9b81d-284">100</span></span>  <br/> |<span data-ttu-id="9b81d-285">1</span><span class="sxs-lookup"><span data-stu-id="9b81d-285">1</span></span>  <br/> |<span data-ttu-id="9b81d-286">5061</span><span class="sxs-lookup"><span data-stu-id="9b81d-286">5061</span></span>  <br/> |<span data-ttu-id="9b81d-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b81d-287">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="9b81d-289">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="9b81d-289">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="9b81d-291">重複上述步驟建立其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="9b81d-291">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="9b81d-292">在第二筆記錄的方塊中，輸入或複製並貼上表格中第二列的值。</span><span class="sxs-lookup"><span data-stu-id="9b81d-292">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9b81d-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9b81d-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

