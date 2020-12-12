---
title: '使用 Amazon Web 服務 (AWS 變更名稱伺服器以設定 Microsoft) '
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: '瞭解如何設定 Microsoft，以在 Amazon Web 服務 (AWS) 上管理您的 DNS 記錄。 '
ms.openlocfilehash: 4700557c40973ab051cced81c129197a826964ab
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658449"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a><span data-ttu-id="f4c9f-103">使用 Amazon Web 服務 (AWS 變更名稱伺服器以設定 Microsoft) </span><span class="sxs-lookup"><span data-stu-id="f4c9f-103">Change nameservers to set up Microsoft with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="f4c9f-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f4c9f-105">如果您想讓 Microsoft 為您管理您的 DNS 記錄，請遵循下列指示。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="f4c9f-106"> (如果您願意，您可以 [在 AWS 管理所有的 MICROSOFT DNS 記錄](create-dns-records-at-aws.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="f4c9f-106">(If you prefer, you can [manage all your Microsoft DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f4c9f-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="f4c9f-107">Add a TXT record for verification</span></span>

<span data-ttu-id="f4c9f-p102">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4c9f-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f4c9f-p104">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f4c9f-114">在 [ **資源** ] 頁面上，選取 [ **主控區域**]。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="f4c9f-115">在 [ **主控區域** ] 頁面上的 [ **功能變數名稱** ] 欄中，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="f4c9f-116">選取 [ **建立記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="f4c9f-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f4c9f-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f4c9f-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="f4c9f-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="f4c9f-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="f4c9f-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f4c9f-121">**名稱**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-121">**Name**</span></span> <br/> |<span data-ttu-id="f4c9f-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-122">**Type**</span></span> <br/> |<span data-ttu-id="f4c9f-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-123">**Alias**</span></span> <br/> |<span data-ttu-id="f4c9f-124">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="f4c9f-125">**Value**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-125">**Value**</span></span> <br/> |<span data-ttu-id="f4c9f-126">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="f4c9f-127"> (將此欄位保留空白) </span><span class="sxs-lookup"><span data-stu-id="f4c9f-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="f4c9f-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="f4c9f-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="f4c9f-129">否</span><span class="sxs-lookup"><span data-stu-id="f4c9f-129">No</span></span>  <br/> |<span data-ttu-id="f4c9f-130">300</span><span class="sxs-lookup"><span data-stu-id="f4c9f-130">300</span></span>  <br/> |<span data-ttu-id="f4c9f-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f4c9f-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="f4c9f-132">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-132">**Note:** This is an example.</span></span> <span data-ttu-id="f4c9f-133">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="f4c9f-134">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="f4c9f-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="f4c9f-135">簡易</span><span class="sxs-lookup"><span data-stu-id="f4c9f-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="f4c9f-136">選取 [建立]。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="f4c9f-137">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f4c9f-138">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="f4c9f-139">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f4c9f-140">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f4c9f-141">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="f4c9f-142">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="f4c9f-143">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f4c9f-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="f4c9f-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="f4c9f-145">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="f4c9f-146">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f4c9f-147">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="f4c9f-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="f4c9f-148">若要使用 Microsoft 設定您的網域，請在您的網域註冊機構變更網域的 NS 記錄，以指向 Microsoft 主要和次要名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="f4c9f-149">這會將 Microsoft 設定為您為您更新網域的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="f4c9f-150">我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f4c9f-151">當您將網域的 NS 記錄變更為指向 Microsoft 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="f4c9f-152">例如，所有傳送至您網域的電子郵件 (例如 rob@ *your_domain*  .com) 會在您進行此變更之後，從 Microsoft 開始。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="f4c9f-153">下列程式將告訴您如何刪除清單中的任何其他、不想要的名稱伺服器，以及如何新增正確的名稱伺服器（如果尚未列出）。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="f4c9f-154">> 完成本節中的步驟之後，應該會列出的唯一名稱伺服器為下列四種： > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f4c9f-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="f4c9f-155">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="f4c9f-156">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f4c9f-157">在 [ **資源** ] 頁面上，選取 [ **主控區域**]。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="f4c9f-158">在 [ **主控區域** ] 頁面上的 [ **功能變數名稱** ] 欄中，選取您要編輯的網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="f4c9f-159">選取 [ **名稱** 伺服器] 記錄集。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="f4c9f-161">在 [**值**] 方塊的 [ **NS-名稱伺服器**] 記錄集中，選取所有的名稱伺服器，然後按下鍵盤上的 **delete** 鍵來刪除所有。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="f4c9f-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="f4c9f-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="f4c9f-163"> (也就是說，只刪除所有  *未*  命名為 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com** 的目前名稱伺服器。 ) </span><span class="sxs-lookup"><span data-stu-id="f4c9f-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="f4c9f-165">在 [ **TTL (秒) ：** ] 區域中，選取 [ **1H** (1 小時) ]。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![選取1H 一小時](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="f4c9f-167">仍在 **NS 名稱伺服器** 記錄集中的 [ **值** ] 方塊中，輸入或複製並貼上下表中的 **第一個行** 值，然後按下鍵盤上的 **Enter** 鍵，然後輸入或複製並貼上下 **一行** 的值。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="f4c9f-168">每個名稱伺服器值都  *必須*  在 [ **值** ] 方塊中各自的個別行上，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f4c9f-169">**第一行**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-169">**First line**</span></span> <br/> |<span data-ttu-id="f4c9f-170">ns1.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="f4c9f-171">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="f4c9f-172">**第二行**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-172">**Second line**</span></span> <br/> |<span data-ttu-id="f4c9f-173">ns2.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="f4c9f-174">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="f4c9f-175">**第三行**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-175">**Third line**</span></span> <br/> |<span data-ttu-id="f4c9f-176">ns3.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="f4c9f-177">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="f4c9f-178">**第四行**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="f4c9f-179">ns4.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="f4c9f-180">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="f4c9f-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![在 [值] 方塊中，輸入或貼上第一個行的值](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="f4c9f-182">選取 [ **儲存記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-182">Select **Save Record Set**.</span></span>
    
    ![選取儲存記錄集](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="f4c9f-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="f4c9f-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="f4c9f-185">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="f4c9f-185">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
