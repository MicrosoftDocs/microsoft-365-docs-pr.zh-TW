---
title: 在 Register.com 建立 Office 365 的 DNS 記錄
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 商務用 Skype 線上商務和 register.com 其他服務的 DNS 記錄。
ms.openlocfilehash: 0210c03a48112d9cc517ae15f879db3b40eb8c94
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42354134"
---
# <a name="create-dns-records-at-registercom-for-office-365"></a><span data-ttu-id="3d7f3-103">在 Register.com 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="3d7f3-103">Create DNS records at Register.com for Office 365</span></span>

 <span data-ttu-id="3d7f3-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3d7f3-105">如果 Register.com 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="3d7f3-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-106">These are the main records to add.</span></span> <span data-ttu-id="3d7f3-107">請依照下列步驟操作或[觀看影片](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="3d7f3-108">在 Register.com 新增 TXT 記錄以驗證您擁有該網域</span><span class="sxs-lookup"><span data-stu-id="3d7f3-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="3d7f3-109">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="3d7f3-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="3d7f3-110">新增 Office 365 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="3d7f3-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="3d7f3-111">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="3d7f3-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="3d7f3-112">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="3d7f3-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="3d7f3-113">在 Register.com 新增這些記錄之後，您的網域就會設定為與 Office 365 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-113">After you add these records at Register.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="3d7f3-114">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d7f3-115">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3d7f3-115">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3d7f3-116">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3d7f3-117">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-117">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="3d7f3-118">在 Register.com 新增 TXT 記錄以驗證您擁有該網域</span><span class="sxs-lookup"><span data-stu-id="3d7f3-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="3d7f3-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3d7f3-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3d7f3-p103">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d7f3-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="3d7f3-124">請依照下列步驟操作或[觀看影片 (從 0:44 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3d7f3-125">首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="3d7f3-126">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="3d7f3-127">Select **Domains**.</span><span class="sxs-lookup"><span data-stu-id="3d7f3-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="3d7f3-128">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="3d7f3-129">尋找包含您要修改的網域名稱的列然後在該資料列中，選取 [**管理**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="3d7f3-130">捲動至 [ **Advanced Technical Settings** ] 區段，然後選取 [**編輯 TXT 記錄 (SPF)**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="3d7f3-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3d7f3-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="3d7f3-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="3d7f3-132">**Host Name**</span></span> <br/> |<span data-ttu-id="3d7f3-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="3d7f3-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="3d7f3-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3d7f3-135">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-135">**Note:** This is an example.</span></span> <span data-ttu-id="3d7f3-136">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-136">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="3d7f3-137">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="3d7f3-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="3d7f3-138">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="3d7f3-139">在 [下一步] 頁面上，選取 [**繼續**]，再以確認您的變更。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="3d7f3-140">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3d7f3-141">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="3d7f3-142">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3d7f3-143">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="3d7f3-144">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="3d7f3-145">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="3d7f3-146">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3d7f3-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3d7f3-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3d7f3-148">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3d7f3-149">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="3d7f3-150">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="3d7f3-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="3d7f3-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3d7f3-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="3d7f3-152">請依照下列步驟操作或[觀看影片 (從 3:32 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3d7f3-153">首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="3d7f3-154">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="3d7f3-155">Select **Domains**.</span><span class="sxs-lookup"><span data-stu-id="3d7f3-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="3d7f3-156">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="3d7f3-157">尋找包含您要修改的網域名稱的列然後在該資料列中，選取 [**管理**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="3d7f3-158">捲動到 [ **Advanced Technical Settings** ] 區段，然後選取 [**編輯郵件交換程式記錄**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![選取 [編輯郵件交換程式記錄](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="3d7f3-160">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="3d7f3-161">（從下拉式清單選擇的**優先順序**值）。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3d7f3-162">主機名稱 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="3d7f3-163">優先順序 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="3d7f3-164">郵件伺服器 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3d7f3-165">高</span><span class="sxs-lookup"><span data-stu-id="3d7f3-165">High</span></span>  <br/> <span data-ttu-id="3d7f3-166">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="3d7f3-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="3d7f3-167">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3d7f3-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="3d7f3-168">**注意：** 從您的 Office 365 帳戶取得您的\<*網域金鑰*\>。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-168">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> <br> [<span data-ttu-id="3d7f3-169">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="3d7f3-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![複製並貼上表格中的值](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="3d7f3-171">如果已經列出任何其他 MX 記錄，請逐一選取要刪除的記錄。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="3d7f3-173">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-173">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="3d7f3-175">在 [下一步] 頁面上，選取 [**繼續]** 再次確認並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![選取 [繼續]](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="3d7f3-177">新增 Office 365 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="3d7f3-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="3d7f3-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3d7f3-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="3d7f3-179">請依照下列步驟操作或[觀看影片 (從 4:23 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3d7f3-180">首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="3d7f3-181">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="3d7f3-182">Select **Domains**.</span><span class="sxs-lookup"><span data-stu-id="3d7f3-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="3d7f3-183">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="3d7f3-184">尋找包含您要修改的網域名稱的列然後在該資料列中，選取 [**管理**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="3d7f3-185">捲動到 [ **Advanced Technical Settings** ] 區段，然後選取 [ **Edit Domain Aliases Records**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![選取 [Edit Domain Aliases Records](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="3d7f3-187">選取 [**新增多個網域別名**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-187">Select **Add more domain aliases**.</span></span>
    
    ![選取 [新增多個網域別名](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="3d7f3-189">新增所需的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="3d7f3-190">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="3d7f3-191">第一個欄位 （沒有標籤） \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="3d7f3-192">指向 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3d7f3-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3d7f3-193">autodiscover</span></span>  <br/> |<span data-ttu-id="3d7f3-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3d7f3-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="3d7f3-195">sip</span><span class="sxs-lookup"><span data-stu-id="3d7f3-195">sip</span></span>  <br/> |<span data-ttu-id="3d7f3-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d7f3-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="3d7f3-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3d7f3-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3d7f3-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d7f3-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="3d7f3-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3d7f3-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3d7f3-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3d7f3-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="3d7f3-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3d7f3-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3d7f3-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3d7f3-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![複製並貼上表格中的 DNS 值](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="3d7f3-204">當您已新增所有您需要的 CNAME 記錄時，選取 [**繼續]**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="3d7f3-206">在 [下一步] 頁面上，選取 [**繼續]** 再次確認並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![選取 [繼續]](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3d7f3-208">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="3d7f3-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3d7f3-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3d7f3-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d7f3-210">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3d7f3-211">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3d7f3-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d7f3-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="3d7f3-213">而是，請將必要的 Office 365 值新增至目前的記錄，以便擁有包含這兩組值的單一 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-213">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="3d7f3-214">請依照下列步驟操作或[觀看影片 (從 5:12 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3d7f3-215">首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="3d7f3-216">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="3d7f3-217">Select **Domains**.</span><span class="sxs-lookup"><span data-stu-id="3d7f3-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="3d7f3-218">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="3d7f3-219">尋找包含您要修改的網域名稱的列然後在該資料列中，選取 [**管理**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="3d7f3-220">捲動到 [ **Advanced Technical Settings** ] 區段，然後選取 [**編輯 TXT 記錄 (SPF)**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![選取 [編輯 TXT 記錄 (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="3d7f3-222">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="3d7f3-223">主機名稱 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="3d7f3-224">TXT 記錄 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="3d7f3-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3d7f3-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3d7f3-226">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![複製並貼上表格中的值](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="3d7f3-228">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-228">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="3d7f3-230">在 [下一步] 頁面上，選取 [**繼續]** 再次確認並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![選取 [繼續]](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="3d7f3-232">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="3d7f3-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="3d7f3-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3d7f3-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="3d7f3-234">請依照下列步驟操作或[觀看影片 (從 5:55 處開始)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3d7f3-p112">首先請用[這個連結](https://www.register.com/myaccount/)移至 Register.com 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="3d7f3-237">Select **Domains**.</span><span class="sxs-lookup"><span data-stu-id="3d7f3-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="3d7f3-238">選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="3d7f3-239">尋找包含您要修改的網域名稱的列然後在該資料列中，選取 [**管理**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="3d7f3-240">捲動到 [ **Advanced Technical Settings** ] 區段，然後選取 [ **Edit SRV Records**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![選取 [Edit SRV 記錄](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="3d7f3-242">新增兩筆 SRV 記錄的第一筆：</span><span class="sxs-lookup"><span data-stu-id="3d7f3-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="3d7f3-243">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="3d7f3-244">（從下拉式清單選擇的**優先順序**值）。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3d7f3-245">服務 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="3d7f3-246">通訊協定 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="3d7f3-247">\*\*\*\*名稱\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="3d7f3-248">優先順序 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="3d7f3-249">權數 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="3d7f3-250">連接埠 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="3d7f3-251">目標 \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d7f3-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3d7f3-252">_sip</span><span class="sxs-lookup"><span data-stu-id="3d7f3-252">_sip</span></span>  <br/> |<span data-ttu-id="3d7f3-253">_tls</span><span class="sxs-lookup"><span data-stu-id="3d7f3-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="3d7f3-254">High (高)</span><span class="sxs-lookup"><span data-stu-id="3d7f3-254">High</span></span>  <br/> |<span data-ttu-id="3d7f3-255">1</span><span class="sxs-lookup"><span data-stu-id="3d7f3-255">1</span></span>  <br/> |<span data-ttu-id="3d7f3-256">443</span><span class="sxs-lookup"><span data-stu-id="3d7f3-256">443</span></span>  <br/> |<span data-ttu-id="3d7f3-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d7f3-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="3d7f3-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="3d7f3-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="3d7f3-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="3d7f3-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="3d7f3-260">High (高)</span><span class="sxs-lookup"><span data-stu-id="3d7f3-260">High</span></span>  <br/> |<span data-ttu-id="3d7f3-261">1</span><span class="sxs-lookup"><span data-stu-id="3d7f3-261">1</span></span>  <br/> |<span data-ttu-id="3d7f3-262">5061</span><span class="sxs-lookup"><span data-stu-id="3d7f3-262">5061</span></span>  <br/> |<span data-ttu-id="3d7f3-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d7f3-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![複製並貼上表格中的值](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="3d7f3-265">選取 [**新增其他 SRV 記錄**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-265">Select **Add more SRV records**.</span></span>
    
    ![選取 [新增其他 SRV 記錄](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="3d7f3-267">新增第二筆 SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="3d7f3-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="3d7f3-268">在第二筆記錄的方塊中，輸入或複製並貼上表格中第二列的值。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="3d7f3-269">當您已新增兩筆 SRV 記錄時，請選取 [**繼續]**。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![選取 [繼續]](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="3d7f3-271">在 [下一步] 頁面上，選取 [**繼續]** 再次確認並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![選取 [繼續]](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="3d7f3-273">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3d7f3-273">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3d7f3-274">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3d7f3-275">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="3d7f3-275">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
