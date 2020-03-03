---
title: 變更名稱伺服器以設定 Office 365 使用 Namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: '了解如何設定 Office 365 自訂網域與 Namecheap，如果您希望 Office 365 來管理您的 DNS 記錄。 '
ms.openlocfilehash: 3a26f2acb9bb52d05974f050b265dd3e1a0fc0cb
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351804"
---
# <a name="change-nameservers-to-set-up-office-365-with-namecheap"></a><span data-ttu-id="fc17e-103">變更名稱伺服器以設定 Office 365 使用 Namecheap</span><span class="sxs-lookup"><span data-stu-id="fc17e-103">Change nameservers to set up Office 365 with Namecheap</span></span>

 <span data-ttu-id="fc17e-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="fc17e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="fc17e-105">如果您希望讓 Office 365 來管理您的 Office 365 DNS 記錄，請遵循下列指示。</span><span class="sxs-lookup"><span data-stu-id="fc17e-105">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you.</span></span> <span data-ttu-id="fc17e-106">（如果您想要的話，您可以[管理在 Namecheap 所有 Office 365 DNS 記錄](create-dns-records-at-namecheap.md)。）</span><span class="sxs-lookup"><span data-stu-id="fc17e-106">(If you prefer, you can [manage all your Office 365 DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fc17e-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="fc17e-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="fc17e-108">若要開始，使用[這個連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)移至您在 Namecheap 的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="fc17e-108">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="fc17e-109">系統會提示您登入，並繼續。</span><span class="sxs-lookup"><span data-stu-id="fc17e-109">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="fc17e-111">在**登陸**頁面上，在 [**帳戶**] 下，從下拉式清單中選擇**網域清單**。</span><span class="sxs-lookup"><span data-stu-id="fc17e-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="fc17e-113">在 [**網域清單**] 頁面上，尋找您想要編輯的網域名稱，然後選取**管理**。</span><span class="sxs-lookup"><span data-stu-id="fc17e-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="fc17e-115">選取 [**進階 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="fc17e-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="fc17e-117">在 [**主機記錄**] 區段中，選取 [**新增新的記錄**。</span><span class="sxs-lookup"><span data-stu-id="fc17e-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="fc17e-119">在 [**類型**下拉式清單，選取 [ **TXT 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="fc17e-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fc17e-120">當您選取 [**新增新的記錄**會自動出現**類型**下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="fc17e-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-DYN-BP-CONFIGURE-1-確認-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="fc17e-122">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="fc17e-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="fc17e-123">（從下拉式清單選擇 [ **TTL** ] 值）。</span><span class="sxs-lookup"><span data-stu-id="fc17e-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="fc17e-124">**類型**</span><span class="sxs-lookup"><span data-stu-id="fc17e-124">**Type**</span></span>|<span data-ttu-id="fc17e-125">**主機**</span><span class="sxs-lookup"><span data-stu-id="fc17e-125">**Host**</span></span>|<span data-ttu-id="fc17e-126">**Value** (值)</span><span class="sxs-lookup"><span data-stu-id="fc17e-126">**Value**</span></span>|<span data-ttu-id="fc17e-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fc17e-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fc17e-128">TXT</span><span class="sxs-lookup"><span data-stu-id="fc17e-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="fc17e-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fc17e-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="fc17e-130">**附註**： 這是範例。</span><span class="sxs-lookup"><span data-stu-id="fc17e-130">**Note**: This is an example.</span></span> <span data-ttu-id="fc17e-131">在這裡請使用您自己的 **[目的地或指向位址]** 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="fc17e-131">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="fc17e-132">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="fc17e-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="fc17e-133">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="fc17e-133">30 min</span></span>  <br/> |
   
   ![Namecheap-DYN-BP-CONFIGURE-1-確認-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="fc17e-135">選取**儲存的變更**（核取記號） 的控制項。</span><span class="sxs-lookup"><span data-stu-id="fc17e-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-確認-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="fc17e-137">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="fc17e-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fc17e-138">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="fc17e-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="fc17e-139">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="fc17e-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fc17e-140">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="fc17e-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="fc17e-141">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="fc17e-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="fc17e-142">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="fc17e-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="fc17e-143">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="fc17e-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="fc17e-p104">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="fc17e-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="fc17e-147">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="fc17e-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="fc17e-p105">如要完成網域設定以用於 Office 365，請在您的網域註冊機構更改網域的 NS 記錄，使它指向 Office 365 主要和次要名稱伺服器。這樣就會設定並讓 Office 365 為您更新網域的 DNS 記錄。我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="fc17e-p105">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="fc17e-p106">當您變更網域的 NS 記錄以指向 Office 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。例如，在您完成這項變更之後，凡是傳送到您的網域 (例如 rob@ *your_domain*  .com) 的電子郵件都將開始傳送到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="fc17e-p106">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="fc17e-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="fc17e-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="fc17e-154">若要開始，使用[這個連結](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)移至您在 Namecheap 的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="fc17e-154">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="fc17e-155">系統會提示您登入，並繼續。</span><span class="sxs-lookup"><span data-stu-id="fc17e-155">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="fc17e-157">在**登陸**頁面上，在 [**帳戶**] 下，從下拉式清單中選擇**網域清單**。</span><span class="sxs-lookup"><span data-stu-id="fc17e-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="fc17e-159">在 [**網域清單**] 頁面上，尋找您想要編輯的網域名稱，然後選取**管理**。</span><span class="sxs-lookup"><span data-stu-id="fc17e-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-DYN-BP-CONFIGURE-1-設定-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="fc17e-161">選取 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="fc17e-161">Select **Domain**.</span></span>
    
    ![Namecheap-DYN-BP-CONFIGURE-1-重新委派-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="fc17e-163">尋找 [**名稱**] 區段中，並再從**Namecheap 預設**下拉式清單中選取 [**自訂**。</span><span class="sxs-lookup"><span data-stu-id="fc17e-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-重新委派-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="fc17e-165">請根據是否已經現在顯示頁面上列出名稱伺服器，繼續進行下列其中一個兩個程序。</span><span class="sxs-lookup"><span data-stu-id="fc17e-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="fc17e-166">如果列表上「沒有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="fc17e-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="fc17e-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="fc17e-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="fc17e-168">選取 [**新增名稱伺服器**兩次，以新增兩個新列。</span><span class="sxs-lookup"><span data-stu-id="fc17e-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![Namecheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="fc17e-170">在 [**名稱**] 方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="fc17e-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="fc17e-171">**Nameserver 1 (名稱伺服器 1)**</span><span class="sxs-lookup"><span data-stu-id="fc17e-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="fc17e-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fc17e-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fc17e-173">**Nameserver 2 (名稱伺服器 2)**</span><span class="sxs-lookup"><span data-stu-id="fc17e-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="fc17e-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fc17e-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fc17e-175">**Nameserver 3 (名稱伺服器 3)**</span><span class="sxs-lookup"><span data-stu-id="fc17e-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="fc17e-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fc17e-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fc17e-177">**Nameserver 4 (名稱伺服器 4)**</span><span class="sxs-lookup"><span data-stu-id="fc17e-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="fc17e-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fc17e-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="fc17e-180">選取**儲存**（核取記號） 的控制項。</span><span class="sxs-lookup"><span data-stu-id="fc17e-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-重新委派-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="fc17e-p108">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="fc17e-p108">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="fc17e-184">如果列表上「有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="fc17e-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="fc17e-185">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span><span class="sxs-lookup"><span data-stu-id="fc17e-185">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span></span> <span data-ttu-id="fc17e-186">(也就是*只*刪除任何目前的名稱伺服器，*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**。)</span><span class="sxs-lookup"><span data-stu-id="fc17e-186">(That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="fc17e-187">如果有任何其他名稱伺服器列在 [**名稱**] 方塊中，刪除每個選取它，然後按鍵盤上的**Delete**鍵。</span><span class="sxs-lookup"><span data-stu-id="fc17e-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-重新委派-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="fc17e-189">選取 [**新增名稱伺服器**兩次，以新增兩個新列。</span><span class="sxs-lookup"><span data-stu-id="fc17e-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="fc17e-191">在 [**名稱**] 方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="fc17e-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="fc17e-192">**Name server 1 (名稱伺服器 1)**</span><span class="sxs-lookup"><span data-stu-id="fc17e-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="fc17e-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fc17e-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fc17e-194">**Name Server 2 (名稱伺服器 2)**</span><span class="sxs-lookup"><span data-stu-id="fc17e-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="fc17e-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fc17e-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fc17e-196">**Nameserver 3 (名稱伺服器 3)**</span><span class="sxs-lookup"><span data-stu-id="fc17e-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="fc17e-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fc17e-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fc17e-198">**Nameserver 4 (名稱伺服器 4)**</span><span class="sxs-lookup"><span data-stu-id="fc17e-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="fc17e-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fc17e-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="fc17e-201">選取**儲存**（核取記號） 的控制項。</span><span class="sxs-lookup"><span data-stu-id="fc17e-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-DYN-BP-CONFIGURE-1-重新委派-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="fc17e-p110">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="fc17e-p110">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>
