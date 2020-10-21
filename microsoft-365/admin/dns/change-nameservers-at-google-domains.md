---
title: 變更名稱伺服器以設定 Microsoft 搭配 Google 網域
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: 瞭解如何設定 Microsoft 以管理 Google 網域的自訂網域的 DNS 記錄。
ms.openlocfilehash: 05d77ef4cb78351727870a384f4a28c6e4acc4b0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646424"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a><span data-ttu-id="11ebe-103">變更名稱伺服器以設定 Microsoft 搭配 Google 網域</span><span class="sxs-lookup"><span data-stu-id="11ebe-103">Change nameservers to set up Microsoft with Google Domains</span></span>

 <span data-ttu-id="11ebe-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="11ebe-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="11ebe-105">如果您想讓 Microsoft 為您管理您的 DNS 記錄，請遵循下列指示。</span><span class="sxs-lookup"><span data-stu-id="11ebe-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="11ebe-106"> (如果您願意，您可以 [管理 Google 網域中的所有 DNS 記錄](create-dns-records-at-google-domains.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="11ebe-106">(If you prefer, you can [manage all your DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="11ebe-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="11ebe-107">Add a TXT record for verification</span></span>

<span data-ttu-id="11ebe-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="11ebe-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="11ebe-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="11ebe-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="11ebe-112">若要開始，請透過 [此連結](https://domains.google.com/registrar)移至 Google 網域上的 [網域] 頁面。</span><span class="sxs-lookup"><span data-stu-id="11ebe-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="11ebe-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="11ebe-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="11ebe-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="11ebe-114">To do so:</span></span>
    
1. <span data-ttu-id="11ebe-115">選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="11ebe-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="11ebe-116">輸入您的登入認證，然後再次選取 [登 **入**]。</span><span class="sxs-lookup"><span data-stu-id="11ebe-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="11ebe-117">在 **[網域]** 頁面中的 **[網域]** 章節，針對您想要編輯的網域，選取 **[設定 DNS]**。</span><span class="sxs-lookup"><span data-stu-id="11ebe-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="11ebe-118">在 [自訂資源記錄]  區段，於新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="11ebe-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="11ebe-119">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="11ebe-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="11ebe-120">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="11ebe-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="11ebe-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="11ebe-121">**Name**</span></span> <br/> |<span data-ttu-id="11ebe-122">**類型**</span><span class="sxs-lookup"><span data-stu-id="11ebe-122">**Type**</span></span> <br/> |<span data-ttu-id="11ebe-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="11ebe-123">**TTL**</span></span> <br/> |<span data-ttu-id="11ebe-124">**資料**</span><span class="sxs-lookup"><span data-stu-id="11ebe-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="11ebe-125">TXT</span><span class="sxs-lookup"><span data-stu-id="11ebe-125">TXT</span></span>  <br/> |<span data-ttu-id="11ebe-126">1H</span><span class="sxs-lookup"><span data-stu-id="11ebe-126">1H</span></span>  <br/> |<span data-ttu-id="11ebe-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="11ebe-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="11ebe-128">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="11ebe-128">**Note:** This is an example.</span></span> <span data-ttu-id="11ebe-129">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="11ebe-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="11ebe-130">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="11ebe-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="11ebe-131">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="11ebe-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="11ebe-132">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="11ebe-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="11ebe-133">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。</span><span class="sxs-lookup"><span data-stu-id="11ebe-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="11ebe-134">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="11ebe-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="11ebe-135">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="11ebe-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="11ebe-136">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="11ebe-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="11ebe-137">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="11ebe-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="11ebe-138">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="11ebe-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="11ebe-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="11ebe-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="11ebe-140">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="11ebe-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="11ebe-141">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="11ebe-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="11ebe-142">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="11ebe-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="11ebe-143">若要使用 Microsoft 設定您的網域，請在您的網域註冊機構變更網域的 NS 記錄，以指向 Microsoft 主要和次要名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="11ebe-143">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="11ebe-144">這會將 Microsoft 設定為您為您更新網域的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="11ebe-144">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="11ebe-145">我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="11ebe-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="11ebe-146">當您將網域的 NS 記錄變更為指向 Microsoft 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。</span><span class="sxs-lookup"><span data-stu-id="11ebe-146">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="11ebe-147">例如，所有傳送至您網域的電子郵件 (如 rob@ *your_domain。*</span><span class="sxs-lookup"><span data-stu-id="11ebe-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="11ebe-148">在您進行此變更之後，com) 會從 Microsoft 開始。</span><span class="sxs-lookup"><span data-stu-id="11ebe-148">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="11ebe-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="11ebe-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="11ebe-150">> 完成本節中的步驟之後，唯一應該會列出的名稱伺服器為下列四種：</span><span class="sxs-lookup"><span data-stu-id="11ebe-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="11ebe-p110">首先請用[這個連結](https://domains.google.com/registrar)移至 Google Domains 上您的網域頁面。系統會提示您登入。若要執行此作業，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="11ebe-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="11ebe-154">選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="11ebe-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="11ebe-155">輸入您的登入認證，然後再次選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="11ebe-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="11ebe-156">在 **[網域]** 頁面中的 **[網域]** 章節，針對您想要編輯的網域，選取 **[設定 DNS]**。</span><span class="sxs-lookup"><span data-stu-id="11ebe-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="11ebe-157">在 [ **網域** ] 頁面上，選取 [ **名稱伺服器** ] 區段中的 [ **使用自訂名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="11ebe-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-網域-BP-重新委派-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="11ebe-159">請根據現在顯示頁面上是否列出名稱伺服器，來選擇下列兩個程序其中一項繼續︰</span><span class="sxs-lookup"><span data-stu-id="11ebe-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="11ebe-160">如果沒有列出 **任何** 名稱伺服器， [則未列出任何名稱伺服器](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="11ebe-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="11ebe-161">如果已 **列出名稱伺服器，** 如果已 [列出名稱伺服器](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="11ebe-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="11ebe-162">如果列表上「沒有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="11ebe-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="11ebe-163">新增第一個名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="11ebe-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="11ebe-164">在 [ **名稱** 伺服器] 區段的 [ **名稱伺服器** ] 方塊中，輸入或複製並貼上下清單格中的第一個值。</span><span class="sxs-lookup"><span data-stu-id="11ebe-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="11ebe-165">**第一個名稱伺服器**</span><span class="sxs-lookup"><span data-stu-id="11ebe-165">**First name server**</span></span> <br/> |<span data-ttu-id="11ebe-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11ebe-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="11ebe-167">**第二個名稱伺服器**</span><span class="sxs-lookup"><span data-stu-id="11ebe-167">**Second name server**</span></span> <br/> |<span data-ttu-id="11ebe-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11ebe-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="11ebe-169">**第三名稱伺服器**</span><span class="sxs-lookup"><span data-stu-id="11ebe-169">**Third name server**</span></span> <br/> |<span data-ttu-id="11ebe-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11ebe-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="11ebe-171">**第四名稱伺服器**</span><span class="sxs-lookup"><span data-stu-id="11ebe-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="11ebe-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11ebe-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-網域-BP-重新委派-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="11ebe-174">選取 [ \*\*+ (新增) \*\* ] 控制項以建立空白列。</span><span class="sxs-lookup"><span data-stu-id="11ebe-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-網域-BP-重新委派-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="11ebe-176">新增其他三個名稱伺服器記錄。</span><span class="sxs-lookup"><span data-stu-id="11ebe-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="11ebe-177">在 [ **使用自訂名稱伺服器** ] 區段中，使用表格中下一列的值來建立記錄，然後選取 [ \*\*+ (新增) \*\* ] 控制項以新增另一個資料列。</span><span class="sxs-lookup"><span data-stu-id="11ebe-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="11ebe-178">重複這個程序，直到四筆名稱伺服器記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="11ebe-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="11ebe-179">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="11ebe-179">Select **Save**.</span></span>
    
    ![Google-網域-BP-重新委派-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="11ebe-181">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。</span><span class="sxs-lookup"><span data-stu-id="11ebe-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="11ebe-182">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="11ebe-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="11ebe-183">如果列表上「有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="11ebe-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="11ebe-184">如果有列出任何其他名稱伺服器，請選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="11ebe-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="11ebe-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="11ebe-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="11ebe-186"> (也就是說，只刪除所有  *未*  命名為 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或 **ns4.bdm.microsoftonline.com**的目前名稱伺服器。 ) </span><span class="sxs-lookup"><span data-stu-id="11ebe-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="11ebe-188">選取它，然後按鍵盤上的 **Delete** 鍵，逐一刪除。</span><span class="sxs-lookup"><span data-stu-id="11ebe-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="11ebe-190">在 [ **名稱** 伺服器] 區段的 [名稱 **伺服器** ] 列中，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="11ebe-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="11ebe-191">**第一個名稱伺服器**</span><span class="sxs-lookup"><span data-stu-id="11ebe-191">**First name server**</span></span> <br/> |<span data-ttu-id="11ebe-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11ebe-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="11ebe-193">**第二個名稱伺服器**</span><span class="sxs-lookup"><span data-stu-id="11ebe-193">**Second name server**</span></span> <br/> |<span data-ttu-id="11ebe-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11ebe-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="11ebe-195">**第三名稱伺服器**</span><span class="sxs-lookup"><span data-stu-id="11ebe-195">**Third name server**</span></span> <br/> |<span data-ttu-id="11ebe-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11ebe-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="11ebe-197">**第四名稱伺服器**</span><span class="sxs-lookup"><span data-stu-id="11ebe-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="11ebe-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11ebe-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-網域-BP-重新委派-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="11ebe-200">選取 [ \*\*+ (新增) \*\* ] 控制項以建立空白列。</span><span class="sxs-lookup"><span data-stu-id="11ebe-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="11ebe-202">新增其他兩筆名稱伺服器記錄。</span><span class="sxs-lookup"><span data-stu-id="11ebe-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="11ebe-203">在 [ **使用自訂名稱伺服器** ] 區段中，使用表格中下一列的值來建立記錄，然後選取 [ \*\*+ (新增) \*\* ] 控制項以新增另一個資料列。</span><span class="sxs-lookup"><span data-stu-id="11ebe-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="11ebe-204">重複這個程序，直到四筆名稱伺服器記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="11ebe-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="11ebe-205">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="11ebe-205">Select **Save**.</span></span>
    
    ![Google-網域-BP-重新委派-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="11ebe-207">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。</span><span class="sxs-lookup"><span data-stu-id="11ebe-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="11ebe-208">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="11ebe-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
