---
title: 在 DNSMadeEasy 建立 Office 365 的 DNS 記錄
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: 了解如何驗證您的網域和設定 Office 365 電子郵件、 Skype for Business Online，與其他服務在 DNSMadeEasy 的 DNS 記錄。
ms.openlocfilehash: 82244d216652b1957aefc3b81acd881ea4b32393
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350314"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a><span data-ttu-id="df8af-103">在 DNSMadeEasy 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="df8af-103">Create DNS records at DNSMadeEasy for Office 365</span></span>

 <span data-ttu-id="df8af-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="df8af-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="df8af-105">如果 DNSMadeEasy 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="df8af-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="df8af-106">在 DNSMadeEasy 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="df8af-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="df8af-107">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="df8af-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="df8af-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="df8af-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="df8af-109">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="df8af-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="df8af-110">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="df8af-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="df8af-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="df8af-111">Add a TXT record for verification</span></span>
<span data-ttu-id="df8af-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="df8af-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="df8af-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="df8af-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df8af-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="df8af-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="df8af-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span><span class="sxs-lookup"><span data-stu-id="df8af-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="df8af-118">DNSMadeEasy does not offer domain registration services.</span><span class="sxs-lookup"><span data-stu-id="df8af-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="df8af-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span><span class="sxs-lookup"><span data-stu-id="df8af-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="df8af-120">首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="df8af-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="df8af-121">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="df8af-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="df8af-122">在 [**管理主控台**] 頁面上，在**最近更新的網域**] 區域中，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="df8af-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="df8af-123">在 [ **Managed DNS** ] 頁面的 [ **TXT 記錄**] 區域中，選取 [( **+**) 控制項 （**新增**）。</span><span class="sxs-lookup"><span data-stu-id="df8af-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="df8af-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="df8af-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="df8af-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="df8af-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="df8af-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="df8af-126">**Name**</span></span> <br/> |<span data-ttu-id="df8af-127">**值**</span><span class="sxs-lookup"><span data-stu-id="df8af-127">**Value**</span></span> <br/> |<span data-ttu-id="df8af-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df8af-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="df8af-129">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="df8af-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="df8af-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="df8af-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="df8af-131">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="df8af-131">**Note:** This is an example.</span></span> <span data-ttu-id="df8af-132">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="df8af-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="df8af-133">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="df8af-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="df8af-134">1800</span><span class="sxs-lookup"><span data-stu-id="df8af-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="df8af-135">選取 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="df8af-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="df8af-136">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="df8af-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="df8af-137">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="df8af-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="df8af-138">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="df8af-138">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="df8af-139">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="df8af-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="df8af-140">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="df8af-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="df8af-141">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="df8af-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="df8af-142">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="df8af-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="df8af-143">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="df8af-143">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="df8af-144">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="df8af-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="df8af-145">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="df8af-145">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="df8af-146">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="df8af-146">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="df8af-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="df8af-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="df8af-p108">首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="df8af-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="df8af-150">在 [**管理主控台**] 頁面上，在**最近更新的網域**] 區域中，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="df8af-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="df8af-151">在 [**管理主控台**] 頁面上，在**最近更新的網域**] 區域中，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="df8af-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="df8af-153">在 [ **Managed DNS** ] 頁面上，在 [ **MX 記錄**] 區域中，選取 **（+）** 控制項 （**新增**）。</span><span class="sxs-lookup"><span data-stu-id="df8af-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="df8af-154">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="df8af-154">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="df8af-156">在 [**新增 MX 記錄**] 區域中，於新記錄的方塊中輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="df8af-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="df8af-157">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="df8af-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="df8af-158">**名稱**</span><span class="sxs-lookup"><span data-stu-id="df8af-158">**Name**</span></span>|<span data-ttu-id="df8af-159">**伺服器**</span><span class="sxs-lookup"><span data-stu-id="df8af-159">**Server**</span></span>|<span data-ttu-id="df8af-160">**MX Level (MX 等級)**</span><span class="sxs-lookup"><span data-stu-id="df8af-160">**MX Level**</span></span>|<span data-ttu-id="df8af-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df8af-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df8af-162">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="df8af-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="df8af-163">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="df8af-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="df8af-164">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="df8af-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="df8af-165">**注意：** 從您的 Office 365 帳戶取得您的\<*網域金鑰*\>。</span><span class="sxs-lookup"><span data-stu-id="df8af-165">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="df8af-166">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="df8af-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="df8af-167">10 </span><span class="sxs-lookup"><span data-stu-id="df8af-167">10</span></span>  <br/> <span data-ttu-id="df8af-168">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="df8af-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="df8af-169">1800</span><span class="sxs-lookup"><span data-stu-id="df8af-169">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="df8af-171">選取 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="df8af-171">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="df8af-173">如果有任何其他 MX 記錄列在 [ **MX 記錄**] 區段中，請選取每個來刪除全部。</span><span class="sxs-lookup"><span data-stu-id="df8af-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="df8af-175">選取所有記錄時，選取 [**刪除選取的**。</span><span class="sxs-lookup"><span data-stu-id="df8af-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="df8af-177">在 [**刪除的 MX 記錄**] 對話方塊中，選取 [**刪除**] 以確認您的變更。</span><span class="sxs-lookup"><span data-stu-id="df8af-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="df8af-179">新增 Office 365 所需的五筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="df8af-179">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="df8af-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="df8af-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="df8af-p110">首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="df8af-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="df8af-183">在 [**管理主控台**] 頁面上，在**最近更新的網域**] 區域中，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="df8af-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="df8af-184">在 [ **Managed DNS** ] 頁面上**筆 CNAME 記錄**] 區域中，選取 **（+）** 控制項 （**新增**）。</span><span class="sxs-lookup"><span data-stu-id="df8af-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="df8af-185">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="df8af-185">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="df8af-187">新增第一筆五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="df8af-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="df8af-188">在 [**新增 CNAME 記錄**] 區域中，於新記錄的方塊中輸入或複製並貼下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="df8af-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="df8af-189">**名稱**</span><span class="sxs-lookup"><span data-stu-id="df8af-189">**Name**</span></span>|<span data-ttu-id="df8af-190">**Alias to (別名)**</span><span class="sxs-lookup"><span data-stu-id="df8af-190">**Alias to**</span></span>|<span data-ttu-id="df8af-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df8af-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="df8af-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="df8af-192">autodiscover</span></span>  <br/> |<span data-ttu-id="df8af-193">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="df8af-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="df8af-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="df8af-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="df8af-195">1800</span><span class="sxs-lookup"><span data-stu-id="df8af-195">1800</span></span>  <br/> |
    |<span data-ttu-id="df8af-196">sip</span><span class="sxs-lookup"><span data-stu-id="df8af-196">sip</span></span>  <br/> |<span data-ttu-id="df8af-197">sipdir.online.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="df8af-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="df8af-198">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="df8af-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="df8af-199">1800</span><span class="sxs-lookup"><span data-stu-id="df8af-199">1800</span></span>  <br/> |
    |<span data-ttu-id="df8af-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="df8af-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="df8af-201">webdir.online.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="df8af-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="df8af-202">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="df8af-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="df8af-203">1800</span><span class="sxs-lookup"><span data-stu-id="df8af-203">1800</span></span>  <br/> |
    |<span data-ttu-id="df8af-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="df8af-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="df8af-205">enterpriseregistration.windows.net>。</span><span class="sxs-lookup"><span data-stu-id="df8af-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="df8af-206">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="df8af-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="df8af-207">1800</span><span class="sxs-lookup"><span data-stu-id="df8af-207">1800</span></span>  <br/> |
    |<span data-ttu-id="df8af-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="df8af-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="df8af-209">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="df8af-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="df8af-210">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="df8af-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="df8af-211">1800</span><span class="sxs-lookup"><span data-stu-id="df8af-211">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="df8af-213">選取 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="df8af-213">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="df8af-215">新增每個其他四筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="df8af-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="df8af-216">在 [ **CNAME 記錄**] 區段中，選擇 **（+）** 控制項 （**新增**） 在表格中，使用下一列的值來建立記錄，然後再次選擇 [**提交**]，以完成該筆記錄。</span><span class="sxs-lookup"><span data-stu-id="df8af-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="df8af-217">重複此程序，直到五筆 CNAME 記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="df8af-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="df8af-218">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="df8af-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="df8af-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="df8af-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="df8af-220">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="df8af-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="df8af-221">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="df8af-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="df8af-222">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="df8af-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="df8af-223">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="df8af-223">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="df8af-224">需要範例？</span><span class="sxs-lookup"><span data-stu-id="df8af-224">Need examples?</span></span> <span data-ttu-id="df8af-225">請參閱這些 [Office 365 的外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)。</span><span class="sxs-lookup"><span data-stu-id="df8af-225">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="df8af-226">若要驗證您的 SPF 記錄，您可以使用其中一種[SPF 驗證工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="df8af-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="df8af-227">首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="df8af-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="df8af-228">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="df8af-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="df8af-229">在 [**管理主控台**] 頁面上，在**最近更新的網域**] 區域中，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="df8af-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="df8af-230">在 [ **Managed DNS** ] 頁面上，在 [ **TXT 記錄**] 區域中，選取 **（+）** 控制項 （**新增**）。</span><span class="sxs-lookup"><span data-stu-id="df8af-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="df8af-231">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="df8af-231">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="df8af-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="df8af-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="df8af-234">**名稱**</span><span class="sxs-lookup"><span data-stu-id="df8af-234">**Name**</span></span>|<span data-ttu-id="df8af-235">**值**</span><span class="sxs-lookup"><span data-stu-id="df8af-235">**Value**</span></span>|<span data-ttu-id="df8af-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df8af-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="df8af-237">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="df8af-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="df8af-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="df8af-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="df8af-239">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="df8af-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="df8af-240">1800</span><span class="sxs-lookup"><span data-stu-id="df8af-240">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="df8af-242">選取 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="df8af-242">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="df8af-244">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="df8af-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="df8af-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="df8af-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="df8af-p113">首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="df8af-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="df8af-248">在 [**管理主控台**] 頁面上，在**最近更新的網域**] 區域中，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="df8af-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="df8af-249">在 [ **Managed DNS** ] 頁面上**SRV 記錄**] 區域中，選取 **（+）** 控制項 （**新增**）。</span><span class="sxs-lookup"><span data-stu-id="df8af-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="df8af-250">(您可能需要向下捲動)</span><span class="sxs-lookup"><span data-stu-id="df8af-250">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="df8af-252">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="df8af-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="df8af-253">在 [**新增 SRV 記錄**] 區域中，於新記錄的方塊中輸入或複製並貼下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="df8af-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="df8af-254">**名稱**</span><span class="sxs-lookup"><span data-stu-id="df8af-254">**Name**</span></span>|<span data-ttu-id="df8af-255">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="df8af-255">**Priority**</span></span>|<span data-ttu-id="df8af-256">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="df8af-256">**Weight**</span></span>|<span data-ttu-id="df8af-257">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="df8af-257">**Port**</span></span>|<span data-ttu-id="df8af-258">**Host** (主機)</span><span class="sxs-lookup"><span data-stu-id="df8af-258">**Host**</span></span>|<span data-ttu-id="df8af-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df8af-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df8af-260">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="df8af-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="df8af-261">100</span><span class="sxs-lookup"><span data-stu-id="df8af-261">100</span></span>  <br/> |<span data-ttu-id="df8af-262">1</span><span class="sxs-lookup"><span data-stu-id="df8af-262">1</span></span>  <br/> |<span data-ttu-id="df8af-263">443</span><span class="sxs-lookup"><span data-stu-id="df8af-263">443</span></span>  <br/> |<span data-ttu-id="df8af-264">sipdir.online.lync.com>。</span><span class="sxs-lookup"><span data-stu-id="df8af-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="df8af-265">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="df8af-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="df8af-266">1800</span><span class="sxs-lookup"><span data-stu-id="df8af-266">1800</span></span>  <br/> |
    |<span data-ttu-id="df8af-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="df8af-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="df8af-268">100</span><span class="sxs-lookup"><span data-stu-id="df8af-268">100</span></span>  <br/> |<span data-ttu-id="df8af-269">1</span><span class="sxs-lookup"><span data-stu-id="df8af-269">1</span></span>  <br/> |<span data-ttu-id="df8af-270">5061</span><span class="sxs-lookup"><span data-stu-id="df8af-270">5061</span></span>  <br/> |<span data-ttu-id="df8af-271">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="df8af-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="df8af-272">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="df8af-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="df8af-273">1800</span><span class="sxs-lookup"><span data-stu-id="df8af-273">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="df8af-275">選取 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="df8af-275">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-DYN-BP-CONFIGURE-1-設定-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="df8af-277">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="df8af-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="df8af-278">在 [ **SRV 記錄**] 區段中，選擇 **（+）** 控制項 （**新增**） 在表格中，使用下一列的值來建立記錄，然後再次選擇 [**提交**]，以完成該筆記錄。</span><span class="sxs-lookup"><span data-stu-id="df8af-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="df8af-279">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="df8af-279">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="df8af-280">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="df8af-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="df8af-281">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="df8af-281">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

