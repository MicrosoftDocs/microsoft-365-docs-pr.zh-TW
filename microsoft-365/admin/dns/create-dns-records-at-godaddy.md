---
title: 在 Microsoft 的 GoDaddy 建立 DNS 記錄
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以供 Microsoft GoDaddy。
ms.openlocfilehash: 995e579e21a185084d9ee64a7ee462930d845844
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646124"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="c2403-103">在 Microsoft 的 GoDaddy 建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="c2403-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="c2403-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="c2403-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="c2403-105">如果 GoDaddy 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="c2403-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="c2403-106">在 GoDaddy 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="c2403-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="c2403-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c2403-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c2403-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="c2403-110">Add a TXT record for verification</span></span>
<span data-ttu-id="c2403-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c2403-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c2403-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="c2403-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="c2403-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="c2403-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="c2403-116">請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="c2403-116">Follow the steps below.</span></span>

1. <span data-ttu-id="c2403-p104">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="c2403-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="c2403-120">在 [ **網域**] 底下，選取您要編輯之網域底下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="c2403-120">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="c2403-122">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="c2403-122">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="c2403-124">Choose **TXT (Text)** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="c2403-124">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="c2403-125">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="c2403-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="c2403-126">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="c2403-126">**Record type**</span></span> |<span data-ttu-id="c2403-127">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="c2403-127">**Host**</span></span>|<span data-ttu-id="c2403-128">**TXT Value** (TXT 值)</span><span class="sxs-lookup"><span data-stu-id="c2403-128">**TXT Value**</span></span>|<span data-ttu-id="c2403-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c2403-129">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c2403-130">TXT (文字)</span><span class="sxs-lookup"><span data-stu-id="c2403-130">TXT (Text)</span></span>|@|<span data-ttu-id="c2403-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c2403-131">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="c2403-132">**請注意**：這是一個範例。</span><span class="sxs-lookup"><span data-stu-id="c2403-132">**Note**: This is an example.</span></span> <span data-ttu-id="c2403-133">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="c2403-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="c2403-134">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="c2403-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="c2403-135">1 小時</span><span class="sxs-lookup"><span data-stu-id="c2403-135">1 hour</span></span>  <br><span data-ttu-id="c2403-136"> (從下拉式清單中選取值。 ) </span><span class="sxs-lookup"><span data-stu-id="c2403-136">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="c2403-138">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="c2403-138">Select **Save**.</span></span>

6. <span data-ttu-id="c2403-139">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="c2403-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="c2403-140">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="c2403-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="c2403-141">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="c2403-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c2403-142">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c2403-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="c2403-143">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="c2403-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="c2403-144">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="c2403-144">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="c2403-145">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="c2403-145">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="c2403-p107">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c2403-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c2403-149">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c2403-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c2403-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c2403-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="c2403-151">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="c2403-151">Follow the steps below.</span></span>

1. <span data-ttu-id="c2403-p108">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="c2403-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="c2403-155">在 [ **網域**] 底下，選取您要編輯之網域底下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="c2403-155">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="c2403-157">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="c2403-157">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="c2403-159">從下拉式清單中選擇 [ \*\*MX (郵件交換器]) \*\* 。</span><span class="sxs-lookup"><span data-stu-id="c2403-159">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="c2403-161">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="c2403-161">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="c2403-162"> (從下拉式清單中選取 [ **TTL** ] 值。 ) </span><span class="sxs-lookup"><span data-stu-id="c2403-162">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="c2403-163">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="c2403-163">**Record type**</span></span>|<span data-ttu-id="c2403-164">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="c2403-164">**Host**</span></span>|<span data-ttu-id="c2403-165">**Points to** (指向)</span><span class="sxs-lookup"><span data-stu-id="c2403-165">**Points to**</span></span>|<span data-ttu-id="c2403-166">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="c2403-166">**Priority**</span></span>|<span data-ttu-id="c2403-167">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c2403-167">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c2403-168">MX (郵件交換程式)</span><span class="sxs-lookup"><span data-stu-id="c2403-168">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="c2403-169">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c2403-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="c2403-170">\**附注：\*\*\*\<domain-key\>* 從您的 Microsoft 帳戶取得。</span><span class="sxs-lookup"><span data-stu-id="c2403-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="c2403-171">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="c2403-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="c2403-172">10 </span><span class="sxs-lookup"><span data-stu-id="c2403-172">10</span></span>  <br/> <span data-ttu-id="c2403-173">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="c2403-173">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="c2403-174">1 小時</span><span class="sxs-lookup"><span data-stu-id="c2403-174">1 hour</span></span>  <br/> |

