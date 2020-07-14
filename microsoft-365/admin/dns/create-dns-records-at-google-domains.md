---
title: 在 Google Domains 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: 了解如何在 Microsoft 的 Google Domains 中驗證網域，並為電子郵件、Lync 和其他服務設定 DNS 記錄。
ms.openlocfilehash: e6b1dd1eb90957a4e7fe22bd4b66ac87b2a51d09
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400446"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="91bcf-103">在 Google Domains 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="91bcf-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="91bcf-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="91bcf-105">如果 Google Domains 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與 Lync 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="91bcf-106">在 Google Domains 新增這些記錄之後，您的網域就會設定為搭配 Microsoft 服務使用。</span><span class="sxs-lookup"><span data-stu-id="91bcf-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="91bcf-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="91bcf-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="91bcf-108">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="91bcf-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="91bcf-109">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Microsoft 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="91bcf-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="91bcf-110">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="91bcf-110">Add a TXT record for verification</span></span>
<span data-ttu-id="91bcf-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="91bcf-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="91bcf-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="91bcf-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="91bcf-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="91bcf-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="91bcf-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="91bcf-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="91bcf-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="91bcf-115">You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="91bcf-116">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="91bcf-116">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="91bcf-117">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="91bcf-117">You'll be prompted to sign in.</span></span> <span data-ttu-id="91bcf-118">To do so:</span><span class="sxs-lookup"><span data-stu-id="91bcf-118">To do so:</span></span>
    
1. <span data-ttu-id="91bcf-119">選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="91bcf-120">輸入您的登入認證，然後再次選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="91bcf-121">在 **[我的網域]** 頁面上，找到您要與 Microsoft 搭配使用的網域，然後選取其旁邊的 **[管理]** 連結。</span><span class="sxs-lookup"><span data-stu-id="91bcf-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="91bcf-122">在左側瀏覽窗格中，選取 **[DNS]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="91bcf-123">在 [自訂資源記錄]  區段，於新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="91bcf-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="91bcf-124">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="91bcf-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="91bcf-125">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="91bcf-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="91bcf-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="91bcf-126">**Name**</span></span> <br/> |<span data-ttu-id="91bcf-127">**類型**</span><span class="sxs-lookup"><span data-stu-id="91bcf-127">**Type**</span></span> <br/> |<span data-ttu-id="91bcf-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="91bcf-128">**TTL**</span></span> <br/> |<span data-ttu-id="91bcf-129">**資料**</span><span class="sxs-lookup"><span data-stu-id="91bcf-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="91bcf-130">TXT</span><span class="sxs-lookup"><span data-stu-id="91bcf-130">TXT</span></span>  <br/> |<span data-ttu-id="91bcf-131">1H</span><span class="sxs-lookup"><span data-stu-id="91bcf-131">1H</span></span>  <br/> |<span data-ttu-id="91bcf-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="91bcf-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="91bcf-133">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="91bcf-133">**Note:** This is an example.</span></span> <span data-ttu-id="91bcf-134">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="91bcf-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="91bcf-135">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="91bcf-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="91bcf-136">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="91bcf-137">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="91bcf-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="91bcf-138">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="91bcf-139">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="91bcf-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="91bcf-140">在 Microsoft 系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="91bcf-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="91bcf-141">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="91bcf-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="91bcf-142">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="91bcf-143">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="91bcf-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="91bcf-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="91bcf-145">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="91bcf-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="91bcf-146">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="91bcf-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="91bcf-147">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="91bcf-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="91bcf-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="91bcf-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="91bcf-149">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="91bcf-149">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="91bcf-150">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="91bcf-150">You'll be prompted to sign in.</span></span> <span data-ttu-id="91bcf-151">To do so:</span><span class="sxs-lookup"><span data-stu-id="91bcf-151">To do so:</span></span>
    
