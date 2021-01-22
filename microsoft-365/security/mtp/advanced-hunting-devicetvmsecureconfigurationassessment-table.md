---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessment 資料表
description: 瞭解進位搜尋架構的 Device時間MSecureConfigurationAssesment 資料表中的安全性評定事件。 這些威脅&管理事件提供裝置資訊，以及安全性設定檔詳細資料、影響和合規性資訊。
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、威脅 & 弱點管理、TVM、裝置管理、安全性群組原則、DeviceMicmSecureConfigurationAssesment
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
ms.openlocfilehash: 6924bbc7a88a4f32d97534c72a180a1f1c4f7db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931095"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="29605-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="29605-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="29605-106">適用於：</span><span class="sxs-lookup"><span data-stu-id="29605-106">**Applies to:**</span></span>
- <span data-ttu-id="29605-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29605-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="29605-108">`DeviceTvmSecureConfigurationAssessment` 資料表中的每一個資料列都包含來自[威脅和弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的特定安全性設定評估事件。</span><span class="sxs-lookup"><span data-stu-id="29605-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="29605-109">使用這個參考資料來檢查最新的評估結果，並判斷裝置是否符合規定。</span><span class="sxs-lookup"><span data-stu-id="29605-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="29605-110">如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="29605-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="29605-111">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="29605-111">Column name</span></span> | <span data-ttu-id="29605-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="29605-112">Data type</span></span> | <span data-ttu-id="29605-113">描述</span><span class="sxs-lookup"><span data-stu-id="29605-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="29605-114">string</span><span class="sxs-lookup"><span data-stu-id="29605-114">string</span></span> | <span data-ttu-id="29605-115">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="29605-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="29605-116">string</span><span class="sxs-lookup"><span data-stu-id="29605-116">string</span></span> | <span data-ttu-id="29605-117">裝置 FQDN (完整) 功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="29605-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="29605-118">string</span><span class="sxs-lookup"><span data-stu-id="29605-118">string</span></span> | <span data-ttu-id="29605-119">在裝置上作業系統平臺。</span><span class="sxs-lookup"><span data-stu-id="29605-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="29605-120">這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="29605-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="29605-121">datetime</span><span class="sxs-lookup"><span data-stu-id="29605-121">datetime</span></span> | <span data-ttu-id="29605-122">記錄的產生日期和時間</span><span class="sxs-lookup"><span data-stu-id="29605-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="29605-123">string</span><span class="sxs-lookup"><span data-stu-id="29605-123">string</span></span> | <span data-ttu-id="29605-124">特定設定的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="29605-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="29605-125">string</span><span class="sxs-lookup"><span data-stu-id="29605-125">string</span></span> | <span data-ttu-id="29605-126">設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制</span><span class="sxs-lookup"><span data-stu-id="29605-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="29605-127">string</span><span class="sxs-lookup"><span data-stu-id="29605-127">string</span></span> | <span data-ttu-id="29605-128">設定所屬的子類別或子群組。</span><span class="sxs-lookup"><span data-stu-id="29605-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="29605-129">在許多情況下，這會描述特定性能或功能。</span><span class="sxs-lookup"><span data-stu-id="29605-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="29605-130">string</span><span class="sxs-lookup"><span data-stu-id="29605-130">string</span></span> | <span data-ttu-id="29605-131">設定對整個設定分數 (1-10) 的評分影響</span><span class="sxs-lookup"><span data-stu-id="29605-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="29605-132">布林值</span><span class="sxs-lookup"><span data-stu-id="29605-132">boolean</span></span> | <span data-ttu-id="29605-133">指出設定或原則是否已正確設定</span><span class="sxs-lookup"><span data-stu-id="29605-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="29605-134">布林值</span><span class="sxs-lookup"><span data-stu-id="29605-134">boolean</span></span> | <span data-ttu-id="29605-135">指出該組配置或原則是否適用于裝置</span><span class="sxs-lookup"><span data-stu-id="29605-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="29605-136">string</span><span class="sxs-lookup"><span data-stu-id="29605-136">string</span></span> | <span data-ttu-id="29605-137">有關群組原則或群組原則的其他關係資訊</span><span class="sxs-lookup"><span data-stu-id="29605-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="29605-138">布林值</span><span class="sxs-lookup"><span data-stu-id="29605-138">boolean</span></span> | <span data-ttu-id="29605-139">指出如果已應用程式組配置或原則，是否會影響使用者</span><span class="sxs-lookup"><span data-stu-id="29605-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="29605-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="29605-140">Related topics</span></span>

- [<span data-ttu-id="29605-141">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="29605-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="29605-142">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="29605-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="29605-143">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="29605-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="29605-144">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="29605-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="29605-145">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="29605-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="29605-146">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="29605-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="29605-147">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="29605-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
