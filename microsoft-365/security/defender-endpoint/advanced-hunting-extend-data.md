---
title: 以適當的設定擴充高級搜尋範圍
description: 檢查 Windows 裝置上的審計設定及其他設定，以協助確保您在高級搜尋中取得最全面的資料
keywords: 高級搜尋、事件、資料透視、實體、審核設定、使用者帳戶管理、安全性群組管理、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、mdatp、Microsoft Defender ATP、Microsoft Defender for Endpoint、Windows Defender、Windows Defender ATP、Windows Defender 高級威脅防護
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500621"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>以適當的設定擴充高級搜尋範圍

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[[高級搜尋](advanced-hunting-overview.md)] 取決於組織內的資料。 若要盡可能取得最完整的資料，請務必在對應的資料來源中具備正確的設定。

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows 裝置上的高級安全性審核

開啟這些高級審核設定，以確保您取得裝置上活動的相關資料，包括本機帳戶管理、本機安全性群組管理及服務建立。

資料 | 描述 | 架構表格 | 如何設定
-|-|-|-
Account management | 以各種值來捕獲的事件， `ActionType` 表示本地帳戶建立、刪除及其他與帳戶相關的活動 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -部署高級安全性審核原則： [審核使用者帳戶管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [深入瞭解高級安全性審核原則](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
安全性群組管理 | 以各種值來捕獲的事件 `ActionType` ，表示本機安全性群組的建立和其他本地群組管理活動 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -部署高級安全性審核原則： [審核安全性群組管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [深入瞭解高級安全性審核原則](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
服務安裝 | 以值捕獲的 `ActionType` 事件 `ServiceInstalled` ，表示已建立服務 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -部署高級安全性審核原則： [審核安全性系統擴充](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [深入瞭解高級安全性審核原則](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)

## <a name="related-topics"></a>相關主題

- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [自訂偵測概觀](overview-custom-detections.md)