2. <span data-ttu-id="91bcf-152">選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="91bcf-153">輸入您的登入認證，然後再次選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="91bcf-154">在 **[網域]** 頁面中的 **[網域]** 章節，針對您想要編輯的網域，選取 **[設定 DNS]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="91bcf-155">如果您擁有 G Suite 電子郵件帳戶，則必須先刪除與該帳戶相關聯的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="91bcf-156">G Suite 的 MX 記錄會使您無法新增其他 MX 記錄，包括 Microsoft 所需的記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="91bcf-157">請注意，刪除 G Suite 記錄並不會刪除您的 G Suite 帳戶。</span><span class="sxs-lookup"><span data-stu-id="91bcf-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="91bcf-158">若要刪除您的 G Suite MX 記錄，請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="91bcf-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="91bcf-159">在 **[綜合記錄]** 章節的 **[G 套件]** 區域，選取 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="91bcf-160">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="91bcf-160">(You may have to scroll down.)</span></span>
    
    ![選取 [綜合記錄] 章節中的 [刪除]。](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="91bcf-162">選取 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-162">Select **Delete**.</span></span>
    
    ![選取 [刪除]](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="91bcf-164">在 [自訂資源記錄]  區段，於新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="91bcf-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="91bcf-165">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="91bcf-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="91bcf-166">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="91bcf-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="91bcf-167">**Name**</span><span class="sxs-lookup"><span data-stu-id="91bcf-167">**Name**</span></span>|<span data-ttu-id="91bcf-168">**類型**</span><span class="sxs-lookup"><span data-stu-id="91bcf-168">**Type**</span></span>|<span data-ttu-id="91bcf-169">**TTL**</span><span class="sxs-lookup"><span data-stu-id="91bcf-169">**TTL**</span></span>|<span data-ttu-id="91bcf-170">**資料**</span><span class="sxs-lookup"><span data-stu-id="91bcf-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="91bcf-171">MX</span><span class="sxs-lookup"><span data-stu-id="91bcf-171">MX</span></span>  <br/> |<span data-ttu-id="91bcf-172">1H</span><span class="sxs-lookup"><span data-stu-id="91bcf-172">1H</span></span>  <br/> |<span data-ttu-id="91bcf-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="91bcf-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="91bcf-174">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="91bcf-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="91bcf-175">**0** 是指 MX 優先順序值。</span><span class="sxs-lookup"><span data-stu-id="91bcf-175">The **0** is the MX priority value.</span></span> <span data-ttu-id="91bcf-176">請將它新增到 MX 值的開頭，並以空格分隔該值的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="91bcf-176">Add it to the beginning of the MX value, separated from the remainder of the value by a space.</span></span>  <br/> <span data-ttu-id="91bcf-177">**注意：** 從您的 Microsoft 帳戶取得您的 \<*domain-key*\>。</span><span class="sxs-lookup"><span data-stu-id="91bcf-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="91bcf-178">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="91bcf-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="91bcf-179">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="91bcf-179">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![在 [自訂資源記錄] 區段中輸入或貼上值](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="91bcf-181">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-181">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="91bcf-183">如果有任何其他的自訂 MX 記錄，請移除它們。</span><span class="sxs-lookup"><span data-stu-id="91bcf-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="91bcf-184">選取 [MX 記錄] 列中的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-184">Select **Edit** in the MX record row.</span></span> 
    
    ![選取 [MX 記錄] 列中的 [編輯]。](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="91bcf-186">針對其他各筆自訂 MX 記錄，選取 **[資料]** 方塊中的項目，然後按下鍵盤上的 **[刪除]** 鍵來刪除該記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="91bcf-187">繼續作業，直到刪除其他各筆 MX 記錄的 **[資料]** 項目為止。</span><span class="sxs-lookup"><span data-stu-id="91bcf-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![刪除 [資料] 方塊中的專案](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="91bcf-189">當您刪除每一筆其他 MX 記錄的 **[資料]** 項目後，選取 **[儲存]** 以儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="91bcf-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![選取 [儲存]。](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="91bcf-191">新增 Microsoft 所需的5筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="91bcf-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="91bcf-192">若要開始使用，請移至您的 [Google 網域頁面] （https://domains.google.com/registrar) 並登入。</span><span class="sxs-lookup"><span data-stu-id="91bcf-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="91bcf-193">在 **[網域]** 頁面中的 **[網域]** 章節，針對您想要編輯的網域，選取 **[設定 DNS]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="91bcf-194">新增第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="91bcf-195">在 [Custom resource records] (自訂資源記錄)\*\*\*\* 區段，於新記錄的方塊中輸入或複製貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="91bcf-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="91bcf-196">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="91bcf-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="91bcf-197">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="91bcf-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="91bcf-198">**Name**</span><span class="sxs-lookup"><span data-stu-id="91bcf-198">**Name**</span></span>|<span data-ttu-id="91bcf-199">**類型**</span><span class="sxs-lookup"><span data-stu-id="91bcf-199">**Type**</span></span>|<span data-ttu-id="91bcf-200">**TTL**</span><span class="sxs-lookup"><span data-stu-id="91bcf-200">**TTL**</span></span>|<span data-ttu-id="91bcf-201">**資料**</span><span class="sxs-lookup"><span data-stu-id="91bcf-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="91bcf-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="91bcf-202">autodiscover</span></span>  <br/> |<span data-ttu-id="91bcf-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="91bcf-203">CNAME</span></span>  <br/> |<span data-ttu-id="91bcf-204">1H</span><span class="sxs-lookup"><span data-stu-id="91bcf-204">1H</span></span>  <br/> |<span data-ttu-id="91bcf-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="91bcf-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="91bcf-206">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="91bcf-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="91bcf-207">sip</span><span class="sxs-lookup"><span data-stu-id="91bcf-207">sip</span></span>  <br/> |<span data-ttu-id="91bcf-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="91bcf-208">CNAME</span></span>  <br/> |<span data-ttu-id="91bcf-209">1H</span><span class="sxs-lookup"><span data-stu-id="91bcf-209">1H</span></span>  <br/> |<span data-ttu-id="91bcf-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="91bcf-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="91bcf-211">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="91bcf-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="91bcf-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="91bcf-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="91bcf-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="91bcf-213">CNAME</span></span>  <br/> |<span data-ttu-id="91bcf-214">1H</span><span class="sxs-lookup"><span data-stu-id="91bcf-214">1H</span></span>  <br/> |<span data-ttu-id="91bcf-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="91bcf-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="91bcf-216">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="91bcf-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="91bcf-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="91bcf-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="91bcf-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="91bcf-218">CNAME</span></span>  <br/> |<span data-ttu-id="91bcf-219">1H</span><span class="sxs-lookup"><span data-stu-id="91bcf-219">1H</span></span>  <br/> |<span data-ttu-id="91bcf-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="91bcf-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="91bcf-221">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="91bcf-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="91bcf-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="91bcf-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="91bcf-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="91bcf-223">CNAME</span></span>  <br/> |<span data-ttu-id="91bcf-224">1H</span><span class="sxs-lookup"><span data-stu-id="91bcf-224">1H</span></span>  <br/> |<span data-ttu-id="91bcf-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="91bcf-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="91bcf-226">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="91bcf-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![在 [自訂資源記錄] 區段中輸入或貼上值](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="91bcf-228">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-228">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="91bcf-230">新增其他四筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="91bcf-231">在 **[自訂資源記錄]** 區段中，使用表格中下一列的值來建立記錄，然後再選取一次 **[新增]** 以完成該筆記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="91bcf-232">重複這個程序，直到所有要求的 CNAME 記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="91bcf-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="91bcf-233">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="91bcf-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91bcf-234">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="91bcf-235">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="91bcf-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="91bcf-236">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="91bcf-237">而是，請將必要的 Microsoft 值新增到目前的記錄，以便擁有包含這兩組值的單一 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="91bcf-238">需要範例？</span><span class="sxs-lookup"><span data-stu-id="91bcf-238">Need examples?</span></span> <span data-ttu-id="91bcf-239">請參閱這些 [Microsoft 的外部網域名稱系統記錄](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="91bcf-239">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="91bcf-240">若要驗證您的 SPF 記錄，您可以使用其中一種 [SPF 驗證工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="91bcf-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="91bcf-241">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="91bcf-241">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="91bcf-242">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="91bcf-242">You'll be prompted to sign in.</span></span> <span data-ttu-id="91bcf-243">To do so:</span><span class="sxs-lookup"><span data-stu-id="91bcf-243">To do so:</span></span>
    
1. <span data-ttu-id="91bcf-244">選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="91bcf-245">輸入您的登入認證，然後再次選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="91bcf-246">在 **[網域]** 頁面中的 **[網域]** 章節，針對您想要編輯的網域，選取 **[設定 DNS]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="91bcf-247">在 **[自訂資源記錄]** 區段中的 TXT記錄列上，選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="91bcf-248">Google Domains 會將 TXT 記錄儲存為一組可包含多個記錄的集合。</span><span class="sxs-lookup"><span data-stu-id="91bcf-248">Google Domains stores TXT records as a set that may contain multiple records.</span></span> <span data-ttu-id="91bcf-249">當您有至少一個其他的 TXT 記錄時 (例如用於驗證網域的 TXT 記錄)，您必須新增 TXT 新記錄到該記錄集。</span><span class="sxs-lookup"><span data-stu-id="91bcf-249">When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set.</span></span> <span data-ttu-id="91bcf-250">任何嘗試輸入額外 TXT 記錄做為不同項目，會導致 **「重複記錄」** 錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="91bcf-250">Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![選取 TXT 記錄列中的 [編輯]](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="91bcf-252">選取 **[+]** 控制項。 </span><span class="sxs-lookup"><span data-stu-id="91bcf-252">Select the **(+)** control.</span></span> 
    
    ![選取加號控制項](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="91bcf-254">在新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="91bcf-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="91bcf-255">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="91bcf-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="91bcf-256">**資料**</span><span class="sxs-lookup"><span data-stu-id="91bcf-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="91bcf-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="91bcf-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="91bcf-258">建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="91bcf-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![在 [自訂資源記錄] 區段中輸入或貼上值](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="91bcf-260">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-260">Select **Save**.</span></span>
    
    ![選取 [儲存]。](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="91bcf-262">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="91bcf-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="91bcf-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="91bcf-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="91bcf-264">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="91bcf-264">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="91bcf-265">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="91bcf-265">You'll be prompted to sign in.</span></span> <span data-ttu-id="91bcf-266">To do so:</span><span class="sxs-lookup"><span data-stu-id="91bcf-266">To do so:</span></span>
    
2. <span data-ttu-id="91bcf-267">選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="91bcf-268">輸入您的登入認證，然後再次選取 **[登入]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="91bcf-269">在 **[網域]** 頁面中的 **[網域]** 章節，針對您想要編輯的網域，選取 **[設定 DNS]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="91bcf-270">新增第一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="91bcf-271">在 [自訂資源記錄]  區段，於新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="91bcf-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="91bcf-272">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="91bcf-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="91bcf-273">(從下拉式清單中選擇 [Type] (類型) 值。)</span><span class="sxs-lookup"><span data-stu-id="91bcf-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="91bcf-274">**Name**</span><span class="sxs-lookup"><span data-stu-id="91bcf-274">**Name**</span></span>|<span data-ttu-id="91bcf-275">**類型**</span><span class="sxs-lookup"><span data-stu-id="91bcf-275">**Type**</span></span>|<span data-ttu-id="91bcf-276">**TTL**</span><span class="sxs-lookup"><span data-stu-id="91bcf-276">**TTL**</span></span>|<span data-ttu-id="91bcf-277">**資料**</span><span class="sxs-lookup"><span data-stu-id="91bcf-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="91bcf-278">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="91bcf-278">_sip._tls</span></span>|<span data-ttu-id="91bcf-279">SRV</span><span class="sxs-lookup"><span data-stu-id="91bcf-279">SRV</span></span>|<span data-ttu-id="91bcf-280">1H</span><span class="sxs-lookup"><span data-stu-id="91bcf-280">1H</span></span>|<span data-ttu-id="91bcf-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="91bcf-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="91bcf-282">**此值必須以英文句點 (.) 結尾** **注意:** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="91bcf-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="91bcf-283">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="91bcf-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="91bcf-284">SRV</span><span class="sxs-lookup"><span data-stu-id="91bcf-284">SRV</span></span>|<span data-ttu-id="91bcf-285">1H</span><span class="sxs-lookup"><span data-stu-id="91bcf-285">1H</span></span>|<span data-ttu-id="91bcf-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="91bcf-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="91bcf-287">**此值必須以英文句點 (.) 結尾。**</span><span class="sxs-lookup"><span data-stu-id="91bcf-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="91bcf-288">建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="91bcf-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![在 [自訂資源記錄] 區段中輸入或貼上值](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="91bcf-290">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="91bcf-290">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="91bcf-292">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="91bcf-293">在 **[自訂資源記錄]** 區段中，使用表格中第二列的值來建立記錄，然後再選取一次 **[新增]** 以完成該筆記錄。</span><span class="sxs-lookup"><span data-stu-id="91bcf-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="91bcf-294">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="91bcf-294">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="91bcf-295">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="91bcf-295">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="91bcf-296">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="91bcf-296">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
