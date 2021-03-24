---
title: 進階搜捕結構描述中的 DeviceTvmSoftwareVulnerabilitiesKB 表格
description: 了解由進階搜捕結構描述之 DeviceTvmSoftwareVulnerabilitiesKB 表格中之威脅與弱點管理所追蹤的軟體弱點。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、威脅 & 漏洞管理、TVM、裝置管理、軟體、庫存、弱點、、CVE ID、CVSS、DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057704"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="41398-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="41398-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41398-105">**適用於**：</span><span class="sxs-lookup"><span data-stu-id="41398-105">**Applies to:**</span></span>
- [<span data-ttu-id="41398-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="41398-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="41398-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="41398-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="41398-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="41398-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="41398-109">進階搜捕結構描述中的 `DeviceTvmSoftwareVulnerabilitiesKB` 表格包含 [威脅與弱點管理](next-gen-threat-and-vuln-mgt.md)為裝置進行評估的弱點清單。</span><span class="sxs-lookup"><span data-stu-id="41398-109">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) assesses devices for.</span></span> <span data-ttu-id="41398-110">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="41398-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="41398-111">如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-reference.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="41398-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="41398-112">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="41398-112">Column name</span></span> | <span data-ttu-id="41398-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="41398-113">Data type</span></span> | <span data-ttu-id="41398-114">描述</span><span class="sxs-lookup"><span data-stu-id="41398-114">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="41398-115">字串</span><span class="sxs-lookup"><span data-stu-id="41398-115">string</span></span> | <span data-ttu-id="41398-116">在常見弱點與漏洞 (CVE) 系統下指派給安全性弱點的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="41398-116">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="41398-117">字串</span><span class="sxs-lookup"><span data-stu-id="41398-117">string</span></span> | <span data-ttu-id="41398-118">在常見弱點計分系統 (CVSS) 下指派給安全性弱點的嚴重性分數</span><span class="sxs-lookup"><span data-stu-id="41398-118">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="41398-119">布林值</span><span class="sxs-lookup"><span data-stu-id="41398-119">boolean</span></span> | <span data-ttu-id="41398-120">表示該弱點的惡意探索代碼是否可供公開使用</span><span class="sxs-lookup"><span data-stu-id="41398-120">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="41398-121">字串</span><span class="sxs-lookup"><span data-stu-id="41398-121">string</span></span> | <span data-ttu-id="41398-122">安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素</span><span class="sxs-lookup"><span data-stu-id="41398-122">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="41398-123">datetime</span><span class="sxs-lookup"><span data-stu-id="41398-123">datetime</span></span> | <span data-ttu-id="41398-124">上次修改之項目及相關中繼資料的日期和時間</span><span class="sxs-lookup"><span data-stu-id="41398-124">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="41398-125">datetime</span><span class="sxs-lookup"><span data-stu-id="41398-125">datetime</span></span> | <span data-ttu-id="41398-126">公開的日期弱點</span><span class="sxs-lookup"><span data-stu-id="41398-126">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="41398-127">字串</span><span class="sxs-lookup"><span data-stu-id="41398-127">string</span></span> | <span data-ttu-id="41398-128">弱點及相關風險的描述</span><span class="sxs-lookup"><span data-stu-id="41398-128">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="41398-129">字串</span><span class="sxs-lookup"><span data-stu-id="41398-129">string</span></span> | <span data-ttu-id="41398-130">受此弱點影響的所有軟體產品清單</span><span class="sxs-lookup"><span data-stu-id="41398-130">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="41398-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="41398-131">Related topics</span></span>

- [<span data-ttu-id="41398-132">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="41398-132">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="41398-133">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="41398-133">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="41398-134">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="41398-134">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="41398-135">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="41398-135">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
