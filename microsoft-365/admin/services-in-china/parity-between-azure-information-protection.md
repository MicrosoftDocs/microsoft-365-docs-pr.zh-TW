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
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418029"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="d68ed-103">由世紀運作之 Office 365 的 Azure 資訊保護支援</span><span class="sxs-lookup"><span data-stu-id="d68ed-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="d68ed-104">本文說明 Azure 資訊保護 (AIP) 支援的 Office 365 （適用于中國）及商業方案，以及在中國為客戶設定 AIP 的特定指示， &mdash; 包括如何安裝 AIP 內部部署掃描器及管理內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="d68ed-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="d68ed-105">由世紀和商務服務運作的 Office 365 AIP 之間的差異</span><span class="sxs-lookup"><span data-stu-id="d68ed-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="d68ed-106">雖然我們的目標是將所有商業的功能和功能提供給中國的客戶 AIP，以供由世紀所運作的 Office 365 使用，但仍有一些遺漏的功能想要反白。</span><span class="sxs-lookup"><span data-stu-id="d68ed-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="d68ed-107">下列清單包含 AIP （由世紀運作之 Office 365）與我們從年 1 2021 月的商務版產品所組成的現有缺口：</span><span class="sxs-lookup"><span data-stu-id="d68ed-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="d68ed-108">只有 Microsoft 365 Apps for enterprise (組建11731.10000 或更新) 版本，才能支援資訊版權管理 (IRM) 。</span><span class="sxs-lookup"><span data-stu-id="d68ed-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="d68ed-109">Office 2010、Office 2013 及其他 Office 2016 版本都不受支援。</span><span class="sxs-lookup"><span data-stu-id="d68ed-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="d68ed-110">從 Active Directory Rights Management Services (AD RMS) 至 AIP 的遷移目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="d68ed-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="d68ed-111">支援與商業雲端中的使用者共用受保護的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d68ed-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="d68ed-112">目前無法使用商業雲端中的使用者共用檔和電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="d68ed-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="d68ed-113">這包括由使用者在商業雲端中運作的 Office 365、由商業雲端中的世紀使用者運作的非 Office 365，以及具有 RMS for 個人授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="d68ed-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="d68ed-114">具有 SharePoint (IRM 保護的網站與文件庫) 的 IRM 目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="d68ed-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="d68ed-115">目前無法使用 AD RMS 的行動裝置分機。</span><span class="sxs-lookup"><span data-stu-id="d68ed-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="d68ed-116">Azure 中國的世紀不支援行動 [檢視器](/azure/information-protection/rms-client/mobile-app-faq) 。</span><span class="sxs-lookup"><span data-stu-id="d68ed-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="d68ed-117">中國的客戶無法使用 Azure 入口網站的 AIP 區域。</span><span class="sxs-lookup"><span data-stu-id="d68ed-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="d68ed-118">使用 [PowerShell 命令](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) ，而不是在入口網站中執行動作，例如安裝內部部署掃描器及管理內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="d68ed-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="d68ed-119">為中國的客戶設定 AIP</span><span class="sxs-lookup"><span data-stu-id="d68ed-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="d68ed-120">若要為中國的客戶設定 AIP：</span><span class="sxs-lookup"><span data-stu-id="d68ed-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="d68ed-121">[啟用租使用者的 Rights Management](#step-1-enable-rights-management-for-the-tenant)。</span><span class="sxs-lookup"><span data-stu-id="d68ed-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="d68ed-122">[設定 DNS 加密](#step-2-configure-dns-encryption)。</span><span class="sxs-lookup"><span data-stu-id="d68ed-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="d68ed-123">[安裝及設定 AIP 的整合標籤用戶端](#step-3-install-and-configure-the-aip-unified-labeling-client)。</span><span class="sxs-lookup"><span data-stu-id="d68ed-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="d68ed-124">[設定 Windows 上的 AIP 應用程式](#step-4-configure-aip-apps-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="d68ed-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="d68ed-125">[安裝 AIP 內部部署掃描程式並管理內容掃描工作](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。</span><span class="sxs-lookup"><span data-stu-id="d68ed-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="d68ed-126">步驟1：啟用租使用者的版權管理</span><span class="sxs-lookup"><span data-stu-id="d68ed-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="d68ed-127">為使加密正確運作，必須對租使用者啟用 RMS。</span><span class="sxs-lookup"><span data-stu-id="d68ed-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="d68ed-128">檢查 RMS 是否已啟用：</span><span class="sxs-lookup"><span data-stu-id="d68ed-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="d68ed-129">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d68ed-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="d68ed-130">若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="d68ed-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="d68ed-131">使用匯入模組 `Import-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="d68ed-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="d68ed-132">使用連線至服務 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="d68ed-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="d68ed-133">執行 `(Get-AipServiceConfiguration).FunctionalState` 並檢查狀態是否為 `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="d68ed-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="d68ed-134">如果功能狀態為 `Disabled` ，請執行 `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="d68ed-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="d68ed-135">步驟2：設定 DNS 加密</span><span class="sxs-lookup"><span data-stu-id="d68ed-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="d68ed-136">若要讓加密正確運作，Office 用戶端應用程式必須連接至服務的中國實例，並從那裡開始進行引導。</span><span class="sxs-lookup"><span data-stu-id="d68ed-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="d68ed-137">若要將用戶端應用程式重新導向至正確的服務實例，租使用者管理員必須使用 Azure RMS URL 的相關資訊來設定 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="d68ed-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="d68ed-138">若沒有 DNS SRV 記錄，用戶端應用程式會在預設會嘗試連線至公用雲端實例，否則會失敗。</span><span class="sxs-lookup"><span data-stu-id="d68ed-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="d68ed-139">此外，假設使用者將會以使用者身分登入，而不是以租使用者為基礎的網域 (來登入，例如 `joe@contoso.cn`) ，而不是使用者 `onmschina` 名稱 (例如 `joe@contoso.onmschina.cn`) 。</span><span class="sxs-lookup"><span data-stu-id="d68ed-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="d68ed-140">Username 的功能變數名稱可用於將 DNS 重新導向至正確的服務實例。</span><span class="sxs-lookup"><span data-stu-id="d68ed-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="d68ed-141">設定 DNS 加密-Windows</span><span class="sxs-lookup"><span data-stu-id="d68ed-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="d68ed-142">取得 RMS ID:</span><span class="sxs-lookup"><span data-stu-id="d68ed-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="d68ed-143">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d68ed-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="d68ed-144">若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="d68ed-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="d68ed-145">使用連線至服務 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="d68ed-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="d68ed-146">執行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以取得 RMS 識別碼。</span><span class="sxs-lookup"><span data-stu-id="d68ed-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="d68ed-147">登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="d68ed-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="d68ed-148">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="d68ed-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="d68ed-149">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="d68ed-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="d68ed-150">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="d68ed-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="d68ed-151">Target = `[GUID].rms.aadrm.cn` (其中 GUID 是 RMS 識別碼) </span><span class="sxs-lookup"><span data-stu-id="d68ed-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="d68ed-152">Priority，權數，Seconds，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="d68ed-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="d68ed-153">將自訂網域與 [Azure 入口網站](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的承租人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d68ed-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="d68ed-154">這會在 DNS 中新增專案，當您將此值新增至 DNS 設定後，可能需要幾分鐘的時間來取得驗證。</span><span class="sxs-lookup"><span data-stu-id="d68ed-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="d68ed-155">使用對應的全域系統管理員認證登入 Microsoft 365 系統管理中心，並新增網域 (例如， `contoso.cn` 針對使用者建立) 。</span><span class="sxs-lookup"><span data-stu-id="d68ed-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="d68ed-156">在驗證程式中，可能需要進行其他 DNS 變更。</span><span class="sxs-lookup"><span data-stu-id="d68ed-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="d68ed-157">完成驗證之後，即可建立使用者。</span><span class="sxs-lookup"><span data-stu-id="d68ed-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="d68ed-158">設定 DNS 加密-Mac、iOS、Android</span><span class="sxs-lookup"><span data-stu-id="d68ed-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="d68ed-159">登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="d68ed-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="d68ed-160">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="d68ed-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="d68ed-161">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="d68ed-161">Protocol = `_http`</span></span>
- <span data-ttu-id="d68ed-162">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="d68ed-162">Name = `_tcp`</span></span>
- <span data-ttu-id="d68ed-163">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="d68ed-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="d68ed-164">埠 = `80`</span><span class="sxs-lookup"><span data-stu-id="d68ed-164">Port = `80`</span></span>
- <span data-ttu-id="d68ed-165">Priority，權數，Seconds，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="d68ed-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="d68ed-166">步驟3：安裝及設定 AIP 的整合標籤用戶端</span><span class="sxs-lookup"><span data-stu-id="d68ed-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="d68ed-167">從 [Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載 AIP 整合標籤用戶端。</span><span class="sxs-lookup"><span data-stu-id="d68ed-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="d68ed-168">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="d68ed-168">For more information, see:</span></span>

- [<span data-ttu-id="d68ed-169">AIP 檔</span><span class="sxs-lookup"><span data-stu-id="d68ed-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="d68ed-170">AIP 版本歷程記錄與支援原則</span><span class="sxs-lookup"><span data-stu-id="d68ed-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="d68ed-171">AIP 系統需求</span><span class="sxs-lookup"><span data-stu-id="d68ed-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="d68ed-172">AIP 快速入門：部署 AIP 用戶端</span><span class="sxs-lookup"><span data-stu-id="d68ed-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="d68ed-173">AIP 管理員指南</span><span class="sxs-lookup"><span data-stu-id="d68ed-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="d68ed-174">AIP 使用者指南</span><span class="sxs-lookup"><span data-stu-id="d68ed-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="d68ed-175">深入瞭解 Microsoft 365 敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d68ed-175">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="d68ed-176">步驟4：設定 Windows 上的 AIP 應用程式</span><span class="sxs-lookup"><span data-stu-id="d68ed-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="d68ed-177">Windows 上的 AIP 應用程式需要下列登錄機碼，將其指向正確的 Azure 中國以及主權雲端：</span><span class="sxs-lookup"><span data-stu-id="d68ed-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="d68ed-178">Registry 節點 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="d68ed-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="d68ed-179">名稱 = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="d68ed-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="d68ed-180">值 = `6` (預設值 = 0) </span><span class="sxs-lookup"><span data-stu-id="d68ed-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="d68ed-181">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="d68ed-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d68ed-182">在卸載後，請確定您沒有刪除登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="d68ed-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="d68ed-183">若機碼為空、不正確或不存在，則該功能將會以預設值 (預設值 = 0 （適用于商業性雲端) ）。</span><span class="sxs-lookup"><span data-stu-id="d68ed-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="d68ed-184">若機碼為空或不正確，則列印錯誤也會新增至記錄檔。</span><span class="sxs-lookup"><span data-stu-id="d68ed-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="d68ed-185">步驟5：安裝 AIP 內部部署掃描器及管理內容掃描工作</span><span class="sxs-lookup"><span data-stu-id="d68ed-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="d68ed-186">安裝 AIP 內部部署掃描器，以掃描您的網路和內容共用的機密資料，並套用組織原則中所設定的分類及保護標籤。</span><span class="sxs-lookup"><span data-stu-id="d68ed-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

- <span data-ttu-id="d68ed-187">當您建立及設定 Azure AD 應用程式的 [AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) 命令時，[ **要求 API 許可權** ] 窗格會顯示 [ **我的組織使用** ] 索引標籤，而非 [ **Microsoft APIs** ] 索引標籤的 APIs。選取 [ **我的組織所用的 APIs** ]，然後選取 [ **Azure Rights Management 服務**]。</span><span class="sxs-lookup"><span data-stu-id="d68ed-187">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span>

- <span data-ttu-id="d68ed-188">安裝掃描程式並管理內容掃描工作時，請使用下列 Cmdlet，而不是商務用產品所用的 Azure 入口網站介面：</span><span class="sxs-lookup"><span data-stu-id="d68ed-188">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

    | <span data-ttu-id="d68ed-189">指令程式</span><span class="sxs-lookup"><span data-stu-id="d68ed-189">Cmdlet</span></span> | <span data-ttu-id="d68ed-190">描述</span><span class="sxs-lookup"><span data-stu-id="d68ed-190">Description</span></span> |
    |--|--|
    | [<span data-ttu-id="d68ed-191">載入 AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="d68ed-191">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="d68ed-192">將新的存放庫加入至內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="d68ed-192">Adds a new repository to your content scan job.</span></span> |
    | [<span data-ttu-id="d68ed-193">AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="d68ed-193">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="d68ed-194">取得內容掃描工作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d68ed-194">Gets details about your content scan job.</span></span> |
    | [<span data-ttu-id="d68ed-195">AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="d68ed-195">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="d68ed-196">取得針對內容掃描工作定義之存放庫的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d68ed-196">Gets details about repositories defined for your content scan job.</span></span> |
    | [<span data-ttu-id="d68ed-197">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="d68ed-197">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="d68ed-198">會刪除您的內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="d68ed-198">Deletes your content scan job.</span></span> |
    | [<span data-ttu-id="d68ed-199">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="d68ed-199">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="d68ed-200">從內容掃描工作中移除存放庫。</span><span class="sxs-lookup"><span data-stu-id="d68ed-200">Removes a repository from your content scan job.</span></span> |
    | [<span data-ttu-id="d68ed-201">AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="d68ed-201">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="d68ed-202">定義內容掃描工作的設定。</span><span class="sxs-lookup"><span data-stu-id="d68ed-202">Defines settings for your content scan job.</span></span> |
    | [<span data-ttu-id="d68ed-203">AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="d68ed-203">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="d68ed-204">定義內容掃描工作中現有存放庫的設定。</span><span class="sxs-lookup"><span data-stu-id="d68ed-204">Defines settings for an existing repository in your content scan job.</span></span> |
    | | |

> [!TIP]
> <span data-ttu-id="d68ed-205">[安裝掃描器](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)時，請在[AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner)命令中使用相同的叢集名稱，以將多個掃描器節點與相同的叢集產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d68ed-205">When [installing the scanner](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner), use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="d68ed-206">對多個掃描器節點使用相同的叢集，可讓多個掃描器一起運作，以執行掃描。</span><span class="sxs-lookup"><span data-stu-id="d68ed-206">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
> 
> <span data-ttu-id="d68ed-207">使用 [AIPScannerConfiguration 指令程式](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) 可傳回有關您的叢集的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d68ed-207">Use the [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) cmdlet to return details about your cluster.</span></span>
> 
<span data-ttu-id="d68ed-208">如需詳細資訊，請參閱 [何謂 Azure 資訊保護統一的標記掃描器？](/azure/information-protection/deploy-aip-scanner) 和 [使用 PowerShell 管理內容掃描工作](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="d68ed-208">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>