---
title: 使用 MyDomain 變更名稱伺服器以設定 Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: 瞭解如何設定 Microsoft，以在 MyDomain 管理自訂網域的 DNS 記錄。
ms.openlocfilehash: d8fc61c3adbe8b5b865bd82b8c4e0944198921e7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400626"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a><span data-ttu-id="cfd7a-103">使用 MyDomain 變更名稱伺服器以設定 Microsoft</span><span class="sxs-lookup"><span data-stu-id="cfd7a-103">Change nameservers to set up Microsoft with MyDomain</span></span>

 <span data-ttu-id="cfd7a-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="cfd7a-105">如果您想讓 Microsoft 為您管理您的 DNS 記錄，請遵循下列指示。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="cfd7a-106">（如果您願意，您可以[在 MyDomain 管理所有的 MICROSOFT DNS 記錄](create-dns-records-at-mydomain.md)。）</span><span class="sxs-lookup"><span data-stu-id="cfd7a-106">(If you prefer, you can [manage all your Microsoft DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cfd7a-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="cfd7a-107">Add a TXT record for verification</span></span>

<span data-ttu-id="cfd7a-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cfd7a-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="cfd7a-p104">首先，請用[此連結](https://www.mydomain.com/controlpanel)移至您在 MyDomain 的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="cfd7a-114">在 **[我的最愛]** 區段中，選取 **[網域中央]**。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="cfd7a-115">在 **[網域]** 下方，選取要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="cfd7a-116">在 **[總覽]** 區段，選取 **[DNS]**。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="cfd7a-117">從 **[修改]** 下拉式清單中，選擇 **[TXT/SPF 記錄]**。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="cfd7a-118">在 **[內容]** 底下，於新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="cfd7a-119">**內容**</span><span class="sxs-lookup"><span data-stu-id="cfd7a-119">**Content**</span></span> <br/> |
|<span data-ttu-id="cfd7a-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cfd7a-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cfd7a-121">**請注意**：這是一個範例。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-121">**Note**: This is an example.</span></span> <span data-ttu-id="cfd7a-122">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-122">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="cfd7a-123">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="cfd7a-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="cfd7a-124">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="cfd7a-125">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cfd7a-126">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 365 並要求 Microsoft 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-126">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="cfd7a-127">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-127">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cfd7a-128">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-128">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="cfd7a-129">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="cfd7a-130">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="cfd7a-131">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cfd7a-132">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cfd7a-132">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cfd7a-133">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cfd7a-134">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-134">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="cfd7a-135">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="cfd7a-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="cfd7a-136">若要使用 Microsoft 設定您的網域，請在您的網域註冊機構變更網域的 NS 記錄，以指向 Microsoft 主要和次要名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-136">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="cfd7a-137">這會將 Microsoft 設定為您為您更新網域的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-137">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="cfd7a-138">我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-138">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="cfd7a-139">當您將網域的 NS 記錄變更為指向 Microsoft 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-139">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="cfd7a-140">例如，所有傳送至您網域的電子郵件（如 rob@ *your_domain。*</span><span class="sxs-lookup"><span data-stu-id="cfd7a-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="cfd7a-141">com）在您進行此變更之後，將會開始進行 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-141">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="cfd7a-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="cfd7a-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <br/> <span data-ttu-id="cfd7a-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="cfd7a-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="cfd7a-p110">首先，請用[此連結](https://www.mydomain.com/controlpanel)移至您在 MyDomain 的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="cfd7a-146">在 **[我的最愛]** 區段中，選取 **[網域中央]**。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="cfd7a-147">在 **[網域]** 下方，選取要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="cfd7a-148">在 [**一覽**] 列中，選取 [**名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![MyDomain-重新委派-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="cfd7a-150">在 [**更新名稱伺服器**] 區段中，選取 [**使用不同的名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![MyDomain-重新委派-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="cfd7a-152">請根據現在顯示頁面上是否列出名稱伺服器，繼續執行下列兩個程式中的其中一項。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="cfd7a-153">如果列表上「有」正確的名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="cfd7a-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="cfd7a-154">如果列表上有正確的名稱伺服器，您可以跳過此步驟。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![MyDomain-重新委派-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="cfd7a-156">如果列表上「沒有」正確的名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="cfd7a-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="cfd7a-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="cfd7a-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="cfd7a-158">（也就是說，只刪除所有*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**的目前名稱伺服器。）</span><span class="sxs-lookup"><span data-stu-id="cfd7a-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="cfd7a-159">選取 [名稱伺服器 **：** ] 欄位中的每個專案，然後按下鍵盤上的**Delete**鍵，以刪除現有的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![MyDomain-重新委派-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="cfd7a-161">選取 [**增加其他**兩項]，以新增兩個新的名稱伺服器列。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![MyDomain-重新委派-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="cfd7a-163">在記錄的方塊中，輸入或複製並貼上下表中名稱伺服器的值。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="cfd7a-164">**Nameserver 1 (名稱伺服器 1)**</span><span class="sxs-lookup"><span data-stu-id="cfd7a-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="cfd7a-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="cfd7a-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="cfd7a-166">**Nameserver 2 (名稱伺服器 2)**</span><span class="sxs-lookup"><span data-stu-id="cfd7a-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="cfd7a-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="cfd7a-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="cfd7a-168">**Nameserver 3 (名稱伺服器 3)**</span><span class="sxs-lookup"><span data-stu-id="cfd7a-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="cfd7a-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="cfd7a-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="cfd7a-170">**Nameserver 4 (名稱伺服器 4)**</span><span class="sxs-lookup"><span data-stu-id="cfd7a-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="cfd7a-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="cfd7a-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![MyDomain-重新委派-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="cfd7a-173">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-173">Select **Save**.</span></span>
    
    ![MyDomain-重新委派-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="cfd7a-175">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-175">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="cfd7a-176">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="cfd7a-176">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
