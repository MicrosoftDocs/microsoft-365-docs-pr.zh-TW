---
title: 使用 Bluehost 變更名稱伺服器以設定 Microsoft
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: '瞭解如何設定 Microsoft 以在 Bluehost 管理您的 DNS 記錄。 '
ms.openlocfilehash: 63084b35c3f0d71764bca1995f25d7c6f0842a86
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629908"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a><span data-ttu-id="dba57-103">使用 Bluehost 變更名稱伺服器以設定 Microsoft</span><span class="sxs-lookup"><span data-stu-id="dba57-103">Change nameservers to set up Microsoft with Bluehost</span></span>

 <span data-ttu-id="dba57-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="dba57-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="dba57-105">如果您想讓 Microsoft 為您管理您的 DNS 記錄，請遵循下列指示。</span><span class="sxs-lookup"><span data-stu-id="dba57-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="dba57-106">（如果您願意，您可以[管理 Bluehost 中的所有 DNS 記錄](create-dns-records-at-bluehost.md)。）</span><span class="sxs-lookup"><span data-stu-id="dba57-106">(If you prefer, you can [manage all your DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="dba57-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="dba57-107">Add a TXT record for verification</span></span>

<span data-ttu-id="dba57-108">在將您的網域與 Microsoft 搭配使用之前，我們必須先確認您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="dba57-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="dba57-109">您能夠在您的網域註冊機構登入您的帳戶，並為您擁有網域的 Microsoft 建立 DNS 記錄證明。</span><span class="sxs-lookup"><span data-stu-id="dba57-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dba57-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="dba57-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="dba57-112">首先請用[這個連結](https://my.bluehost.com/cgi/dm)移至 Bluehost 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="dba57-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="dba57-113">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dba57-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="dba57-114">在 [**網域**] 頁面的 [**網域**] 區域中，尋找您要變更之網域的列，然後選取該網域的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dba57-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="dba57-115">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dba57-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="dba57-116">在 [ **domain_name** ] 區域的 [ **DNS 區域編輯器**] 列中，選取 [**管理 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dba57-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="dba57-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="dba57-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="dba57-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="dba57-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dba57-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="dba57-119">**Host Record**</span></span> <br/> |<span data-ttu-id="dba57-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dba57-120">**TTL**</span></span> <br/> |<span data-ttu-id="dba57-121">**類型**</span><span class="sxs-lookup"><span data-stu-id="dba57-121">**Type**</span></span> <br/> |<span data-ttu-id="dba57-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="dba57-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="dba57-123">14400</span><span class="sxs-lookup"><span data-stu-id="dba57-123">14400</span></span>  <br/> |<span data-ttu-id="dba57-124">TXT</span><span class="sxs-lookup"><span data-stu-id="dba57-124">TXT</span></span>  <br/> |<span data-ttu-id="dba57-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="dba57-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="dba57-126">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="dba57-126">**Note:** This is an example.</span></span> <span data-ttu-id="dba57-127">從表格中，使用您的特定**目的地或指向位址**值。</span><span class="sxs-lookup"><span data-stu-id="dba57-127">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="dba57-128">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="dba57-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="dba57-129">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="dba57-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="dba57-130">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="dba57-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="dba57-131">現在，您已在網域註冊機構的網站上新增記錄，您會回到 Microsoft 並要求搜尋該記錄。</span><span class="sxs-lookup"><span data-stu-id="dba57-131">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="dba57-132">當 Microsoft 找到正確的 TXT 記錄後，您的網域就會經過驗證。</span><span class="sxs-lookup"><span data-stu-id="dba57-132">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="dba57-133">在 Microsoft 系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="dba57-133">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="dba57-134">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="dba57-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="dba57-135">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="dba57-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="dba57-136">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dba57-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dba57-137">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="dba57-137">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="dba57-138">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="dba57-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="dba57-139">如果您在新增 DNS 記錄後遇到郵件流程或其他問題的問題，請參閱[尋找並修正新增您的網域或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dba57-139">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="dba57-140">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="dba57-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="dba57-141">若要使用 Microsoft 設定您的網域，請在您的網域註冊機構變更網域的 NS 記錄，以指向主要和次要名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="dba57-141">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the  primary and secondary name servers.</span></span> <span data-ttu-id="dba57-142">這會將 Microsoft 設定為您為您更新網域的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="dba57-142">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="dba57-143">我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="dba57-143">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="dba57-144">當您將網域的 NS 記錄變更為指向 Microsoft 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。</span><span class="sxs-lookup"><span data-stu-id="dba57-144">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="dba57-145">例如，在您進行此變更之後，所有傳送至您網域的電子郵件（如 rob@ *your_domain* .com）都會開始向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="dba57-145">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="dba57-146">下列程式將告訴您如何刪除清單中的任何其他、不想要的名稱伺服器，以及如何新增正確的名稱伺服器（如果尚未列出）。</span><span class="sxs-lookup"><span data-stu-id="dba57-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="dba57-147">> 完成本節中的步驟之後，應該會列出的唯一名稱伺服器為下列四種： > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dba57-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="dba57-148">首先請用[這個連結](https://my.bluehost.com/cgi/dm)移至 Bluehost 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="dba57-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="dba57-149">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="dba57-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="dba57-150">在 [**網域**] 頁面上的 [ **domain_name** ] 區域中，選取您網域的核取方塊，然後選取 [**名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="dba57-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="dba57-152">在 [ **domain_name** ] 區域中，選取 [**使用自訂名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="dba57-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="dba57-154">請根據現在顯示頁面上是否列出名稱伺服器，來選擇下列兩個程序其中一項繼續︰</span><span class="sxs-lookup"><span data-stu-id="dba57-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="dba57-155">如果沒有列出**任何**名稱伺服器，[則未列出任何名稱伺服器](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="dba57-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="dba57-156">如果已**列出名稱伺服器，** 如果已[列出名稱伺服器](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="dba57-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="dba57-157">如果列表上「沒有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="dba57-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="dba57-158">在 [**使用自訂名稱伺服器**] 區段中，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="dba57-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="dba57-159">**第一個空白列**</span><span class="sxs-lookup"><span data-stu-id="dba57-159">**First empty row**</span></span> <br/> |<span data-ttu-id="dba57-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dba57-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="dba57-161">**第二個空白列**</span><span class="sxs-lookup"><span data-stu-id="dba57-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="dba57-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dba57-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-重新委派-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="dba57-164">選取 [**新增列**]。</span><span class="sxs-lookup"><span data-stu-id="dba57-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="dba57-166">仍在 [**使用自訂名稱伺服器**] 區段中，輸入或複製並貼上下表第一列中的值至新的空白列。</span><span class="sxs-lookup"><span data-stu-id="dba57-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="dba57-167">**第三個空白列**</span><span class="sxs-lookup"><span data-stu-id="dba57-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="dba57-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dba57-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="dba57-169">**第四個空白列**</span><span class="sxs-lookup"><span data-stu-id="dba57-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="dba57-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dba57-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. <span data-ttu-id="dba57-171">若要新增第四個名稱伺服器記錄，請再次選取 [**新增列**]，然後使用上表最後一列的值來建立記錄。</span><span class="sxs-lookup"><span data-stu-id="dba57-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="dba57-172">選取 [儲存名稱伺服器**設定**]。</span><span class="sxs-lookup"><span data-stu-id="dba57-172">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="dba57-174">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。</span><span class="sxs-lookup"><span data-stu-id="dba57-174">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="dba57-175">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="dba57-175">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="dba57-176">如果列表上「有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="dba57-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="dba57-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="dba57-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="dba57-178">（也就是說，只刪除所有*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**的目前名稱伺服器。）</span><span class="sxs-lookup"><span data-stu-id="dba57-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="dba57-179">如果有列出任何其他名稱伺服器，請選取每個伺服器，然後按鍵盤上的**delete**鍵將其刪除。</span><span class="sxs-lookup"><span data-stu-id="dba57-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="dba57-181">仍在 [**使用自訂名稱伺服器**] 區段中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dba57-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="dba57-182">**第一個空白列**</span><span class="sxs-lookup"><span data-stu-id="dba57-182">**First empty row**</span></span> <br/> |<span data-ttu-id="dba57-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dba57-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="dba57-184">**第二個空白列**</span><span class="sxs-lookup"><span data-stu-id="dba57-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="dba57-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dba57-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-重新委派-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="dba57-187">選取 [**新增列**]。</span><span class="sxs-lookup"><span data-stu-id="dba57-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="dba57-189">仍在 [**使用自訂名稱伺服器**] 區段中，輸入或複製並貼上下表第一列中的值至新的空白列。</span><span class="sxs-lookup"><span data-stu-id="dba57-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="dba57-190">**第三個空白列**</span><span class="sxs-lookup"><span data-stu-id="dba57-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="dba57-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dba57-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="dba57-192">**第四個空白列**</span><span class="sxs-lookup"><span data-stu-id="dba57-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="dba57-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dba57-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-重新委派-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="dba57-195">若要新增第四個名稱伺服器記錄，請再次選取 [**新增列**]，然後使用上表最後一列的值來建立記錄。</span><span class="sxs-lookup"><span data-stu-id="dba57-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="dba57-196">選取 [儲存名稱伺服器**設定**]。</span><span class="sxs-lookup"><span data-stu-id="dba57-196">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="dba57-198">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。</span><span class="sxs-lookup"><span data-stu-id="dba57-198">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="dba57-199">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="dba57-199">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
