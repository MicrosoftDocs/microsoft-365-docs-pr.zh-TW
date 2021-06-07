---
title: 使用 Python API 指南進行的高級搜尋
ms.reviewer: ''
description: 深入瞭解如何使用 Microsoft Defender for Endpoint API （使用 Python）進行查詢，包含範例。
keywords: api、支援的 api、高級搜尋、查詢
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 17ad28121935adfc958629f7999311c11a8d784e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771438"
---
# <a name="advanced-hunting-using-python"></a>使用 Python 進階搜尋

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

使用 Python 執行高級查詢，請參閱 [Advanced 搜尋 API](run-advanced-query-api.md)。

在本節中，我們會共用 Python 範例以取得權杖，並使用它來執行查詢。

>必要條件 **：您** 必須先 [建立應用程式](apis-intro.md)。

## <a name="get-token"></a>取得 token

- 執行下列命令：

```

import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.microsoftonline.com/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]

```

那裡
- tenantId：代表您要執行查詢 (的承租人識別碼，也就是在此租使用者的資料上執行查詢) 
- appId： Azure AD 應用程式的識別碼 (應用程式必須具有 Microsoft Defender for Endpoint) 的「執行高級查詢」許可權。
- appSecret：您的 Azure AD 應用程式的機密

## <a name="run-query"></a>執行查詢

 執行下列查詢：

```
query = 'RegistryEvents | limit 10' # Paste your own query here

url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
headers = { 
    'Content-Type' : 'application/json',
    'Accept' : 'application/json',
    'Authorization' : "Bearer " + aadToken
}

data = json.dumps({ 'Query' : query }).encode("utf-8")

req = urllib.request.Request(url, data, headers)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
schema = jsonResponse["Schema"]
results = jsonResponse["Results"]

```

- 架構包含查詢結果的架構
- 結果包含查詢的結果

### <a name="complex-queries"></a>複雜的查詢

如果您想要執行複雜查詢 (或 multilines 查詢) ，請將查詢儲存在檔案中，而不是上述範例中的第一行，請執行下列命令：

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>使用查詢結果工作

您現在可以使用查詢結果。

若要迴圈查看結果，請執行下列動作：

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


若要在 file 中以 CSV 格式輸出查詢結果 file1.csv 執行下列作業：

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

若要在 file file1.js中輸出 JSON 格式的查詢結果，請執行下列操作：

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a>相關主題
- [Microsoft Defender for Endpoint APIs](apis-intro.md)
- [進階搜捕 API](run-advanced-query-api.md)
- [使用 PowerShell 進階搜尋](run-advanced-query-sample-powershell.md)
