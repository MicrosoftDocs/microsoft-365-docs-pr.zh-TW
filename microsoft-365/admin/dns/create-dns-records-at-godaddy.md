---
title: 在 Microsoft 的 GoDaddy 建立 DNS 記錄
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以供 Microsoft GoDaddy。
ms.custom: okr_smb
ms.openlocfilehash: 0e9b75bcd4aa93270efd9b2d94fa2ceeb6e55f75
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629548"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="1d18a-103">在 Microsoft 的 GoDaddy 建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="1d18a-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="1d18a-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="1d18a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="1d18a-105">如果 GoDaddy 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="1d18a-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="1d18a-106">在 GoDaddy 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="1d18a-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

<span data-ttu-id="1d18a-107">若要深入瞭解 Microsoft 的網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="1d18a-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="1d18a-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1d18a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1d18a-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="1d18a-111">Add a TXT record for verification</span></span>
<span data-ttu-id="1d18a-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1d18a-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1d18a-113">在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="1d18a-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="1d18a-114">您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。</span><span class="sxs-lookup"><span data-stu-id="1d18a-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="1d18a-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="1d18a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="1d18a-117">請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="1d18a-117">Follow the steps below.</span></span>

1. <span data-ttu-id="1d18a-p104">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1d18a-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="1d18a-121">在 [**網域**] 底下，選取您要編輯之網域底下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="1d18a-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="1d18a-123">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d18a-123">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="1d18a-125">Choose **TXT (Text)** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1d18a-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="1d18a-126">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="1d18a-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="1d18a-127">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="1d18a-127">**Record type**</span></span> |<span data-ttu-id="1d18a-128">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="1d18a-128">**Host**</span></span>|<span data-ttu-id="1d18a-129">**TXT Value** (TXT 值)</span><span class="sxs-lookup"><span data-stu-id="1d18a-129">**TXT Value**</span></span>|<span data-ttu-id="1d18a-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1d18a-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1d18a-131">TXT (文字)</span><span class="sxs-lookup"><span data-stu-id="1d18a-131">TXT (Text)</span></span>|@|<span data-ttu-id="1d18a-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1d18a-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="1d18a-133">**請注意**：這是一個範例。</span><span class="sxs-lookup"><span data-stu-id="1d18a-133">**Note**: This is an example.</span></span> <span data-ttu-id="1d18a-134">從表格中，使用您的特定**目的地或指向位址**值。</span><span class="sxs-lookup"><span data-stu-id="1d18a-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="1d18a-135">如何找到這項資訊？</span><span class="sxs-lookup"><span data-stu-id="1d18a-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="1d18a-136">1 小時</span><span class="sxs-lookup"><span data-stu-id="1d18a-136">1 hour</span></span>  <br><span data-ttu-id="1d18a-137">（從下拉式清單中選取值）。</span><span class="sxs-lookup"><span data-stu-id="1d18a-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="1d18a-139">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1d18a-139">Select **Save**.</span></span>

6. <span data-ttu-id="1d18a-140">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="1d18a-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="1d18a-141">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求記錄。</span><span class="sxs-lookup"><span data-stu-id="1d18a-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="1d18a-142">當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="1d18a-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1d18a-143">在 Microsoft 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="1d18a-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1d18a-144">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="1d18a-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1d18a-145">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="1d18a-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="1d18a-146">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="1d18a-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="1d18a-p107">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1d18a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1d18a-150">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="1d18a-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1d18a-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1d18a-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="1d18a-152">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="1d18a-152">Follow the steps below.</span></span>

1. <span data-ttu-id="1d18a-p108">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1d18a-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="1d18a-156">在 [**網域**] 底下，選取您要編輯之網域底下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="1d18a-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="1d18a-158">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d18a-158">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="1d18a-160">從下拉式清單中選擇 [ **MX] （郵件交換器）** 。</span><span class="sxs-lookup"><span data-stu-id="1d18a-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="1d18a-162">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="1d18a-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="1d18a-163">（從下拉式清單中選擇 [ **TTL** ] 值。）</span><span class="sxs-lookup"><span data-stu-id="1d18a-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="1d18a-164">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="1d18a-164">**Record type**</span></span>|<span data-ttu-id="1d18a-165">**Host**</span><span class="sxs-lookup"><span data-stu-id="1d18a-165">**Host**</span></span>|<span data-ttu-id="1d18a-166">**Points to** (指向)</span><span class="sxs-lookup"><span data-stu-id="1d18a-166">**Points to**</span></span>|<span data-ttu-id="1d18a-167">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="1d18a-167">**Priority**</span></span>|<span data-ttu-id="1d18a-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1d18a-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1d18a-169">MX (郵件交換程式)</span><span class="sxs-lookup"><span data-stu-id="1d18a-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="1d18a-170">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1d18a-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="1d18a-171">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="1d18a-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="1d18a-172">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="1d18a-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1d18a-173">10 </span><span class="sxs-lookup"><span data-stu-id="1d18a-173">10</span></span>  <br/> <span data-ttu-id="1d18a-174">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="1d18a-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="1d18a-175">1 小時</span><span class="sxs-lookup"><span data-stu-id="1d18a-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="1d18a-176">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1d18a-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1d18a-177">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="1d18a-177">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1d18a-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1d18a-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="1d18a-179">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="1d18a-179">Follow the steps below.</span></span>

