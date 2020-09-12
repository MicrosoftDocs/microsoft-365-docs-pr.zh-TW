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
ms.openlocfilehash: 8db74c04335e0846666991d74980648cedb4d9d7
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547127"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="6dab0-103">如何設定 Exchange Server 內部部署以使用混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="6dab0-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="6dab0-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="6dab0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6dab0-105">混合式新式驗證 (HMA) 是一種提供更安全的使用者驗證和授權方法，可供 Exchange server 內部部署混合式部署使用。</span><span class="sxs-lookup"><span data-stu-id="6dab0-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="6dab0-106">僅供參考</span><span class="sxs-lookup"><span data-stu-id="6dab0-106">FYI</span></span>

<span data-ttu-id="6dab0-107">開始之前，我會致電：</span><span class="sxs-lookup"><span data-stu-id="6dab0-107">Before we begin, I call:</span></span>

- <span data-ttu-id="6dab0-108">混合式新式驗證 \> HMA</span><span class="sxs-lookup"><span data-stu-id="6dab0-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="6dab0-109">Exchange 內部部署 \> nm-exch-um-2nd</span><span class="sxs-lookup"><span data-stu-id="6dab0-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="6dab0-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="6dab0-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="6dab0-111">此外， *如果本文中的圖形具有 ' 變暗」或「暗灰色」的物件，表示以灰色顯示的元素不會包含在 HMA 特定* 的設定中。</span><span class="sxs-lookup"><span data-stu-id="6dab0-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration* .</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="6dab0-112">啟用混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="6dab0-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="6dab0-113">開啟 HMA 的方式：</span><span class="sxs-lookup"><span data-stu-id="6dab0-113">Turning HMA on means:</span></span>

