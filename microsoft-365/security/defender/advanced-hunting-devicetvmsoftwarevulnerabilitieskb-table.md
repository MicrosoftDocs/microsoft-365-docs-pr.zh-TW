---
title: 進階搜捕結構描述中的 DeviceTvmSoftwareVulnerabilitiesKB 表格
description: 了解由進階搜捕結構描述之 DeviceTvmSoftwareVulnerabilitiesKB 表格中之威脅與弱點管理所追蹤的軟體弱點。
keywords: 「高級搜尋」、「威脅搜尋」、「網路威脅搜尋」、「Microsoft 365 Defender」、「Microsoft 365」、「m365」、「搜尋」、「遙測」、「架構」、「kusto」、「表格」、「資料類型」、「描述」、「威脅 & 弱點管理、TVM、裝置管理、軟體、清查、弱點、CVE ID
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
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023794"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="e89cf-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="e89cf-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e89cf-105">**適用於**：</span><span class="sxs-lookup"><span data-stu-id="e89cf-105">**Applies to:**</span></span>
- <span data-ttu-id="e89cf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e89cf-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="e89cf-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e89cf-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="e89cf-108">進階搜捕結構描述中的 `DeviceTvmSoftwareVulnerabilitiesKB` 表格包含 [威脅與弱點管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)為裝置進行評估的弱點清單。</span><span class="sxs-lookup"><span data-stu-id="e89cf-108">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="e89cf-109">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="e89cf-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="e89cf-110">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="e89cf-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e89cf-111">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="e89cf-111">Column name</span></span> | <span data-ttu-id="e89cf-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="e89cf-112">Data type</span></span> | <span data-ttu-id="e89cf-113">描述</span><span class="sxs-lookup"><span data-stu-id="e89cf-113">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="e89cf-114">字串</span><span class="sxs-lookup"><span data-stu-id="e89cf-114">string</span></span> | <span data-ttu-id="e89cf-115">在常見弱點與漏洞 (CVE) 系統下指派給安全性弱點的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="e89cf-115">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="e89cf-116">字串</span><span class="sxs-lookup"><span data-stu-id="e89cf-116">string</span></span> | <span data-ttu-id="e89cf-117">在常見弱點計分系統 (CVSS) 下指派給安全性弱點的嚴重性分數</span><span class="sxs-lookup"><span data-stu-id="e89cf-117">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="e89cf-118">布林值</span><span class="sxs-lookup"><span data-stu-id="e89cf-118">boolean</span></span> | <span data-ttu-id="e89cf-119">表示該弱點的惡意探索代碼是否可供公開使用</span><span class="sxs-lookup"><span data-stu-id="e89cf-119">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="e89cf-120">字串</span><span class="sxs-lookup"><span data-stu-id="e89cf-120">string</span></span> | <span data-ttu-id="e89cf-121">安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素</span><span class="sxs-lookup"><span data-stu-id="e89cf-121">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="e89cf-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e89cf-122">datetime</span></span> | <span data-ttu-id="e89cf-123">上次修改之項目及相關中繼資料的日期和時間</span><span class="sxs-lookup"><span data-stu-id="e89cf-123">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="e89cf-124">datetime</span><span class="sxs-lookup"><span data-stu-id="e89cf-124">datetime</span></span> | <span data-ttu-id="e89cf-125">公開的日期弱點</span><span class="sxs-lookup"><span data-stu-id="e89cf-125">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="e89cf-126">字串</span><span class="sxs-lookup"><span data-stu-id="e89cf-126">string</span></span> | <span data-ttu-id="e89cf-127">弱點及相關風險的描述</span><span class="sxs-lookup"><span data-stu-id="e89cf-127">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="e89cf-128">字串</span><span class="sxs-lookup"><span data-stu-id="e89cf-128">string</span></span> | <span data-ttu-id="e89cf-129">受此弱點影響的所有軟體產品清單</span><span class="sxs-lookup"><span data-stu-id="e89cf-129">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e89cf-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="e89cf-130">Related topics</span></span>

- [<span data-ttu-id="e89cf-131">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="e89cf-131">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e89cf-132">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="e89cf-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e89cf-133">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="e89cf-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e89cf-134">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="e89cf-134">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e89cf-135">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="e89cf-135">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e89cf-136">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="e89cf-136">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e89cf-137">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="e89cf-137">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)