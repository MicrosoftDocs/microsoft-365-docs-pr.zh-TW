---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessmentKB 表格
description: 在進階搜捕結構描述之 DeviceTvmSecureConfigurationAssessmentKB 表格中，了解由威脅與弱點管理評估的各種安全性設定。
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，table，欄，資料類型，描述，威脅 & 漏洞管理，TVM，裝置管理，安全性設定，MITRE ATT&CK framework，知識庫，KB，DeviceTvmSecureConfigurationAssessmentKB
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a265bb84b0ad59ee56cb0f0670951bab1bcd344a
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327948"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="3b208-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="3b208-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="3b208-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="3b208-105">**Applies to:**</span></span>
- <span data-ttu-id="3b208-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="3b208-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="3b208-107">在進階搜捕結構描述中的 `DeviceTvmSecureConfigurationAssessmentKB` 表格包含各種安全性設定的資訊 (如裝置是否已開啟自動更新)，是由[威脅與弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)進行檢查。</span><span class="sxs-lookup"><span data-stu-id="3b208-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="3b208-108">其中也包含風險資訊、相關的行業效能評定，以及適用的 MITRE ATT&CK 技術和技巧。</span><span class="sxs-lookup"><span data-stu-id="3b208-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="3b208-109">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="3b208-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="3b208-110">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="3b208-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3b208-111">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="3b208-111">Column name</span></span> | <span data-ttu-id="3b208-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="3b208-112">Data type</span></span> | <span data-ttu-id="3b208-113">描述</span><span class="sxs-lookup"><span data-stu-id="3b208-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="3b208-114">string</span><span class="sxs-lookup"><span data-stu-id="3b208-114">string</span></span> | <span data-ttu-id="3b208-115">特定設定的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="3b208-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="3b208-116">string</span><span class="sxs-lookup"><span data-stu-id="3b208-116">string</span></span> | <span data-ttu-id="3b208-117">設定對整個組態分數 (1-10) 的評分影響</span><span class="sxs-lookup"><span data-stu-id="3b208-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="3b208-118">string</span><span class="sxs-lookup"><span data-stu-id="3b208-118">string</span></span> | <span data-ttu-id="3b208-119">組態的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="3b208-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="3b208-120">string</span><span class="sxs-lookup"><span data-stu-id="3b208-120">string</span></span> | <span data-ttu-id="3b208-121">組態的描述</span><span class="sxs-lookup"><span data-stu-id="3b208-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="3b208-122">string</span><span class="sxs-lookup"><span data-stu-id="3b208-122">string</span></span> | <span data-ttu-id="3b208-123">相關風險的描述</span><span class="sxs-lookup"><span data-stu-id="3b208-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="3b208-124">string</span><span class="sxs-lookup"><span data-stu-id="3b208-124">string</span></span> | <span data-ttu-id="3b208-125">設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制</span><span class="sxs-lookup"><span data-stu-id="3b208-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="3b208-126">string</span><span class="sxs-lookup"><span data-stu-id="3b208-126">string</span></span> |<span data-ttu-id="3b208-127">設定所屬的子類別或子群組。</span><span class="sxs-lookup"><span data-stu-id="3b208-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="3b208-128">在許多情況下，這會描述特定性能或功能。</span><span class="sxs-lookup"><span data-stu-id="3b208-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="3b208-129">string</span><span class="sxs-lookup"><span data-stu-id="3b208-129">string</span></span> | <span data-ttu-id="3b208-130">行業效能評定清單建議相同或類似的設定</span><span class="sxs-lookup"><span data-stu-id="3b208-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="3b208-131">string</span><span class="sxs-lookup"><span data-stu-id="3b208-131">string</span></span> | <span data-ttu-id="3b208-132">與設定相關的 Mitre ATT&CK 架構技術清單</span><span class="sxs-lookup"><span data-stu-id="3b208-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="3b208-133">字串</span><span class="sxs-lookup"><span data-stu-id="3b208-133">string</span></span> | <span data-ttu-id="3b208-134">與設定相關的 Mitre ATT&CK 架構技巧清單</span><span class="sxs-lookup"><span data-stu-id="3b208-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3b208-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="3b208-135">Related topics</span></span>

- [<span data-ttu-id="3b208-136">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="3b208-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3b208-137">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="3b208-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3b208-138">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="3b208-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3b208-139">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="3b208-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3b208-140">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="3b208-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3b208-141">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="3b208-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="3b208-142">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="3b208-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
