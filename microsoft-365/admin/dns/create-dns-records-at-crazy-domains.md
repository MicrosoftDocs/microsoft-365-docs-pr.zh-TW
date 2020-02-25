---
title: 在 Crazy Domains 建立 Office 365 的 DNS 記錄
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: 了解以驗證您的網域及設定在 Crazy Domains for Office 365 電子郵件、 Skype for Business Online，與其他服務的 DNS 記錄。
ms.openlocfilehash: 5b344ebdc4a4608c27c0a84299ea171391c09ba0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240390"
---
# <a name="create-dns-records-at-crazy-domains-for-office-365"></a><span data-ttu-id="383ce-103">在 Crazy Domains 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="383ce-103">Create DNS records at Crazy Domains for Office 365</span></span>

 <span data-ttu-id="383ce-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="383ce-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="383ce-105">如果 Crazy Domains 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="383ce-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="383ce-106">在 Crazy Domains 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="383ce-106">After you add these records at Crazy Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="383ce-107">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="383ce-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="383ce-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="383ce-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="383ce-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="383ce-111">Add a TXT record for verification</span></span>
<span data-ttu-id="383ce-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="383ce-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="383ce-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="383ce-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="383ce-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="383ce-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="383ce-p104">首先請用[這個連結](https://manage.crazydomains.com/members/domains/)移至 Crazy Domains 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="383ce-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="383ce-120">在 [ **My Account** ] 區段中，選取 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="383ce-122">在 [**網域名稱**] 頁面上，在 [**網域**] 區段中，選取您要更新的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="383ce-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="383ce-124">在 [ **DNS 設定**] 區段中，選取下拉式清單圖示。</span><span class="sxs-lookup"><span data-stu-id="383ce-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="383ce-126">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-126">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="383ce-128">Choose **TXT Record** from the **Add Record** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="383ce-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-確認-1-1](../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="383ce-130">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="383ce-130">Select **Add**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-確認-1-2](../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="383ce-132">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="383ce-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="383ce-133">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="383ce-133">**Sub Domain**</span></span>|<span data-ttu-id="383ce-134">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="383ce-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="383ce-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="383ce-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="383ce-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="383ce-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="383ce-137">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="383ce-137">**Note:** This is an example.</span></span> <span data-ttu-id="383ce-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span><span class="sxs-lookup"><span data-stu-id="383ce-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="383ce-139">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="383ce-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-DYN-BP-CONFIGURE-1-確認-1-3](../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="383ce-141">選取 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-141">Select **Update**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-確認-1-4](../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="383ce-143">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="383ce-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="383ce-144">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="383ce-144">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="383ce-145">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="383ce-145">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="383ce-146">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="383ce-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="383ce-147">在 [**網域**] 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="383ce-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="383ce-148">在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="383ce-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="383ce-149">在 [**驗證網域**] 頁面上，選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="383ce-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="383ce-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="383ce-153">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="383ce-153">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="383ce-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="383ce-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="383ce-p107">首先請用[這個連結](https://manage.crazydomains.com/members/domains/)移至 Crazy Domains 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="383ce-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="383ce-158">在 [ **My Account** ] 區段中，選取 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="383ce-160">在 [**網域名稱**] 頁面上，在 [**網域**] 區段中，選取您要更新的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="383ce-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="383ce-162">在 [ **DNS 設定**] 區段中，選取下拉式清單圖示。</span><span class="sxs-lookup"><span data-stu-id="383ce-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="383ce-164">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-164">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="383ce-166">選擇 [ **MX 記錄**從**新增記錄：** 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="383ce-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-2-1](../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="383ce-168">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="383ce-168">Select **Add**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-2-2](../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="383ce-170">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="383ce-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="383ce-171">（從下拉式清單選擇的**優先順序**值）。</span><span class="sxs-lookup"><span data-stu-id="383ce-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="383ce-172">**Mail For Zone (區域郵件)**</span><span class="sxs-lookup"><span data-stu-id="383ce-172">**Mail For Zone**</span></span>|<span data-ttu-id="383ce-173">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="383ce-173">**Priority**</span></span>|<span data-ttu-id="383ce-174">**Assigned To Server (指派給伺服器)**</span><span class="sxs-lookup"><span data-stu-id="383ce-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="383ce-175">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="383ce-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="383ce-176">1</span><span class="sxs-lookup"><span data-stu-id="383ce-176">1</span></span>  <br/> <span data-ttu-id="383ce-177">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="383ce-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="383ce-178">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="383ce-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="383ce-179">**附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="383ce-179">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="383ce-180">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="383ce-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-2-3](../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="383ce-182">選取 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-182">Select **Update**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-2-4](../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="383ce-184">如果有任何其他 MX 記錄列在 [ **MX 記錄**] 區段中，選取 [**修改**其中的記錄。</span><span class="sxs-lookup"><span data-stu-id="383ce-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-2-5](../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="383ce-186">選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-186">Select **Delete**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-2-6](../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="383ce-188">選取 [**更新**]，以確認刪除。</span><span class="sxs-lookup"><span data-stu-id="383ce-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-2-7](../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="383ce-190">使用相同方法移除清單中其他所有 MX 記錄，直到只剩下您先前在本程序中新增的記錄為止。</span><span class="sxs-lookup"><span data-stu-id="383ce-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="383ce-191">新增 Office 365 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="383ce-191">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="383ce-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="383ce-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="383ce-p109">首先請用[這個連結](https://manage.crazydomains.com/members/domains/)移至 Crazy Domains 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="383ce-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="383ce-196">在 [ **My Account** ] 區段中，選取 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="383ce-198">在 [**網域名稱**] 頁面上，在 [**網域**] 區段中，選取您要更新的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="383ce-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="383ce-200">在 [ **DNS 設定**] 區段中，選取下拉式清單圖示。</span><span class="sxs-lookup"><span data-stu-id="383ce-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="383ce-202">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-202">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="383ce-204">選擇 [ **CNAME 記錄**從**新增記錄：** 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="383ce-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-3-1](../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="383ce-206">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="383ce-206">Select **Add**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-3-2](../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="383ce-208">新增六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="383ce-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="383ce-209">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="383ce-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="383ce-210">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="383ce-210">**Sub Domain**</span></span>|<span data-ttu-id="383ce-211">**Alias for (別名)**</span><span class="sxs-lookup"><span data-stu-id="383ce-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="383ce-212">autodiscover</span><span class="sxs-lookup"><span data-stu-id="383ce-212">autodiscover</span></span>  <br/> |<span data-ttu-id="383ce-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="383ce-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="383ce-214">sip</span><span class="sxs-lookup"><span data-stu-id="383ce-214">sip</span></span>  <br/> |<span data-ttu-id="383ce-215">sipdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="383ce-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="383ce-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="383ce-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="383ce-217">webdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="383ce-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="383ce-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="383ce-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="383ce-219">enterpriseregistration.windows.net></span><span class="sxs-lookup"><span data-stu-id="383ce-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="383ce-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="383ce-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="383ce-221">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="383ce-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-3-3](../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="383ce-223">選取 [**新增 CNAME 記錄**。</span><span class="sxs-lookup"><span data-stu-id="383ce-223">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-3-4](../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="383ce-225">新增第二筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="383ce-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="383ce-226">在新記錄的方塊，在表格中，使用下一列的值，然後再次選擇 [ **Add CNAME Record**。</span><span class="sxs-lookup"><span data-stu-id="383ce-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="383ce-227">重複這個程序，直到六筆 CNAME 記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="383ce-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="383ce-228">選取 [**更新**] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="383ce-228">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-3-5](../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="383ce-230">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="383ce-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="383ce-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="383ce-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="383ce-232">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="383ce-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="383ce-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="383ce-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="383ce-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="383ce-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="383ce-235">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="383ce-235">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="383ce-p111">首先請用[這個連結](https://manage.crazydomains.com/members/domains/)移至 Crazy Domains 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="383ce-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="383ce-239">在 [ **My Account** ] 區段中，選取 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="383ce-241">在 [**網域名稱**] 頁面上，在 [**網域**] 區段中，選取您要更新的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="383ce-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="383ce-243">在 [ **DNS 設定**] 區段中，選取下拉式清單圖示。</span><span class="sxs-lookup"><span data-stu-id="383ce-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="383ce-245">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-245">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="383ce-247">選擇 [ **TXT 記錄**從**新增記錄：** 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="383ce-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-4-1](../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="383ce-249">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="383ce-249">Select **Add**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-4-2](../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="383ce-251">在新記錄的方塊中，輸入或貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="383ce-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="383ce-252">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="383ce-252">**Sub Domain**</span></span>|<span data-ttu-id="383ce-253">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="383ce-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="383ce-254">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="383ce-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="383ce-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="383ce-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="383ce-256">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="383ce-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-4-3](../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="383ce-258">選取 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-258">Select **Update**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-4 4](../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="383ce-260">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="383ce-260">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="383ce-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="383ce-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="383ce-p112">首先請用[這個連結](https://manage.crazydomains.com/members/domains/)移至 Crazy Domains 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="383ce-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="383ce-265">在 [ **My Account** ] 區段中，選取 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="383ce-267">在 [**網域名稱**] 頁面上，在 [**網域**] 區段中，選取您要更新的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="383ce-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="383ce-269">在 [ **DNS 設定**] 區段中，選取下拉式清單圖示。</span><span class="sxs-lookup"><span data-stu-id="383ce-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="383ce-271">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="383ce-271">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="383ce-273">選擇 [ **SRV 記錄**從**新增記錄：** 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="383ce-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-5-1](../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="383ce-275">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="383ce-275">Select **Add**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-5-2](../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="383ce-277">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="383ce-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="383ce-278">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="383ce-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="383ce-279">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="383ce-279">**Record Type**</span></span>|<span data-ttu-id="383ce-280">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="383ce-280">**Sub Domain**</span></span>|<span data-ttu-id="383ce-281">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="383ce-281">**Priority**</span></span>|<span data-ttu-id="383ce-282">**Weight**</span><span class="sxs-lookup"><span data-stu-id="383ce-282">**Weight**</span></span>|<span data-ttu-id="383ce-283">**Port**</span><span class="sxs-lookup"><span data-stu-id="383ce-283">**Port**</span></span>|<span data-ttu-id="383ce-284">**Target**</span><span class="sxs-lookup"><span data-stu-id="383ce-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="383ce-285">SRV Record (SRV 記錄)</span><span class="sxs-lookup"><span data-stu-id="383ce-285">SRV Record</span></span>  <br/> |<span data-ttu-id="383ce-286">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="383ce-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="383ce-287">100</span><span class="sxs-lookup"><span data-stu-id="383ce-287">100</span></span>  <br/> |<span data-ttu-id="383ce-288">1</span><span class="sxs-lookup"><span data-stu-id="383ce-288">1</span></span>  <br/> |<span data-ttu-id="383ce-289">443</span><span class="sxs-lookup"><span data-stu-id="383ce-289">443</span></span>  <br/> |<span data-ttu-id="383ce-290">sipdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="383ce-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="383ce-291">SRV Record (SRV 記錄)</span><span class="sxs-lookup"><span data-stu-id="383ce-291">SRV Record</span></span>  <br/> |<span data-ttu-id="383ce-292">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="383ce-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="383ce-293">100</span><span class="sxs-lookup"><span data-stu-id="383ce-293">100</span></span>  <br/> |<span data-ttu-id="383ce-294">1</span><span class="sxs-lookup"><span data-stu-id="383ce-294">1</span></span>  <br/> |<span data-ttu-id="383ce-295">5061</span><span class="sxs-lookup"><span data-stu-id="383ce-295">5061</span></span>  <br/> |<span data-ttu-id="383ce-296">sipfed.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="383ce-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-5-3](../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="383ce-298">選取 [**新增一筆 SRV 記錄**。</span><span class="sxs-lookup"><span data-stu-id="383ce-298">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-5-4](../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="383ce-300">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="383ce-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="383ce-301">在新記錄的方塊中，使用下表第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="383ce-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="383ce-302">選取 [**更新**] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="383ce-302">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-DYN-BP-CONFIGURE-1-設定-5-5](../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="383ce-p113">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="383ce-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
