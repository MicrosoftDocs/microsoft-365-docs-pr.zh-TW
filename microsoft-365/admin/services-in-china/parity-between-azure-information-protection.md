---
title: 由世紀運作之 Office 365 的 Azure 資訊保護支援
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: 深入瞭解 Azure 資訊保護的詳細資訊，請 (AIP) ，以供世紀運作 Office 365 以及如何為中國的客戶進行設定。
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535839"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="c3e48-103">由世紀運作之 Office 365 的 Azure 資訊保護支援</span><span class="sxs-lookup"><span data-stu-id="c3e48-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="c3e48-104">本文涵蓋 Azure 資訊保護 (AIP) 支援的 Office 365 （由世紀和商業產品運作），以及在中國為客戶設定 AIP 的特定指示， &mdash; 包括如何安裝 AIP 內部部署掃描器及管理內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="c3e48-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="c3e48-105">AIP 和商務版產品所運作的 Office 365 之間的差異</span><span class="sxs-lookup"><span data-stu-id="c3e48-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="c3e48-106">雖然我們的目標是將所有商業功能和功能提供給中國的客戶 AIP，以供由世紀所運作的 Office 365 使用，但仍有一些遺漏的功能可供您反白。</span><span class="sxs-lookup"><span data-stu-id="c3e48-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="c3e48-107">下列清單包含 AIP 在由世紀所運作的 Office 365 之間的現有缺口，以及從2021年1月的商業產品方案：</span><span class="sxs-lookup"><span data-stu-id="c3e48-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="c3e48-108">只有 Microsoft 365 Apps 企業版 (組建11731.10000 或更新) 版本，才支援資訊版權管理 (IRM) 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="c3e48-109">Office 2010、Office 2013 及其他 Office 2016 版本都不受支援。</span><span class="sxs-lookup"><span data-stu-id="c3e48-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="c3e48-110">目前無法使用從 Active Directory Rights Management Services (AD RMS) 遷移至 AIP。</span><span class="sxs-lookup"><span data-stu-id="c3e48-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="c3e48-111">支援與商業雲端中的使用者共用受保護的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c3e48-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="c3e48-112">目前無法使用商業雲端中的使用者共用檔和電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="c3e48-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="c3e48-113">這包括由使用者在商業雲端中運作的 Office 365、商業雲端中的世紀使用者運作的非 Office 365，以及具有 RMS for 個人授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="c3e48-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="c3e48-114">具有 SharePoint (irm 保護的網站與文件庫) 的 irm 目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="c3e48-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="c3e48-115">目前無法使用 AD RMS 的行動裝置分機。</span><span class="sxs-lookup"><span data-stu-id="c3e48-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="c3e48-116">Azure 中國的世紀不支援行動 [檢視器](/azure/information-protection/rms-client/mobile-app-faq) 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="c3e48-117">中國的客戶無法使用 Azure 入口網站的 AIP 區域。</span><span class="sxs-lookup"><span data-stu-id="c3e48-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="c3e48-118">使用 [PowerShell 命令](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) ，而不是在入口網站中執行動作，例如管理及執行內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="c3e48-118">Use [PowerShell commands](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as managing and running your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="c3e48-119">為中國的客戶設定 AIP</span><span class="sxs-lookup"><span data-stu-id="c3e48-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="c3e48-120">若要為中國的客戶設定 AIP：</span><span class="sxs-lookup"><span data-stu-id="c3e48-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="c3e48-121">[啟用租使用者的 Rights Management](#step-1-enable-rights-management-for-the-tenant)。</span><span class="sxs-lookup"><span data-stu-id="c3e48-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

1. <span data-ttu-id="c3e48-122">[新增 Microsoft Information Protection Sync service 服務主體](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)。</span><span class="sxs-lookup"><span data-stu-id="c3e48-122">[Add the Microsoft Information Protection Sync Service service principal](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).</span></span>

