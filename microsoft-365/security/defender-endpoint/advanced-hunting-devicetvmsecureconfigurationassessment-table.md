---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessment 資料表
description: 深入瞭解高級搜尋架構的 DeviceTvmSecureConfigurationAssessment 資料表中的威脅 & 漏洞管理安全性評估事件。 這些事件會提供裝置資訊，以及安全性設定詳細資料、影響和符合性資訊。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、威脅 & 漏洞管理、TVM、裝置管理、安全性設定、DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059767"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="b87ae-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="b87ae-105">DeviceTvmSecureConfigurationAssessment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b87ae-106">適用於：</span><span class="sxs-lookup"><span data-stu-id="b87ae-106">**Applies to:**</span></span>
- [<span data-ttu-id="b87ae-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b87ae-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="b87ae-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b87ae-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b87ae-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b87ae-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b87ae-110">`DeviceTvmSecureConfigurationAssessment` 資料表中的每一個資料列都包含來自[威脅和弱點管理](next-gen-threat-and-vuln-mgt.md)的特定安全性設定評估事件。</span><span class="sxs-lookup"><span data-stu-id="b87ae-110">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="b87ae-111">使用這個參考資料來檢查最新的評估結果，並判斷裝置是否符合規定。</span><span class="sxs-lookup"><span data-stu-id="b87ae-111">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="b87ae-112">如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。</span><span class="sxs-lookup"><span data-stu-id="b87ae-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="b87ae-113">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="b87ae-113">Column name</span></span> | <span data-ttu-id="b87ae-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="b87ae-114">Data type</span></span> | <span data-ttu-id="b87ae-115">描述</span><span class="sxs-lookup"><span data-stu-id="b87ae-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="b87ae-116">string</span><span class="sxs-lookup"><span data-stu-id="b87ae-116">string</span></span> | <span data-ttu-id="b87ae-117">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="b87ae-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b87ae-118">string</span><span class="sxs-lookup"><span data-stu-id="b87ae-118">string</span></span> | <span data-ttu-id="b87ae-119">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="b87ae-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="b87ae-120">string</span><span class="sxs-lookup"><span data-stu-id="b87ae-120">string</span></span> | <span data-ttu-id="b87ae-121">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="b87ae-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="b87ae-122">這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="b87ae-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="b87ae-123">datetime</span><span class="sxs-lookup"><span data-stu-id="b87ae-123">datetime</span></span> |<span data-ttu-id="b87ae-124">記錄的產生日期和時間</span><span class="sxs-lookup"><span data-stu-id="b87ae-124">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="b87ae-125">string</span><span class="sxs-lookup"><span data-stu-id="b87ae-125">string</span></span> | <span data-ttu-id="b87ae-126">特定設定的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="b87ae-126">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="b87ae-127">string</span><span class="sxs-lookup"><span data-stu-id="b87ae-127">string</span></span> | <span data-ttu-id="b87ae-128">設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制</span><span class="sxs-lookup"><span data-stu-id="b87ae-128">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="b87ae-129">string</span><span class="sxs-lookup"><span data-stu-id="b87ae-129">string</span></span> |<span data-ttu-id="b87ae-130">設定所屬的子類別或子群組。</span><span class="sxs-lookup"><span data-stu-id="b87ae-130">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="b87ae-131">在許多情況下，這會描述特定性能或功能。</span><span class="sxs-lookup"><span data-stu-id="b87ae-131">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="b87ae-132">string</span><span class="sxs-lookup"><span data-stu-id="b87ae-132">string</span></span> | <span data-ttu-id="b87ae-133">設定對整個設定分數 (1-10) 的評分影響</span><span class="sxs-lookup"><span data-stu-id="b87ae-133">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="b87ae-134">布林值</span><span class="sxs-lookup"><span data-stu-id="b87ae-134">boolean</span></span> | <span data-ttu-id="b87ae-135">指出設定或原則是否已正確設定</span><span class="sxs-lookup"><span data-stu-id="b87ae-135">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="b87ae-136">布林值</span><span class="sxs-lookup"><span data-stu-id="b87ae-136">boolean</span></span> | <span data-ttu-id="b87ae-137">指出設定或原則是否適用于裝置</span><span class="sxs-lookup"><span data-stu-id="b87ae-137">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="b87ae-138">string</span><span class="sxs-lookup"><span data-stu-id="b87ae-138">string</span></span> | <span data-ttu-id="b87ae-139">有關設定或原則的其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="b87ae-139">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="b87ae-140">布林值</span><span class="sxs-lookup"><span data-stu-id="b87ae-140">boolean</span></span> | <span data-ttu-id="b87ae-141">指出如果套用設定或原則，是否會影響使用者</span><span class="sxs-lookup"><span data-stu-id="b87ae-141">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b87ae-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="b87ae-142">Related topics</span></span>

- [<span data-ttu-id="b87ae-143">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="b87ae-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b87ae-144">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="b87ae-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b87ae-145">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="b87ae-145">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="b87ae-146">威脅與弱點管理的概觀</span><span class="sxs-lookup"><span data-stu-id="b87ae-146">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)