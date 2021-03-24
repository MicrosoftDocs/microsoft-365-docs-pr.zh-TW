---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessmentKB 表格
description: 深入瞭解 Advanced 搜尋架構的 DeviceTvmSecureConfigurationAssessmentKB 資料表中威脅 & 漏洞管理所評估的各種安全設定。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、威脅 & 漏洞管理、TVM、裝置管理、安全性設定、MITRE ATT&CK framework，知識庫，KB，DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059764"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="2e7ec-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="2e7ec-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2e7ec-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="2e7ec-105">**Applies to:**</span></span>
- [<span data-ttu-id="2e7ec-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2e7ec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="2e7ec-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2e7ec-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2e7ec-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2e7ec-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="2e7ec-109">在進階搜捕結構描述中的 `DeviceTvmSecureConfigurationAssessmentKB` 表格包含各種安全性設定的資訊 (如裝置是否已開啟自動更新)，是由[威脅與弱點管理](next-gen-threat-and-vuln-mgt.md)進行檢查。</span><span class="sxs-lookup"><span data-stu-id="2e7ec-109">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="2e7ec-110">其中也包含風險資訊、相關的行業效能評定，以及適用的 MITRE ATT&CK 技術和技巧。</span><span class="sxs-lookup"><span data-stu-id="2e7ec-110">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="2e7ec-111">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="2e7ec-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="2e7ec-112">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="2e7ec-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="2e7ec-113">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="2e7ec-113">Column name</span></span> | <span data-ttu-id="2e7ec-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="2e7ec-114">Data type</span></span> | <span data-ttu-id="2e7ec-115">描述</span><span class="sxs-lookup"><span data-stu-id="2e7ec-115">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="2e7ec-116">string</span><span class="sxs-lookup"><span data-stu-id="2e7ec-116">string</span></span> | <span data-ttu-id="2e7ec-117">特定設定的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="2e7ec-117">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="2e7ec-118">string</span><span class="sxs-lookup"><span data-stu-id="2e7ec-118">string</span></span> | <span data-ttu-id="2e7ec-119">設定對整個組態分數 (1-10) 的評分影響</span><span class="sxs-lookup"><span data-stu-id="2e7ec-119">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="2e7ec-120">字串</span><span class="sxs-lookup"><span data-stu-id="2e7ec-120">string</span></span> | <span data-ttu-id="2e7ec-121">組態的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="2e7ec-121">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="2e7ec-122">字串</span><span class="sxs-lookup"><span data-stu-id="2e7ec-122">string</span></span> | <span data-ttu-id="2e7ec-123">組態的描述</span><span class="sxs-lookup"><span data-stu-id="2e7ec-123">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="2e7ec-124">字串</span><span class="sxs-lookup"><span data-stu-id="2e7ec-124">string</span></span> | <span data-ttu-id="2e7ec-125">相關風險的描述</span><span class="sxs-lookup"><span data-stu-id="2e7ec-125">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="2e7ec-126">字串</span><span class="sxs-lookup"><span data-stu-id="2e7ec-126">string</span></span> | <span data-ttu-id="2e7ec-127">設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制</span><span class="sxs-lookup"><span data-stu-id="2e7ec-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="2e7ec-128">string</span><span class="sxs-lookup"><span data-stu-id="2e7ec-128">string</span></span> |<span data-ttu-id="2e7ec-129">設定所屬的子類別或子群組。</span><span class="sxs-lookup"><span data-stu-id="2e7ec-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="2e7ec-130">在許多情況下，這會描述特定性能或功能。</span><span class="sxs-lookup"><span data-stu-id="2e7ec-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="2e7ec-131">字串</span><span class="sxs-lookup"><span data-stu-id="2e7ec-131">string</span></span> | <span data-ttu-id="2e7ec-132">行業效能評定清單建議相同或類似的設定</span><span class="sxs-lookup"><span data-stu-id="2e7ec-132">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="2e7ec-133">字串</span><span class="sxs-lookup"><span data-stu-id="2e7ec-133">string</span></span> | <span data-ttu-id="2e7ec-134">與設定相關的 Mitre ATT&CK 架構技術清單</span><span class="sxs-lookup"><span data-stu-id="2e7ec-134">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="2e7ec-135">字串</span><span class="sxs-lookup"><span data-stu-id="2e7ec-135">string</span></span> | <span data-ttu-id="2e7ec-136">與設定相關的 Mitre ATT&CK 架構技巧清單</span><span class="sxs-lookup"><span data-stu-id="2e7ec-136">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2e7ec-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="2e7ec-137">Related topics</span></span>

- [<span data-ttu-id="2e7ec-138">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="2e7ec-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2e7ec-139">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="2e7ec-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2e7ec-140">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="2e7ec-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="2e7ec-141">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="2e7ec-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
