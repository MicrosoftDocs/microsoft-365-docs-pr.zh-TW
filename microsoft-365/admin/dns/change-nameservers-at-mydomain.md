---
title: 使用 MyDomain 變更名稱伺服器以設定 Office 365
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: 瞭解如何設定 Office 365，以管理位於 MyDomain 的自訂網域的 DNS 記錄。
ms.openlocfilehash: f88f0528caf2229441fd3e5364b53864b923099f
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212042"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a><span data-ttu-id="f9457-103">使用 MyDomain 變更名稱伺服器以設定 Office 365</span><span class="sxs-lookup"><span data-stu-id="f9457-103">Change nameservers to set up Office 365 with MyDomain</span></span>

 <span data-ttu-id="f9457-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="f9457-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="f9457-p101">如果您希望讓 Office 365 來管理您的 Office 365 DNS 記錄，請遵循下列指示。(如果您想要的話，可以[在 MyDomain 管理所有的 Office 365 DNS 記錄](create-dns-records-at-mydomain.md)。)</span><span class="sxs-lookup"><span data-stu-id="f9457-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f9457-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="f9457-107">Add a TXT record for verification</span></span>

<span data-ttu-id="f9457-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="f9457-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9457-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="f9457-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f9457-p104">首先，請用[此連結](https://www.mydomain.com/controlpanel)移至您在 MyDomain 的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="f9457-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f9457-114">在 [我的最愛]\*\*\*\* 區段中，選取 [網域中央]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9457-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="f9457-115">在 [網域]\*\*\*\* 下方，選取要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="f9457-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="f9457-116">在 [總覽]\*\*\*\* 區段，選取 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9457-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="f9457-117">從 [修改]\*\*\*\* 下拉式清單中，選擇 [TXT/SPF 記錄]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9457-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="f9457-118">在 [內容] 底下，於新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="f9457-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="f9457-119">**內容**</span><span class="sxs-lookup"><span data-stu-id="f9457-119">**Content**</span></span> <br/> |
|<span data-ttu-id="f9457-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f9457-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f9457-121">**請注意**：這是一個範例。</span><span class="sxs-lookup"><span data-stu-id="f9457-121">**Note**: This is an example.</span></span> <span data-ttu-id="f9457-122">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="f9457-122">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="f9457-123">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="f9457-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="f9457-124">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9457-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="f9457-125">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="f9457-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f9457-126">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="f9457-126">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f9457-127">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="f9457-127">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f9457-128">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f9457-128">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f9457-129">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="f9457-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="f9457-130">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="f9457-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="f9457-131">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9457-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f9457-132">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="f9457-132">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="f9457-133">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="f9457-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="f9457-134">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f9457-134">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f9457-135">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="f9457-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="f9457-p107">如要完成網域設定以用於 Office 365，請在您的網域註冊機構更改網域的 NS 記錄，使它指向 Office 365 主要和次要名稱伺服器。這樣就會設定並讓 Office 365 為您更新網域的 DNS 記錄。我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="f9457-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f9457-139">當您變更網域的 NS 記錄以指向 Office 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。</span><span class="sxs-lookup"><span data-stu-id="f9457-139">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="f9457-140">例如，所有傳送至您網域的電子郵件（如 rob@ *your_domain。*</span><span class="sxs-lookup"><span data-stu-id="f9457-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="f9457-141">com）在您進行此變更後，會開始進入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f9457-141">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f9457-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="f9457-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <br/> <span data-ttu-id="f9457-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="f9457-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="f9457-p110">首先，請用[此連結](https://www.mydomain.com/controlpanel)移至您在 MyDomain 的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="f9457-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f9457-146">在 [我的最愛]\*\*\*\* 區段中，選取 [網域中央]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9457-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="f9457-147">在 [網域]\*\*\*\* 下方，選取要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="f9457-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="f9457-148">在 [**一覽**] 列中，選取 [**名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="f9457-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![MyDomain-重新委派-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="f9457-150">在 [**更新名稱伺服器**] 區段中，選取 [**使用不同的名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="f9457-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![MyDomain-重新委派-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="f9457-152">請根據現在顯示頁面上是否列出名稱伺服器，繼續執行下列兩個程式中的其中一項。</span><span class="sxs-lookup"><span data-stu-id="f9457-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="f9457-153">如果列表上「有」正確的名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="f9457-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="f9457-154">如果列表上有正確的名稱伺服器，您可以跳過此步驟。</span><span class="sxs-lookup"><span data-stu-id="f9457-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![MyDomain-重新委派-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="f9457-156">如果列表上「沒有」正確的名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="f9457-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="f9457-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="f9457-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="f9457-158">（也就是說，只刪除所有*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**的目前名稱伺服器。）</span><span class="sxs-lookup"><span data-stu-id="f9457-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="f9457-159">選取 [名稱伺服器 **：** ] 欄位中的每個專案，然後按下鍵盤上的**Delete**鍵，以刪除現有的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="f9457-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![MyDomain-重新委派-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="f9457-161">選取 [**增加其他**兩項]，以新增兩個新的名稱伺服器列。</span><span class="sxs-lookup"><span data-stu-id="f9457-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![MyDomain-重新委派-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="f9457-163">在記錄的方塊中，輸入或複製並貼上下表中名稱伺服器的值。</span><span class="sxs-lookup"><span data-stu-id="f9457-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="f9457-164">**Nameserver 1 (名稱伺服器 1)**</span><span class="sxs-lookup"><span data-stu-id="f9457-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="f9457-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f9457-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f9457-166">**Nameserver 2 (名稱伺服器 2)**</span><span class="sxs-lookup"><span data-stu-id="f9457-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="f9457-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f9457-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f9457-168">**Nameserver 3 (名稱伺服器 3)**</span><span class="sxs-lookup"><span data-stu-id="f9457-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="f9457-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f9457-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f9457-170">**Nameserver 4 (名稱伺服器 4)**</span><span class="sxs-lookup"><span data-stu-id="f9457-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="f9457-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f9457-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![MyDomain-重新委派-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="f9457-173">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="f9457-173">Select **Save**.</span></span>
    
    ![MyDomain-重新委派-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="f9457-p112">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="f9457-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
