---
title: 使用 Network Solutions 變更名稱伺服器以設定 Office 365
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: '了解如何設定 Office 365 使用 Network Solutions 自訂網域，如果您希望 Office 365 來管理您的 DNS 記錄。 '
ms.openlocfilehash: c9465da507e6b4dea35f9ead50b5bc7c14a1b38f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239807"
---
# <a name="change-nameservers-to-set-up-office-365-with-network-solutions"></a><span data-ttu-id="b84b9-103">使用 Network Solutions 變更名稱伺服器以設定 Office 365</span><span class="sxs-lookup"><span data-stu-id="b84b9-103">Change nameservers to set up Office 365 with Network Solutions</span></span>

 <span data-ttu-id="b84b9-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="b84b9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="b84b9-p101">如果要讓 Office 365 為您管理 Office 365 DNS 記錄，請按照下列指示進行 (您可視需要[在 Network Solutions 管理所有 Office 365 DNS 記錄](create-dns-records-at-network-solutions.md))。</span><span class="sxs-lookup"><span data-stu-id="b84b9-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="b84b9-107">在 Network Solutions 新增 TXT 記錄以驗證您擁有該網域</span><span class="sxs-lookup"><span data-stu-id="b84b9-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="b84b9-p102">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="b84b9-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b84b9-p103">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="b84b9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="b84b9-112">請依照下列步驟操作或[觀看影片 (從 0:47 處開始)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="b84b9-112">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b84b9-p104">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="b84b9-p104">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b84b9-115">您選取 [**登入**] 按鈕之前，請先選擇 [**管理我的網域名稱**中**登入至：** 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="b84b9-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="b84b9-117">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b84b9-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="b84b9-119">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="b84b9-119">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS](../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="b84b9-121">選取 [**管理進階的 DNS 記錄**]。</span><span class="sxs-lookup"><span data-stu-id="b84b9-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="b84b9-122">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="b84b9-122">(You may have to scroll down.)</span></span>
    
    ![選取 [管理進階的 DNS 記錄](../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="b84b9-124">向下的**文字 （TXT 記錄）** 區段中，捲動，然後選取 [**編輯 TXT 記錄**。</span><span class="sxs-lookup"><span data-stu-id="b84b9-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![選取 [編輯 TXT 記錄](../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="b84b9-126">In the boxes for the new record, type or copy and paste the values in the following table.</span><span class="sxs-lookup"><span data-stu-id="b84b9-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="b84b9-127">**Host (主機)**</span><span class="sxs-lookup"><span data-stu-id="b84b9-127">**Host**</span></span>|<span data-ttu-id="b84b9-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b84b9-128">**TTL**</span></span>|<span data-ttu-id="b84b9-129">**Text**</span><span class="sxs-lookup"><span data-stu-id="b84b9-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="b84b9-130">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="b84b9-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="b84b9-131">3600</span><span class="sxs-lookup"><span data-stu-id="b84b9-131">3600</span></span>  <br/> |<span data-ttu-id="b84b9-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b84b9-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b84b9-133">**附註**： 這是範例。</span><span class="sxs-lookup"><span data-stu-id="b84b9-133">**Note**: This is an example.</span></span> <span data-ttu-id="b84b9-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span><span class="sxs-lookup"><span data-stu-id="b84b9-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="b84b9-135">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="b84b9-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![輸入或貼於新記錄的方塊中的值](../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="b84b9-137">選取 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="b84b9-137">Select **Continue**.</span></span>
    
    ![選取 [繼續]](../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="b84b9-139">選取 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="b84b9-139">Select **Save Changes**.</span></span>
    
    ![選取 [儲存的變更](../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="b84b9-141">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="b84b9-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b84b9-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="b84b9-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="b84b9-143">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="b84b9-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b84b9-144">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b84b9-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b84b9-145">在 [**網域**] 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="b84b9-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b84b9-146">在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="b84b9-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b84b9-147">在 [**驗證網域**] 頁面上，選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="b84b9-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b84b9-p106">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b84b9-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="b84b9-151">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="b84b9-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="b84b9-p107">如要完成網域設定以用於 Office 365，請在您的網域註冊機構更改網域的 NS 記錄，使它指向 Office 365 主要和次要名稱伺服器。這樣就會設定並讓 Office 365 為您更新網域的 DNS 記錄。我們會新增所有記錄，好讓電子郵件、商務用 Skype Online 和您的公用網站都能使用您的網域，為您做好一切準備。</span><span class="sxs-lookup"><span data-stu-id="b84b9-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b84b9-p108">當您變更網域的 NS 記錄以指向 Office 365 名稱伺服器時，所有目前與您網域相關聯的服務都會受到影響。例如，在您完成這項變更之後，凡是傳送到您的網域 (例如 rob@ *your_domain*  .com) 的電子郵件都將開始傳送到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="b84b9-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span>
  
<span data-ttu-id="b84b9-p109">準備要變更 NS 記錄，以便讓 Office 365 設定您的網域？請依照下列步驟操作或[觀看影片 (從 2:23 處開始)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="b84b9-p109">Ready to change your NS records so Office 365 can set up your domain? Follow the steps below or [watch the video (start at 2:23)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="b84b9-159">*僅限*名稱伺服器應該會列出當您完成本節中的步驟時，是這四個： **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**及**ns4.bdm.microsoftonline.com**。</span><span class="sxs-lookup"><span data-stu-id="b84b9-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="b84b9-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="b84b9-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="b84b9-161">首先請用[這個連結](https://www.networksolutions.com/manage-it)移至 Network Solutions 上您的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="b84b9-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="b84b9-162">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="b84b9-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b84b9-163">您選取 [**登入**] 按鈕之前，請先選擇 [**管理我的網域名稱**中**登入至：** 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="b84b9-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![選擇 [管理我的網域名稱]，然後登入 Network Solutions](../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="b84b9-165">選取您要修改之網域名稱旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b84b9-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![針對您的網域選取核取方塊](../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="b84b9-167">選取 [**編輯 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="b84b9-167">Select **Edit DNS**.</span></span>
    
    ![選取 [編輯 DNS](../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="b84b9-169">選取 [**移動 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="b84b9-169">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-1](../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="b84b9-171">請根據現在顯示頁面上是否列出名稱伺服器，來選擇下列兩個程序其中一項繼續︰</span><span class="sxs-lookup"><span data-stu-id="b84b9-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="b84b9-172">如果有**無**列 」 名稱伺服器，[如果有列出名稱伺服器](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="b84b9-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="b84b9-173">如果**是**那里 」 列出名稱伺服器，[如果有列出名稱伺服器](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="b84b9-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="b84b9-174">如果列表上「沒有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="b84b9-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="b84b9-175">在 [**網域**] 頁面上，在 [**指定網域名稱伺服器**] 區段中，選取**新增更多名稱伺服器**。</span><span class="sxs-lookup"><span data-stu-id="b84b9-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-2-1](../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="b84b9-177">在 [**網域名稱**] 頁面中，輸入或複製並貼上下表中的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="b84b9-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="b84b9-178">**Name server 1 (名稱伺服器 1)**</span><span class="sxs-lookup"><span data-stu-id="b84b9-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="b84b9-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b84b9-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b84b9-180">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="b84b9-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="b84b9-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b84b9-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b84b9-182">**Name Server 2 (名稱伺服器 2)**</span><span class="sxs-lookup"><span data-stu-id="b84b9-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="b84b9-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b84b9-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b84b9-184">**Name Server 2 (名稱伺服器 2)**</span><span class="sxs-lookup"><span data-stu-id="b84b9-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="b84b9-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b84b9-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-重新委派-1-2-2](../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="b84b9-187">選取 [**移動 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="b84b9-187">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-2-3](../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="b84b9-189">選取 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="b84b9-189">Select **Save Changes**.</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-2-4](../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="b84b9-p112">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="b84b9-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="b84b9-193">如果列表上「有」名稱伺服器</span><span class="sxs-lookup"><span data-stu-id="b84b9-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="b84b9-194">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span><span class="sxs-lookup"><span data-stu-id="b84b9-194">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers.</span></span> <span data-ttu-id="b84b9-195">(也就是*只*刪除任何目前的名稱伺服器，*未*命名為**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**。)</span><span class="sxs-lookup"><span data-stu-id="b84b9-195">(That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="b84b9-196">如果有任何其他列出的名稱伺服器，請逐一選取它，然後按鍵盤上的**Delete**鍵。</span><span class="sxs-lookup"><span data-stu-id="b84b9-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![NetworkSolutions-DYN-BP-CONFIGURE-1-重新委派-1-5](../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="b84b9-198">選取 [**新增更多名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="b84b9-198">Select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-2-1](../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="b84b9-200">在 [**網域名稱**] 頁面中，輸入或複製並貼上下表中的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="b84b9-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="b84b9-201">**Name server 1 (名稱伺服器 1)**</span><span class="sxs-lookup"><span data-stu-id="b84b9-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="b84b9-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b84b9-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b84b9-203">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="b84b9-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="b84b9-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b84b9-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b84b9-205">**Name Server 3 (名稱伺服器 3)**</span><span class="sxs-lookup"><span data-stu-id="b84b9-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="b84b9-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b84b9-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b84b9-207">**Name Server 4 (名稱伺服器 4)**</span><span class="sxs-lookup"><span data-stu-id="b84b9-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="b84b9-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b84b9-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-重新委派-1-2-2](../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="b84b9-210">選取 [**移動 DNS**]。</span><span class="sxs-lookup"><span data-stu-id="b84b9-210">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-2-3](../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="b84b9-212">選取 [**儲存變更。**</span><span class="sxs-lookup"><span data-stu-id="b84b9-212">Select **Save Changes.**</span></span>
    
    ![NetworkSolutionsBP-重新委派-1-2-4](../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="b84b9-p114">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="b84b9-p114">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>