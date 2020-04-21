---
title: 在 OVH 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft OVH。
ms.openlocfilehash: 01c455f54a7ee2efc6114dba1c01170b97ea5f71
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629284"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="c5fcc-103">在 OVH 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="c5fcc-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="c5fcc-104">[檢查網域的常見問題集](../setup/domains-faq.md) ：供您在找不到所需功能時參考。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c5fcc-105">如果 OVH 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c5fcc-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="c5fcc-107">在 OVH 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="c5fcc-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="c5fcc-108">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c5fcc-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="c5fcc-109">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="c5fcc-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="c5fcc-110">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="c5fcc-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="c5fcc-111">新增 Microsoft 所需的兩筆 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="c5fcc-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="c5fcc-112">在 OVH 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="c5fcc-113">若要深入瞭解 Microsoft 的網站的主控和 DNS，請參閱搭配[Microsoft 使用公用網站](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="c5fcc-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c5fcc-117">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="c5fcc-117">Add a TXT record for verification</span></span>
<span data-ttu-id="c5fcc-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="c5fcc-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="c5fcc-119">在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="c5fcc-120">您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c5fcc-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c5fcc-123">若要開始使用，請使用[此連結](https://www.ovh.com/manager/)移至 OVH 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-123">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="c5fcc-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="c5fcc-124">You'll be prompted to log in.</span></span>
    
    ![OVH 登入](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="c5fcc-126">在 [**網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 選取網域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="c5fcc-128">選取 [ **DNS 區域**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-128">Select **DNS zone**.</span></span>
    
    ![OVH 選取 DNS 區域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="c5fcc-130">選取 [**新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-130">Select **Add an entry**.</span></span>
    
    ![OVH 新增專案](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="c5fcc-132">選取**TXT**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-132">Select **TXT**</span></span>
    
    ![OVH 選取 TXT 專案](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="c5fcc-134">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="c5fcc-135">若要指派 TTL 值，請從下拉式清單中選擇 [**個人**化]，然後在文字方塊中輸入值。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="c5fcc-136">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-136">**Record type**</span></span>|<span data-ttu-id="c5fcc-137">**子域**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-137">**Sub-domain**</span></span>|<span data-ttu-id="c5fcc-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-138">**TTL**</span></span>|<span data-ttu-id="c5fcc-139">**值**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c5fcc-140">TXT</span><span class="sxs-lookup"><span data-stu-id="c5fcc-140">TXT</span></span>  <br/> |<span data-ttu-id="c5fcc-141">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="c5fcc-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="c5fcc-142">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="c5fcc-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="c5fcc-143">MS= msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="c5fcc-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="c5fcc-144">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-144">**Note:** This is an example.</span></span> <span data-ttu-id="c5fcc-145">從表格中，使用您的特定**目的地或指向位址**值。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="c5fcc-146">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="c5fcc-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="c5fcc-147">選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-147">Select **Confirm**.</span></span> 
    
    ![OVH 確認 TXT 以進行驗證](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="c5fcc-149">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c5fcc-150">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求記錄。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-150">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="c5fcc-151">當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-151">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c5fcc-152">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c5fcc-153">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="c5fcc-154">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="c5fcc-155">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="c5fcc-p107">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c5fcc-159">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c5fcc-159">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c5fcc-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="c5fcc-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="c5fcc-161">若要開始使用，請使用[此連結](https://www.ovh.com/manager/)移至 OVH 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-161">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="c5fcc-162">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="c5fcc-162">You'll be prompted to log in.</span></span>
    
    ![OVH 登入](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="c5fcc-164">在 [**網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 選取網域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="c5fcc-166">選取 [ **DNS 區域**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-166">Select **DNS zone**.</span></span>
    
    ![OVH 選取 DNS 區域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="c5fcc-168">選取 [**新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-168">Select **Add an entry**.</span></span>
    
    ![OVH 新增專案](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="c5fcc-170">選取 [ **MX**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-170">Select **MX**.</span></span>
    
    ![OVH MX 記錄類型](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="c5fcc-172">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="c5fcc-173">若要指派 TTL 值，請從下拉式清單中選擇 [**個人**化]，然後在文字方塊中輸入值。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c5fcc-174">依預設，OVH 會對目標使用相對符號，將功能變數名稱新增至目標記錄的結尾。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="c5fcc-175">若要改為使用絕對標記法，請將點新增至目標記錄，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="c5fcc-176">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-176">**Record type**</span></span>|<span data-ttu-id="c5fcc-177">**子域**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-177">**Sub-domain**</span></span>|<span data-ttu-id="c5fcc-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-178">**TTL**</span></span>|<span data-ttu-id="c5fcc-179">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-179">**Priority**</span></span>|<span data-ttu-id="c5fcc-180">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="c5fcc-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c5fcc-181">MX</span><span class="sxs-lookup"><span data-stu-id="c5fcc-181">MX</span></span>  <br/> |<span data-ttu-id="c5fcc-182">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="c5fcc-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="c5fcc-183">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="c5fcc-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="c5fcc-184">10 </span><span class="sxs-lookup"><span data-stu-id="c5fcc-184">10</span></span>  <br/> <span data-ttu-id="c5fcc-185">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5fcc-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="c5fcc-186">\<網域金鑰\>。 mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c5fcc-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="c5fcc-187">**附注：** 從您的 Microsoft 帳戶取得您\* \<的網域金鑰\> \* 。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="c5fcc-188">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="c5fcc-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![郵件的 OVH MX 記錄](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="c5fcc-190">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-190">Select **Next**.</span></span>
    
    ![OVH MX 記錄選取 [下一步]](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="c5fcc-192">選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-192">Select **Confirm**.</span></span>
    
    ![OVH MX 記錄選取 [確認]](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="c5fcc-194">如果有任何其他 MX 記錄，請在 [ **DNS 區域**] 頁面上的清單中全部刪除。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="c5fcc-195">選取每一筆記錄，然後在 [**動作**] 欄中，選取 [垃圾箱] [可**刪除**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH 刪除 MX 記錄](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="c5fcc-197">選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c5fcc-198">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="c5fcc-198">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c5fcc-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="c5fcc-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="c5fcc-200">若要開始使用，請使用[此連結](https://www.ovh.com/manager/)移至 OVH 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-200">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="c5fcc-201">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="c5fcc-201">You'll be prompted to log in.</span></span>
    
    ![OVH 登入](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="c5fcc-203">在 [**網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 選取網域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="c5fcc-205">選取 [ **DNS 區域**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-205">Select **DNS zone**.</span></span>
    
    ![OVH 選取 DNS 區域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="c5fcc-207">選取 [**新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-207">Select **Add an entry**.</span></span>
    
    ![OVH 新增專案](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="c5fcc-209">選取 [ **CNAME**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-209">Select **CNAME**.</span></span>
    
    ![OVH 新增 CNAME 記錄類型](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="c5fcc-211">建立第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="c5fcc-212">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="c5fcc-213">若要指派 TTL 值，請從下拉式清單中選擇 [**個人**化]，然後在文字方塊中輸入值。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="c5fcc-214">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-214">**Record type**</span></span>|<span data-ttu-id="c5fcc-215">**子域**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-215">**Sub-domain**</span></span>|<span data-ttu-id="c5fcc-216">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="c5fcc-216">**Target**</span></span>|<span data-ttu-id="c5fcc-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c5fcc-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="c5fcc-218">CNAME</span></span>  <br/> |<span data-ttu-id="c5fcc-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c5fcc-219">autodiscover</span></span>  <br/> |<span data-ttu-id="c5fcc-220">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="c5fcc-221">3600秒</span><span class="sxs-lookup"><span data-stu-id="c5fcc-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="c5fcc-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="c5fcc-222">CNAME</span></span>  <br/> |<span data-ttu-id="c5fcc-223">sip</span><span class="sxs-lookup"><span data-stu-id="c5fcc-223">sip</span></span>  <br/> |<span data-ttu-id="c5fcc-224">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="c5fcc-225">3600秒</span><span class="sxs-lookup"><span data-stu-id="c5fcc-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="c5fcc-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="c5fcc-226">CNAME</span></span>  <br/> |<span data-ttu-id="c5fcc-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c5fcc-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c5fcc-228">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="c5fcc-229">3600秒</span><span class="sxs-lookup"><span data-stu-id="c5fcc-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="c5fcc-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="c5fcc-230">CNAME</span></span>  <br/> |<span data-ttu-id="c5fcc-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c5fcc-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c5fcc-232">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="c5fcc-233">3600秒</span><span class="sxs-lookup"><span data-stu-id="c5fcc-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="c5fcc-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="c5fcc-234">CNAME</span></span>  <br/> |<span data-ttu-id="c5fcc-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c5fcc-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c5fcc-236">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="c5fcc-237">3600秒</span><span class="sxs-lookup"><span data-stu-id="c5fcc-237">3600 seconds</span></span>  <br/> |
   
    ![OVH CNAME 記錄](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="c5fcc-239">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-239">Select **Next**.</span></span>
    
    ![OVH 新增 CNAME 值，然後選取 [下一步]](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="c5fcc-241">選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="c5fcc-242">重複上述步驟，以建立其他五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="c5fcc-243">針對每個記錄，輸入或複製並貼上表格中下一列的值，然後將其貼到該記錄的方塊中。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c5fcc-244">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="c5fcc-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c5fcc-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="c5fcc-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5fcc-246">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c5fcc-247">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c5fcc-248">如果您已有網域的 SPF 記錄，請不要為 Microsoft 建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-248">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c5fcc-249">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的*單一*SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-249">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="c5fcc-250">若要開始使用，請使用[此連結](https://www.ovh.com/manager/)移至 OVH 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-250">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="c5fcc-251">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="c5fcc-251">You'll be prompted to log in.</span></span>
    
    ![OVH 登入](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="c5fcc-253">在 [**網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 選取網域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="c5fcc-255">選取 [ **DNS 區域**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-255">Select **DNS zone**.</span></span>
    
    ![OVH 選取 DNS 區域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="c5fcc-257">選取 [**新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-257">Select **Add an entry**.</span></span>
    
    ![OVH 新增專案](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="c5fcc-259">選取 [ **TXT**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="c5fcc-260">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="c5fcc-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="c5fcc-261">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-261">**Record type**</span></span>|<span data-ttu-id="c5fcc-262">**子域**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-262">**Sub-domain**</span></span>|<span data-ttu-id="c5fcc-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-263">**TTL**</span></span>|<span data-ttu-id="c5fcc-264">**TXT Value** (TXT 值)</span><span class="sxs-lookup"><span data-stu-id="c5fcc-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c5fcc-265">TXT</span><span class="sxs-lookup"><span data-stu-id="c5fcc-265">TXT</span></span>  <br/> |<span data-ttu-id="c5fcc-266">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="c5fcc-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="c5fcc-267">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="c5fcc-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="c5fcc-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c5fcc-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c5fcc-269">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH 新增 SPF 的 TXT 記錄](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="c5fcc-271">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-271">Select **Next**.</span></span>
    
    ![OVH 新增 SPF 的 TXT 記錄，然後選取 [下一步]](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="c5fcc-273">選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-273">Select **Confirm**.</span></span>
    
    ![OVH 新增 SPF 及確認的 TXT 記錄](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c5fcc-275">新增 Microsoft 所需的兩筆 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="c5fcc-275">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c5fcc-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="c5fcc-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="c5fcc-277">若要開始使用，請使用[此連結](https://www.ovh.com/manager/)移至 OVH 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-277">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="c5fcc-278">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="c5fcc-278">You'll be prompted to log in.</span></span>
    
    ![OVH 登入](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="c5fcc-280">在 [**網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 選取網域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="c5fcc-282">選取 [ **DNS 區域**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-282">Select **DNS zone**.</span></span>
    
    ![OVH 選取 DNS 區域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="c5fcc-284">選取 [**新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-284">Select **Add an entry**.</span></span>
    
    ![OVH 新增專案](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="c5fcc-286">選取 [ **SRV**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-286">Select **SRV**.</span></span>
    
    ![OVH 選取 SRV 記錄類型](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="c5fcc-288">建立第一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="c5fcc-289">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="c5fcc-290">若要指派 TTL 值，請從下拉式清單中選擇 [**個人**化]，然後在文字方塊中輸入值。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="c5fcc-291">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-291">**Record type**</span></span>|<span data-ttu-id="c5fcc-292">**子域**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-292">**Sub-domain**</span></span>|<span data-ttu-id="c5fcc-293">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="c5fcc-293">**Priority**</span></span>|<span data-ttu-id="c5fcc-294">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="c5fcc-294">**Weight**</span></span>|<span data-ttu-id="c5fcc-295">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="c5fcc-295">**Port**</span></span>|<span data-ttu-id="c5fcc-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5fcc-296">**TTL**</span></span>|<span data-ttu-id="c5fcc-297">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="c5fcc-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c5fcc-298">SRV (Service) (SRV (服務))</span><span class="sxs-lookup"><span data-stu-id="c5fcc-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="c5fcc-299">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="c5fcc-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="c5fcc-300">100</span><span class="sxs-lookup"><span data-stu-id="c5fcc-300">100</span></span>  <br/> |<span data-ttu-id="c5fcc-301">1 </span><span class="sxs-lookup"><span data-stu-id="c5fcc-301">1</span></span>  <br/> |<span data-ttu-id="c5fcc-302">443</span><span class="sxs-lookup"><span data-stu-id="c5fcc-302">443</span></span>  <br/> |<span data-ttu-id="c5fcc-303">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="c5fcc-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="c5fcc-304">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="c5fcc-305">SRV (Service) (SRV (服務))</span><span class="sxs-lookup"><span data-stu-id="c5fcc-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="c5fcc-306">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="c5fcc-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="c5fcc-307">100</span><span class="sxs-lookup"><span data-stu-id="c5fcc-307">100</span></span>  <br/> |<span data-ttu-id="c5fcc-308">1 </span><span class="sxs-lookup"><span data-stu-id="c5fcc-308">1</span></span>  <br/> |<span data-ttu-id="c5fcc-309">5061</span><span class="sxs-lookup"><span data-stu-id="c5fcc-309">5061</span></span>  <br/> |<span data-ttu-id="c5fcc-310">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="c5fcc-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="c5fcc-311">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH SRV 記錄](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="c5fcc-313">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-313">Select **Next**.</span></span>
    
    ![OVH SRV 記錄選取 [下一步]](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="c5fcc-315">選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="c5fcc-316">重複上述步驟，以建立其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-316">Repeat the previous steps to create the other SRV record.</span></span> <span data-ttu-id="c5fcc-317">在第二筆記錄的方塊中，輸入或複製並貼上表格中第二列的值。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-317">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="c5fcc-p120">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c5fcc-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
