---
title: 在 Freenom 建立 Office 365 的 DNS 記錄
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
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Office 365 Freenom。
ms.openlocfilehash: d8c33df611a0ef1be95d32026f5d6b99808258f6
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211748"
---
# <a name="create-dns-records-at-freenom-for-office-365"></a><span data-ttu-id="66335-103">在 Freenom 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="66335-103">Create DNS records at Freenom for Office 365</span></span>

<span data-ttu-id="66335-104">如果您找不到所需的專案，[請檢查網域常見問題](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="66335-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="66335-105">Freenom 網站不支援 SRV 記錄，這表示有幾部商務用 Skype Online 和 Outlook Web App 功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="66335-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="66335-106">不論使用哪一種 Office 365 方案，都有重大的服務限制，您可能想要切換至不同的 DNS 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="66335-106">No matter which Office 365 plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="66335-107">不論服務限制，您可以選擇在 Freenom 管理您自己的 Office 365 DNS 記錄，請遵循本文中的步驟來驗證您的網域，並設定電子郵件和其他服務的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="66335-107">If despite the service limitations, you choose to manage your own Office 365 DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
<span data-ttu-id="66335-108">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="66335-108">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="66335-p102">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="66335-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="66335-112">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="66335-112">Add a TXT record for verification</span></span>
<span data-ttu-id="66335-113"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="66335-113"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="66335-p103">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="66335-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66335-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="66335-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="66335-118">若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="66335-118">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="66335-119">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="66335-119">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="66335-121">選取 [**服務**]，然後選取 [**我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="66335-121">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="66335-123">針對您要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="66335-123">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="66335-125">選取 [**管理 FREENOM DNS**]。</span><span class="sxs-lookup"><span data-stu-id="66335-125">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom 管理 Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="66335-127">在 [**新增記錄**] 底下的 [**類型**] 欄中，選擇功能表中的 [ **TXT** ]。</span><span class="sxs-lookup"><span data-stu-id="66335-127">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="66335-129">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="66335-129">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="66335-130">**名稱**</span><span class="sxs-lookup"><span data-stu-id="66335-130">**Name**</span></span>|<span data-ttu-id="66335-131">**Type**</span><span class="sxs-lookup"><span data-stu-id="66335-131">**Type**</span></span>|<span data-ttu-id="66335-132">**TTL**</span><span class="sxs-lookup"><span data-stu-id="66335-132">**TTL**</span></span>|<span data-ttu-id="66335-133">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="66335-133">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="66335-134">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="66335-134">(leave blank)</span></span>  <br/> |<span data-ttu-id="66335-135">TXT</span><span class="sxs-lookup"><span data-stu-id="66335-135">TXT</span></span>  <br/> |<span data-ttu-id="66335-136">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="66335-136">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="66335-137">MS=msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="66335-137">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="66335-138">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="66335-138">**Note:** This is an example.</span></span> <span data-ttu-id="66335-139">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="66335-139">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="66335-140">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="66335-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom 用於驗證的 TXT 值](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="66335-142">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="66335-142">Select **Save Changes**.</span></span>
    
    ![Freenom TXT 記錄儲存變更](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="66335-144">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="66335-144">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="66335-145">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="66335-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="66335-146">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="66335-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="66335-147">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="66335-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="66335-148">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="66335-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="66335-149">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="66335-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="66335-150">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="66335-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="66335-p107">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="66335-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="66335-154">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="66335-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="66335-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="66335-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="66335-156">若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="66335-156">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="66335-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="66335-157">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="66335-159">選取 [**服務**]，然後選取 [**我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="66335-159">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="66335-161">針對您要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="66335-161">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="66335-163">將您的網域的名稱設為預設的 Freenom 名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="66335-163">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="66335-164">選取 [**管理工具**]，然後選取 [**名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="66335-164">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom 名稱伺服器設定](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="66335-166">請確認已選取 [**使用預設名稱伺服器**]，然後選取 [**變更名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="66335-166">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom 變更名稱伺服器](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="66335-168">選取 [**管理 FREENOM DNS**]。</span><span class="sxs-lookup"><span data-stu-id="66335-168">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="66335-170">在 [**新增記錄**] 底下的 [**類型**] 欄中，從功能表選擇 [ **MX** ]。</span><span class="sxs-lookup"><span data-stu-id="66335-170">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom 新增記錄類型 MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="66335-172">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="66335-172">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="66335-173">**名稱**</span><span class="sxs-lookup"><span data-stu-id="66335-173">**Name**</span></span>|<span data-ttu-id="66335-174">**Type**</span><span class="sxs-lookup"><span data-stu-id="66335-174">**Type**</span></span>|<span data-ttu-id="66335-175">**TTL**</span><span class="sxs-lookup"><span data-stu-id="66335-175">**TTL**</span></span>|<span data-ttu-id="66335-176">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="66335-176">**Target**</span></span>|<span data-ttu-id="66335-177">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="66335-177">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="66335-178">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="66335-178">(leave blank)</span></span>  <br/> |<span data-ttu-id="66335-179">MX (郵件交換程式)</span><span class="sxs-lookup"><span data-stu-id="66335-179">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="66335-180">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="66335-180">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="66335-181">\<網域金鑰\>。 mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="66335-181">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="66335-182">**附注：** 從您的 Office 365 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="66335-182">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="66335-183">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="66335-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="66335-184">10 </span><span class="sxs-lookup"><span data-stu-id="66335-184">10</span></span>  <br/> <span data-ttu-id="66335-185">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span><span class="sxs-lookup"><span data-stu-id="66335-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Freenom MX 記錄](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="66335-187">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="66335-187">Select **Save Changes**.</span></span>
    
    ![Freenom MX 記錄儲存變更](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="66335-189">如果有任何其他 MX 記錄，請全部刪除。</span><span class="sxs-lookup"><span data-stu-id="66335-189">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="66335-190">針對每筆記錄，選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="66335-190">For each record, select **Delete**.</span></span> <span data-ttu-id="66335-191">當郵件**確實要移除此專案時？** 隨即出現，請選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="66335-191">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="66335-192">新增 Office 365 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="66335-192">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="66335-193"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="66335-193"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="66335-194">若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="66335-194">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="66335-195">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="66335-195">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="66335-197">選取 [**服務**]，然後選取 [**我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="66335-197">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="66335-199">針對您要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="66335-199">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="66335-201">選取 [**管理 FREENOM DNS**]。</span><span class="sxs-lookup"><span data-stu-id="66335-201">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="66335-203">在 [**新增記錄**] 底下的 [**類型**] 欄中，從功能表選擇 [ **CNAME** ]。</span><span class="sxs-lookup"><span data-stu-id="66335-203">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom 新增記錄類型 CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="66335-205">建立第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="66335-205">Create the first CNAME record.</span></span> <span data-ttu-id="66335-206">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="66335-206">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="66335-207">**名稱**</span><span class="sxs-lookup"><span data-stu-id="66335-207">**Name**</span></span>|<span data-ttu-id="66335-208">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="66335-208">**Record type**</span></span>|<span data-ttu-id="66335-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="66335-209">**TTL**</span></span>|<span data-ttu-id="66335-210">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="66335-210">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="66335-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="66335-211">autodiscover</span></span>  <br/> |<span data-ttu-id="66335-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="66335-212">CNAME</span></span>  <br/> |<span data-ttu-id="66335-213">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="66335-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="66335-214">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="66335-214">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="66335-215">sip</span><span class="sxs-lookup"><span data-stu-id="66335-215">sip</span></span>  <br/> |<span data-ttu-id="66335-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="66335-216">CNAME</span></span>  <br/> |<span data-ttu-id="66335-217">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="66335-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="66335-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="66335-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="66335-219">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="66335-219">lyncdiscover</span></span>  <br/> |<span data-ttu-id="66335-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="66335-220">CNAME</span></span>  <br/> |<span data-ttu-id="66335-221">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="66335-221">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="66335-222">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="66335-222">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="66335-223">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="66335-223">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="66335-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="66335-224">CNAME</span></span>  <br/> |<span data-ttu-id="66335-225">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="66335-225">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="66335-226">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="66335-226">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="66335-227">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="66335-227">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="66335-228">CNAME</span><span class="sxs-lookup"><span data-stu-id="66335-228">CNAME</span></span>  <br/> |<span data-ttu-id="66335-229">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="66335-229">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="66335-230">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="66335-230">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME 值](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="66335-232">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="66335-232">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME 儲存變更](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="66335-234">重複上述步驟，以建立其他五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="66335-234">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="66335-235">針對每個記錄，輸入或複製並貼上表格中下一列的值，然後將其貼到該記錄的方塊中。</span><span class="sxs-lookup"><span data-stu-id="66335-235">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="66335-236">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="66335-236">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="66335-237"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="66335-237"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="66335-238">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="66335-238">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="66335-239">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="66335-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="66335-240">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="66335-240">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="66335-241">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="66335-241">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="66335-242">若要開始使用，請使用[此連結](https://my.freenom.com/)移至 Freenom 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="66335-242">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="66335-243">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="66335-243">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="66335-245">選取 [**服務**]，然後選取 [**我的網域**]。</span><span class="sxs-lookup"><span data-stu-id="66335-245">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="66335-247">針對您要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="66335-247">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取管理網域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="66335-249">選取 [**管理 FREENOM DNS**]。</span><span class="sxs-lookup"><span data-stu-id="66335-249">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="66335-251">在 [**新增記錄**] 底下的 [**類型**] 欄中，選擇功能表中的 [ **TXT** ]。</span><span class="sxs-lookup"><span data-stu-id="66335-251">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="66335-253">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="66335-253">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="66335-254">**名稱**</span><span class="sxs-lookup"><span data-stu-id="66335-254">**Name**</span></span>|<span data-ttu-id="66335-255">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="66335-255">**Record type**</span></span>|<span data-ttu-id="66335-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="66335-256">**TTL**</span></span>|<span data-ttu-id="66335-257">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="66335-257">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="66335-258">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="66335-258">(leave blank)</span></span>  <br/> |<span data-ttu-id="66335-259">TXT</span><span class="sxs-lookup"><span data-stu-id="66335-259">TXT</span></span>  <br/> |<span data-ttu-id="66335-260">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="66335-260">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="66335-261">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="66335-261">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="66335-262">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="66335-262">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom SPF 的 TXT 值](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="66335-264">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="66335-264">Select **Save Changes**.</span></span>
    
    ![Freenom SPF 儲存變更的 TXT 記錄](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

