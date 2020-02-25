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
search.appverid:
- MET150
- GEU150
- GEA150
description: 深入了解 Azure 資訊保護 21Vianet 以及如何將它設定為客戶在中國由 21vianet 運作的 Office 365。
monikerRange: o365-21vianet
ms.openlocfilehash: a4eb8c3370a123b939fdccc53eec3905f79ee806
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240279"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="2067d-103">由 21Vianet 和商業供應項目運作的 Office 365 的 Azure 資訊保護之間的同位檢查</span><span class="sxs-lookup"><span data-stu-id="2067d-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="2067d-104">雖然我們的目標是由 21Vianet 提供的功能運作的 Office 365 的客戶在中國使用我們的 Azure 資訊保護傳遞所有商業功能和功能，還有一些遺漏的功能，我們想要反白顯示。</span><span class="sxs-lookup"><span data-stu-id="2067d-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="2067d-105">由 21Vianet 和截至年 7 月 2019年我們商業供應項目運作的 Office 365 的 Azure 資訊保護之間的現有差距，如下：</span><span class="sxs-lookup"><span data-stu-id="2067d-105">These are the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="2067d-106">僅適用於 Office 365 專業增強版 （組建 11731.10000 或更高版本） 支援資訊版權管理 (IRM)。</span><span class="sxs-lookup"><span data-stu-id="2067d-106">Information Rights Management (IRM) is supported only for Office 365 ProPlus (build 11731.10000 or higher).</span></span> <span data-ttu-id="2067d-107">不支援 office 2010、 Office 2013 和其他 Office 2016 版本。</span><span class="sxs-lookup"><span data-stu-id="2067d-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="2067d-108">從 Active Directory Rights Management Services (AD RMS) 移轉至 Azure 資訊保護目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="2067d-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="2067d-109">支援的受保護的電子郵件給商業雲端中的使用者共用。</span><span class="sxs-lookup"><span data-stu-id="2067d-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="2067d-110">共用文件和電子郵件附件商業雲端中使用者的目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="2067d-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="2067d-111">這包括由 21Vianet 使用者商業雲端，非 Office 365 21vianet 運作的商業雲端中，21Vianet 使用者和使用 RMS 個人授權的使用者中運作的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2067d-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="2067d-112">IRM 與 SharePoint （受 IRM 保護的網站和文件庫） 目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="2067d-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="2067d-113">版權管理連接器目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="2067d-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="2067d-114">AD rms 的行動裝置擴充目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="2067d-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="2067d-115">中國的客戶設定 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="2067d-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="2067d-116">針對租用戶啟用權限管理</span><span class="sxs-lookup"><span data-stu-id="2067d-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="2067d-117">若要正常運作的加密，RMS 必須啟用租用戶。</span><span class="sxs-lookup"><span data-stu-id="2067d-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="2067d-118">如果已啟用 RMS，檢查：</span><span class="sxs-lookup"><span data-stu-id="2067d-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="2067d-119">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2067d-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="2067d-120">如果未安裝 AIPService 模組，執行 `Install-Module AipService`。</span><span class="sxs-lookup"><span data-stu-id="2067d-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="2067d-121">匯入模組使用`Import-Module AipService`。</span><span class="sxs-lookup"><span data-stu-id="2067d-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="2067d-122">連線至服務使用 `Connect-AipService -environmentname azurechinacloud`。</span><span class="sxs-lookup"><span data-stu-id="2067d-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="2067d-123">執行 `(Get-AipServiceConfiguration).FunctionalState` 及檢查的狀態是否為 `Enabled`。</span><span class="sxs-lookup"><span data-stu-id="2067d-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="2067d-124">如果正常運作狀態是 `Disabled`、 執行 `Enable-AipService`。</span><span class="sxs-lookup"><span data-stu-id="2067d-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="2067d-125">DNS 組態加密 (Windows)</span><span class="sxs-lookup"><span data-stu-id="2067d-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="2067d-126">加密能夠正常運作，Office 用戶端應用程式必須連線至中國執行個體的服務和啟動安裝程式從該處。</span><span class="sxs-lookup"><span data-stu-id="2067d-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="2067d-127">若要重新導向至正確的服務執行個體的用戶端應用程式，租用戶系統管理員必須設定 DNS SRV 記錄，與 Azure RMS URL 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2067d-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="2067d-128">DNS SRV 記錄，而用戶端應用程式會嘗試連線至公用雲端執行個體，根據預設，並將會失敗。</span><span class="sxs-lookup"><span data-stu-id="2067d-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="2067d-129">此外，將假設是使用者將登入基礎關閉租用戶擁有網域使用者名稱 (例如， `joe@contoso.cn`)，而不`onmschina`使用者名稱 (例如， `joe@contoso.onmschina.cn`)。</span><span class="sxs-lookup"><span data-stu-id="2067d-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="2067d-130">使用者名稱的網域名稱用於 DNS 重新導向至正確的服務執行個體。</span><span class="sxs-lookup"><span data-stu-id="2067d-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="2067d-131">取得 RMS 識別碼：</span><span class="sxs-lookup"><span data-stu-id="2067d-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="2067d-132">以系統管理員身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2067d-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="2067d-133">如果未安裝 AIPService 模組，執行 `Install-Module AipService`。</span><span class="sxs-lookup"><span data-stu-id="2067d-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="2067d-134">連線至服務使用 `Connect-AipService -environmentname azurechinacloud`。</span><span class="sxs-lookup"><span data-stu-id="2067d-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="2067d-135">執行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 若要取得 RMS 識別碼。</span><span class="sxs-lookup"><span data-stu-id="2067d-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="2067d-136">登入您的 DNS 提供者，瀏覽至該網域的 DNS 設定，然後新增新的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="2067d-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="2067d-137">服務 = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="2067d-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="2067d-138">通訊協定 = `_http`</span><span class="sxs-lookup"><span data-stu-id="2067d-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="2067d-139">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="2067d-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="2067d-140">目標 = `[GUID].rms.aadrm.cn` （其中的 GUID 是 RMS 識別碼）</span><span class="sxs-lookup"><span data-stu-id="2067d-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="2067d-141">優先順序、 粗細秒，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="2067d-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="2067d-142">建立自訂的網域與 [Azure 入口網站](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的租用戶的關聯。</span><span class="sxs-lookup"><span data-stu-id="2067d-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="2067d-143">這會在 DNS 中，這可能需要數分鐘才能取得驗證之後您將值新增至 [DNS 設定新增項目。</span><span class="sxs-lookup"><span data-stu-id="2067d-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="2067d-144">Microsoft 365 系統管理中心使用對應的全域系統管理員認證登入，並新增網域 (例如， `contoso.cn`) 的使用者建立。</span><span class="sxs-lookup"><span data-stu-id="2067d-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="2067d-145">中的驗證程序可能需要額外的 DNS 變更。</span><span class="sxs-lookup"><span data-stu-id="2067d-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="2067d-146">一旦完成驗證時，您可以建立使用者。</span><span class="sxs-lookup"><span data-stu-id="2067d-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="2067d-147">DNS 組態加密 (Mac、 iOS、 Android)</span><span class="sxs-lookup"><span data-stu-id="2067d-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="2067d-148">登入您的 DNS 提供者，瀏覽至該網域的 DNS 設定，然後新增新的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="2067d-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="2067d-149">服務 = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="2067d-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="2067d-150">通訊協定 = `_http`</span><span class="sxs-lookup"><span data-stu-id="2067d-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="2067d-151">名稱 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="2067d-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="2067d-152">目標 = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="2067d-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="2067d-153">連接埠 = `80`</span><span class="sxs-lookup"><span data-stu-id="2067d-153">Port = `80`</span></span>
  - <span data-ttu-id="2067d-154">優先順序、 粗細秒，TTL = 預設值</span><span class="sxs-lookup"><span data-stu-id="2067d-154">Priority, Weight, Seconds, TTL = default values</span></span>
