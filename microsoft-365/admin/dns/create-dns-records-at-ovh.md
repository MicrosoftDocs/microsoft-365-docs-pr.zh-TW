---
title: 在 OVH 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft OVH。
ms.openlocfilehash: 87a2a731a253fdc0593a1aae8020e615dca63c4a
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645812"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="16645-103">在 OVH 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="16645-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="16645-104">[檢查網域的常見問題集](../setup/domains-faq.md) ：供您在找不到所需功能時參考。</span><span class="sxs-lookup"><span data-stu-id="16645-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="16645-105">如果 OVH 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="16645-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="16645-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="16645-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="16645-107">在 OVH 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="16645-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="16645-108">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="16645-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="16645-109">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="16645-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="16645-110">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="16645-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="16645-111">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="16645-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="16645-112">在 OVH 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="16645-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="16645-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="16645-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="16645-116">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="16645-116">Add a TXT record for verification</span></span>
<span data-ttu-id="16645-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="16645-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="16645-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="16645-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16645-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="16645-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="16645-122">若要開始使用，請使用 [此連結](https://www.ovh.com/manager/)移至 OVH 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="16645-122">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="16645-123">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="16645-123">You'll be prompted to log in.</span></span>
    
    ![OVH 登入](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="16645-125">在 [ **網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="16645-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 選取網域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="16645-127">選取 [ **DNS 區域**]。</span><span class="sxs-lookup"><span data-stu-id="16645-127">Select **DNS zone**.</span></span>
    
    ![OVH 選取 DNS 區域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="16645-129">選取 [ **新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="16645-129">Select **Add an entry**.</span></span>
    
    ![OVH 新增專案](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="16645-131">選取 **TXT**</span><span class="sxs-lookup"><span data-stu-id="16645-131">Select **TXT**</span></span>
    
    ![OVH 選取 TXT 專案](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="16645-133">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="16645-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="16645-134">若要指派 TTL 值，請從下拉式清單中選擇 [ **個人** 化]，然後在文字方塊中輸入值。</span><span class="sxs-lookup"><span data-stu-id="16645-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="16645-135">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="16645-135">**Record type**</span></span>|<span data-ttu-id="16645-136">**子域**</span><span class="sxs-lookup"><span data-stu-id="16645-136">**Sub-domain**</span></span>|<span data-ttu-id="16645-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="16645-137">**TTL**</span></span>|<span data-ttu-id="16645-138">**Value**</span><span class="sxs-lookup"><span data-stu-id="16645-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16645-139">TXT</span><span class="sxs-lookup"><span data-stu-id="16645-139">TXT</span></span>  <br/> |<span data-ttu-id="16645-140">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="16645-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="16645-141">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="16645-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16645-142">MS= msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="16645-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="16645-143">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="16645-143">**Note:** This is an example.</span></span> <span data-ttu-id="16645-144">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="16645-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="16645-145">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="16645-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="16645-146">選取 **[確認]**。</span><span class="sxs-lookup"><span data-stu-id="16645-146">Select **Confirm**.</span></span> 
    
    ![OVH 確認 TXT 以進行驗證](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="16645-148">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="16645-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="16645-149">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="16645-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="16645-150">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="16645-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="16645-151">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="16645-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="16645-152">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="16645-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="16645-153">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="16645-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="16645-154">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="16645-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="16645-p107">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="16645-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="16645-158">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="16645-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="16645-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="16645-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="16645-160">若要開始使用，請使用 [此連結](https://www.ovh.com/manager/)移至 OVH 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="16645-160">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="16645-161">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="16645-161">You'll be prompted to log in.</span></span>
    
    ![OVH 登入](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="16645-163">在 [ **網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="16645-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 選取網域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="16645-165">選取 [ **DNS 區域**]。</span><span class="sxs-lookup"><span data-stu-id="16645-165">Select **DNS zone**.</span></span>
    
    ![OVH 選取 DNS 區域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="16645-167">選取 [ **新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="16645-167">Select **Add an entry**.</span></span>
    
    ![OVH 新增專案](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="16645-169">選取 [ **MX**]。</span><span class="sxs-lookup"><span data-stu-id="16645-169">Select **MX**.</span></span>
    
    ![OVH MX 記錄類型](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="16645-171">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="16645-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="16645-172">若要指派 TTL 值，請從下拉式清單中選擇 [ **個人** 化]，然後在文字方塊中輸入值。</span><span class="sxs-lookup"><span data-stu-id="16645-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="16645-173">依預設，OVH 會對目標使用相對符號，將功能變數名稱新增至目標記錄的結尾。</span><span class="sxs-lookup"><span data-stu-id="16645-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="16645-174">若要改為使用絕對標記法，請將點新增至目標記錄，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="16645-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="16645-175">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="16645-175">**Record type**</span></span>|<span data-ttu-id="16645-176">**子域**</span><span class="sxs-lookup"><span data-stu-id="16645-176">**Sub-domain**</span></span>|<span data-ttu-id="16645-177">**TTL**</span><span class="sxs-lookup"><span data-stu-id="16645-177">**TTL**</span></span>|<span data-ttu-id="16645-178">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="16645-178">**Priority**</span></span>|<span data-ttu-id="16645-179">**Target**</span><span class="sxs-lookup"><span data-stu-id="16645-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16645-180">MX</span><span class="sxs-lookup"><span data-stu-id="16645-180">MX</span></span>  <br/> |<span data-ttu-id="16645-181">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="16645-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="16645-182">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="16645-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16645-183">10 </span><span class="sxs-lookup"><span data-stu-id="16645-183">10</span></span>  <br/> <span data-ttu-id="16645-184">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="16645-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="16645-185">\<domain-key\>mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="16645-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="16645-186">\**附注：\*\*\*\<domain-key\>* 從您的 Microsoft 帳戶取得。</span><span class="sxs-lookup"><span data-stu-id="16645-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="16645-187">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="16645-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![郵件的 OVH MX 記錄](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="16645-189">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16645-189">Select **Next**.</span></span>
    
    ![OVH MX 記錄選取 [下一步]](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="16645-191">選取 **[確認]**。</span><span class="sxs-lookup"><span data-stu-id="16645-191">Select **Confirm**.</span></span>
    
    ![OVH MX 記錄選取 [確認]](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="16645-193">如果有任何其他 MX 記錄，請在 [ **DNS 區域** ] 頁面上的清單中全部刪除。</span><span class="sxs-lookup"><span data-stu-id="16645-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="16645-194">選取每一筆記錄，然後在 [ **動作** ] 欄中，選取 [垃圾箱] [可 **刪除** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="16645-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH 刪除 MX 記錄](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="16645-196">選取 **[確認]**。</span><span class="sxs-lookup"><span data-stu-id="16645-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="16645-197">新增 Microsoft 所需的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="16645-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="16645-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="16645-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="16645-199">若要開始使用，請使用 [此連結](https://www.ovh.com/manager/)移至 OVH 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="16645-199">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="16645-200">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="16645-200">You'll be prompted to log in.</span></span>
    
    ![OVH 登入](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="16645-202">在 [ **網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="16645-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 選取網域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="16645-204">選取 [ **DNS 區域**]。</span><span class="sxs-lookup"><span data-stu-id="16645-204">Select **DNS zone**.</span></span>
    
    ![OVH 選取 DNS 區域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="16645-206">選取 [ **新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="16645-206">Select **Add an entry**.</span></span>
    
    ![OVH 新增專案](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="16645-208">選取 [ **CNAME**]。</span><span class="sxs-lookup"><span data-stu-id="16645-208">Select **CNAME**.</span></span>
    
    ![OVH 新增 CNAME 記錄類型](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="16645-210">建立第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="16645-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="16645-211">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="16645-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="16645-212">若要指派 TTL 值，請從下拉式清單中選擇 [ **個人** 化]，然後在文字方塊中輸入值。</span><span class="sxs-lookup"><span data-stu-id="16645-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="16645-213">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="16645-213">**Record type**</span></span>|<span data-ttu-id="16645-214">**子域**</span><span class="sxs-lookup"><span data-stu-id="16645-214">**Sub-domain**</span></span>|<span data-ttu-id="16645-215">**Target**</span><span class="sxs-lookup"><span data-stu-id="16645-215">**Target**</span></span>|<span data-ttu-id="16645-216">**TTL**</span><span class="sxs-lookup"><span data-stu-id="16645-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16645-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="16645-217">CNAME</span></span>  <br/> |<span data-ttu-id="16645-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="16645-218">autodiscover</span></span>  <br/> |<span data-ttu-id="16645-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="16645-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="16645-220">3600秒</span><span class="sxs-lookup"><span data-stu-id="16645-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="16645-221">CNAME</span><span class="sxs-lookup"><span data-stu-id="16645-221">CNAME</span></span>  <br/> |<span data-ttu-id="16645-222">sip</span><span class="sxs-lookup"><span data-stu-id="16645-222">sip</span></span>  <br/> |<span data-ttu-id="16645-223">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="16645-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="16645-224">3600秒</span><span class="sxs-lookup"><span data-stu-id="16645-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="16645-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="16645-225">CNAME</span></span>  <br/> |<span data-ttu-id="16645-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="16645-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="16645-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="16645-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="16645-228">3600秒</span><span class="sxs-lookup"><span data-stu-id="16645-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="16645-229">CNAME</span><span class="sxs-lookup"><span data-stu-id="16645-229">CNAME</span></span>  <br/> |<span data-ttu-id="16645-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="16645-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="16645-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="16645-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="16645-232">3600秒</span><span class="sxs-lookup"><span data-stu-id="16645-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="16645-233">CNAME</span><span class="sxs-lookup"><span data-stu-id="16645-233">CNAME</span></span>  <br/> |<span data-ttu-id="16645-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="16645-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="16645-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="16645-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="16645-236">3600秒</span><span class="sxs-lookup"><span data-stu-id="16645-236">3600 seconds</span></span>  <br/> |
   
    ![OVH CNAME 記錄](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="16645-238">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16645-238">Select **Next**.</span></span>
    
    ![OVH 新增 CNAME 值，然後選取 [下一步]](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="16645-240">選取 **[確認]**。</span><span class="sxs-lookup"><span data-stu-id="16645-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="16645-241">重複上述步驟，以建立其他五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="16645-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="16645-242">針對每個記錄，輸入或複製並貼上表格中下一列的值，然後將其貼到該記錄的方塊中。</span><span class="sxs-lookup"><span data-stu-id="16645-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="16645-243">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="16645-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="16645-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="16645-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="16645-245">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="16645-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="16645-246">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="16645-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="16645-247">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="16645-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="16645-248">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="16645-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="16645-249">若要開始使用，請使用 [此連結](https://www.ovh.com/manager/)移至 OVH 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="16645-249">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="16645-250">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="16645-250">You'll be prompted to log in.</span></span>
    
    ![OVH 登入](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="16645-252">在 [ **網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="16645-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 選取網域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="16645-254">選取 [ **DNS 區域**]。</span><span class="sxs-lookup"><span data-stu-id="16645-254">Select **DNS zone**.</span></span>
    
    ![OVH 選取 DNS 區域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="16645-256">選取 [ **新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="16645-256">Select **Add an entry**.</span></span>
    
    ![OVH 新增專案](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="16645-258">選取 [ **TXT**]。</span><span class="sxs-lookup"><span data-stu-id="16645-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="16645-259">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="16645-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="16645-260">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="16645-260">**Record type**</span></span>|<span data-ttu-id="16645-261">**子域**</span><span class="sxs-lookup"><span data-stu-id="16645-261">**Sub-domain**</span></span>|<span data-ttu-id="16645-262">**TTL**</span><span class="sxs-lookup"><span data-stu-id="16645-262">**TTL**</span></span>|<span data-ttu-id="16645-263">**TXT Value** (TXT 值)</span><span class="sxs-lookup"><span data-stu-id="16645-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16645-264">TXT</span><span class="sxs-lookup"><span data-stu-id="16645-264">TXT</span></span>  <br/> |<span data-ttu-id="16645-265">(保留空白)</span><span class="sxs-lookup"><span data-stu-id="16645-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="16645-266">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="16645-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16645-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="16645-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="16645-268">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="16645-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH 新增 SPF 的 TXT 記錄](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="16645-270">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16645-270">Select **Next**.</span></span>
    
    ![OVH 新增 SPF 的 TXT 記錄，然後選取 [下一步]](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="16645-272">選取 **[確認]**。</span><span class="sxs-lookup"><span data-stu-id="16645-272">Select **Confirm**.</span></span>
    
    ![OVH 新增 SPF 及確認的 TXT 記錄](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="16645-274">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="16645-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="16645-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="16645-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="16645-276">若要開始使用，請使用 [此連結](https://www.ovh.com/manager/)移至 OVH 中您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="16645-276">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="16645-277">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="16645-277">You'll be prompted to log in.</span></span>
    
    ![OVH 登入](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="16645-279">在 [ **網域**] 底下，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="16645-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 選取網域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="16645-281">選取 [ **DNS 區域**]。</span><span class="sxs-lookup"><span data-stu-id="16645-281">Select **DNS zone**.</span></span>
    
    ![OVH 選取 DNS 區域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="16645-283">選取 [ **新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="16645-283">Select **Add an entry**.</span></span>
    
    ![OVH 新增專案](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="16645-285">選取 [ **SRV**]。</span><span class="sxs-lookup"><span data-stu-id="16645-285">Select **SRV**.</span></span>
    
    ![OVH 選取 SRV 記錄類型](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="16645-287">建立第一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="16645-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="16645-288">在每一筆新記錄的方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="16645-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="16645-289">若要指派 TTL 值，請從下拉式清單中選擇 [ **個人** 化]，然後在文字方塊中輸入值。</span><span class="sxs-lookup"><span data-stu-id="16645-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="16645-290">**記錄類型**</span><span class="sxs-lookup"><span data-stu-id="16645-290">**Record type**</span></span>|<span data-ttu-id="16645-291">**子域**</span><span class="sxs-lookup"><span data-stu-id="16645-291">**Sub-domain**</span></span>|<span data-ttu-id="16645-292">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="16645-292">**Priority**</span></span>|<span data-ttu-id="16645-293">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="16645-293">**Weight**</span></span>|<span data-ttu-id="16645-294">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="16645-294">**Port**</span></span>|<span data-ttu-id="16645-295">**TTL**</span><span class="sxs-lookup"><span data-stu-id="16645-295">**TTL**</span></span>|<span data-ttu-id="16645-296">**Target**</span><span class="sxs-lookup"><span data-stu-id="16645-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="16645-297">SRV (Service) (SRV (服務))</span><span class="sxs-lookup"><span data-stu-id="16645-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="16645-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="16645-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="16645-299">100</span><span class="sxs-lookup"><span data-stu-id="16645-299">100</span></span>  <br/> |<span data-ttu-id="16645-300">1 </span><span class="sxs-lookup"><span data-stu-id="16645-300">1</span></span>  <br/> |<span data-ttu-id="16645-301">443</span><span class="sxs-lookup"><span data-stu-id="16645-301">443</span></span>  <br/> |<span data-ttu-id="16645-302">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="16645-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16645-303">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="16645-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="16645-304">SRV (Service) (SRV (服務))</span><span class="sxs-lookup"><span data-stu-id="16645-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="16645-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="16645-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="16645-306">100</span><span class="sxs-lookup"><span data-stu-id="16645-306">100</span></span>  <br/> |<span data-ttu-id="16645-307">1 </span><span class="sxs-lookup"><span data-stu-id="16645-307">1</span></span>  <br/> |<span data-ttu-id="16645-308">5061</span><span class="sxs-lookup"><span data-stu-id="16645-308">5061</span></span>  <br/> |<span data-ttu-id="16645-309">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="16645-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="16645-310">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="16645-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH SRV 記錄](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="16645-312">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16645-312">Select **Next**.</span></span>
    
    ![OVH SRV 記錄選取 [下一步]](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="16645-314">選取 **[確認]**。</span><span class="sxs-lookup"><span data-stu-id="16645-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="16645-315">重複上述步驟，以建立其他 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="16645-315">Repeat the previous steps to create the other SRV record.</span></span> <span data-ttu-id="16645-316">在第二筆記錄的方塊中，輸入或複製並貼上表格中第二列的值。</span><span class="sxs-lookup"><span data-stu-id="16645-316">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="16645-p120">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="16645-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