1. <span data-ttu-id="1d18a-p110">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1d18a-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="1d18a-183">在 [**網域**] 底下，選取您要編輯之網域底下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="1d18a-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="1d18a-185">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d18a-185">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="1d18a-187">從下拉式清單中選擇 [ **CNAME （別名）** ]。</span><span class="sxs-lookup"><span data-stu-id="1d18a-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="1d18a-189">建立第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="1d18a-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="1d18a-190">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="1d18a-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="1d18a-191">（從下拉式清單中選擇 [ **TTL** ] 值。）</span><span class="sxs-lookup"><span data-stu-id="1d18a-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="1d18a-192">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="1d18a-192">**Record type**</span></span>|<span data-ttu-id="1d18a-193">**Host**</span><span class="sxs-lookup"><span data-stu-id="1d18a-193">**Host**</span></span>|<span data-ttu-id="1d18a-194">**Points to** (指向)</span><span class="sxs-lookup"><span data-stu-id="1d18a-194">**Points to**</span></span>|<span data-ttu-id="1d18a-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1d18a-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1d18a-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="1d18a-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1d18a-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1d18a-197">autodiscover</span></span>  <br/> |<span data-ttu-id="1d18a-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1d18a-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="1d18a-199">1 小時</span><span class="sxs-lookup"><span data-stu-id="1d18a-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="1d18a-200">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="1d18a-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1d18a-201">sip</span><span class="sxs-lookup"><span data-stu-id="1d18a-201">sip</span></span>  <br/> |<span data-ttu-id="1d18a-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1d18a-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1d18a-203">1 小時</span><span class="sxs-lookup"><span data-stu-id="1d18a-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="1d18a-204">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="1d18a-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1d18a-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1d18a-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1d18a-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1d18a-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1d18a-207">1 小時</span><span class="sxs-lookup"><span data-stu-id="1d18a-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="1d18a-208">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="1d18a-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1d18a-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1d18a-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1d18a-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1d18a-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="1d18a-211">1 小時</span><span class="sxs-lookup"><span data-stu-id="1d18a-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="1d18a-212">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="1d18a-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1d18a-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1d18a-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1d18a-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1d18a-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="1d18a-215">1 小時</span><span class="sxs-lookup"><span data-stu-id="1d18a-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="1d18a-216">重複這些步驟，以新增下一個 CNAME 記錄，直到您已建立所有的六筆 CNAME 記錄為止。</span><span class="sxs-lookup"><span data-stu-id="1d18a-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1d18a-217">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="1d18a-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1d18a-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1d18a-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d18a-219">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="1d18a-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1d18a-220">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="1d18a-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1d18a-221">如果您已有網域的 SPF 記錄，請不要為 Microsoft 建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="1d18a-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1d18a-222">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="1d18a-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="1d18a-223">請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="1d18a-223">Follow the steps below.</span></span>

