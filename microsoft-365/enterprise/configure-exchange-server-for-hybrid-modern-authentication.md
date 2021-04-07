---
title: 如何設定 Exchange Server 內部部署以使用混合式新式驗證
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: 瞭解如何設定 Exchange Server 內部部署以使用混合式新式驗證 (HMA) ，為您提供更安全的使用者驗證和授權。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e0a0e521f4ac81a8aa113b2e945045d31f2c1952
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599496"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="c8747-103">如何設定 Exchange Server 內部部署以使用混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="c8747-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="c8747-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="c8747-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c8747-105">混合式新式驗證 (HMA) 是一種提供更安全的使用者驗證和授權方法，可供 Exchange server 內部部署混合式部署使用。</span><span class="sxs-lookup"><span data-stu-id="c8747-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="c8747-106">僅供參考</span><span class="sxs-lookup"><span data-stu-id="c8747-106">FYI</span></span>

<span data-ttu-id="c8747-107">開始之前，我會致電：</span><span class="sxs-lookup"><span data-stu-id="c8747-107">Before we begin, I call:</span></span>

- <span data-ttu-id="c8747-108">混合式新式驗證 \> HMA</span><span class="sxs-lookup"><span data-stu-id="c8747-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="c8747-109">Exchange 內部部署 \> nm-exch-um-2nd</span><span class="sxs-lookup"><span data-stu-id="c8747-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="c8747-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="c8747-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="c8747-111">此外， *如果本文中的圖形具有 ' 變暗」或「暗灰色」的物件，表示以灰色顯示的元素不會包含在 HMA 特定* 的設定中。</span><span class="sxs-lookup"><span data-stu-id="c8747-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="c8747-112">啟用混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="c8747-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="c8747-113">開啟 HMA 表示：</span><span class="sxs-lookup"><span data-stu-id="c8747-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="c8747-114">在您開始之前，請確定您已符合必要條件。</span><span class="sxs-lookup"><span data-stu-id="c8747-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="c8747-115">由於商務用 Skype 和 Exchange 皆是許多 **必要條件** ，所以 [混合新式驗證概述和必要條件搭配內部部署商務用 Skype 和 Exchange 伺服器使用它](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c8747-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="c8747-116">在您開始進行本文中的任何步驟之前，請先執行此動作。</span><span class="sxs-lookup"><span data-stu-id="c8747-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="c8747-117">將內部部署 web 服務 URLs 新增為 **服務主體名稱 (** Azure AD 中的 spn) 。</span><span class="sxs-lookup"><span data-stu-id="c8747-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span> <span data-ttu-id="c8747-118">在 NM-EXCH-UM-2ND 與 **多個承租人** 混合的情況下，這些內部部署 web 服務 URLs 必須新增為與 nm-exch-um-2nd 混合的所有承租人 Azure AD 中的 spn。</span><span class="sxs-lookup"><span data-stu-id="c8747-118">In case EXCH is in hybrid with **multiple tenants**, these on-premises web service URLs must be added as SPNs in the Azure AD of all the tenants which are in hybrid with EXCH.</span></span>

1. <span data-ttu-id="c8747-119">確保所有虛擬目錄都已啟用 HMA</span><span class="sxs-lookup"><span data-stu-id="c8747-119">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="c8747-120">檢查 EvoSTS 驗證服務器物件</span><span class="sxs-lookup"><span data-stu-id="c8747-120">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="c8747-121">啟用 NM-EXCH-UM-2ND 中的 HMA。</span><span class="sxs-lookup"><span data-stu-id="c8747-121">Enabling HMA in EXCH.</span></span>

