---
title: 以適當的設定擴充高級搜尋範圍
description: 檢查 Windows 裝置上的審計設定及其他設定，以協助確保您在高級搜尋中取得最全面的資料
keywords: 高級搜尋、事件、資料透視、實體、審核設定、使用者帳戶管理、安全性群組管理、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、Microsoft 365、Microsoft 威脅防護
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
ms.openlocfilehash: 9c1b9c1853d80d818d97084e2668d3b12b6da0e6
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503211"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>以適當的設定擴充高級搜尋範圍

適用於：****
- Microsoft 威脅防護

[[高級搜尋](advanced-hunting-overview.md)] 取決於來自各種來源的資料，包括您的裝置、Office 365 工作區、Azure AD 和 azure ATP。 若要盡可能取得最完整的資料，請務必在對應的資料來源中具備正確的設定。

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows 裝置上的高級安全性審核
開啟這些高級審核設定，以確保您取得裝置上活動的相關資料，包括本機帳戶管理、本機安全性群組管理及服務建立。

| 資料 | 描述 | 架構表格 | 如何設定 |
| --- | --- | --- | --- |
| Account management | 以各種值來捕獲的事件， `ActionType` 表示本地帳戶建立、刪除及其他與帳戶相關的活動 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -部署高級安全性審核原則：[審核使用者帳戶管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [深入瞭解高級安全性審核原則](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 安全性群組管理 | 以各種值來捕獲的事件 `ActionType` ，表示本機安全性群組的建立和其他本地群組管理活動 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -部署高級安全性審核原則：[審核安全性群組管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [深入瞭解高級安全性審核原則](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 服務安裝 | 以值捕獲的 `ActionType` 事件 `ServiceInstalled` ，表示已建立服務 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -部署高級安全性審核原則：[審核安全性系統擴充](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [深入瞭解高級安全性審核原則](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="azure-atp-sensor-on-the-domain-controller"></a>網域控制站上的 Azure ATP 感應器
如果您正在內部部署中執行 Active Directory，您必須在網域控制站上安裝 Azure ATP 感應器，以取得 Azure ATP 的資料。 安裝並正確設定後，此資料也會透過 Azure ATP 進入高級搜尋，並提供網路中身分識別資訊和事件的整體功能。 這項資料也會增強 Azure ATP 產生相關警示的能力，這些警示也是由高級搜尋所涵蓋。 

| 資料 | 描述 | 架構表格 | 如何設定 |
| --- | --- | --- | --- |
| 網域控制站 | 從內部部署 Active Directory 傳送至 Azure ATP 的資料，濃縮 identity 相關的資訊，例如帳戶詳細資料、登入活動和 Active Directory 查詢 | 多個資料表，包括[IdentityInfo](advanced-hunting-identityinfo-table.md)、 [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)及[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | [安裝 Azure ATP 感應器](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)|

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解結構描述](advanced-hunting-schema-tables.md)