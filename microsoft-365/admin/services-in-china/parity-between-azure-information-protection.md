---
title: 21Vianet 運作的 Office 365
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
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
description: 深入瞭解 Office 365 所運作的 Azure 資訊保護，以及如何在中國為客戶設定它。
monikerRange: o365-21vianet
ms.openlocfilehash: 1f5d73f5c421a545ea0085f018a2c2a703b0b374
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399035"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="67dca-103">由世紀和商業版產品運作之 Office 365 的 Azure 資訊保護之間的奇偶性</span><span class="sxs-lookup"><span data-stu-id="67dca-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="67dca-104">雖然我們的目標是將所有商業功能和功能提供給中國客戶的 Azure 資訊保護，以供由世紀所運作的 Office 365 使用，但我們仍需要反白顯示某些功能。</span><span class="sxs-lookup"><span data-stu-id="67dca-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="67dca-105">這些是由世紀運作的 Office 365 Azure 資訊保護之間的現有缺口，從7月2019起。</span><span class="sxs-lookup"><span data-stu-id="67dca-105">These are the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="67dca-106">僅適用于企業版（組建11731.10000 或更新版本）的 Microsoft 365 應用程式支援資訊版權管理（IRM）。</span><span class="sxs-lookup"><span data-stu-id="67dca-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="67dca-107">Office 2010、Office 2013 及其他 Office 2016 版本都不受支援。</span><span class="sxs-lookup"><span data-stu-id="67dca-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="67dca-108">從 Active Directory Rights Management Services （AD RMS）到 Azure 資訊保護的遷移目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="67dca-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="67dca-109">支援將受保護的電子郵件共用至商業雲端中的使用者。</span><span class="sxs-lookup"><span data-stu-id="67dca-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="67dca-110">目前無法將檔和電子郵件附件共用給商業雲端中的使用者。</span><span class="sxs-lookup"><span data-stu-id="67dca-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="67dca-111">這包括由使用者在商業雲端中運作的 Office 365、由商業雲端中的世紀使用者運作的非 Office 365，以及具有 RMS for 個人授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="67dca-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="67dca-112">具有 SharePoint （IRM 保護的網站和程式庫）的 IRM 目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="67dca-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="67dca-113">目前無法使用 Rights Management 連接器。</span><span class="sxs-lookup"><span data-stu-id="67dca-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="67dca-114">目前無法使用 AD RMS 的行動裝置分機。</span><span class="sxs-lookup"><span data-stu-id="67dca-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="67dca-115">為中國的客戶設定 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="67dca-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="67dca-116">啟用租使用者的版權管理</span><span class="sxs-lookup"><span data-stu-id="67dca-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="67dca-117">為使加密正確運作，RMS 必須啟用租使用者。</span><span class="sxs-lookup"><span data-stu-id="67dca-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="67dca-118">檢查 RMS 是否已啟用：</span><span class="sxs-lookup"><span data-stu-id="67dca-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="67dca-119">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="67dca-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="67dca-120">若未安裝 AIPService 模組，請執行  `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="67dca-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="67dca-121">使用匯入模組 `Import-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="67dca-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="67dca-122">使用連線至服務  `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="67dca-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="67dca-123">執行  `(Get-AipServiceConfiguration).FunctionalState`   並檢查狀態是否為  `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="67dca-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="67dca-124">如果功能狀態為  `Disabled` ，請執行  `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="67dca-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="67dca-125">加密的 DNS 設定（Windows）</span><span class="sxs-lookup"><span data-stu-id="67dca-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="67dca-126">若要讓加密正確運作，Office 用戶端應用程式必須連接至服務的中國實例，並從那裡開始進行引導。</span><span class="sxs-lookup"><span data-stu-id="67dca-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="67dca-127">若要將用戶端應用程式重新導向至正確的服務實例，租使用者管理員必須使用 Azure RMS URL 的相關資訊來設定 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="67dca-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="67dca-128">若沒有 DNS SRV 記錄，用戶端應用程式會在預設會嘗試連線至公用雲端實例，否則會失敗。</span><span class="sxs-lookup"><span data-stu-id="67dca-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="67dca-129">此外，假設使用者將會以使用者身分登入，而不是以租使用者擁有的網域（例如）來登入 `joe@contoso.cn` ，而不是使用者的使用者 `onmschina` 名稱（例如 `joe@contoso.onmschina.cn` ）。</span><span class="sxs-lookup"><span data-stu-id="67dca-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="67dca-130">Username 的功能變數名稱可用於將 DNS 重新導向至正確的服務實例。</span><span class="sxs-lookup"><span data-stu-id="67dca-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="67dca-131">取得 RMS ID:</span><span class="sxs-lookup"><span data-stu-id="67dca-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="67dca-132">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="67dca-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="67dca-133">若未安裝 AIPService 模組，請執行  `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="67dca-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="67dca-134">使用連線至服務  `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="67dca-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="67dca-135">執行  `(Get-AipServiceConfiguration).RightsManagementServiceId`   以取得 RMS 識別碼。</span><span class="sxs-lookup"><span data-stu-id="67dca-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="67dca-136">登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="67dca-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="67dca-137">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="67dca-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="67dca-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="67dca-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="67dca-139">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="67dca-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="67dca-140">Target =  `[GUID].rms.aadrm.cn`   （GUID 是 RMS 識別碼）</span><span class="sxs-lookup"><span data-stu-id="67dca-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="67dca-141">Priority，權數，Seconds，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="67dca-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="67dca-142">將自訂網域與 [Azure 入口網站](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的承租人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="67dca-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="67dca-143">這會在 DNS 中新增專案，當您將此值新增至 DNS 設定後，可能需要幾分鐘的時間來取得驗證。</span><span class="sxs-lookup"><span data-stu-id="67dca-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="67dca-144">使用對應的全域系統管理員認證登入 Microsoft 365 系統管理中心，並新增網域（例如 `contoso.cn` ）以供使用者建立。</span><span class="sxs-lookup"><span data-stu-id="67dca-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="67dca-145">在驗證程式中，可能需要進行其他 DNS 變更。</span><span class="sxs-lookup"><span data-stu-id="67dca-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="67dca-146">完成驗證之後，即可建立使用者。</span><span class="sxs-lookup"><span data-stu-id="67dca-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="67dca-147">加密的 DNS 設定（Mac、iOS、Android）</span><span class="sxs-lookup"><span data-stu-id="67dca-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="67dca-148">登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="67dca-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="67dca-149">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="67dca-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="67dca-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="67dca-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="67dca-151">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="67dca-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="67dca-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="67dca-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="67dca-153">埠 = `80`</span><span class="sxs-lookup"><span data-stu-id="67dca-153">Port = `80`</span></span>
  - <span data-ttu-id="67dca-154">Priority，權數，Seconds，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="67dca-154">Priority, Weight, Seconds, TTL = default values</span></span>
