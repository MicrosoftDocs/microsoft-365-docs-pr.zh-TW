---
title: machineAction 資源類型
description: 深入瞭解 Microsoft Defender for Endpoint 中的 MachineAction 資源類型的方法和屬性。
keywords: api、支援的 api、get、machineaction、最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a3b017a9a05964c15411668787b035f1052c68cf
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878277"
---
# <a name="machineaction-resource-type"></a>MachineAction 資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- 如需詳細資訊，請參閱 [回應動作](respond-machine-alerts.md)。 

| 方法                                                            | 傳回類型                        | 描述                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [清單 MachineActions](get-machineactions-collection.md)           | [電腦動作](machineaction.md) | 列出 [電腦動作](machineaction.md) 實體。           |
| [取得 MachineAction](get-machineaction-object.md)                  | [電腦動作](machineaction.md) | 取得單一 [機器動作](machineaction.md) 實體。     |
| [收集調查套件](collect-investigation-package.md) | [電腦動作](machineaction.md) | 從 [機器](machine.md)收集調查套件。 |
| [取得調查套件 SAS URI](get-package-sas-uri.md)       | [電腦動作](machineaction.md) | 取得下載調查套件的 URI。          |
| [隔離電腦](isolate-machine.md)                             | [電腦動作](machineaction.md) | 從網路隔離 [電腦](machine.md) 。                 |
| [將電腦從隔離中釋出](unisolate-machine.md)            | [電腦動作](machineaction.md) | 獨立發行 [電腦](machine.md) 。               |
| [限制應用程式執行](restrict-code-execution.md)              | [電腦動作](machineaction.md) | 限制應用程式的執行。                             |
| [移除應用程式限制](unrestrict-code-execution.md)            | [電腦動作](machineaction.md) | 移除應用程式執行限制。                   |
| [執行防毒掃描](run-av-scan.md)                              | [電腦動作](machineaction.md) | 在適用) 時，使用 Windows Defender (執行 AV 掃描。    |
| [下機](offboard-machine-api.md)                       | [電腦動作](machineaction.md) | 從 Microsoft Defender for Endpoint 下架 [電腦](machine.md) 。 |
| [停止並隔離檔案](stop-and-quarantine-file.md)           | [電腦動作](machineaction.md) | 停止執行機器上的檔案，並將它刪除。        |
| [執行 live 回應](run-live-response.md)                     | [電腦動作](machineaction.md)  | 在裝置上執行 live response 命令順序                       |
| [取得即時回應結果](get-live-response-result.md) | URL 實體      | 依其索引，檢索特定即時回應命令結果下載連結。 |
|[取消機器動作](cancel-machine-action.md)                                | [電腦動作](machineaction.md)  | 取消使用中的機器動作。                                            |

<br>

## <a name="properties"></a>屬性

| 屬性	            | 類型           | 描述                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 識別碼                  | Guid           | [機器動作](machineaction.md)實體的身分識別。                                                                                                                                                     |
| 類型                | Enum           | 動作的類型。 可能的值為： "RunAntiVirusScan"、"下架"、"CollectInvestigationPackage"、"隔離"、"Unisolate"、"StopAndQuarantineFile"、"RestrictCodeExecution" 和 "UnrestrictCodeExecution" |
| 範圍               | 字串         | 動作的範圍。 "Full" 或 "選擇性" 進行隔離，"Quick" 或 "Full" 表示防病毒掃描。                                                                                                   |
| 請求           | 字串         | 執行動作之人員的身分識別。                                                                                                                                                               |
| requestorComment    | 字串         | 發出動作時所撰寫的批註。                                                                                                                                                              |
| 地位              | Enum           | 命令的目前狀態。 可能的值為：「擱置」、「InProgress」、「成功」、「失敗」、「超時」和「取消」。                                                                                 |
| machineId           | 字串         | 執行動作所在之 [機器](machine.md) 的識別碼。                                                                                                                                              |
| machineId           | 字串         | 執行動作所在之 [機器](machine.md) 的名稱。                                                                                                                                            |
| creationDateTimeUtc | DateTimeOffset | 動作的建立日期和時間。                                                                                                                                                                 |
| lastUpdateTimeUtc   | DateTimeOffset | 動作狀態更新的最後日期和時間。                                                                                                                                                     |
| relatedFileInfo     | 類別          | 包含兩個屬性。 字串 ```fileIdentifier``` ，列舉的 ```fileIdentifierType``` 可能值為 "Sha1"，"Sha256"，"Md5"。                                                                         |



## <a name="json-representation"></a>Json 標記法

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
