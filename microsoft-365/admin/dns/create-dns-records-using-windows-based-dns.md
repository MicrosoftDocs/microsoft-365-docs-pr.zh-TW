---
title: 使用 Windows 型 DNS 建立 Office 365 的 DNS 記錄
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: 瞭解如何驗證您的網域，並設定電子郵件、商務用 Skype Online 和其他服務的 DNS 記錄，以 Windows a 為基礎的 Windows DNS for Office 365。
ms.openlocfilehash: d33a2f79111f8951c3ec31ca5680877ad2e7d570
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210561"
---
# <a name="create-dns-records-for-office-365-using-windows-based-dns"></a><span data-ttu-id="40980-103">使用 Windows 型 DNS 建立 Office 365 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="40980-103">Create DNS records for Office 365 using Windows-based DNS</span></span>

 <span data-ttu-id="40980-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="40980-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
   
<span data-ttu-id="40980-105">如果您使用 Windows 型 DNS 託管自己的 DNS 記錄，請按照本文的步驟設定您電子郵件的記錄、商務用 Skype Online 等。</span><span class="sxs-lookup"><span data-stu-id="40980-105">If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="40980-106">若要開始，您必須[在 Windows 型 dns 中尋找您的 dns 記錄](#find-your-dns-records-in-windows-based-dns)，以便您進行更新。</span><span class="sxs-lookup"><span data-stu-id="40980-106">To get started, you need to [find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns) so you can update them.</span></span> <span data-ttu-id="40980-107">此外，如果您計畫要同步處理內部部署 Active Directory 與 Office 365，請參閱[在部署 Active directory 中做為 UPN 的非路由電子郵件地址](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="40980-107">Also, if you're planning to synchronize your on-premises Active Directory with Office 365, see [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).</span></span>
  
<span data-ttu-id="40980-108">新增 DNS 記錄後，出現郵件流程或其他問題的相關問題，請參閱[疑難排解變更功能變數名稱或 DNS 記錄後的問題](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="40980-108">Trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a><span data-ttu-id="40980-109">在 Windows 架構的 DNS 中尋您的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="40980-109">Find your DNS records in Windows-based DNS</span></span>
<span data-ttu-id="40980-110"><a name="BKMK_find_your_dns_1"> </a>移至具有您網域之 DNS 記錄的頁面。</span><span class="sxs-lookup"><span data-stu-id="40980-110"><a name="BKMK_find_your_dns_1"> </a> Go to the page that has the DNS records for your domain.</span></span> <span data-ttu-id="40980-111">如果您是在 Windows Server 2008 中工作，請移至**開始** > **執行**。</span><span class="sxs-lookup"><span data-stu-id="40980-111">If you're working in Windows Server 2008, go to **Start** > **Run**.</span></span> <span data-ttu-id="40980-112">如果您是在 Windows Server 2012 中工作，請按 Windows 鍵和**r**。</span><span class="sxs-lookup"><span data-stu-id="40980-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span></span> <span data-ttu-id="40980-113">輸入**dnsmgmnt**，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="40980-113">Type **dnsmgmnt.msc**, and then select **OK**.</span></span> <span data-ttu-id="40980-114">在 [dns 管理員] 中，展開\*\* \<[dns 伺服器名稱\> \>正向對應區域  \*\*]。</span><span class="sxs-lookup"><span data-stu-id="40980-114">In DNS Manager, expand **\<DNS server name\>  \> Forward Lookup Zones**.</span></span> <span data-ttu-id="40980-115">選取您的網域。</span><span class="sxs-lookup"><span data-stu-id="40980-115">Select your domain.</span></span> <span data-ttu-id="40980-116">您現在可以建立 DNS 記錄了！</span><span class="sxs-lookup"><span data-stu-id="40980-116">You're now ready to create the DNS records.</span></span>
   
## <a name="add-mx-record"></a><span data-ttu-id="40980-117">新增 MX 記錄</span><span class="sxs-lookup"><span data-stu-id="40980-117">Add MX record</span></span>
<span data-ttu-id="40980-118"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="40980-118"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="40980-119">新增 MX 記錄，以便將您網域的電子郵件送至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="40980-119">Add an MX record so email for your domain will come to Office 365.</span></span>
- <span data-ttu-id="40980-120">您要新增的 MX 記錄包含一個類似 \<MX token\>.mail.protection.outlook.com 的值 (**[指向位址]** 值)，其中 \<MX token\> 值類似 MSxxxxxxx。</span><span class="sxs-lookup"><span data-stu-id="40980-120">The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.</span></span> 
- <span data-ttu-id="40980-121">從 Office 365 的 [新增 DNS 記錄] 頁面的 [Exchange Online] 區段中的 [MX] 列中，複製 [點數為下列值] 底下所列的值。</span><span class="sxs-lookup"><span data-stu-id="40980-121">From the MX row in the Exchange Online section of the Add DNS records page in Office 365, copy the value listed under Points to address.</span></span> <span data-ttu-id="40980-122">您將會在您要建立的記錄中使用此值。</span><span class="sxs-lookup"><span data-stu-id="40980-122">You'll use this value in the record you're creating in this task.</span></span> 
- <span data-ttu-id="40980-123">在網域的 [DNS 管理員] 頁面上，移至 [**動作** > **郵件交換器（MX）**]。</span><span class="sxs-lookup"><span data-stu-id="40980-123">On the DNS Manager page for the domain, go to **Action** > **Mail Exchanger (MX)**.</span></span> <span data-ttu-id="40980-124">若要尋找網域的此頁面，請參閱[在 Windows 型 dns 中尋找您的 DNS 記錄](#find-your-dns-records-in-windows-based-dns)。</span><span class="sxs-lookup"><span data-stu-id="40980-124">To find this page for the domain, see [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).</span></span>  
- <span data-ttu-id="40980-125">在 [**新增資源記錄**] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="40980-125">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span> 
    - <span data-ttu-id="40980-126">主機名稱：</span><span class="sxs-lookup"><span data-stu-id="40980-126">Host Name:</span></span> 
    - <span data-ttu-id="40980-127">@Address：在這裡，貼上您剛才從 Office 365 複製的點到位址值。</span><span class="sxs-lookup"><span data-stu-id="40980-127">@Address: Paste the Points to address  value that you just copied from Office 365 here.</span></span>  
    - <span data-ttu-id="40980-128">Pref:</span><span class="sxs-lookup"><span data-stu-id="40980-128">Pref:</span></span> 
- <span data-ttu-id="40980-129">選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="40980-129">Select **Save Changes**.</span></span>
- <span data-ttu-id="40980-130">移除任何過時的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-130">Remove any obsolete MX records.</span></span> <span data-ttu-id="40980-131">如果您有此網域的任何舊版 MX 記錄，可將電子郵件路由傳送至其他地方，請選取每個舊記錄旁邊的核取方塊，然後選取 [**刪除** > **確定]**。</span><span class="sxs-lookup"><span data-stu-id="40980-131">If you have any old MX records for this domain that route email somewhere else, select the check box next to each old record, and then select **Delete** > **OK**.</span></span> 
   
## <a name="add-cname-records"></a><span data-ttu-id="40980-132">新增 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="40980-132">Add CNAME records</span></span>
<span data-ttu-id="40980-133"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="40980-133"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="40980-134">新增 Office 365 所需的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-134">Add the CNAME records that are required for Office 365.</span></span> <span data-ttu-id="40980-135">如果 Office 365 中列出其他 CNAME 記錄，也請同樣按照這裡顯示的一般步驟來新增這些記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-135">If additional CNAME records are listed in Office 365, add those following the same general steps shown here.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="40980-136">如果您有 Office 365 行動裝置管理 (MDM)，則您必須建立兩筆其他的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-136">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="40980-137">請按照您針對其他四筆 CNAME 記錄所進行的程序執行，但提供下表的值。</span><span class="sxs-lookup"><span data-stu-id="40980-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="40980-138">（如果您沒有 MDM，您可以略過此步驟。）</span><span class="sxs-lookup"><span data-stu-id="40980-138">(If you do not have MDM, you can skip this step.)</span></span> 

- <span data-ttu-id="40980-139">在網域的 [DNS 管理員] 頁面上，移至 [**動作** > **CNAME （cname）**]。</span><span class="sxs-lookup"><span data-stu-id="40980-139">On the DNS Manager page for the domain, go to **Action** > **CNAME (CNAME)**.</span></span>
- <span data-ttu-id="40980-140">在 [**新增資源記錄**] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="40980-140">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="40980-141">主機名稱：自動探索</span><span class="sxs-lookup"><span data-stu-id="40980-141">Host Name: autodiscover</span></span>
    - <span data-ttu-id="40980-142">類型：</span><span class="sxs-lookup"><span data-stu-id="40980-142">Type:</span></span> 
    - <span data-ttu-id="40980-143">Cname 位址： autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="40980-143">CNAMEAddress: autodiscover.outlook.com</span></span>
- <span data-ttu-id="40980-144">選取 [ **O**K]。</span><span class="sxs-lookup"><span data-stu-id="40980-144">Select **O**K.</span></span>

<span data-ttu-id="40980-145">新增 SIP CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-145">Add the SIP CNAME record.</span></span> 
- <span data-ttu-id="40980-146">在網域的 [DNS 管理員] 頁面上，移至 [**動作** \> **CNAME （cname）**]。</span><span class="sxs-lookup"><span data-stu-id="40980-146">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="40980-147">在 [**新增資源記錄**] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="40980-147">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="40980-148">主機名稱： sip</span><span class="sxs-lookup"><span data-stu-id="40980-148">Host Name: sip</span></span>
    - <span data-ttu-id="40980-149">類型： CNAME</span><span class="sxs-lookup"><span data-stu-id="40980-149">Type: CNAME</span></span>
    - <span data-ttu-id="40980-150">位址： sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="40980-150">Address: sipdir.online.lync.com</span></span>
- <span data-ttu-id="40980-151">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40980-151">Select **OK**.</span></span>

<span data-ttu-id="40980-152">新增商務用 Skype Online 自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-152">Add the Skype for Business Online Autodiscover CNAME record.</span></span>  
- <span data-ttu-id="40980-153">在網域的 [DNS 管理員] 頁面上，移至 [**動作** \> **CNAME （cname）**]。</span><span class="sxs-lookup"><span data-stu-id="40980-153">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> <span data-ttu-id="40980-154">在 [**新增資源記錄**] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="40980-154">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="40980-155">主機名稱： lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="40980-155">Host Name: lyncdiscover</span></span>
    - <span data-ttu-id="40980-156">類型： CNAME</span><span class="sxs-lookup"><span data-stu-id="40980-156">Type: CNAME</span></span>
    - <span data-ttu-id="40980-157">位址： webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="40980-157">Address: webdir.online.lync.com</span></span>
- <span data-ttu-id="40980-158">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40980-158">Select **OK**.</span></span>
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a><span data-ttu-id="40980-159">為 Office 365 行動裝置管理 (MDM) 新增兩筆 CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="40980-159">Add two CNAME records for Mobile Device Management (MDM) for Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40980-160">如果您有 Office 365 行動裝置管理 (MDM)，則您必須建立兩筆其他的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-160">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="40980-161">請按照您針對其他四筆 CNAME 記錄所進行的程序執行，但提供下表的值。</span><span class="sxs-lookup"><span data-stu-id="40980-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="40980-162">> （如果您沒有 MDM，您可以略過此步驟）。</span><span class="sxs-lookup"><span data-stu-id="40980-162">>(If you do not have MDM, you can skip this step.)</span></span> 
  

<span data-ttu-id="40980-163">新增 MDM Enterpriseregistration CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-163">Add the MDM Enterpriseregistration CNAME record.</span></span>  
- <span data-ttu-id="40980-164">在網域的 [DNS 管理員] 頁面上，移至 [**動作** \> **CNAME （cname）**]。</span><span class="sxs-lookup"><span data-stu-id="40980-164">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="40980-165">在 [**新增資源記錄**] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="40980-165">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
- <span data-ttu-id="40980-166">主機名稱： enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="40980-166">Host Name: enterpriseregistration</span></span>
- <span data-ttu-id="40980-167">類型： CNAME</span><span class="sxs-lookup"><span data-stu-id="40980-167">Type: CNAME</span></span>
- <span data-ttu-id="40980-168">位址： enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="40980-168">Address: enterpriseregistration.windows.net</span></span>
- <span data-ttu-id="40980-169">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40980-169">Select **OK**.</span></span> 

<span data-ttu-id="40980-170">新增 MDM Enterpriseenrollment CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-170">Add the MDM Enterpriseenrollment CNAME record.</span></span> 
-  <span data-ttu-id="40980-171">在網域的 [DNS 管理員] 頁面上，移至 [**動作** \> **CNAME （cname）**]。</span><span class="sxs-lookup"><span data-stu-id="40980-171">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
-  <span data-ttu-id="40980-172">在 [**新增資源記錄**] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="40980-172">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="40980-173">主機名稱： enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="40980-173">Host Name: enterpriseenrollment</span></span>
    - <span data-ttu-id="40980-174">類型： CNAME</span><span class="sxs-lookup"><span data-stu-id="40980-174">Type: CNAME</span></span>
    - <span data-ttu-id="40980-175">位址： enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="40980-175">Address: enterpriseenrollment-s.manage.microsoft.com</span></span>
- <span data-ttu-id="40980-176">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40980-176">Select **OK**.</span></span>
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="40980-177">新增 SPF 的 TXT 記錄以協助防範垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="40980-177">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="40980-178"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="40980-178"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="40980-179">網域的 SPF 不得擁有一個以上的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-179">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="40980-180">如果您的網域具有多筆 SPF 記錄，您將收到電子郵件錯誤，以及傳送及垃圾郵件分類問題。</span><span class="sxs-lookup"><span data-stu-id="40980-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="40980-181">如果網域已經有 SPF 記錄，請勿為 Office 365 建立一個新的記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-181">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="40980-182">而是，請將必要的 Office 365 值新增到目前的記錄，以便擁有包含這兩組值的*單一* SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-182">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="40980-183">新增網域的 SPF TXT 記錄，以協助防堵垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="40980-183">Add the SPF TXT record for your domain to help prevent email spam.</span></span>
  
- <span data-ttu-id="40980-p111">萬一這筆記錄的 [TXT] 值已有其他字串 (例如行銷電子郵件的字串)，沒關係，請保留那些字串，然後再加上這個字串，並分別用雙引號括住字串加以區分。</span><span class="sxs-lookup"><span data-stu-id="40980-p111">You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them.</span></span> 
- <span data-ttu-id="40980-186">在您網域的 [DNS 管理員] 頁面上，移至 [**動作** \> **文字（TXT）**]。</span><span class="sxs-lookup"><span data-stu-id="40980-186">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-  <span data-ttu-id="40980-187">在 [**新增資源記錄**] 對話方塊中，確定欄位已設定為嚴格下列的值。</span><span class="sxs-lookup"><span data-stu-id="40980-187">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 
 > [!IMPORTANT]
> <span data-ttu-id="40980-188">在某些 Windows DNS 管理員版本中，可能已設定網域，因此當您建立 txt 記錄時，首頁名稱會預設為上層網域。</span><span class="sxs-lookup"><span data-stu-id="40980-188">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="40980-189">在此情況中，當您新增 TXT 記錄時，請將主機名稱設定為空白 (無值)，而不是將它設定為 @ 或網域名稱。</span><span class="sxs-lookup"><span data-stu-id="40980-189">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

-  <span data-ttu-id="40980-190">主機類型：@</span><span class="sxs-lookup"><span data-stu-id="40980-190">Host type: @</span></span>
-  <span data-ttu-id="40980-191">記錄類型： TXT</span><span class="sxs-lookup"><span data-stu-id="40980-191">Record Type: TXT</span></span>
-  <span data-ttu-id="40980-192">Address： v = spf1 包含: spf.protection.outlook.com。 .com-all</span><span class="sxs-lookup"><span data-stu-id="40980-192">Address: v=spf1 include:spf.protection.outlook.com -all</span></span> 
         
-  <span data-ttu-id="40980-193">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40980-193">Select **OK**.</span></span>
   
## <a name="add-srv-records"></a><span data-ttu-id="40980-194">新增 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="40980-194">Add SRV records</span></span>
<span data-ttu-id="40980-195"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="40980-195"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="40980-196">新增兩筆 Office 365.所需的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-196">Add the two SRV records that are required for Office 365.</span></span>

<span data-ttu-id="40980-197">為商務用 Skype Online Web 會議新增 SIP SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-197">Add the SIP SRV record for Skype for Business Online web conferencing.</span></span>  <br/> 
-  <span data-ttu-id="40980-198">在您網域的 [DNS 管理員] 頁面上，移至 [**動作** \> ] [**其他新記錄**]。</span><span class="sxs-lookup"><span data-stu-id="40980-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span> 
-   <span data-ttu-id="40980-199">在 [**資源記錄類型**] 視窗中，選取 [**服務位置（SRV）**]，然後選取 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="40980-199">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="40980-200">在 [**新增資源記錄**] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="40980-200">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="40980-201">服務： _sip</span><span class="sxs-lookup"><span data-stu-id="40980-201">Service: _sip</span></span>
    -  <span data-ttu-id="40980-202">通訊協定： _tls</span><span class="sxs-lookup"><span data-stu-id="40980-202">Protocol: _tls</span></span>
    -  <span data-ttu-id="40980-203">優先順序：100</span><span class="sxs-lookup"><span data-stu-id="40980-203">Priority: 100</span></span>
    -  <span data-ttu-id="40980-204">加權：1</span><span class="sxs-lookup"><span data-stu-id="40980-204">Weight: 1</span></span>
    -  <span data-ttu-id="40980-205">連接埠：443</span><span class="sxs-lookup"><span data-stu-id="40980-205">Port: 443</span></span>
    -  <span data-ttu-id="40980-206">目標（主機名稱）： sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="40980-206">Target (Hostname): sipdir.online.lync.com</span></span>
-  <span data-ttu-id="40980-207">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40980-207">Select **OK**.</span></span> 


<span data-ttu-id="40980-208">為商務用 Skype Online 同盟新增 SIP SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-208">Add the SIP SRV record for Skype for Business Online federation.</span></span>  
-  <span data-ttu-id="40980-209">在您網域的 [DNS 管理員] 頁面上，移至 [**動作** \> ] [**其他新記錄**]。</span><span class="sxs-lookup"><span data-stu-id="40980-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span>  
-  <span data-ttu-id="40980-210">在 [**資源記錄類型**] 視窗中，選取 [**服務位置（SRV）**]，然後選取 [**建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="40980-210">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="40980-211">在 [**新增資源記錄**] 對話方塊中，確定已將欄位設定為嚴格下列值：</span><span class="sxs-lookup"><span data-stu-id="40980-211">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="40980-212">服務： _sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="40980-212">Service: _sipfederationtls</span></span>
    -  <span data-ttu-id="40980-213">通訊協定： _tcp</span><span class="sxs-lookup"><span data-stu-id="40980-213">Protocol: _tcp</span></span>
    -  <span data-ttu-id="40980-214">優先順序：100</span><span class="sxs-lookup"><span data-stu-id="40980-214">Priority: 100</span></span>
    -  <span data-ttu-id="40980-215">加權：1</span><span class="sxs-lookup"><span data-stu-id="40980-215">Weight: 1</span></span>
    -  <span data-ttu-id="40980-216">連接埠：5061</span><span class="sxs-lookup"><span data-stu-id="40980-216">Port: 5061</span></span>
    -  <span data-ttu-id="40980-217">目標（主機名稱）： sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="40980-217">Target (Hostname): sipfed.online.lync.com</span></span>
-  <span data-ttu-id="40980-218">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40980-218">Select **OK**.</span></span> 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a><span data-ttu-id="40980-219">新增記錄以驗證您擁有網域 (若您尚未這麼做)</span><span class="sxs-lookup"><span data-stu-id="40980-219">Add a record to verify that you own the domain, if you haven't already</span></span>
<span data-ttu-id="40980-220"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="40980-220"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="40980-p113">在新增 DNS 記錄以設定 Office 365 服務之前，Office 365 必須先確認您擁有所要新增的網域。若要這麼做，請新增一筆記錄，然後依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="40980-p113">Before you add the DNS records to set up your Office 365 services, Office 365 has to confirm that you own the domain you're adding. To do this, you add a record, following the steps below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40980-223">這筆記錄只會用於驗證您擁有自己的網域，不會影響其他項目。</span><span class="sxs-lookup"><span data-stu-id="40980-223">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> 
  

1. <span data-ttu-id="40980-224">從 Office 365 收集資訊。</span><span class="sxs-lookup"><span data-stu-id="40980-224">Gather information from Office 365.</span></span>  <br/> 
2. <span data-ttu-id="40980-225">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="40980-225">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span> 
3. <span data-ttu-id="40980-226">在 [**網域**] 頁面上，于您所驗證之網域的 [**動作**] 欄中，選取 [**開始設定**]。</span><span class="sxs-lookup"><span data-stu-id="40980-226">On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**.</span></span> 
4. <span data-ttu-id="40980-227">在 [**新增網域至 Office 365** ] 頁面上，選取 [**開始步驟 1**]。</span><span class="sxs-lookup"><span data-stu-id="40980-227">On the **Add a domain to Office 365** page, select **Start step 1**.</span></span> 
5. <span data-ttu-id="40980-228">在 [**確認您擁有您的網域**] 頁面上，于 [**請參閱執行此步驟的指示**] 下拉式清單中，選擇 **[一般指示**]。</span><span class="sxs-lookup"><span data-stu-id="40980-228">On the **Confirm that you own your domain** page, in the **See instructions for performing this step with** drop-down list, choose **General instructions**.</span></span> 
6. <span data-ttu-id="40980-229">從表格複製 [目的地或指向位址] 值。</span><span class="sxs-lookup"><span data-stu-id="40980-229">From the table, copy the Destination or Points to Address value.</span></span> <span data-ttu-id="40980-230">您在下一步會需要這項資訊。</span><span class="sxs-lookup"><span data-stu-id="40980-230">You'll need it for the next step.</span></span> <span data-ttu-id="40980-231">我們建議您複製並貼上此值，如此一來，所有的間距皆會保持正確。</span><span class="sxs-lookup"><span data-stu-id="40980-231">We recommend copying and pasting this value, so that all of the spacing stays correct.</span></span>

<span data-ttu-id="40980-232">新增 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-232">Add a TXT record.</span></span> 
-  <span data-ttu-id="40980-233">在您網域的 [DNS 管理員] 頁面上，移至 [**動作** \> **文字（TXT）**]。</span><span class="sxs-lookup"><span data-stu-id="40980-233">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-   <span data-ttu-id="40980-234">在 [**新增資源記錄**] 對話方塊中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="40980-234">In the **New Resource Record** dialog box, select **Edit**.</span></span>  
-  <span data-ttu-id="40980-235">在 [**新增資源記錄**] 對話方塊的 [**自訂主機名稱**] 區域中，確定欄位已設定為嚴格下列的值。</span><span class="sxs-lookup"><span data-stu-id="40980-235">In the **Custom Host Names** area of the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="40980-236">在某些 Windows DNS 管理員版本中，可能已設定網域，因此當您建立 txt 記錄時，首頁名稱會預設為上層網域。</span><span class="sxs-lookup"><span data-stu-id="40980-236">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="40980-237">在此情況中，當您新增 TXT 記錄時，請將主機名稱設定為空白 (無值)，而不是將它設定為 @ 或網域名稱。</span><span class="sxs-lookup"><span data-stu-id="40980-237">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

- <span data-ttu-id="40980-238">主機名稱：@</span><span class="sxs-lookup"><span data-stu-id="40980-238">Host Name: @</span></span>
- <span data-ttu-id="40980-239">類型： TXT</span><span class="sxs-lookup"><span data-stu-id="40980-239">Type: TXT</span></span>
- <span data-ttu-id="40980-240">Address：貼上您剛從 Office 365 複製的目的地或指向位址值。</span><span class="sxs-lookup"><span data-stu-id="40980-240">Address: Paste the Destination or Points to Address value that you just copied from Office 365 here.</span></span>  
- <span data-ttu-id="40980-241">選取 **[確定** > **完成**]。</span><span class="sxs-lookup"><span data-stu-id="40980-241">Select **OK** > **Done**.</span></span>

<span data-ttu-id="40980-242">在 Office 365 驗證您的網域。</span><span class="sxs-lookup"><span data-stu-id="40980-242">Verify your domain in Office 365.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="40980-243">請等候大約15分鐘，再執行這項作業，這樣您剛才建立的記錄便可在網際網路上更新。</span><span class="sxs-lookup"><span data-stu-id="40980-243">Wait about 15 minutes before you do this, so the record you just created can update across the Internet.</span></span>       

- <span data-ttu-id="40980-244">回到 Office 365，然後按照下列步驟要求驗證檢查。</span><span class="sxs-lookup"><span data-stu-id="40980-244">Go back to Office 365 and follow the steps below to request a verification check.</span></span> <span data-ttu-id="40980-245">這項檢查會尋找您在上述步驟中新增的 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="40980-245">The check looks for the TXT record you added in the previous step.</span></span> <span data-ttu-id="40980-246">找到正確的 TXT 記錄之後，網域即驗證完畢。</span><span class="sxs-lookup"><span data-stu-id="40980-246">When it finds the correct TXT record, the domain is verified.</span></span>  
1. <span data-ttu-id="40980-247">在系統管理中心中，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="40980-247">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
2. <span data-ttu-id="40980-248">在 [**網域**] 頁面上，于您所驗證之網域的 [**動作**] 欄中，選取 [**開始設定**]。</span><span class="sxs-lookup"><span data-stu-id="40980-248">On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**.</span></span> 
3. <span data-ttu-id="40980-249">在 [**確認您擁有您的網域**] 頁面上，選取 [**完成，立即驗證**]，然後在確認對話方塊中，選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="40980-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span></span> 
   
> [!NOTE]
>  <span data-ttu-id="40980-p117">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="40980-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a><span data-ttu-id="40980-253">在內部部署 Active Directory 中用來做為 UPN 的非可路由電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="40980-253">Non-routable email address used as a UPN in your on-prem Active Directory</span></span>
<span data-ttu-id="40980-254"><a name="BKMK_ADNote"> </a></span><span class="sxs-lookup"><span data-stu-id="40980-254"><a name="BKMK_ADNote"> </a></span></span>

<span data-ttu-id="40980-255">如果您計劃同步處理內部部署 Active Directory 與 Office 365，您會想要確認 Active Directory 使用者主體名稱 (UPN) 尾碼是有效的網域尾碼，而非不受支援的網域尾碼，例如 @contoso.local。</span><span class="sxs-lookup"><span data-stu-id="40980-255">If you're planning to synchronize your on-premises Active Directory with Office 365, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local.</span></span> <span data-ttu-id="40980-256">如果您需要變更 UPN 尾碼，請參閱 how [to prepare a 不可路由的網域以進行目錄同步](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7)處理。</span><span class="sxs-lookup"><span data-stu-id="40980-256">If you need to change your UPN suffix, see [How to prepare a non-routable domain for directory synchronization](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="40980-p119">DNS 變更生效通常約需 15 分鐘的時間。而如果您所做的變更要在整個網際網路 DNS 系統中生效，有時可能需要更久的時間。在您新增 DNS 記錄後，如有郵件流程或其他方面的問題，請參閱[變更網域名稱或 DNS 記錄之後所發生問題的疑難排解](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="40980-p119">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
