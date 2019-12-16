---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessment 資料表
description: 了解在進階搜捕結構描述的 DeviceTvmSecureConfigurationAssessment 資料表中的威脅與弱點管理安全性評估事件。 這些事件會提供電腦資訊以及安全性設定的詳細資料、影響及合規性資訊。
keywords: 進階搜捕, 威脅搜捕, 網路威脅搜捕, 搜尋, 查詢, 遙測, 結構描述參照, Kusto, 資料表, 資料行, 資料類型, 描述, 威脅與弱點管理, TVM, 裝置管理, 安全性設定, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 2fee44c0d9c9ff30ca23ccef863e056cadee7de8
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910890"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="488da-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="488da-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="488da-106">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="488da-106">**Applies to:**</span></span>
- <span data-ttu-id="488da-107">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="488da-107">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="488da-108">`DeviceTvmSecureConfigurationAssessment` 資料表中的每一個資料列都包含來自[威脅和弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的特定安全性設定評估事件。</span><span class="sxs-lookup"><span data-stu-id="488da-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="488da-109">使用這個參考資料來檢查最新的評估結果，並判斷裝置是否符合規定。</span><span class="sxs-lookup"><span data-stu-id="488da-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="488da-110">如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="488da-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="488da-111">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="488da-111">Column name</span></span> | <span data-ttu-id="488da-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="488da-112">Data type</span></span> | <span data-ttu-id="488da-113">描述</span><span class="sxs-lookup"><span data-stu-id="488da-113">Description</span></span> |
|-------------|-----------|-------------|
| `MachineId` | <span data-ttu-id="488da-114">string</span><span class="sxs-lookup"><span data-stu-id="488da-114">string</span></span> | <span data-ttu-id="488da-115">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="488da-115">Unique identifier for the machine in the service</span></span> |
| `ComputerName` | <span data-ttu-id="488da-116">string</span><span class="sxs-lookup"><span data-stu-id="488da-116">string</span></span> | <span data-ttu-id="488da-117">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="488da-117">Fully qualified domain name (FQDN) of the pool</span></span> |
| `OSPlatform` | <span data-ttu-id="488da-118">string</span><span class="sxs-lookup"><span data-stu-id="488da-118">string</span></span> | <span data-ttu-id="488da-119">電腦上執行的作業系統平台。</span><span class="sxs-lookup"><span data-stu-id="488da-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="488da-120">這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="488da-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="488da-121">datetime</span><span class="sxs-lookup"><span data-stu-id="488da-121">DateTime</span></span> | <span data-ttu-id="488da-122">記錄的產生日期和時間</span><span class="sxs-lookup"><span data-stu-id="488da-122">Date and time when the migration was started</span></span> |
| `ConfigurationId` | <span data-ttu-id="488da-123">string</span><span class="sxs-lookup"><span data-stu-id="488da-123">string</span></span> | <span data-ttu-id="488da-124">特定設定的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="488da-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="488da-125">string</span><span class="sxs-lookup"><span data-stu-id="488da-125">string</span></span> | <span data-ttu-id="488da-126">設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制</span><span class="sxs-lookup"><span data-stu-id="488da-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="488da-127">string</span><span class="sxs-lookup"><span data-stu-id="488da-127">string</span></span> | <span data-ttu-id="488da-128">設定所屬的子類別或子群組。</span><span class="sxs-lookup"><span data-stu-id="488da-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="488da-129">在許多情況下，這會描述特定性能或功能。</span><span class="sxs-lookup"><span data-stu-id="488da-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="488da-130">string</span><span class="sxs-lookup"><span data-stu-id="488da-130">string</span></span> | <span data-ttu-id="488da-131">設定對整個設定分數 (1-10) 的評分影響</span><span class="sxs-lookup"><span data-stu-id="488da-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="488da-132">布林值</span><span class="sxs-lookup"><span data-stu-id="488da-132">boolean</span></span> | <span data-ttu-id="488da-133">指出設定或原則是否已正確設定</span><span class="sxs-lookup"><span data-stu-id="488da-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="488da-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="488da-134">Related topics</span></span>

- [<span data-ttu-id="488da-135">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="488da-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="488da-136">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="488da-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="488da-137">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="488da-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="488da-138">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="488da-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="488da-139">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="488da-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="488da-140">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="488da-140">Apply design best practices.</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="488da-141">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="488da-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
