---
title: 在 Freenom 建立 Microsoft 的 DNS 記錄
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Freenom。
ms.openlocfilehash: a7ad45d3d785478966df5120567836200de316da
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939224"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="04e76-103">在 Freenom 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="04e76-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="04e76-104">如果您找不到所需的專案，[請檢查網域常見問題](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="04e76-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="04e76-105">Freenom 網站不支援 SRV 記錄，這表示有幾部商務用 Skype Online 和 Outlook Web App 功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="04e76-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="04e76-106">不論使用哪一種 Microsoft 方案，都有重大的服務限制，您可能想要切換至不同的 DNS 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="04e76-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="04e76-107">不論服務限制，您可以選擇在 Freenom 管理您自己的 Microsoft DNS 記錄，請遵循本文中的步驟來驗證您的網域，並設定電子郵件和其他服務的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="04e76-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="04e76-p102">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="04e76-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="04e76-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="04e76-111">Add a TXT record for verification</span></span>
<span data-ttu-id="04e76-112"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="04e76-112"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="04e76-p103">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="04e76-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="04e76-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="04e76-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="04e76-117">若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="04e76-117">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="04e76-118">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="04e76-118">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="04e76-120">選取 [**服務**]，然後選取 [**我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-120">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="04e76-122">針對您要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-122">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="04e76-124">選取 [**管理 FREENOM DNS**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-124">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom 管理 Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="04e76-126">在 [**新增記錄**] 底下的 [**類型**] 欄中，選擇功能表中的 [ **TXT** ]。</span><span class="sxs-lookup"><span data-stu-id="04e76-126">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="04e76-128">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="04e76-128">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="04e76-129">**Name**</span><span class="sxs-lookup"><span data-stu-id="04e76-129">**Name**</span></span>|<span data-ttu-id="04e76-130">**Type**</span><span class="sxs-lookup"><span data-stu-id="04e76-130">**Type**</span></span>|<span data-ttu-id="04e76-131">**TTL**</span><span class="sxs-lookup"><span data-stu-id="04e76-131">**TTL**</span></span>|<span data-ttu-id="04e76-132">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="04e76-132">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="04e76-133">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="04e76-133">(leave blank)</span></span>  <br/> |<span data-ttu-id="04e76-134">TXT</span><span class="sxs-lookup"><span data-stu-id="04e76-134">TXT</span></span>  <br/> |<span data-ttu-id="04e76-135">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="04e76-135">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="04e76-136">MS=msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="04e76-136">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="04e76-137">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="04e76-137">**Note:** This is an example.</span></span> <span data-ttu-id="04e76-138">在這裡請使用您自己來自表格的 [目的地或指向位址]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="04e76-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="04e76-139">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="04e76-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom 用於驗證的 TXT 值](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="04e76-141">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-141">Select **Save Changes**.</span></span>
    
    ![Freenom TXT 記錄儲存變更](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="04e76-143">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="04e76-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="04e76-144">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="04e76-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="04e76-145">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="04e76-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="04e76-146">在 Microsoft 系統管理中心中，移至 [設定]\*\*\*\* \> [網域]<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="04e76-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="04e76-147">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="04e76-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="04e76-148">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="04e76-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="04e76-149">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="04e76-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="04e76-p107">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="04e76-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="04e76-153">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="04e76-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="04e76-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="04e76-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="04e76-155">若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="04e76-155">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="04e76-156">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="04e76-156">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="04e76-158">選取 [**服務**]，然後選取 [**我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-158">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="04e76-160">針對您要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-160">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="04e76-162">將您的網域的名稱設為預設的 Freenom 名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="04e76-162">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="04e76-163">選取 [**管理工具**]，然後選取 [**名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-163">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom 名稱伺服器設定](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="04e76-165">請確認已選取 [**使用預設名稱伺服器**]，然後選取 [**變更名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-165">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom 變更名稱伺服器](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="04e76-167">選取 [**管理 FREENOM DNS**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-167">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="04e76-169">在 [**新增記錄**] 底下的 [**類型**] 欄中，從功能表選擇 [ **MX** ]。</span><span class="sxs-lookup"><span data-stu-id="04e76-169">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom 新增記錄類型 MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="04e76-171">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="04e76-171">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="04e76-172">**Name**</span><span class="sxs-lookup"><span data-stu-id="04e76-172">**Name**</span></span>|<span data-ttu-id="04e76-173">**Type**</span><span class="sxs-lookup"><span data-stu-id="04e76-173">**Type**</span></span>|<span data-ttu-id="04e76-174">**TTL**</span><span class="sxs-lookup"><span data-stu-id="04e76-174">**TTL**</span></span>|<span data-ttu-id="04e76-175">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="04e76-175">**Target**</span></span>|<span data-ttu-id="04e76-176">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="04e76-176">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="04e76-177">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="04e76-177">(leave blank)</span></span>  <br/> |<span data-ttu-id="04e76-178">MX (郵件交換程式)</span><span class="sxs-lookup"><span data-stu-id="04e76-178">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="04e76-179">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="04e76-179">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="04e76-180">\<網域金鑰\>。 mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="04e76-180">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="04e76-181">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="04e76-181">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="04e76-182">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="04e76-182">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="04e76-183">10 </span><span class="sxs-lookup"><span data-stu-id="04e76-183">10</span></span>  <br/> <span data-ttu-id="04e76-184">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span><span class="sxs-lookup"><span data-stu-id="04e76-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Freenom MX 記錄](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="04e76-186">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-186">Select **Save Changes**.</span></span>
    
    ![Freenom MX 記錄儲存變更](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="04e76-188">如果有任何其他 MX 記錄，請全部刪除。</span><span class="sxs-lookup"><span data-stu-id="04e76-188">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="04e76-189">針對每筆記錄，選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-189">For each record, select **Delete**.</span></span> <span data-ttu-id="04e76-190">當郵件**確實要移除此專案時？** 隨即出現，請選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="04e76-190">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="04e76-191">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="04e76-191">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="04e76-192"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="04e76-192"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="04e76-193">若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="04e76-193">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="04e76-194">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="04e76-194">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="04e76-196">選取 [**服務**]，然後選取 [**我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-196">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="04e76-198">針對您要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-198">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="04e76-200">選取 [**管理 FREENOM DNS**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-200">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="04e76-202">在 [**新增記錄**] 底下的 [**類型**] 欄中，從功能表選擇 [ **CNAME** ]。</span><span class="sxs-lookup"><span data-stu-id="04e76-202">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom 新增記錄類型 CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="04e76-204">建立第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="04e76-204">Create the first CNAME record.</span></span> <span data-ttu-id="04e76-205">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="04e76-205">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="04e76-206">**Name**</span><span class="sxs-lookup"><span data-stu-id="04e76-206">**Name**</span></span>|<span data-ttu-id="04e76-207">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="04e76-207">**Record type**</span></span>|<span data-ttu-id="04e76-208">**TTL**</span><span class="sxs-lookup"><span data-stu-id="04e76-208">**TTL**</span></span>|<span data-ttu-id="04e76-209">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="04e76-209">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="04e76-210">autodiscover</span><span class="sxs-lookup"><span data-stu-id="04e76-210">autodiscover</span></span>  <br/> |<span data-ttu-id="04e76-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="04e76-211">CNAME</span></span>  <br/> |<span data-ttu-id="04e76-212">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="04e76-212">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="04e76-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="04e76-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="04e76-214">sip</span><span class="sxs-lookup"><span data-stu-id="04e76-214">sip</span></span>  <br/> |<span data-ttu-id="04e76-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="04e76-215">CNAME</span></span>  <br/> |<span data-ttu-id="04e76-216">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="04e76-216">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="04e76-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="04e76-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="04e76-218">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="04e76-218">lyncdiscover</span></span>  <br/> |<span data-ttu-id="04e76-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="04e76-219">CNAME</span></span>  <br/> |<span data-ttu-id="04e76-220">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="04e76-220">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="04e76-221">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="04e76-221">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="04e76-222">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="04e76-222">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="04e76-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="04e76-223">CNAME</span></span>  <br/> |<span data-ttu-id="04e76-224">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="04e76-224">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="04e76-225">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="04e76-225">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="04e76-226">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="04e76-226">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="04e76-227">CNAME</span><span class="sxs-lookup"><span data-stu-id="04e76-227">CNAME</span></span>  <br/> |<span data-ttu-id="04e76-228">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="04e76-228">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="04e76-229">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="04e76-229">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME 值](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="04e76-231">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-231">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME 儲存變更](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="04e76-233">重複上述步驟，以建立其他五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="04e76-233">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="04e76-234">針對每個記錄，輸入或複製並貼上表格中下一列的值，然後將其貼到該記錄的方塊中。</span><span class="sxs-lookup"><span data-stu-id="04e76-234">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="04e76-235">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="04e76-235">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="04e76-236"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="04e76-236"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="04e76-237">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="04e76-237">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="04e76-238">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="04e76-238">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="04e76-239">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="04e76-239">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="04e76-240">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="04e76-240">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="04e76-241">若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="04e76-241">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="04e76-242">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="04e76-242">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="04e76-244">選取 [**服務**]，然後選取 [**我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-244">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="04e76-246">針對您要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-246">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="04e76-248">選取 [**管理 FREENOM DNS**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-248">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="04e76-250">在 [**新增記錄**] 底下的 [**類型**] 欄中，選擇功能表中的 [ **TXT** ]。</span><span class="sxs-lookup"><span data-stu-id="04e76-250">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="04e76-252">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="04e76-252">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="04e76-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="04e76-253">**Name**</span></span>|<span data-ttu-id="04e76-254">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="04e76-254">**Record type**</span></span>|<span data-ttu-id="04e76-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="04e76-255">**TTL**</span></span>|<span data-ttu-id="04e76-256">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="04e76-256">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="04e76-257">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="04e76-257">(leave blank)</span></span>  <br/> |<span data-ttu-id="04e76-258">TXT</span><span class="sxs-lookup"><span data-stu-id="04e76-258">TXT</span></span>  <br/> |<span data-ttu-id="04e76-259">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="04e76-259">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="04e76-260">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="04e76-260">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="04e76-261">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="04e76-261">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom SPF 的 TXT 值](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="04e76-263">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="04e76-263">Select **Save Changes**.</span></span>
    
    ![Freenom SPF 儲存變更的 TXT 記錄](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