1. <span data-ttu-id="6dab0-114">在您開始之前，請確定您已符合必要條件。</span><span class="sxs-lookup"><span data-stu-id="6dab0-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="6dab0-115">由於商務用 Skype 和 Exchange 皆是許多 **必要條件** ，所以 [混合新式驗證概述和必要條件搭配內部部署商務用 Skype 和 Exchange 伺服器使用它](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6dab0-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="6dab0-116">在您開始進行本文中的任何步驟之前，請先執行此動作。</span><span class="sxs-lookup"><span data-stu-id="6dab0-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="6dab0-117">將內部部署 web 服務 URLs 新增為 **服務主體名稱 (** Azure AD 中的 spn) 。</span><span class="sxs-lookup"><span data-stu-id="6dab0-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="6dab0-118">確保所有虛擬目錄都已啟用 HMA</span><span class="sxs-lookup"><span data-stu-id="6dab0-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="6dab0-119">檢查 EvoSTS 驗證服務器物件</span><span class="sxs-lookup"><span data-stu-id="6dab0-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="6dab0-120">啟用 NM-EXCH-UM-2ND 中的 HMA。</span><span class="sxs-lookup"><span data-stu-id="6dab0-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="6dab0-121">**記事** 您的 Office 版本是否支援 MA？</span><span class="sxs-lookup"><span data-stu-id="6dab0-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="6dab0-122">請參閱 [如何在 office 2013 和 office 2016 用戶端應用程式中運作新式驗證](modern-auth-for-office-2013-and-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="6dab0-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="6dab0-123">請確認您符合所有必要條件</span><span class="sxs-lookup"><span data-stu-id="6dab0-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="6dab0-124">由於商務用 Skype 和 Exchange 一般都有許多必要條件，所以請參閱 [混合式新式驗證概述和使用內部部署商務用 skype 和 Exchange 伺服器的必要條件](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6dab0-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="6dab0-125">在您開始進行本文中的任何步驟之前，請  *先*  執行此動作。</span><span class="sxs-lookup"><span data-stu-id="6dab0-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="6dab0-126">在 Azure AD 中將內部部署 web 服務 URLs 當做 Spn 新增</span><span class="sxs-lookup"><span data-stu-id="6dab0-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="6dab0-127">執行將您的內部部署 web 服務 URLs 指派為 Azure AD Spn 的命令。</span><span class="sxs-lookup"><span data-stu-id="6dab0-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="6dab0-128">在驗證和授權期間，用戶端機器和裝置會使用 Spn。</span><span class="sxs-lookup"><span data-stu-id="6dab0-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="6dab0-129">所有可能用來從內部部署至 Azure Active Directory (Azure AD) 的 URLs，都必須在 Azure AD 中註冊， (這包括內部及外部命名空間) 。</span><span class="sxs-lookup"><span data-stu-id="6dab0-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="6dab0-130">首先，請收集您需要在 AAD 中新增的所有 URLs。</span><span class="sxs-lookup"><span data-stu-id="6dab0-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="6dab0-131">在內部部署執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6dab0-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="6dab0-132">確定用戶端可以連線的 URLs 已列為 AAD 中的 HTTPS 服務主體名稱。</span><span class="sxs-lookup"><span data-stu-id="6dab0-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="6dab0-133">首先，使用 [這些指示](connect-to-microsoft-365-powershell.md)連接至 AAD。</span><span class="sxs-lookup"><span data-stu-id="6dab0-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="6dab0-134">**記事** 您必須使用此頁面上的 _Connect-MsolService_ 選項，才能使用下列命令。</span><span class="sxs-lookup"><span data-stu-id="6dab0-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="6dab0-135">針對您的 Exchange 相關 URLs，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="6dab0-135">For your Exchange related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="6dab0-136">記下 (和螢幕擷取畫面，以供稍後比較) 此命令的輸出應包含 HTTPs://  *autodiscover.yourdomain.com*  和 Https://  *mail.yourdomain.com* URL，但通常是由以 00000002-0000-0Ff1-ce00-000000000000/開頭的 spn 所組成。</span><span class="sxs-lookup"><span data-stu-id="6dab0-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="6dab0-137">如果從您的內部部署 HTTPs://URLs，將需要將這些特定記錄新增至此清單。</span><span class="sxs-lookup"><span data-stu-id="6dab0-137">If there are https:// URLs from your on-premises that are missing we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="6dab0-138">如果您沒有看到您的內部及外部 MAPI/HTTP、EWS、ActiveSync、OAB 及自動探索記錄，您必須使用下列命令來新增， (範例 URLs 是 ' `mail.corp.contoso.com` ' 和 ' ' `owa.contoso.com` ，但是您會 \*\*以您自己的 URLs 取代範例 ) \*\* ：</span><span class="sxs-lookup"><span data-stu-id="6dab0-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own** ):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="6dab0-139">再次執行步驟2上的 New-msolserviceprincipal 命令，然後查看輸出，以確認新增的記錄已新增。</span><span class="sxs-lookup"><span data-stu-id="6dab0-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="6dab0-140">將清單/螢幕擷取畫面與新的 Spn 清單進行比較 (您也可以將記錄新增至新清單) 。</span><span class="sxs-lookup"><span data-stu-id="6dab0-140">Compare the list / screenshot from before to the new list of SPNs (you may also screenshot the new list for your records).</span></span> <span data-ttu-id="6dab0-141">如果您成功，您會在清單中看到兩個新的 URLs。</span><span class="sxs-lookup"><span data-stu-id="6dab0-141">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="6dab0-142">接下來的範例，Spn 清單現在會包含特定的 URLs  `https://mail.corp.contoso.com`  和  `https://owa.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="6dab0-142">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="6dab0-143">確認已正確設定虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="6dab0-143">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="6dab0-144">現在，請執行下列命令，確認已在 Exchange 上針對所有可用的虛擬目錄，確認是否已在 Exchange 上正確啟用 OAuth：</span><span class="sxs-lookup"><span data-stu-id="6dab0-144">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="6dab0-145">檢查輸出，確定每個 VDirs 都已啟用 **OAuth** ，它看起來像這樣 (，而要查看的關鍵事項是「OAuth ' ) ：</span><span class="sxs-lookup"><span data-stu-id="6dab0-145">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="6dab0-146">如果任何伺服器及任何四個虛擬目錄中的 OAuth 都缺失，您必須使用相關命令新增它，然後再繼續 ([設定 MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory)、 [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory)、 [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)及 [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)) 。</span><span class="sxs-lookup"><span data-stu-id="6dab0-146">If OAuth is missing from any server and any of the four virtual directories then you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="6dab0-147">確認 EvoSTS 驗證服務器物件存在</span><span class="sxs-lookup"><span data-stu-id="6dab0-147">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="6dab0-148">回到此最後一個命令的內部部署 Exchange 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="6dab0-148">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="6dab0-149">現在，您可以驗證您的內部部署是否具有 evoSTS 驗證提供者的專案：</span><span class="sxs-lookup"><span data-stu-id="6dab0-149">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="6dab0-150">您的輸出應顯示名稱為 EvoSts 的 Set-authserver，且 [Enabled] 狀態應該為 True。</span><span class="sxs-lookup"><span data-stu-id="6dab0-150">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="6dab0-151">如果您未看到此內容，您應該下載並執行最新版本的混合式設定向導。</span><span class="sxs-lookup"><span data-stu-id="6dab0-151">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="6dab0-152">**重要事項** 如果您正在環境中執行 Exchange 2010，將不會建立 EvoSTS 驗證提供者。</span><span class="sxs-lookup"><span data-stu-id="6dab0-152">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="6dab0-153">啟用 HMA</span><span class="sxs-lookup"><span data-stu-id="6dab0-153">Enable HMA</span></span>

