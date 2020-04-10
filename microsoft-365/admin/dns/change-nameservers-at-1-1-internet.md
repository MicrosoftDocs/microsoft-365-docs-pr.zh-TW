---
title: 使用 1&1 IONOS 變更名稱伺服器以設定 Office 365
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: 瞭解如何設定由世紀運作的 Office 365，以管理您的 DNS 記錄（1&1 網際網路是 DNS 主機服務提供者時）。
ms.openlocfilehash: bda6a19ba7bfca20bc1764187f429e13900d8460
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212362"
---
# <a name="change-nameservers-to-set-up-office-365-with-11-ionos"></a><span data-ttu-id="b6de9-103">使用 1&1 IONOS 變更名稱伺服器以設定 Office 365</span><span class="sxs-lookup"><span data-stu-id="b6de9-103">Change nameservers to set up Office 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="b6de9-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="b6de9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b6de9-105">如果您希望讓 Office 365 來管理您的 Office 365 DNS 記錄，請遵循下列指示。</span><span class="sxs-lookup"><span data-stu-id="b6de9-105">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you.</span></span> <span data-ttu-id="b6de9-106">（如果您願意，您可以[在 1&1 IONOS，管理所有 Office 365 DNS 記錄](create-dns-records-at-1-1-internet.md)。）</span><span class="sxs-lookup"><span data-stu-id="b6de9-106">(If you prefer, you can [manage all your Office 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b6de9-107">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="b6de9-107">Add a TXT record for verification</span></span>


