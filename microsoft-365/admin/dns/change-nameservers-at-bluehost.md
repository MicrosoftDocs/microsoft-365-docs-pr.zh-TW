---
title: 使用 Bluehost 變更名稱伺服器以設定 Office 365
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: '了解如何設定 Office 365 來管理您的 DNS 記錄，在 Bluehost。 '
ms.openlocfilehash: 081abe977b498ea0cc0a0e2da9b54b00687df530
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352374"
---
# <a name="change-nameservers-to-set-up-office-365-with-bluehost"></a><span data-ttu-id="049eb-103">使用 Bluehost 變更名稱伺服器以設定 Office 365</span><span class="sxs-lookup"><span data-stu-id="049eb-103">Change nameservers to set up Office 365 with Bluehost</span></span>

 <span data-ttu-id="049eb-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="049eb-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="049eb-p101">如果您希望 Office 365 為您管理 Office 365 DNS 記錄，請按照下列指示進行。(您可視需要[在 Bluehost 管理所有 Office 365 DNS 記錄](create-dns-records-at-bluehost.md)。)</span><span class="sxs-lookup"><span data-stu-id="049eb-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="049eb-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="049eb-107">Add a TXT record for verification</span></span>

<span data-ttu-id="049eb-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="049eb-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="049eb-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="049eb-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="049eb-112">首先請用[這個連結](https://my.bluehost.com/cgi/dm)移至 Bluehost 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="049eb-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="049eb-113">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="049eb-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="049eb-114">在 [**網域**] 頁面上，在 [**網域**] 區域中，尋找您要變更，網域列，然後選取該網域的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="049eb-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="049eb-115">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="049eb-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="049eb-116">在**domain_name**區域中，在 [ **DNS 區域編輯器**] 列中，選取 [**管理 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="049eb-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="049eb-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="049eb-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="049eb-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="049eb-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="049eb-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="049eb-119">**Host Record**</span></span> <br/> |<span data-ttu-id="049eb-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="049eb-120">**TTL**</span></span> <br/> |<span data-ttu-id="049eb-121">**類型**</span><span class="sxs-lookup"><span data-stu-id="049eb-121">**Type**</span></span> <br/> |<span data-ttu-id="049eb-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="049eb-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="049eb-123">14400</span><span class="sxs-lookup"><span data-stu-id="049eb-123">14400</span></span>  <br/> |<span data-ttu-id="049eb-124">TXT</span><span class="sxs-lookup"><span data-stu-id="049eb-124">TXT</span></span>  <br/> |<span data-ttu-id="049eb-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="049eb-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="049eb-126">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="049eb-126">**Note:** This is an example.</span></span> <span data-ttu-id="049eb-127">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="049eb-127">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="049eb-128">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="049eb-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="049eb-129">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="049eb-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="049eb-130">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="049eb-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="049eb-131">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="049eb-131">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="049eb-132">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="049eb-132">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="049eb-133">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="049eb-133">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="049eb-134">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="049eb-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="049eb-135">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="049eb-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="049eb-136">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="049eb-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="049eb-137">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="049eb-137">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="049eb-138">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="049eb-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="049eb-139">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="049eb-139">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="049eb-140">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="049eb-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="049eb-p107">如要完成網域設定以用於 Office 365，請在您的網域註冊機構更改網域的 NS 記錄，使它指向 Office 365 主要和次要名稱伺服器。這樣就會設定並讓 Office 365 為您更新網域的 DNS 記錄。我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="049eb-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="049eb-p108">當您變更網域的 NS 記錄以指向 Office 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。例如，在您完成這項變更之後，凡是傳送到您的網域 (例如 rob@ *your_domain*  .com) 的電子郵件都將開始傳送到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="049eb-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="049eb-146">下列程序將告訴您如何從清單中，刪除任何其他不想要的名稱以及 how to： 新增如果他們沒有 」 列出正確的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="049eb-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="049eb-147">當您完成在此區段中，應該會列出的唯一名稱伺服器的步驟 > 是這四個: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="049eb-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="049eb-148">首先請用[這個連結](https://my.bluehost.com/cgi/dm)移至 Bluehost 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="049eb-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="049eb-149">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="049eb-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="049eb-150">在 [**網域**] 頁面的**domain_name**區域中，選取您網域的核取方塊，然後選取**名稱伺服器**。</span><span class="sxs-lookup"><span data-stu-id="049eb-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="049eb-152">在**domain_name**區域中，選取 [**使用自訂名稱伺服器**。</span><span class="sxs-lookup"><span data-stu-id="049eb-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="049eb-154">請根據現在顯示頁面上是否列出名稱伺服器，來選擇下列兩個程序其中一項繼續︰</span><span class="sxs-lookup"><span data-stu-id="049eb-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="049eb-155">如果有**無**列 」 名稱伺服器，[如果有列出名稱伺服器](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="049eb-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="049eb-156">如果**是**那里 」 列出名稱伺服器，[如果有列出名稱伺服器](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="049eb-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="049eb-157">如果列表上「沒有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="049eb-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="049eb-158">在 [**使用自訂名稱伺服器**] 區段中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="049eb-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="049eb-159">**第一個空白列**</span><span class="sxs-lookup"><span data-stu-id="049eb-159">**First empty row**</span></span> <br/> |<span data-ttu-id="049eb-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="049eb-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="049eb-161">**第二個空白列**</span><span class="sxs-lookup"><span data-stu-id="049eb-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="049eb-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="049eb-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="049eb-164">選取 [**新增資料列**。</span><span class="sxs-lookup"><span data-stu-id="049eb-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="049eb-166">仍在**使用自訂名稱伺服器**] 區段中，輸入或複製並貼上下表第一列中的值到新的空白列。</span><span class="sxs-lookup"><span data-stu-id="049eb-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="049eb-167">**第三個空白列**</span><span class="sxs-lookup"><span data-stu-id="049eb-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="049eb-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="049eb-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="049eb-169">**第四個空白列**</span><span class="sxs-lookup"><span data-stu-id="049eb-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="049eb-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="049eb-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. <span data-ttu-id="049eb-171">若要新增第四筆名稱伺服器記錄，再選取 [**新增資料列**，並使用上述表格的最後一列中的值建立記錄。</span><span class="sxs-lookup"><span data-stu-id="049eb-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="049eb-172">選取 [**儲存名稱伺服器設定**]。</span><span class="sxs-lookup"><span data-stu-id="049eb-172">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="049eb-p111">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="049eb-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="049eb-176">如果列表上「有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="049eb-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="049eb-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="049eb-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="049eb-178">(也就是刪除只是任何目前的名稱*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**。)</span><span class="sxs-lookup"><span data-stu-id="049eb-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="049eb-179">如果沒有列出任何其他名稱伺服器，則選取它，然後按鍵盤上的**Delete**鍵逐一刪除。</span><span class="sxs-lookup"><span data-stu-id="049eb-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="049eb-181">同樣在 [**使用自訂名稱伺服器**] 區段中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="049eb-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="049eb-182">**第一個空白列**</span><span class="sxs-lookup"><span data-stu-id="049eb-182">**First empty row**</span></span> <br/> |<span data-ttu-id="049eb-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="049eb-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="049eb-184">**第二個空白列**</span><span class="sxs-lookup"><span data-stu-id="049eb-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="049eb-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="049eb-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-DYN-BP-CONFIGURE-1-重新委派-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="049eb-187">選取 [**新增資料列**。</span><span class="sxs-lookup"><span data-stu-id="049eb-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="049eb-189">仍在**使用自訂名稱伺服器**] 區段中，輸入或複製並貼上下表第一列中的值到新的空白列。</span><span class="sxs-lookup"><span data-stu-id="049eb-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="049eb-190">**第三個空白列**</span><span class="sxs-lookup"><span data-stu-id="049eb-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="049eb-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="049eb-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="049eb-192">**第四個空白列**</span><span class="sxs-lookup"><span data-stu-id="049eb-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="049eb-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="049eb-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="049eb-195">若要新增第四筆名稱伺服器記錄，再選取 [**新增資料列**，並使用上述表格的最後一列中的值建立記錄。</span><span class="sxs-lookup"><span data-stu-id="049eb-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="049eb-196">選取 [**儲存名稱伺服器設定**]。</span><span class="sxs-lookup"><span data-stu-id="049eb-196">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="049eb-p113">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="049eb-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
