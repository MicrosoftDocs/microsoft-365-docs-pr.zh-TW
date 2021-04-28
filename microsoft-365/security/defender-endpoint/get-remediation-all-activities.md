---
title: 列出所有修復活動
description: 傳回所有修復活動的資訊。
keywords: api，修正，修正 api，get，修復工作，
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
ms.technology: mde
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061107"
---
# <a name="list-all-remediation-activities"></a>列出所有修復活動

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 描述

傳回所有修復活動的資訊。

[深入瞭解修復活動](tvm-remediation.md)。

**URL:** GET:/api/remediationTasks

**屬性** 詳細資料

屬性 (識別碼)  | 資料類型 | 描述 | 傳回值的範例
:---|:---|:---|:---
類別 | 字串 |  (軟體/安全性設定) 的修復活動類別 | 軟體
completerEmail | 字串 | 若某人已手動完成修復活動，此欄會包含他們的電子郵件 | Null
completerId | 字串 | 若某人已手動完成修復活動，此欄會包含其物件識別碼 | Null
completionMethod | 字串 | 如果所有裝置都已) 或「手動」或「手動」（由選取「標記為完成」）進行修補，便可完成「 (自動」的修復活動。 | 自動
createdOn | DateTime | 建立此修復活動的時間 | 2021-01-12T18：54： 11.5499478 Z
描述 | 字串 | 此修復活動的描述 | 將 Chrome 更新為更新的版本，以減輕影響裝置的1248已知弱點。
dueOn | DateTime | 到期日此修復活動的建立者設定 | 2021-01-13T00：00：00Z
fixedDevices | . | 已修復的裝置數目 | 第
id | 字串 | 此修復活動的識別碼 | 097d9735-5479-4899-b1b7-77398899df92
nameId | 字串 | 相關產品名稱 | 鉻
優先 | 字串 | 為此修復活動的建立者設定的優先順序 (High\Medium\Low)  | 高
Id | 字串 | 相關產品識別碼 | google-_-chrome
productivityImpactRemediationType | 字串 | 只會對沒有使用者影響的裝置要求一些設定變更。 此值表示「所有公開的裝置」或「只有沒有使用者影響的裝置」之間的選取範圍。 | AllExposedAssets
rbacGroupNames | 字串 | 相關的裝置群組名稱 | [Windows Servers]，"Windows 10"]
recommendedProgram | 字串 | 升級為的建議程式 | Null
recommendedVendor | 字串 | 升級為的建議供應商 | Null
recommendedVersion | 字串 | 更新/升級的建議版本 | Null
relatedComponent | 字串 | 此修復活動的相關元件 (類似安全性建議的相關元件)  | Google Chrome
requesterEmail | 字串 | 建立者電子郵件地址 | globaladmin@UserName.contoso.com
requesterId | 字串 | Creator 物件識別碼 | r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes | 字串 | 為此修復活動新增的建立者) 附注 (自由文字 | Null
Scid | 字串 | 相關安全性建議的 SCID | Null
地位 | 字串 | 修復活動狀態 (Active/已完成)  | 作用中
statusLastModifiedOn | DateTime | 更新狀態欄位的日期 | 2021-01-12T18：54： 11.5499487 Z
targetDevices | Long | 此修復適用的公開裝置數目 | 43
標題 | String | 此修復活動的標題 | 更新 Google Chrome
類型 | 字串 | 修正類型 | Update
vendorId | 字串 | 相關的供應商名稱 | 谷歌

## <a name="example"></a>範例

**要求** 範例

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

**回應** 範例

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a>另請參閱

- [修正方法和屬性](get-remediation-methods-properties.md)

- [依識別碼取得一個修復活動](get-remediation-one-activity.md)

- [列出某項修復活動的公開裝置](get-remediation-exposed-devices-activities.md)

- [風險威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)

- [組織中的薄弱環節](tvm-weaknesses.md)
