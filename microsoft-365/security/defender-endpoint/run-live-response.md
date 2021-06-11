---
title: 在裝置上執行 live 回應命令
description: 瞭解如何在裝置上執行 live response 命令順序。
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
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879653"
---
#  <a name="run-live-response-commands-on-a-device"></a>在裝置上執行 live 回應命令

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 描述

在裝置上執行 live response 命令順序

## <a name="limitations"></a>限制

1.  此 API 的速率限制是每分鐘10個通話 (其他要求會以 HTTP 429) 回應。

2.  25個同時執行的會話 (要求超過節流限制，將會收到「429-太多要求」回應) 。

3.  如果機器無法使用，會話將會排隊等候最多3天。

4.  10分鐘後 RunScript 命令逾時。

5.  當 live response 命令失敗時，將不會執行所有遵循的動作。

## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [入門](apis-intro.md)。

| 許可權類型                    | 權限           | 許可權顯示名稱                   |
|------------------------------------|----------------------|-------------------------------------------|
| 應用程式                        | LiveResponse | 在特定電腦上執行 live 回應 |
| 委派 (工作或學校帳戶)  | LiveResponse | 在特定電腦上執行 live 回應 |

## <a name="http-request"></a>HTTP 要求

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>要求標頭

| 名稱      | 類型 | 描述                 |
|---------------|----------|---------------------------------|
| 授權 | 字串   | 承載\<token>\. 此為必要動作。   |
| Content-Type  | string   | application/json。 此為必要動作。 |

## <a name="request-body"></a>要求正文

| 參數 | 類型 | 描述                                                        |
|---------------|----------|------------------------------------------------------------------------|
| 留言       | 字串   | 與動作相關聯的批註。                                 |
| 命令      | 陣列    | 要執行的命令。 允許的值為 PutFile、RunScript、GetFile。 |

命令：

| 命令類型 | 參數                                                                          | 描述                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| PutFile      | 索引鍵： FileName  <br><br>  值：\<file name\>                                                                          | 將檔案從文件庫放入裝置。 檔案儲存在工作資料夾中，而且會在預設重新開機裝置時刪除。
| RunScript    | 機碼： ScriptName<br>值：\<Script from library\> <br><br> Key： Args  <br> 值：\<Script arguments\>                          | 在裝置上的文件庫中執行腳本。    <br><br>  Args 參數會傳遞給您的腳本。 <br><br> 10分鐘後超時。     
| GetFile      | Key： Path <br> 值：\<File path\>                                                        | 從裝置收集檔案。 附注：路徑中的反斜線必須進行轉義。                                                                      |

## <a name="response"></a>回應

-   如果成功，這個方法會傳回200，[確定]。
    Action 實體。 如果找不到具有指定識別碼的電腦-找不到404。

## <a name="example"></a>範例

**請求**

以下是要求的範例。

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
**Json**

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

**回應**

以下是回應的範例。

```HTTP
HTTP/1.1 200 Ok
```

內容類型： application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a>相關主題
- [取得機器動作 API](get-machineaction-object.md)
- [取得即時回應結果](get-live-response-result.md)
- [取消機器動作](cancel-machine-action.md)
