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
ms.openlocfilehash: fd7c56b6db9fe5f5dbb0637ad5abcb40a64bef8f
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876346"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a><span data-ttu-id="eb248-103">使用以 Windows 為基礎的 DNS 建立 Microsoft 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="eb248-103">Create DNS records for Microsoft using Windows-based DNS</span></span>

 <span data-ttu-id="eb248-104">若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="eb248-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
   
<span data-ttu-id="eb248-105">如果您使用 Windows 型 DNS 託管自己的 DNS 記錄，請按照本文的步驟設定您電子郵件的記錄、商務用 Skype Online 等。</span><span class="sxs-lookup"><span data-stu-id="eb248-105">If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="eb248-106">若要開始，您必須 [在 Windows 型 dns 中尋找您的 dns 記錄](#find-your-dns-records-in-windows-based-dns) ，以便您進行更新。</span><span class="sxs-lookup"><span data-stu-id="eb248-106">To get started, you need to [find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns) so you can update them.</span></span> <span data-ttu-id="eb248-107">此外，如果您想要將內部部署的 Active Directory 與 Microsoft 同步處理，請參閱 [在您的部署 Active directory 中做為 UPN 的非路由電子郵件地址](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="eb248-107">Also, if you're planning to synchronize your on-premises Active Directory with Microsoft, see [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).</span></span>
  
<span data-ttu-id="eb248-108">新增 DNS 記錄後，出現郵件流程或其他問題的相關問題，請參閱 [疑難排解變更功能變數名稱或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="eb248-108">Trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a><span data-ttu-id="eb248-109">在 Windows 架構的 DNS 中尋您的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="eb248-109">Find your DNS records in Windows-based DNS</span></span>
<span data-ttu-id="eb248-110"><a name="BKMK_find_your_dns_1"></a>移至具有您網域之 DNS 記錄的頁面。</span><span class="sxs-lookup"><span data-stu-id="eb248-110"><a name="BKMK_find_your_dns_1"> </a> Go to the page that has the DNS records for your domain.</span></span> <span data-ttu-id="eb248-111">如果您是在 Windows Server 2008 中工作，請移至 **開始**  >  **執行**。</span><span class="sxs-lookup"><span data-stu-id="eb248-111">If you're working in Windows Server 2008, go to **Start** > **Run**.</span></span> <span data-ttu-id="eb248-112">如果您是在 Windows Server 2012 中工作，請按 Windows 鍵和 **r**。</span><span class="sxs-lookup"><span data-stu-id="eb248-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span></span> <span data-ttu-id="eb248-113">輸入 **dnsmgmnt**，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="eb248-113">Type **dnsmgmnt.msc**, and then select **OK**.</span></span> <span data-ttu-id="eb248-114">在 [DNS 管理員] 中，展開 [ **\<DNS server name\> \> 正向對應區域**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-114">In DNS Manager, expand **\<DNS server name\>  \> Forward Lookup Zones**.</span></span> <span data-ttu-id="eb248-115">選取您的網域。</span><span class="sxs-lookup"><span data-stu-id="eb248-115">Select your domain.</span></span> <span data-ttu-id="eb248-116">您現在可以建立 DNS 記錄了！</span><span class="sxs-lookup"><span data-stu-id="eb248-116">You're now ready to create the DNS records.</span></span>
   
## <a name="add-mx-record"></a><span data-ttu-id="eb248-117">新增 MX 記錄</span><span class="sxs-lookup"><span data-stu-id="eb248-117">Add MX record</span></span>
<span data-ttu-id="eb248-118"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="eb248-118"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="eb248-119">新增 MX 記錄，使您網域的電子郵件將會傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="eb248-119">Add an MX record so email for your domain will come to Microsoft.</span></span>
- <span data-ttu-id="eb248-120">您將新增的 MX 記錄會包含值 () 的 [ **點數** ] 值，此值如下所示： \<MX token\> MSxxxxxxx，其中 \<MX token\> 是類似的值。</span><span class="sxs-lookup"><span data-stu-id="eb248-120">The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.</span></span> 
- <span data-ttu-id="eb248-121">從 Microsoft 的 [新增 DNS 記錄] 頁面的 [Exchange Online] 區段中的 [MX] 列中，複製列于 [位址] 底下的值。</span><span class="sxs-lookup"><span data-stu-id="eb248-121">From the MX row in the Exchange Online section of the Add DNS records page in Microsoft, copy the value listed under Points to address.</span></span> <span data-ttu-id="eb248-122">您將會在您要建立的記錄中使用此值。</span><span class="sxs-lookup"><span data-stu-id="eb248-122">You'll use this value in the record you're creating in this task.</span></span> 
- <span data-ttu-id="eb248-123">在網域的 [DNS 管理員] 頁面上，移至 [**動作**  >  **郵件交換器 (MX)**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-123">On the DNS Manager page for the domain, go to **Action** > **Mail Exchanger (MX)**.</span></span> <span data-ttu-id="eb248-124">若要尋找網域的此頁面，請參閱 [在 Windows 型 dns 中尋找您的 DNS 記錄](#find-your-dns-records-in-windows-based-dns)。</span><span class="sxs-lookup"><span data-stu-id="eb248-124">To find this page for the domain, see [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).</span></span>  
- <span data-ttu-id="eb248-125">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="eb248-125">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span> 
    - <span data-ttu-id="eb248-126">主機名稱: </span><span class="sxs-lookup"><span data-stu-id="eb248-126">Host Name:</span></span> 
    - <span data-ttu-id="eb248-127">@Address：將點貼到您剛剛從 Microsoft 複製的位址值。</span><span class="sxs-lookup"><span data-stu-id="eb248-127">@Address: Paste the Points to address  value that you just copied from Microsoft here.</span></span>  
    - <span data-ttu-id="eb248-128">Pref:</span><span class="sxs-lookup"><span data-stu-id="eb248-128">Pref:</span></span> 
- <span data-ttu-id="eb248-129">選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-129">Select **Save Changes**.</span></span>
- <span data-ttu-id="eb248-130">移除任何過時的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-130">Remove any obsolete MX records.</span></span> <span data-ttu-id="eb248-131">如果您有此網域的任何舊版 MX 記錄，可將電子郵件路由傳送至其他地方，請選取每個舊記錄旁邊的核取方塊，然後選取 [**刪除**  >  **確定]**。</span><span class="sxs-lookup"><span data-stu-id="eb248-131">If you have any old MX records for this domain that route email somewhere else, select the check box next to each old record, and then select **Delete** > **OK**.</span></span> 
   
## <a name="add-cname-records"></a><span data-ttu-id="eb248-132">新增 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="eb248-132">Add CNAME records</span></span>
<span data-ttu-id="eb248-133"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="eb248-133"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="eb248-134">新增 Microsoft 所需的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-134">Add the CNAME records that are required for Microsoft.</span></span> <span data-ttu-id="eb248-135">如果 Microsoft 中列出其他 CNAME 記錄，請將下列相同一般步驟新增至此記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-135">If additional CNAME records are listed in Microsoft, add those following the same general steps shown here.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="eb248-136">如果您有適用于 Microsoft 的行動裝置管理 (MDM) ，則必須建立兩個額外的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-136">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="eb248-137">請按照您針對其他四筆 CNAME 記錄所進行的程序執行，但提供下表的值。</span><span class="sxs-lookup"><span data-stu-id="eb248-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="eb248-138"> (如果您沒有 MDM，您可以略過此步驟。 ) </span><span class="sxs-lookup"><span data-stu-id="eb248-138">(If you do not have MDM, you can skip this step.)</span></span> 

- <span data-ttu-id="eb248-139">在網域的 [DNS 管理員] 頁面上，移至 [**動作**  >  **CNAME (cname)**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-139">On the DNS Manager page for the domain, go to **Action** > **CNAME (CNAME)**.</span></span>
- <span data-ttu-id="eb248-140">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="eb248-140">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="eb248-141">主機名稱：自動探索</span><span class="sxs-lookup"><span data-stu-id="eb248-141">Host Name: autodiscover</span></span>
    - <span data-ttu-id="eb248-142">類型：</span><span class="sxs-lookup"><span data-stu-id="eb248-142">Type:</span></span> 
    - <span data-ttu-id="eb248-143">Cname 位址： autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="eb248-143">CNAMEAddress: autodiscover.outlook.com</span></span>
- <span data-ttu-id="eb248-144">選取 [ **O** K]。</span><span class="sxs-lookup"><span data-stu-id="eb248-144">Select **O** K.</span></span>

<span data-ttu-id="eb248-145">新增 SIP CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-145">Add the SIP CNAME record.</span></span> 
- <span data-ttu-id="eb248-146">在網域的 [DNS 管理員] 頁面上，移至 [ **動作** \> **CNAME (cname)**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-146">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="eb248-147">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="eb248-147">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="eb248-148">主機名稱： sip</span><span class="sxs-lookup"><span data-stu-id="eb248-148">Host Name: sip</span></span>
    - <span data-ttu-id="eb248-149">類型： CNAME</span><span class="sxs-lookup"><span data-stu-id="eb248-149">Type: CNAME</span></span>
    - <span data-ttu-id="eb248-150">位址： sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb248-150">Address: sipdir.online.lync.com</span></span>
- <span data-ttu-id="eb248-151">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="eb248-151">Select **OK**.</span></span>

<span data-ttu-id="eb248-152">新增商務用 Skype Online 自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-152">Add the Skype for Business Online Autodiscover CNAME record.</span></span>  
- <span data-ttu-id="eb248-153">在網域的 [DNS 管理員] 頁面上，移至 [ **動作** \> **CNAME (cname)**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-153">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> <span data-ttu-id="eb248-154">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="eb248-154">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="eb248-155">主機名稱： lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="eb248-155">Host Name: lyncdiscover</span></span>
    - <span data-ttu-id="eb248-156">類型： CNAME</span><span class="sxs-lookup"><span data-stu-id="eb248-156">Type: CNAME</span></span>
    - <span data-ttu-id="eb248-157">位址： webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb248-157">Address: webdir.online.lync.com</span></span>
- <span data-ttu-id="eb248-158">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="eb248-158">Select **OK**.</span></span>
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a><span data-ttu-id="eb248-159">為 Microsoft 的 (MDM) 新增兩個適用于行動裝置管理的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-159">Add two CNAME records for Mobile Device Management (MDM) for Microsoft</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb248-160">如果您有適用于 Microsoft 的行動裝置管理 (MDM) ，則必須建立兩個額外的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-160">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="eb248-161">請按照您針對其他四筆 CNAME 記錄所進行的程序執行，但提供下表的值。</span><span class="sxs-lookup"><span data-stu-id="eb248-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="eb248-162">> (若您沒有 MDM，您可以略過此步驟。 ) </span><span class="sxs-lookup"><span data-stu-id="eb248-162">>(If you do not have MDM, you can skip this step.)</span></span> 
  

<span data-ttu-id="eb248-163">新增 MDM Enterpriseregistration CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-163">Add the MDM Enterpriseregistration CNAME record.</span></span>  
- <span data-ttu-id="eb248-164">在網域的 [DNS 管理員] 頁面上，移至 [ **動作** \> **CNAME (cname)**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-164">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="eb248-165">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="eb248-165">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
- <span data-ttu-id="eb248-166">主機名稱： enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="eb248-166">Host Name: enterpriseregistration</span></span>
- <span data-ttu-id="eb248-167">類型： CNAME</span><span class="sxs-lookup"><span data-stu-id="eb248-167">Type: CNAME</span></span>
- <span data-ttu-id="eb248-168">位址： enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="eb248-168">Address: enterpriseregistration.windows.net</span></span>
- <span data-ttu-id="eb248-169">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="eb248-169">Select **OK**.</span></span> 

<span data-ttu-id="eb248-170">新增 MDM Enterpriseenrollment CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-170">Add the MDM Enterpriseenrollment CNAME record.</span></span> 
-  <span data-ttu-id="eb248-171">在網域的 [DNS 管理員] 頁面上，移至 [ **動作** \> **CNAME (cname)**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-171">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
-  <span data-ttu-id="eb248-172">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="eb248-172">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="eb248-173">主機名稱： enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="eb248-173">Host Name: enterpriseenrollment</span></span>
    - <span data-ttu-id="eb248-174">類型： CNAME</span><span class="sxs-lookup"><span data-stu-id="eb248-174">Type: CNAME</span></span>
    - <span data-ttu-id="eb248-175">位址： enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="eb248-175">Address: enterpriseenrollment-s.manage.microsoft.com</span></span>
- <span data-ttu-id="eb248-176">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="eb248-176">Select **OK**.</span></span>
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="eb248-177">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="eb248-177">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="eb248-178"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="eb248-178"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb248-179">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-179">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="eb248-180">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="eb248-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="eb248-181">如果網域已經有 SPF 記錄，請勿為 Microsoft 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-181">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="eb248-182">請改為將必要的 Microsoft 值新增至目前的記錄，讓您擁有包含這兩組值的  *單一*  SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-182">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="eb248-183">新增網域的 SPF TXT 記錄，以協助防堵垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="eb248-183">Add the SPF TXT record for your domain to help prevent email spam.</span></span>
  
- <span data-ttu-id="eb248-p111">萬一這筆記錄的 [TXT] 值已有其他字串 (例如行銷電子郵件的字串)，沒關係，請保留那些字串，然後再加上這個字串，並分別用雙引號括住字串加以區分。</span><span class="sxs-lookup"><span data-stu-id="eb248-p111">You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them.</span></span> 
- <span data-ttu-id="eb248-186">在您網域的 [DNS 管理員] 頁面上，移至 [ **動作** \> **文字] (TXT)**。</span><span class="sxs-lookup"><span data-stu-id="eb248-186">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-  <span data-ttu-id="eb248-187">在 [ **新增資源記錄** ] 對話方塊中，確定欄位已設定為嚴格下列的值。</span><span class="sxs-lookup"><span data-stu-id="eb248-187">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 
 > [!IMPORTANT]
> <span data-ttu-id="eb248-188">在某些 Windows DNS 管理員版本中，可能已設定網域，因此當您建立 txt 記錄時，首頁名稱會預設為上層網域。</span><span class="sxs-lookup"><span data-stu-id="eb248-188">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="eb248-189">在此情況中，當您新增 TXT 記錄時，請將主機名稱設定為空白 (無值)，而不是將它設定為 @ 或網域名稱。</span><span class="sxs-lookup"><span data-stu-id="eb248-189">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

-  <span data-ttu-id="eb248-190">主機類型：@</span><span class="sxs-lookup"><span data-stu-id="eb248-190">Host type: @</span></span>
-  <span data-ttu-id="eb248-191">記錄類型： TXT</span><span class="sxs-lookup"><span data-stu-id="eb248-191">Record Type: TXT</span></span>
-  <span data-ttu-id="eb248-192">Address： v = spf1 包含: spf.protection.outlook.com。 .com-all</span><span class="sxs-lookup"><span data-stu-id="eb248-192">Address: v=spf1 include:spf.protection.outlook.com -all</span></span> 
         
-  <span data-ttu-id="eb248-193">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="eb248-193">Select **OK**.</span></span>
   
## <a name="add-srv-records"></a><span data-ttu-id="eb248-194">新增 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="eb248-194">Add SRV records</span></span>
<span data-ttu-id="eb248-195"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="eb248-195"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="eb248-196">新增 Microsoft 所需的兩筆 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-196">Add the two SRV records that are required for Microsoft.</span></span>

<span data-ttu-id="eb248-197">為商務用 Skype Online Web 會議新增 SIP SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-197">Add the SIP SRV record for Skype for Business Online web conferencing.</span></span>  <br/> 
-  <span data-ttu-id="eb248-198">在您網域的 [DNS 管理員] 頁面上，移至 [ **動作**] [ \> **其他新記錄**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span> 
-   <span data-ttu-id="eb248-199">在 [ **資源記錄類型** ] 視窗中，選取 [ **服務位置] (SRV)**]，然後選取 [ **建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-199">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="eb248-200">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="eb248-200">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="eb248-201">服務： _sip</span><span class="sxs-lookup"><span data-stu-id="eb248-201">Service: _sip</span></span>
    -  <span data-ttu-id="eb248-202">通訊協定： _tls</span><span class="sxs-lookup"><span data-stu-id="eb248-202">Protocol: _tls</span></span>
    -  <span data-ttu-id="eb248-203">優先順序：100</span><span class="sxs-lookup"><span data-stu-id="eb248-203">Priority: 100</span></span>
    -  <span data-ttu-id="eb248-204">加權：1</span><span class="sxs-lookup"><span data-stu-id="eb248-204">Weight: 1</span></span>
    -  <span data-ttu-id="eb248-205">連接埠：443</span><span class="sxs-lookup"><span data-stu-id="eb248-205">Port: 443</span></span>
    -  <span data-ttu-id="eb248-206">目標 (主機名稱) ： sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb248-206">Target (Hostname): sipdir.online.lync.com</span></span>
-  <span data-ttu-id="eb248-207">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="eb248-207">Select **OK**.</span></span> 


<span data-ttu-id="eb248-208">為商務用 Skype Online 同盟新增 SIP SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-208">Add the SIP SRV record for Skype for Business Online federation.</span></span>  
-  <span data-ttu-id="eb248-209">在您網域的 [DNS 管理員] 頁面上，移至 [ **動作**] [ \> **其他新記錄**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span>  
-  <span data-ttu-id="eb248-210">在 [ **資源記錄類型** ] 視窗中，選取 [ **服務位置] (SRV)**]，然後選取 [ **建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-210">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="eb248-211">在 [ **新增資源記錄** ] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="eb248-211">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="eb248-212">服務： _sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="eb248-212">Service: _sipfederationtls</span></span>
    -  <span data-ttu-id="eb248-213">通訊協定： _tcp</span><span class="sxs-lookup"><span data-stu-id="eb248-213">Protocol: _tcp</span></span>
    -  <span data-ttu-id="eb248-214">優先順序：100</span><span class="sxs-lookup"><span data-stu-id="eb248-214">Priority: 100</span></span>
    -  <span data-ttu-id="eb248-215">加權：1</span><span class="sxs-lookup"><span data-stu-id="eb248-215">Weight: 1</span></span>
    -  <span data-ttu-id="eb248-216">連接埠：5061</span><span class="sxs-lookup"><span data-stu-id="eb248-216">Port: 5061</span></span>
    -  <span data-ttu-id="eb248-217">目標 (主機名稱) ： sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb248-217">Target (Hostname): sipfed.online.lync.com</span></span>
-  <span data-ttu-id="eb248-218">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="eb248-218">Select **OK**.</span></span> 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a><span data-ttu-id="eb248-219">新增記錄以驗證您擁有網域 (若您尚未這麼做)</span><span class="sxs-lookup"><span data-stu-id="eb248-219">Add a record to verify that you own the domain, if you haven't already</span></span>
<span data-ttu-id="eb248-220"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="eb248-220"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="eb248-221">在您新增 DNS 記錄以設定 Microsoft 服務之前，Microsoft 必須先確認您擁有您所加入的網域。</span><span class="sxs-lookup"><span data-stu-id="eb248-221">Before you add the DNS records to set up your Microsoft services, Microsoft has to confirm that you own the domain you're adding.</span></span> <span data-ttu-id="eb248-222">若要這麼做，請新增一筆記錄，然後依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="eb248-222">To do this, you add a record, following the steps below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eb248-223">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。</span><span class="sxs-lookup"><span data-stu-id="eb248-223">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> 
  

1. <span data-ttu-id="eb248-224">從 Microsoft 收集資訊。</span><span class="sxs-lookup"><span data-stu-id="eb248-224">Gather information from Microsoft.</span></span>  <br/> 
2. <span data-ttu-id="eb248-225">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="eb248-225">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span> 
3. <span data-ttu-id="eb248-226">在 [ **網域** ] 頁面上，于您所驗證之網域的 [ **動作** ] 欄中，選取 [ **開始設定**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-226">On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**.</span></span> 
4. <span data-ttu-id="eb248-227">在 [ **新增網域至 Microsoft** ] 頁面上，選取 [ **開始步驟 1**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-227">On the **Add a domain to Microsoft** page, select **Start step 1**.</span></span> 
5. <span data-ttu-id="eb248-228">在 [ **確認您擁有您的網域** ] 頁面上，于 [ **請參閱執行此步驟的指示** ] 下拉式清單中，選擇 **[一般指示**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-228">On the **Confirm that you own your domain** page, in the **See instructions for performing this step with** drop-down list, choose **General instructions**.</span></span> 
6. <span data-ttu-id="eb248-229">從表格複製 [目的地或指向位址] 值。</span><span class="sxs-lookup"><span data-stu-id="eb248-229">From the table, copy the Destination or Points to Address value.</span></span> <span data-ttu-id="eb248-230">您在下一步會需要這項資訊。</span><span class="sxs-lookup"><span data-stu-id="eb248-230">You'll need it for the next step.</span></span> <span data-ttu-id="eb248-231">我們建議您複製並貼上此值，如此一來，所有的間距皆會保持正確。</span><span class="sxs-lookup"><span data-stu-id="eb248-231">We recommend copying and pasting this value, so that all of the spacing stays correct.</span></span>

<span data-ttu-id="eb248-232">新增 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-232">Add a TXT record.</span></span> 
-  <span data-ttu-id="eb248-233">在您網域的 [DNS 管理員] 頁面上，移至 [ **動作** \> **文字] (TXT)**。</span><span class="sxs-lookup"><span data-stu-id="eb248-233">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-   <span data-ttu-id="eb248-234">在 [ **新增資源記錄** ] 對話方塊中，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-234">In the **New Resource Record** dialog box, select **Edit**.</span></span>  
-  <span data-ttu-id="eb248-235">在 [**新增資源記錄**] 對話方塊的 [**自訂主機名稱**] 區域中，確定欄位已設定為嚴格下列的值。</span><span class="sxs-lookup"><span data-stu-id="eb248-235">In the **Custom Host Names** area of the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="eb248-236">在某些 Windows DNS 管理員版本中，可能已設定網域，因此當您建立 txt 記錄時，首頁名稱會預設為上層網域。</span><span class="sxs-lookup"><span data-stu-id="eb248-236">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="eb248-237">在此情況中，當您新增 TXT 記錄時，請將主機名稱設定為空白 (無值)，而不是將它設定為 @ 或網域名稱。</span><span class="sxs-lookup"><span data-stu-id="eb248-237">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

- <span data-ttu-id="eb248-238">主機名稱：@</span><span class="sxs-lookup"><span data-stu-id="eb248-238">Host Name: @</span></span>
- <span data-ttu-id="eb248-239">類型： TXT</span><span class="sxs-lookup"><span data-stu-id="eb248-239">Type: TXT</span></span>
- <span data-ttu-id="eb248-240">Address：貼上您剛從 Microsoft 複製的目的地或指向位址值。</span><span class="sxs-lookup"><span data-stu-id="eb248-240">Address: Paste the Destination or Points to Address value that you just copied from Microsoft here.</span></span>  
- <span data-ttu-id="eb248-241">選取 **[確定**  >  **完成**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-241">Select **OK** > **Done**.</span></span>

<span data-ttu-id="eb248-242">在 Microsoft 中驗證您的網域。</span><span class="sxs-lookup"><span data-stu-id="eb248-242">Verify your domain in Microsoft.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="eb248-243">請等候大約15分鐘，再執行這項作業，這樣您剛才建立的記錄便可在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="eb248-243">Wait about 15 minutes before you do this, so the record you just created can update across the Internet.</span></span>       

- <span data-ttu-id="eb248-244">請回到 Microsoft，遵循下列步驟以要求驗證檢查。</span><span class="sxs-lookup"><span data-stu-id="eb248-244">Go back to Microsoft and follow the steps below to request a verification check.</span></span> <span data-ttu-id="eb248-245">這項檢查會尋找您在上述步驟中新增的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="eb248-245">The check looks for the TXT record you added in the previous step.</span></span> <span data-ttu-id="eb248-246">找到正確的 TXT 記錄之後，網域即驗證完畢。</span><span class="sxs-lookup"><span data-stu-id="eb248-246">When it finds the correct TXT record, the domain is verified.</span></span>  
1. <span data-ttu-id="eb248-247">在系統管理中心中，移至 [ **安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a> ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="eb248-247">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
2. <span data-ttu-id="eb248-248">在 [ **網域** ] 頁面上，于您所驗證之網域的 [ **動作** ] 欄中，選取 [ **開始設定**]。</span><span class="sxs-lookup"><span data-stu-id="eb248-248">On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**.</span></span> 
3. <span data-ttu-id="eb248-249">在 [ **確認您擁有您的網域** ] 頁面上，選取 [ **完成，立即驗證**]，然後在確認對話方塊中，選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="eb248-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span></span> 
   
> [!NOTE]
>  <span data-ttu-id="eb248-p117">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="eb248-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a><span data-ttu-id="eb248-253">在內部部署 Active Directory 中用來做為 UPN 的非可路由電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="eb248-253">Non-routable email address used as a UPN in your on-prem Active Directory</span></span>
<span data-ttu-id="eb248-254"><a name="BKMK_ADNote"> </a></span><span class="sxs-lookup"><span data-stu-id="eb248-254"><a name="BKMK_ADNote"> </a></span></span>

<span data-ttu-id="eb248-255">如果您想要將內部部署的 Active Directory 與 Microsoft 同步，請確定 Active Directory 使用者主體名稱 (UPN) 尾碼是有效的網域尾碼，而不是不受支援的網域尾碼，例如 @contoso。</span><span class="sxs-lookup"><span data-stu-id="eb248-255">If you're planning to synchronize your on-premises Active Directory with Microsoft, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local.</span></span> <span data-ttu-id="eb248-256">如果您需要變更 UPN 尾碼，請參閱 how [to prepare a 不可路由的網域以進行目錄同步](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)處理。</span><span class="sxs-lookup"><span data-stu-id="eb248-256">If you need to change your UPN suffix, see [How to prepare a non-routable domain for directory synchronization](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="eb248-p119">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="eb248-p119">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

## <a name="related-content"></a><span data-ttu-id="eb248-260">相關內容</span><span class="sxs-lookup"><span data-stu-id="eb248-260">Related content</span></span>

<span data-ttu-id="eb248-261">[將網域從 Micrsoft 365 轉接至其他主機](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host) (文章) </span><span class="sxs-lookup"><span data-stu-id="eb248-261">[Transfer a domain from Micrsoft 365 to another host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host) (article)</span></span>

<span data-ttu-id="eb248-262">[從我的自訂網域試用 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain) (文章) </span><span class="sxs-lookup"><span data-stu-id="eb248-262">[Pilot Microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain) (article)</span></span>

<span data-ttu-id="eb248-263">[網域常見問題解答](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) (篇) </span><span class="sxs-lookup"><span data-stu-id="eb248-263">[Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) (article)</span></span>