1. <span data-ttu-id="c3e48-123">[設定 DNS 加密](#step-3-configure-dns-encryption)。</span><span class="sxs-lookup"><span data-stu-id="c3e48-123">[Configure DNS encryption](#step-3-configure-dns-encryption).</span></span>

1. <span data-ttu-id="c3e48-124">[安裝及設定 AIP 的整合標籤用戶端](#step-4-install-and-configure-the-aip-unified-labeling-client)。</span><span class="sxs-lookup"><span data-stu-id="c3e48-124">[Install and configure the AIP unified labeling client](#step-4-install-and-configure-the-aip-unified-labeling-client).</span></span>

1. <span data-ttu-id="c3e48-125">[在 Windows 上設定 AIP 應用程式](#step-5-configure-aip-apps-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="c3e48-125">[Configure AIP apps on Windows](#step-5-configure-aip-apps-on-windows).</span></span>

1. <span data-ttu-id="c3e48-126">[安裝 AIP 內部部署掃描程式並管理內容掃描工作](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。</span><span class="sxs-lookup"><span data-stu-id="c3e48-126">[Install the AIP on-premises scanner and manage content scan jobs](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="c3e48-127">步驟1：啟用租使用者的版權管理</span><span class="sxs-lookup"><span data-stu-id="c3e48-127">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="c3e48-128">為使加密正確運作，必須對租使用者啟用 RMS。</span><span class="sxs-lookup"><span data-stu-id="c3e48-128">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="c3e48-129">檢查 RMS 是否已啟用：</span><span class="sxs-lookup"><span data-stu-id="c3e48-129">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="c3e48-130">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c3e48-130">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="c3e48-131">若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-131">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="c3e48-132">使用匯入模組 `Import-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-132">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="c3e48-133">使用服務連線 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="c3e48-134">執行 `(Get-AipServiceConfiguration).FunctionalState` 並檢查狀態是否為 `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-134">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="c3e48-135">如果功能狀態為 `Disabled` ，請執行 `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-135">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a><span data-ttu-id="c3e48-136">步驟2：新增 Microsoft 資訊保護同步服務服務主體</span><span class="sxs-lookup"><span data-stu-id="c3e48-136">Step 2: Add the Microsoft Information Protection Sync Service service principal</span></span>

<span data-ttu-id="c3e48-137">根據預設，Azure 中國租使用者無法使用 **Microsoft 資訊保護同步處理服務** 服務主體，Azure 資訊保護需要該主體。</span><span class="sxs-lookup"><span data-stu-id="c3e48-137">The **Microsoft Information Protection Sync Service** service principal is not available in Azure China tenants by default, and is required for Azure Information Protection.</span></span>

1. <span data-ttu-id="c3e48-138">使用 [AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) Cmdlet 及 `870c4f2e-85b6-4d43-bdda-6ed9a579b725` Microsoft Information Protection Sync service 的應用程式識別碼，手動建立此服務主體。</span><span class="sxs-lookup"><span data-stu-id="c3e48-138">Create this service principal manually using the [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet and the `870c4f2e-85b6-4d43-bdda-6ed9a579b725` application ID for the Microsoft Information Protection Sync Service.</span></span> 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. <span data-ttu-id="c3e48-139">新增服務主體後，新增服務所需的相關許可權。</span><span class="sxs-lookup"><span data-stu-id="c3e48-139">After adding the service principal, add the relevant permissions required to the service.</span></span>

### <a name="step-3-configure-dns-encryption"></a><span data-ttu-id="c3e48-140">步驟3：設定 DNS 加密</span><span class="sxs-lookup"><span data-stu-id="c3e48-140">Step 3: Configure DNS encryption</span></span>

<span data-ttu-id="c3e48-141">若要讓加密正確運作，Office 用戶端應用程式必須連接至服務的中國實例，並從那裡進行引導。</span><span class="sxs-lookup"><span data-stu-id="c3e48-141">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="c3e48-142">若要將用戶端應用程式重新導向至正確的服務實例，租使用者管理員必須使用 Azure RMS URL 的相關資訊來設定 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="c3e48-142">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="c3e48-143">若沒有 DNS SRV 記錄，用戶端應用程式會在預設會嘗試連線至公用雲端實例，否則會失敗。</span><span class="sxs-lookup"><span data-stu-id="c3e48-143">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="c3e48-144">此外，假設使用者將會以使用者身分登入，而不是以租使用者為基礎的網域 (來登入，例如 `joe@contoso.cn`) ，而不是使用者 `onmschina` 名稱 (例如 `joe@contoso.onmschina.cn`) 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-144">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="c3e48-145">Username 的功能變數名稱可用於將 DNS 重新導向至正確的服務實例。</span><span class="sxs-lookup"><span data-stu-id="c3e48-145">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="c3e48-146">設定 DNS 加密-Windows</span><span class="sxs-lookup"><span data-stu-id="c3e48-146">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="c3e48-147">取得 RMS ID:</span><span class="sxs-lookup"><span data-stu-id="c3e48-147">Get the RMS ID:</span></span>

    1. <span data-ttu-id="c3e48-148">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c3e48-148">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="c3e48-149">若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-149">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="c3e48-150">使用服務連線 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-150">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="c3e48-151">執行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以取得 RMS 識別碼。</span><span class="sxs-lookup"><span data-stu-id="c3e48-151">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="c3e48-152">登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="c3e48-152">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="c3e48-153">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="c3e48-153">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="c3e48-154">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="c3e48-154">Protocol = `_http`</span></span>
    - <span data-ttu-id="c3e48-155">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="c3e48-155">Name = `_tcp`</span></span>
    - <span data-ttu-id="c3e48-156">Target = `[GUID].rms.aadrm.cn` (其中 GUID 是 RMS 識別碼) </span><span class="sxs-lookup"><span data-stu-id="c3e48-156">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="c3e48-157">Priority，權數，Seconds，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="c3e48-157">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="c3e48-158">將自訂網域與 [Azure 入口網站](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的承租人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="c3e48-158">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="c3e48-159">這會在 DNS 中新增專案，當您將此值新增至 DNS 設定後，可能需要幾分鐘的時間來取得驗證。</span><span class="sxs-lookup"><span data-stu-id="c3e48-159">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="c3e48-160">使用對應的全域系統管理員認證登入 Microsoft 365 系統管理中心，並新增網域 (例如， `contoso.cn`) 供使用者建立。</span><span class="sxs-lookup"><span data-stu-id="c3e48-160">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="c3e48-161">在驗證程式中，可能需要進行其他 DNS 變更。</span><span class="sxs-lookup"><span data-stu-id="c3e48-161">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="c3e48-162">完成驗證之後，即可建立使用者。</span><span class="sxs-lookup"><span data-stu-id="c3e48-162">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="c3e48-163">設定 DNS 加密-Mac、iOS、Android</span><span class="sxs-lookup"><span data-stu-id="c3e48-163">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="c3e48-164">登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="c3e48-164">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="c3e48-165">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="c3e48-165">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="c3e48-166">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="c3e48-166">Protocol = `_http`</span></span>
- <span data-ttu-id="c3e48-167">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="c3e48-167">Name = `_tcp`</span></span>
- <span data-ttu-id="c3e48-168">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="c3e48-168">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="c3e48-169">埠 = `80`</span><span class="sxs-lookup"><span data-stu-id="c3e48-169">Port = `80`</span></span>
- <span data-ttu-id="c3e48-170">Priority，權數，Seconds，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="c3e48-170">Priority, Weight, Seconds, TTL = default values</span></span>


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="c3e48-171">步驟4：安裝及設定 AIP 的整合標籤用戶端</span><span class="sxs-lookup"><span data-stu-id="c3e48-171">Step 4: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="c3e48-172">從 [Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載並安裝 AIP 的整合標籤用戶端。</span><span class="sxs-lookup"><span data-stu-id="c3e48-172">Download and install the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="c3e48-173">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="c3e48-173">For more information, see:</span></span>

- [<span data-ttu-id="c3e48-174">AIP 檔</span><span class="sxs-lookup"><span data-stu-id="c3e48-174">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="c3e48-175">AIP 版本歷程記錄與支援原則</span><span class="sxs-lookup"><span data-stu-id="c3e48-175">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="c3e48-176">AIP 系統需求</span><span class="sxs-lookup"><span data-stu-id="c3e48-176">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="c3e48-177">AIP 快速入門：部署 AIP 用戶端</span><span class="sxs-lookup"><span data-stu-id="c3e48-177">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="c3e48-178">AIP 管理員指南</span><span class="sxs-lookup"><span data-stu-id="c3e48-178">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="c3e48-179">AIP 使用者指南</span><span class="sxs-lookup"><span data-stu-id="c3e48-179">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="c3e48-180">深入瞭解 Microsoft 365 敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="c3e48-180">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a><span data-ttu-id="c3e48-181">步驟5：在 Windows 上設定 AIP 應用程式</span><span class="sxs-lookup"><span data-stu-id="c3e48-181">Step 5: Configure AIP apps on Windows</span></span>

<span data-ttu-id="c3e48-182">Windows 上的 AIP 應用程式需要下列登錄機碼，將其指向正確的 Azure 中國以及主權雲端：</span><span class="sxs-lookup"><span data-stu-id="c3e48-182">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="c3e48-183">Registry 節點 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="c3e48-183">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="c3e48-184">名稱 = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="c3e48-184">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="c3e48-185">值 = `6` (預設值 = 0) </span><span class="sxs-lookup"><span data-stu-id="c3e48-185">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="c3e48-186">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="c3e48-186">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3e48-187">在卸載後，請確定您沒有刪除登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="c3e48-187">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="c3e48-188">若機碼為空、不正確或不存在，則該功能將會以預設值 (預設值 = 0 （適用于商業性雲端) ）。</span><span class="sxs-lookup"><span data-stu-id="c3e48-188">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="c3e48-189">若機碼為空或不正確，則列印錯誤也會新增至記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c3e48-189">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="c3e48-190">步驟6：安裝 AIP 內部部署掃描器及管理內容掃描工作</span><span class="sxs-lookup"><span data-stu-id="c3e48-190">Step 6: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="c3e48-191">安裝 AIP 內部部署掃描器，以掃描您的網路和內容共用的機密資料，並套用組織原則中所設定的分類及保護標籤。</span><span class="sxs-lookup"><span data-stu-id="c3e48-191">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="c3e48-192">設定及管理內容掃描工作時，請使用下列程式，而不是商務用產品所用的 [Azure 入口網站介面](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-192">When configuring and managing your content scan jobs, use the following procedure instead of the [Azure portal interface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) that's used by the commercial offerings.</span></span>

<span data-ttu-id="c3e48-193">如需詳細資訊，請參閱 [何謂 Azure 資訊保護統一的標記掃描器？](/azure/information-protection/deploy-aip-scanner) 和 [使用 PowerShell 管理內容掃描工作](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="c3e48-193">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>

<span data-ttu-id="c3e48-194">**若要安裝及設定掃描器**：</span><span class="sxs-lookup"><span data-stu-id="c3e48-194">**To install and configure your scanner**:</span></span>

1. <span data-ttu-id="c3e48-195">登入將執行掃描器的 Windows 伺服器電腦。</span><span class="sxs-lookup"><span data-stu-id="c3e48-195">Sign in to the Windows Server computer that will run the scanner.</span></span> <span data-ttu-id="c3e48-196">使用具有本機系統管理員許可權的帳戶，且具有寫入 SQL Server master 資料庫的許可權。</span><span class="sxs-lookup"><span data-stu-id="c3e48-196">Use an account that has local administrator rights and that has permissions to write to the SQL Server master database.</span></span>

1. <span data-ttu-id="c3e48-197">開始使用 PowerShell 關閉]。</span><span class="sxs-lookup"><span data-stu-id="c3e48-197">Start with PowerShell closed.</span></span> <span data-ttu-id="c3e48-198">如果您先前已安裝 AIP 用戶端和掃描器，請確定 **AIPScanner** 服務已停止。</span><span class="sxs-lookup"><span data-stu-id="c3e48-198">If you've previously installed the AIP client and scanner, make sure that the **AIPScanner** service is stopped.</span></span>

1. <span data-ttu-id="c3e48-199">使用 [以 **系統管理員身分執行**] 選項開啟 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="c3e48-199">Open a Windows PowerShell session with the **Run as an administrator** option.</span></span>

1. <span data-ttu-id="c3e48-200">執行[AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner)指令程式，指定您的 SQL Server 實例，以針對 Azure 資訊保護掃描程式建立資料庫，並指定您的掃描器叢集有意義的名稱。</span><span class="sxs-lookup"><span data-stu-id="c3e48-200">Run the [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet, specifying your SQL Server instance on which to create a database for the Azure Information Protection scanner, and a meaningful name for your scanner cluster.</span></span>

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > <span data-ttu-id="c3e48-201">您可以在 [AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) 命令中使用相同的叢集名稱，以將多個掃描器節點與同一個叢集產生關聯。</span><span class="sxs-lookup"><span data-stu-id="c3e48-201">You can use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="c3e48-202">對多個掃描器節點使用相同的叢集，可讓多個掃描器一起運作，以執行掃描。</span><span class="sxs-lookup"><span data-stu-id="c3e48-202">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
    > 

1. <span data-ttu-id="c3e48-203">使用系統 **管理工具** 服務，確認現在已安裝服務  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3e48-203">Verify that the service is now installed by using **Administrative Tools** > **Services**.</span></span>

    <span data-ttu-id="c3e48-204">已安裝的服務命名為 **Azure 資訊保護掃描器** ，而且會設定為使用您建立的掃描器服務帳戶來執行。</span><span class="sxs-lookup"><span data-stu-id="c3e48-204">The installed service is named **Azure Information Protection Scanner** and is configured to run by using the scanner service account that you created.</span></span>

1. <span data-ttu-id="c3e48-205">取得 Azure token 以搭配掃描器使用。</span><span class="sxs-lookup"><span data-stu-id="c3e48-205">Get an Azure token to use with your scanner.</span></span> <span data-ttu-id="c3e48-206">Azure AD token 可讓掃描器驗證 Azure 資訊保護服務，讓掃描器以非互動方式執行。</span><span class="sxs-lookup"><span data-stu-id="c3e48-206">An Azure AD token allows the scanner to authenticate to the Azure Information Protection service, enabling the scanner to run non-interactively.</span></span> 

    1. <span data-ttu-id="c3e48-207">開啟 Azure 入口網站，並建立 Azure AD 應用程式，以指定驗證的存取權杖。</span><span class="sxs-lookup"><span data-stu-id="c3e48-207">Open the Azure portal and create an Azure AD application to specify an access token for authentication.</span></span> <span data-ttu-id="c3e48-208">如需詳細資訊，請參閱 how [to 以非互動式方式標記檔案以供 Azure 資訊保護](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="c3e48-208">For more information, see [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>
    
        > [!TIP]
        > <span data-ttu-id="c3e48-209">當您建立及設定 Azure AD 應用程式的 [AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) 命令時，[ **要求 API 許可權** ] 窗格會顯示 [ **我的組織使用** ] 索引標籤，而非 [ **Microsoft APIs** ] 索引標籤的 APIs。選取 [ **我的組織所用的 APIs** ]，然後選取 [ **Azure Rights Management 服務**]。</span><span class="sxs-lookup"><span data-stu-id="c3e48-209">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span> 
        >

    1. <span data-ttu-id="c3e48-210">從 Windows Server 電腦上，如果您的掃描器服務帳戶已授與 **本機登** 入的許可權，請使用此帳戶登入，然後啟動 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="c3e48-210">From the Windows Server computer, if your scanner service account has been granted the **Log on locally** right for the installation, sign in with this account and start a PowerShell session.</span></span> 
    
        <span data-ttu-id="c3e48-211">如果您的掃描器服務帳戶無法授與安裝的 **本機登** 入許可權，請使用具有 [AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)的 *OnBehalfOf* 參數（如 [如何以非互動式方式標示 Azure 資訊保護](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)檔案中所述）。</span><span class="sxs-lookup"><span data-stu-id="c3e48-211">If your scanner service account cannot be granted the **Log on locally** right for the installation, use the *OnBehalfOf* parameter with [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), as described in [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>

    1. <span data-ttu-id="c3e48-212">執行 [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)，指定從 Azure AD 應用程式複製的值：</span><span class="sxs-lookup"><span data-stu-id="c3e48-212">Run [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specifying values copied from your Azure AD application:</span></span>

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      <span data-ttu-id="c3e48-213">例如：</span><span class="sxs-lookup"><span data-stu-id="c3e48-213">For example:</span></span>

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    <span data-ttu-id="c3e48-214">掃描器現在具有用於驗證 Azure AD 的權杖。</span><span class="sxs-lookup"><span data-stu-id="c3e48-214">The scanner now has a token to authenticate to Azure AD.</span></span> <span data-ttu-id="c3e48-215">根據您在 Azure AD 中設定的 **Web 應用程式/API** 用戶端密碼，此權杖的有效期為一年、兩年或永不。</span><span class="sxs-lookup"><span data-stu-id="c3e48-215">This token is valid for one year, two years, or never, according to your configuration of the **Web app /API** client secret in Azure AD.</span></span> <span data-ttu-id="c3e48-216">當令牌到期時，您必須重複此程式。</span><span class="sxs-lookup"><span data-stu-id="c3e48-216">When the token expires, you must repeat this procedure.</span></span>

1. <span data-ttu-id="c3e48-217">執行 [AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) 指令程式，將掃描器設定為在離線模式下運作。</span><span class="sxs-lookup"><span data-stu-id="c3e48-217">Run the [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet to set the scanner to function in offline mode.</span></span> <span data-ttu-id="c3e48-218">運行：</span><span class="sxs-lookup"><span data-stu-id="c3e48-218">Run:</span></span>

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. <span data-ttu-id="c3e48-219">執行 [AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) Cmdlet 來建立預設內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="c3e48-219">Run the [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet to create a default content scan job.</span></span>

    <span data-ttu-id="c3e48-220">**AIPScannerContentScanJob 指令程式** 中的唯一必要參數會 **強制執行**。</span><span class="sxs-lookup"><span data-stu-id="c3e48-220">The only required parameter in the **Set-AIPScannerContentScanJob** cmdlet is **Enforce**.</span></span> <span data-ttu-id="c3e48-221">不過，您此時可能會想為內容掃描工作定義其他設定。</span><span class="sxs-lookup"><span data-stu-id="c3e48-221">However, you may want to define other settings for your content scan job at this time.</span></span> <span data-ttu-id="c3e48-222">例如：</span><span class="sxs-lookup"><span data-stu-id="c3e48-222">For example:</span></span>

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    <span data-ttu-id="c3e48-223">以上語法會在您繼續設定時設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="c3e48-223">The syntax above configures the following settings while you continue the configuration:</span></span>

    - <span data-ttu-id="c3e48-224">讓掃描器執行排程，以進行 *手動*</span><span class="sxs-lookup"><span data-stu-id="c3e48-224">Keeps the scanner run scheduling to *manual*</span></span>
    - <span data-ttu-id="c3e48-225">根據敏感度標籤原則，設定要探索的資訊類型</span><span class="sxs-lookup"><span data-stu-id="c3e48-225">Sets the information types to be discovered based on the sensitivity labeling policy</span></span>
    - <span data-ttu-id="c3e48-226">*不* 強制執行敏感度標記原則</span><span class="sxs-lookup"><span data-stu-id="c3e48-226">Does *not* enforce a sensitivity labeling policy</span></span>
    - <span data-ttu-id="c3e48-227">使用針對敏感度標記原則所定義的預設標籤，根據內容自動標籤檔</span><span class="sxs-lookup"><span data-stu-id="c3e48-227">Automatically labels files based on content, using the default label defined for the sensitivity labeling policy</span></span>
    - <span data-ttu-id="c3e48-228">*不* 允許重新標記檔案</span><span class="sxs-lookup"><span data-stu-id="c3e48-228">Does *not* allow for relabeling files</span></span>
    - <span data-ttu-id="c3e48-229">在掃描及自動標籤時保留檔案詳細資料，包括 *修改日期*、 *上次修改* 時間及 *修改者* 值</span><span class="sxs-lookup"><span data-stu-id="c3e48-229">Preserves file details while scanning and auto-labeling, including *date modified*, *last modified*, and *modified by* values</span></span>
    - <span data-ttu-id="c3e48-230">在執行時，將掃描器設定為排除 .msg 和 .tmp 檔案的狀態</span><span class="sxs-lookup"><span data-stu-id="c3e48-230">Sets the scanner to exclude .msg and .tmp files when running</span></span>
    - <span data-ttu-id="c3e48-231">將預設擁有者設定為執行掃描器時所要使用的帳戶</span><span class="sxs-lookup"><span data-stu-id="c3e48-231">Sets the default owner to the account you want to use when running the scanner</span></span>

1. <span data-ttu-id="c3e48-232">使用 [AIPScannerRepository 指令程式](/powershell/module/azureinformationprotection/add-aipscannerrepository) 來定義您想要在內容掃描工作中掃描的存放庫。</span><span class="sxs-lookup"><span data-stu-id="c3e48-232">Use the [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet to define the repositories you want to scan in your content scan job.</span></span> <span data-ttu-id="c3e48-233">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="c3e48-233">For example, run:</span></span>

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    <span data-ttu-id="c3e48-234">使用下列其中一個語法，視您要新增的存放庫類型而定：</span><span class="sxs-lookup"><span data-stu-id="c3e48-234">Use one of the following syntaxes, depending on the type of repository you're adding:</span></span>

    - <span data-ttu-id="c3e48-235">若為網路共用，請使用 `\\Server\Folder` 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-235">For a network share, use `\\Server\Folder`.</span></span>
    - <span data-ttu-id="c3e48-236">若為 SharePoint 庫，請使用 `http://sharepoint.contoso.com/Shared%20Documents/Folder` 。</span><span class="sxs-lookup"><span data-stu-id="c3e48-236">For a SharePoint library, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.</span></span>
    - <span data-ttu-id="c3e48-237">若為本機路徑： `C:\Folder`</span><span class="sxs-lookup"><span data-stu-id="c3e48-237">For a local path: `C:\Folder`</span></span>
    - <span data-ttu-id="c3e48-238">若為 UNC 路徑： `\\Server\Folder`</span><span class="sxs-lookup"><span data-stu-id="c3e48-238">For a UNC path: `\\Server\Folder`</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3e48-239">不支援萬用字元，也不支援 WebDav 位置。</span><span class="sxs-lookup"><span data-stu-id="c3e48-239">Wildcards are not supported and WebDav locations are not supported.</span></span>
    >
    > <span data-ttu-id="c3e48-240">若要稍後修改存放庫，請改用 [AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c3e48-240">To modify the repository later on, use the [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet instead.</span></span> 


<span data-ttu-id="c3e48-241">視需要繼續執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="c3e48-241">Continue with the following steps as needed:</span></span>

- [<span data-ttu-id="c3e48-242">運行搜索循環並查看掃描器報告</span><span class="sxs-lookup"><span data-stu-id="c3e48-242">Run a discovery cycle and view reports for the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [<span data-ttu-id="c3e48-243">使用 PowerShell 設定掃描器套用分類及保護</span><span class="sxs-lookup"><span data-stu-id="c3e48-243">Use PowerShell to configure the scanner to apply classification and protection</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [<span data-ttu-id="c3e48-244">使用 PowerShell 以掃描器來設定 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="c3e48-244">Use PowerShell to configure a DLP policy with the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

<span data-ttu-id="c3e48-245">下表列出與安裝掃描器及管理內容掃描工作相關的 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c3e48-245">The following table lists PowerShell cmdlets that are relevant for installing the scanner and managing your content scan jobs:</span></span>

| <span data-ttu-id="c3e48-246">指令程式</span><span class="sxs-lookup"><span data-stu-id="c3e48-246">Cmdlet</span></span> | <span data-ttu-id="c3e48-247">描述</span><span class="sxs-lookup"><span data-stu-id="c3e48-247">Description</span></span> |
|--|--|
| [<span data-ttu-id="c3e48-248">載入 AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="c3e48-248">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="c3e48-249">將新的存放庫加入至內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="c3e48-249">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="c3e48-250">AIPScannerConfiguration</span><span class="sxs-lookup"><span data-stu-id="c3e48-250">Get-AIPScannerConfiguration</span></span>](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|<span data-ttu-id="c3e48-251">傳回群集的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c3e48-251">Returns details about your cluster.</span></span> |
| [<span data-ttu-id="c3e48-252">AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="c3e48-252">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="c3e48-253">取得內容掃描工作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c3e48-253">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="c3e48-254">AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="c3e48-254">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="c3e48-255">取得針對內容掃描工作定義之存放庫的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c3e48-255">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="c3e48-256">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="c3e48-256">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="c3e48-257">會刪除您的內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="c3e48-257">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="c3e48-258">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="c3e48-258">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="c3e48-259">從內容掃描工作中移除存放庫。</span><span class="sxs-lookup"><span data-stu-id="c3e48-259">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="c3e48-260">AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="c3e48-260">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="c3e48-261">定義內容掃描工作的設定。</span><span class="sxs-lookup"><span data-stu-id="c3e48-261">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="c3e48-262">AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="c3e48-262">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="c3e48-263">定義內容掃描工作中現有存放庫的設定。</span><span class="sxs-lookup"><span data-stu-id="c3e48-263">Defines settings for an existing repository in your content scan job.</span></span> |
| | |

<span data-ttu-id="c3e48-264">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="c3e48-264">For more information, see:</span></span>

- [<span data-ttu-id="c3e48-265">何謂 Azure 資訊保護的整合標籤掃描器？</span><span class="sxs-lookup"><span data-stu-id="c3e48-265">What is the Azure Information Protection unified labeling scanner?</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="c3e48-266">設定及安裝 Azure 資訊保護 (AIP) 整合的標記掃描器</span><span class="sxs-lookup"><span data-stu-id="c3e48-266">Configuring and installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- <span data-ttu-id="c3e48-267">[僅使用 PowerShell 管理內容掃描工作](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="c3e48-267">[Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