6. <span data-ttu-id="c2403-175">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="c2403-175">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c2403-176">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="c2403-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c2403-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c2403-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="c2403-178">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="c2403-178">Follow the steps below.</span></span>

1. <span data-ttu-id="c2403-p110">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="c2403-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="c2403-182">在 [ **網域**] 底下，選取您要編輯之網域底下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="c2403-182">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="c2403-184">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="c2403-184">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="c2403-186">從下拉式清單中選擇 [ \*\*CNAME (別名]) \*\* 。</span><span class="sxs-lookup"><span data-stu-id="c2403-186">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="c2403-188">建立第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="c2403-188">Create the first CNAME record.</span></span>

    <span data-ttu-id="c2403-189">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="c2403-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="c2403-190"> (從下拉式清單中選取 [ **TTL** ] 值。 ) </span><span class="sxs-lookup"><span data-stu-id="c2403-190">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="c2403-191">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="c2403-191">**Record type**</span></span>|<span data-ttu-id="c2403-192">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="c2403-192">**Host**</span></span>|<span data-ttu-id="c2403-193">**Points to** (指向)</span><span class="sxs-lookup"><span data-stu-id="c2403-193">**Points to**</span></span>|<span data-ttu-id="c2403-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c2403-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c2403-195">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="c2403-195">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="c2403-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c2403-196">autodiscover</span></span>  <br/> |<span data-ttu-id="c2403-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c2403-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="c2403-198">1 小時</span><span class="sxs-lookup"><span data-stu-id="c2403-198">1 hour</span></span>  <br/> |
    |<span data-ttu-id="c2403-199">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="c2403-199">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="c2403-200">sip</span><span class="sxs-lookup"><span data-stu-id="c2403-200">sip</span></span>  <br/> |<span data-ttu-id="c2403-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c2403-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="c2403-202">1 小時</span><span class="sxs-lookup"><span data-stu-id="c2403-202">1 hour</span></span>  <br/> |
    |<span data-ttu-id="c2403-203">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="c2403-203">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="c2403-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c2403-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c2403-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c2403-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="c2403-206">1 小時</span><span class="sxs-lookup"><span data-stu-id="c2403-206">1 hour</span></span>  <br/> |
    |<span data-ttu-id="c2403-207">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="c2403-207">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="c2403-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c2403-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c2403-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c2403-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="c2403-210">1 小時</span><span class="sxs-lookup"><span data-stu-id="c2403-210">1 hour</span></span>  <br/> |
    |<span data-ttu-id="c2403-211">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="c2403-211">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="c2403-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c2403-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c2403-213">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c2403-213">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="c2403-214">1 小時</span><span class="sxs-lookup"><span data-stu-id="c2403-214">1 hour</span></span>  <br/> |



6. <span data-ttu-id="c2403-215">重複這些步驟，以新增下一個 CNAME 記錄，直到您已建立所有的六筆 CNAME 記錄為止。</span><span class="sxs-lookup"><span data-stu-id="c2403-215">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c2403-216">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="c2403-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c2403-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c2403-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2403-218">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="c2403-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c2403-219">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="c2403-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c2403-220">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="c2403-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c2403-221">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="c2403-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="c2403-222">請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="c2403-222">Follow the steps below.</span></span>

1. <span data-ttu-id="c2403-p112">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="c2403-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="c2403-226">在 [ **網域**] 底下，選取您要編輯之網域底下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="c2403-226">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="c2403-228">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="c2403-228">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="c2403-230">Choose **TXT (Text)** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="c2403-230">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="c2403-232">在每一筆新記錄的方塊中，輸入或複製並貼上下列的值。</span><span class="sxs-lookup"><span data-stu-id="c2403-232">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="c2403-233"> (從下拉式清單中選擇 **TTL** 值。 ) </span><span class="sxs-lookup"><span data-stu-id="c2403-233">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="c2403-234">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="c2403-234">**Record type**</span></span>|<span data-ttu-id="c2403-235">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="c2403-235">**Host**</span></span>|<span data-ttu-id="c2403-236">**TXT Value** (TXT 值)</span><span class="sxs-lookup"><span data-stu-id="c2403-236">**TXT Value**</span></span>|<span data-ttu-id="c2403-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c2403-237">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c2403-238">TXT (文字)</span><span class="sxs-lookup"><span data-stu-id="c2403-238">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="c2403-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c2403-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c2403-240">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="c2403-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="c2403-241">1 hour (1 小時)</span><span class="sxs-lookup"><span data-stu-id="c2403-241">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="c2403-243">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="c2403-243">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c2403-244">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="c2403-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c2403-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c2403-245"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="c2403-246">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="c2403-246">Follow the steps below.</span></span>

