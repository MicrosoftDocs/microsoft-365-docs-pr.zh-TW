---
title: 在 Hostgator 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft Hostgator。
ms.openlocfilehash: d2d8d535d137ca3de2fc6dfc04abe8cf61dda07d
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939188"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a><span data-ttu-id="efd43-103">在 Hostgator 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="efd43-103">Create DNS records at Hostgator for Microsoft</span></span>

 <span data-ttu-id="efd43-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="efd43-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="efd43-105">如果 Hostgator 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="efd43-105">If Hostgator is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="efd43-106">您必須先執行第一個 procedurebelow，將[您的網域指向您的託管帳戶](#point-your-domain-to-your-hosting-account)，再使用本文中的任何其他程式新增 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="efd43-106">You must perform the first procedurebelow, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account), before you add DNS records by using any of the other procedures in this article.</span></span> 

<span data-ttu-id="efd43-107">在 Hostgator 進行上述所有變更之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="efd43-107">After you make all of these changes at Hostgator, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="efd43-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="efd43-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="efd43-109">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="efd43-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="efd43-110">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="efd43-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="efd43-111">將您的網域指向您的託管帳戶</span><span class="sxs-lookup"><span data-stu-id="efd43-111">Point your domain to your hosting account</span></span>
<span data-ttu-id="efd43-112"><a name="BKMK_PointDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="efd43-112"><a name="BKMK_PointDomain"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="efd43-113">您必須先執行此程式，再執行本文中的任何其他程式。</span><span class="sxs-lookup"><span data-stu-id="efd43-113">You must perform this procedure before you perform any of the other procedures in this article.</span></span> 
  
<span data-ttu-id="efd43-114">請遵循下列步驟，建立您的網域和代管帳戶的關聯。</span><span class="sxs-lookup"><span data-stu-id="efd43-114">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="efd43-115">若要開始使用，請移至您的網域管理頁面 Hostgator，方法是使用[此連結](https://portal.hostgator.com/)。</span><span class="sxs-lookup"><span data-stu-id="efd43-115">To get started, go to your domain management page at Hostgator by using [this link](https://portal.hostgator.com/).</span></span> <span data-ttu-id="efd43-116">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="efd43-116">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="efd43-117">選取左側的 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-117">Select **Domains** on the left.</span></span>
  
3. <span data-ttu-id="efd43-118">在 [**管理網域**] 頁面上，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="efd43-118">On the **Manage Domains** page, select the domain you want to update.</span></span> 
  
4. <span data-ttu-id="efd43-119">在左側的快顯功能表上，選取 [**名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-119">On the pop-out menu on the left, select **Name Servers**.</span></span>
  
5. <span data-ttu-id="efd43-120">在您網域的 [**名稱伺服器**] 頁面上，在 [**自動將此網域指向我的主機帳戶**] 下拉式清單中，選擇與您的網域相關聯的主控帳戶。</span><span class="sxs-lookup"><span data-stu-id="efd43-120">On the **Name Servers** page for your domain, in the **Automatically point this domain to my hosting account** drop-down list, choose the hosting account that is associated with your domain.</span></span> 
  
6. <span data-ttu-id="efd43-121">選取 [**儲存名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-121">Select **Save Name Servers**.</span></span>
    
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="efd43-122">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="efd43-122">Add a TXT record for verification</span></span>
<span data-ttu-id="efd43-123"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="efd43-123"><a name="BKMK_verify"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="efd43-124">執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。</span><span class="sxs-lookup"><span data-stu-id="efd43-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
<span data-ttu-id="efd43-p103">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="efd43-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="efd43-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="efd43-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="efd43-p105">若要開始使用，請移至您位於 Hostgator 的 cPanel 頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="efd43-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="efd43-131">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="efd43-131">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="efd43-132">您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="efd43-132">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="efd43-133">您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。</span><span class="sxs-lookup"><span data-stu-id="efd43-133">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="efd43-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="efd43-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="efd43-135">若要開始使用 Microsoft，您可以從 Hostgator 或重新委派名稱伺服器購買主控帳戶，[以指向 Microsoft](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="efd43-135">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="efd43-136">在 [**控制台**] 頁面的 [**網域**] 區域中，選取 [**高級區域編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-136">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="efd43-137">在 [**高級區域編輯器**] 頁面的 [新增**記錄**] 區域，于新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="efd43-137">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="efd43-138">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="efd43-138">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="efd43-139">**Name**</span><span class="sxs-lookup"><span data-stu-id="efd43-139">**Name**</span></span> <br/> |<span data-ttu-id="efd43-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="efd43-140">**TTL**</span></span> <br/> |<span data-ttu-id="efd43-141">**類型**</span><span class="sxs-lookup"><span data-stu-id="efd43-141">**Type**</span></span> <br/> |<span data-ttu-id="efd43-142">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="efd43-142">**TXT Data**</span></span> <br/> |
    |<span data-ttu-id="efd43-143">使用您的*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="efd43-143">Use your  *domain_name*.</span></span> <span data-ttu-id="efd43-144">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="efd43-144">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="efd43-145">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="efd43-145">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="efd43-146">1 </span><span class="sxs-lookup"><span data-stu-id="efd43-146">1</span></span>  <br/> |<span data-ttu-id="efd43-147">TXT</span><span class="sxs-lookup"><span data-stu-id="efd43-147">TXT</span></span>  <br/> |<span data-ttu-id="efd43-148">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="efd43-148">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="efd43-149">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="efd43-149">**Note:** This is an example.</span></span> <span data-ttu-id="efd43-150">在這裡請使用您自己來自表格的 [目的地或指向位址]\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="efd43-150">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="efd43-151">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="efd43-151">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="efd43-152">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-152">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="efd43-153">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="efd43-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="efd43-154">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="efd43-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="efd43-155">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="efd43-155">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="efd43-156">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="efd43-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="efd43-157">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="efd43-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="efd43-158">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="efd43-158">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="efd43-159">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="efd43-159">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="efd43-160">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="efd43-160">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="efd43-161">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="efd43-161">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="efd43-162">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="efd43-162">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="efd43-163">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="efd43-163">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="efd43-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="efd43-164"><a name="BKMK_add_MX"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="efd43-165">執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。</span><span class="sxs-lookup"><span data-stu-id="efd43-165">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="efd43-166">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="efd43-166">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="efd43-167">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="efd43-167">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="efd43-168">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="efd43-168">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="efd43-169">您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="efd43-169">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="efd43-170">您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。</span><span class="sxs-lookup"><span data-stu-id="efd43-170">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="efd43-171">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="efd43-171">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="efd43-172">若要開始使用 Microsoft，您可以從 Hostgator 或重新委派名稱伺服器購買主控帳戶，[以指向 Microsoft](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="efd43-172">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="efd43-173">在 [**控制台**] 頁面的 [**電子郵件**] 區域中，選取 [ **MX 專案**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-173">On the **Control Panel** page, in the **Email** area, select **MX Entry**.</span></span>
    
 
3. <span data-ttu-id="efd43-174">在 [**電子郵件路由**] 區域中，選取 [**遠端郵件交換器**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-174">In the **Email Routing** area, select **Remote Mail Exchanger**.</span></span>

4. <span data-ttu-id="efd43-175">選取 [**變更**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-175">Select **Change**.</span></span>
  
5. <span data-ttu-id="efd43-176">在 [新增**記錄**] 區域的新記錄方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="efd43-176">In the **Add a New Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="efd43-177">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="efd43-177">**Priority**</span></span>|<span data-ttu-id="efd43-178">**Destination**</span><span class="sxs-lookup"><span data-stu-id="efd43-178">**Destination**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="efd43-179">0</span><span class="sxs-lookup"><span data-stu-id="efd43-179">0</span></span>  <br/> <span data-ttu-id="efd43-180">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="efd43-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="efd43-181">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="efd43-181">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="efd43-182">**附注：** 從您\<的 Microsoft 帳戶取得您的*網域金鑰*\> 。  </span><span class="sxs-lookup"><span data-stu-id="efd43-182">**Note:** Get your \< *domain-key*  \> from your Microsoft account.</span></span>  [<span data-ttu-id="efd43-183">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="efd43-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
  
6. <span data-ttu-id="efd43-184">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-184">Select **Add New Record**.</span></span>
   
 
7. <span data-ttu-id="efd43-185">如果 [ **Mx 記錄**] 區段中有任何其他 MX 記錄，請移除每個記錄。</span><span class="sxs-lookup"><span data-stu-id="efd43-185">If there are any other MX records in the **MX Records** section, remove each of them.</span></span> 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="efd43-186">新增 Microsoft 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="efd43-186">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="efd43-187"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="efd43-187"><a name="BKMK_add_CNAME"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="efd43-188">執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。</span><span class="sxs-lookup"><span data-stu-id="efd43-188">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="efd43-189">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="efd43-189">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="efd43-190">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="efd43-190">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="efd43-191">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="efd43-191">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="efd43-192">您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="efd43-192">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="efd43-193">您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。</span><span class="sxs-lookup"><span data-stu-id="efd43-193">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="efd43-194">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="efd43-194">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="efd43-195">若要開始使用 Microsoft，您可以從 Hostgator 或重新委派名稱伺服器購買主控帳戶，[以指向 Microsoft](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="efd43-195">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="efd43-196">在 [**控制台**] 頁面的 [**網域**] 區域中，選取 [**高級區域編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-196">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="efd43-197">新增六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="efd43-197">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="efd43-198">在 [**高級區域編輯器**] 頁面的 [新增**記錄**] 區域，于新記錄的方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="efd43-198">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="efd43-199">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="efd43-199">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="efd43-200">**Name**</span><span class="sxs-lookup"><span data-stu-id="efd43-200">**Name**</span></span>|<span data-ttu-id="efd43-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="efd43-201">**TTL**</span></span>|<span data-ttu-id="efd43-202">**類型**</span><span class="sxs-lookup"><span data-stu-id="efd43-202">**Type**</span></span>|<span data-ttu-id="efd43-203">**CNAME**</span><span class="sxs-lookup"><span data-stu-id="efd43-203">**CNAME**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="efd43-204">autodiscover.</span><span class="sxs-lookup"><span data-stu-id="efd43-204">autodiscover.</span></span> <span data-ttu-id="efd43-205">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="efd43-205">*domain_name*.</span></span> <span data-ttu-id="efd43-206">（例如，autodiscover.fourthcoffee.com）。</span><span class="sxs-lookup"><span data-stu-id="efd43-206">(for example, autodiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="efd43-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="efd43-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="efd43-208">3600</span><span class="sxs-lookup"><span data-stu-id="efd43-208">3600</span></span>  <br/> |<span data-ttu-id="efd43-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="efd43-209">CNAME</span></span>  <br/> |<span data-ttu-id="efd43-210">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="efd43-210">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="efd43-211">sip.</span><span class="sxs-lookup"><span data-stu-id="efd43-211">sip.</span></span> <span data-ttu-id="efd43-212">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="efd43-212">*domain_name*.</span></span> <span data-ttu-id="efd43-213">（例如，sip.fourthcoffee.com）。</span><span class="sxs-lookup"><span data-stu-id="efd43-213">(for example, sip.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="efd43-214">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="efd43-214">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="efd43-215">3600</span><span class="sxs-lookup"><span data-stu-id="efd43-215">3600</span></span>  <br/> |<span data-ttu-id="efd43-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="efd43-216">CNAME</span></span>  <br/> |<span data-ttu-id="efd43-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="efd43-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="efd43-218">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="efd43-218">lyncdiscover.</span></span> <span data-ttu-id="efd43-219">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="efd43-219">*domain_name*.</span></span> <span data-ttu-id="efd43-220">（例如，lyncdiscover.fourthcoffee.com）。</span><span class="sxs-lookup"><span data-stu-id="efd43-220">(for example, lyncdiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="efd43-221">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="efd43-221">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="efd43-222">3600</span><span class="sxs-lookup"><span data-stu-id="efd43-222">3600</span></span>  <br/> |<span data-ttu-id="efd43-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="efd43-223">CNAME</span></span>  <br/> |<span data-ttu-id="efd43-224">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="efd43-224">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="efd43-225">enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="efd43-225">enterpriseregistration.</span></span> <span data-ttu-id="efd43-226">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="efd43-226">*domain_name*.</span></span> <span data-ttu-id="efd43-227">（例如，enterpriseregistration.fourthcoffee.com）。</span><span class="sxs-lookup"><span data-stu-id="efd43-227">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="efd43-228">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="efd43-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="efd43-229">3600</span><span class="sxs-lookup"><span data-stu-id="efd43-229">3600</span></span>  <br/> |<span data-ttu-id="efd43-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="efd43-230">CNAME</span></span>  <br/> |<span data-ttu-id="efd43-231">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="efd43-231">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="efd43-232">enterpriseenrollment.</span><span class="sxs-lookup"><span data-stu-id="efd43-232">enterpriseenrollment.</span></span> <span data-ttu-id="efd43-233">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="efd43-233">*domain_name*.</span></span> <span data-ttu-id="efd43-234">（例如，enterpriseregistration.fourthcoffee.com）。</span><span class="sxs-lookup"><span data-stu-id="efd43-234">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="efd43-235">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="efd43-235">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="efd43-236">3600</span><span class="sxs-lookup"><span data-stu-id="efd43-236">3600</span></span>  <br/> |<span data-ttu-id="efd43-237">CNAME</span><span class="sxs-lookup"><span data-stu-id="efd43-237">CNAME</span></span>  <br/> |<span data-ttu-id="efd43-238">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="efd43-238">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |

  
4. <span data-ttu-id="efd43-239">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-239">Select **Add Record**.</span></span>

5. <span data-ttu-id="efd43-240">逐一新增其餘五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="efd43-240">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="efd43-241">在 [ **Add a record] （新增記錄**）區段中，使用表格中下一列的值來建立記錄，然後再選取 [**新增記錄**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="efd43-241">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
    <span data-ttu-id="efd43-242">重複這個程序，直到六筆 CNAME 記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="efd43-242">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="efd43-243">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="efd43-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="efd43-244"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="efd43-244"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="efd43-245">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="efd43-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="efd43-246">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="efd43-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="efd43-247">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="efd43-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="efd43-248">而是，請將必要的 Microsoft 值新增到目前的記錄，以便擁有包含這兩組值的單一 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="efd43-248">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="efd43-249">需要範例？</span><span class="sxs-lookup"><span data-stu-id="efd43-249">Need examples?</span></span> <span data-ttu-id="efd43-250">請參閱這些 [Microsoft 的外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="efd43-250">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="efd43-251">若要驗證您的 SPF 記錄，您可以使用其中一種 [SPF 驗證工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="efd43-251">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="efd43-252">執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。</span><span class="sxs-lookup"><span data-stu-id="efd43-252">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="efd43-253">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="efd43-253">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="efd43-254">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="efd43-254">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="efd43-255">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="efd43-255">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="efd43-256">您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="efd43-256">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="efd43-257">您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。</span><span class="sxs-lookup"><span data-stu-id="efd43-257">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="efd43-258">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="efd43-258">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="efd43-259">若要開始使用 Microsoft，您可以從 Hostgator 或重新委派名稱伺服器購買主控帳戶，[以指向 Microsoft](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="efd43-259">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="efd43-260">在 [**控制台**] 頁面的 [**網域**] 區域中，選取 [**高級區域編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-260">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="efd43-261">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="efd43-261">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="efd43-262">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="efd43-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="efd43-263">**Name**</span><span class="sxs-lookup"><span data-stu-id="efd43-263">**Name**</span></span>|<span data-ttu-id="efd43-264">**TTL**</span><span class="sxs-lookup"><span data-stu-id="efd43-264">**TTL**</span></span>|<span data-ttu-id="efd43-265">**類型**</span><span class="sxs-lookup"><span data-stu-id="efd43-265">**Type**</span></span>|<span data-ttu-id="efd43-266">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="efd43-266">**TXT Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="efd43-267">使用您的*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="efd43-267">Use your  *domain_name*.</span></span> <span data-ttu-id="efd43-268">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="efd43-268">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="efd43-269">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="efd43-269">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="efd43-270">3600</span><span class="sxs-lookup"><span data-stu-id="efd43-270">3600</span></span>  <br/> |<span data-ttu-id="efd43-271">TXT</span><span class="sxs-lookup"><span data-stu-id="efd43-271">TXT</span></span>  <br/> |<span data-ttu-id="efd43-272">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="efd43-272">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="efd43-273">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="efd43-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
  
4. <span data-ttu-id="efd43-274">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-274">Select **Add Record**.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="efd43-275">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="efd43-275">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="efd43-276"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="efd43-276"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="efd43-277">執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。</span><span class="sxs-lookup"><span data-stu-id="efd43-277">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="efd43-278">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="efd43-278">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="efd43-279">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="efd43-279">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="efd43-280">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="efd43-280">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="efd43-281">您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="efd43-281">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="efd43-282">您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。</span><span class="sxs-lookup"><span data-stu-id="efd43-282">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="efd43-283">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="efd43-283">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="efd43-284">若要開始使用 Microsoft，您可以從 Hostgator 或重新委派名稱伺服器購買主控帳戶，[以指向 Microsoft](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="efd43-284">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="efd43-285">在 [**控制台**] 頁面的 [**網域**] 區域中，選取 [**高級區域編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-285">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>

    
3. <span data-ttu-id="efd43-286">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="efd43-286">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="efd43-287">在 [ **ADVANCED DNS 區域編輯器**] 頁面上的 [**新增記錄**] 區域，于新記錄的方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="efd43-287">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="efd43-288">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="efd43-288">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="efd43-289">**Name**</span><span class="sxs-lookup"><span data-stu-id="efd43-289">**Name**</span></span>|<span data-ttu-id="efd43-290">**TTL**</span><span class="sxs-lookup"><span data-stu-id="efd43-290">**TTL**</span></span>|<span data-ttu-id="efd43-291">**類型**</span><span class="sxs-lookup"><span data-stu-id="efd43-291">**Type**</span></span>|<span data-ttu-id="efd43-292">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="efd43-292">**Priority**</span></span>|<span data-ttu-id="efd43-293">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="efd43-293">**Weight**</span></span>|<span data-ttu-id="efd43-294">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="efd43-294">**Port**</span></span>|<span data-ttu-id="efd43-295">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="efd43-295">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="efd43-296">_sip。 _tls。</span><span class="sxs-lookup"><span data-stu-id="efd43-296">_sip._tls.</span></span> <span data-ttu-id="efd43-297">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="efd43-297">*domain_name*.</span></span> <span data-ttu-id="efd43-298">（例如 _sip，_tls fourthcoffee）</span><span class="sxs-lookup"><span data-stu-id="efd43-298">(for example, _sip._tls.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="efd43-299">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="efd43-299">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="efd43-300">3600</span><span class="sxs-lookup"><span data-stu-id="efd43-300">3600</span></span>  <br/> |<span data-ttu-id="efd43-301">SRV</span><span class="sxs-lookup"><span data-stu-id="efd43-301">SRV</span></span>  <br/> |<span data-ttu-id="efd43-302">100</span><span class="sxs-lookup"><span data-stu-id="efd43-302">100</span></span>  <br/> |<span data-ttu-id="efd43-303">1 </span><span class="sxs-lookup"><span data-stu-id="efd43-303">1</span></span>  <br/> |<span data-ttu-id="efd43-304">443</span><span class="sxs-lookup"><span data-stu-id="efd43-304">443</span></span>  <br/> |<span data-ttu-id="efd43-305">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="efd43-305">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="efd43-306">_sipfederationtls。 _tcp。</span><span class="sxs-lookup"><span data-stu-id="efd43-306">_sipfederationtls._tcp.</span></span> <span data-ttu-id="efd43-307">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="efd43-307">*domain_name*.</span></span> <span data-ttu-id="efd43-308">（例如 _sipfederationtls，_tcp fourthcoffee）</span><span class="sxs-lookup"><span data-stu-id="efd43-308">(for example, _sipfederationtls._tcp.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="efd43-309">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="efd43-309">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="efd43-310">3600</span><span class="sxs-lookup"><span data-stu-id="efd43-310">3600</span></span>  <br/> |<span data-ttu-id="efd43-311">SRV</span><span class="sxs-lookup"><span data-stu-id="efd43-311">SRV</span></span>  <br/> |<span data-ttu-id="efd43-312">100</span><span class="sxs-lookup"><span data-stu-id="efd43-312">100</span></span>  <br/> |<span data-ttu-id="efd43-313">1 </span><span class="sxs-lookup"><span data-stu-id="efd43-313">1</span></span>  <br/> |<span data-ttu-id="efd43-314">5061</span><span class="sxs-lookup"><span data-stu-id="efd43-314">5061</span></span>  <br/> |<span data-ttu-id="efd43-315">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="efd43-315">sipfed.online.lync.com</span></span>  <br/> |
   

4. <span data-ttu-id="efd43-316">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="efd43-316">Select **Add Record**.</span></span>

  
5. <span data-ttu-id="efd43-317">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="efd43-317">Add the other SRV record.</span></span>
    
    <span data-ttu-id="efd43-318">在 [ **Add a record] （新增記錄**）區段中，使用表格中下一列的值來建立記錄，然後再選取 [**新增記錄**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="efd43-318">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="efd43-319">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="efd43-319">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="efd43-320">然而有時可能需要更久的時間，您所做的變更才能在整個網際網路的 DNS 系統中生效。</span><span class="sxs-lookup"><span data-stu-id="efd43-320">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="efd43-321">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="efd43-321">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
