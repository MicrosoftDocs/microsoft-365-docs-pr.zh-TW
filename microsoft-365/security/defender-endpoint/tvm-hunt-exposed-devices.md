---
title: 尋找公開的裝置
description: 瞭解如何使用威脅和弱點管理來協助安全性系統管理員、IT 系統管理員和 SecOps 共同作業。
keywords: mdatp-tvm 案例、mdatp、tvm、tvm 案例、減少威脅 & 弱點嚴重性、減少威脅和弱點、改善安全性設定、增加 Microsoft 安全分數的裝置、增加威脅 & 弱點 Microsoft 安全評分
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9af7464d9cae06dc53abb019aa0b189d6e72e749
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056681"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>尋找公開的裝置-威脅和弱點管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威脅與弱點管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>使用高級搜尋來尋找包含弱點的裝置

進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。 您可以主動檢查您網路中的事件，以找出威脅指示器和實體。 對資料的靈活存取可對已知和潛在的威脅進行無限制的搜尋。 [深入瞭解高級搜尋](advanced-hunting-overview.md)

### <a name="schema-tables"></a>結構描述表格

- [DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) -安裝于裝置上的軟體清單，包括其版本資訊和支援終止狀態

- [DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) -在裝置上找到的軟體弱點，以及解決每個弱點的可用安全性更新清單。

- [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) -公開披露之弱點的知識基底，包含是否公開利用程式碼

- [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) -威脅和弱點管理評估事件，指出裝置上的各種安全性設定狀態

- [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) -威脅 & 漏洞管理所使用之各種安全性設定的知識基底，以評估裝置;包含各種標準和基準的對應

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>檢查高嚴重性警示中包含哪些裝置

1. 移至 Microsoft Defender Security Center 左側的功能窗格中的「 **高級搜尋** 」。

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

- [威脅和弱點管理概述](next-gen-threat-and-vuln-mgt.md)
- [安全性建議](tvm-security-recommendation.md)
- [API](next-gen-threat-and-vuln-mgt.md#apis)
- [設定威脅和弱點管理角色的資料存取權](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [進階搜捕概觀](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [所有高級搜尋表格](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
