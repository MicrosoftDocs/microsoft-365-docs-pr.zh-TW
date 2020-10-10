---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessment 資料表
description: 了解在進階搜捕結構描述的 DeviceTvmSecureConfigurationAssessment 資料表中的威脅與弱點管理安全性評估事件。 這些事件會提供電腦資訊以及安全性設定的詳細資料、影響及合規性資訊。
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，資料表，欄，資料類型，描述，威脅 & 漏洞管理，TVM，裝置管理，安全性設定，DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: f25c0ad47a520ec23a94775b64a4f1ecc2eb9486
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414247"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="6065b-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="6065b-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6065b-106">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6065b-106">**Applies to:**</span></span>
- <span data-ttu-id="6065b-107">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="6065b-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="6065b-108">`DeviceTvmSecureConfigurationAssessment` 資料表中的每一個資料列都包含來自[威脅和弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的特定安全性設定評估事件。</span><span class="sxs-lookup"><span data-stu-id="6065b-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="6065b-109">使用這個參考資料來檢查最新的評估結果，並判斷裝置是否符合規定。</span><span class="sxs-lookup"><span data-stu-id="6065b-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="6065b-110">如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="6065b-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6065b-111">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="6065b-111">Column name</span></span> | <span data-ttu-id="6065b-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="6065b-112">Data type</span></span> | <span data-ttu-id="6065b-113">描述</span><span class="sxs-lookup"><span data-stu-id="6065b-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="6065b-114">string</span><span class="sxs-lookup"><span data-stu-id="6065b-114">string</span></span> | <span data-ttu-id="6065b-115">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="6065b-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6065b-116">string</span><span class="sxs-lookup"><span data-stu-id="6065b-116">string</span></span> | <span data-ttu-id="6065b-117">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="6065b-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="6065b-118">string</span><span class="sxs-lookup"><span data-stu-id="6065b-118">string</span></span> | <span data-ttu-id="6065b-119">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="6065b-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="6065b-120">這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="6065b-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="6065b-121">datetime</span><span class="sxs-lookup"><span data-stu-id="6065b-121">datetime</span></span> | <span data-ttu-id="6065b-122">記錄的產生日期和時間</span><span class="sxs-lookup"><span data-stu-id="6065b-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="6065b-123">string</span><span class="sxs-lookup"><span data-stu-id="6065b-123">string</span></span> | <span data-ttu-id="6065b-124">特定設定的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="6065b-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="6065b-125">string</span><span class="sxs-lookup"><span data-stu-id="6065b-125">string</span></span> | <span data-ttu-id="6065b-126">設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制</span><span class="sxs-lookup"><span data-stu-id="6065b-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="6065b-127">string</span><span class="sxs-lookup"><span data-stu-id="6065b-127">string</span></span> | <span data-ttu-id="6065b-128">設定所屬的子類別或子群組。</span><span class="sxs-lookup"><span data-stu-id="6065b-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="6065b-129">在許多情況下，這會描述特定性能或功能。</span><span class="sxs-lookup"><span data-stu-id="6065b-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="6065b-130">string</span><span class="sxs-lookup"><span data-stu-id="6065b-130">string</span></span> | <span data-ttu-id="6065b-131">設定對整個設定分數 (1-10) 的評分影響</span><span class="sxs-lookup"><span data-stu-id="6065b-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="6065b-132">布林值</span><span class="sxs-lookup"><span data-stu-id="6065b-132">boolean</span></span> | <span data-ttu-id="6065b-133">指出設定或原則是否已正確設定</span><span class="sxs-lookup"><span data-stu-id="6065b-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6065b-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="6065b-134">Related topics</span></span>

- [<span data-ttu-id="6065b-135">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="6065b-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6065b-136">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="6065b-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6065b-137">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="6065b-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6065b-138">搜捕裝置、電子郵件、應用程式和身分識別</span><span class="sxs-lookup"><span data-stu-id="6065b-138">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6065b-139">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="6065b-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6065b-140">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="6065b-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6065b-141">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="6065b-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
