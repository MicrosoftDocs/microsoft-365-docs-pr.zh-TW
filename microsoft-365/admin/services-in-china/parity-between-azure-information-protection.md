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
description: 深入瞭解 Office 365 運作的 Azure 資訊保護 (AIP) ，以及如何為中國的客戶設定該功能。
monikerRange: o365-21vianet
ms.openlocfilehash: cee50384587ffc3e1e43eb9c6bb07d2e0ced7e13
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988041"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="383da-103">由世紀運作之 Office 365 的 Azure 資訊保護支援</span><span class="sxs-lookup"><span data-stu-id="383da-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="383da-104">本文說明 Azure 資訊保護 (AIP) 支援的 Office 365 （適用于中國）及商業方案，以及在中國為客戶設定 AIP 的特定指示， &mdash; 包括如何安裝 AIP 內部部署掃描器及管理內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="383da-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="383da-105">由世紀和商務服務運作的 Office 365 AIP 之間的差異</span><span class="sxs-lookup"><span data-stu-id="383da-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="383da-106">雖然我們的目標是將所有商業的功能和功能提供給中國的客戶 AIP，以供由世紀所運作的 Office 365 使用，但仍有一些遺漏的功能想要反白。</span><span class="sxs-lookup"><span data-stu-id="383da-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="383da-107">下列清單包含 AIP （由世紀運作之 Office 365）與我們從年 1 2021 月的商務版產品所組成的現有缺口：</span><span class="sxs-lookup"><span data-stu-id="383da-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="383da-108">只有 Microsoft 365 Apps for enterprise (組建11731.10000 或更新) 版本，才能支援資訊版權管理 (IRM) 。</span><span class="sxs-lookup"><span data-stu-id="383da-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="383da-109">Office 2010、Office 2013 及其他 Office 2016 版本都不受支援。</span><span class="sxs-lookup"><span data-stu-id="383da-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="383da-110">從 Active Directory Rights Management Services (AD RMS) 至 AIP 的遷移目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="383da-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="383da-111">支援與商業雲端中的使用者共用受保護的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="383da-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="383da-112">目前無法使用商業雲端中的使用者共用檔和電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="383da-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="383da-113">這包括由使用者在商業雲端中運作的 Office 365、由商業雲端中的世紀使用者運作的非 Office 365，以及具有 RMS for 個人授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="383da-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="383da-114">具有 SharePoint (IRM 保護的網站與文件庫) 的 IRM 目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="383da-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="383da-115">目前無法使用 AD RMS 的行動裝置分機。</span><span class="sxs-lookup"><span data-stu-id="383da-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="383da-116">Azure 中國的世紀不支援行動 [檢視器](/azure/information-protection/rms-client/mobile-app-faq) 。</span><span class="sxs-lookup"><span data-stu-id="383da-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="383da-117">為中國的客戶設定 AIP</span><span class="sxs-lookup"><span data-stu-id="383da-117">Configure AIP for customers in China</span></span>

