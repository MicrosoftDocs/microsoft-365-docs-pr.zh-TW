---
title: 建立 Azure DNS 區域的 DNS 記錄
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 及其他服務的 DNS 記錄，以供 Microsoft 用 Azure DNS 區域。
ms.openlocfilehash: 40fadb81ebd0ae5385bbbdad727b1c579142b227
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645668"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="28964-103">建立 Azure DNS 區域的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="28964-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="28964-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="28964-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="28964-105">如果 Azure 是您的 DNS 主機服務提供者，請遵循本文中的步驟來驗證您的網域，並設定電子郵件、商務用 Skype Online 等的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="28964-106">以下是要新增的主要記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="28964-107">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="28964-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="28964-108">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="28964-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="28964-109">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="28964-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="28964-110">新增 Microsoft 所需的四種 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="28964-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="28964-111">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="28964-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="28964-112">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="28964-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="28964-113">在 Azure 新增這些記錄之後，您的網域就會設定為與 Microsoft 服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="28964-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="28964-p101">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="28964-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="28964-117">變更您網域的名稱伺服器 (NS) 記錄</span><span class="sxs-lookup"><span data-stu-id="28964-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="28964-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="28964-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="28964-119">您必須在您購買及註冊網域的網域註冊機構中執行此程序。</span><span class="sxs-lookup"><span data-stu-id="28964-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="28964-120">當您註冊 Azure 時，您會在 DNS 區域中建立資源群組，然後將您的功能變數名稱指派給該資源群組。</span><span class="sxs-lookup"><span data-stu-id="28964-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="28964-121">該功能變數名稱已註冊到外部網域註冊機構;Azure 不提供網域註冊服務。</span><span class="sxs-lookup"><span data-stu-id="28964-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="28964-122">若要在 Microsoft 中驗證及建立網域的 DNS 記錄，您必須先在您的網域註冊機構中變更名稱伺服器，以便使用指派給您資源群組的 Azure 名稱伺服器。</span><span class="sxs-lookup"><span data-stu-id="28964-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="28964-123">若要自行在網域註冊機構網站變更自家網域的名稱伺服器，請遵循下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="28964-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="28964-124">在網域註冊機構的網站上，找出您可編輯您網域之名稱伺服器的區域。</span><span class="sxs-lookup"><span data-stu-id="28964-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="28964-125">您可以使用下表中的值建立兩筆名稱伺服器記錄，或編輯現有的名稱伺服器記錄，使其符合這些值。</span><span class="sxs-lookup"><span data-stu-id="28964-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="28964-126">Azure 指派名稱伺服器的範例如下所示。</span><span class="sxs-lookup"><span data-stu-id="28964-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="28964-127">**第一個** 名稱伺服器：使用 Azure 所指派的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="28964-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="28964-128">**第二個** 名稱伺服器：使用 Azure 所指派的名稱伺服器值。</span><span class="sxs-lookup"><span data-stu-id="28964-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-重新委派-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="28964-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="28964-130">You should use at least two name server records.</span></span> <span data-ttu-id="28964-131">如果您的網域註冊機構網站上列出任何其他名稱伺服器，您應該將其刪除。</span><span class="sxs-lookup"><span data-stu-id="28964-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="28964-132">儲存變更。</span><span class="sxs-lookup"><span data-stu-id="28964-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="28964-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="28964-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="28964-134">然後，您的 Microsoft 電子郵件和其他服務將全部設定為與您的網域搭配使用。</span><span class="sxs-lookup"><span data-stu-id="28964-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="28964-135">新增 TXT 記錄以供驗證</span><span class="sxs-lookup"><span data-stu-id="28964-135">Add a TXT record for verification</span></span>
<span data-ttu-id="28964-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="28964-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="28964-p106">在您將自己的網域用於 Microsoft 之前，我們必須先確認您擁有該網域。如果您能在自己的網域註冊機構登入自己的帳戶並能建立 DNS 記錄，Microsoft 就能確信您擁有該網域。</span><span class="sxs-lookup"><span data-stu-id="28964-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="28964-p107">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。您可以選擇稍後再刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="28964-141">若要開始使用，請使用 [此連結](https://portal.azure.com )前往 Azure 上的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="28964-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="28964-142">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="28964-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="28964-144">使用 [**儀表板**] 頁面上的**搜尋**列，輸入 [ **DNS 區域**]。</span><span class="sxs-lookup"><span data-stu-id="28964-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="28964-145">在 [結果顯示] 中，選取 [**服務**] 部分底下的 [ **DNS 區域**]。</span><span class="sxs-lookup"><span data-stu-id="28964-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="28964-146">重新導向後，請選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="28964-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="28964-148">在您網域的 [ **設定** ] 頁面上，選取 [ **DNS 區域** ] 區域中的 [ **+ 記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="28964-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="28964-150">在 [新增 **記錄集** ] 區域，于新記錄集的方塊中，選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="28964-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="28964-151"> (從下拉式清單中選擇 [ **類型** ] 和 [ **TTL 單位** ] 值。 ) </span><span class="sxs-lookup"><span data-stu-id="28964-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="28964-152">**名稱**</span><span class="sxs-lookup"><span data-stu-id="28964-152">**Name**</span></span>|<span data-ttu-id="28964-153">**類型**</span><span class="sxs-lookup"><span data-stu-id="28964-153">**Type**</span></span>|<span data-ttu-id="28964-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="28964-154">**TTL**</span></span>|<span data-ttu-id="28964-155">**TTL 單位**</span><span class="sxs-lookup"><span data-stu-id="28964-155">**TTL unit**</span></span>|<span data-ttu-id="28964-156">**Value**</span><span class="sxs-lookup"><span data-stu-id="28964-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="28964-157">TXT</span><span class="sxs-lookup"><span data-stu-id="28964-157">TXT</span></span>  <br/> |<span data-ttu-id="28964-158">1 </span><span class="sxs-lookup"><span data-stu-id="28964-158">1</span></span>  <br/> |<span data-ttu-id="28964-159">小時</span><span class="sxs-lookup"><span data-stu-id="28964-159">Hours</span></span>  <br/> |<span data-ttu-id="28964-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="28964-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="28964-161">**附註：** 這是範例。</span><span class="sxs-lookup"><span data-stu-id="28964-161">**Note:** This is an example.</span></span> <span data-ttu-id="28964-162">在這裡請使用您自己來自表格的 **[目的地或指向位址]** 值。</span><span class="sxs-lookup"><span data-stu-id="28964-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="28964-163">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="28964-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="28964-165">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28964-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="28964-166">繼續進行之前，請先稍候幾分鐘，好讓您剛剛建立的記錄能在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="28964-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="28964-167">現在您已在網域註冊機構網站新增記錄，請返回 Microsoft 並要求該記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="28964-168">在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。</span><span class="sxs-lookup"><span data-stu-id="28964-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="28964-169">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="28964-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="28964-170">在 **[網域]** 頁面上，選取您要驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="28964-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="28964-171">在 **[設定]** 頁面上，選取 **[開始設定]**。</span><span class="sxs-lookup"><span data-stu-id="28964-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="28964-172">在 **[驗證網域]** 頁面上，選取 **[驗證]**。</span><span class="sxs-lookup"><span data-stu-id="28964-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="28964-p111">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="28964-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="28964-176">新增 MX 記錄，以將寄往您網域的電子郵件轉至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="28964-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="28964-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="28964-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="28964-178">若要開始使用，請使用 [此連結](https://portal.azure.com )前往 Azure 上的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="28964-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="28964-179">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="28964-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="28964-181">在 [ **儀表板** ] 頁面上的 [ **所有資源** ] 區域中，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="28964-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="28964-183">在您網域的 [ **設定** ] 頁面上，選取 [ **DNS 區域** ] 區域中的 [ **+ 記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="28964-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="28964-185">在 [新增 **記錄集** ] 區域，于新記錄集的方塊中，選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="28964-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="28964-186"> (從下拉式清單中選擇 [ **類型** ] 和 [ **TTL 單位** ] 值。 ) </span><span class="sxs-lookup"><span data-stu-id="28964-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="28964-187">**名稱**</span><span class="sxs-lookup"><span data-stu-id="28964-187">**Name**</span></span>|<span data-ttu-id="28964-188">**類型**</span><span class="sxs-lookup"><span data-stu-id="28964-188">**Type**</span></span>|<span data-ttu-id="28964-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="28964-189">**TTL**</span></span>|<span data-ttu-id="28964-190">**TTL 單位**</span><span class="sxs-lookup"><span data-stu-id="28964-190">**TTL unit**</span></span>|<span data-ttu-id="28964-191">**偏好**</span><span class="sxs-lookup"><span data-stu-id="28964-191">**Preference**</span></span>|<span data-ttu-id="28964-192">**郵件交換**</span><span class="sxs-lookup"><span data-stu-id="28964-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="28964-193">MX</span><span class="sxs-lookup"><span data-stu-id="28964-193">MX</span></span>  <br/> |<span data-ttu-id="28964-194">1 </span><span class="sxs-lookup"><span data-stu-id="28964-194">1</span></span>  <br/> |<span data-ttu-id="28964-195">小時</span><span class="sxs-lookup"><span data-stu-id="28964-195">Hours</span></span>  <br/> |<span data-ttu-id="28964-196">10 </span><span class="sxs-lookup"><span data-stu-id="28964-196">10</span></span>  <br/> <span data-ttu-id="28964-197">如需關於優先順序的詳細資訊，請參閱[什麼是 MX 優先順序？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="28964-197">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="28964-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="28964-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="28964-199">\**附注：\*\*\*\<domain-key\>* 從您的 Microsoft 帳戶取得。</span><span class="sxs-lookup"><span data-stu-id="28964-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="28964-200">如何找到呢？</span><span class="sxs-lookup"><span data-stu-id="28964-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="28964-202">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28964-202">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="28964-204">如果 [ **Mx 記錄** ] 區段中列出任何其他 MX 記錄，您必須加以刪除。</span><span class="sxs-lookup"><span data-stu-id="28964-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="28964-205">首先，在 [ **DNS 區域** ] 區域中，選取 **MX 記錄集**。</span><span class="sxs-lookup"><span data-stu-id="28964-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-Configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="28964-207">接下來，選取您要刪除的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-Configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="28964-209">選取 \*\*快顯功能表 ( ... ) \*\*，然後選擇 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="28964-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-Configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="28964-211">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="28964-211">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="28964-213">新增 Microsoft 所需的四種 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="28964-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="28964-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="28964-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="28964-215">若要開始使用，請使用 [此連結](https://portal.azure.com )前往 Azure 上的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="28964-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="28964-216">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="28964-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="28964-218">在 [ **儀表板** ] 頁面上的 [ **所有資源** ] 區域中，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="28964-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="28964-220">在您網域的 [ **設定** ] 頁面上，選取 [ **DNS 區域** ] 區域中的 [ **+ 記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="28964-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="28964-222">新增四筆 CNAME 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="28964-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="28964-223">在 [新增 **記錄集** ] 區域，于新記錄集的方塊中，輸入或複製並貼上下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="28964-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="28964-224"> (從下拉式清單中選擇 [ **類型** ] 和 [ **TTL 單位** ] 值。 ) </span><span class="sxs-lookup"><span data-stu-id="28964-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="28964-225">**名稱**</span><span class="sxs-lookup"><span data-stu-id="28964-225">**Name**</span></span>|<span data-ttu-id="28964-226">**類型**</span><span class="sxs-lookup"><span data-stu-id="28964-226">**Type**</span></span>|<span data-ttu-id="28964-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="28964-227">**TTL**</span></span>|<span data-ttu-id="28964-228">**TTL 單位**</span><span class="sxs-lookup"><span data-stu-id="28964-228">**TTL unit**</span></span>|<span data-ttu-id="28964-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="28964-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="28964-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="28964-230">autodiscover</span></span>  <br/> |<span data-ttu-id="28964-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="28964-231">CNAME</span></span>  <br/> |<span data-ttu-id="28964-232">1 </span><span class="sxs-lookup"><span data-stu-id="28964-232">1</span></span>  <br/> |<span data-ttu-id="28964-233">小時</span><span class="sxs-lookup"><span data-stu-id="28964-233">Hours</span></span>  <br/> |<span data-ttu-id="28964-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="28964-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="28964-235">sip</span><span class="sxs-lookup"><span data-stu-id="28964-235">sip</span></span>  <br/> |<span data-ttu-id="28964-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="28964-236">CNAME</span></span>  <br/> |<span data-ttu-id="28964-237">1 </span><span class="sxs-lookup"><span data-stu-id="28964-237">1</span></span>  <br/> |<span data-ttu-id="28964-238">小時</span><span class="sxs-lookup"><span data-stu-id="28964-238">Hours</span></span>  <br/> |<span data-ttu-id="28964-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="28964-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="28964-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="28964-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="28964-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="28964-241">CNAME</span></span>  <br/> |<span data-ttu-id="28964-242">1 </span><span class="sxs-lookup"><span data-stu-id="28964-242">1</span></span>  <br/> |<span data-ttu-id="28964-243">小時</span><span class="sxs-lookup"><span data-stu-id="28964-243">Hours</span></span>  <br/> |<span data-ttu-id="28964-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="28964-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-Configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="28964-246">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28964-246">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="28964-248">新增其他三筆 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="28964-249">在 [ **DNS 區域** ] 區域中，選取 [ **+ 記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="28964-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="28964-250">然後，在空白的記錄集中，使用表格中下一列的值來建立記錄，然後再選取 **[確定]** 以完成記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="28964-251">重複此程式，直到您已建立所有四筆 CNAME 記錄為止。</span><span class="sxs-lookup"><span data-stu-id="28964-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="28964-252"> (選用) 新增兩個 MDM 的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="28964-253">如果您有適用于 Microsoft 的行動裝置管理 (MDM) ，則必須建立兩個額外的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="28964-254">請按照您針對其他四筆 CNAME 記錄所進行的程序執行，但提供下表的值。</span><span class="sxs-lookup"><span data-stu-id="28964-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="28964-255"> (如果您沒有 MDM，您可以略過此步驟。 ) </span><span class="sxs-lookup"><span data-stu-id="28964-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="28964-256">**名稱**</span><span class="sxs-lookup"><span data-stu-id="28964-256">**Name**</span></span>|<span data-ttu-id="28964-257">**類型**</span><span class="sxs-lookup"><span data-stu-id="28964-257">**Type**</span></span>|<span data-ttu-id="28964-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="28964-258">**TTL**</span></span>|<span data-ttu-id="28964-259">**TTL 單位**</span><span class="sxs-lookup"><span data-stu-id="28964-259">**TTL unit**</span></span>|<span data-ttu-id="28964-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="28964-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28964-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="28964-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="28964-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="28964-262">CNAME</span></span>  <br/> |<span data-ttu-id="28964-263">1 </span><span class="sxs-lookup"><span data-stu-id="28964-263">1</span></span>  <br/> |<span data-ttu-id="28964-264">小時</span><span class="sxs-lookup"><span data-stu-id="28964-264">Hours</span></span>  <br/> |<span data-ttu-id="28964-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="28964-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="28964-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="28964-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="28964-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="28964-267">CNAME</span></span>  <br/> |<span data-ttu-id="28964-268">1 </span><span class="sxs-lookup"><span data-stu-id="28964-268">1</span></span>  <br/> |<span data-ttu-id="28964-269">小時</span><span class="sxs-lookup"><span data-stu-id="28964-269">Hours</span></span>  <br/> |<span data-ttu-id="28964-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="28964-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="28964-271">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="28964-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="28964-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="28964-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="28964-273">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="28964-274">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="28964-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="28964-275">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="28964-276">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="28964-277">若要開始使用，請使用 [此連結](https://portal.azure.com )前往 Azure 上的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="28964-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="28964-278">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="28964-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="28964-280">在 [ **儀表板** ] 頁面上的 [ **所有資源** ] 區域中，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="28964-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="28964-282">在 [ **DNS 區域** ] 區域中，選取 **TXT 記錄集**。</span><span class="sxs-lookup"><span data-stu-id="28964-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-Configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="28964-284">在 [ **記錄集屬性** ] 區域的新記錄集方塊中，選取下表中的值。</span><span class="sxs-lookup"><span data-stu-id="28964-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="28964-285"> (從下拉式清單中選擇 [ **類型** ] 和 [ **TTL 單位** ] 值。 ) </span><span class="sxs-lookup"><span data-stu-id="28964-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="28964-286">**名稱**</span><span class="sxs-lookup"><span data-stu-id="28964-286">**Name**</span></span>|<span data-ttu-id="28964-287">**類型**</span><span class="sxs-lookup"><span data-stu-id="28964-287">**Type**</span></span>|<span data-ttu-id="28964-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="28964-288">**TTL**</span></span>|<span data-ttu-id="28964-289">**TTL 單位**</span><span class="sxs-lookup"><span data-stu-id="28964-289">**TTL unit**</span></span>|<span data-ttu-id="28964-290">**Value**</span><span class="sxs-lookup"><span data-stu-id="28964-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="28964-291">TXT</span><span class="sxs-lookup"><span data-stu-id="28964-291">TXT</span></span>  <br/> |<span data-ttu-id="28964-292">1 </span><span class="sxs-lookup"><span data-stu-id="28964-292">1</span></span>  <br/> |<span data-ttu-id="28964-293">小時</span><span class="sxs-lookup"><span data-stu-id="28964-293">Hours</span></span>  <br/> |<span data-ttu-id="28964-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="28964-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="28964-295">**注意：** 建議您複製並貼上這個項目，好讓所有的間距保持正確。</span><span class="sxs-lookup"><span data-stu-id="28964-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-Configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="28964-297">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="28964-297">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="28964-299">新增兩筆 Microsoft 所需的 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="28964-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="28964-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="28964-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="28964-301">若要開始使用，請使用 [此連結](https://portal.azure.com )前往 Azure 上的網域頁面。</span><span class="sxs-lookup"><span data-stu-id="28964-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="28964-302">系統會提示您先登入。</span><span class="sxs-lookup"><span data-stu-id="28964-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="28964-304">在 [ **儀表板** ] 頁面上的 [ **所有資源** ] 區域中，選取您要更新的網域。</span><span class="sxs-lookup"><span data-stu-id="28964-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="28964-306">在您網域的 [ **設定** ] 頁面上，選取 [ **DNS 區域** ] 區域中的 [ **+ 記錄集**]。</span><span class="sxs-lookup"><span data-stu-id="28964-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="28964-308">新增兩筆 SRV 記錄中的第一筆。</span><span class="sxs-lookup"><span data-stu-id="28964-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="28964-309">在 [新增 **記錄集** ] 區域，于新記錄集的方塊中，選取下表中第一列的值。</span><span class="sxs-lookup"><span data-stu-id="28964-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="28964-310"> (從下拉式清單中選擇 [ **類型** ] 和 [ **TTL 單位** ] 值。 ) </span><span class="sxs-lookup"><span data-stu-id="28964-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="28964-311">**名稱**</span><span class="sxs-lookup"><span data-stu-id="28964-311">**Name**</span></span>|<span data-ttu-id="28964-312">**類型**</span><span class="sxs-lookup"><span data-stu-id="28964-312">**Type**</span></span>|<span data-ttu-id="28964-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="28964-313">**TTL**</span></span>|<span data-ttu-id="28964-314">**TTL 單位**</span><span class="sxs-lookup"><span data-stu-id="28964-314">**TTL unit**</span></span>|<span data-ttu-id="28964-315">**Priority** (優先順序)</span><span class="sxs-lookup"><span data-stu-id="28964-315">**Priority**</span></span>|<span data-ttu-id="28964-316">**Weight** (權數)</span><span class="sxs-lookup"><span data-stu-id="28964-316">**Weight**</span></span>|<span data-ttu-id="28964-317">**Port** (連接埠)</span><span class="sxs-lookup"><span data-stu-id="28964-317">**Port**</span></span>|<span data-ttu-id="28964-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="28964-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="28964-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="28964-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="28964-320">SRV</span><span class="sxs-lookup"><span data-stu-id="28964-320">SRV</span></span>  <br/> |<span data-ttu-id="28964-321">1 </span><span class="sxs-lookup"><span data-stu-id="28964-321">1</span></span>  <br/> |<span data-ttu-id="28964-322">小時</span><span class="sxs-lookup"><span data-stu-id="28964-322">Hours</span></span>  <br/> |<span data-ttu-id="28964-323">100</span><span class="sxs-lookup"><span data-stu-id="28964-323">100</span></span>  <br/> |<span data-ttu-id="28964-324">1 </span><span class="sxs-lookup"><span data-stu-id="28964-324">1</span></span>  <br/> |<span data-ttu-id="28964-325">443</span><span class="sxs-lookup"><span data-stu-id="28964-325">443</span></span>  <br/> |<span data-ttu-id="28964-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="28964-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="28964-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="28964-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="28964-328">SRV</span><span class="sxs-lookup"><span data-stu-id="28964-328">SRV</span></span>  <br/> |<span data-ttu-id="28964-329">1 </span><span class="sxs-lookup"><span data-stu-id="28964-329">1</span></span>  <br/> |<span data-ttu-id="28964-330">小時</span><span class="sxs-lookup"><span data-stu-id="28964-330">Hours</span></span>  <br/> |<span data-ttu-id="28964-331">100</span><span class="sxs-lookup"><span data-stu-id="28964-331">100</span></span>  <br/> |<span data-ttu-id="28964-332">1 </span><span class="sxs-lookup"><span data-stu-id="28964-332">1</span></span>  <br/> |<span data-ttu-id="28964-333">5061</span><span class="sxs-lookup"><span data-stu-id="28964-333">5061</span></span>  <br/> |<span data-ttu-id="28964-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="28964-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-Configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="28964-336">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28964-336">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="28964-338">新增另一筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="28964-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="28964-339">在新記錄的方塊中，輸入或複製並貼上表格中第二列的值。</span><span class="sxs-lookup"><span data-stu-id="28964-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="28964-p120">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="28964-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
