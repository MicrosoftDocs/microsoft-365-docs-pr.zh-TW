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
ms.openlocfilehash: 828a1728606338017383857e4b59d6a62d087fc7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629560"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="0493f-103">在 Freenom 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="0493f-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="0493f-104">如果您找不到所需的專案，[請檢查網域常見問題](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="0493f-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="0493f-105">Freenom 網站不支援 SRV 記錄，這表示有幾部商務用 Skype Online 和 Outlook Web App 功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="0493f-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="0493f-106">不論使用哪一種 Microsoft 方案，都有重大的服務限制，您可能想要切換至不同的 DNS 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="0493f-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="0493f-107">不論服務限制，您可以選擇在 Freenom 管理您自己的 Microsoft DNS 記錄，請遵循本文中的步驟來驗證您的網域，並設定電子郵件和其他服務的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="0493f-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
<span data-ttu-id="0493f-108">若要深入瞭解 Microsoft 的網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0493f-108">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0493f-p102">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="0493f-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0493f-112">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="0493f-112">Add a TXT record for verification</span></span>
<span data-ttu-id="0493f-113"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="0493f-113"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="0493f-114">在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="0493f-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="0493f-115">您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。</span><span class="sxs-lookup"><span data-stu-id="0493f-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0493f-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="0493f-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0493f-118">若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="0493f-118">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="0493f-119">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0493f-119">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="0493f-121">選取 [**服務**]，然後選取 [**我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-121">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="0493f-123">針對您要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-123">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="0493f-125">選取 [**管理 FREENOM DNS**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-125">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom 管理 Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="0493f-127">在 [**新增記錄**] 底下的 [**類型**] 欄中，選擇功能表中的 [ **TXT** ]。</span><span class="sxs-lookup"><span data-stu-id="0493f-127">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="0493f-129">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="0493f-129">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="0493f-130">**名稱**</span><span class="sxs-lookup"><span data-stu-id="0493f-130">**Name**</span></span>|<span data-ttu-id="0493f-131">**Type**</span><span class="sxs-lookup"><span data-stu-id="0493f-131">**Type**</span></span>|<span data-ttu-id="0493f-132">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0493f-132">**TTL**</span></span>|<span data-ttu-id="0493f-133">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="0493f-133">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0493f-134">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="0493f-134">(leave blank)</span></span>  <br/> |<span data-ttu-id="0493f-135">TXT</span><span class="sxs-lookup"><span data-stu-id="0493f-135">TXT</span></span>  <br/> |<span data-ttu-id="0493f-136">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="0493f-136">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0493f-137">MS=msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="0493f-137">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="0493f-138">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="0493f-138">**Note:** This is an example.</span></span> <span data-ttu-id="0493f-139">從表格中，使用您的特定**目的地或指向位址**值。</span><span class="sxs-lookup"><span data-stu-id="0493f-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="0493f-140">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="0493f-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom 用於驗證的 TXT 值](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="0493f-142">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-142">Select **Save Changes**.</span></span>
    
    ![Freenom TXT 記錄儲存變更](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="0493f-144">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="0493f-144">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0493f-145">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求記錄。</span><span class="sxs-lookup"><span data-stu-id="0493f-145">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="0493f-146">當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="0493f-146">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0493f-147">在 Microsoft 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0493f-147">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0493f-148">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="0493f-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="0493f-149">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="0493f-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="0493f-150">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="0493f-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="0493f-p107">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="0493f-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0493f-154">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="0493f-154">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0493f-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="0493f-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="0493f-156">若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="0493f-156">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="0493f-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0493f-157">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="0493f-159">選取 [**服務**]，然後選取 [**我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-159">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="0493f-161">針對您要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-161">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="0493f-163">將您的網域的名稱設為預設的 Freenom 名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="0493f-163">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="0493f-164">選取 [**管理工具**]，然後選取 [**名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-164">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom 名稱伺服器設定](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="0493f-166">請確認已選取 [**使用預設名稱伺服器**]，然後選取 [**變更名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-166">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom 變更名稱伺服器](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="0493f-168">選取 [**管理 FREENOM DNS**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-168">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="0493f-170">在 [**新增記錄**] 底下的 [**類型**] 欄中，從功能表選擇 [ **MX** ]。</span><span class="sxs-lookup"><span data-stu-id="0493f-170">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom 新增記錄類型 MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="0493f-172">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="0493f-172">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="0493f-173">**名稱**</span><span class="sxs-lookup"><span data-stu-id="0493f-173">**Name**</span></span>|<span data-ttu-id="0493f-174">**Type**</span><span class="sxs-lookup"><span data-stu-id="0493f-174">**Type**</span></span>|<span data-ttu-id="0493f-175">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0493f-175">**TTL**</span></span>|<span data-ttu-id="0493f-176">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="0493f-176">**Target**</span></span>|<span data-ttu-id="0493f-177">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="0493f-177">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0493f-178">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="0493f-178">(leave blank)</span></span>  <br/> |<span data-ttu-id="0493f-179">MX (郵件交換程式)</span><span class="sxs-lookup"><span data-stu-id="0493f-179">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="0493f-180">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="0493f-180">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0493f-181">\<網域金鑰\>。 mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0493f-181">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="0493f-182">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="0493f-182">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="0493f-183">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="0493f-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0493f-184">10 </span><span class="sxs-lookup"><span data-stu-id="0493f-184">10</span></span>  <br/> <span data-ttu-id="0493f-185">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span><span class="sxs-lookup"><span data-stu-id="0493f-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Freenom MX 記錄](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="0493f-187">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-187">Select **Save Changes**.</span></span>
    
    ![Freenom MX 記錄儲存變更](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="0493f-189">如果有任何其他 MX 記錄，請全部刪除。</span><span class="sxs-lookup"><span data-stu-id="0493f-189">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="0493f-190">針對每筆記錄，選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-190">For each record, select **Delete**.</span></span> <span data-ttu-id="0493f-191">當郵件**確實要移除此專案時？** 隨即出現，請選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0493f-191">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0493f-192">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="0493f-192">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0493f-193"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="0493f-193"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="0493f-194">若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="0493f-194">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="0493f-195">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0493f-195">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="0493f-197">選取 [**服務**]，然後選取 [**我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-197">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="0493f-199">針對您要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-199">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="0493f-201">選取 [**管理 FREENOM DNS**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-201">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="0493f-203">在 [**新增記錄**] 底下的 [**類型**] 欄中，從功能表選擇 [ **CNAME** ]。</span><span class="sxs-lookup"><span data-stu-id="0493f-203">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom 新增記錄類型 CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="0493f-205">建立第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="0493f-205">Create the first CNAME record.</span></span> <span data-ttu-id="0493f-206">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="0493f-206">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="0493f-207">**Name** (名稱)</span><span class="sxs-lookup"><span data-stu-id="0493f-207">**Name**</span></span>|<span data-ttu-id="0493f-208">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="0493f-208">**Record type**</span></span>|<span data-ttu-id="0493f-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0493f-209">**TTL**</span></span>|<span data-ttu-id="0493f-210">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="0493f-210">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0493f-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0493f-211">autodiscover</span></span>  <br/> |<span data-ttu-id="0493f-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="0493f-212">CNAME</span></span>  <br/> |<span data-ttu-id="0493f-213">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="0493f-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0493f-214">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0493f-214">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="0493f-215">sip</span><span class="sxs-lookup"><span data-stu-id="0493f-215">sip</span></span>  <br/> |<span data-ttu-id="0493f-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="0493f-216">CNAME</span></span>  <br/> |<span data-ttu-id="0493f-217">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="0493f-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0493f-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0493f-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0493f-219">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0493f-219">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0493f-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="0493f-220">CNAME</span></span>  <br/> |<span data-ttu-id="0493f-221">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="0493f-221">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0493f-222">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0493f-222">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0493f-223">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0493f-223">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0493f-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="0493f-224">CNAME</span></span>  <br/> |<span data-ttu-id="0493f-225">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="0493f-225">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0493f-226">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="0493f-226">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="0493f-227">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0493f-227">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0493f-228">CNAME</span><span class="sxs-lookup"><span data-stu-id="0493f-228">CNAME</span></span>  <br/> |<span data-ttu-id="0493f-229">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="0493f-229">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0493f-230">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0493f-230">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME 值](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="0493f-232">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-232">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME 儲存變更](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="0493f-234">重複上述步驟，以建立其他五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="0493f-234">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="0493f-235">針對每個記錄，輸入或複製並貼上表格中下一列的值，然後將其貼到該記錄的方塊中。</span><span class="sxs-lookup"><span data-stu-id="0493f-235">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0493f-236">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="0493f-236">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0493f-237"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="0493f-237"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0493f-238">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="0493f-238">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0493f-239">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="0493f-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0493f-240">如果您已有網域的 SPF 記錄，請不要為 Microsoft 建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="0493f-240">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0493f-241">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="0493f-241">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="0493f-242">若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="0493f-242">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="0493f-243">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="0493f-243">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="0493f-245">選取 [**服務**]，然後選取 [**我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-245">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="0493f-247">針對您要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-247">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="0493f-249">選取 [**管理 FREENOM DNS**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-249">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="0493f-251">在 [**新增記錄**] 底下的 [**類型**] 欄中，選擇功能表中的 [ **TXT** ]。</span><span class="sxs-lookup"><span data-stu-id="0493f-251">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="0493f-253">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="0493f-253">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="0493f-254">**Name** (名稱)</span><span class="sxs-lookup"><span data-stu-id="0493f-254">**Name**</span></span>|<span data-ttu-id="0493f-255">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="0493f-255">**Record type**</span></span>|<span data-ttu-id="0493f-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0493f-256">**TTL**</span></span>|<span data-ttu-id="0493f-257">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="0493f-257">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0493f-258">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="0493f-258">(leave blank)</span></span>  <br/> |<span data-ttu-id="0493f-259">TXT</span><span class="sxs-lookup"><span data-stu-id="0493f-259">TXT</span></span>  <br/> |<span data-ttu-id="0493f-260">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="0493f-260">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0493f-261">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0493f-261">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="0493f-262">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="0493f-262">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom SPF 的 TXT 值](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="0493f-264">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="0493f-264">Select **Save Changes**.</span></span>
    
    ![Freenom SPF 儲存變更的 TXT 記錄](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

