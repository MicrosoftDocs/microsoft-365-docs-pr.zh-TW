---
title: 進階搜捕結構描述中的 DeviceTvmSoftwareVulnerabilitiesKB 表格
description: 了解由進階搜捕結構描述之 DeviceTvmSoftwareVulnerabilitiesKB 表格中之威脅與弱點管理所追蹤的軟體弱點。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構、參考、kusto、表格、欄、資料類型、描述、威脅 & 漏洞管理、TVM、裝置管理、軟體、庫存、弱點、CVE 識別碼、CVSS、DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 4b7447bce3d1859f71cd1f3f7ea100b9978641c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907237"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="13776-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="13776-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="13776-105">**適用於**：</span><span class="sxs-lookup"><span data-stu-id="13776-105">**Applies to:**</span></span>
- <span data-ttu-id="13776-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13776-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="13776-107">進階搜捕結構描述中的 `DeviceTvmSoftwareVulnerabilitiesKB` 表格包含 [威脅與弱點管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)為裝置進行評估的弱點清單。</span><span class="sxs-lookup"><span data-stu-id="13776-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="13776-108">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="13776-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="13776-109">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="13776-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="13776-110">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="13776-110">Column name</span></span> | <span data-ttu-id="13776-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="13776-111">Data type</span></span> | <span data-ttu-id="13776-112">描述</span><span class="sxs-lookup"><span data-stu-id="13776-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="13776-113">字串</span><span class="sxs-lookup"><span data-stu-id="13776-113">string</span></span> | <span data-ttu-id="13776-114">在常見弱點與漏洞 (CVE) 系統下指派給安全性弱點的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="13776-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="13776-115">字串</span><span class="sxs-lookup"><span data-stu-id="13776-115">string</span></span> | <span data-ttu-id="13776-116">在常見弱點計分系統 (CVSS) 下指派給安全性弱點的嚴重性分數</span><span class="sxs-lookup"><span data-stu-id="13776-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="13776-117">布林值</span><span class="sxs-lookup"><span data-stu-id="13776-117">boolean</span></span> | <span data-ttu-id="13776-118">表示該弱點的惡意探索代碼是否可供公開使用</span><span class="sxs-lookup"><span data-stu-id="13776-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="13776-119">字串</span><span class="sxs-lookup"><span data-stu-id="13776-119">string</span></span> | <span data-ttu-id="13776-120">安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素</span><span class="sxs-lookup"><span data-stu-id="13776-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="13776-121">datetime</span><span class="sxs-lookup"><span data-stu-id="13776-121">datetime</span></span> | <span data-ttu-id="13776-122">上次修改之項目及相關中繼資料的日期和時間</span><span class="sxs-lookup"><span data-stu-id="13776-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="13776-123">datetime</span><span class="sxs-lookup"><span data-stu-id="13776-123">datetime</span></span> | <span data-ttu-id="13776-124">公開的日期弱點</span><span class="sxs-lookup"><span data-stu-id="13776-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="13776-125">字串</span><span class="sxs-lookup"><span data-stu-id="13776-125">string</span></span> | <span data-ttu-id="13776-126">弱點及相關風險的描述</span><span class="sxs-lookup"><span data-stu-id="13776-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="13776-127">字串</span><span class="sxs-lookup"><span data-stu-id="13776-127">string</span></span> | <span data-ttu-id="13776-128">受此弱點影響的所有軟體產品清單</span><span class="sxs-lookup"><span data-stu-id="13776-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="13776-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="13776-129">Related topics</span></span>

- [<span data-ttu-id="13776-130">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="13776-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="13776-131">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="13776-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="13776-132">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="13776-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="13776-133">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="13776-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="13776-134">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="13776-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="13776-135">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="13776-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="13776-136">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="13776-136">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)