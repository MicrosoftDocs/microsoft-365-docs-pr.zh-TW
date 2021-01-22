---
title: 以正確的設定擴充進位搜尋範圍
description: 檢查 Windows 裝置上的稽核設定及其他設定，以確保您取得最完整的進一次搜尋資料
keywords: 進進搜尋、事件、樞紐、實體、稽核設定、使用者帳戶管理、安全性群組管理、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、Microsoft 365、Microsoft 威脅防護
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
ms.openlocfilehash: 9773658bea752175fe7988b9322fb26a9d5b7f05
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929583"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>以正確的設定擴充進位搜尋範圍

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

[進位](advanced-hunting-overview.md) 搜尋仰賴來自各種來源的資料，包括您的裝置、您的 Office 365 工作區、Azure AD 和 Microsoft Defender 的身分識別。 若要盡可能取得最完整的資料，請確保您在對應資料來源中擁有正確的設定。

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows 裝置上的進位安全性稽核
開啟這些進位稽核設定，以確保您取得裝置上的活動資料，包括本地帳戶管理、本地安全性群組管理，以及服務建立。

| 資料 | 描述 | 架構資料表 | 如何設定 |
| --- | --- | --- | --- |
| Account management | 事件會以各種 `ActionType` 值捕獲，指出建立、刪除和其他帳戶相關活動 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 部署進一步的安全性稽核政策 [：稽核使用者帳戶管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [瞭解進位安全性稽核政策](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 安全性群組管理 | 事件會以各種值來取用，指出建立本地 `ActionType` 安全性群組和其他本機群組管理活動 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 部署進一步的安全性稽核政策 [：稽核安全性群組管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [瞭解進位安全性稽核政策](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 服務安裝 | 使用值所取 `ActionType` 的事件 `ServiceInstalled` ，表示已建立服務 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 部署進一步的安全性稽核政策 [：稽核安全性系統擴充功能](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [瞭解進位安全性稽核政策](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>網域控制站上的 Microsoft Defender for Identity 感應器
如果您執行內部部署 Active Directory，您必須在網域控制站上安裝 Microsoft Defender for Identity 感應器，以取得 Microsoft Defender for Identity 的資料。 安裝並正確安裝之後，這項資料也會透過 Microsoft Defender for Identity 進一步搜尋，並提供您網路中身分識別資訊和事件的更深入資訊。 此資料也強化了 Microsoft Defender for Identity 產生進一步搜尋所涵蓋之相關警示的能力。 

| 資料 | 描述 | 架構資料表 | 如何設定 |
| --- | --- | --- | --- |
| 網域控制站 | 內部部署 Active Directory 的資料會針對身分識別而寄至 Microsoft Defender，豐富身分識別相關資訊，例如帳戶詳細資料、登入活動和 Active Directory 查詢 | 多個資料表，包括[IdentityInfo、IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)和[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) [](advanced-hunting-identityinfo-table.md)  | - [安裝 Microsoft Defender for Identity 感應器](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [開啟相關的 Windows 活動](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