<span data-ttu-id="6dab0-154">在 Exchange 管理命令介面內部部署中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6dab0-154">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="6dab0-155">驗證</span><span class="sxs-lookup"><span data-stu-id="6dab0-155">Verify</span></span>

<span data-ttu-id="6dab0-156">一旦您啟用 HMA，用戶端的下一個登入將會使用新的驗證流程。</span><span class="sxs-lookup"><span data-stu-id="6dab0-156">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="6dab0-157">請注意，只要開啟 HMA，就不會觸發任何用戶端的重新驗證。</span><span class="sxs-lookup"><span data-stu-id="6dab0-157">Note that just turning on HMA won't trigger a re-authentication for any client.</span></span> <span data-ttu-id="6dab0-158">用戶端會根據驗證權杖和/或憑證的存留時間，重新進行驗證。</span><span class="sxs-lookup"><span data-stu-id="6dab0-158">The clients re-authenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="6dab0-159">您也應該同時按住 CTRL 鍵，以滑鼠右鍵按一下 Outlook 用戶端的圖示 (也在 Windows 通知盤) 中，然後按一下 [線上狀態]。</span><span class="sxs-lookup"><span data-stu-id="6dab0-159">You should also hold down the CTRL key at the same time you right click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="6dab0-160">根據 ' Authn ' 類型的 ' 載體 ' 尋找用戶端的 SMTP 位址 \* ，它代表 OAuth 中使用的持有者權杖。</span><span class="sxs-lookup"><span data-stu-id="6dab0-160">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="6dab0-161">**記事** 需要使用 HMA 設定商務用 Skype？</span><span class="sxs-lookup"><span data-stu-id="6dab0-161">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="6dab0-162">您將需要兩個文章：一個會列出 [支援的拓撲](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)，另一個說明 [如何進行](configure-skype-for-business-for-hybrid-modern-authentication.md)設定。</span><span class="sxs-lookup"><span data-stu-id="6dab0-162">You'll need two articles: One that lists [supported topologies](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="6dab0-163">對 Outlook for iOS 和 Android 使用混合新式驗證</span><span class="sxs-lookup"><span data-stu-id="6dab0-163">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="6dab0-164">如果您是使用 TCP 443 上 Exchange server 的內部部署客戶，請將下列 IP 範圍列入白名單：</span><span class="sxs-lookup"><span data-stu-id="6dab0-164">If you are an on-premises customer using Exchange server on TCP 443, please whitelist the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="6dab0-165">相關主題</span><span class="sxs-lookup"><span data-stu-id="6dab0-165">Related topics</span></span>

[<span data-ttu-id="6dab0-166">從 Office 365 專屬/ITAR 轉換為 vNext 的新式驗證設定需求</span><span class="sxs-lookup"><span data-stu-id="6dab0-166">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
