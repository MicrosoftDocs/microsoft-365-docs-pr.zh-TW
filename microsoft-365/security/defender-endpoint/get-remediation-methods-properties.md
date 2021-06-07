---
title: 補救活動方法和屬性
description: API 回應包含您租使用者中建立弱點管理修復活動 & 威脅。 您可以要求所有修復活動、只有一個修復活動，或選取的修復工作的公開裝置相關資訊。
keywords: api，修正，修正 api，get，修正工作，修正方法，修正屬性
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 67009961ecc3755b5af21b2e773bc817ea46bec0
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769230"
---
# <a name="remediation-activity-methods-and-properties"></a>補救活動方法和屬性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

API 回應包含 [](next-gen-threat-and-vuln-mgt.md)   已在您的租使用者中建立弱點管理修復活動的威脅 &。  

## <a name="methods"></a>方法

方法	 | 資料類型 | 描述
:---|:---|:---
[列出所有補救活動](get-remediation-all-activities.md) | 調查集合 | 傳回所有修復活動的資訊。
[列出一個補救活動的公開裝置](get-remediation-exposed-devices-activities.md) | 調查實體 | 傳回所指定修復活動的公開裝置資訊。
[根據識別碼取得一個補救活動](get-remediation-one-activity.md) | 調查實體 | 傳回指定之修復活動的資訊。

深入瞭解 [修復活動](tvm-remediation.md)。

## <a name="properties"></a>屬性

屬性識別碼 | 資料類型 | 描述
:---|:---|:---
類別 | 字串 |  (軟體/安全性設定) 的修復活動類別
completerEmail | 字串 | 若某人已手動完成修復活動，此欄會包含他們的電子郵件
completerId | 字串 | 若某人已手動完成修復活動，此欄會包含其物件識別碼
completionMethod | 字串 | 若所有裝置都已) 或「手動」或「手動」（由選取「標記為完成」）進行修補，便可執行「 (自動」的修復活動。
createdOn | DateTime | 建立此修復活動的時間
描述 | 字串 | 此修復活動的描述
dueOn | DateTime | 到期日此修復活動的建立者設定
fixedDevices |  | 已修復的裝置數目
id | 字串 | 此修復活動的識別碼
nameId | 字串 | 相關產品名稱
優先 | 字串 | 為此修復活動的建立者設定的優先順序 (High\Medium\Low) 
Id | 字串 | 相關產品識別碼
productivityImpactRemediationType | 字串 | 只會對沒有使用者影響的裝置要求一些設定變更。 此值表示「所有公開的裝置」或「只有沒有使用者影響的裝置」之間的選取範圍。
rbacGroupNames | 字串 | 相關的裝置群組名稱
recommendedProgram | 字串 | 升級為的建議程式
recommendedVendor | 字串 | 升級為的建議供應商
recommendedVersion | 字串 | 更新/升級的建議版本
relatedComponent | 字串 | 此修復活動的相關元件 (類似安全性建議的相關元件) 
requesterEmail | 字串 | 建立者電子郵件地址
requesterId | 字串 | Creator 物件識別碼
requesterNotes | 字串 | 為此修復活動新增的建立者) 附注 (自由文字
Scid | 字串 | 相關安全性建議的 SCID
地位 | 字串 | 修復活動狀態 (Active/已完成) 
statusLastModifiedOn | DateTime | 更新狀態欄位的日期
targetDevices | Long | 此修復適用的公開裝置數目
標題 | String | 此修復活動的標題
類型 | 字串 | 修正類型
vendorId | 字串 | 相關的供應商名稱

## <a name="see-also"></a>請參閱

- [根據識別碼取得一個補救活動](get-remediation-one-activity.md)

- [列出所有補救活動](get-remediation-all-activities.md)

- [列出一個補救活動的公開裝置](get-remediation-exposed-devices-activities.md)

- [風險威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)

- [組織中的薄弱環節](tvm-weaknesses.md)
