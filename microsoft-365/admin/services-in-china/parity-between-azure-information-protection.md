---
title: 由世紀和商業版產品運作之 Office 365 的 Azure 資訊保護之間的奇偶性
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
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
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840298"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="1a254-103">由世紀和商業版產品運作之 Office 365 的 Azure 資訊保護之間的奇偶性</span><span class="sxs-lookup"><span data-stu-id="1a254-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="1a254-104">雖然我們的目標是將所有商業功能和功能提供給中國的客戶，但其 Azure 資訊保護 (AIP) 適用于由世紀所運作的 Office 365，但仍有一些遺漏的功能，我們想要反白。</span><span class="sxs-lookup"><span data-stu-id="1a254-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection (AIP) for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="1a254-105">下列清單包含在由世紀運作之 Office 365 之 Azure 資訊保護之間的現有缺口，以及從年 1 2021 月的商業產品方案：</span><span class="sxs-lookup"><span data-stu-id="1a254-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="1a254-106">只有 Microsoft 365 Apps for enterprise (組建11731.10000 或更新) 版本，才能支援資訊版權管理 (IRM) 。</span><span class="sxs-lookup"><span data-stu-id="1a254-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="1a254-107">Office 2010、Office 2013 及其他 Office 2016 版本都不受支援。</span><span class="sxs-lookup"><span data-stu-id="1a254-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="1a254-108">從 Active Directory Rights Management Services 到 Azure 資訊保護的 Active Directory Rights Management Services (AD RMS) 目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="1a254-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="1a254-109">支援將受保護的電子郵件共用至商業雲端中的使用者。</span><span class="sxs-lookup"><span data-stu-id="1a254-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="1a254-110">目前無法將檔和電子郵件附件共用給商業雲端中的使用者。</span><span class="sxs-lookup"><span data-stu-id="1a254-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="1a254-111">這包括由使用者在商業雲端中運作的 Office 365、由商業雲端中的世紀使用者運作的非 Office 365，以及具有 RMS for 個人授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="1a254-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="1a254-112">具有 SharePoint (IRM 保護的網站與文件庫) 的 IRM 目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="1a254-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="1a254-113">目前無法使用 AD RMS 的行動裝置分機。</span><span class="sxs-lookup"><span data-stu-id="1a254-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="1a254-114">Azure 中國的世紀不支援行動 [檢視器](/azure/information-protection/rms-client/mobile-app-faq) 。</span><span class="sxs-lookup"><span data-stu-id="1a254-114">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="1a254-115">為中國的客戶設定 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="1a254-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="1a254-116">啟用租使用者的版權管理</span><span class="sxs-lookup"><span data-stu-id="1a254-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="1a254-117">為使加密正確運作，RMS 必須啟用租使用者。</span><span class="sxs-lookup"><span data-stu-id="1a254-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="1a254-118">檢查 RMS 是否已啟用：</span><span class="sxs-lookup"><span data-stu-id="1a254-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="1a254-119">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1a254-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="1a254-120">若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="1a254-120">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="1a254-121">使用匯入模組 `Import-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="1a254-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="1a254-122">使用連線至服務 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="1a254-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="1a254-123">執行 `(Get-AipServiceConfiguration).FunctionalState` 並檢查狀態是否為 `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="1a254-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="1a254-124">如果功能狀態為 `Disabled` ，請執行 `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="1a254-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="1a254-125"> (Windows) 加密的 DNS 設定</span><span class="sxs-lookup"><span data-stu-id="1a254-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="1a254-126">若要讓加密正確運作，Office 用戶端應用程式必須連接至服務的中國實例，並從那裡開始進行引導。</span><span class="sxs-lookup"><span data-stu-id="1a254-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="1a254-127">若要將用戶端應用程式重新導向至正確的服務實例，租使用者管理員必須使用 Azure RMS URL 的相關資訊來設定 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1a254-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="1a254-128">若沒有 DNS SRV 記錄，用戶端應用程式會在預設會嘗試連線至公用雲端實例，否則會失敗。</span><span class="sxs-lookup"><span data-stu-id="1a254-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="1a254-129">此外，假設使用者將會以使用者身分登入，而不是以租使用者為基礎的網域 (來登入，例如 `joe@contoso.cn`) ，而不是使用者 `onmschina` 名稱 (例如 `joe@contoso.onmschina.cn`) 。</span><span class="sxs-lookup"><span data-stu-id="1a254-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="1a254-130">Username 的功能變數名稱可用於將 DNS 重新導向至正確的服務實例。</span><span class="sxs-lookup"><span data-stu-id="1a254-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="1a254-131">取得 RMS ID:</span><span class="sxs-lookup"><span data-stu-id="1a254-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="1a254-132">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1a254-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="1a254-133">若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="1a254-133">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="1a254-134">使用連線至服務 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="1a254-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="1a254-135">執行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以取得 RMS 識別碼。</span><span class="sxs-lookup"><span data-stu-id="1a254-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="1a254-136">登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1a254-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="1a254-137">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="1a254-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="1a254-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="1a254-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="1a254-139">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="1a254-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="1a254-140">Target = `[GUID].rms.aadrm.cn` (其中 GUID 是 RMS 識別碼) </span><span class="sxs-lookup"><span data-stu-id="1a254-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="1a254-141">Priority，權數，Seconds，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="1a254-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="1a254-142">將自訂網域與 [Azure 入口網站](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的承租人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="1a254-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="1a254-143">這會在 DNS 中新增專案，當您將此值新增至 DNS 設定後，可能需要幾分鐘的時間來取得驗證。</span><span class="sxs-lookup"><span data-stu-id="1a254-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="1a254-144">使用對應的全域系統管理員認證登入 Microsoft 365 系統管理中心，並新增網域 (例如， `contoso.cn` 針對使用者建立) 。</span><span class="sxs-lookup"><span data-stu-id="1a254-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="1a254-145">在驗證程式中，可能需要進行其他 DNS 變更。</span><span class="sxs-lookup"><span data-stu-id="1a254-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="1a254-146">完成驗證之後，即可建立使用者。</span><span class="sxs-lookup"><span data-stu-id="1a254-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="1a254-147">加密 (Mac、iOS、Android) 的 DNS 設定</span><span class="sxs-lookup"><span data-stu-id="1a254-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

<span data-ttu-id="1a254-148">登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1a254-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="1a254-149">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="1a254-149">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="1a254-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="1a254-150">Protocol = `_http`</span></span>
- <span data-ttu-id="1a254-151">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="1a254-151">Name = `_tcp`</span></span>
- <span data-ttu-id="1a254-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="1a254-152">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="1a254-153">埠 = `80`</span><span class="sxs-lookup"><span data-stu-id="1a254-153">Port = `80`</span></span>
- <span data-ttu-id="1a254-154">Priority，權數，Seconds，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="1a254-154">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="aip-client-configuration"></a><span data-ttu-id="1a254-155">AIP 用戶端設定</span><span class="sxs-lookup"><span data-stu-id="1a254-155">AIP client configuration</span></span>

<span data-ttu-id="1a254-156">您可以從 [Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載統一 AIP 用戶端。</span><span class="sxs-lookup"><span data-stu-id="1a254-156">The unified AIP client can be downloaded from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="1a254-157">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="1a254-157">For more information, see:</span></span>

- [<span data-ttu-id="1a254-158">Azure 資訊保護檔</span><span class="sxs-lookup"><span data-stu-id="1a254-158">Azure Information Protection documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="1a254-159">AIP 版本歷程記錄與支援原則</span><span class="sxs-lookup"><span data-stu-id="1a254-159">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="1a254-160">AIP 系統需求</span><span class="sxs-lookup"><span data-stu-id="1a254-160">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="1a254-161">AIP 快速入門：部署 AIP 用戶端</span><span class="sxs-lookup"><span data-stu-id="1a254-161">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="1a254-162">AIP 管理員指南</span><span class="sxs-lookup"><span data-stu-id="1a254-162">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="1a254-163">AIP 使用者指南</span><span class="sxs-lookup"><span data-stu-id="1a254-163">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="1a254-164">深入瞭解 Microsoft 365 敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="1a254-164">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a><span data-ttu-id="1a254-165">AIP apps configuration (僅限整合標籤用戶端) </span><span class="sxs-lookup"><span data-stu-id="1a254-165">AIP apps configuration (unified labeling client only)</span></span>

<span data-ttu-id="1a254-166">針對整合的標籤解決方案，Windows 上的 AIP 應用程式需要下列登錄機碼，將其指向適用于 Azure 中國的正確以及主權雲端：</span><span class="sxs-lookup"><span data-stu-id="1a254-166">For the unified labeling solution, AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="1a254-167">Registry 節點 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="1a254-167">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="1a254-168">名稱 = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="1a254-168">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="1a254-169">值 = `6` (預設值 = 0) </span><span class="sxs-lookup"><span data-stu-id="1a254-169">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="1a254-170">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="1a254-170">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a254-171">在卸載後，請確定您沒有刪除登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="1a254-171">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="1a254-172">若機碼為空、不正確或不存在，則該功能將會以預設值 (預設值 = 0 （適用于商業性雲端) ）。</span><span class="sxs-lookup"><span data-stu-id="1a254-172">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="1a254-173">若機碼為空或不正確，則列印錯誤也會新增至記錄檔。</span><span class="sxs-lookup"><span data-stu-id="1a254-173">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="manage-azure-information-protection-content-scan-jobs"></a><span data-ttu-id="1a254-174">管理 Azure 資訊保護內容掃描工作</span><span class="sxs-lookup"><span data-stu-id="1a254-174">Manage Azure Information Protection content scan jobs</span></span>

<span data-ttu-id="1a254-175">若要使用 Azure 中國掃描器伺服器管理 Azure 資訊保護內容掃描工作，請使用下列 Cmdlet，而不是 Azure 入口網站：</span><span class="sxs-lookup"><span data-stu-id="1a254-175">To manage your Azure Information Protection content scan jobs with an Azure China scanner server, use the following cmdlets instead of the Azure portal:</span></span><br><br>

| <span data-ttu-id="1a254-176">指令程式</span><span class="sxs-lookup"><span data-stu-id="1a254-176">Cmdlet</span></span> | <span data-ttu-id="1a254-177">描述</span><span class="sxs-lookup"><span data-stu-id="1a254-177">Description</span></span> |
|--|--|
| [<span data-ttu-id="1a254-178">載入 AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="1a254-178">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="1a254-179">將新的存放庫加入至內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="1a254-179">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="1a254-180">AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="1a254-180">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="1a254-181">取得內容掃描工作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1a254-181">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="1a254-182">AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="1a254-182">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="1a254-183">取得針對內容掃描工作定義之存放庫的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1a254-183">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="1a254-184">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="1a254-184">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="1a254-185">會刪除您的內容掃描工作。</span><span class="sxs-lookup"><span data-stu-id="1a254-185">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="1a254-186">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="1a254-186">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="1a254-187">從內容掃描工作中移除存放庫。</span><span class="sxs-lookup"><span data-stu-id="1a254-187">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="1a254-188">AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="1a254-188">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="1a254-189">定義內容掃描工作的設定。</span><span class="sxs-lookup"><span data-stu-id="1a254-189">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="1a254-190">AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="1a254-190">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="1a254-191">定義內容掃描工作中現有存放庫的設定。</span><span class="sxs-lookup"><span data-stu-id="1a254-191">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="1a254-192">如需詳細資訊，請參閱 [使用 PowerShell 管理內容掃描工作](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="1a254-192">For more information, see [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>