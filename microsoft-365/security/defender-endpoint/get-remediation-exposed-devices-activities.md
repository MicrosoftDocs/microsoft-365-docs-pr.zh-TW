---
title: 列出一個補救活動的公開裝置
description: 傳回所指定修復程式工作的公開裝置資訊。
keywords: api，修正，修正 api，get，修正工作，修正公開裝置
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
ms.openlocfilehash: 9b10659f76e5b05bea11f5c6c55ca7c2a34a2db5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772158"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a>列出一個補救活動的公開裝置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 描述

傳回所指定修復程式工作的公開裝置資訊。

[深入瞭解修復活動](tvm-remediation.md)。

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a>列出與修復工作相關聯的公開裝置 (id) 

**URL:** /Api/remediationTasks/ \{ id \} /machineReferences GET:

## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)

許可權類型 | 權限 | 許可權顯示名稱
:---|:---|:---
應用程式 | RemediationTask Read。 All | \'讀取威脅及弱點管理弱點資訊\'
委派 (工作或學校帳戶)  | RemediationTask 讀取。 | \'讀取威脅及弱點管理弱點資訊\'

## <a name="properties-details"></a>屬性詳細資料

屬性 (識別碼)  | 資料類型 | 描述 | 範例
:---|:---|:---|:---
id | 字串 | 裝置識別碼 | w2957837fwda8w9ae7f023dba081059dw8d94503
computerDnsName | 字串 | 裝置名稱 | SRV2012R2Foo-UserNameVldNet
osPlatform | 字串 | 裝置作業系統 | WindowsServer2012R2
rbacGroupName | 字串 | 此裝置相關聯的裝置群組名稱 | 伺服器

## <a name="example"></a>範例

### <a name="request-example"></a>要求範例

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a>回應範例

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        }
]
}
```

## <a name="see-also"></a>請參閱

- [修正方法和屬性](get-remediation-methods-properties.md)

- [根據識別碼取得一個補救活動](get-remediation-one-activity.md)

- [列出所有補救活動](get-remediation-all-activities.md)

- [風險威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)

- [組織中的薄弱環節](tvm-weaknesses.md)
