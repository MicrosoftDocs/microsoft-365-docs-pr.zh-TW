---
title: PowerShell API 基礎知識的高級搜尋
ms.reviewer: ''
description: 深入瞭解使用 PowerShell 查詢 Microsoft Defender for Endpoint API 的基礎知識。
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
ms.openlocfilehash: 9192662b8d4ed23a5903dddb555f07bf182ab17f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771498"
---
# <a name="advanced-hunting-using-powershell"></a>使用 PowerShell 進階搜尋

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

使用 PowerShell 執行高級查詢，請參閱 [Advanced 搜尋 API](run-advanced-query-api.md)。

在本節中，我們會分享 PowerShell 範例，以檢索權杖，並使用它來執行查詢。

## <a name="before-you-begin"></a>開始之前
您必須先 [建立應用程式](apis-intro.md)。

## <a name="preparation-instructions"></a>準備指示

- 開啟 PowerShell 視窗。
- 如果您的原則不允許您執行 PowerShell 命令，您可以執行下列命令：
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

>如需詳細資訊，請參閱 [PowerShell 檔](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>取得 token

- 執行下列命令：

```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$body = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$response = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $body -ErrorAction Stop
$aadToken = $response.access_token
```

那裡
- $tenantId：代表您要執行查詢的承租人識別碼 (也就是說，將在此租使用者的資料上執行查詢) 
- $appId： Azure AD 應用程式的識別碼 (應用程式必須具有 Endpoint for Endpoint 的「執行高級查詢」許可權) 
- $appSecret： Azure AD 應用程式的機密

## <a name="run-query"></a>執行查詢

執行下列查詢：

```
$query = 'RegistryEvents | limit 10' # Paste your own query here

$url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$body = ConvertTo-Json -InputObject @{ 'Query' = $query }
$webResponse = Invoke-WebRequest -Method Post -Uri $url -Headers $headers -Body $body -ErrorAction Stop
$response =  $webResponse | ConvertFrom-Json
$results = $response.Results
$schema = $response.Schema
```

- 包含查詢結果的 $results
- $schema 包含查詢結果的架構

### <a name="complex-queries"></a>複雜的查詢

如果您想要執行複雜查詢 (或 multilines 查詢) ，請將查詢儲存在檔案中，而不是上述範例中的第一行，請執行下列命令：

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>使用查詢結果工作

您現在可以使用查詢結果。

若要在 file 中以 CSV 格式輸出查詢結果 file1.csv 執行下列作業：

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

若要在 file file1.js中輸出 JSON 格式的查詢結果，請執行下列操作：

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>相關主題
- [Microsoft Defender for Endpoint APIs](apis-intro.md)
- [進階搜捕 API](run-advanced-query-api.md)
- [使用 Python 進階搜尋](run-advanced-query-sample-python.md)
