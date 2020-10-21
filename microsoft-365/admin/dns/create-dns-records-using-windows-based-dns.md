---
title: 使用以 Windows 為基礎的 DNS 建立 Microsoft 的 DNS 記錄
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以在 Microsoft 的 Windows 基礎 DNS 上進行。
ms.openlocfilehash: 471aa0323bd59b09c672431ef39bb33f5c89b555
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645572"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a><span data-ttu-id="9c6a8-103">使用以 Windows 為基礎的 DNS 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="9c6a8-103">Create DNS records for Microsoft using Windows-based DNS</span></span>

 <span data-ttu-id="9c6a8-104">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
   
<span data-ttu-id="9c6a8-105">如果您使用 Windows 型 DNS 託管自己的 DNS 記錄，請按照本文的步驟設定您電子郵件的記錄、商務用 Skype Online 等。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-105">If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9c6a8-106">若要開始，您必須 [在 Windows 型 dns 中尋找您的 dns 記錄](#find-your-dns-records-in-windows-based-dns) ，以便您進行更新。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-106">To get started, you need to [find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns) so you can update them.</span></span> <span data-ttu-id="9c6a8-107">此外，如果您想要將內部部署的 Active Directory 與 Microsoft 同步處理，請參閱 [在您的部署 Active directory 中做為 UPN 的非路由電子郵件地址](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-107">Also, if you're planning to synchronize your on-premises Active Directory with Microsoft, see [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).</span></span>
  
<span data-ttu-id="9c6a8-108">新增 DNS 記錄後，出現郵件流程或其他問題的相關問題，請參閱 [疑難排解變更功能變數名稱或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-108">Trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a><span data-ttu-id="9c6a8-109">在 Windows 架構的 DNS 中尋您的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="9c6a8-109">Find your DNS records in Windows-based DNS</span></span>
<span data-ttu-id="9c6a8-110"><a name="BKMK_find_your_dns_1"> </a>移至具有您網域之 DNS 記錄的頁面。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-110"><a name="BKMK_find_your_dns_1"> </a> Go to the page that has the DNS records for your domain.</span></span> <span data-ttu-id="9c6a8-111">如果您是在 Windows Server 2008 中工作，請移至**開始**  >  **執行**。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-111">If you're working in Windows Server 2008, go to **Start** > **Run**.</span></span> <span data-ttu-id="9c6a8-112">如果您是在 Windows Server 2012 中工作，請按 Windows 鍵和 **r**。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span></span> <span data-ttu-id="9c6a8-113">輸入 **dnsmgmnt**，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-113">Type **dnsmgmnt.msc**, and then select **OK**.</span></span> <span data-ttu-id="9c6a8-114">在 [DNS 管理員] 中，展開 [ \*\* \<DNS server name\> \> 正向對應區域  \*\*]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-114">In DNS Manager, expand **\<DNS server name\>  \> Forward Lookup Zones**.</span></span> <span data-ttu-id="9c6a8-115">選取您的網域。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-115">Select your domain.</span></span> <span data-ttu-id="9c6a8-116">您現在可以建立 DNS 記錄了！</span><span class="sxs-lookup"><span data-stu-id="9c6a8-116">You're now ready to create the DNS records.</span></span>
   
## <a name="add-mx-record"></a><span data-ttu-id="9c6a8-117">新增 MX 記錄</span><span class="sxs-lookup"><span data-stu-id="9c6a8-117">Add MX record</span></span>
<span data-ttu-id="9c6a8-118"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9c6a8-118"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="9c6a8-119">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-119">Add an MX record so email for your domain will come to Microsoft.</span></span>
- <span data-ttu-id="9c6a8-120">您將新增的 MX 記錄會包含值 () 的 [ **點數** ] 值，此值如下所示： \<MX token\> MSxxxxxxx，其中 \<MX token\> 是類似的值。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-120">The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.</span></span> 
- <span data-ttu-id="9c6a8-121">從 Microsoft 的 [新增 DNS 記錄] 頁面的 [Exchange Online] 區段中的 [MX] 列中，複製列于 [位址] 底下的值。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-121">From the MX row in the Exchange Online section of the Add DNS records page in Microsoft, copy the value listed under Points to address.</span></span> <span data-ttu-id="9c6a8-122">您將會在您要建立的記錄中使用此值。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-122">You'll use this value in the record you're creating in this task.</span></span> 
- <span data-ttu-id="9c6a8-123">在網域的 [DNS 管理員] 頁面上，移至 [**動作**  >  \*\*郵件交換器 (MX) \*\*]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-123">On the DNS Manager page for the domain, go to **Action** > **Mail Exchanger (MX)**.</span></span> <span data-ttu-id="9c6a8-124">若要尋找網域的此頁面，請參閱 [在 Windows 型 dns 中尋找您的 DNS 記錄](#find-your-dns-records-in-windows-based-dns)。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-124">To find this page for the domain, see [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).</span></span>  
- <span data-ttu-id="9c6a8-125">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="9c6a8-125">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span> 
    - <span data-ttu-id="9c6a8-126">主機名稱: </span><span class="sxs-lookup"><span data-stu-id="9c6a8-126">Host Name:</span></span> 
    - <span data-ttu-id="9c6a8-127">@Address：將點貼到您剛剛從 Microsoft 複製的位址值。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-127">@Address: Paste the Points to address  value that you just copied from Microsoft here.</span></span>  
    - <span data-ttu-id="9c6a8-128">Pref:</span><span class="sxs-lookup"><span data-stu-id="9c6a8-128">Pref:</span></span> 
- <span data-ttu-id="9c6a8-129">選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-129">Select **Save Changes**.</span></span>
- <span data-ttu-id="9c6a8-130">移除任何過時的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-130">Remove any obsolete MX records.</span></span> <span data-ttu-id="9c6a8-131">如果您有此網域的任何舊版 MX 記錄，可將電子郵件路由傳送至其他地方，請選取每個舊記錄旁邊的核取方塊，然後選取 [**刪除**  >  **確定]**。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-131">If you have any old MX records for this domain that route email somewhere else, select the check box next to each old record, and then select **Delete** > **OK**.</span></span> 
   
## <a name="add-cname-records"></a><span data-ttu-id="9c6a8-132">新增 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="9c6a8-132">Add CNAME records</span></span>
<span data-ttu-id="9c6a8-133"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9c6a8-133"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="9c6a8-134">新增 Microsoft 所需的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-134">Add the CNAME records that are required for Microsoft.</span></span> <span data-ttu-id="9c6a8-135">如果 Microsoft 中列出其他 CNAME 記錄，請將下列相同一般步驟新增至此記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-135">If additional CNAME records are listed in Microsoft, add those following the same general steps shown here.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9c6a8-136">如果您有適用于 Microsoft 的行動裝置管理 (MDM) ，則必須建立兩個額外的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-136">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="9c6a8-137">請按照您針對其他四筆 CNAME 記錄所進行的程序執行，但提供下表的值。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="9c6a8-138"> (如果您沒有 MDM，您可以略過此步驟。 ) </span><span class="sxs-lookup"><span data-stu-id="9c6a8-138">(If you do not have MDM, you can skip this step.)</span></span> 

- <span data-ttu-id="9c6a8-139">在網域的 [DNS 管理員] 頁面上，移至 [**動作**  >  \*\*CNAME (cname) \*\*]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-139">On the DNS Manager page for the domain, go to **Action** > **CNAME (CNAME)**.</span></span>
- <span data-ttu-id="9c6a8-140">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="9c6a8-140">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="9c6a8-141">主機名稱：自動探索</span><span class="sxs-lookup"><span data-stu-id="9c6a8-141">Host Name: autodiscover</span></span>
    - <span data-ttu-id="9c6a8-142">類型：</span><span class="sxs-lookup"><span data-stu-id="9c6a8-142">Type:</span></span> 
    - <span data-ttu-id="9c6a8-143">Cname 位址： autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9c6a8-143">CNAMEAddress: autodiscover.outlook.com</span></span>
- <span data-ttu-id="9c6a8-144">選取 [ **O**K]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-144">Select **O**K.</span></span>

<span data-ttu-id="9c6a8-145">新增 SIP CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-145">Add the SIP CNAME record.</span></span> 
- <span data-ttu-id="9c6a8-146">在網域的 [DNS 管理員] 頁面上，移至 [ **動作** \> \*\*CNAME (cname) \*\*]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-146">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="9c6a8-147">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="9c6a8-147">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="9c6a8-148">主機名稱： sip</span><span class="sxs-lookup"><span data-stu-id="9c6a8-148">Host Name: sip</span></span>
    - <span data-ttu-id="9c6a8-149">類型： CNAME</span><span class="sxs-lookup"><span data-stu-id="9c6a8-149">Type: CNAME</span></span>
    - <span data-ttu-id="9c6a8-150">位址： sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9c6a8-150">Address: sipdir.online.lync.com</span></span>
- <span data-ttu-id="9c6a8-151">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-151">Select **OK**.</span></span>

<span data-ttu-id="9c6a8-152">新增商務用 Skype Online 自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-152">Add the Skype for Business Online Autodiscover CNAME record.</span></span>  
- <span data-ttu-id="9c6a8-153">在網域的 [DNS 管理員] 頁面上，移至 [ **動作** \> \*\*CNAME (cname) \*\*]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-153">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> <span data-ttu-id="9c6a8-154">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="9c6a8-154">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="9c6a8-155">主機名稱： lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9c6a8-155">Host Name: lyncdiscover</span></span>
    - <span data-ttu-id="9c6a8-156">類型： CNAME</span><span class="sxs-lookup"><span data-stu-id="9c6a8-156">Type: CNAME</span></span>
    - <span data-ttu-id="9c6a8-157">位址： webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9c6a8-157">Address: webdir.online.lync.com</span></span>
- <span data-ttu-id="9c6a8-158">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-158">Select **OK**.</span></span>
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a><span data-ttu-id="9c6a8-159">為 Microsoft 的 (MDM) 新增兩個適用于行動裝置管理的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-159">Add two CNAME records for Mobile Device Management (MDM) for Microsoft</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c6a8-160">如果您有適用于 Microsoft 的行動裝置管理 (MDM) ，則必須建立兩個額外的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-160">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="9c6a8-161">請按照您針對其他四筆 CNAME 記錄所進行的程序執行，但提供下表的值。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="9c6a8-162">> (若您沒有 MDM，您可以略過此步驟。 ) </span><span class="sxs-lookup"><span data-stu-id="9c6a8-162">>(If you do not have MDM, you can skip this step.)</span></span> 
  

<span data-ttu-id="9c6a8-163">新增 MDM Enterpriseregistration CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-163">Add the MDM Enterpriseregistration CNAME record.</span></span>  
- <span data-ttu-id="9c6a8-164">在網域的 [DNS 管理員] 頁面上，移至 [ **動作** \> \*\*CNAME (cname) \*\*]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-164">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="9c6a8-165">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="9c6a8-165">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
- <span data-ttu-id="9c6a8-166">主機名稱： enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9c6a8-166">Host Name: enterpriseregistration</span></span>
- <span data-ttu-id="9c6a8-167">類型： CNAME</span><span class="sxs-lookup"><span data-stu-id="9c6a8-167">Type: CNAME</span></span>
- <span data-ttu-id="9c6a8-168">位址： enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9c6a8-168">Address: enterpriseregistration.windows.net</span></span>
- <span data-ttu-id="9c6a8-169">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-169">Select **OK**.</span></span> 

<span data-ttu-id="9c6a8-170">新增 MDM Enterpriseenrollment CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-170">Add the MDM Enterpriseenrollment CNAME record.</span></span> 
-  <span data-ttu-id="9c6a8-171">在網域的 [DNS 管理員] 頁面上，移至 [ **動作** \> \*\*CNAME (cname) \*\*]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-171">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
-  <span data-ttu-id="9c6a8-172">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="9c6a8-172">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="9c6a8-173">主機名稱： enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9c6a8-173">Host Name: enterpriseenrollment</span></span>
    - <span data-ttu-id="9c6a8-174">類型： CNAME</span><span class="sxs-lookup"><span data-stu-id="9c6a8-174">Type: CNAME</span></span>
    - <span data-ttu-id="9c6a8-175">位址： enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9c6a8-175">Address: enterpriseenrollment-s.manage.microsoft.com</span></span>
- <span data-ttu-id="9c6a8-176">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-176">Select **OK**.</span></span>
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9c6a8-177">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="9c6a8-177">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9c6a8-178"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9c6a8-178"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c6a8-179">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-179">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9c6a8-180">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9c6a8-181">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-181">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9c6a8-182">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-182">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="9c6a8-183">新增網域的 SPF TXT 記錄，以協助防堵垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-183">Add the SPF TXT record for your domain to help prevent email spam.</span></span>
  
- <span data-ttu-id="9c6a8-p111">萬一這筆記錄的 [TXT] 值已有其他字串 (例如行銷電子郵件的字串)，沒關係，請保留那些字串，然後再加上這個字串，並分別用雙引號括住字串加以區分。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-p111">You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them.</span></span> 
- <span data-ttu-id="9c6a8-186">在您網域的 [DNS 管理員] 頁面上，移至 [ **動作** \> \*\*文字] (TXT) \*\*。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-186">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-  <span data-ttu-id="9c6a8-187">在 [ **新增資源記錄** ] 對話方塊中，確定欄位已設定為嚴格下列的值。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-187">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 
 > [!IMPORTANT]
> <span data-ttu-id="9c6a8-188">在某些 Windows DNS 管理員版本中，可能已設定網域，因此當您建立 txt 記錄時，首頁名稱會預設為上層網域。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-188">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="9c6a8-189">在此情況中，當您新增 TXT 記錄時，請將主機名稱設定為空白 (無值)，而不是將它設定為 @ 或網域名稱。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-189">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

-  <span data-ttu-id="9c6a8-190">主機類型：@</span><span class="sxs-lookup"><span data-stu-id="9c6a8-190">Host type: @</span></span>
-  <span data-ttu-id="9c6a8-191">記錄類型： TXT</span><span class="sxs-lookup"><span data-stu-id="9c6a8-191">Record Type: TXT</span></span>
-  <span data-ttu-id="9c6a8-192">Address： v = spf1 包含: spf.protection.outlook.com。 .com-all</span><span class="sxs-lookup"><span data-stu-id="9c6a8-192">Address: v=spf1 include:spf.protection.outlook.com -all</span></span> 
         
-  <span data-ttu-id="9c6a8-193">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-193">Select **OK**.</span></span>
   
## <a name="add-srv-records"></a><span data-ttu-id="9c6a8-194">新增 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="9c6a8-194">Add SRV records</span></span>
<span data-ttu-id="9c6a8-195"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9c6a8-195"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="9c6a8-196">新增 Microsoft 所需的兩筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-196">Add the two SRV records that are required for Microsoft.</span></span>

<span data-ttu-id="9c6a8-197">為商務用 Skype Online Web 會議新增 SIP SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-197">Add the SIP SRV record for Skype for Business Online web conferencing.</span></span>  <br/> 
-  <span data-ttu-id="9c6a8-198">在您網域的 [DNS 管理員] 頁面上，移至 [ **動作**] [ \> **其他新記錄**]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span> 
-   <span data-ttu-id="9c6a8-199">在 [ **資源記錄類型** ] 視窗中，選取 [ \*\*服務位置] (SRV) \*\*]，然後選取 [ **建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-199">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="9c6a8-200">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="9c6a8-200">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="9c6a8-201">服務： _sip</span><span class="sxs-lookup"><span data-stu-id="9c6a8-201">Service: _sip</span></span>
    -  <span data-ttu-id="9c6a8-202">通訊協定： _tls</span><span class="sxs-lookup"><span data-stu-id="9c6a8-202">Protocol: _tls</span></span>
    -  <span data-ttu-id="9c6a8-203">優先順序：100</span><span class="sxs-lookup"><span data-stu-id="9c6a8-203">Priority: 100</span></span>
    -  <span data-ttu-id="9c6a8-204">加權：1</span><span class="sxs-lookup"><span data-stu-id="9c6a8-204">Weight: 1</span></span>
    -  <span data-ttu-id="9c6a8-205">連接埠：443</span><span class="sxs-lookup"><span data-stu-id="9c6a8-205">Port: 443</span></span>
    -  <span data-ttu-id="9c6a8-206">目標 (主機名稱) ： sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9c6a8-206">Target (Hostname): sipdir.online.lync.com</span></span>
-  <span data-ttu-id="9c6a8-207">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-207">Select **OK**.</span></span> 


<span data-ttu-id="9c6a8-208">為商務用 Skype Online 同盟新增 SIP SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-208">Add the SIP SRV record for Skype for Business Online federation.</span></span>  
-  <span data-ttu-id="9c6a8-209">在您網域的 [DNS 管理員] 頁面上，移至 [ **動作**] [ \> **其他新記錄**]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span>  
-  <span data-ttu-id="9c6a8-210">在 [ **資源記錄類型** ] 視窗中，選取 [ \*\*服務位置] (SRV) \*\*]，然後選取 [ **建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-210">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="9c6a8-211">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="9c6a8-211">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="9c6a8-212">服務： _sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9c6a8-212">Service: _sipfederationtls</span></span>
    -  <span data-ttu-id="9c6a8-213">通訊協定： _tcp</span><span class="sxs-lookup"><span data-stu-id="9c6a8-213">Protocol: _tcp</span></span>
    -  <span data-ttu-id="9c6a8-214">優先順序：100</span><span class="sxs-lookup"><span data-stu-id="9c6a8-214">Priority: 100</span></span>
    -  <span data-ttu-id="9c6a8-215">加權：1</span><span class="sxs-lookup"><span data-stu-id="9c6a8-215">Weight: 1</span></span>
    -  <span data-ttu-id="9c6a8-216">連接埠：5061</span><span class="sxs-lookup"><span data-stu-id="9c6a8-216">Port: 5061</span></span>
    -  <span data-ttu-id="9c6a8-217">目標 (主機名稱) ： sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9c6a8-217">Target (Hostname): sipfed.online.lync.com</span></span>
-  <span data-ttu-id="9c6a8-218">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-218">Select **OK**.</span></span> 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a><span data-ttu-id="9c6a8-219">新增記錄以驗證您擁有網域 (若您尚未這麼做)</span><span class="sxs-lookup"><span data-stu-id="9c6a8-219">Add a record to verify that you own the domain, if you haven't already</span></span>
<span data-ttu-id="9c6a8-220"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9c6a8-220"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9c6a8-221">在您新增 DNS 記錄以設定 Microsoft 服務之前，Microsoft 必須先確認您擁有您所加入的網域。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-221">Before you add the DNS records to set up your Microsoft services, Microsoft has to confirm that you own the domain you're adding.</span></span> <span data-ttu-id="9c6a8-222">若要這麼做，請新增一筆記錄，然後依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-222">To do this, you add a record, following the steps below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c6a8-223">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-223">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> 
  

1. <span data-ttu-id="9c6a8-224">從 Microsoft 收集資訊。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-224">Gather information from Microsoft.</span></span>  <br/> 
2. <span data-ttu-id="9c6a8-225">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-225">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span> 
3. <span data-ttu-id="9c6a8-226">在 [ **網域** ] 頁面上，于您所驗證之網域的 [ **動作** ] 欄中，選取 [ **開始設定**]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-226">On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**.</span></span> 
4. <span data-ttu-id="9c6a8-227">在 [ **新增網域至 Microsoft** ] 頁面上，選取 [ **開始步驟 1**]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-227">On the **Add a domain to Microsoft** page, select **Start step 1**.</span></span> 
5. <span data-ttu-id="9c6a8-228">在 [ **確認您擁有您的網域** ] 頁面上，于 [ **請參閱執行此步驟的指示** ] 下拉式清單中，選擇 **[一般指示**]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-228">On the **Confirm that you own your domain** page, in the **See instructions for performing this step with** drop-down list, choose **General instructions**.</span></span> 
6. <span data-ttu-id="9c6a8-229">從表格複製 [目的地或指向位址] 值。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-229">From the table, copy the Destination or Points to Address value.</span></span> <span data-ttu-id="9c6a8-230">您在下一步會需要這項資訊。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-230">You'll need it for the next step.</span></span> <span data-ttu-id="9c6a8-231">我們建議您複製並貼上此值，如此一來，所有的間距皆會保持正確。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-231">We recommend copying and pasting this value, so that all of the spacing stays correct.</span></span>

<span data-ttu-id="9c6a8-232">新增 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-232">Add a TXT record.</span></span> 
-  <span data-ttu-id="9c6a8-233">在您網域的 [DNS 管理員] 頁面上，移至 [ **動作** \> \*\*文字] (TXT) \*\*。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-233">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-   <span data-ttu-id="9c6a8-234">在 [ **新增資源記錄** ] 對話方塊中，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-234">In the **New Resource Record** dialog box, select **Edit**.</span></span>  
-  <span data-ttu-id="9c6a8-235">在 [**新增資源記錄**] 對話方塊的 [**自訂主機名稱**] 區域中，確定欄位已設定為嚴格下列的值。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-235">In the **Custom Host Names** area of the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="9c6a8-236">在某些 Windows DNS 管理員版本中，可能已設定網域，因此當您建立 txt 記錄時，首頁名稱會預設為上層網域。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-236">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="9c6a8-237">在此情況中，當您新增 TXT 記錄時，請將主機名稱設定為空白 (無值)，而不是將它設定為 @ 或網域名稱。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-237">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

- <span data-ttu-id="9c6a8-238">主機名稱：@</span><span class="sxs-lookup"><span data-stu-id="9c6a8-238">Host Name: @</span></span>
- <span data-ttu-id="9c6a8-239">類型： TXT</span><span class="sxs-lookup"><span data-stu-id="9c6a8-239">Type: TXT</span></span>
- <span data-ttu-id="9c6a8-240">Address：貼上您剛從 Microsoft 複製的目的地或指向位址值。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-240">Address: Paste the Destination or Points to Address value that you just copied from Microsoft here.</span></span>  
- <span data-ttu-id="9c6a8-241">選取 **[確定**  >  **完成**]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-241">Select **OK** > **Done**.</span></span>

<span data-ttu-id="9c6a8-242">在 Microsoft 中驗證您的網域。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-242">Verify your domain in Microsoft.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="9c6a8-243">請等候大約15分鐘，再執行這項作業，這樣您剛才建立的記錄便可在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-243">Wait about 15 minutes before you do this, so the record you just created can update across the Internet.</span></span>       

- <span data-ttu-id="9c6a8-244">請回到 Microsoft，遵循下列步驟以要求驗證檢查。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-244">Go back to Microsoft and follow the steps below to request a verification check.</span></span> <span data-ttu-id="9c6a8-245">這項檢查會尋找您在上述步驟中新增的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-245">The check looks for the TXT record you added in the previous step.</span></span> <span data-ttu-id="9c6a8-246">找到正確的 TXT 記錄之後，網域即驗證完畢。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-246">When it finds the correct TXT record, the domain is verified.</span></span>  
1. <span data-ttu-id="9c6a8-247">在系統管理中心中，移至 [ **安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a> ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-247">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
2. <span data-ttu-id="9c6a8-248">在 [ **網域** ] 頁面上，于您所驗證之網域的 [ **動作** ] 欄中，選取 [ **開始設定**]。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-248">On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**.</span></span> 
3. <span data-ttu-id="9c6a8-249">在 [ **確認您擁有您的網域** ] 頁面上，選取 [ **完成，立即驗證**]，然後在確認對話方塊中，選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span></span> 
   
> [!NOTE]
>  <span data-ttu-id="9c6a8-p117">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a><span data-ttu-id="9c6a8-253">在內部部署 Active Directory 中用來做為 UPN 的非可路由電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="9c6a8-253">Non-routable email address used as a UPN in your on-prem Active Directory</span></span>
<span data-ttu-id="9c6a8-254"><a name="BKMK_ADNote"> </a></span><span class="sxs-lookup"><span data-stu-id="9c6a8-254"><a name="BKMK_ADNote"> </a></span></span>

<span data-ttu-id="9c6a8-255">如果您想要將內部部署的 Active Directory 與 Microsoft 同步，請確定 Active Directory 使用者主體名稱 (UPN) 尾碼是有效的網域尾碼，而不是不受支援的網域尾碼，例如 @contoso。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-255">If you're planning to synchronize your on-premises Active Directory with Microsoft, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local.</span></span> <span data-ttu-id="9c6a8-256">如果您需要變更 UPN 尾碼，請參閱 how [to prepare a 不可路由的網域以進行目錄同步](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)處理。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-256">If you need to change your UPN suffix, see [How to prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="9c6a8-p119">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9c6a8-p119">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
