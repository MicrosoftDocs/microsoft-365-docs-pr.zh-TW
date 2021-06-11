---
title: 取得即時回應結果
description: 瞭解如何根據其索引來取回特定即時回應命令結果。
keywords: api，graph api，支援的 api，上傳至文件庫
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879686"
---
#  <a name="get-live-response-results"></a>取得即時回應結果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 描述

依其索引來檢索特定即時回應命令結果。

## <a name="limitations"></a>限制

1.  此 API 的速率限制為每分鐘100個通話，每小時1500個通話。

## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [入門](apis-intro.md)。

| 許可權類型                    | 權限           | 許可權顯示名稱                   |
|------------------------------------|----------------------|-------------------------------------------|
| 應用程式                        | LiveResponse | 在特定電腦上執行 live 回應 |
| 委派 (工作或學校帳戶)  | LiveResponse | 在特定電腦上執行 live 回應 |

## <a name="http-request"></a>HTTP 要求

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>要求標頭

| 名稱      | 類型 | 描述               |
|---------------|----------|-------------------------------|
| 授權 | 字串   | 載荷 {token}。 此為必要動作。 |

## <a name="request-body"></a>要求正文

空白

## <a name="response"></a>回應

如果成功，這個方法會傳回200、Ok 回應碼，其物件會在 *value* 屬性中包含命令結果的連結。 此連結的有效期為30分鐘，應立即用來將套件下載至本機儲存區。 已到期的連結可以由另一個呼叫重新建立，而且不需要重新執行 live 回應。

*Runscript 成績單屬性：*

| 屬性	  | 描述                       |
|---------------|---------------------------------------|
| Name          | 已執行的腳本名稱                  |
| exit_code     | 已執行腳本的退出程式碼             |
| script_output | 已執行腳本標準輸出       |
| script_error  | 已執行的腳本標準錯誤輸出 |

## <a name="example"></a>範例

**請求**

以下是要求的範例。

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

**回應**

以下是回應的範例。

HTTP/1.1 200 確定

內容類型： application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

*檔內容：* 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a>相關主題

- [取得機器動作 API](get-machineaction-object.md)
- [取消機器動作](cancel-machine-action.md)
- [執行 live 回應](run-live-response.md) 
