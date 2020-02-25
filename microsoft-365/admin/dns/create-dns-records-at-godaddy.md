---
title: 在 GoDaddy 建立 Office 365 的 DNS 記錄
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: 了解如何驗證您的網域和設定 Office 365 電子郵件、 Skype for Business Online，與其他服務在 GoDaddy 的 DNS 記錄。
ms.custom: okr_smb
ms.openlocfilehash: 4a67ef090c2b91c4cf1fdde376ab35e3a4ed4e20
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239147"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="7f569-103">在 GoDaddy 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="7f569-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="7f569-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="7f569-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="7f569-105">如果 GoDaddy 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="7f569-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="7f569-106">在 GoDaddy 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="7f569-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="7f569-107">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="7f569-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="7f569-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="7f569-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7f569-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="7f569-111">Add a TXT record for verification</span></span>
<span data-ttu-id="7f569-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7f569-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7f569-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="7f569-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="7f569-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="7f569-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="7f569-117">請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="7f569-117">Follow the steps below.</span></span>

1. <span data-ttu-id="7f569-p104">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="7f569-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="7f569-121">[**網域**] 中，選取 [您想要編輯的網域下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="7f569-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="7f569-123">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="7f569-123">Select **Add**.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="7f569-125">Choose **TXT (Text)** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="7f569-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="7f569-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7f569-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="7f569-127">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="7f569-127">**Record type**</span></span> |<span data-ttu-id="7f569-128">**Host (主機)**</span><span class="sxs-lookup"><span data-stu-id="7f569-128">**Host**</span></span>|<span data-ttu-id="7f569-129">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="7f569-129">**TXT Value**</span></span>|<span data-ttu-id="7f569-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f569-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f569-131">TXT (文字)</span><span class="sxs-lookup"><span data-stu-id="7f569-131">TXT (Text)</span></span>|@|<span data-ttu-id="7f569-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7f569-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="7f569-133">**附註**： 這是範例。</span><span class="sxs-lookup"><span data-stu-id="7f569-133">**Note**: This is an example.</span></span> <span data-ttu-id="7f569-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f569-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="7f569-135">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="7f569-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="7f569-136">1 hour</span><span class="sxs-lookup"><span data-stu-id="7f569-136">1 hour</span></span>  <br><span data-ttu-id="7f569-137">（從下拉式清單選取值）。</span><span class="sxs-lookup"><span data-stu-id="7f569-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-DYN-BP-CONFIGURE-1-確認-1-0](../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="7f569-139">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7f569-139">Select **Save**.</span></span>

6. <span data-ttu-id="7f569-140">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="7f569-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="7f569-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="7f569-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="7f569-142">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="7f569-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7f569-143">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7f569-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7f569-144">在 [**網域**] 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="7f569-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7f569-145">在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="7f569-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="7f569-146">在 [**驗證網域**] 頁面上，選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="7f569-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="7f569-p107">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="7f569-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="7f569-150">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="7f569-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="7f569-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7f569-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="7f569-152">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="7f569-152">Follow the steps below.</span></span>

1. <span data-ttu-id="7f569-p108">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="7f569-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="7f569-156">[**網域**] 中，選取 [您想要編輯的網域下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="7f569-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="7f569-158">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="7f569-158">Select **Add**.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="7f569-160">從下拉式清單中選擇**MX （郵件交換程式）** 。</span><span class="sxs-lookup"><span data-stu-id="7f569-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-2-0](../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="7f569-162">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="7f569-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="7f569-163">（從下拉式清單選擇 [ **TTL** ] 值）。</span><span class="sxs-lookup"><span data-stu-id="7f569-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="7f569-164">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="7f569-164">**Record type**</span></span>|<span data-ttu-id="7f569-165">**Host (主機)**</span><span class="sxs-lookup"><span data-stu-id="7f569-165">**Host**</span></span>|<span data-ttu-id="7f569-166">\*\*Points to \*\*</span><span class="sxs-lookup"><span data-stu-id="7f569-166">**Points to**</span></span>|<span data-ttu-id="7f569-167">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="7f569-167">**Priority**</span></span>|<span data-ttu-id="7f569-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f569-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f569-169">MX (郵件交換程式)</span><span class="sxs-lookup"><span data-stu-id="7f569-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="7f569-170">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7f569-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="7f569-171">**附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="7f569-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="7f569-172">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="7f569-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="7f569-173">10 </span><span class="sxs-lookup"><span data-stu-id="7f569-173">10</span></span>  <br/> <span data-ttu-id="7f569-174">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="7f569-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="7f569-175">1 hour</span><span class="sxs-lookup"><span data-stu-id="7f569-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="7f569-176">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7f569-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="7f569-177">新增 Office 365 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="7f569-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="7f569-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7f569-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="7f569-179">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="7f569-179">Follow the steps below.</span></span>

1. <span data-ttu-id="7f569-p110">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="7f569-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="7f569-183">[**網域**] 中，選取 [您想要編輯的網域下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="7f569-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="7f569-185">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="7f569-185">Select **Add**.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="7f569-187">從下拉式清單中，選擇 [ **CNAME (Alias)** 。</span><span class="sxs-lookup"><span data-stu-id="7f569-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-3-0](../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="7f569-189">建立第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="7f569-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="7f569-190">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="7f569-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="7f569-191">（從下拉式清單選擇 [ **TTL** ] 值）。</span><span class="sxs-lookup"><span data-stu-id="7f569-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="7f569-192">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="7f569-192">**Record type**</span></span>|<span data-ttu-id="7f569-193">**Host (主機)**</span><span class="sxs-lookup"><span data-stu-id="7f569-193">**Host**</span></span>|<span data-ttu-id="7f569-194">\*\*Points to \*\*</span><span class="sxs-lookup"><span data-stu-id="7f569-194">**Points to**</span></span>|<span data-ttu-id="7f569-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f569-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f569-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="7f569-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7f569-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7f569-197">autodiscover</span></span>  <br/> |<span data-ttu-id="7f569-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7f569-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="7f569-199">1 hour</span><span class="sxs-lookup"><span data-stu-id="7f569-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="7f569-200">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="7f569-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7f569-201">sip</span><span class="sxs-lookup"><span data-stu-id="7f569-201">sip</span></span>  <br/> |<span data-ttu-id="7f569-202">sipdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="7f569-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="7f569-203">1 小時</span><span class="sxs-lookup"><span data-stu-id="7f569-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="7f569-204">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="7f569-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7f569-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7f569-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7f569-206">webdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="7f569-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="7f569-207">1 小時</span><span class="sxs-lookup"><span data-stu-id="7f569-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="7f569-208">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="7f569-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7f569-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7f569-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7f569-210">enterpriseregistration.windows.net></span><span class="sxs-lookup"><span data-stu-id="7f569-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="7f569-211">1 小時</span><span class="sxs-lookup"><span data-stu-id="7f569-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="7f569-212">CNAME (Alias) (CNAME (別名))</span><span class="sxs-lookup"><span data-stu-id="7f569-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7f569-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7f569-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7f569-214">enterpriseenrollment.manage.microsoft.com></span><span class="sxs-lookup"><span data-stu-id="7f569-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="7f569-215">1 小時</span><span class="sxs-lookup"><span data-stu-id="7f569-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="7f569-216">重複這些步驟來新增的下一筆 CNAME 記錄，直到建立完所有六筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="7f569-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7f569-217">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="7f569-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7f569-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7f569-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f569-219">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="7f569-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7f569-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="7f569-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7f569-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f569-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="7f569-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="7f569-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="7f569-223">請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="7f569-223">Follow the steps below.</span></span>

1. <span data-ttu-id="7f569-p112">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="7f569-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="7f569-227">[**網域**] 中，選取 [您想要編輯的網域下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="7f569-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="7f569-229">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="7f569-229">Select **Add**.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="7f569-231">Choose **TXT (Text)** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="7f569-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-4-0](../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="7f569-233">在每一筆新記錄的方塊中，輸入或複製並貼上下列的值。</span><span class="sxs-lookup"><span data-stu-id="7f569-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="7f569-234">（從下拉式清單選擇 [ **TTL** ] 值）。</span><span class="sxs-lookup"><span data-stu-id="7f569-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="7f569-235">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="7f569-235">**Record type**</span></span>|<span data-ttu-id="7f569-236">**Host (主機)**</span><span class="sxs-lookup"><span data-stu-id="7f569-236">**Host**</span></span>|<span data-ttu-id="7f569-237">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="7f569-237">**TXT Value**</span></span>|<span data-ttu-id="7f569-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f569-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f569-239">TXT (文字)</span><span class="sxs-lookup"><span data-stu-id="7f569-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="7f569-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7f569-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7f569-241">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="7f569-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="7f569-242">1 hour</span><span class="sxs-lookup"><span data-stu-id="7f569-242">1 hour</span></span>  <br/> |

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-4-1](../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="7f569-244">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7f569-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="7f569-245">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="7f569-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="7f569-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7f569-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="7f569-247">請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="7f569-247">Follow the steps below.</span></span>

1. <span data-ttu-id="7f569-p113">首先請用[這個連結](https://account.godaddy.com/products/?go_redirect=disabled)移至 GoDaddy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="7f569-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="7f569-251">[**網域**] 中，選取 [您想要編輯的網域下的 [DNS]。</span><span class="sxs-lookup"><span data-stu-id="7f569-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="7f569-253">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="7f569-253">Select **Add**.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="7f569-255">從下拉式清單中選擇**SRV （服務）** 。</span><span class="sxs-lookup"><span data-stu-id="7f569-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-5-0](../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="7f569-257">建立第一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="7f569-257">Create the first SRV record.</span></span>

    <span data-ttu-id="7f569-258">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="7f569-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="7f569-259">（從下拉式清單選擇 [**記錄類型**] 和 [ **TTL**值）。</span><span class="sxs-lookup"><span data-stu-id="7f569-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="7f569-260">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="7f569-260">**Record type**</span></span>|<span data-ttu-id="7f569-261">**Name**</span><span class="sxs-lookup"><span data-stu-id="7f569-261">**Name**</span></span>|<span data-ttu-id="7f569-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="7f569-262">**Target**</span></span>|<span data-ttu-id="7f569-263">**通訊協定**</span><span class="sxs-lookup"><span data-stu-id="7f569-263">**Protocol**</span></span>|<span data-ttu-id="7f569-264">**服務**</span><span class="sxs-lookup"><span data-stu-id="7f569-264">**Service**</span></span>|<span data-ttu-id="7f569-265">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="7f569-265">**Priority**</span></span>|<span data-ttu-id="7f569-266">**Weight**</span><span class="sxs-lookup"><span data-stu-id="7f569-266">**Weight**</span></span>|<span data-ttu-id="7f569-267">**Port**</span><span class="sxs-lookup"><span data-stu-id="7f569-267">**Port**</span></span>|<span data-ttu-id="7f569-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7f569-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7f569-269">SRV (Service) (SRV (服務))</span><span class="sxs-lookup"><span data-stu-id="7f569-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="7f569-270">sipdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="7f569-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="7f569-271">_tls</span><span class="sxs-lookup"><span data-stu-id="7f569-271">_tls</span></span>  <br/> |<span data-ttu-id="7f569-272">_sip</span><span class="sxs-lookup"><span data-stu-id="7f569-272">_sip</span></span>  <br/> |<span data-ttu-id="7f569-273">100</span><span class="sxs-lookup"><span data-stu-id="7f569-273">100</span></span>  <br/> |<span data-ttu-id="7f569-274">1</span><span class="sxs-lookup"><span data-stu-id="7f569-274">1</span></span>  <br/> |<span data-ttu-id="7f569-275">443</span><span class="sxs-lookup"><span data-stu-id="7f569-275">443</span></span>  <br/> |<span data-ttu-id="7f569-276">1 小時</span><span class="sxs-lookup"><span data-stu-id="7f569-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="7f569-277">SRV (Service) (SRV (服務))</span><span class="sxs-lookup"><span data-stu-id="7f569-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="7f569-278">sipfed.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="7f569-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="7f569-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="7f569-279">_tcp</span></span>  <br/> |<span data-ttu-id="7f569-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7f569-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="7f569-281">100</span><span class="sxs-lookup"><span data-stu-id="7f569-281">100</span></span>  <br/> |<span data-ttu-id="7f569-282">1</span><span class="sxs-lookup"><span data-stu-id="7f569-282">1</span></span>  <br/> |<span data-ttu-id="7f569-283">5061</span><span class="sxs-lookup"><span data-stu-id="7f569-283">5061</span></span>  <br/> |<span data-ttu-id="7f569-284">1 小時</span><span class="sxs-lookup"><span data-stu-id="7f569-284">1 hour</span></span>  <br/> |

    ![GoDaddy-DYN-BP-CONFIGURE-1-設定-5-1](../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="7f569-286">重複**步驟 5** ，以建立其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="7f569-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="7f569-287">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7f569-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="7f569-p114">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="7f569-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
