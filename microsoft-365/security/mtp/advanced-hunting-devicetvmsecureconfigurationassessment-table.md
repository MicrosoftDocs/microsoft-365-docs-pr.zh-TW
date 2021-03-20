---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessment 資料表
description: 深入瞭解高級搜尋架構的 DeviceTvmSecureConfigurationAssessment 資料表中的安全性評估事件。 這些威脅 & 弱點管理事件會提供裝置資訊，以及安全性設定詳細資料、影響和符合性資訊。
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，資料表，欄，資料類型，描述，威脅 & 漏洞管理，TVM，裝置管理，安全性設定，DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 891bfcc775f8c8ebddea63d5490c1c9fef4e691a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907345"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="c5c22-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="c5c22-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c5c22-106">適用於：</span><span class="sxs-lookup"><span data-stu-id="c5c22-106">**Applies to:**</span></span>
- <span data-ttu-id="c5c22-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5c22-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="c5c22-108">`DeviceTvmSecureConfigurationAssessment` 資料表中的每一個資料列都包含來自[威脅和弱點管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的特定安全性設定評估事件。</span><span class="sxs-lookup"><span data-stu-id="c5c22-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="c5c22-109">使用這個參考資料來檢查最新的評估結果，並判斷裝置是否符合規定。</span><span class="sxs-lookup"><span data-stu-id="c5c22-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="c5c22-110">如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="c5c22-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c5c22-111">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="c5c22-111">Column name</span></span> | <span data-ttu-id="c5c22-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="c5c22-112">Data type</span></span> | <span data-ttu-id="c5c22-113">描述</span><span class="sxs-lookup"><span data-stu-id="c5c22-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="c5c22-114">string</span><span class="sxs-lookup"><span data-stu-id="c5c22-114">string</span></span> | <span data-ttu-id="c5c22-115">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c5c22-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c5c22-116">string</span><span class="sxs-lookup"><span data-stu-id="c5c22-116">string</span></span> | <span data-ttu-id="c5c22-117">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="c5c22-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="c5c22-118">string</span><span class="sxs-lookup"><span data-stu-id="c5c22-118">string</span></span> | <span data-ttu-id="c5c22-119">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="c5c22-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="c5c22-120">這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="c5c22-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="c5c22-121">datetime</span><span class="sxs-lookup"><span data-stu-id="c5c22-121">datetime</span></span> | <span data-ttu-id="c5c22-122">記錄的產生日期和時間</span><span class="sxs-lookup"><span data-stu-id="c5c22-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="c5c22-123">string</span><span class="sxs-lookup"><span data-stu-id="c5c22-123">string</span></span> | <span data-ttu-id="c5c22-124">特定設定的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c5c22-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="c5c22-125">string</span><span class="sxs-lookup"><span data-stu-id="c5c22-125">string</span></span> | <span data-ttu-id="c5c22-126">設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制</span><span class="sxs-lookup"><span data-stu-id="c5c22-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="c5c22-127">string</span><span class="sxs-lookup"><span data-stu-id="c5c22-127">string</span></span> | <span data-ttu-id="c5c22-128">設定所屬的子類別或子群組。</span><span class="sxs-lookup"><span data-stu-id="c5c22-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="c5c22-129">在許多情況下，這會描述特定性能或功能。</span><span class="sxs-lookup"><span data-stu-id="c5c22-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="c5c22-130">string</span><span class="sxs-lookup"><span data-stu-id="c5c22-130">string</span></span> | <span data-ttu-id="c5c22-131">設定對整個設定分數 (1-10) 的評分影響</span><span class="sxs-lookup"><span data-stu-id="c5c22-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="c5c22-132">布林值</span><span class="sxs-lookup"><span data-stu-id="c5c22-132">boolean</span></span> | <span data-ttu-id="c5c22-133">指出設定或原則是否已正確設定</span><span class="sxs-lookup"><span data-stu-id="c5c22-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="c5c22-134">布林值</span><span class="sxs-lookup"><span data-stu-id="c5c22-134">boolean</span></span> | <span data-ttu-id="c5c22-135">指出設定或原則是否適用于裝置</span><span class="sxs-lookup"><span data-stu-id="c5c22-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="c5c22-136">string</span><span class="sxs-lookup"><span data-stu-id="c5c22-136">string</span></span> | <span data-ttu-id="c5c22-137">有關設定或原則的其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="c5c22-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="c5c22-138">布林值</span><span class="sxs-lookup"><span data-stu-id="c5c22-138">boolean</span></span> | <span data-ttu-id="c5c22-139">指出如果套用設定或原則，是否會影響使用者</span><span class="sxs-lookup"><span data-stu-id="c5c22-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c5c22-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="c5c22-140">Related topics</span></span>

- [<span data-ttu-id="c5c22-141">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="c5c22-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c5c22-142">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="c5c22-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c5c22-143">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="c5c22-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c5c22-144">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="c5c22-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c5c22-145">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="c5c22-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c5c22-146">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="c5c22-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c5c22-147">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="c5c22-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)