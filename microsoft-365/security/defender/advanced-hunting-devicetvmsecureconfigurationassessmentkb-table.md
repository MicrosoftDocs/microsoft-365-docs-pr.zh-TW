---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessmentKB 表格
description: 在進階搜捕結構描述之 DeviceTvmSecureConfigurationAssessmentKB 表格中，了解由威脅與弱點管理評估的各種安全性設定。
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，microsoft 365，m365，search，query，遙測，schema reference，kusto，table，欄，資料類型，描述，威脅 & 漏洞管理，TVM，裝置管理，安全性設定，MITRE ATT&CK framework，知識庫，KB，DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1dfa710b86afdcfd8a5643555564a0f34c7b4702
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024238"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="6d00f-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="6d00f-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6d00f-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="6d00f-105">**Applies to:**</span></span>
- <span data-ttu-id="6d00f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d00f-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="6d00f-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6d00f-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="6d00f-108">在進階搜捕結構描述中的 `DeviceTvmSecureConfigurationAssessmentKB` 表格包含各種安全性設定的資訊 (如裝置是否已開啟自動更新)，是由[威脅與弱點管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)進行檢查。</span><span class="sxs-lookup"><span data-stu-id="6d00f-108">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="6d00f-109">其中也包含風險資訊、相關的行業效能評定，以及適用的 MITRE ATT&CK 技術和技巧。</span><span class="sxs-lookup"><span data-stu-id="6d00f-109">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="6d00f-110">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="6d00f-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6d00f-111">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="6d00f-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6d00f-112">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="6d00f-112">Column name</span></span> | <span data-ttu-id="6d00f-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="6d00f-113">Data type</span></span> | <span data-ttu-id="6d00f-114">描述</span><span class="sxs-lookup"><span data-stu-id="6d00f-114">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="6d00f-115">string</span><span class="sxs-lookup"><span data-stu-id="6d00f-115">string</span></span> | <span data-ttu-id="6d00f-116">特定設定的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="6d00f-116">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="6d00f-117">string</span><span class="sxs-lookup"><span data-stu-id="6d00f-117">string</span></span> | <span data-ttu-id="6d00f-118">設定對整個組態分數 (1-10) 的評分影響</span><span class="sxs-lookup"><span data-stu-id="6d00f-118">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="6d00f-119">字串</span><span class="sxs-lookup"><span data-stu-id="6d00f-119">string</span></span> | <span data-ttu-id="6d00f-120">組態的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="6d00f-120">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="6d00f-121">字串</span><span class="sxs-lookup"><span data-stu-id="6d00f-121">string</span></span> | <span data-ttu-id="6d00f-122">組態的描述</span><span class="sxs-lookup"><span data-stu-id="6d00f-122">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="6d00f-123">字串</span><span class="sxs-lookup"><span data-stu-id="6d00f-123">string</span></span> | <span data-ttu-id="6d00f-124">相關風險的描述</span><span class="sxs-lookup"><span data-stu-id="6d00f-124">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="6d00f-125">字串</span><span class="sxs-lookup"><span data-stu-id="6d00f-125">string</span></span> | <span data-ttu-id="6d00f-126">設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制</span><span class="sxs-lookup"><span data-stu-id="6d00f-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="6d00f-127">string</span><span class="sxs-lookup"><span data-stu-id="6d00f-127">string</span></span> |<span data-ttu-id="6d00f-128">設定所屬的子類別或子群組。</span><span class="sxs-lookup"><span data-stu-id="6d00f-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="6d00f-129">在許多情況下，這會描述特定性能或功能。</span><span class="sxs-lookup"><span data-stu-id="6d00f-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="6d00f-130">字串</span><span class="sxs-lookup"><span data-stu-id="6d00f-130">string</span></span> | <span data-ttu-id="6d00f-131">行業效能評定清單建議相同或類似的設定</span><span class="sxs-lookup"><span data-stu-id="6d00f-131">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="6d00f-132">字串</span><span class="sxs-lookup"><span data-stu-id="6d00f-132">string</span></span> | <span data-ttu-id="6d00f-133">代表用來識別或分類安全性設定之各種屬性的標籤</span><span class="sxs-lookup"><span data-stu-id="6d00f-133">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="6d00f-134">string</span><span class="sxs-lookup"><span data-stu-id="6d00f-134">string</span></span> | <span data-ttu-id="6d00f-135">建議的動作可減少或解決任何相關聯的風險</span><span class="sxs-lookup"><span data-stu-id="6d00f-135">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6d00f-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="6d00f-136">Related topics</span></span>

- [<span data-ttu-id="6d00f-137">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="6d00f-137">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6d00f-138">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="6d00f-138">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6d00f-139">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="6d00f-139">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6d00f-140">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="6d00f-140">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6d00f-141">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="6d00f-141">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6d00f-142">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="6d00f-142">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6d00f-143">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="6d00f-143">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)