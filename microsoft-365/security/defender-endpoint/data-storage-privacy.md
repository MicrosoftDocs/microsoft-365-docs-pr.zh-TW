---
title: Microsoft Defender for Endpoint data storage and 隱私權
description: 瞭解 Microsoft Defender for Endpoint 如何處理隱私權和其收集的資料。
keywords: Microsoft Defender for endpoint，Microsoft Defender for Endpoint，data storage and 隱私權，storage，隱私權，授權，地理位置，資料保留，資料
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dfdfcdcfb8d76f95e3b866f5f95af7efd94ed59e
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904125"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a><span data-ttu-id="db9c9-104">Microsoft Defender for Endpoint data storage and 隱私權</span><span class="sxs-lookup"><span data-stu-id="db9c9-104">Microsoft Defender for Endpoint data storage and privacy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="db9c9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="db9c9-105">**Applies to:**</span></span>
- [<span data-ttu-id="db9c9-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="db9c9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="db9c9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db9c9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="db9c9-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="db9c9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="db9c9-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="db9c9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="db9c9-110">本節涵蓋一些有關隱私權和用於 Defender 的資料處理的最常見常見問題。</span><span class="sxs-lookup"><span data-stu-id="db9c9-110">This section covers some of the most frequently asked questions regarding privacy and data handling for Defender for Endpoint.</span></span>
> [!NOTE]
> <span data-ttu-id="db9c9-111">這份檔說明與 Defender for Endpoint 相關的資料儲存區與隱私權詳細資料。</span><span class="sxs-lookup"><span data-stu-id="db9c9-111">This document explains the data storage and privacy details related to Defender for Endpoint.</span></span> <span data-ttu-id="db9c9-112">如需與 Defender for Endpoint 和其他產品及服務如 Microsoft Defender 防病毒和 Windows 10 相關的詳細資訊，請參閱 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?linkid=827576)。</span><span class="sxs-lookup"><span data-stu-id="db9c9-112">For more information related to Defender for Endpoint and other products and services like Microsoft Defender Antivirus and Windows 10, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=827576).</span></span> <span data-ttu-id="db9c9-113">如需詳細資訊，另請參閱 [Windows 10 隱私權 FAQ](https://go.microsoft.com/fwlink/?linkid=827577) 。</span><span class="sxs-lookup"><span data-stu-id="db9c9-113">See also [Windows 10 privacy FAQ](https://go.microsoft.com/fwlink/?linkid=827577) for more information.</span></span>


## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a><span data-ttu-id="db9c9-114">Microsoft Defender for Endpoint 會收集哪些資料？</span><span class="sxs-lookup"><span data-stu-id="db9c9-114">What data does Microsoft Defender for Endpoint collect?</span></span>

<span data-ttu-id="db9c9-115">Microsoft Defender for Endpoint 會收集和儲存已設定裝置中已設定之裝置的資訊，以供系統管理、追蹤和報告之用的客戶專用和隔離租使用者使用。</span><span class="sxs-lookup"><span data-stu-id="db9c9-115">Microsoft Defender for Endpoint will collect and store information from your configured devices in a customer dedicated and segregated tenant specific to the service for administration, tracking, and reporting purposes.</span></span> 

<span data-ttu-id="db9c9-116">收集的資訊包括檔案資料 (例如：檔案名、大小和雜湊) 、處理資料 (執行中的程式、雜湊) 、登錄資料、網路連線資料 (主機 IPs 及埠) ，以及裝置詳細資料 (（如裝置識別碼、名稱和作業系統版本) ）。</span><span class="sxs-lookup"><span data-stu-id="db9c9-116">Information collected includes file data (such as file names, sizes, and hashes), process data (running processes, hashes), registry data, network connection data (host IPs and ports), and device details (such as device identifiers, names, and the operating system version).</span></span>

<span data-ttu-id="db9c9-117">Microsoft 會安全地將此資料儲存在 Microsoft Azure 中，並依照 Microsoft 隱私權慣例和 [Microsoft 信任中心原則](https://go.microsoft.com/fwlink/?linkid=827578)加以維護。</span><span class="sxs-lookup"><span data-stu-id="db9c9-117">Microsoft stores this data securely in Microsoft Azure and maintains it in accordance with Microsoft privacy practices and [Microsoft Trust Center policies](https://go.microsoft.com/fwlink/?linkid=827578).</span></span>

<span data-ttu-id="db9c9-118">此資料可讓 Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="db9c9-118">This data enables Defender for Endpoint to:</span></span>
- <span data-ttu-id="db9c9-119">主動識別組織中 (IOAs) 的攻擊指示器</span><span class="sxs-lookup"><span data-stu-id="db9c9-119">Proactively identify indicators of attack (IOAs) in your organization</span></span>
- <span data-ttu-id="db9c9-120">偵測到可能的攻擊時產生警示</span><span class="sxs-lookup"><span data-stu-id="db9c9-120">Generate alerts if a possible attack was detected</span></span>
- <span data-ttu-id="db9c9-121">在裝置、檔案和 URLs 中，提供與網路威脅信號相關的安全性作業，讓您能夠調查和探索網路上是否有安全性威脅。</span><span class="sxs-lookup"><span data-stu-id="db9c9-121">Provide your security operations with a view into devices, files, and URLs related to threat signals from your network, enabling you to investigate and explore the presence of security threats on the network.</span></span>

<span data-ttu-id="db9c9-122">Microsoft 不會使用您的資料進行廣告。</span><span class="sxs-lookup"><span data-stu-id="db9c9-122">Microsoft does not use your data for advertising.</span></span>

## <a name="data-protection-and-encryption"></a><span data-ttu-id="db9c9-123">資料保護和加密</span><span class="sxs-lookup"><span data-stu-id="db9c9-123">Data protection and encryption</span></span>
<span data-ttu-id="db9c9-124">「Defender for Endpoint service」利用以 Microsoft Azure 基礎結構為基礎的 art 資料保護技術狀態。</span><span class="sxs-lookup"><span data-stu-id="db9c9-124">The Defender for Endpoint service utilizes state of the art data protection technologies which are based on Microsoft Azure infrastructure.</span></span> 

<span data-ttu-id="db9c9-125">有許多與我們的服務維護相關之資料保護的相關事項。</span><span class="sxs-lookup"><span data-stu-id="db9c9-125">There are various aspects relevant to data protection that our service takes care of.</span></span> <span data-ttu-id="db9c9-126">加密是一項最重要的功能，其中包括靜態資料加密、航班中的加密，以及使用主要 Vault 的金鑰管理。</span><span class="sxs-lookup"><span data-stu-id="db9c9-126">Encryption is one of the most critical and it includes data encryption at rest, encryption in flight, and key management with Key Vault.</span></span> <span data-ttu-id="db9c9-127">如需有關供 Defender for Endpoint service 使用之其他技術的詳細資訊，請參閱 [Azure 加密概述](https://docs.microsoft.com/azure/security/security-azure-encryption-overview)。</span><span class="sxs-lookup"><span data-stu-id="db9c9-127">For more information on other technologies used by the Defender for Endpoint service, see [Azure encryption overview](https://docs.microsoft.com/azure/security/security-azure-encryption-overview).</span></span> 

<span data-ttu-id="db9c9-128">在所有案例中，至少會以256位的 [AES 加密](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) 加密資料。</span><span class="sxs-lookup"><span data-stu-id="db9c9-128">In all scenarios, data is encrypted using 256-bit [AES encryption](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) at the minimum.</span></span>


## <a name="data-storage-location"></a><span data-ttu-id="db9c9-129">資料儲存位置</span><span class="sxs-lookup"><span data-stu-id="db9c9-129">Data storage location</span></span>

<span data-ttu-id="db9c9-130">在歐洲同盟、英國或美國地區的 Microsoft Azure 資料中心內，用來進行端點的 Defender。</span><span class="sxs-lookup"><span data-stu-id="db9c9-130">Defender for Endpoint operates in the Microsoft Azure datacenters in the European Union, the United Kingdom, or in the United States.</span></span> <span data-ttu-id="db9c9-131">服務所收集的客戶資料可能會儲存在： (a) 租使用者地理位置（如布建期間所識別）; 若要使用其他 Microsoft online 服務處理這類資料，則 (b) （如其他線上服務的資料儲存規則所定義的地理位置）。</span><span class="sxs-lookup"><span data-stu-id="db9c9-131">Customer data collected by the service may be stored in: (a) the geo-location of the tenant as identified during provisioning or, (b) if Defender for Endpoint uses another Microsoft online service to process such data, the geolocation as defined by the data storage rules of that other online service.</span></span>

<span data-ttu-id="db9c9-132">在假名化表單中的客戶資料也可以儲存在美國的中央儲存區與處理系統中。</span><span class="sxs-lookup"><span data-stu-id="db9c9-132">Customer data in pseudonymized form may also be stored in the central storage and processing systems in the United States.</span></span>

<span data-ttu-id="db9c9-133">設定後，您就無法變更儲存資料的位置。</span><span class="sxs-lookup"><span data-stu-id="db9c9-133">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="db9c9-134">這會透過主動選取資料所在的地理位置，提供一種簡便的方法來降低法規遵從性風險。</span><span class="sxs-lookup"><span data-stu-id="db9c9-134">This provides a convenient way to minimize compliance risk by actively selecting the geographic locations where your data will reside.</span></span> 

## <a name="is-my-data-isolated-from-other-customer-data"></a><span data-ttu-id="db9c9-135">我的資料是否獨立于其他客戶資料？</span><span class="sxs-lookup"><span data-stu-id="db9c9-135">Is my data isolated from other customer data?</span></span>
<span data-ttu-id="db9c9-136">是的，您的資料會透過存取驗證及根據客戶識別碼的邏輯隔離來隔離。</span><span class="sxs-lookup"><span data-stu-id="db9c9-136">Yes, your data is isolated through access authentication and logical segregation based on customer identifier.</span></span> <span data-ttu-id="db9c9-137">每個客戶只能存取來自其自身組織的資料，以及 Microsoft 所提供的一般資料。</span><span class="sxs-lookup"><span data-stu-id="db9c9-137">Each customer can only access data collected from its own organization and generic data that Microsoft provides.</span></span>

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a><span data-ttu-id="db9c9-138">Microsoft 如何防止惡意內部人員活動和濫用高許可權角色？</span><span class="sxs-lookup"><span data-stu-id="db9c9-138">How does Microsoft prevent malicious insider activities and abuse of high privilege roles?</span></span>

<span data-ttu-id="db9c9-139">根據設計，Microsoft 開發人員和系統管理員已獲足夠的許可權來執行所指派的職責，以進行服務的運作及演化。</span><span class="sxs-lookup"><span data-stu-id="db9c9-139">Microsoft developers and administrators have, by design, been given sufficient privileges to carry out their assigned duties to operate and evolve the service.</span></span> <span data-ttu-id="db9c9-140">Microsoft 會部署預防性、偵探和反應性控制措施的組合，包括下列機制，以協助防止未經授權的開發人員和/或管理活動：</span><span class="sxs-lookup"><span data-stu-id="db9c9-140">Microsoft deploys combinations of preventive, detective, and reactive controls including the following mechanisms to help protect against unauthorized developer and/or administrative activity:</span></span>

- <span data-ttu-id="db9c9-141">敏感性資料的緊密存取控制</span><span class="sxs-lookup"><span data-stu-id="db9c9-141">Tight access control to sensitive data</span></span>
- <span data-ttu-id="db9c9-142">極大地增強獨立偵測惡意活動的控制群組合</span><span class="sxs-lookup"><span data-stu-id="db9c9-142">Combinations of controls that greatly enhance independent detection of malicious activity</span></span>
- <span data-ttu-id="db9c9-143">多層的監控、記錄和報告</span><span class="sxs-lookup"><span data-stu-id="db9c9-143">Multiple levels of monitoring, logging, and reporting</span></span>

<span data-ttu-id="db9c9-144">此外，Microsoft 會執行某些作業人員的後臺驗證檢查，並限制對應用程式、系統和網路基礎結構的存取，以與背景驗證層級成比例。</span><span class="sxs-lookup"><span data-stu-id="db9c9-144">Additionally, Microsoft conducts background verification checks of certain operations personnel, and limits access to applications, systems, and network infrastructure in proportion to the level of background verification.</span></span> <span data-ttu-id="db9c9-145">當您需要存取客戶的帳戶或其職責效能中的相關資訊時，作業人員會遵循正式的處理常式。</span><span class="sxs-lookup"><span data-stu-id="db9c9-145">Operations personnel follow a formal process when they are required to access a customer’s account or related information in the performance of their duties.</span></span>

<span data-ttu-id="db9c9-146">在 Microsoft Azure 政府資料中心內部署之服務的資料存取權只會授與受限於特定政府法規和需求的資料，例如 FedRAMP、NIST 800.171 (DIB) 、ITAR、IRS 1075、DoD L4 及 CJIS。</span><span class="sxs-lookup"><span data-stu-id="db9c9-146">Access to data for services deployed in Microsoft Azure Government data centers is only granted to operating personnel who have been screened and approved to handle data that is subject to certain government regulations and requirements, such as FedRAMP, NIST 800.171 (DIB), ITAR, IRS 1075, DoD L4, and CJIS.</span></span>


## <a name="is-data-shared-with-other-customers"></a><span data-ttu-id="db9c9-147">資料是否與其他客戶共用？</span><span class="sxs-lookup"><span data-stu-id="db9c9-147">Is data shared with other customers?</span></span>
<span data-ttu-id="db9c9-148">不對。</span><span class="sxs-lookup"><span data-stu-id="db9c9-148">No.</span></span> <span data-ttu-id="db9c9-149">客戶資料會與其他客戶隔離，而且不會共用。</span><span class="sxs-lookup"><span data-stu-id="db9c9-149">Customer data is isolated from other customers and is not shared.</span></span> <span data-ttu-id="db9c9-150">不過，Microsoft 處理所產生的資料或不包含任何客戶特有資料的深入資訊，可能會與其他客戶共用。</span><span class="sxs-lookup"><span data-stu-id="db9c9-150">However, insights on the data resulting from Microsoft processing, and which don’t contain any customer-specific data, might be shared with other customers.</span></span> <span data-ttu-id="db9c9-151">每個客戶只能存取來自其自身組織的資料，以及 Microsoft 所提供的一般資料。</span><span class="sxs-lookup"><span data-stu-id="db9c9-151">Each customer can only access data collected from its own organization and generic data that Microsoft provides.</span></span>

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a><span data-ttu-id="db9c9-152">Microsoft 將資料儲存多久？</span><span class="sxs-lookup"><span data-stu-id="db9c9-152">How long will Microsoft store my data?</span></span> <span data-ttu-id="db9c9-153">什麼是 Microsoft 的資料保留原則？</span><span class="sxs-lookup"><span data-stu-id="db9c9-153">What is Microsoft’s data retention policy?</span></span>
<span data-ttu-id="db9c9-154">**在服務上架**</span><span class="sxs-lookup"><span data-stu-id="db9c9-154">**At service onboarding**</span></span><br>
<span data-ttu-id="db9c9-155">根據預設，會在180天內保留資料;不過，您可以指定資料的資料保留原則。</span><span class="sxs-lookup"><span data-stu-id="db9c9-155">By default, data is retained for 180 days; however, you can specify the data retention policy for your data.</span></span> <span data-ttu-id="db9c9-156">這會決定 Windows Defender 端點用來儲存資料的時間長短。</span><span class="sxs-lookup"><span data-stu-id="db9c9-156">This determines how long Window Defender for Endpoint will store your data.</span></span> <span data-ttu-id="db9c9-157">您可以在一個月的範圍內靈活選擇六個月，以滿足公司的法規遵從性需求。</span><span class="sxs-lookup"><span data-stu-id="db9c9-157">There’s a flexibility of choosing in the range of one month to six months to meet your company’s regulatory compliance needs.</span></span>

<span data-ttu-id="db9c9-158">**合同終止或到期**</span><span class="sxs-lookup"><span data-stu-id="db9c9-158">**At contract termination or expiration**</span></span><br>
<span data-ttu-id="db9c9-159">您的資料將會保留，並可供您使用，但授權是在寬限期間或暫留模式下。</span><span class="sxs-lookup"><span data-stu-id="db9c9-159">Your data will be kept and will be available to you while the license is under grace period or suspended mode.</span></span> <span data-ttu-id="db9c9-160">在此期間結束時，將會從 Microsoft 系統中清除該資料，使其無法復原，不得超過180天的合約終止或到期時間。</span><span class="sxs-lookup"><span data-stu-id="db9c9-160">At the end of this period, that data will be erased from Microsoft’s systems to make it unrecoverable, no later than 180 days from contract termination or expiration.</span></span>

<span data-ttu-id="db9c9-161">**高級搜尋資料**</span><span class="sxs-lookup"><span data-stu-id="db9c9-161">**Advanced Hunting data**</span></span><br>
<span data-ttu-id="db9c9-162">進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。</span><span class="sxs-lookup"><span data-stu-id="db9c9-162">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span>


## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a><span data-ttu-id="db9c9-163">Microsoft 是否可以協助我們維護法規遵從性？</span><span class="sxs-lookup"><span data-stu-id="db9c9-163">Can Microsoft help us maintain regulatory compliance?</span></span>

<span data-ttu-id="db9c9-164">Microsoft 為客戶提供 Microsoft 安全性與合規性計畫的詳細資訊，包括審核報告和規範套件，以協助客戶根據自己的法律和法規需求，針對其評估 Endpoint 服務。</span><span class="sxs-lookup"><span data-stu-id="db9c9-164">Microsoft provides customers with detailed information about Microsoft's security and compliance programs, including audit reports and compliance packages, to help customers assess Defender for Endpoint services against their own legal and regulatory requirements.</span></span> <span data-ttu-id="db9c9-165">Defender for Endpoint 已取得許多憑證，包括 ISO、SOC、FedRAMP 高及 PCI，並繼續採用其他國家、地區和行業特定的認證。</span><span class="sxs-lookup"><span data-stu-id="db9c9-165">Defender for Endpoint has achieved a number of certifications including ISO, SOC, FedRAMP High, and PCI and continues to pursue additional national, regional and industry-specific certifications.</span></span>

<span data-ttu-id="db9c9-166">透過為客戶提供相容且獨立驗證的服務，Microsoft 可讓客戶輕鬆取得所執行之基礎結構和應用程式的規範。</span><span class="sxs-lookup"><span data-stu-id="db9c9-166">By providing customers with compliant, independently verified services, Microsoft makes it easier for customers to achieve compliance for the infrastructure and applications they run.</span></span>

<span data-ttu-id="db9c9-167">如需有關 Defender for Endpoint 認證報告的詳細資訊，請參閱 [Microsoft 信任中心](https://servicetrust.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="db9c9-167">For more information on the Defender for Endpoint certification reports, see [Microsoft Trust Center](https://servicetrust.microsoft.com/).</span></span> 

><span data-ttu-id="db9c9-168">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="db9c9-168">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="db9c9-169">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="db9c9-169">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-datastorage-belowfoldlink) 
