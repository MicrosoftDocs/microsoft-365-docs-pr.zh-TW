---
title: 在 Freenom 建立 Office 365 的 DNS 記錄
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: 了解如何驗證您的網域和設定 Office 365 的電子郵件、 Skype for Business Online，並在 Freenom 其他服務的 DNS 記錄。
ms.openlocfilehash: a1396964c7dc9c279589a6020e0c741fd0cb29d5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240795"
---
# <a name="create-dns-records-at-freenom-for-office-365"></a><span data-ttu-id="92cf2-103">在 Freenom 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="92cf2-103">Create DNS records at Freenom for Office 365</span></span>

<span data-ttu-id="92cf2-104">[檢查網域常見問題集](../setup/domains-faq.md)找不到您要尋找。</span><span class="sxs-lookup"><span data-stu-id="92cf2-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="92cf2-105">在 Freenom 網站不支援 SRV 記錄，這表示幾個 Skype for Business Online 和 Outlook Web App 功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="92cf2-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="92cf2-106">不論您使用哪一個 Office 365 方案，有重大服務限制，以及您可能想要切換至不同的 DNS 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="92cf2-106">No matter which Office 365 plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="92cf2-107">儘管服務的限制，如果您選擇 [管理 Office 365 DNS 記錄，在 Freenom，請遵循本文以驗證您的網域及設定電子郵件和其他服務的 DNS 記錄中的步驟。</span><span class="sxs-lookup"><span data-stu-id="92cf2-107">If despite the service limitations, you choose to manage your own Office 365 DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
<span data-ttu-id="92cf2-108">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="92cf2-108">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="92cf2-p102">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="92cf2-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="92cf2-112">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="92cf2-112">Add a TXT record for verification</span></span>
<span data-ttu-id="92cf2-113"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="92cf2-113"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="92cf2-p103">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="92cf2-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="92cf2-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="92cf2-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="92cf2-118">若要開始，使用[此連結](https://my.freenom.com/)移至您在 Freenom 中的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="92cf2-118">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="92cf2-119">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="92cf2-119">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="92cf2-121">選取 [**服務**]，然後選取 [**我的網域**。</span><span class="sxs-lookup"><span data-stu-id="92cf2-121">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="92cf2-123">針對您想要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="92cf2-123">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取 [管理網域](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="92cf2-125">選取 [**管理 Freenom DNS**]。</span><span class="sxs-lookup"><span data-stu-id="92cf2-125">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom 管理 Freenom DNS](../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="92cf2-127">[**新增記錄**，在 [**類型**] 欄中， **TXT**從功能表中選擇。</span><span class="sxs-lookup"><span data-stu-id="92cf2-127">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom 新增記錄類型 TXT](../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="92cf2-129">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="92cf2-129">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="92cf2-130">**Name**</span><span class="sxs-lookup"><span data-stu-id="92cf2-130">**Name**</span></span>|<span data-ttu-id="92cf2-131">**Type**</span><span class="sxs-lookup"><span data-stu-id="92cf2-131">**Type**</span></span>|<span data-ttu-id="92cf2-132">**TTL**</span><span class="sxs-lookup"><span data-stu-id="92cf2-132">**TTL**</span></span>|<span data-ttu-id="92cf2-133">**Target**</span><span class="sxs-lookup"><span data-stu-id="92cf2-133">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="92cf2-134">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="92cf2-134">(leave blank)</span></span>  <br/> |<span data-ttu-id="92cf2-135">TXT</span><span class="sxs-lookup"><span data-stu-id="92cf2-135">TXT</span></span>  <br/> |<span data-ttu-id="92cf2-136">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="92cf2-136">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="92cf2-137">MS = msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="92cf2-137">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="92cf2-138">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="92cf2-138">**Note:** This is an example.</span></span> <span data-ttu-id="92cf2-139">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span><span class="sxs-lookup"><span data-stu-id="92cf2-139">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="92cf2-140">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="92cf2-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT 值，以供驗證](../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="92cf2-142">選取 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="92cf2-142">Select **Save Changes**.</span></span>
    
    ![Freenom TXT 記錄儲存的變更](../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="92cf2-144">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="92cf2-144">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="92cf2-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="92cf2-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="92cf2-146">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="92cf2-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="92cf2-147">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="92cf2-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="92cf2-148">在 [**網域**] 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="92cf2-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="92cf2-149">在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="92cf2-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="92cf2-150">在 [**驗證網域**] 頁面上，選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="92cf2-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="92cf2-p107">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="92cf2-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="92cf2-154">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="92cf2-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="92cf2-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="92cf2-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="92cf2-156">若要開始，使用[此連結](https://my.freenom.com/)移至您在 Freenom 中的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="92cf2-156">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="92cf2-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="92cf2-157">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="92cf2-159">選取 [**服務**]，然後選取 [**我的網域**。</span><span class="sxs-lookup"><span data-stu-id="92cf2-159">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="92cf2-161">針對您想要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="92cf2-161">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取 [管理網域](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="92cf2-163">設定您的網域名稱做為預設 Freenom 名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="92cf2-163">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="92cf2-164">選取 [**管理工具**]，然後選取 [**名稱伺服器**。</span><span class="sxs-lookup"><span data-stu-id="92cf2-164">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom 名稱伺服器設定](../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="92cf2-166">請確定已選取 [**使用預設名稱伺服器**，，然後選取 [**變更名稱伺服器**。</span><span class="sxs-lookup"><span data-stu-id="92cf2-166">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom 變更名稱伺服器](../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="92cf2-168">選取 [**管理 Freenom DNS**]。</span><span class="sxs-lookup"><span data-stu-id="92cf2-168">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom 選取管理 Freenom DNS](../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="92cf2-170">[**新增記錄**，在 [**類型**] 欄中， **MX**從功能表中選擇。</span><span class="sxs-lookup"><span data-stu-id="92cf2-170">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom 新增記錄類型 MX](../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="92cf2-172">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="92cf2-172">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="92cf2-173">**Name**</span><span class="sxs-lookup"><span data-stu-id="92cf2-173">**Name**</span></span>|<span data-ttu-id="92cf2-174">**Type**</span><span class="sxs-lookup"><span data-stu-id="92cf2-174">**Type**</span></span>|<span data-ttu-id="92cf2-175">**TTL**</span><span class="sxs-lookup"><span data-stu-id="92cf2-175">**TTL**</span></span>|<span data-ttu-id="92cf2-176">**Target**</span><span class="sxs-lookup"><span data-stu-id="92cf2-176">**Target**</span></span>|<span data-ttu-id="92cf2-177">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="92cf2-177">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="92cf2-178">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="92cf2-178">(leave blank)</span></span>  <br/> |<span data-ttu-id="92cf2-179">MX (郵件交換程式)</span><span class="sxs-lookup"><span data-stu-id="92cf2-179">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="92cf2-180">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="92cf2-180">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="92cf2-181">\<網域金鑰\>。 mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="92cf2-181">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="92cf2-182">**附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="92cf2-182">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="92cf2-183">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="92cf2-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="92cf2-184">10 </span><span class="sxs-lookup"><span data-stu-id="92cf2-184">10</span></span>  <br/> <span data-ttu-id="92cf2-185">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span><span class="sxs-lookup"><span data-stu-id="92cf2-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Freenom MX 記錄](../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="92cf2-187">選取 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="92cf2-187">Select **Save Changes**.</span></span>
    
    ![Freenom MX 記錄儲存的變更](../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="92cf2-189">如果有任何其他 MX 記錄，請將它們全數刪除。</span><span class="sxs-lookup"><span data-stu-id="92cf2-189">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="92cf2-190">每一筆記錄中，選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="92cf2-190">For each record, select **Delete**.</span></span> <span data-ttu-id="92cf2-191">當郵件**您真的要移除此項目？** 出現，請選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="92cf2-191">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="92cf2-192">新增 Office 365 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="92cf2-192">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="92cf2-193"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="92cf2-193"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="92cf2-194">若要開始，使用[此連結](https://my.freenom.com/)移至您在 Freenom 中的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="92cf2-194">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="92cf2-195">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="92cf2-195">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="92cf2-197">選取 [**服務**]，然後選取 [**我的網域**。</span><span class="sxs-lookup"><span data-stu-id="92cf2-197">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="92cf2-199">針對您想要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="92cf2-199">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取 [管理網域](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="92cf2-201">選取 [**管理 Freenom DNS**]。</span><span class="sxs-lookup"><span data-stu-id="92cf2-201">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom 選取管理 Freenom DNS](../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="92cf2-203">[**新增記錄**，在 [**類型**] 欄中， **CNAME**從功能表中選擇。</span><span class="sxs-lookup"><span data-stu-id="92cf2-203">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom 新增記錄類型 CNAME](../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="92cf2-205">建立第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="92cf2-205">Create the first CNAME record.</span></span> <span data-ttu-id="92cf2-206">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="92cf2-206">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="92cf2-207">**Name**</span><span class="sxs-lookup"><span data-stu-id="92cf2-207">**Name**</span></span>|<span data-ttu-id="92cf2-208">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="92cf2-208">**Record type**</span></span>|<span data-ttu-id="92cf2-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="92cf2-209">**TTL**</span></span>|<span data-ttu-id="92cf2-210">**Target**</span><span class="sxs-lookup"><span data-stu-id="92cf2-210">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="92cf2-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="92cf2-211">autodiscover</span></span>  <br/> |<span data-ttu-id="92cf2-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="92cf2-212">CNAME</span></span>  <br/> |<span data-ttu-id="92cf2-213">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="92cf2-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="92cf2-214">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="92cf2-214">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="92cf2-215">sip</span><span class="sxs-lookup"><span data-stu-id="92cf2-215">sip</span></span>  <br/> |<span data-ttu-id="92cf2-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="92cf2-216">CNAME</span></span>  <br/> |<span data-ttu-id="92cf2-217">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="92cf2-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="92cf2-218">sipdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="92cf2-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="92cf2-219">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="92cf2-219">lyncdiscover</span></span>  <br/> |<span data-ttu-id="92cf2-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="92cf2-220">CNAME</span></span>  <br/> |<span data-ttu-id="92cf2-221">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="92cf2-221">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="92cf2-222">webdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="92cf2-222">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="92cf2-223">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="92cf2-223">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="92cf2-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="92cf2-224">CNAME</span></span>  <br/> |<span data-ttu-id="92cf2-225">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="92cf2-225">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="92cf2-226">enterpriseregistration.windows.net></span><span class="sxs-lookup"><span data-stu-id="92cf2-226">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="92cf2-227">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="92cf2-227">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="92cf2-228">CNAME</span><span class="sxs-lookup"><span data-stu-id="92cf2-228">CNAME</span></span>  <br/> |<span data-ttu-id="92cf2-229">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="92cf2-229">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="92cf2-230">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="92cf2-230">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME 值](../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="92cf2-232">選取 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="92cf2-232">Select **Save Changes**.</span></span>
    
    ![儲存變更的 Freenom CNAME](../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="92cf2-234">重複上述步驟建立其他五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="92cf2-234">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="92cf2-235">每一筆記錄，輸入或複製並貼入該記錄的方塊中的表格中下一列中的值。</span><span class="sxs-lookup"><span data-stu-id="92cf2-235">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="92cf2-236">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="92cf2-236">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="92cf2-237"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="92cf2-237"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="92cf2-238">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="92cf2-238">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="92cf2-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="92cf2-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="92cf2-240">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="92cf2-240">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="92cf2-241">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="92cf2-241">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="92cf2-242">若要開始，使用[此連結](https://my.freenom.com/)移至您在 Freenom 中的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="92cf2-242">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="92cf2-243">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="92cf2-243">You'll be prompted to log in.</span></span>
    
    ![Freenom 登入](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="92cf2-245">選取 [**服務**]，然後選取 [**我的網域**。</span><span class="sxs-lookup"><span data-stu-id="92cf2-245">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 選取服務和我的網域](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="92cf2-247">針對您想要編輯的網域，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="92cf2-247">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 選取 [管理網域](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="92cf2-249">選取 [**管理 Freenom DNS**]。</span><span class="sxs-lookup"><span data-stu-id="92cf2-249">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom 選取管理 Freenom DNS](../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="92cf2-251">[**新增記錄**，在 [**類型**] 欄中， **TXT**從功能表中選擇。</span><span class="sxs-lookup"><span data-stu-id="92cf2-251">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom 新增記錄類型 TXT](../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="92cf2-253">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="92cf2-253">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="92cf2-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="92cf2-254">**Name**</span></span>|<span data-ttu-id="92cf2-255">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="92cf2-255">**Record type**</span></span>|<span data-ttu-id="92cf2-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="92cf2-256">**TTL**</span></span>|<span data-ttu-id="92cf2-257">**Target**</span><span class="sxs-lookup"><span data-stu-id="92cf2-257">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="92cf2-258">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="92cf2-258">(leave blank)</span></span>  <br/> |<span data-ttu-id="92cf2-259">TXT</span><span class="sxs-lookup"><span data-stu-id="92cf2-259">TXT</span></span>  <br/> |<span data-ttu-id="92cf2-260">3600 （秒）</span><span class="sxs-lookup"><span data-stu-id="92cf2-260">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="92cf2-261">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="92cf2-261">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="92cf2-262">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="92cf2-262">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Spf Freenom TXT 值](../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="92cf2-264">選取 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="92cf2-264">Select **Save Changes**.</span></span>
    
    ![Freenom TXT 記錄以 SPF 儲存變更](../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

