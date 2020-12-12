---
title: 在 Microsoft 的 DNSMadeEasy 建立 DNS 記錄
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以供 Microsoft DNSMadeEasy。
ms.openlocfilehash: 719b416564447b3a6f4108b747ae921b4f6f6bb8
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657945"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="1eb84-103">在 Microsoft 的 DNSMadeEasy 建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="1eb84-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="1eb84-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="1eb84-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1eb84-105">如果 DNSMadeEasy 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與商務用 Skype Online 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="1eb84-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="1eb84-106">在 DNSMadeEasy 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="1eb84-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="1eb84-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1eb84-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1eb84-108">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="1eb84-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1eb84-109">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1eb84-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1eb84-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="1eb84-110">Add a TXT record for verification</span></span>
<span data-ttu-id="1eb84-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1eb84-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1eb84-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="1eb84-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1eb84-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="1eb84-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1eb84-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span><span class="sxs-lookup"><span data-stu-id="1eb84-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="1eb84-117">DNSMadeEasy does not offer domain registration services.</span><span class="sxs-lookup"><span data-stu-id="1eb84-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="1eb84-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span><span class="sxs-lookup"><span data-stu-id="1eb84-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="1eb84-119">首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="1eb84-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="1eb84-120">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1eb84-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="1eb84-121">在 [ **管理主控台** ] 頁面上的 [ **最近更新的網域** ] 區域中，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="1eb84-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="1eb84-122">在 [ **受管理的 DNS** ] 頁面上的 [ **TXT 記錄** ] 區域中，選取 [ ( **+**) 控制項] ( [ **新增**) ]。</span><span class="sxs-lookup"><span data-stu-id="1eb84-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="1eb84-123">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="1eb84-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="1eb84-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1eb84-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="1eb84-125">**名稱**</span><span class="sxs-lookup"><span data-stu-id="1eb84-125">**Name**</span></span> <br/> |<span data-ttu-id="1eb84-126">**Value**</span><span class="sxs-lookup"><span data-stu-id="1eb84-126">**Value**</span></span> <br/> |<span data-ttu-id="1eb84-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1eb84-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="1eb84-128">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="1eb84-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1eb84-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1eb84-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1eb84-130">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="1eb84-130">**Note:** This is an example.</span></span> <span data-ttu-id="1eb84-131">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="1eb84-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="1eb84-132">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="1eb84-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1eb84-133">1800</span><span class="sxs-lookup"><span data-stu-id="1eb84-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="1eb84-134">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="1eb84-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="1eb84-135">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="1eb84-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1eb84-136">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="1eb84-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="1eb84-137">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="1eb84-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1eb84-138">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="1eb84-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1eb84-139">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="1eb84-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="1eb84-140">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="1eb84-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="1eb84-141">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="1eb84-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1eb84-142">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1eb84-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1eb84-143">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="1eb84-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1eb84-144">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1eb84-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1eb84-145">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="1eb84-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1eb84-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1eb84-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="1eb84-p108">首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1eb84-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="1eb84-149">在 [ **管理主控台** ] 頁面上的 [ **最近更新的網域** ] 區域中，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="1eb84-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="1eb84-150">在 [ **管理主控台** ] 頁面上的 [ **最近更新的網域** ] 區域中，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="1eb84-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="1eb84-152">在 [ **受管理的 DNS** ] 頁面的 [ **MX 記錄** ] 區域中，選取 [ **(+)** 控制項] ( [ **新增**) ]。</span><span class="sxs-lookup"><span data-stu-id="1eb84-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="1eb84-153">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="1eb84-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="1eb84-155">在 [新增 **MX 記錄** ] 區域的新記錄方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="1eb84-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1eb84-156">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="1eb84-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="1eb84-157">**名稱**</span><span class="sxs-lookup"><span data-stu-id="1eb84-157">**Name**</span></span>|<span data-ttu-id="1eb84-158">**伺服器**</span><span class="sxs-lookup"><span data-stu-id="1eb84-158">**Server**</span></span>|<span data-ttu-id="1eb84-159">**MX Level (MX 等級)**</span><span class="sxs-lookup"><span data-stu-id="1eb84-159">**MX Level**</span></span>|<span data-ttu-id="1eb84-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1eb84-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1eb84-161">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1eb84-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="1eb84-162">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1eb84-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="1eb84-163">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1eb84-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="1eb84-164">**注意：** 從您的 Microsoft 帳戶取得您的 \<*domain-key*\>。</span><span class="sxs-lookup"><span data-stu-id="1eb84-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="1eb84-165">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="1eb84-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1eb84-166">10 </span><span class="sxs-lookup"><span data-stu-id="1eb84-166">10</span></span>  <br/> <span data-ttu-id="1eb84-167">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="1eb84-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="1eb84-168">1800</span><span class="sxs-lookup"><span data-stu-id="1eb84-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="1eb84-170">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="1eb84-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="1eb84-172">如果 [ **Mx 記錄** ] 區段中列出任何其他 MX 記錄，請逐一選取所有的 mx 記錄加以刪除。</span><span class="sxs-lookup"><span data-stu-id="1eb84-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="1eb84-174">選取所有記錄後，請選取 [ **刪除選取** 的]。</span><span class="sxs-lookup"><span data-stu-id="1eb84-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="1eb84-176">在 [ **刪除 MX 記錄** ] 對話方塊中，選取 [ **刪除** ] 以確認您的變更。</span><span class="sxs-lookup"><span data-stu-id="1eb84-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1eb84-178">新增 Microsoft 所需的5筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="1eb84-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1eb84-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1eb84-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="1eb84-p110">首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1eb84-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="1eb84-182">在 [ **管理主控台** ] 頁面上的 [ **最近更新的網域** ] 區域中，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="1eb84-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="1eb84-183">在 [ **受管理的 DNS** ] 頁面上，選取 [ **CNAME 記錄** ] 區域中的 [ **(+)** ] 控制項 ( [ **新增**) ]。</span><span class="sxs-lookup"><span data-stu-id="1eb84-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="1eb84-184">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="1eb84-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="1eb84-186">新增五筆 CNAME 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="1eb84-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="1eb84-187">在 [新增 **CNAME 記錄** ] 區域的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="1eb84-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="1eb84-188">**名稱**</span><span class="sxs-lookup"><span data-stu-id="1eb84-188">**Name**</span></span>|<span data-ttu-id="1eb84-189">**Alias to (別名)**</span><span class="sxs-lookup"><span data-stu-id="1eb84-189">**Alias to**</span></span>|<span data-ttu-id="1eb84-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1eb84-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1eb84-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1eb84-191">autodiscover</span></span>  <br/> |<span data-ttu-id="1eb84-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1eb84-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="1eb84-193">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1eb84-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1eb84-194">1800</span><span class="sxs-lookup"><span data-stu-id="1eb84-194">1800</span></span>  <br/> |
    |<span data-ttu-id="1eb84-195">sip</span><span class="sxs-lookup"><span data-stu-id="1eb84-195">sip</span></span>  <br/> |<span data-ttu-id="1eb84-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1eb84-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1eb84-197">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1eb84-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1eb84-198">1800</span><span class="sxs-lookup"><span data-stu-id="1eb84-198">1800</span></span>  <br/> |
    |<span data-ttu-id="1eb84-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1eb84-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1eb84-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1eb84-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1eb84-201">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1eb84-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1eb84-202">1800</span><span class="sxs-lookup"><span data-stu-id="1eb84-202">1800</span></span>  <br/> |
    |<span data-ttu-id="1eb84-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1eb84-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1eb84-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="1eb84-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="1eb84-205">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1eb84-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1eb84-206">1800</span><span class="sxs-lookup"><span data-stu-id="1eb84-206">1800</span></span>  <br/> |
    |<span data-ttu-id="1eb84-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1eb84-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1eb84-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1eb84-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="1eb84-209">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1eb84-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1eb84-210">1800</span><span class="sxs-lookup"><span data-stu-id="1eb84-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="1eb84-212">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="1eb84-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="1eb84-214">新增其他四筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="1eb84-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="1eb84-215">在 [ **CNAME 記錄** ] 區段中，選取 [ **(+)** 控制項] ( [ **新增**) ]，使用表格中下一列的值來建立記錄，然後再選取 [ **提交** ] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="1eb84-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="1eb84-216">重複此程式，直到您已建立全部五筆 CNAME 記錄為止。</span><span class="sxs-lookup"><span data-stu-id="1eb84-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1eb84-217">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="1eb84-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1eb84-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1eb84-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1eb84-219">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="1eb84-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1eb84-220">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="1eb84-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1eb84-221">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="1eb84-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1eb84-222">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="1eb84-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="1eb84-223">需要範例？</span><span class="sxs-lookup"><span data-stu-id="1eb84-223">Need examples?</span></span> <span data-ttu-id="1eb84-224">請參閱這些 [Microsoft 的外部網域名稱系統記錄](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)。</span><span class="sxs-lookup"><span data-stu-id="1eb84-224">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="1eb84-225">若要驗證您的 SPF 記錄，您可以使用其中一種[spf 驗證工具](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="1eb84-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="1eb84-226">首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="1eb84-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="1eb84-227">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1eb84-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="1eb84-228">在 [ **管理主控台** ] 頁面上的 [ **最近更新的網域** ] 區域中，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="1eb84-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="1eb84-229">在 [ **受管理的 DNS** ] 頁面上的 [ **TXT 記錄** ] 區域中，選取 [ **(+)** 控制項] ( [ **新增**) ]。</span><span class="sxs-lookup"><span data-stu-id="1eb84-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="1eb84-230">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="1eb84-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="1eb84-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1eb84-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="1eb84-233">**名稱**</span><span class="sxs-lookup"><span data-stu-id="1eb84-233">**Name**</span></span>|<span data-ttu-id="1eb84-234">**Value**</span><span class="sxs-lookup"><span data-stu-id="1eb84-234">**Value**</span></span>|<span data-ttu-id="1eb84-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1eb84-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1eb84-236">(將此欄位保留空白。)</span><span class="sxs-lookup"><span data-stu-id="1eb84-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1eb84-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1eb84-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1eb84-238">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="1eb84-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="1eb84-239">1800</span><span class="sxs-lookup"><span data-stu-id="1eb84-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="1eb84-241">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="1eb84-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1eb84-243">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="1eb84-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1eb84-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1eb84-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="1eb84-p113">首先請用[這個連結](https://cp.dnsmadeeasy.com/)移至 DNSMadeEasy 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="1eb84-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="1eb84-247">在 [ **管理主控台** ] 頁面上的 [ **最近更新的網域** ] 區域中，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="1eb84-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="1eb84-248">在 [ **受管理的 DNS** ] 頁面上，選取 [ **SRV 記錄** ] 區域中的 [ **(+)** ] 控制項 ( [ **新增**) ]。</span><span class="sxs-lookup"><span data-stu-id="1eb84-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="1eb84-249">(您可能需要向下捲動)</span><span class="sxs-lookup"><span data-stu-id="1eb84-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="1eb84-251">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="1eb84-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="1eb84-252">在 [ **ADD SRV** record] （新增 SRV 記錄）區域的新記錄方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="1eb84-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="1eb84-253">**名稱**</span><span class="sxs-lookup"><span data-stu-id="1eb84-253">**Name**</span></span>|<span data-ttu-id="1eb84-254">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="1eb84-254">**Priority**</span></span>|<span data-ttu-id="1eb84-255">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="1eb84-255">**Weight**</span></span>|<span data-ttu-id="1eb84-256">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="1eb84-256">**Port**</span></span>|<span data-ttu-id="1eb84-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="1eb84-257">**Host**</span></span>|<span data-ttu-id="1eb84-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1eb84-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1eb84-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="1eb84-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="1eb84-260">100</span><span class="sxs-lookup"><span data-stu-id="1eb84-260">100</span></span>  <br/> |<span data-ttu-id="1eb84-261">1 </span><span class="sxs-lookup"><span data-stu-id="1eb84-261">1</span></span>  <br/> |<span data-ttu-id="1eb84-262">443</span><span class="sxs-lookup"><span data-stu-id="1eb84-262">443</span></span>  <br/> |<span data-ttu-id="1eb84-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1eb84-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1eb84-264">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1eb84-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1eb84-265">1800</span><span class="sxs-lookup"><span data-stu-id="1eb84-265">1800</span></span>  <br/> |
    |<span data-ttu-id="1eb84-266">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="1eb84-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="1eb84-267">100</span><span class="sxs-lookup"><span data-stu-id="1eb84-267">100</span></span>  <br/> |<span data-ttu-id="1eb84-268">1 </span><span class="sxs-lookup"><span data-stu-id="1eb84-268">1</span></span>  <br/> |<span data-ttu-id="1eb84-269">5061</span><span class="sxs-lookup"><span data-stu-id="1eb84-269">5061</span></span>  <br/> |<span data-ttu-id="1eb84-270">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="1eb84-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="1eb84-271">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="1eb84-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="1eb84-272">1800</span><span class="sxs-lookup"><span data-stu-id="1eb84-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="1eb84-274">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="1eb84-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="1eb84-276">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1eb84-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="1eb84-277">在 [ **SRV 記錄** ] 區段中，選取 [ **(+)** 控制項] ( [ **新增**) ]，使用表格中下一列的值來建立記錄，然後再選取 [ **提交** ] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="1eb84-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1eb84-278">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1eb84-278">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1eb84-279">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="1eb84-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1eb84-280">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1eb84-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

