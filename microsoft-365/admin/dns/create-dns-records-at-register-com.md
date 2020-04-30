---
title: 在 Register.com 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Register.com。
ms.openlocfilehash: 7d1293368a9a7ab94a5556ca266c716280ae85f5
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939116"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="836ea-103">在 Register.com 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="836ea-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="836ea-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="836ea-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="836ea-105">如果 Register.com 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="836ea-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="836ea-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="836ea-106">These are the main records to add.</span></span> <span data-ttu-id="836ea-107">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="836ea-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="836ea-108">在 Register.com 新增 TXT 記錄以驗證您擁有該網域</span><span class="sxs-lookup"><span data-stu-id="836ea-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="836ea-109">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="836ea-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="836ea-110">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="836ea-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="836ea-111">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="836ea-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="836ea-112">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="836ea-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="836ea-113">在 Register.com 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="836ea-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="836ea-114">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="836ea-114">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="836ea-115">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="836ea-115">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="836ea-116">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="836ea-116">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="836ea-117">在 Register.com 新增 TXT 記錄以驗證您擁有該網域</span><span class="sxs-lookup"><span data-stu-id="836ea-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="836ea-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="836ea-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="836ea-p103">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="836ea-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="836ea-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="836ea-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="836ea-123">請依照下列步驟操作或[觀看影片 (從 0:44 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="836ea-123">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="836ea-124">首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="836ea-124">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="836ea-125">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="836ea-125">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="836ea-126">Select **Domains**.</span><span class="sxs-lookup"><span data-stu-id="836ea-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="836ea-127">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="836ea-128">尋找包含您要修改的功能變數名稱的列;然後在該資料列中，選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="836ea-129">向下滾動至 [**高級技術設定**] 區段，然後選取 [**編輯 TXT 記錄（SPF）**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="836ea-130">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="836ea-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="836ea-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="836ea-131">**Host Name**</span></span> <br/> |<span data-ttu-id="836ea-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="836ea-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="836ea-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="836ea-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="836ea-134">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="836ea-134">**Note:** This is an example.</span></span> <span data-ttu-id="836ea-135">在這裡請使用您自己來自表格的 [目的地或指向位址]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="836ea-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="836ea-136">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="836ea-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="836ea-137">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="836ea-138">在下一個頁面上，選取 [**繼續**]，以確認您的變更。</span><span class="sxs-lookup"><span data-stu-id="836ea-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="836ea-139">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="836ea-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="836ea-140">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="836ea-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="836ea-141">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="836ea-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="836ea-142">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="836ea-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="836ea-143">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="836ea-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="836ea-144">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="836ea-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="836ea-145">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="836ea-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="836ea-146">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="836ea-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="836ea-147">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="836ea-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="836ea-148">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="836ea-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="836ea-149">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="836ea-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="836ea-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="836ea-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="836ea-151">請依照下列步驟操作或[觀看影片 (從 3:32 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="836ea-151">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="836ea-152">首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="836ea-152">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="836ea-153">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="836ea-153">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="836ea-154">Select **Domains**.</span><span class="sxs-lookup"><span data-stu-id="836ea-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="836ea-155">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="836ea-156">尋找包含您要修改的功能變數名稱的列;然後在該資料列中，選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="836ea-157">流覽至 [**高級技術設定**] 區段，然後選取 [**編輯郵件交換器記錄**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![選取 [編輯郵件交換器] 記錄](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="836ea-159">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="836ea-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="836ea-160">（從下拉式清單中選擇 [**優先順序**] 值。）</span><span class="sxs-lookup"><span data-stu-id="836ea-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="836ea-161">主機名稱 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="836ea-162">優先順序 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="836ea-163">郵件伺服器 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="836ea-164">高</span><span class="sxs-lookup"><span data-stu-id="836ea-164">High</span></span>  <br/> <span data-ttu-id="836ea-165">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="836ea-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="836ea-166">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="836ea-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="836ea-167">**注意：** 從您的 Microsoft 帳戶取得您的\<*網域金鑰*\>。</span><span class="sxs-lookup"><span data-stu-id="836ea-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="836ea-168">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="836ea-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![複製並貼上表格中的值](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="836ea-170">如果已經列出任何其他 MX 記錄，請逐一選取要刪除的記錄。</span><span class="sxs-lookup"><span data-stu-id="836ea-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="836ea-172">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-172">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="836ea-174">在下一個頁面上，選取 [**繼續**] 以確認並儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="836ea-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![選取 [繼續]](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="836ea-176">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="836ea-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="836ea-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="836ea-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="836ea-178">請依照下列步驟操作或[觀看影片 (從 4:23 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="836ea-178">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="836ea-179">首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="836ea-179">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="836ea-180">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="836ea-180">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="836ea-181">Select **Domains**.</span><span class="sxs-lookup"><span data-stu-id="836ea-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="836ea-182">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="836ea-183">尋找包含您要修改的功能變數名稱的列;然後在該資料列中，選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="836ea-184">流覽至 [**高級技術設定**] 區段，然後選取 [**編輯網域別名記錄**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![選取 [編輯網域別名記錄]](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="836ea-186">選取 [**新增更多網域別名**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-186">Select **Add more domain aliases**.</span></span>
    
    ![選取 [新增更多網域別名]](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="836ea-188">新增所需的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="836ea-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="836ea-189">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="836ea-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="836ea-190">第一個欄位（未標記） \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="836ea-191">指向 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="836ea-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="836ea-192">autodiscover</span></span>  <br/> |<span data-ttu-id="836ea-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="836ea-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="836ea-194">sip</span><span class="sxs-lookup"><span data-stu-id="836ea-194">sip</span></span>  <br/> |<span data-ttu-id="836ea-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="836ea-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="836ea-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="836ea-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="836ea-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="836ea-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="836ea-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="836ea-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="836ea-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="836ea-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="836ea-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="836ea-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="836ea-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="836ea-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![複製並貼上表格中的 DNS 值](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="836ea-203">當您已新增所需的所有 CNAME 記錄後，請選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="836ea-205">在下一個頁面上，選取 [**繼續**] 以確認並儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="836ea-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![選取 [繼續]](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="836ea-207">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="836ea-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="836ea-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="836ea-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="836ea-209">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="836ea-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="836ea-210">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="836ea-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="836ea-211">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="836ea-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="836ea-212">而是，請將必要的 Microsoft 值新增到目前的記錄，以便擁有包含這兩組值的單一 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="836ea-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="836ea-213">請依照下列步驟操作或[觀看影片 (從 5:12 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="836ea-213">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="836ea-214">首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="836ea-214">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="836ea-215">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="836ea-215">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="836ea-216">Select **Domains**.</span><span class="sxs-lookup"><span data-stu-id="836ea-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="836ea-217">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="836ea-218">尋找包含您要修改的功能變數名稱的列;然後在該資料列中，選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="836ea-219">滾動至 [**高級技術設定**] 區段，然後選取 **[編輯 TXT 記錄（SPF）**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![選取 [編輯 TXT 記錄（SPF）]](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="836ea-221">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="836ea-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="836ea-222">主機名稱 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="836ea-223">TXT 記錄 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="836ea-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="836ea-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="836ea-225">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="836ea-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![複製並貼上表格中的值](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="836ea-227">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-227">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="836ea-229">在下一個頁面上，選取 [**繼續**] 以確認並儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="836ea-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![選取 [繼續]](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="836ea-231">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="836ea-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="836ea-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="836ea-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="836ea-233">請依照下列步驟操作或[觀看影片 (從 5:55 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="836ea-233">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="836ea-p112">首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="836ea-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="836ea-236">Select **Domains**.</span><span class="sxs-lookup"><span data-stu-id="836ea-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="836ea-237">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="836ea-238">尋找包含您要修改的功能變數名稱的列;然後在該資料列中，選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="836ea-239">滾動至 [**高級技術設定**] 區段，然後選取 [**編輯 SRV 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![選取 [編輯 SRV 記錄]](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="836ea-241">新增兩筆 SRV 記錄的第一筆：</span><span class="sxs-lookup"><span data-stu-id="836ea-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="836ea-242">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="836ea-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="836ea-243">（從下拉式清單中選擇 [**優先順序**] 值。）</span><span class="sxs-lookup"><span data-stu-id="836ea-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="836ea-244">服務 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="836ea-245">Proto \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="836ea-246">\*\*\*\*名稱\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="836ea-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="836ea-247">優先順序 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="836ea-248">體重 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="836ea-249">埠 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="836ea-250">目標 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="836ea-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="836ea-251">_sip</span><span class="sxs-lookup"><span data-stu-id="836ea-251">_sip</span></span>  <br/> |<span data-ttu-id="836ea-252">_tls</span><span class="sxs-lookup"><span data-stu-id="836ea-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="836ea-253">High (高)</span><span class="sxs-lookup"><span data-stu-id="836ea-253">High</span></span>  <br/> |<span data-ttu-id="836ea-254">1 </span><span class="sxs-lookup"><span data-stu-id="836ea-254">1</span></span>  <br/> |<span data-ttu-id="836ea-255">443</span><span class="sxs-lookup"><span data-stu-id="836ea-255">443</span></span>  <br/> |<span data-ttu-id="836ea-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="836ea-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="836ea-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="836ea-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="836ea-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="836ea-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="836ea-259">High (高)</span><span class="sxs-lookup"><span data-stu-id="836ea-259">High</span></span>  <br/> |<span data-ttu-id="836ea-260">1 </span><span class="sxs-lookup"><span data-stu-id="836ea-260">1</span></span>  <br/> |<span data-ttu-id="836ea-261">5061</span><span class="sxs-lookup"><span data-stu-id="836ea-261">5061</span></span>  <br/> |<span data-ttu-id="836ea-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="836ea-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![複製並貼上表格中的值](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="836ea-264">選取 [**新增更多 SRV 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-264">Select **Add more SRV records**.</span></span>
    
    ![選取 [新增更多 SRV 記錄]](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="836ea-266">新增第二筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="836ea-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="836ea-267">在第二筆記錄的方塊中，輸入或複製並貼上表格中第二列的值。</span><span class="sxs-lookup"><span data-stu-id="836ea-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="836ea-268">當您新增這兩個 SRV 記錄時，請選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="836ea-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="836ea-270">在下一個頁面上，選取 [**繼續**] 以確認並儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="836ea-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![選取 [繼續]](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="836ea-272">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="836ea-272">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="836ea-273">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="836ea-273">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="836ea-274">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="836ea-274">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
