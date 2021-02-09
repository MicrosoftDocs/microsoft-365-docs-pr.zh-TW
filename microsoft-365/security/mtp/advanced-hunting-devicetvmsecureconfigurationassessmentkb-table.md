---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessmentKB 表格
description: 在進階搜捕結構描述之 DeviceTvmSecureConfigurationAssessmentKB 表格中，了解由威脅與弱點管理評估的各種安全性設定。
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，table，欄，資料類型，描述，威脅 & 漏洞管理，TVM，裝置管理，安全性設定，MITRE ATT&CK framework，知識庫，KB，DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: cf4204767843b9a9e0b0bbfecc2d3fc50db531fc
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145448"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="897a2-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="897a2-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="897a2-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="897a2-105">**Applies to:**</span></span>
- <span data-ttu-id="897a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="897a2-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="897a2-107">在進階搜捕結構描述中的 `DeviceTvmSecureConfigurationAssessmentKB` 表格包含各種安全性設定的資訊 (如裝置是否已開啟自動更新)，是由[威脅與弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)進行檢查。</span><span class="sxs-lookup"><span data-stu-id="897a2-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="897a2-108">其中也包含風險資訊、相關的行業效能評定，以及適用的 MITRE ATT&CK 技術和技巧。</span><span class="sxs-lookup"><span data-stu-id="897a2-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="897a2-109">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="897a2-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="897a2-110">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="897a2-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="897a2-111">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="897a2-111">Column name</span></span> | <span data-ttu-id="897a2-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="897a2-112">Data type</span></span> | <span data-ttu-id="897a2-113">描述</span><span class="sxs-lookup"><span data-stu-id="897a2-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="897a2-114">string</span><span class="sxs-lookup"><span data-stu-id="897a2-114">string</span></span> | <span data-ttu-id="897a2-115">特定設定的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="897a2-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="897a2-116">string</span><span class="sxs-lookup"><span data-stu-id="897a2-116">string</span></span> | <span data-ttu-id="897a2-117">設定對整個組態分數 (1-10) 的評分影響</span><span class="sxs-lookup"><span data-stu-id="897a2-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="897a2-118">字串</span><span class="sxs-lookup"><span data-stu-id="897a2-118">string</span></span> | <span data-ttu-id="897a2-119">組態的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="897a2-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="897a2-120">字串</span><span class="sxs-lookup"><span data-stu-id="897a2-120">string</span></span> | <span data-ttu-id="897a2-121">組態的描述</span><span class="sxs-lookup"><span data-stu-id="897a2-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="897a2-122">字串</span><span class="sxs-lookup"><span data-stu-id="897a2-122">string</span></span> | <span data-ttu-id="897a2-123">相關風險的描述</span><span class="sxs-lookup"><span data-stu-id="897a2-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="897a2-124">字串</span><span class="sxs-lookup"><span data-stu-id="897a2-124">string</span></span> | <span data-ttu-id="897a2-125">設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制</span><span class="sxs-lookup"><span data-stu-id="897a2-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="897a2-126">string</span><span class="sxs-lookup"><span data-stu-id="897a2-126">string</span></span> |<span data-ttu-id="897a2-127">設定所屬的子類別或子群組。</span><span class="sxs-lookup"><span data-stu-id="897a2-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="897a2-128">在許多情況下，這會描述特定性能或功能。</span><span class="sxs-lookup"><span data-stu-id="897a2-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="897a2-129">字串</span><span class="sxs-lookup"><span data-stu-id="897a2-129">string</span></span> | <span data-ttu-id="897a2-130">行業效能評定清單建議相同或類似的設定</span><span class="sxs-lookup"><span data-stu-id="897a2-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="897a2-131">字串</span><span class="sxs-lookup"><span data-stu-id="897a2-131">string</span></span> | <span data-ttu-id="897a2-132">代表用來識別或分類安全性設定之各種屬性的標籤</span><span class="sxs-lookup"><span data-stu-id="897a2-132">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="897a2-133">string</span><span class="sxs-lookup"><span data-stu-id="897a2-133">string</span></span> | <span data-ttu-id="897a2-134">建議的動作可減少或解決任何相關聯的風險</span><span class="sxs-lookup"><span data-stu-id="897a2-134">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="897a2-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="897a2-135">Related topics</span></span>

- [<span data-ttu-id="897a2-136">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="897a2-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="897a2-137">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="897a2-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="897a2-138">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="897a2-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="897a2-139">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="897a2-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="897a2-140">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="897a2-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="897a2-141">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="897a2-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="897a2-142">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="897a2-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
