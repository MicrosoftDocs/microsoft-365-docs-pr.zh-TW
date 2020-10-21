---
title: 使用 Namecheap 變更名稱伺服器以設定 Microsoft
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: '若要讓 Microsoft 管理您的 DNS 記錄，請瞭解如何使用 Namecheap 設定您的 Microsoft 自訂網域。 '
ms.openlocfilehash: e305abb7768b286dbd24336c1dab39d919f9a0ac
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646448"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a><span data-ttu-id="ece07-103">使用 Namecheap 變更名稱伺服器以設定 Microsoft</span><span class="sxs-lookup"><span data-stu-id="ece07-103">Change nameservers to set up Microsoft with Namecheap</span></span>

 <span data-ttu-id="ece07-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="ece07-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="ece07-105">如果您想讓 Microsoft 為您管理您的 DNS 記錄，請遵循下列指示。</span><span class="sxs-lookup"><span data-stu-id="ece07-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="ece07-106"> (如果您願意，您可以 [在 Namecheap 管理所有的 MICROSOFT DNS 記錄](create-dns-records-at-namecheap.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="ece07-106">(If you prefer, you can [manage all your Microsoft DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ece07-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="ece07-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="ece07-108">若要開始使用，請移至您的網域頁面 Namecheap，方法是使用 [此連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)。</span><span class="sxs-lookup"><span data-stu-id="ece07-108">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="ece07-109">系統會提示您登入並繼續。</span><span class="sxs-lookup"><span data-stu-id="ece07-109">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="ece07-111">在 [ **登陸** ] 頁面的 [ **帳戶**] 下，從下拉式清單中選擇 [ **網域清單** ]。</span><span class="sxs-lookup"><span data-stu-id="ece07-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="ece07-113">在 [ **網域清單** ] 頁面上，尋找您要編輯的網功能變數名稱稱，然後選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="ece07-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="ece07-115">選取 [ **ADVANCED DNS**]。</span><span class="sxs-lookup"><span data-stu-id="ece07-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="ece07-117">在 [ **主機記錄** ] 區段中，選取 [ **新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="ece07-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="ece07-119">在 [ **類型** ] 下拉式清單中，選取 [ **TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="ece07-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ece07-120">當您選取 [**新增記錄**] 時，會自動顯示 [**類型**] 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="ece07-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="ece07-122">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="ece07-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="ece07-123"> (從下拉式清單中選取 [ **TTL** ] 值。 ) </span><span class="sxs-lookup"><span data-stu-id="ece07-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="ece07-124">**類型**</span><span class="sxs-lookup"><span data-stu-id="ece07-124">**Type**</span></span>|<span data-ttu-id="ece07-125">**主機**</span><span class="sxs-lookup"><span data-stu-id="ece07-125">**Host**</span></span>|<span data-ttu-id="ece07-126">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="ece07-126">**Value**</span></span>|<span data-ttu-id="ece07-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ece07-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ece07-128">TXT</span><span class="sxs-lookup"><span data-stu-id="ece07-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="ece07-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ece07-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ece07-130">**請注意**：這是一個範例。</span><span class="sxs-lookup"><span data-stu-id="ece07-130">**Note**: This is an example.</span></span> <span data-ttu-id="ece07-131">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="ece07-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="ece07-132">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="ece07-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ece07-133">30分鐘</span><span class="sxs-lookup"><span data-stu-id="ece07-133">30 min</span></span>  <br/> |
   
   ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="ece07-135">選取 [ **儲存變更** ] (核取記號) 控制項。</span><span class="sxs-lookup"><span data-stu-id="ece07-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="ece07-137">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="ece07-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ece07-138">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。</span><span class="sxs-lookup"><span data-stu-id="ece07-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="ece07-139">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="ece07-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ece07-140">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ece07-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="ece07-141">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="ece07-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ece07-142">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="ece07-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ece07-143">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="ece07-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ece07-p104">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="ece07-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="ece07-147">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="ece07-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="ece07-148">若要使用 Microsoft 設定您的網域，請在您的網域註冊機構變更網域的 NS 記錄，以指向 Microsoft 主要和次要名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="ece07-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="ece07-149">這會將 Microsoft 設定為您為您更新網域的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="ece07-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="ece07-150">我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="ece07-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ece07-151">當您將網域的 NS 記錄變更為指向 Microsoft 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。</span><span class="sxs-lookup"><span data-stu-id="ece07-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="ece07-152">例如，所有傳送至您網域的電子郵件 (例如 rob@ *your_domain*  .com) 會在您進行此變更之後，從 Microsoft 開始。</span><span class="sxs-lookup"><span data-stu-id="ece07-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="ece07-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="ece07-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="ece07-154">若要開始使用，請移至您的網域頁面 Namecheap，方法是使用 [此連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)。</span><span class="sxs-lookup"><span data-stu-id="ece07-154">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="ece07-155">系統會提示您登入並繼續。</span><span class="sxs-lookup"><span data-stu-id="ece07-155">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="ece07-157">在 [ **登陸** ] 頁面的 [ **帳戶**] 下，從下拉式清單中選擇 [ **網域清單** ]。</span><span class="sxs-lookup"><span data-stu-id="ece07-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="ece07-159">在 [ **網域清單** ] 頁面上，尋找您要編輯的網功能變數名稱稱，然後選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="ece07-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="ece07-161">選取 [ **網域**]。</span><span class="sxs-lookup"><span data-stu-id="ece07-161">Select **Domain**.</span></span>
    
    ![Namecheap-BP-重新委派-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="ece07-163">找到 [**名稱伺服器**] 區段，然後從 [ **Namecheap 預設**] 下拉式清單中選取 [**自訂**]。</span><span class="sxs-lookup"><span data-stu-id="ece07-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-BP-重新委派-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="ece07-165">請根據現在顯示頁面上是否列出名稱伺服器，繼續執行下列兩個程式中的其中一項。</span><span class="sxs-lookup"><span data-stu-id="ece07-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="ece07-166">如果列表上「沒有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="ece07-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="ece07-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="ece07-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="ece07-168">選取 [ **新增** 名稱伺服器] 兩次，以新增兩個新列。</span><span class="sxs-lookup"><span data-stu-id="ece07-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![Namecheap-BP-重新委派-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="ece07-170">在 [名稱伺服器 **] 方塊中** ，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="ece07-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="ece07-171">**Nameserver 1 (名稱伺服器 1)**</span><span class="sxs-lookup"><span data-stu-id="ece07-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="ece07-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ece07-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ece07-173">**Nameserver 2 (名稱伺服器 2)**</span><span class="sxs-lookup"><span data-stu-id="ece07-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="ece07-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ece07-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ece07-175">**Nameserver 3 (名稱伺服器 3)**</span><span class="sxs-lookup"><span data-stu-id="ece07-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="ece07-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ece07-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ece07-177">**Nameserver 4 (名稱伺服器 4)**</span><span class="sxs-lookup"><span data-stu-id="ece07-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="ece07-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ece07-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-重新委派-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="ece07-180">選取 [ **儲存** (] 核取記號) 控制項。</span><span class="sxs-lookup"><span data-stu-id="ece07-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-重新委派-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="ece07-182">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="ece07-182">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="ece07-183">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ece07-183">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="ece07-184">如果列表上「有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="ece07-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="ece07-185">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span><span class="sxs-lookup"><span data-stu-id="ece07-185">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span></span> <span data-ttu-id="ece07-186"> (也就是說，  *只*  刪除所有  *未*  命名為 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或 **ns4.bdm.microsoftonline.com**的目前名稱伺服器。 ) </span><span class="sxs-lookup"><span data-stu-id="ece07-186">(That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="ece07-187">如果名稱 **伺服器方塊中** 列出任何其他名稱伺服器，請選取它，然後按鍵盤上的 **delete** 鍵，逐一刪除。</span><span class="sxs-lookup"><span data-stu-id="ece07-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-BP-重新委派-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="ece07-189">選取 [ **新增** 名稱伺服器] 兩次，以新增兩個新列。</span><span class="sxs-lookup"><span data-stu-id="ece07-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![Namecheap-BP-重新委派-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="ece07-191">在 [名稱伺服器 **] 方塊中** ，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="ece07-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="ece07-192">**Name server 1 (名稱伺服器 1)**</span><span class="sxs-lookup"><span data-stu-id="ece07-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="ece07-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ece07-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ece07-194">**Name Server 2 (名稱伺服器 2)**</span><span class="sxs-lookup"><span data-stu-id="ece07-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="ece07-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ece07-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ece07-196">**Nameserver 3 (名稱伺服器 3)**</span><span class="sxs-lookup"><span data-stu-id="ece07-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="ece07-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ece07-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ece07-198">**Nameserver 4 (名稱伺服器 4)**</span><span class="sxs-lookup"><span data-stu-id="ece07-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="ece07-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ece07-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-重新委派-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="ece07-201">選取 [ **儲存** (] 核取記號) 控制項。</span><span class="sxs-lookup"><span data-stu-id="ece07-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-重新委派-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="ece07-203">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="ece07-203">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="ece07-204">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ece07-204">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
