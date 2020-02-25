---
title: 建立 Azure DNS 區域的 DNS 記錄
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: 了解以驗證您的網域及設定 Azure DNS 區域在 Office 365 的電子郵件、 Skype for Business Online，與其他服務的 DNS 記錄。
ms.openlocfilehash: 3758b525bd98c724165f2671023ba416c338786d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239026"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="f14fc-103">建立 Azure DNS 區域的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="f14fc-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="f14fc-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="f14fc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f14fc-105">如果 Azure DNS 主機供應商，遵循的步驟中本篇文章以驗證您的網域和設定 DNS 記錄的電子郵件、 Skype for Business Online 等等。</span><span class="sxs-lookup"><span data-stu-id="f14fc-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f14fc-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="f14fc-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="f14fc-107">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="f14fc-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="f14fc-108">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="f14fc-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="f14fc-109">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="f14fc-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="f14fc-110">新增 Office 365 所需的四個 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="f14fc-110">Add the four CNAME records that are required for Office 365</span></span>](#add-the-four-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="f14fc-111">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="f14fc-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="f14fc-112">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="f14fc-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="f14fc-113">在 Azure 新增這些記錄之後，您的網域就是設定為搭配 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="f14fc-113">After you add these records at Azure, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f14fc-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f14fc-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f14fc-117">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="f14fc-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="f14fc-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="f14fc-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f14fc-119">您必須在您購買及註冊網域的網域註冊機構中執行此程序。</span><span class="sxs-lookup"><span data-stu-id="f14fc-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="f14fc-120">當您註冊 Azure 」 時，您建立 DNS 區域內，資源群組，然後指派給該資源群組的 [您的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="f14fc-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="f14fc-121">該網域名稱註冊到外部網域註冊機構中;Azure 不提供網域註冊服務。</span><span class="sxs-lookup"><span data-stu-id="f14fc-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="f14fc-122">若要確認並在 Office 365 建立 DNS 記錄為您的網域，您需要變更的名稱伺服器，在您網域註冊機構，讓他們使用 Azure 指派給您的資源群組的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="f14fc-122">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="f14fc-123">若要自行在網域註冊機構網站變更自家網域的名稱伺服器，請遵循下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="f14fc-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="f14fc-124">在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="f14fc-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="f14fc-125">在下列表格中，使用的值來建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，使其符合這些值。</span><span class="sxs-lookup"><span data-stu-id="f14fc-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="f14fc-126">指派給 Azure 的範例如下所示的名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="f14fc-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="f14fc-127">**第一個名稱伺服器：** 使用 Azure 由指派的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="f14fc-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="f14fc-128">**第二個名稱伺服器：** 使用 Azure 由指派的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="f14fc-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-DYN-BP-CONFIGURE-1-重新委派-1-1](../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="f14fc-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="f14fc-130">You should use at least two name server records.</span></span> <span data-ttu-id="f14fc-131">如果沒有列在您的網域註冊機構網站的任何其他名稱伺服器，您應該將予以刪除。</span><span class="sxs-lookup"><span data-stu-id="f14fc-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="f14fc-132">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="f14fc-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f14fc-p105">您的名稱伺服器記錄更新可能需要數小時的時間，才能更新到整個網際網路的 DNS 系統。接著，您的 Office 365 電子郵件和其他服務就能搭配您的網域順利運作。</span><span class="sxs-lookup"><span data-stu-id="f14fc-p105">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f14fc-135">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="f14fc-135">Add a TXT record for verification</span></span>
<span data-ttu-id="f14fc-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f14fc-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f14fc-p106">在您將自己的網域用於 Office 365 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Office 365 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="f14fc-p106">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f14fc-p107">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="f14fc-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f14fc-141">若要開始，使用[這個連結](https://portal.azure.com )移至您在 Azure 的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="f14fc-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="f14fc-142">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f14fc-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-1](../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="f14fc-144">使用**搜尋列**在 [**儀表板**] 頁面上，輸入**DNS 區域**中。</span><span class="sxs-lookup"><span data-stu-id="f14fc-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="f14fc-145">在結果中顯示，選取 [ **Services**部分的**DNS 區域**。</span><span class="sxs-lookup"><span data-stu-id="f14fc-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="f14fc-146">一旦您已被重新導向，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="f14fc-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-2](../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="f14fc-148">在您的網域，在 [ **DNS 區域**] 區域中，[**設定**] 頁面上選取 [ **+ 記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="f14fc-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-3](../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="f14fc-150">在 [**新增記錄集**] 區域中，於新記錄集的方塊中選取值從下表。</span><span class="sxs-lookup"><span data-stu-id="f14fc-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="f14fc-151">（從下拉式清單選擇 [**類型**] 和 [ **TTL 單位**值）。</span><span class="sxs-lookup"><span data-stu-id="f14fc-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f14fc-152">**Name**</span><span class="sxs-lookup"><span data-stu-id="f14fc-152">**Name**</span></span>|<span data-ttu-id="f14fc-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="f14fc-153">**Type**</span></span>|<span data-ttu-id="f14fc-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f14fc-154">**TTL**</span></span>|<span data-ttu-id="f14fc-155">**TTL 單位**</span><span class="sxs-lookup"><span data-stu-id="f14fc-155">**TTL unit**</span></span>|<span data-ttu-id="f14fc-156">**值**</span><span class="sxs-lookup"><span data-stu-id="f14fc-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f14fc-157">TXT</span><span class="sxs-lookup"><span data-stu-id="f14fc-157">TXT</span></span>  <br/> |<span data-ttu-id="f14fc-158">1</span><span class="sxs-lookup"><span data-stu-id="f14fc-158">1</span></span>  <br/> |<span data-ttu-id="f14fc-159">小時</span><span class="sxs-lookup"><span data-stu-id="f14fc-159">Hours</span></span>  <br/> |<span data-ttu-id="f14fc-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f14fc-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f14fc-161">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="f14fc-161">**Note:** This is an example.</span></span> <span data-ttu-id="f14fc-162">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span><span class="sxs-lookup"><span data-stu-id="f14fc-162">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="f14fc-163">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="f14fc-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-DYN-BP-CONFIGURE-1-確認-1-1](../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="f14fc-165">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f14fc-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="f14fc-166">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="f14fc-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f14fc-167">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="f14fc-167">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f14fc-168">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="f14fc-168">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f14fc-169">在系統管理中心，移至 [**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f14fc-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="f14fc-170">在 [**網域**] 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="f14fc-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f14fc-171">在 [**安裝**] 頁面上，選取 [**啟動安裝程式**。</span><span class="sxs-lookup"><span data-stu-id="f14fc-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f14fc-172">在 [**驗證網域**] 頁面上，選取 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="f14fc-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f14fc-p111">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f14fc-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="f14fc-176">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Office 365</span><span class="sxs-lookup"><span data-stu-id="f14fc-176">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="f14fc-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f14fc-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f14fc-178">若要開始，使用[這個連結](https://portal.azure.com )移至您在 Azure 的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="f14fc-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="f14fc-179">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f14fc-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-1](../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="f14fc-181">在 [**儀表板**] 頁面上**的所有資源**] 區域中，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="f14fc-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-2](../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="f14fc-183">在您的網域，在 [ **DNS 區域**] 區域中，[**設定**] 頁面上選取 [ **+ 記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="f14fc-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-3](../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="f14fc-185">在 [**新增記錄集**] 區域中，於新記錄集的方塊中選取值從下表。</span><span class="sxs-lookup"><span data-stu-id="f14fc-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="f14fc-186">（從下拉式清單選擇 [**類型**] 和 [ **TTL 單位**值）。</span><span class="sxs-lookup"><span data-stu-id="f14fc-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f14fc-187">**Name**</span><span class="sxs-lookup"><span data-stu-id="f14fc-187">**Name**</span></span>|<span data-ttu-id="f14fc-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="f14fc-188">**Type**</span></span>|<span data-ttu-id="f14fc-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f14fc-189">**TTL**</span></span>|<span data-ttu-id="f14fc-190">**TTL 單位**</span><span class="sxs-lookup"><span data-stu-id="f14fc-190">**TTL unit**</span></span>|<span data-ttu-id="f14fc-191">**喜好設定**</span><span class="sxs-lookup"><span data-stu-id="f14fc-191">**Preference**</span></span>|<span data-ttu-id="f14fc-192">**郵件交換**</span><span class="sxs-lookup"><span data-stu-id="f14fc-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f14fc-193">MX</span><span class="sxs-lookup"><span data-stu-id="f14fc-193">MX</span></span>  <br/> |<span data-ttu-id="f14fc-194">1</span><span class="sxs-lookup"><span data-stu-id="f14fc-194">1</span></span>  <br/> |<span data-ttu-id="f14fc-195">小時</span><span class="sxs-lookup"><span data-stu-id="f14fc-195">Hours</span></span>  <br/> |<span data-ttu-id="f14fc-196">10 </span><span class="sxs-lookup"><span data-stu-id="f14fc-196">10</span></span>  <br/> <span data-ttu-id="f14fc-197">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="f14fc-197">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="f14fc-198">*\<網域金鑰\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f14fc-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="f14fc-199">**附註：** 取得您*\<網域金鑰\>* 從您的 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="f14fc-199">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="f14fc-200">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="f14fc-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-DYN-BP-CONFIGURE-1-設定-2-1](../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="f14fc-202">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f14fc-202">Select **OK**.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-2-2](../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="f14fc-204">如果有任何其他 MX 記錄列在 [ **MX 記錄**] 區段中，您必須將它們刪除。</span><span class="sxs-lookup"><span data-stu-id="f14fc-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="f14fc-205">首先，在 [ **DNS 區域**] 區域中，選取 [ **MX 記錄設定**]。</span><span class="sxs-lookup"><span data-stu-id="f14fc-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-2-3](../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="f14fc-207">下一步]，選取您想要刪除的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="f14fc-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-2-4](../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="f14fc-209">選取 [**快顯功能表 （...）**]，然後選擇 [**移除**。</span><span class="sxs-lookup"><span data-stu-id="f14fc-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-2-5](../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="f14fc-211">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="f14fc-211">Select **Save**.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-2-6](../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="f14fc-213">新增 Office 365 所需的四個 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="f14fc-213">Add the four CNAME records that are required for Office 365</span></span>
<span data-ttu-id="f14fc-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f14fc-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f14fc-215">若要開始，使用[這個連結](https://portal.azure.com )移至您在 Azure 的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="f14fc-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="f14fc-216">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f14fc-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-1](../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="f14fc-218">在 [**儀表板**] 頁面上**的所有資源**] 區域中，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="f14fc-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-2](../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="f14fc-220">在您的網域，在 [ **DNS 區域**] 區域中，[**設定**] 頁面上選取 [ **+ 記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="f14fc-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-3](../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="f14fc-222">新增第一筆四筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="f14fc-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="f14fc-223">在 [**新增記錄集**] 區域中，於新記錄的方塊中設定、 輸入或複製並貼下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="f14fc-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="f14fc-224">（從下拉式清單選擇 [**類型**] 和 [ **TTL 單位**值）。</span><span class="sxs-lookup"><span data-stu-id="f14fc-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f14fc-225">**Name**</span><span class="sxs-lookup"><span data-stu-id="f14fc-225">**Name**</span></span>|<span data-ttu-id="f14fc-226">**Type**</span><span class="sxs-lookup"><span data-stu-id="f14fc-226">**Type**</span></span>|<span data-ttu-id="f14fc-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f14fc-227">**TTL**</span></span>|<span data-ttu-id="f14fc-228">**TTL 單位**</span><span class="sxs-lookup"><span data-stu-id="f14fc-228">**TTL unit**</span></span>|<span data-ttu-id="f14fc-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f14fc-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f14fc-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f14fc-230">autodiscover</span></span>  <br/> |<span data-ttu-id="f14fc-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="f14fc-231">CNAME</span></span>  <br/> |<span data-ttu-id="f14fc-232">1</span><span class="sxs-lookup"><span data-stu-id="f14fc-232">1</span></span>  <br/> |<span data-ttu-id="f14fc-233">小時</span><span class="sxs-lookup"><span data-stu-id="f14fc-233">Hours</span></span>  <br/> |<span data-ttu-id="f14fc-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f14fc-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="f14fc-235">sip</span><span class="sxs-lookup"><span data-stu-id="f14fc-235">sip</span></span>  <br/> |<span data-ttu-id="f14fc-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="f14fc-236">CNAME</span></span>  <br/> |<span data-ttu-id="f14fc-237">1</span><span class="sxs-lookup"><span data-stu-id="f14fc-237">1</span></span>  <br/> |<span data-ttu-id="f14fc-238">小時</span><span class="sxs-lookup"><span data-stu-id="f14fc-238">Hours</span></span>  <br/> |<span data-ttu-id="f14fc-239">sipdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="f14fc-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f14fc-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f14fc-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f14fc-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="f14fc-241">CNAME</span></span>  <br/> |<span data-ttu-id="f14fc-242">1</span><span class="sxs-lookup"><span data-stu-id="f14fc-242">1</span></span>  <br/> |<span data-ttu-id="f14fc-243">小時</span><span class="sxs-lookup"><span data-stu-id="f14fc-243">Hours</span></span>  <br/> |<span data-ttu-id="f14fc-244">webdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="f14fc-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-DYN-BP-CONFIGURE-1-設定-3-1](../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="f14fc-246">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f14fc-246">Select **OK**.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-3-2](../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="f14fc-248">新增每個其他三筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="f14fc-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="f14fc-249">在 [ **DNS 區域**] 區域中，選取 [ **+ 記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="f14fc-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="f14fc-250">然後，在空的記錄組中，在表格中，使用下一列的值來建立記錄，並再次選擇 **[確定]** 以完成該筆記錄。</span><span class="sxs-lookup"><span data-stu-id="f14fc-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="f14fc-251">重複此程序，直到四筆 CNAME 記錄全部建立完畢。</span><span class="sxs-lookup"><span data-stu-id="f14fc-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="f14fc-252">（選用）新增 MDM 2 的 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="f14fc-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f14fc-253">如果您有 Office 365 行動裝置管理 (MDM)，您必須建立兩個額外的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="f14fc-253">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="f14fc-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f14fc-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="f14fc-255">（如果您沒有 MDM，您可以略過此步驟。）</span><span class="sxs-lookup"><span data-stu-id="f14fc-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="f14fc-256">**Name**</span><span class="sxs-lookup"><span data-stu-id="f14fc-256">**Name**</span></span>|<span data-ttu-id="f14fc-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="f14fc-257">**Type**</span></span>|<span data-ttu-id="f14fc-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f14fc-258">**TTL**</span></span>|<span data-ttu-id="f14fc-259">**TTL 單位**</span><span class="sxs-lookup"><span data-stu-id="f14fc-259">**TTL unit**</span></span>|<span data-ttu-id="f14fc-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f14fc-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f14fc-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f14fc-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f14fc-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="f14fc-262">CNAME</span></span>  <br/> |<span data-ttu-id="f14fc-263">1</span><span class="sxs-lookup"><span data-stu-id="f14fc-263">1</span></span>  <br/> |<span data-ttu-id="f14fc-264">小時</span><span class="sxs-lookup"><span data-stu-id="f14fc-264">Hours</span></span>  <br/> |<span data-ttu-id="f14fc-265">enterpriseregistration.windows.net></span><span class="sxs-lookup"><span data-stu-id="f14fc-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="f14fc-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f14fc-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f14fc-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="f14fc-267">CNAME</span></span>  <br/> |<span data-ttu-id="f14fc-268">1</span><span class="sxs-lookup"><span data-stu-id="f14fc-268">1</span></span>  <br/> |<span data-ttu-id="f14fc-269">小時</span><span class="sxs-lookup"><span data-stu-id="f14fc-269">Hours</span></span>  <br/> |<span data-ttu-id="f14fc-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f14fc-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f14fc-271">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="f14fc-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f14fc-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f14fc-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f14fc-273">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="f14fc-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f14fc-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="f14fc-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f14fc-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="f14fc-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="f14fc-276">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="f14fc-276">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="f14fc-277">若要開始，使用[這個連結](https://portal.azure.com )移至您在 Azure 的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="f14fc-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="f14fc-278">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f14fc-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-1](../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="f14fc-280">在 [**儀表板**] 頁面上**的所有資源**] 區域中，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="f14fc-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-2](../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="f14fc-282">在 [ **DNS 區域**] 區域中，選取 [ **TXT 記錄設定**]。</span><span class="sxs-lookup"><span data-stu-id="f14fc-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-4-1](../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="f14fc-284">在 [**記錄設定內容**區域中，於新記錄集的方塊中選取值從下表。</span><span class="sxs-lookup"><span data-stu-id="f14fc-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="f14fc-285">（從下拉式清單選擇 [**類型**] 和 [ **TTL 單位**值）。</span><span class="sxs-lookup"><span data-stu-id="f14fc-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f14fc-286">**Name**</span><span class="sxs-lookup"><span data-stu-id="f14fc-286">**Name**</span></span>|<span data-ttu-id="f14fc-287">**Type**</span><span class="sxs-lookup"><span data-stu-id="f14fc-287">**Type**</span></span>|<span data-ttu-id="f14fc-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f14fc-288">**TTL**</span></span>|<span data-ttu-id="f14fc-289">**TTL 單位**</span><span class="sxs-lookup"><span data-stu-id="f14fc-289">**TTL unit**</span></span>|<span data-ttu-id="f14fc-290">**值**</span><span class="sxs-lookup"><span data-stu-id="f14fc-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f14fc-291">TXT</span><span class="sxs-lookup"><span data-stu-id="f14fc-291">TXT</span></span>  <br/> |<span data-ttu-id="f14fc-292">1</span><span class="sxs-lookup"><span data-stu-id="f14fc-292">1</span></span>  <br/> |<span data-ttu-id="f14fc-293">小時</span><span class="sxs-lookup"><span data-stu-id="f14fc-293">Hours</span></span>  <br/> |<span data-ttu-id="f14fc-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f14fc-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f14fc-295">**附註：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="f14fc-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-DYN-BP-CONFIGURE-1-設定-4-2](../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="f14fc-297">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="f14fc-297">Select **Save**.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-4-3](../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="f14fc-299">新增兩筆 Office 365 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="f14fc-299">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="f14fc-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f14fc-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="f14fc-301">若要開始，使用[這個連結](https://portal.azure.com )移至您在 Azure 的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="f14fc-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="f14fc-302">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f14fc-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-1](../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="f14fc-304">在 [**儀表板**] 頁面上**的所有資源**] 區域中，選取您想要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="f14fc-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-2](../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="f14fc-306">在您的網域，在 [ **DNS 區域**] 區域中，[**設定**] 頁面上選取 [ **+ 記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="f14fc-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-1-3](../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="f14fc-308">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="f14fc-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="f14fc-309">在 [**新增記錄集**] 區域中，於新記錄集的方塊中選取值從下表中的第一列。</span><span class="sxs-lookup"><span data-stu-id="f14fc-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="f14fc-310">（從下拉式清單選擇 [**類型**] 和 [ **TTL 單位**值）。</span><span class="sxs-lookup"><span data-stu-id="f14fc-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f14fc-311">**Name**</span><span class="sxs-lookup"><span data-stu-id="f14fc-311">**Name**</span></span>|<span data-ttu-id="f14fc-312">**Type**</span><span class="sxs-lookup"><span data-stu-id="f14fc-312">**Type**</span></span>|<span data-ttu-id="f14fc-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f14fc-313">**TTL**</span></span>|<span data-ttu-id="f14fc-314">**TTL 單位**</span><span class="sxs-lookup"><span data-stu-id="f14fc-314">**TTL unit**</span></span>|<span data-ttu-id="f14fc-315">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="f14fc-315">**Priority**</span></span>|<span data-ttu-id="f14fc-316">**Weight**</span><span class="sxs-lookup"><span data-stu-id="f14fc-316">**Weight**</span></span>|<span data-ttu-id="f14fc-317">**Port**</span><span class="sxs-lookup"><span data-stu-id="f14fc-317">**Port**</span></span>|<span data-ttu-id="f14fc-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="f14fc-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f14fc-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="f14fc-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="f14fc-320">SRV</span><span class="sxs-lookup"><span data-stu-id="f14fc-320">SRV</span></span>  <br/> |<span data-ttu-id="f14fc-321">1</span><span class="sxs-lookup"><span data-stu-id="f14fc-321">1</span></span>  <br/> |<span data-ttu-id="f14fc-322">小時</span><span class="sxs-lookup"><span data-stu-id="f14fc-322">Hours</span></span>  <br/> |<span data-ttu-id="f14fc-323">100</span><span class="sxs-lookup"><span data-stu-id="f14fc-323">100</span></span>  <br/> |<span data-ttu-id="f14fc-324">1</span><span class="sxs-lookup"><span data-stu-id="f14fc-324">1</span></span>  <br/> |<span data-ttu-id="f14fc-325">443</span><span class="sxs-lookup"><span data-stu-id="f14fc-325">443</span></span>  <br/> |<span data-ttu-id="f14fc-326">sipdir.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="f14fc-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f14fc-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="f14fc-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="f14fc-328">SRV</span><span class="sxs-lookup"><span data-stu-id="f14fc-328">SRV</span></span>  <br/> |<span data-ttu-id="f14fc-329">1</span><span class="sxs-lookup"><span data-stu-id="f14fc-329">1</span></span>  <br/> |<span data-ttu-id="f14fc-330">小時</span><span class="sxs-lookup"><span data-stu-id="f14fc-330">Hours</span></span>  <br/> |<span data-ttu-id="f14fc-331">100</span><span class="sxs-lookup"><span data-stu-id="f14fc-331">100</span></span>  <br/> |<span data-ttu-id="f14fc-332">1</span><span class="sxs-lookup"><span data-stu-id="f14fc-332">1</span></span>  <br/> |<span data-ttu-id="f14fc-333">5061</span><span class="sxs-lookup"><span data-stu-id="f14fc-333">5061</span></span>  <br/> |<span data-ttu-id="f14fc-334">sipfed.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="f14fc-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-DYN-BP-CONFIGURE-1-設定-5-1](../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="f14fc-336">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f14fc-336">Select **OK**.</span></span>
    
    ![Azure-DYN-BP-CONFIGURE-1-設定-5-2](../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="f14fc-338">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="f14fc-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="f14fc-339">在新記錄方塊中，輸入或複製並貼上表格中第二列中的值。</span><span class="sxs-lookup"><span data-stu-id="f14fc-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f14fc-p120">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f14fc-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
