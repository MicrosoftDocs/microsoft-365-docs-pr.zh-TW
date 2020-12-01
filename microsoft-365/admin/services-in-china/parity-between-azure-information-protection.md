---
title: 由世紀和商業版產品運作之 Office 365 的 Azure 資訊保護之間的奇偶性
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
description: 深入瞭解 Office 365 所運作的 Azure 資訊保護，以及如何在中國為客戶設定它。
monikerRange: o365-21vianet
ms.openlocfilehash: 7be40466c43a49cf51a2a2c1c273cef035bee831
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519338"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="5454b-103">由世紀和商業版產品運作之 Office 365 的 Azure 資訊保護之間的奇偶性</span><span class="sxs-lookup"><span data-stu-id="5454b-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="5454b-104">雖然我們的目標是將所有商業功能和功能提供給中國客戶的 Azure 資訊保護，以供由世紀所運作的 Office 365 使用，但我們仍需要反白顯示某些功能。</span><span class="sxs-lookup"><span data-stu-id="5454b-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="5454b-105">下列清單包含在由世紀運作的 Office 365 Azure 資訊保護之間的現有中斷（從7月2019日起）：</span><span class="sxs-lookup"><span data-stu-id="5454b-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="5454b-106">只有 Microsoft 365 Apps for enterprise (組建11731.10000 或更新) 版本，才能支援資訊版權管理 (IRM) 。</span><span class="sxs-lookup"><span data-stu-id="5454b-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="5454b-107">Office 2010、Office 2013 及其他 Office 2016 版本都不受支援。</span><span class="sxs-lookup"><span data-stu-id="5454b-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="5454b-108">從 Active Directory Rights Management Services 到 Azure 資訊保護的 Active Directory Rights Management Services (AD RMS) 目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="5454b-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="5454b-109">支援將受保護的電子郵件共用至商業雲端中的使用者。</span><span class="sxs-lookup"><span data-stu-id="5454b-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="5454b-110">目前無法將檔和電子郵件附件共用給商業雲端中的使用者。</span><span class="sxs-lookup"><span data-stu-id="5454b-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="5454b-111">這包括由使用者在商業雲端中運作的 Office 365、由商業雲端中的世紀使用者運作的非 Office 365，以及具有 RMS for 個人授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="5454b-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="5454b-112">具有 SharePoint (IRM 保護的網站與文件庫) 的 IRM 目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="5454b-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="5454b-113">目前無法使用 AD RMS 的行動裝置分機。</span><span class="sxs-lookup"><span data-stu-id="5454b-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="5454b-114">為中國的客戶設定 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="5454b-114">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="5454b-115">啟用租使用者的版權管理</span><span class="sxs-lookup"><span data-stu-id="5454b-115">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="5454b-116">為使加密正確運作，RMS 必須啟用租使用者。</span><span class="sxs-lookup"><span data-stu-id="5454b-116">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="5454b-117">檢查 RMS 是否已啟用：</span><span class="sxs-lookup"><span data-stu-id="5454b-117">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="5454b-118">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5454b-118">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="5454b-119">若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="5454b-119">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="5454b-120">使用匯入模組 `Import-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="5454b-120">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="5454b-121">使用連線至服務 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="5454b-121">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="5454b-122">執行 `(Get-AipServiceConfiguration).FunctionalState` 並檢查狀態是否為 `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="5454b-122">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="5454b-123">如果功能狀態為 `Disabled` ，請執行 `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="5454b-123">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="5454b-124"> (Windows) 加密的 DNS 設定</span><span class="sxs-lookup"><span data-stu-id="5454b-124">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="5454b-125">若要讓加密正確運作，Office 用戶端應用程式必須連接至服務的中國實例，並從那裡開始進行引導。</span><span class="sxs-lookup"><span data-stu-id="5454b-125">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="5454b-126">若要將用戶端應用程式重新導向至正確的服務實例，租使用者管理員必須使用 Azure RMS URL 的相關資訊來設定 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="5454b-126">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="5454b-127">若沒有 DNS SRV 記錄，用戶端應用程式會在預設會嘗試連線至公用雲端實例，否則會失敗。</span><span class="sxs-lookup"><span data-stu-id="5454b-127">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="5454b-128">此外，假設使用者將會以使用者身分登入，而不是以租使用者為基礎的網域 (來登入，例如 `joe@contoso.cn`) ，而不是使用者 `onmschina` 名稱 (例如 `joe@contoso.onmschina.cn`) 。</span><span class="sxs-lookup"><span data-stu-id="5454b-128">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="5454b-129">Username 的功能變數名稱可用於將 DNS 重新導向至正確的服務實例。</span><span class="sxs-lookup"><span data-stu-id="5454b-129">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="5454b-130">取得 RMS ID:</span><span class="sxs-lookup"><span data-stu-id="5454b-130">Get the RMS ID:</span></span>
  1. <span data-ttu-id="5454b-131">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5454b-131">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="5454b-132">若未安裝 AIPService 模組，請執行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="5454b-132">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="5454b-133">使用連線至服務 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="5454b-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="5454b-134">執行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以取得 RMS 識別碼。</span><span class="sxs-lookup"><span data-stu-id="5454b-134">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="5454b-135">登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="5454b-135">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="5454b-136">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="5454b-136">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="5454b-137">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="5454b-137">Protocol = `_http`</span></span>
  - <span data-ttu-id="5454b-138">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="5454b-138">Name = `_tcp`</span></span>
  - <span data-ttu-id="5454b-139">Target = `[GUID].rms.aadrm.cn` (其中 GUID 是 RMS 識別碼) </span><span class="sxs-lookup"><span data-stu-id="5454b-139">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="5454b-140">Priority，權數，Seconds，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="5454b-140">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="5454b-141">將自訂網域與 [Azure 入口網站](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的承租人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="5454b-141">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="5454b-142">這會在 DNS 中新增專案，當您將此值新增至 DNS 設定後，可能需要幾分鐘的時間來取得驗證。</span><span class="sxs-lookup"><span data-stu-id="5454b-142">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="5454b-143">使用對應的全域系統管理員認證登入 Microsoft 365 系統管理中心，並新增網域 (例如， `contoso.cn` 針對使用者建立) 。</span><span class="sxs-lookup"><span data-stu-id="5454b-143">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="5454b-144">在驗證程式中，可能需要進行其他 DNS 變更。</span><span class="sxs-lookup"><span data-stu-id="5454b-144">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="5454b-145">完成驗證之後，即可建立使用者。</span><span class="sxs-lookup"><span data-stu-id="5454b-145">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="5454b-146">加密 (Mac、iOS、Android) 的 DNS 設定</span><span class="sxs-lookup"><span data-stu-id="5454b-146">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="5454b-147">登入您的 DNS 提供者，流覽至網域的 DNS 設定，然後新增 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="5454b-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="5454b-148">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="5454b-148">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="5454b-149">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="5454b-149">Protocol = `_http`</span></span>
  - <span data-ttu-id="5454b-150">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="5454b-150">Name = `_tcp`</span></span>
  - <span data-ttu-id="5454b-151">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="5454b-151">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="5454b-152">埠 = `80`</span><span class="sxs-lookup"><span data-stu-id="5454b-152">Port = `80`</span></span>
  - <span data-ttu-id="5454b-153">Priority，權數，Seconds，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="5454b-153">Priority, Weight, Seconds, TTL = default values</span></span>
