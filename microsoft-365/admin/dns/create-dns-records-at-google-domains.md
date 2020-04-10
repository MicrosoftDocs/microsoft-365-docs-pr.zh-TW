---
title: 在 Google Domains 建立 Office 365 的 DNS 記錄
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: 瞭解如何驗證您的網域，以及如何設定適用于 Office 365 之 Google 網域的電子郵件、Lync 及其他服務的 DNS 記錄。
ms.openlocfilehash: f0a9a42127fc5b722679013b899255f77840d670
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211724"
---
# <a name="create-dns-records-at-google-domains-for-office-365"></a><span data-ttu-id="48328-103">在 Google Domains 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="48328-103">Create DNS records at Google Domains for Office 365</span></span>

 <span data-ttu-id="48328-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="48328-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="48328-105">如果 Google Domains 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並設定電子郵件與 Lync 等項目的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="48328-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="48328-106">在 Google Domains 新增這些記錄之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="48328-106">After you add these records at Google Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="48328-107">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="48328-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="48328-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="48328-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="48328-109">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="48328-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="48328-110">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="48328-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="48328-111">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="48328-111">Add a TXT record for verification</span></span>
<span data-ttu-id="48328-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="48328-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="48328-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="48328-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48328-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="48328-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="48328-p104">首先請用[這個連結](https://domains.google.com/registrar)移至 Google Domains 上您的網域頁面。系統會提示您登入。若要執行此作業，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="48328-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="48328-120">選取 [登**入**]。</span><span class="sxs-lookup"><span data-stu-id="48328-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="48328-121">輸入您的登入認證，然後再選取 [登**入**]。</span><span class="sxs-lookup"><span data-stu-id="48328-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="48328-122">在 [**我的網域**] 頁面上，尋找您要與 Office 365 搭配使用的網域，然後選取它旁邊的 [**管理**] 連結。</span><span class="sxs-lookup"><span data-stu-id="48328-122">On the **My domains** page, find the domain you want to use with Office 365, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="48328-123">在左側導覽中，選取 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="48328-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="48328-124">在 [自訂資源記錄] （\*）區段的新記錄方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="48328-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="48328-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="48328-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="48328-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="48328-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="48328-127">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48328-127">**Name**</span></span> <br/> |<span data-ttu-id="48328-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="48328-128">**Type**</span></span> <br/> |<span data-ttu-id="48328-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48328-129">**TTL**</span></span> <br/> |<span data-ttu-id="48328-130">**資料**</span><span class="sxs-lookup"><span data-stu-id="48328-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="48328-131">TXT</span><span class="sxs-lookup"><span data-stu-id="48328-131">TXT</span></span>  <br/> |<span data-ttu-id="48328-132">1H</span><span class="sxs-lookup"><span data-stu-id="48328-132">1H</span></span>  <br/> |<span data-ttu-id="48328-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="48328-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="48328-134">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="48328-134">**Note:** This is an example.</span></span> <span data-ttu-id="48328-135">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="48328-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="48328-136">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="48328-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="48328-137">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="48328-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="48328-138">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="48328-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="48328-139">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="48328-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="48328-140">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="48328-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="48328-141">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="48328-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="48328-142">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="48328-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="48328-143">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="48328-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="48328-144">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="48328-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="48328-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="48328-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="48328-146">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="48328-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="48328-147">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="48328-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="48328-148">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="48328-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="48328-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="48328-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="48328-p108">首先請用[這個連結](https://domains.google.com/registrar)移至 Google Domains 上您的網域頁面。系統會提示您登入。若要執行此作業，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="48328-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="48328-153">選取 [登**入**]。</span><span class="sxs-lookup"><span data-stu-id="48328-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="48328-154">輸入您的登入認證，然後再選取 [登**入**]。</span><span class="sxs-lookup"><span data-stu-id="48328-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="48328-155">在 [**網域**] 頁面上的 [**網域**] 區段中，針對您要編輯的網域選取 [**設定 DNS** ]。</span><span class="sxs-lookup"><span data-stu-id="48328-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="48328-p109">如果您擁有 G Suite 電子郵件帳戶，則必須先刪除與該帳戶相關聯的 MX 記錄。G Suite 的 MX 記錄會使您無法新增其他 MX 記錄，包括 Office 365 所需的記錄。請注意，刪除 G Suite 記錄並不會刪除您的 G Suite 帳戶。若要刪除您的 G Suite MX 記錄，請依照下列步驟操作。</span><span class="sxs-lookup"><span data-stu-id="48328-p109">If you have a G Suite email account, you must first delete the MX records associated with that account. The G Suite MX records prevent you from adding any other MX records, including those required for Office 365. Note that deleting the G Suite records does not delete your G Suite account. To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="48328-160">在 [**綜合記錄**] 區段的 [ **G Suite** ] 區域中，選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="48328-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="48328-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="48328-161">(You may have to scroll down.)</span></span>
    
    ![在 [綜合記錄] 區段中，選取 [刪除]](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="48328-163">選取 [刪除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="48328-163">Select **Delete**.</span></span>
    
    ![選取 [刪除]](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="48328-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="48328-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="48328-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="48328-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="48328-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="48328-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="48328-168">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48328-168">**Name**</span></span>|<span data-ttu-id="48328-169">**Type**</span><span class="sxs-lookup"><span data-stu-id="48328-169">**Type**</span></span>|<span data-ttu-id="48328-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48328-170">**TTL**</span></span>|<span data-ttu-id="48328-171">**資料**</span><span class="sxs-lookup"><span data-stu-id="48328-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="48328-172">MX</span><span class="sxs-lookup"><span data-stu-id="48328-172">MX</span></span>  <br/> |<span data-ttu-id="48328-173">1H</span><span class="sxs-lookup"><span data-stu-id="48328-173">1H</span></span>  <br/> |<span data-ttu-id="48328-174">0  *\<網域金鑰\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="48328-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="48328-175">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="48328-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="48328-176">**0**是 MX 優先順序值。</span><span class="sxs-lookup"><span data-stu-id="48328-176">The **0** is the MX priority value.</span></span> <span data-ttu-id="48328-177">請將它新增到 MX 值的開頭，並以空格分隔該值的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="48328-177">Add it to the beginning of the MX value, separated from the remainder of the value by a space.</span></span>  <br/> <span data-ttu-id="48328-178">**注意：** 從您的 Office 365 帳戶取得您的\<*網域金鑰*\>。</span><span class="sxs-lookup"><span data-stu-id="48328-178">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span>  [<span data-ttu-id="48328-179">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="48328-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="48328-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="48328-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![在自訂資源記錄區段中輸入或貼上值](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="48328-182">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="48328-182">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="48328-184">如果有任何其他的自訂 MX 記錄，請移除它們。</span><span class="sxs-lookup"><span data-stu-id="48328-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="48328-185">在 [MX 記錄] 列中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="48328-185">Select **Edit** in the MX record row.</span></span> 
    
    ![在 [MX 記錄] 資料列中，選取 [編輯]](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="48328-187">針對每個其他自訂 MX 記錄，選取 [**資料**] 方塊中的專案，然後按下鍵盤上的**Delete**鍵，以刪除該記錄。</span><span class="sxs-lookup"><span data-stu-id="48328-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="48328-188">繼續執行，直到您刪除每個其他 MX 記錄的**資料**輸入為止。</span><span class="sxs-lookup"><span data-stu-id="48328-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="48328-190">當您已刪除每個其他 MX 記錄的**資料**輸入時，請選取 [**儲存**] 以儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="48328-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![選取 [儲存]](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="48328-192">新增 Office 365 所需的五個 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="48328-192">Add the five CNAME records that are required for Office 365</span></span>

1. <span data-ttu-id="48328-193">若要開始，請移至 [Google 網域] 頁面]https://domains.google.com/registrar) （並登入。</span><span class="sxs-lookup"><span data-stu-id="48328-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="48328-194">在 [**網域**] 頁面上的 [**網域**] 區段中，針對您要編輯的網域選取 [**設定 DNS** ]。</span><span class="sxs-lookup"><span data-stu-id="48328-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="48328-195">新增第一筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="48328-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="48328-196">在 [**自訂資源記錄**] 區段的新記錄方塊中，輸入或複製並貼上下表第一列中的值。</span><span class="sxs-lookup"><span data-stu-id="48328-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="48328-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="48328-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="48328-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="48328-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="48328-199">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48328-199">**Name**</span></span>|<span data-ttu-id="48328-200">**Type**</span><span class="sxs-lookup"><span data-stu-id="48328-200">**Type**</span></span>|<span data-ttu-id="48328-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48328-201">**TTL**</span></span>|<span data-ttu-id="48328-202">**資料**</span><span class="sxs-lookup"><span data-stu-id="48328-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="48328-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="48328-203">autodiscover</span></span>  <br/> |<span data-ttu-id="48328-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="48328-204">CNAME</span></span>  <br/> |<span data-ttu-id="48328-205">1H</span><span class="sxs-lookup"><span data-stu-id="48328-205">1H</span></span>  <br/> |<span data-ttu-id="48328-206">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="48328-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="48328-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="48328-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48328-208">sip</span><span class="sxs-lookup"><span data-stu-id="48328-208">sip</span></span>  <br/> |<span data-ttu-id="48328-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="48328-209">CNAME</span></span>  <br/> |<span data-ttu-id="48328-210">1H</span><span class="sxs-lookup"><span data-stu-id="48328-210">1H</span></span>  <br/> |<span data-ttu-id="48328-211">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="48328-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="48328-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="48328-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48328-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="48328-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="48328-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="48328-214">CNAME</span></span>  <br/> |<span data-ttu-id="48328-215">1H</span><span class="sxs-lookup"><span data-stu-id="48328-215">1H</span></span>  <br/> |<span data-ttu-id="48328-216">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="48328-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="48328-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="48328-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48328-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="48328-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="48328-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="48328-219">CNAME</span></span>  <br/> |<span data-ttu-id="48328-220">1H</span><span class="sxs-lookup"><span data-stu-id="48328-220">1H</span></span>  <br/> |<span data-ttu-id="48328-221">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="48328-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="48328-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="48328-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="48328-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="48328-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="48328-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="48328-224">CNAME</span></span>  <br/> |<span data-ttu-id="48328-225">1H</span><span class="sxs-lookup"><span data-stu-id="48328-225">1H</span></span>  <br/> |<span data-ttu-id="48328-226">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="48328-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="48328-227">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="48328-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![在自訂資源記錄區段中輸入或貼上值](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="48328-229">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="48328-229">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="48328-231">新增其他四筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="48328-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="48328-232">在 [**自訂資源記錄**] 區段中，使用表格中下一列的值來建立記錄，然後再選取 [**新增**] 以完成該記錄。</span><span class="sxs-lookup"><span data-stu-id="48328-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="48328-233">重複此程式，直到您已建立所有必要的 CNAME 記錄為止。</span><span class="sxs-lookup"><span data-stu-id="48328-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="48328-234">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="48328-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48328-235">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="48328-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="48328-236">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="48328-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="48328-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="48328-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="48328-238">而是，請將必要的 Office 365 值新增至目前的記錄，以便擁有包含這兩組值的單一 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="48328-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="48328-239">需要範例？</span><span class="sxs-lookup"><span data-stu-id="48328-239">Need examples?</span></span> <span data-ttu-id="48328-240">請參閱這些 [Office 365 的外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="48328-240">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="48328-241">若要驗證您的 SPF 記錄，您可以使用其中一種 [SPF 驗證工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="48328-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="48328-p113">首先請用[這個連結](https://domains.google.com/registrar)移至 Google Domains 上您的網域頁面。系統會提示您登入。若要執行此作業，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="48328-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="48328-245">選取 [登**入**]。</span><span class="sxs-lookup"><span data-stu-id="48328-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="48328-246">輸入您的登入認證，然後再選取 [登**入**]。</span><span class="sxs-lookup"><span data-stu-id="48328-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="48328-247">在 [**網域**] 頁面上的 [**網域**] 區段中，針對您要編輯的網域選取 [**設定 DNS** ]。</span><span class="sxs-lookup"><span data-stu-id="48328-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="48328-248">在 [**自訂資源記錄**] 區段的 [TXT 記錄] 列中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="48328-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="48328-249">Google Domains 會將 TXT 記錄儲存為一組可包含多個記錄的集合。</span><span class="sxs-lookup"><span data-stu-id="48328-249">Google Domains stores TXT records as a set that may contain multiple records.</span></span> <span data-ttu-id="48328-250">當您有至少一個其他的 TXT 記錄時 (例如用於驗證網域的 TXT 記錄)，您必須新增 TXT 新記錄到該記錄集。</span><span class="sxs-lookup"><span data-stu-id="48328-250">When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set.</span></span> <span data-ttu-id="48328-251">任何嘗試輸入其他 TXT 記錄做為個別專案會產生重複的**記錄**錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="48328-251">Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![在 TXT 記錄列中選取 [編輯]](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="48328-253">選取 **（+）** 控制項。</span><span class="sxs-lookup"><span data-stu-id="48328-253">Select the **(+)** control.</span></span> 
    
    ![選取加號控制項](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="48328-255">在每一筆新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="48328-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="48328-256">(您可能需要向下捲動。)</span><span class="sxs-lookup"><span data-stu-id="48328-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="48328-257">**資料**</span><span class="sxs-lookup"><span data-stu-id="48328-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="48328-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="48328-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="48328-259">建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="48328-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![在自訂資源記錄區段中輸入或貼上值](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="48328-261">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="48328-261">Select **Save**.</span></span>
    
    ![選取 [儲存]](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="48328-263">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="48328-263">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="48328-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="48328-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="48328-p115">首先請用[這個連結](https://domains.google.com/registrar)移至 Google Domains 上您的網域頁面。系統會提示您登入。若要執行此作業，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="48328-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="48328-268">選取 [登**入**]。</span><span class="sxs-lookup"><span data-stu-id="48328-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="48328-269">輸入您的登入認證，然後再選取 [登**入**]。</span><span class="sxs-lookup"><span data-stu-id="48328-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="48328-270">在 [**網域**] 頁面上的 [**網域**] 區段中，針對您要編輯的網域選取 [**設定 DNS** ]。</span><span class="sxs-lookup"><span data-stu-id="48328-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="48328-271">新增第一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="48328-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="48328-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="48328-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="48328-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="48328-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="48328-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="48328-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="48328-275">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48328-275">**Name**</span></span>|<span data-ttu-id="48328-276">**Type**</span><span class="sxs-lookup"><span data-stu-id="48328-276">**Type**</span></span>|<span data-ttu-id="48328-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="48328-277">**TTL**</span></span>|<span data-ttu-id="48328-278">**資料**</span><span class="sxs-lookup"><span data-stu-id="48328-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="48328-279">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="48328-279">_sip._tls</span></span>|<span data-ttu-id="48328-280">SRV</span><span class="sxs-lookup"><span data-stu-id="48328-280">SRV</span></span>|<span data-ttu-id="48328-281">1H</span><span class="sxs-lookup"><span data-stu-id="48328-281">1H</span></span>|<span data-ttu-id="48328-282">100 1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="48328-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="48328-283">**此值必須以句點（.）結尾\*\*\*\*附注：** 建議您複製並貼上此專案，讓所有的間距都保持正確。</span><span class="sxs-lookup"><span data-stu-id="48328-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="48328-284">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="48328-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="48328-285">SRV</span><span class="sxs-lookup"><span data-stu-id="48328-285">SRV</span></span>|<span data-ttu-id="48328-286">1H</span><span class="sxs-lookup"><span data-stu-id="48328-286">1H</span></span>|<span data-ttu-id="48328-287">100 1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="48328-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="48328-288">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="48328-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="48328-289">建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="48328-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![在自訂資源記錄區段中輸入或貼上值](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="48328-291">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="48328-291">Select **Add**.</span></span>
    
    ![選取 [新增]](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="48328-293">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="48328-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="48328-294">在 [**自訂資源記錄**] 區段中，使用表格中第二列的值來建立記錄，然後再選取 [**新增**] 以完成該記錄。</span><span class="sxs-lookup"><span data-stu-id="48328-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="48328-295">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="48328-295">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="48328-296">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="48328-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="48328-297">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="48328-297">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