1. <span data-ttu-id="1d18a-p112">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1d18a-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="1d18a-227">在 [**網域**] 底下，選取您要編輯之網域底下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="1d18a-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="1d18a-229">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d18a-229">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="1d18a-231">Choose **TXT (Text)** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="1d18a-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="1d18a-233">在每一筆新記錄的方塊中，輸入或複製並貼上下列的值。</span><span class="sxs-lookup"><span data-stu-id="1d18a-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="1d18a-234">（從下拉式清單中選擇 [ **TTL** ] 值。）</span><span class="sxs-lookup"><span data-stu-id="1d18a-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="1d18a-235">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="1d18a-235">**Record type**</span></span>|<span data-ttu-id="1d18a-236">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="1d18a-236">**Host**</span></span>|<span data-ttu-id="1d18a-237">**TXT Value** (TXT 值)</span><span class="sxs-lookup"><span data-stu-id="1d18a-237">**TXT Value**</span></span>|<span data-ttu-id="1d18a-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1d18a-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1d18a-239">TXT (文字)</span><span class="sxs-lookup"><span data-stu-id="1d18a-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="1d18a-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1d18a-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1d18a-241">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="1d18a-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="1d18a-242">1 hour (1 小時)</span><span class="sxs-lookup"><span data-stu-id="1d18a-242">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="1d18a-244">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1d18a-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1d18a-245">新增 Microsoft 所需的兩筆 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="1d18a-245">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1d18a-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1d18a-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="1d18a-247">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="1d18a-247">Follow the steps below.</span></span>

1. <span data-ttu-id="1d18a-p113">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1d18a-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="1d18a-251">在 [**網域**] 底下，選取您要編輯之網域底下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="1d18a-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="1d18a-253">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d18a-253">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="1d18a-255">從下拉式清單中選擇 [ **SRV （服務）** ]。</span><span class="sxs-lookup"><span data-stu-id="1d18a-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="1d18a-257">建立第一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1d18a-257">Create the first SRV record.</span></span>

    <span data-ttu-id="1d18a-258">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="1d18a-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="1d18a-259">（從下拉式清單中選擇 [**記錄類型**] 和 [ **TTL** ] 值。）</span><span class="sxs-lookup"><span data-stu-id="1d18a-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="1d18a-260">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="1d18a-260">**Record type**</span></span>|<span data-ttu-id="1d18a-261">**Name** (名稱)</span><span class="sxs-lookup"><span data-stu-id="1d18a-261">**Name**</span></span>|<span data-ttu-id="1d18a-262">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="1d18a-262">**Target**</span></span>|<span data-ttu-id="1d18a-263">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="1d18a-263">**Protocol**</span></span>|<span data-ttu-id="1d18a-264">**Service** (服務)</span><span class="sxs-lookup"><span data-stu-id="1d18a-264">**Service**</span></span>|<span data-ttu-id="1d18a-265">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="1d18a-265">**Priority**</span></span>|<span data-ttu-id="1d18a-266">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="1d18a-266">**Weight**</span></span>|<span data-ttu-id="1d18a-267">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="1d18a-267">**Port**</span></span>|<span data-ttu-id="1d18a-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1d18a-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1d18a-269">SRV (Service) (SRV (服務))</span><span class="sxs-lookup"><span data-stu-id="1d18a-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="1d18a-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1d18a-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1d18a-271">_tls</span><span class="sxs-lookup"><span data-stu-id="1d18a-271">_tls</span></span>  <br/> |<span data-ttu-id="1d18a-272">_sip</span><span class="sxs-lookup"><span data-stu-id="1d18a-272">_sip</span></span>  <br/> |<span data-ttu-id="1d18a-273">100</span><span class="sxs-lookup"><span data-stu-id="1d18a-273">100</span></span>  <br/> |<span data-ttu-id="1d18a-274">1 </span><span class="sxs-lookup"><span data-stu-id="1d18a-274">1</span></span>  <br/> |<span data-ttu-id="1d18a-275">443</span><span class="sxs-lookup"><span data-stu-id="1d18a-275">443</span></span>  <br/> |<span data-ttu-id="1d18a-276">1 小時</span><span class="sxs-lookup"><span data-stu-id="1d18a-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="1d18a-277">SRV (Service) (SRV (服務))</span><span class="sxs-lookup"><span data-stu-id="1d18a-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="1d18a-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1d18a-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="1d18a-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="1d18a-279">_tcp</span></span>  <br/> |<span data-ttu-id="1d18a-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="1d18a-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="1d18a-281">100</span><span class="sxs-lookup"><span data-stu-id="1d18a-281">100</span></span>  <br/> |<span data-ttu-id="1d18a-282">1 </span><span class="sxs-lookup"><span data-stu-id="1d18a-282">1</span></span>  <br/> |<span data-ttu-id="1d18a-283">5061</span><span class="sxs-lookup"><span data-stu-id="1d18a-283">5061</span></span>  <br/> |<span data-ttu-id="1d18a-284">1 小時</span><span class="sxs-lookup"><span data-stu-id="1d18a-284">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="1d18a-286">重複**步驟 5**以建立其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1d18a-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="1d18a-287">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1d18a-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="1d18a-p114">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1d18a-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
