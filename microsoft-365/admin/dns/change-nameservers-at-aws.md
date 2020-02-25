---
title: 變更名稱伺服器以使用 Amazon Web Services (AWS) 設定 Office 365
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: '了解如何設定 Office 365 來管理您的 DNS 記錄在 Amazon Web Services (AWS)。 '
ms.openlocfilehash: 08deba83738ba0e530e719cd6fd57bee423df5e0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239872"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a><span data-ttu-id="ddff9-103">變更名稱伺服器以使用 Amazon Web Services (AWS) 設定 Office 365</span><span class="sxs-lookup"><span data-stu-id="ddff9-103">Change nameservers to set up Office 365 with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="ddff9-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="ddff9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ddff9-p101">如果您希望讓 Office 365 來管理您的 Office 365 DNS 記錄，請遵循下列指示。(如果您想要的話，可以[在 AWS 管理所有的 Office 365 DNS 記錄](create-dns-records-at-aws.md)。)</span><span class="sxs-lookup"><span data-stu-id="ddff9-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ddff9-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="ddff9-107">Add a TXT record for verification</span></span>

<span data-ttu-id="ddff9-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="ddff9-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ddff9-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="ddff9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ddff9-p104">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="ddff9-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ddff9-114">在 [**資源**] 頁面上，選取 [**託管區域**]。</span><span class="sxs-lookup"><span data-stu-id="ddff9-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="ddff9-115">在 [**託管區域**] 頁面上，在**網域名稱**] 欄中，選取您想要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="ddff9-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="ddff9-116">選取 [**建立記錄集**。</span><span class="sxs-lookup"><span data-stu-id="ddff9-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="ddff9-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ddff9-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ddff9-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="ddff9-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="ddff9-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="ddff9-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ddff9-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="ddff9-121">**Name**</span></span> <br/> |<span data-ttu-id="ddff9-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="ddff9-122">**Type**</span></span> <br/> |<span data-ttu-id="ddff9-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ddff9-123">**Alias**</span></span> <br/> |<span data-ttu-id="ddff9-124">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="ddff9-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="ddff9-125">**值**</span><span class="sxs-lookup"><span data-stu-id="ddff9-125">**Value**</span></span> <br/> |<span data-ttu-id="ddff9-126">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="ddff9-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="ddff9-127">（此欄位請保留空白）</span><span class="sxs-lookup"><span data-stu-id="ddff9-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="ddff9-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="ddff9-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="ddff9-129">否</span><span class="sxs-lookup"><span data-stu-id="ddff9-129">No</span></span>  <br/> |<span data-ttu-id="ddff9-130">300</span><span class="sxs-lookup"><span data-stu-id="ddff9-130">300</span></span>  <br/> |<span data-ttu-id="ddff9-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ddff9-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="ddff9-132">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="ddff9-132">**Note:** This is an example.</span></span> <span data-ttu-id="ddff9-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ddff9-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="ddff9-134">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="ddff9-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="ddff9-135">簡易</span><span class="sxs-lookup"><span data-stu-id="ddff9-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="ddff9-136">選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ddff9-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="ddff9-137">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="ddff9-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ddff9-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="ddff9-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="ddff9-139">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="ddff9-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ddff9-140">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ddff9-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="ddff9-141">在 [**網域**] 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="ddff9-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="ddff9-142">在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="ddff9-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="ddff9-143">在 [**驗證網域**] 頁面上，選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="ddff9-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ddff9-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ddff9-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ddff9-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="ddff9-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ddff9-146">如果您遇到與郵件流程或其他問題新增 DNS 記錄之後，請參閱[尋找並修正新增網域或 Office 365 中的 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="ddff9-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="ddff9-147">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="ddff9-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="ddff9-p108">如要完成網域設定以用於 Office 365，請在您的網域註冊機構更改網域的 NS 記錄，使它指向 Office 365 主要和次要名稱伺服器。這樣就會設定並讓 Office 365 為您更新網域的 DNS 記錄。我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="ddff9-p108">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ddff9-p109">當您變更網域的 NS 記錄以指向 Office 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。例如，在您完成這項變更之後，凡是傳送到您的網域 (例如 rob@ *your_domain*  .com) 的電子郵件都將開始傳送到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ddff9-p109">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="ddff9-153">下列程序將告訴您如何從清單中，刪除任何其他不想要的名稱以及 how to： 新增如果他們沒有 」 列出正確的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="ddff9-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="ddff9-154">當您完成在此區段中，應該會列出的唯一名稱伺服器的步驟 > 是這四個: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ddff9-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="ddff9-155">首先請用[這個連結](https://console.aws.amazon.com/route53/home)移至 AWS 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="ddff9-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="ddff9-156">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="ddff9-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ddff9-157">在 [**資源**] 頁面上，選取 [**託管區域**]。</span><span class="sxs-lookup"><span data-stu-id="ddff9-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="ddff9-158">在 [**託管區域**] 頁面上，在**網域名稱**] 欄中，選取您想要編輯的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="ddff9-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="ddff9-159">選取**名稱伺服器**記錄集。</span><span class="sxs-lookup"><span data-stu-id="ddff9-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="ddff9-161">**NS-名稱伺服器**記錄中**的值**] 方塊中設定，刪除所有名稱伺服器選取全部，然後按鍵盤上的**Delete**鍵。</span><span class="sxs-lookup"><span data-stu-id="ddff9-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="ddff9-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="ddff9-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="ddff9-163">(也就是刪除只是任何目前的名稱*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**。)</span><span class="sxs-lookup"><span data-stu-id="ddff9-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="ddff9-165">在 [ **TTL （秒）：** ] 區域中，選取 [ **1h]** （1 小時）。</span><span class="sxs-lookup"><span data-stu-id="ddff9-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![選取一小時 1h]](../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="ddff9-167">仍在**NS-名稱伺服器**記錄設定，請在 [**值**] 方塊中，輸入或複製貼上下表中，**第一行**值，然後按**Enter**鍵上您的鍵盤並輸入或複製並貼上的下一個**行**值。</span><span class="sxs-lookup"><span data-stu-id="ddff9-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ddff9-168">每個名稱伺服器值，*必須*是自己 [**值**] 方塊內的個別行上，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="ddff9-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ddff9-169">**第一行**</span><span class="sxs-lookup"><span data-stu-id="ddff9-169">**First line**</span></span> <br/> |<span data-ttu-id="ddff9-170">ns1.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="ddff9-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="ddff9-171">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ddff9-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="ddff9-172">**第二行**</span><span class="sxs-lookup"><span data-stu-id="ddff9-172">**Second line**</span></span> <br/> |<span data-ttu-id="ddff9-173">ns2.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="ddff9-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="ddff9-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ddff9-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="ddff9-175">**第三行**</span><span class="sxs-lookup"><span data-stu-id="ddff9-175">**Third line**</span></span> <br/> |<span data-ttu-id="ddff9-176">ns3.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="ddff9-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="ddff9-177">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ddff9-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="ddff9-178">**第四行**</span><span class="sxs-lookup"><span data-stu-id="ddff9-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="ddff9-179">ns4.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="ddff9-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="ddff9-180">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="ddff9-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![鍵入或貼上值] 方塊中的第一個行值](../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="ddff9-182">選取 [**儲存記錄集**。</span><span class="sxs-lookup"><span data-stu-id="ddff9-182">Select **Save Record Set**.</span></span>
    
    ![選取 [儲存記錄集](../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="ddff9-p113">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="ddff9-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