> [!NOTE]
> <span data-ttu-id="c8747-122">您的 Office 版本是否支援 MA？</span><span class="sxs-lookup"><span data-stu-id="c8747-122">Does your version of Office support MA?</span></span> <span data-ttu-id="c8747-123">請參閱 [如何在 office 2013 和 office 2016 用戶端應用程式中運作新式驗證](modern-auth-for-office-2013-and-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="c8747-123">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>


## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="c8747-124">請確認您符合所有必要條件</span><span class="sxs-lookup"><span data-stu-id="c8747-124">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="c8747-125">由於商務用 Skype 和 Exchange 一般都有許多必要條件，所以請參閱 [混合式新式驗證概述和使用內部部署商務用 skype 和 Exchange 伺服器的必要條件](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c8747-125">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="c8747-126">在您開始進行本文中的任何步驟之前，請  *先*  執行此動作。</span><span class="sxs-lookup"><span data-stu-id="c8747-126">Do this  *before*  you begin any of the steps in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="c8747-127">Outlook Web App 和 Exchange 控制台無法與混合式新式驗證一起運作。</span><span class="sxs-lookup"><span data-stu-id="c8747-127">Outlook Web App and Exchange Control Panel does not work with hybrid Modern Authentication.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="c8747-128">在 Azure AD 中將內部部署 web 服務 URLs 當做 Spn 新增</span><span class="sxs-lookup"><span data-stu-id="c8747-128">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="c8747-129">執行將您的內部部署 web 服務 URLs 指派為 Azure AD Spn 的命令。</span><span class="sxs-lookup"><span data-stu-id="c8747-129">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="c8747-130">在驗證和授權期間，用戶端機器和裝置會使用 Spn。</span><span class="sxs-lookup"><span data-stu-id="c8747-130">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="c8747-131">所有可能用來從內部部署至 Azure Active Directory (Azure AD) 的 URLs，都必須在 Azure AD 中註冊， (這包括內部及外部命名空間) 。</span><span class="sxs-lookup"><span data-stu-id="c8747-131">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="c8747-132">首先，請收集您需要在 AAD 中新增的所有 URLs。</span><span class="sxs-lookup"><span data-stu-id="c8747-132">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="c8747-133">在內部部署執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c8747-133">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="c8747-134">確定用戶端可以連線的 URLs 已列為 AAD 中的 HTTPS 服務主體名稱。</span><span class="sxs-lookup"><span data-stu-id="c8747-134">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span> <span data-ttu-id="c8747-135">在 NM-EXCH-UM-2ND 與 **多個承租人** 混合的情況下，這些 HTTPS spn 應新增在與 nm-exch-um-2nd 混合之所有承租人的 AAD 中。</span><span class="sxs-lookup"><span data-stu-id="c8747-135">In case EXCH is in hybrid with **multiple tenants**, these HTTPS SPNs should be added in the AAD of all the tenants in hybrid with EXCH.</span></span>

1. <span data-ttu-id="c8747-136">首先，使用 [這些指示](connect-to-microsoft-365-powershell.md)連接至 AAD。</span><span class="sxs-lookup"><span data-stu-id="c8747-136">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c8747-137">您必須使用此頁面上的 _Connect-MsolService_ 選項，才能使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="c8747-137">You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="c8747-138">若為 Exchange 相關的 URLs，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c8747-138">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="c8747-139">記下 (和螢幕擷取畫面，以供稍後比較) 此命令的輸出應包含 HTTPs://  *autodiscover.yourdomain.com*  和 Https://  *mail.yourdomain.com* URL，但通常是由以 00000002-0000-0Ff1-ce00-000000000000/開頭的 spn 所組成。</span><span class="sxs-lookup"><span data-stu-id="c8747-139">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="c8747-140">如果從您的內部部署 HTTPs://URLs，我們需要將這些特定記錄新增至此清單。</span><span class="sxs-lookup"><span data-stu-id="c8747-140">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="c8747-141">如果您未在此清單中看到您的內部及外部 MAPI/HTTP、EWS、ActiveSync、OAB 及自動探索記錄，您必須使用下列命令新增這些記錄， (範例 URLs 是 ' `mail.corp.contoso.com` ' 和 ' ' `owa.contoso.com` ，但是您會 **以您自己的 URLs 取代範例)** ：</span><span class="sxs-lookup"><span data-stu-id="c8747-141">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="c8747-142">再次執行步驟2的 Get-MsolServicePrincipal 命令，然後查看輸出，以確認新增的記錄已新增。</span><span class="sxs-lookup"><span data-stu-id="c8747-142">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="c8747-143">將清單/螢幕擷取畫面與新的 Spn 清單進行比較。</span><span class="sxs-lookup"><span data-stu-id="c8747-143">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="c8747-144">您也可以取得記錄的新清單的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="c8747-144">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="c8747-145">如果您成功，您會在清單中看到兩個新的 URLs。</span><span class="sxs-lookup"><span data-stu-id="c8747-145">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="c8747-146">接下來的範例，Spn 清單現在會包含特定的 URLs  `https://mail.corp.contoso.com`  和  `https://owa.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="c8747-146">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="c8747-147">確認已正確設定虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="c8747-147">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="c8747-148">現在，請執行下列命令，確認已在 Exchange 上針對所有可用的虛擬目錄，確認是否已在 Exchange 上正確啟用 OAuth：</span><span class="sxs-lookup"><span data-stu-id="c8747-148">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="c8747-149">檢查輸出，確定每個 VDirs 都已啟用 **OAuth** ，它看起來像這樣 (，而要查看的關鍵事項是「OAuth ' ) ：</span><span class="sxs-lookup"><span data-stu-id="c8747-149">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="c8747-150">如果任何伺服器和任何四個虛擬目錄中的 OAuth 都缺失，您必須使用相關命令新增它，才能繼續 ([設定 MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory)、 [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory)、 [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)及 [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)) 。</span><span class="sxs-lookup"><span data-stu-id="c8747-150">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="c8747-151">確認 EvoSTS 驗證服務器物件存在</span><span class="sxs-lookup"><span data-stu-id="c8747-151">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="c8747-152">回到此最後一個命令的內部部署 Exchange 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="c8747-152">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="c8747-153">現在，您可以驗證您的內部部署是否具有 evoSTS 驗證提供者的專案：</span><span class="sxs-lookup"><span data-stu-id="c8747-153">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="c8747-154">您的輸出應顯示名稱為 EvoSts 的 Set-authserver，且 [Enabled] 狀態應該為 True。</span><span class="sxs-lookup"><span data-stu-id="c8747-154">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="c8747-155">如果您未看到此內容，您應該下載並執行最新版本的混合式設定向導。</span><span class="sxs-lookup"><span data-stu-id="c8747-155">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="c8747-156">在 NM-EXCH-UM-2ND 與 **多個承租人** 混合的情況下，您的輸出應該會顯示每個承租人中每個租使用者名稱 EvoSts {GUID} 的 set-authserver，且所有 set-authserver 物件的「Enabled」狀態應該是 True。</span><span class="sxs-lookup"><span data-stu-id="c8747-156">In case EXCH is in hybrid with **multiple tenants**, your output should show one AuthServer of the Name EvoSts - {GUID} for each tenant in hybrid with EXCH and the 'Enabled' state should be True for all of these AuthServer objects.</span></span>

 <span data-ttu-id="c8747-157">**重要事項** 如果您正在環境中執行 Exchange 2010，將不會建立 EvoSTS 驗證提供者。</span><span class="sxs-lookup"><span data-stu-id="c8747-157">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="c8747-158">啟用 HMA</span><span class="sxs-lookup"><span data-stu-id="c8747-158">Enable HMA</span></span>

<span data-ttu-id="c8747-159">在 Exchange 管理命令介面內部部署中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c8747-159">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

<span data-ttu-id="c8747-160">如果 NM-EXCH-UM-2ND 版本為 Exchange 2016 (CU18 或更高版本) 或 Exchange 2019 (CU7 或更高版本) 和混合已設定 HCW 在2020年9月之後下載，請在 Exchange 管理命令介面（內部部署）上執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c8747-160">If the EXCH version is Exchange 2016 (CU18 or higher) or Exchange 2019 (CU7 or higher) and hybrid was configured with HCW downloaded after September 2020, run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -Domain "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> <span data-ttu-id="c8747-161">在 NM-EXCH-UM-2ND 與 **多個承租人** 混合的情況下，nm-exch-um-2nd 中有多個 set-authserver 物件會與每個租使用者對應的網域一起存在。</span><span class="sxs-lookup"><span data-stu-id="c8747-161">In case EXCH is in hybrid with **multiple tenants**, there are multiple AuthServer objects present in EXCH with domains corresponding to each tenant.</span></span>  <span data-ttu-id="c8747-162">**IsDefaultAuthorizationEndpoint** 旗標應設定為 true (使用 **IsDefaultAuthorizationEndpoint** 指令程式) 以上任何一個 set-authserver 物件。</span><span class="sxs-lookup"><span data-stu-id="c8747-162">The **IsDefaultAuthorizationEndpoint** flag should be set to true (using the **IsDefaultAuthorizationEndpoint** cmdlet) for any one of these AuthServer objects.</span></span> <span data-ttu-id="c8747-163">即使其中一個 Set-authserver 物件的 **IsDefaultAuthorizationEndpoint** 旗標設定為 true，這個旗標也不能設定為 True，set-authserver 物件和 HMA 都會啟用。</span><span class="sxs-lookup"><span data-stu-id="c8747-163">This flag can't be set to true for all the Authserver objects and HMA would be enabled even if one of these AuthServer object's **IsDefaultAuthorizationEndpoint** flag is set to true.</span></span>

## <a name="verify"></a><span data-ttu-id="c8747-164">驗證</span><span class="sxs-lookup"><span data-stu-id="c8747-164">Verify</span></span>

<span data-ttu-id="c8747-165">一旦您啟用 HMA，用戶端的下一個登入將會使用新的驗證流程。</span><span class="sxs-lookup"><span data-stu-id="c8747-165">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="c8747-166">請注意，只要開啟 HMA，就不會對任何用戶端觸發重新驗證。</span><span class="sxs-lookup"><span data-stu-id="c8747-166">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="c8747-167">用戶端會根據驗證權杖和/或憑證的存留時間來驗證。</span><span class="sxs-lookup"><span data-stu-id="c8747-167">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="c8747-168">您也應該同時按住 CTRL 鍵，以滑鼠右鍵按一下 Outlook 用戶端 (圖示，也可以在 Windows 通知託盤) 中，然後按一下 [線上狀態]。</span><span class="sxs-lookup"><span data-stu-id="c8747-168">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="c8747-169">根據 ' Authn ' 類型的 ' 載體 ' 尋找用戶端的 SMTP 位址 \* ，它代表 OAuth 中使用的持有者權杖。</span><span class="sxs-lookup"><span data-stu-id="c8747-169">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

> [!NOTE]
> <span data-ttu-id="c8747-170">需要使用 HMA 設定商務用 Skype？</span><span class="sxs-lookup"><span data-stu-id="c8747-170">Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="c8747-171">您將需要兩個文章：一個會列出 [支援的拓撲](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)，另一個說明 [如何進行](configure-skype-for-business-for-hybrid-modern-authentication.md)設定。</span><span class="sxs-lookup"><span data-stu-id="c8747-171">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="c8747-172">對 Outlook for iOS 和 Android 使用混合新式驗證</span><span class="sxs-lookup"><span data-stu-id="c8747-172">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="c8747-173">如果您是使用 TCP 443 上 Exchange server 的內部部署客戶，請略過下列 IP 位址範圍的流量處理：</span><span class="sxs-lookup"><span data-stu-id="c8747-173">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP address ranges:</span></span>

```
52.125.128.0/20
52.127.96.0/23
```

<span data-ttu-id="c8747-174">適用于 iOS 和 Android 的 Outlook 應用程式是設計為使用 Microsoft 服務在行動裝置上體驗 Microsoft 365 或 Office 365 的最佳方式，以協助您尋找、規劃及設定每日生命週期和工作的優先順序。</span><span class="sxs-lookup"><span data-stu-id="c8747-174">The Outlook app for iOS and Android is designed as the best way to experience Microsoft 365 or Office 365 on your mobile device by using Microsoft services to help find, plan, and prioritize your daily life and work.</span></span> <span data-ttu-id="c8747-175">如需詳細資訊，請參閱對 [使用 Outlook 的混合新式驗證 iOS 和 Android](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019)。</span><span class="sxs-lookup"><span data-stu-id="c8747-175">For more information, please refer to [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c8747-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="c8747-176">Related topics</span></span>

[<span data-ttu-id="c8747-177">從 Office 365 專屬/ITAR 轉換為 vNext 的新式驗證設定需求</span><span class="sxs-lookup"><span data-stu-id="c8747-177">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