1. <span data-ttu-id="c2403-p113">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="c2403-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="c2403-250">在 [ **網域**] 底下，選取您要編輯之網域底下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="c2403-250">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="c2403-252">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="c2403-252">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="c2403-254">從下拉式清單中選擇 [ \*\*SRV (服務]) \*\* 。</span><span class="sxs-lookup"><span data-stu-id="c2403-254">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="c2403-256">建立第一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="c2403-256">Create the first SRV record.</span></span>

    <span data-ttu-id="c2403-257">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="c2403-257">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="c2403-258"> (從下拉式清單中選擇 [ **記錄類型** ] 和 [ **TTL** ] 值。 ) </span><span class="sxs-lookup"><span data-stu-id="c2403-258">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="c2403-259">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="c2403-259">**Record type**</span></span>|<span data-ttu-id="c2403-260">**Name** (名稱)</span><span class="sxs-lookup"><span data-stu-id="c2403-260">**Name**</span></span>|<span data-ttu-id="c2403-261">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="c2403-261">**Target**</span></span>|<span data-ttu-id="c2403-262">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="c2403-262">**Protocol**</span></span>|<span data-ttu-id="c2403-263">**Service** (服務)</span><span class="sxs-lookup"><span data-stu-id="c2403-263">**Service**</span></span>|<span data-ttu-id="c2403-264">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="c2403-264">**Priority**</span></span>|<span data-ttu-id="c2403-265">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="c2403-265">**Weight**</span></span>|<span data-ttu-id="c2403-266">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="c2403-266">**Port**</span></span>|<span data-ttu-id="c2403-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c2403-267">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c2403-268">SRV (Service) (SRV (服務))</span><span class="sxs-lookup"><span data-stu-id="c2403-268">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="c2403-269">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c2403-269">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="c2403-270">_tls</span><span class="sxs-lookup"><span data-stu-id="c2403-270">_tls</span></span>  <br/> |<span data-ttu-id="c2403-271">_sip</span><span class="sxs-lookup"><span data-stu-id="c2403-271">_sip</span></span>  <br/> |<span data-ttu-id="c2403-272">100</span><span class="sxs-lookup"><span data-stu-id="c2403-272">100</span></span>  <br/> |<span data-ttu-id="c2403-273">1 </span><span class="sxs-lookup"><span data-stu-id="c2403-273">1</span></span>  <br/> |<span data-ttu-id="c2403-274">443</span><span class="sxs-lookup"><span data-stu-id="c2403-274">443</span></span>  <br/> |<span data-ttu-id="c2403-275">1 小時</span><span class="sxs-lookup"><span data-stu-id="c2403-275">1 hour</span></span>  <br/> |
    |<span data-ttu-id="c2403-276">SRV (Service) (SRV (服務))</span><span class="sxs-lookup"><span data-stu-id="c2403-276">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="c2403-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c2403-277">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="c2403-278">_tcp</span><span class="sxs-lookup"><span data-stu-id="c2403-278">_tcp</span></span>  <br/> |<span data-ttu-id="c2403-279">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c2403-279">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="c2403-280">100</span><span class="sxs-lookup"><span data-stu-id="c2403-280">100</span></span>  <br/> |<span data-ttu-id="c2403-281">1 </span><span class="sxs-lookup"><span data-stu-id="c2403-281">1</span></span>  <br/> |<span data-ttu-id="c2403-282">5061</span><span class="sxs-lookup"><span data-stu-id="c2403-282">5061</span></span>  <br/> |<span data-ttu-id="c2403-283">1 小時</span><span class="sxs-lookup"><span data-stu-id="c2403-283">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="c2403-285">重複 **步驟 5** 以建立其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="c2403-285">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="c2403-286">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="c2403-286">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="c2403-p114">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c2403-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