<span data-ttu-id="b6de9-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="b6de9-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6de9-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="b6de9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="b6de9-112">請依照下列步驟操作或[觀看影片 (從 0:42 處開始)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="b6de9-112">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b6de9-113">若要開始，請移至您的網域頁面 1&1 IONOS 透過[此連結](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)。</span><span class="sxs-lookup"><span data-stu-id="b6de9-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="b6de9-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="b6de9-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="b6de9-115">在 [**我的網域**] 底下，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="b6de9-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="b6de9-116">在 [**網域中心**] 頁面上，尋找您要更新的網域;然後，選取該網域的 [**面板**] （ **v**）控制項。</span><span class="sxs-lookup"><span data-stu-id="b6de9-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="b6de9-117">在 [**網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="b6de9-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="b6de9-118">在 [ **TXT 和 SRV 記錄**] 區段中，選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="b6de9-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="b6de9-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="b6de9-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="b6de9-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b6de9-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="b6de9-121">**類型**</span><span class="sxs-lookup"><span data-stu-id="b6de9-121">**Type**</span></span> <br/> |<span data-ttu-id="b6de9-122">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="b6de9-122">**Prefix**</span></span> <br/> |<span data-ttu-id="b6de9-123">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="b6de9-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="b6de9-124">TXT</span><span class="sxs-lookup"><span data-stu-id="b6de9-124">TXT</span></span>  <br/> |<span data-ttu-id="b6de9-125">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="b6de9-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b6de9-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b6de9-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="b6de9-127">**請注意**：這是一個範例。</span><span class="sxs-lookup"><span data-stu-id="b6de9-127">**Note**: This is an example.</span></span> <span data-ttu-id="b6de9-128">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="b6de9-128">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="b6de9-129">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="b6de9-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="b6de9-130">請選取 [**儲存**]，然後再**儲存**一次。</span><span class="sxs-lookup"><span data-stu-id="b6de9-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="b6de9-131">在 [**編輯 DNS 設定**] 對話方塊中，選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="b6de9-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="b6de9-132">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="b6de9-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b6de9-133">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="b6de9-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="b6de9-134">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="b6de9-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b6de9-135">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="b6de9-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b6de9-136">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="b6de9-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b6de9-137">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="b6de9-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b6de9-138">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b6de9-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b6de9-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b6de9-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b6de9-140">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="b6de9-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b6de9-141">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b6de9-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="b6de9-142">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="b6de9-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="b6de9-p107">如要完成網域設定以用於 Office 365，請在您的網域註冊機構更改網域的 NS 記錄，使它指向 Office 365 主要和次要名稱伺服器。這樣就會設定並讓 Office 365 為您更新網域的 DNS 記錄。我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="b6de9-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b6de9-p108">當您變更網域的 NS 記錄以指向 Office 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。例如，在您完成這項變更之後，凡是傳送到您的網域 (例如 rob@ *your_domain*  .com) 的電子郵件都將開始傳送到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="b6de9-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
<span data-ttu-id="b6de9-p109">準備要變更 NS 記錄，以便讓 Office 365 設定您的網域？請依照下列步驟操作或[觀看影片 (從 2:47 處開始)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="b6de9-p109">Ready to change your NS records so Office 365 can set up your domain? Follow the steps below or [watch the video (start at 2:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="b6de9-150">下列程式將告訴您如何刪除清單中的任何其他、不想要的名稱伺服器，以及如何新增正確的名稱伺服器（如果尚未列出）。</span><span class="sxs-lookup"><span data-stu-id="b6de9-150">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="b6de9-151">> 完成本節中的步驟之後，應該會列出的唯一名稱伺服器為下列四種： > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b6de9-151">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="b6de9-152">若要開始使用，請移至您的網域頁面，1&1 IONOS，方法是使用[此連結](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)。</span><span class="sxs-lookup"><span data-stu-id="b6de9-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="b6de9-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="b6de9-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="b6de9-154">在 [**我的網域**] 底下，選取 [**管理網域**]。</span><span class="sxs-lookup"><span data-stu-id="b6de9-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="b6de9-155">在 [**網域中心**] 頁面上，找到您要更新的網域，然後選取該網域的 [**面板**] （ **v**）控制。</span><span class="sxs-lookup"><span data-stu-id="b6de9-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="b6de9-156">在 [**網域設定**] 區域中，選取 [**編輯 DNS 設定**]。</span><span class="sxs-lookup"><span data-stu-id="b6de9-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="b6de9-157">在 [**名稱伺服器設定**] 區段中，選取 [**其他名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="b6de9-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="b6de9-158">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="b6de9-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="b6de9-159">請根據現在顯示頁面上是否列出名稱伺服器，來選擇下列兩個程序其中一項繼續︰</span><span class="sxs-lookup"><span data-stu-id="b6de9-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="b6de9-160">如果沒有列出**任何**名稱伺服器，[則未列出任何名稱伺服器](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="b6de9-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="b6de9-161">如果已**列出名稱伺服器，** 如果已[列出名稱伺服器](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="b6de9-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="b6de9-162">如果列表上「沒有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="b6de9-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="b6de9-163">在 [**名稱伺服器 1** ] 方塊中，輸入或複製並貼上下清單格中的值。</span><span class="sxs-lookup"><span data-stu-id="b6de9-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b6de9-164">**名稱伺服器1**</span><span class="sxs-lookup"><span data-stu-id="b6de9-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="b6de9-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b6de9-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![在 [名稱伺服器 1] 方塊中輸入值](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="b6de9-167">在 [**其他名稱伺服器**] 下拉式清單中，選擇 [**我的次要名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="b6de9-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="b6de9-169">在 [**名稱伺服器2、3] 及 [4** ] 方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="b6de9-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b6de9-170">**名稱伺服器2**</span><span class="sxs-lookup"><span data-stu-id="b6de9-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="b6de9-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b6de9-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b6de9-172">**名稱伺服器3**</span><span class="sxs-lookup"><span data-stu-id="b6de9-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="b6de9-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b6de9-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b6de9-174">**名稱伺服器4**</span><span class="sxs-lookup"><span data-stu-id="b6de9-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="b6de9-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b6de9-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Entering name server values](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="b6de9-176">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b6de9-176">Select **Save**.</span></span>
    
    ![在 [名稱伺服器設定] 頁面上選取 [儲存]](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="b6de9-178">在 [**編輯 DNS 設定**] 對話方塊中，選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="b6de9-178">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![在 [編輯 DNS 設定] 對話方塊中選取 [儲存]](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="b6de9-p112">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="b6de9-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="b6de9-182">如果列表上「有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="b6de9-182">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="b6de9-183">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span><span class="sxs-lookup"><span data-stu-id="b6de9-183">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span></span> <span data-ttu-id="b6de9-184">（也就是說，*只*刪除所有*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**的目前名稱伺服器。）</span><span class="sxs-lookup"><span data-stu-id="b6de9-184">(That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="b6de9-185">如果 [名稱伺服器] 方塊中已列出名稱伺服器，請選取每個**名稱伺服器**，然後按鍵盤上的**delete**鍵，逐一刪除。</span><span class="sxs-lookup"><span data-stu-id="b6de9-185">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="b6de9-187">在 [**名稱伺服器1、2、3] 及 [4** ] 方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="b6de9-187">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b6de9-188">**名稱伺服器1**</span><span class="sxs-lookup"><span data-stu-id="b6de9-188">**Name server 1**</span></span> <br/> |<span data-ttu-id="b6de9-189">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b6de9-189">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b6de9-190">**名稱伺服器2**</span><span class="sxs-lookup"><span data-stu-id="b6de9-190">**Name server 2**</span></span> <br/> |<span data-ttu-id="b6de9-191">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b6de9-191">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b6de9-192">**名稱伺服器3**</span><span class="sxs-lookup"><span data-stu-id="b6de9-192">**Name server 3**</span></span> <br/> |<span data-ttu-id="b6de9-193">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b6de9-193">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b6de9-194">**名稱伺服器4**</span><span class="sxs-lookup"><span data-stu-id="b6de9-194">**Name server 4**</span></span> <br/> |<span data-ttu-id="b6de9-195">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b6de9-195">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![輸入名稱伺服器值](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="b6de9-197">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b6de9-197">Select **Save**.</span></span>
    
    ![在 [名稱伺服器設定] 頁面上選取 [儲存]](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="b6de9-199">在 [**編輯 DNS 設定**] 對話方塊中，選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="b6de9-199">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![在 [編輯 DNS 設定] 對話方塊中選取 [儲存]](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="b6de9-p114">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="b6de9-p114">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  