<span data-ttu-id="383da-118">若要為中國的客戶設定 AIP：</span><span class="sxs-lookup"><span data-stu-id="383da-118">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="383da-119">[啟用租使用者的 Rights Management](#step-1-enable-rights-management-for-the-tenant)。</span><span class="sxs-lookup"><span data-stu-id="383da-119">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="383da-120">[設定 DNS 加密](#step-2-configure-dns-encryption)。</span><span class="sxs-lookup"><span data-stu-id="383da-120">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="383da-121">[安裝及設定 AIP 的整合標籤用戶端](#step-3-install-and-configure-the-aip-unified-labeling-client)。</span><span class="sxs-lookup"><span data-stu-id="383da-121">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="383da-122">[設定 Windows 上的 AIP 應用程式](#step-4-configure-aip-apps-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="383da-122">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="383da-123">[安裝 AIP 內部部署掃描程式並管理內容掃描工作](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。</span><span class="sxs-lookup"><span data-stu-id="383da-123">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="383da-124">步驟1：啟用租使用者的版權管理</span><span class="sxs-lookup"><span data-stu-id="383da-124">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="383da-125">為使加密正確運作，必須對租使用者啟用 RMS。</span><span class="sxs-lookup"><span data-stu-id="383da-125">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="383da-126">檢查 RMS 是否已啟用：</span><span class="sxs-lookup"><span data-stu-id="383da-126">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="383da-127">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="383da-127">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="383da-128">若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="383da-128">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="383da-129">使用匯入模組 `Import-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="383da-129">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="383da-130">使用連線至服務 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="383da-130">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="383da-131">執行 `(Get-AipServiceConfiguration).FunctionalState` 並檢查狀態是否為 `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="383da-131">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="383da-132">如果功能狀態為 `Disabled` ，請執行 `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="383da-132">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="383da-133">步驟2：設定 DNS 加密</span><span class="sxs-lookup"><span data-stu-id="383da-133">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="383da-134">若要讓加密正確運作，Office 用戶端應用程式必須連接至服務的中國實例，並從那裡開始進行引導。</span><span class="sxs-lookup"><span data-stu-id="383da-134">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="383da-135">若要將用戶端應用程式重新導向至正確的服務實例，租使用者管理員必須使用 Azure RMS URL 的相關資訊來設定 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="383da-135">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="383da-136">若沒有 DNS SRV 記錄，用戶端應用程式會在預設會嘗試連線至公用雲端實例，否則會失敗。</span><span class="sxs-lookup"><span data-stu-id="383da-136">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="383da-137">此外，假設使用者將會以使用者身分登入，而不是以租使用者為基礎的網域 (來登入，例如 `joe@contoso.cn`) ，而不是使用者 `onmschina` 名稱 (例如 `joe@contoso.onmschina.cn`) 。</span><span class="sxs-lookup"><span data-stu-id="383da-137">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="383da-138">Username 的功能變數名稱可用於將 DNS 重新導向至正確的服務實例。</span><span class="sxs-lookup"><span data-stu-id="383da-138">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="383da-139">設定 DNS 加密-Windows</span><span class="sxs-lookup"><span data-stu-id="383da-139">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="383da-140">取得 RMS ID:</span><span class="sxs-lookup"><span data-stu-id="383da-140">Get the RMS ID:</span></span>

    1. <span data-ttu-id="383da-141">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="383da-141">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="383da-142">若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="383da-142">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="383da-143">使用連線至服務 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="383da-143">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="383da-144">執行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以取得 RMS 識別碼。</span><span class="sxs-lookup"><span data-stu-id="383da-144">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="383da-145">登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="383da-145">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="383da-146">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="383da-146">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="383da-147">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="383da-147">Protocol = `_http`</span></span>
    - <span data-ttu-id="383da-148">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="383da-148">Name = `_tcp`</span></span>
    - <span data-ttu-id="383da-149">Target = `[GUID].rms.aadrm.cn` (其中 GUID 是 RMS 識別碼) </span><span class="sxs-lookup"><span data-stu-id="383da-149">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="383da-150">Priority，權數，Seconds，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="383da-150">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="383da-151">將自訂網域與 [Azure 入口網站](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的承租人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="383da-151">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="383da-152">這會在 DNS 中新增專案，當您將此值新增至 DNS 設定後，可能需要幾分鐘的時間來取得驗證。</span><span class="sxs-lookup"><span data-stu-id="383da-152">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="383da-153">使用對應的全域系統管理員認證登入 Microsoft 365 系統管理中心，並新增網域 (例如， `contoso.cn` 針對使用者建立) 。</span><span class="sxs-lookup"><span data-stu-id="383da-153">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="383da-154">在驗證程式中，可能需要進行其他 DNS 變更。</span><span class="sxs-lookup"><span data-stu-id="383da-154">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="383da-155">完成驗證之後，即可建立使用者。</span><span class="sxs-lookup"><span data-stu-id="383da-155">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="383da-156">設定 DNS 加密-Mac、iOS、Android</span><span class="sxs-lookup"><span data-stu-id="383da-156">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="383da-157">登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="383da-157">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="383da-158">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="383da-158">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="383da-159">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="383da-159">Protocol = `_http`</span></span>
- <span data-ttu-id="383da-160">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="383da-160">Name = `_tcp`</span></span>
- <span data-ttu-id="383da-161">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="383da-161">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="383da-162">埠 = `80`</span><span class="sxs-lookup"><span data-stu-id="383da-162">Port = `80`</span></span>
- <span data-ttu-id="383da-163">Priority，權數，Seconds，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="383da-163">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="383da-164">步驟3：安裝及設定 AIP 的整合標籤用戶端</span><span class="sxs-lookup"><span data-stu-id="383da-164">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="383da-165">從 [Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載 AIP 整合標籤用戶端。</span><span class="sxs-lookup"><span data-stu-id="383da-165">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="383da-166">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="383da-166">For more information, see:</span></span>

- [<span data-ttu-id="383da-167">AIP 檔</span><span class="sxs-lookup"><span data-stu-id="383da-167">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="383da-168">AIP 版本歷程記錄與支援原則</span><span class="sxs-lookup"><span data-stu-id="383da-168">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="383da-169">AIP 系統需求</span><span class="sxs-lookup"><span data-stu-id="383da-169">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="383da-170">AIP 快速入門：部署 AIP 用戶端</span><span class="sxs-lookup"><span data-stu-id="383da-170">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="383da-171">AIP 管理員指南</span><span class="sxs-lookup"><span data-stu-id="383da-171">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="383da-172">AIP 使用者指南</span><span class="sxs-lookup"><span data-stu-id="383da-172">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="383da-173">深入瞭解 Microsoft 365 敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="383da-173">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="383da-174">步驟4：設定 Windows 上的 AIP 應用程式</span><span class="sxs-lookup"><span data-stu-id="383da-174">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="383da-175">Windows 上的 AIP 應用程式需要下列登錄機碼，將其指向正確的 Azure 中國以及主權雲端：</span><span class="sxs-lookup"><span data-stu-id="383da-175">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="383da-176">Registry 節點 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="383da-176">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="383da-177">名稱 = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="383da-177">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="383da-178">值 = `6` (預設值 = 0) </span><span class="sxs-lookup"><span data-stu-id="383da-178">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="383da-179">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="383da-179">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="383da-180">在卸載後，請確定您沒有刪除登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="383da-180">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="383da-181">若機碼為空、不正確或不存在，則該功能將會以預設值 (預設值 = 0 （適用于商業性雲端) ）。</span><span class="sxs-lookup"><span data-stu-id="383da-181">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="383da-182">若機碼為空或不正確，則列印錯誤也會新增至記錄檔。</span><span class="sxs-lookup"><span data-stu-id="383da-182">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="383da-183">步驟5：安裝 AIP 內部部署掃描器及管理內容掃描工作</span><span class="sxs-lookup"><span data-stu-id="383da-183">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="383da-184">安裝 AIP 內部部署掃描器，以掃描您的網路和內容共用的機密資料，並套用組織原則中所設定的分類及保護標籤。</span><span class="sxs-lookup"><span data-stu-id="383da-184">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="383da-185">安裝掃描程式並管理內容掃描工作時，請使用下列 Cmdlet，而不是商務用產品所用的 Azure 入口網站介面：</span><span class="sxs-lookup"><span data-stu-id="383da-185">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="383da-186">指令程式</span><span class="sxs-lookup"><span data-stu-id="383da-186">Cmdlet</span></span> | <span data-ttu-id="383da-187">描述</span><span class="sxs-lookup"><span data-stu-id="383da-187">Description</span></span> |
|--|--|
| [<span data-ttu-id="383da-188">載入 AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="383da-188">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="383da-189">將新的存放庫加入至內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="383da-189">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="383da-190">AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="383da-190">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="383da-191">取得內容掃描工作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="383da-191">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="383da-192">AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="383da-192">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="383da-193">取得針對內容掃描工作定義之存放庫的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="383da-193">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="383da-194">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="383da-194">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="383da-195">會刪除您的內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="383da-195">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="383da-196">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="383da-196">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="383da-197">從內容掃描工作中移除存放庫。</span><span class="sxs-lookup"><span data-stu-id="383da-197">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="383da-198">AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="383da-198">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="383da-199">定義內容掃描工作的設定。</span><span class="sxs-lookup"><span data-stu-id="383da-199">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="383da-200">AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="383da-200">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="383da-201">定義內容掃描工作中現有存放庫的設定。</span><span class="sxs-lookup"><span data-stu-id="383da-201">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="383da-202">如需詳細資訊，請參閱 [何謂 Azure 資訊保護統一的標記掃描器？](/azure/information-protection/deploy-aip-scanner) 和 [使用 PowerShell 管理內容掃描工作](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="383da-202">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>