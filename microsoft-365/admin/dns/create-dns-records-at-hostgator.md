---
title: 在 Hostgator 建立 Office 365 的 DNS 記錄
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
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Office 365 Hostgator。
ms.openlocfilehash: a5a41e5c1eba9d99d1927192472da7746277dd38
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211712"
---
# <a name="create-dns-records-at-hostgator-for-office-365"></a><span data-ttu-id="a7e5c-103">在 Hostgator 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="a7e5c-103">Create DNS records at Hostgator for Office 365</span></span>

 <span data-ttu-id="a7e5c-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a7e5c-105">如果 Hostgator 是您的 DNS 主機服務提供者，請按照本文所述的步驟驗證網域，並為電子郵件與商務用 Skype Online 等項目設定 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-105">If Hostgator is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a7e5c-106">您必須先執行第一個 procedurebelow，將[您的網域指向您的託管帳戶](#point-your-domain-to-your-hosting-account)，再使用本文中的任何其他程式新增 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-106">You must perform the first procedurebelow, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account), before you add DNS records by using any of the other procedures in this article.</span></span> 

<span data-ttu-id="a7e5c-107">在 Hostgator 進行上述所有變更之後，您的網域就會設定為搭配 Office 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-107">After you make all of these changes at Hostgator, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="a7e5c-108">若要了解使用 Office 365 網站的虛擬主機和 DNS，請參閱[搭配 Office 365 使用公用網站](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-108">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7e5c-109">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-109">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a7e5c-110">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a7e5c-111">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-111">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="a7e5c-112">將您的網域指向您的託管帳戶</span><span class="sxs-lookup"><span data-stu-id="a7e5c-112">Point your domain to your hosting account</span></span>
<span data-ttu-id="a7e5c-113"><a name="BKMK_PointDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e5c-113"><a name="BKMK_PointDomain"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e5c-114">您必須先執行此程式，再執行本文中的任何其他程式。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-114">You must perform this procedure before you perform any of the other procedures in this article.</span></span> 
  
<span data-ttu-id="a7e5c-115">請遵循下列步驟，建立您的網域和代管帳戶的關聯。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-115">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="a7e5c-116">若要開始使用，請移至您的網域管理頁面 Hostgator，方法是使用[此連結](https://portal.hostgator.com/)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-116">To get started, go to your domain management page at Hostgator by using [this link](https://portal.hostgator.com/).</span></span> <span data-ttu-id="a7e5c-117">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-117">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="a7e5c-118">選取左側的 [**網域**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-118">Select **Domains** on the left.</span></span>
  
3. <span data-ttu-id="a7e5c-119">在 [**管理網域**] 頁面上，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-119">On the **Manage Domains** page, select the domain you want to update.</span></span> 
  
4. <span data-ttu-id="a7e5c-120">在左側的快顯功能表上，選取 [**名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-120">On the pop-out menu on the left, select **Name Servers**.</span></span>
  
5. <span data-ttu-id="a7e5c-121">在您網域的 [**名稱伺服器**] 頁面上，在 [**自動將此網域指向我的主機帳戶**] 下拉式清單中，選擇與您的網域相關聯的主控帳戶。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-121">On the **Name Servers** page for your domain, in the **Automatically point this domain to my hosting account** drop-down list, choose the hosting account that is associated with your domain.</span></span> 
  
6. <span data-ttu-id="a7e5c-122">選取 [**儲存名稱伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-122">Select **Save Name Servers**.</span></span>
    
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a7e5c-123">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="a7e5c-123">Add a TXT record for verification</span></span>
<span data-ttu-id="a7e5c-124"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e5c-124"><a name="BKMK_verify"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e5c-125">執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-125">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
<span data-ttu-id="a7e5c-p103">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7e5c-p104">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a7e5c-p105">若要開始使用，請移至您位於 Hostgator 的 cPanel 頁面。系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="a7e5c-132">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-132">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="a7e5c-133">您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-133">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="a7e5c-134">您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-134">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a7e5c-p107">若要讓 cPanel 與您的網域相關聯，要有一個 Hostgator 代管的帳戶。若要開始使用 Office 365，您可以從 Hostgator 購買代管帳戶或[重新委派您的名稱伺服器以指向 Office 365](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-p107">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="a7e5c-137">在 [**控制台**] 頁面的 [**網域**] 區域中，選取 [**高級區域編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-137">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="a7e5c-138">在 [**高級區域編輯器**] 頁面的 [新增**記錄**] 區域，于新記錄的方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-138">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a7e5c-139">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="a7e5c-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7e5c-140">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-140">**Name**</span></span> <br/> |<span data-ttu-id="a7e5c-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-141">**TTL**</span></span> <br/> |<span data-ttu-id="a7e5c-142">**類型**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-142">**Type**</span></span> <br/> |<span data-ttu-id="a7e5c-143">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-143">**TXT Data**</span></span> <br/> |
    |<span data-ttu-id="a7e5c-144">使用您的*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-144">Use your  *domain_name*.</span></span> <span data-ttu-id="a7e5c-145">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="a7e5c-145">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="a7e5c-146">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e5c-147">1 </span><span class="sxs-lookup"><span data-stu-id="a7e5c-147">1</span></span>  <br/> |<span data-ttu-id="a7e5c-148">TXT</span><span class="sxs-lookup"><span data-stu-id="a7e5c-148">TXT</span></span>  <br/> |<span data-ttu-id="a7e5c-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a7e5c-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a7e5c-150">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-150">**Note:** This is an example.</span></span> <span data-ttu-id="a7e5c-151">在這裡請使用您自己的 [目的地或指向位址] 值，請參閱 Office 365 表格。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-151">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="a7e5c-152">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="a7e5c-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="a7e5c-153">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="a7e5c-154">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a7e5c-155">現在您已在網域註冊機構網站新增記錄，請返回 Office 365 並要求 Office 365 尋找該記錄。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-155">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="a7e5c-156">在 Office 365 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-156">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a7e5c-157">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a7e5c-158">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="a7e5c-159">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="a7e5c-160">在 [驗證網域]\*\*\*\* 頁面上，選取 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a7e5c-161">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-161">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a7e5c-162">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a7e5c-163">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-163">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="a7e5c-164">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="a7e5c-164">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="a7e5c-165"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e5c-165"><a name="BKMK_add_MX"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e5c-166">執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-166">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="a7e5c-167">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-167">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="a7e5c-168">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-168">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="a7e5c-169">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-169">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="a7e5c-170">您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-170">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="a7e5c-171">您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-171">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a7e5c-p113">若要讓 cPanel 與您的網域相關聯，要有一個 Hostgator 代管的帳戶。若要開始使用 Office 365，您可以從 Hostgator 購買代管帳戶或[重新委派您的名稱伺服器以指向 Office 365](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-p113">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="a7e5c-174">在 [**控制台**] 頁面的 [**電子郵件**] 區域中，選取 [ **MX 專案**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-174">On the **Control Panel** page, in the **Email** area, select **MX Entry**.</span></span>
    
 
3. <span data-ttu-id="a7e5c-175">在 [**電子郵件路由**] 區域中，選取 [**遠端郵件交換器**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-175">In the **Email Routing** area, select **Remote Mail Exchanger**.</span></span>

4. <span data-ttu-id="a7e5c-176">選取 [**變更**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-176">Select **Change**.</span></span>
  
5. <span data-ttu-id="a7e5c-177">在 [新增**記錄**] 區域的新記錄方塊中，輸入或複製並貼上下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-177">In the **Add a New Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="a7e5c-178">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-178">**Priority**</span></span>|<span data-ttu-id="a7e5c-179">**目的地**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-179">**Destination**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a7e5c-180">0</span><span class="sxs-lookup"><span data-stu-id="a7e5c-180">0</span></span>  <br/> <span data-ttu-id="a7e5c-181">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7e5c-181">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="a7e5c-182">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a7e5c-182">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a7e5c-183">**附注：** 從您\<的 Office 365 帳戶取得您的*網域金鑰*\> 。  </span><span class="sxs-lookup"><span data-stu-id="a7e5c-183">**Note:** Get your \< *domain-key*  \> from your Office 365 account.</span></span>  [<span data-ttu-id="a7e5c-184">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="a7e5c-184">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
  
6. <span data-ttu-id="a7e5c-185">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-185">Select **Add New Record**.</span></span>
   
 
7. <span data-ttu-id="a7e5c-186">如果 [ **Mx 記錄**] 區段中有任何其他 MX 記錄，請移除每個記錄。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-186">If there are any other MX records in the **MX Records** section, remove each of them.</span></span> 

    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="a7e5c-187">新增 Office 365 所需的六筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="a7e5c-187">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="a7e5c-188"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e5c-188"><a name="BKMK_add_CNAME"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e5c-189">執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-189">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="a7e5c-190">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-190">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="a7e5c-191">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-191">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="a7e5c-192">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-192">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="a7e5c-193">您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-193">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="a7e5c-194">您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-194">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a7e5c-p117">若要讓 cPanel 與您的網域相關聯，要有一個 Hostgator 代管的帳戶。若要開始使用 Office 365，您可以從 Hostgator 購買代管帳戶或[重新委派您的名稱伺服器以指向 Office 365](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-p117">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="a7e5c-197">在 [**控制台**] 頁面的 [**網域**] 區域中，選取 [**高級區域編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-197">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="a7e5c-198">新增六筆 CNAME 記錄的第一筆。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-198">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="a7e5c-199">在 [**高級區域編輯器**] 頁面的 [新增**記錄**] 區域，于新記錄的方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-199">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="a7e5c-200">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="a7e5c-200">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a7e5c-201">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-201">**Name**</span></span>|<span data-ttu-id="a7e5c-202">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-202">**TTL**</span></span>|<span data-ttu-id="a7e5c-203">**類型**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-203">**Type**</span></span>|<span data-ttu-id="a7e5c-204">**CNAME**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-204">**CNAME**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7e5c-205">autodiscover.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-205">autodiscover.</span></span> <span data-ttu-id="a7e5c-206">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-206">*domain_name*.</span></span> <span data-ttu-id="a7e5c-207">（例如，autodiscover.fourthcoffee.com）。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-207">(for example, autodiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="a7e5c-208">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e5c-209">3600</span><span class="sxs-lookup"><span data-stu-id="a7e5c-209">3600</span></span>  <br/> |<span data-ttu-id="a7e5c-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7e5c-210">CNAME</span></span>  <br/> |<span data-ttu-id="a7e5c-211">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a7e5c-211">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a7e5c-212">sip.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-212">sip.</span></span> <span data-ttu-id="a7e5c-213">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-213">*domain_name*.</span></span> <span data-ttu-id="a7e5c-214">（例如，sip.fourthcoffee.com）。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-214">(for example, sip.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="a7e5c-215">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-215">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e5c-216">3600</span><span class="sxs-lookup"><span data-stu-id="a7e5c-216">3600</span></span>  <br/> |<span data-ttu-id="a7e5c-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7e5c-217">CNAME</span></span>  <br/> |<span data-ttu-id="a7e5c-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7e5c-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a7e5c-219">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-219">lyncdiscover.</span></span> <span data-ttu-id="a7e5c-220">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-220">*domain_name*.</span></span> <span data-ttu-id="a7e5c-221">（例如，lyncdiscover.fourthcoffee.com）。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-221">(for example, lyncdiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="a7e5c-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-222">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e5c-223">3600</span><span class="sxs-lookup"><span data-stu-id="a7e5c-223">3600</span></span>  <br/> |<span data-ttu-id="a7e5c-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7e5c-224">CNAME</span></span>  <br/> |<span data-ttu-id="a7e5c-225">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7e5c-225">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a7e5c-226">enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-226">enterpriseregistration.</span></span> <span data-ttu-id="a7e5c-227">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-227">*domain_name*.</span></span> <span data-ttu-id="a7e5c-228">（例如，enterpriseregistration.fourthcoffee.com）。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-228">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="a7e5c-229">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-229">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e5c-230">3600</span><span class="sxs-lookup"><span data-stu-id="a7e5c-230">3600</span></span>  <br/> |<span data-ttu-id="a7e5c-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7e5c-231">CNAME</span></span>  <br/> |<span data-ttu-id="a7e5c-232">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a7e5c-232">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="a7e5c-233">enterpriseenrollment.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-233">enterpriseenrollment.</span></span> <span data-ttu-id="a7e5c-234">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-234">*domain_name*.</span></span> <span data-ttu-id="a7e5c-235">（例如，enterpriseregistration.fourthcoffee.com）。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-235">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="a7e5c-236">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-236">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e5c-237">3600</span><span class="sxs-lookup"><span data-stu-id="a7e5c-237">3600</span></span>  <br/> |<span data-ttu-id="a7e5c-238">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7e5c-238">CNAME</span></span>  <br/> |<span data-ttu-id="a7e5c-239">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a7e5c-239">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |

  
4. <span data-ttu-id="a7e5c-240">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-240">Select **Add Record**.</span></span>

5. <span data-ttu-id="a7e5c-241">逐一新增其餘五筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-241">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="a7e5c-242">在 [ **Add a record] （新增記錄**）區段中，使用表格中下一列的值來建立記錄，然後再選取 [**新增記錄**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-242">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
    <span data-ttu-id="a7e5c-243">重複這個程序，直到六筆 CNAME 記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-243">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a7e5c-244">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="a7e5c-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a7e5c-245"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e5c-245"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e5c-246">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a7e5c-247">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a7e5c-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="a7e5c-249">而是，請將必要的 Office 365 值新增至目前的記錄，以便擁有包含這兩組值的單一 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-249">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="a7e5c-250">需要範例？</span><span class="sxs-lookup"><span data-stu-id="a7e5c-250">Need examples?</span></span> <span data-ttu-id="a7e5c-251">請參閱這些 [Office 365 的外部網域名稱系統記錄](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-251">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="a7e5c-252">若要驗證您的 SPF 記錄，您可以使用其中一種 [SPF 驗證工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-252">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a7e5c-253">執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-253">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="a7e5c-254">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-254">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="a7e5c-255">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-255">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="a7e5c-256">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-256">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="a7e5c-257">您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-257">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="a7e5c-258">您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-258">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a7e5c-p126">若要讓 cPanel 與您的網域相關聯，要有一個 Hostgator 代管的帳戶。若要開始使用 Office 365，您可以從 Hostgator 購買代管帳戶或[重新委派您的名稱伺服器以指向 Office 365](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-p126">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="a7e5c-261">在 [**控制台**] 頁面的 [**網域**] 區域中，選取 [**高級區域編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-261">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="a7e5c-262">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-262">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a7e5c-263">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="a7e5c-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a7e5c-264">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-264">**Name**</span></span>|<span data-ttu-id="a7e5c-265">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-265">**TTL**</span></span>|<span data-ttu-id="a7e5c-266">**類型**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-266">**Type**</span></span>|<span data-ttu-id="a7e5c-267">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-267">**TXT Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7e5c-268">使用您的*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-268">Use your  *domain_name*.</span></span> <span data-ttu-id="a7e5c-269">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="a7e5c-269">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="a7e5c-270">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-270">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e5c-271">3600</span><span class="sxs-lookup"><span data-stu-id="a7e5c-271">3600</span></span>  <br/> |<span data-ttu-id="a7e5c-272">TXT</span><span class="sxs-lookup"><span data-stu-id="a7e5c-272">TXT</span></span>  <br/> |<span data-ttu-id="a7e5c-273">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a7e5c-273">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a7e5c-274">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-274">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
  
4. <span data-ttu-id="a7e5c-275">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-275">Select **Add Record**.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="a7e5c-276">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="a7e5c-276">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="a7e5c-277"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e5c-277"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e5c-278">執行此程序之前，您必須先執行本文中第一節的程序[＜將您的網域指向您的代管帳戶＞](#point-your-domain-to-your-hosting-account)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-278">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="a7e5c-279">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-279">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="a7e5c-280">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-280">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="a7e5c-281">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-281">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="a7e5c-282">您的 Nm-server-w15-cpanel-short 位址應該如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-282">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="a7e5c-283">您從 Hostgator 收到的註冊電子郵件將會指定該位址，而且**主控**頁面也可以使用 nm-server-w15-cpanel-short 連結。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-283">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a7e5c-p130">若要讓 cPanel 與您的網域相關聯，要有一個 Hostgator 代管的帳戶。若要開始使用 Office 365，您可以從 Hostgator 購買代管帳戶或[重新委派您的名稱伺服器以指向 Office 365](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-p130">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="a7e5c-286">在 [**控制台**] 頁面的 [**網域**] 區域中，選取 [**高級區域編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-286">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>

    
3. <span data-ttu-id="a7e5c-287">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-287">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="a7e5c-288">在 [ **ADVANCED DNS 區域編輯器**] 頁面上的 [**新增記錄**] 區域，于新記錄的方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-288">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="a7e5c-289">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="a7e5c-289">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a7e5c-290">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-290">**Name**</span></span>|<span data-ttu-id="a7e5c-291">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-291">**TTL**</span></span>|<span data-ttu-id="a7e5c-292">**類型**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-292">**Type**</span></span>|<span data-ttu-id="a7e5c-293">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="a7e5c-293">**Priority**</span></span>|<span data-ttu-id="a7e5c-294">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="a7e5c-294">**Weight**</span></span>|<span data-ttu-id="a7e5c-295">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="a7e5c-295">**Port**</span></span>|<span data-ttu-id="a7e5c-296">**Target** (目標)</span><span class="sxs-lookup"><span data-stu-id="a7e5c-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7e5c-297">_sip。 _tls。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-297">_sip._tls.</span></span> <span data-ttu-id="a7e5c-298">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-298">*domain_name*.</span></span> <span data-ttu-id="a7e5c-299">（例如 _sip，_tls fourthcoffee）</span><span class="sxs-lookup"><span data-stu-id="a7e5c-299">(for example, _sip._tls.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="a7e5c-300">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-300">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e5c-301">3600</span><span class="sxs-lookup"><span data-stu-id="a7e5c-301">3600</span></span>  <br/> |<span data-ttu-id="a7e5c-302">SRV</span><span class="sxs-lookup"><span data-stu-id="a7e5c-302">SRV</span></span>  <br/> |<span data-ttu-id="a7e5c-303">100</span><span class="sxs-lookup"><span data-stu-id="a7e5c-303">100</span></span>  <br/> |<span data-ttu-id="a7e5c-304">1 </span><span class="sxs-lookup"><span data-stu-id="a7e5c-304">1</span></span>  <br/> |<span data-ttu-id="a7e5c-305">443</span><span class="sxs-lookup"><span data-stu-id="a7e5c-305">443</span></span>  <br/> |<span data-ttu-id="a7e5c-306">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7e5c-306">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a7e5c-307">_sipfederationtls。 _tcp。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-307">_sipfederationtls._tcp.</span></span> <span data-ttu-id="a7e5c-308">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-308">*domain_name*.</span></span> <span data-ttu-id="a7e5c-309">（例如 _sipfederationtls，_tcp fourthcoffee）</span><span class="sxs-lookup"><span data-stu-id="a7e5c-309">(for example, _sipfederationtls._tcp.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="a7e5c-310">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a7e5c-310">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a7e5c-311">3600</span><span class="sxs-lookup"><span data-stu-id="a7e5c-311">3600</span></span>  <br/> |<span data-ttu-id="a7e5c-312">SRV</span><span class="sxs-lookup"><span data-stu-id="a7e5c-312">SRV</span></span>  <br/> |<span data-ttu-id="a7e5c-313">100</span><span class="sxs-lookup"><span data-stu-id="a7e5c-313">100</span></span>  <br/> |<span data-ttu-id="a7e5c-314">1 </span><span class="sxs-lookup"><span data-stu-id="a7e5c-314">1</span></span>  <br/> |<span data-ttu-id="a7e5c-315">5061</span><span class="sxs-lookup"><span data-stu-id="a7e5c-315">5061</span></span>  <br/> |<span data-ttu-id="a7e5c-316">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7e5c-316">sipfed.online.lync.com</span></span>  <br/> |
   

4. <span data-ttu-id="a7e5c-317">選取 [**新增記錄**]。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-317">Select **Add Record**.</span></span>

  
5. <span data-ttu-id="a7e5c-318">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-318">Add the other SRV record.</span></span>
    
    <span data-ttu-id="a7e5c-319">在 [ **Add a record] （新增記錄**）區段中，使用表格中下一列的值來建立記錄，然後再選取 [**新增記錄**] 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-319">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="a7e5c-320">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a7e5c-320">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a7e5c-321">而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-321">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a7e5c-322">在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e5c-322">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
