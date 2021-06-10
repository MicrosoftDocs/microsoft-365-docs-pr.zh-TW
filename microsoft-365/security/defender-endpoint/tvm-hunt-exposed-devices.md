---
title: 搜尋暴露的裝置
description: 瞭解如何使用威脅與弱點管理來協助安全性系統管理員、IT 系統管理員和 SecOps 共同作業。
keywords: Microsoft Defender for Endpoint tvm 案例，Microsoft Defender for Endpoint，tvm，tvm 案例，減少威脅 & 弱點洩密，減少威脅和弱點，改善安全性設定，增加 Microsoft 安全分數的裝置，增加威脅 & 弱點的 microsoft 安全分數，Microsoft 安全評分的裝置，披露分數，安全性控制
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9a8ebcc89c3009cd93fbb42f2a74bbb9ffcc31b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934090"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a><span data-ttu-id="08080-104">搜尋公開的裝置-威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="08080-104">Hunt for exposed devices - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="08080-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="08080-105">**Applies to:**</span></span>

- [<span data-ttu-id="08080-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="08080-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="08080-107">威脅及弱點管理</span><span class="sxs-lookup"><span data-stu-id="08080-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="08080-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08080-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="08080-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="08080-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="08080-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="08080-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a><span data-ttu-id="08080-111">使用高級搜尋來尋找包含弱點的裝置</span><span class="sxs-lookup"><span data-stu-id="08080-111">Use advanced hunting to find devices with vulnerabilities</span></span>

<span data-ttu-id="08080-112">進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。</span><span class="sxs-lookup"><span data-stu-id="08080-112">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="08080-113">您可以主動檢查您網路中的事件，以找出威脅指示器和實體。</span><span class="sxs-lookup"><span data-stu-id="08080-113">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="08080-114">對資料的靈活存取可對已知和潛在的威脅進行無限制的搜尋。</span><span class="sxs-lookup"><span data-stu-id="08080-114">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span> [<span data-ttu-id="08080-115">深入瞭解高級搜尋</span><span class="sxs-lookup"><span data-stu-id="08080-115">Learn more about advanced hunting</span></span>](advanced-hunting-overview.md)

### <a name="schema-tables"></a><span data-ttu-id="08080-116">結構描述表格</span><span class="sxs-lookup"><span data-stu-id="08080-116">Schema tables</span></span>

- <span data-ttu-id="08080-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) -安裝在裝置上的軟體清單，包括其版本資訊和支援終止狀態。</span><span class="sxs-lookup"><span data-stu-id="08080-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventory of software installed on devices, including their version information and end-of-support status.</span></span>

- <span data-ttu-id="08080-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) -裝置上的軟體弱點，以及解決每個弱點的可用安全性更新清單。</span><span class="sxs-lookup"><span data-stu-id="08080-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Software vulnerabilities found on devices and the list of available security updates that address each vulnerability.</span></span>

- <span data-ttu-id="08080-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) -公開披露之弱點的知識基底，包含是否公開使用漏洞。</span><span class="sxs-lookup"><span data-stu-id="08080-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available.</span></span>

- <span data-ttu-id="08080-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) -威脅及弱點管理評估事件，指出裝置上各種安全性設定的狀態。</span><span class="sxs-lookup"><span data-stu-id="08080-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Threat and vulnerability management assessment events, indicating the status of various security configurations on devices.</span></span>

- <span data-ttu-id="08080-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) -威脅 & 漏洞管理所使用之各種安全性設定的知識基底，以評估裝置;包含各種標準和基準的對應</span><span class="sxs-lookup"><span data-stu-id="08080-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a><span data-ttu-id="08080-122">檢查高嚴重性警示中包含哪些裝置</span><span class="sxs-lookup"><span data-stu-id="08080-122">Check which devices are involved in high severity alerts</span></span>

1. <span data-ttu-id="08080-123">從 Microsoft Defender 資訊安全中心的左導覽窗格移至 [**高級搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="08080-123">Go to **Advanced hunting** from the left-hand navigation pane of the Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="08080-124">向 TVM 高級搜尋架構以熟悉欄名。</span><span class="sxs-lookup"><span data-stu-id="08080-124">Scroll down to the TVM advanced hunting schemas to familiarize yourself with the column names.</span></span>

3. <span data-ttu-id="08080-125">輸入下列查詢：</span><span class="sxs-lookup"><span data-stu-id="08080-125">Enter the following queries:</span></span>

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a><span data-ttu-id="08080-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="08080-126">Related topics</span></span>

- [<span data-ttu-id="08080-127">威脅與弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="08080-127">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="08080-128">安全性建議</span><span class="sxs-lookup"><span data-stu-id="08080-128">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="08080-129">API</span><span class="sxs-lookup"><span data-stu-id="08080-129">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)
- [<span data-ttu-id="08080-130">設定威脅與弱點管理角色的資料存取權</span><span class="sxs-lookup"><span data-stu-id="08080-130">Configure data access for threat and vulnerability management roles</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [<span data-ttu-id="08080-131">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="08080-131">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [<span data-ttu-id="08080-132">所有高級搜尋表格</span><span class="sxs-lookup"><span data-stu-id="08080-132">All advanced hunting tables</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
