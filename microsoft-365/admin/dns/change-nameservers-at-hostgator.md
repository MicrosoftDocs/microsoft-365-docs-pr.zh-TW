---
title: 使用 Hostgator 變更名稱伺服器以設定 Microsoft
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: 瞭解如何在 Hostgator 中設定 Microsoft 管理自訂網域的 DNS 記錄。
ms.openlocfilehash: 02052e98ba92c970a1e8bcc89c73df6946a6c472
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646436"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a><span data-ttu-id="94e2d-103">使用 Hostgator 變更名稱伺服器以設定 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94e2d-103">Change nameservers to set up Microsoft 365 with Hostgator</span></span>

 <span data-ttu-id="94e2d-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="94e2d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="94e2d-105">如果您想讓 Microsoft 為您管理您的 DNS 記錄，請遵循下列指示。</span><span class="sxs-lookup"><span data-stu-id="94e2d-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="94e2d-106"> (如果您願意，您可以 [在 Hostgator 管理所有的 MICROSOFT DNS 記錄](create-dns-records-at-hostgator.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="94e2d-106">(If you prefer, you can [manage all your Microsoft DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="94e2d-107">將您的網域指向您的代管帳戶。</span><span class="sxs-lookup"><span data-stu-id="94e2d-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94e2d-108">您必須先執行此程式，再執行下一節中的 **程式，新增 TXT 記錄以進行驗證**。</span><span class="sxs-lookup"><span data-stu-id="94e2d-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="94e2d-109">請遵循下列步驟，建立您的網域和代管帳戶的關聯。</span><span class="sxs-lookup"><span data-stu-id="94e2d-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="94e2d-p102">首先請用[這個連結](https://portal.hostgator.com/domain/manage)移至 Hostgator 上您的客戶入口網站頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="94e2d-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="94e2d-113">選取 [ **網域** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="94e2d-113">Select the **Domains** tab.</span></span>
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="94e2d-115">在 [ **管理網域** ] 頁面上的 [ **我的網域** ] 區域中，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="94e2d-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="94e2d-117">在 [ **網域概述** ] 頁面的 [ **名稱伺服器** ] 區域中，選取 [ **變更**]。</span><span class="sxs-lookup"><span data-stu-id="94e2d-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="94e2d-119">在您網域的 [ **名稱伺服器** ] 頁面上，于 [ **選取主控帳戶** ] 下拉式清單中，選擇與您的網域相關聯的 **主控帳戶** 。</span><span class="sxs-lookup"><span data-stu-id="94e2d-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="94e2d-121">選取 [ **儲存名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="94e2d-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="94e2d-123">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="94e2d-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94e2d-124">在執行此程式之前，您必須先執行本文第一節中的 [程式，將您的網域指向您的託管帳戶。](#point-your-domain-to-your-hosting-account)。</span><span class="sxs-lookup"><span data-stu-id="94e2d-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="94e2d-p103">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="94e2d-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="94e2d-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="94e2d-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="94e2d-p105">若要開始使用，請移至您位於 Hostgator 的 cPanel 頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="94e2d-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="94e2d-p106">(每個 Hostgator 代管的帳戶都有一個唯一的 cPanel 位址。您的 cPanel 位址看起來應該像這樣：https://YourSiteAddress:secure-port-number。您從 Hostgator 收到的註冊電子郵件會指出該位址。)</span><span class="sxs-lookup"><span data-stu-id="94e2d-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="94e2d-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="94e2d-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="94e2d-135">若要開始使用，您可以從 Hostgator 購買主控帳戶，也可以 [變更您網域的名稱伺服器 (NS) 記錄](#change-your-domains-nameserver-ns-records) ，以指向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="94e2d-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span></span> 
  
2. <span data-ttu-id="94e2d-136">在 [ **控制台** ] 頁面的 [ **網域** ] 區域中，選取 [ **高級 DNS 區域編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="94e2d-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="94e2d-137">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="94e2d-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="94e2d-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="94e2d-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="94e2d-139">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="94e2d-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="94e2d-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="94e2d-140">**Name**</span></span> <br/> |<span data-ttu-id="94e2d-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="94e2d-141">**TTL**</span></span> <br/> |<span data-ttu-id="94e2d-142">**類型**</span><span class="sxs-lookup"><span data-stu-id="94e2d-142">**Type**</span></span> <br/> |<span data-ttu-id="94e2d-143">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="94e2d-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="94e2d-144">使用您的  *domain_name*  。</span><span class="sxs-lookup"><span data-stu-id="94e2d-144">Use your  *domain_name*  .</span></span> <span data-ttu-id="94e2d-145">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="94e2d-145">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="94e2d-146">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="94e2d-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="94e2d-147">1 </span><span class="sxs-lookup"><span data-stu-id="94e2d-147">1</span></span>  <br/> |<span data-ttu-id="94e2d-148">TXT</span><span class="sxs-lookup"><span data-stu-id="94e2d-148">TXT</span></span>  <br/> |<span data-ttu-id="94e2d-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="94e2d-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="94e2d-150">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="94e2d-150">**Note:** This is an example.</span></span> <span data-ttu-id="94e2d-151">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="94e2d-151">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="94e2d-152">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="94e2d-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="94e2d-153">選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="94e2d-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="94e2d-154">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="94e2d-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="94e2d-155">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。</span><span class="sxs-lookup"><span data-stu-id="94e2d-155">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="94e2d-156">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="94e2d-156">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="94e2d-157">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="94e2d-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="94e2d-158">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="94e2d-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="94e2d-159">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="94e2d-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="94e2d-160">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="94e2d-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="94e2d-161">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="94e2d-161">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="94e2d-162">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="94e2d-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="94e2d-163">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="94e2d-163">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="94e2d-164">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="94e2d-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="94e2d-165">若要使用 Microsoft 設定您的網域，請在您的網域註冊機構變更網域的 NS 記錄，以指向 Microsoft 主要和次要名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="94e2d-165">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="94e2d-166">這會將 Microsoft 設定為您為您更新網域的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="94e2d-166">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="94e2d-167">我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="94e2d-167">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="94e2d-168">當您將網域的 NS 記錄變更為指向 Microsoft 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。</span><span class="sxs-lookup"><span data-stu-id="94e2d-168">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="94e2d-169">例如，所有傳送至您網域的電子郵件 (例如 rob@ *your_domain*  .com) 會在您進行此變更之後，從 Microsoft 開始。</span><span class="sxs-lookup"><span data-stu-id="94e2d-169">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="94e2d-170">下列程式將告訴您如何刪除清單中的任何其他、不想要的名稱伺服器，以及如何新增正確的名稱伺服器（如果尚未列出）。</span><span class="sxs-lookup"><span data-stu-id="94e2d-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="94e2d-171">當您完成本節中的步驟之後，應該會列出的唯一名稱伺服器為下列四種：  **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**和 **ns4.bdm.microsoftonline.com**。</span><span class="sxs-lookup"><span data-stu-id="94e2d-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="94e2d-p114">首先請用[這個連結](https://portal.hostgator.com/domain/manage)移至 Hostgator 上您的客戶入口網站頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="94e2d-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="94e2d-175">選取 [ **網域** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="94e2d-175">Select the **Domains** tab.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="94e2d-177">在 [ **管理網域** ] 頁面上的 [ **我的網域** ] 區域中，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="94e2d-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="94e2d-179">在 [ **網域一覽** ] 頁面的 [ **名稱伺服器** ] 區域中，選取 [ **變更**]。</span><span class="sxs-lookup"><span data-stu-id="94e2d-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="94e2d-181">在您網域的 [ **名稱伺服器** ] 頁面上，于 [ **選取主控帳戶** ] 下拉式清單中，選擇與您的網域相關聯的 **主控帳戶** 。</span><span class="sxs-lookup"><span data-stu-id="94e2d-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="94e2d-183">選取 [ **手動設定我的名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="94e2d-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="94e2d-185">**警告**：只有當現有的名稱伺服器不是四個正確的名稱伺服器時，才遵循這些步驟。</span><span class="sxs-lookup"><span data-stu-id="94e2d-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="94e2d-186"> (也就是說，只刪除所有  *未*  命名為 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或 **ns4.bdm.microsoftonline.com**的目前名稱伺服器。 ) </span><span class="sxs-lookup"><span data-stu-id="94e2d-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="94e2d-187">在您網域的 [名稱伺服器] 頁面上，在名稱伺服器清單中，選取清單中的每個名稱伺服器，然後按鍵盤上的**delete**鍵，以刪除清單中的每個**名稱伺服器**。</span><span class="sxs-lookup"><span data-stu-id="94e2d-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![Hostgator-BP-Redelegate-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="94e2d-189">同樣在名稱伺服器清單中，輸入或複製並貼上下表中的前兩個值。</span><span class="sxs-lookup"><span data-stu-id="94e2d-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="94e2d-190">**Name Server 1: (名稱伺服器 1:)**</span><span class="sxs-lookup"><span data-stu-id="94e2d-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="94e2d-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="94e2d-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="94e2d-192">**名稱伺服器2：**</span><span class="sxs-lookup"><span data-stu-id="94e2d-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="94e2d-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="94e2d-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="94e2d-194">**名稱伺服器3：**</span><span class="sxs-lookup"><span data-stu-id="94e2d-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="94e2d-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="94e2d-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="94e2d-196">**名稱伺服器4：**</span><span class="sxs-lookup"><span data-stu-id="94e2d-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="94e2d-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="94e2d-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Hostgator-BP-重新委派-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="94e2d-199">新增其他名稱伺服器的值。</span><span class="sxs-lookup"><span data-stu-id="94e2d-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="94e2d-200">選取 [ \*\* (+) \*\* 新增]，然後在記錄的方塊中輸入或複製並貼上表格中下一列的值。</span><span class="sxs-lookup"><span data-stu-id="94e2d-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="94e2d-201">重複這個程序，直到四筆名稱伺服器記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="94e2d-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="94e2d-203">選取 [ **儲存名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="94e2d-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="94e2d-205">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。</span><span class="sxs-lookup"><span data-stu-id="94e2d-205">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="94e2d-206">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="94e2d-206">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
