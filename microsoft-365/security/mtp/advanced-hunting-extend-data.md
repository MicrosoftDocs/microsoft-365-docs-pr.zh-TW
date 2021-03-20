---
title: 以適當的設定擴充高級搜尋範圍
description: 檢查 Windows 裝置上的審計設定及其他設定，以協助確保您在高級搜尋中取得最全面的資料
keywords: 高級搜尋、事件、資料透視、實體、審核設定、使用者帳戶管理、安全性群組管理、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、Microsoft 365、Microsoft 威脅防護
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
ms.openlocfilehash: 856f61aac8e7297f1b5dfb3aadc46da06cb16289
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907213"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>以適當的設定擴充高級搜尋範圍

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

[[高級搜尋](advanced-hunting-overview.md)] 取決於來自各種來源的資料，包括您的裝置、Office 365 工作區、Azure AD 及 Microsoft Defender 身分識別。 若要盡可能取得最完整的資料，請務必在對應的資料來源中具備正確的設定。

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows 裝置上的高級安全性審核
開啟這些高級審核設定，以確保您取得裝置上活動的相關資料，包括本機帳戶管理、本機安全性群組管理及服務建立。

| 資料 | 描述 | 架構表格 | 如何設定 |
| --- | --- | --- | --- |
| Account management | 以各種值來捕獲的事件， `ActionType` 表示本地帳戶建立、刪除及其他與帳戶相關的活動 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -部署高級安全性審核原則： [審核使用者帳戶管理](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [深入瞭解高級安全性審核原則](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 安全性群組管理 | 以各種值來捕獲的事件 `ActionType` ，表示本機安全性群組的建立和其他本地群組管理活動 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -部署高級安全性審核原則： [審核安全性群組管理](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [深入瞭解高級安全性審核原則](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 服務安裝 | 以值捕獲的 `ActionType` 事件 `ServiceInstalled` ，表示已建立服務 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -部署高級安全性審核原則： [審核安全性系統擴充](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [深入瞭解高級安全性審核原則](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>網域控制站上的身分識別感應器的 Microsoft Defender
如果您要在內部部署中執行 Active Directory，您必須在網域控制站上安裝 Microsoft Defender for Identity 感應器，以取得 Microsoft Defender 身分識別的資料。 安裝並正確設定後，此資料也會進入透過 Microsoft Defender 身分識別的高級搜尋，並提供網路中身分識別資訊和事件的整體功能。 這項資料也會增強 Microsoft Defender 身分識別產生相關警示的功能，這些警示也會在高級搜尋中涵蓋。 

| 資料 | 描述 | 架構表格 | 如何設定 |
| --- | --- | --- | --- |
| 網域控制站 | 從內部部署 Active Directory 傳送至 Microsoft Defender 以進行身分識別的資料，濃縮身分識別相關的資訊，例如帳戶詳細資料、登入活動和 Active Directory 查詢 | 多個資料表，包括 [IdentityInfo](advanced-hunting-identityinfo-table.md)、 [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)及 [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [安裝 Microsoft Defender 的身分識別感應器](/azure-advanced-threat-protection/install-atp-step4)<br>- [開啟相關的 Windows 事件](/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解結構描述](advanced-hunting-schema-tables.md)