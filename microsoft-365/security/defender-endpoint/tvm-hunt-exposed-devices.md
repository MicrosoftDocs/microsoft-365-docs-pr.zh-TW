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
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>搜尋公開的裝置-威脅與弱點管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威脅及弱點管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>使用高級搜尋來尋找包含弱點的裝置

進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。 您可以主動檢查您網路中的事件，以找出威脅指示器和實體。 對資料的靈活存取可對已知和潛在的威脅進行無限制的搜尋。 [深入瞭解高級搜尋](advanced-hunting-overview.md)

### <a name="schema-tables"></a>結構描述表格

- [DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) -安裝在裝置上的軟體清單，包括其版本資訊和支援終止狀態。

- [DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) -裝置上的軟體弱點，以及解決每個弱點的可用安全性更新清單。

- [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) -公開披露之弱點的知識基底，包含是否公開使用漏洞。

- [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) -威脅及弱點管理評估事件，指出裝置上各種安全性設定的狀態。

- [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) -威脅 & 漏洞管理所使用之各種安全性設定的知識基底，以評估裝置;包含各種標準和基準的對應

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>檢查高嚴重性警示中包含哪些裝置

1. 從 Microsoft Defender 資訊安全中心的左導覽窗格移至 [**高級搜尋**]。

2. 向 TVM 高級搜尋架構以熟悉欄名。

3. 輸入下列查詢：

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

## <a name="related-topics"></a>相關主題

- [威脅與弱點管理概述](next-gen-threat-and-vuln-mgt.md)
- [安全性建議](tvm-security-recommendation.md)
- [API](next-gen-threat-and-vuln-mgt.md#apis)
- [設定威脅與弱點管理角色的資料存取權](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [進階搜捕概觀](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [所有高級搜尋表格](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
