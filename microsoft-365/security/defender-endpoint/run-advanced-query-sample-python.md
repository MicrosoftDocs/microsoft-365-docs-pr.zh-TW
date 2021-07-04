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
ms.openlocfilehash: 7ee431c88430916fcba60266a3a3a5180d830c0d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289256"
---
# <a name="advanced-hunting-using-python"></a><span data-ttu-id="f0ba1-104">使用 Python 進階搜尋</span><span class="sxs-lookup"><span data-stu-id="f0ba1-104">Advanced Hunting using Python</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f0ba1-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f0ba1-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f0ba1-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="f0ba1-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f0ba1-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f0ba1-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f0ba1-108">使用 Python 執行高級查詢，請參閱 [Advanced 搜尋 API](run-advanced-query-api.md)。</span><span class="sxs-lookup"><span data-stu-id="f0ba1-108">Run advanced queries using Python, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="f0ba1-109">在本節中，我們會共用 Python 範例以取得權杖，並使用它來執行查詢。</span><span class="sxs-lookup"><span data-stu-id="f0ba1-109">In this section, we share Python samples to retrieve a token and use it to run a query.</span></span>

> <span data-ttu-id="f0ba1-110">必要條件 **：您** 必須先 [建立應用程式](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="f0ba1-110">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="get-token"></a><span data-ttu-id="f0ba1-111">取得 token</span><span class="sxs-lookup"><span data-stu-id="f0ba1-111">Get token</span></span>

- <span data-ttu-id="f0ba1-112">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f0ba1-112">Run the following commands:</span></span>

```python
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

<span data-ttu-id="f0ba1-113">那裡</span><span class="sxs-lookup"><span data-stu-id="f0ba1-113">where</span></span>

- <span data-ttu-id="f0ba1-114">tenantId：代表您要執行查詢 (的承租人識別碼，也就是在此租使用者的資料上執行查詢) </span><span class="sxs-lookup"><span data-stu-id="f0ba1-114">tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="f0ba1-115">appId： Azure AD 應用程式的識別碼 (應用程式必須具有 Microsoft Defender for Endpoint) 的「執行高級查詢」許可權。</span><span class="sxs-lookup"><span data-stu-id="f0ba1-115">appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Microsoft Defender for Endpoint)</span></span>
- <span data-ttu-id="f0ba1-116">appSecret：您的 Azure AD 應用程式的機密</span><span class="sxs-lookup"><span data-stu-id="f0ba1-116">appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="f0ba1-117">執行查詢</span><span class="sxs-lookup"><span data-stu-id="f0ba1-117">Run query</span></span>

 <span data-ttu-id="f0ba1-118">執行下列查詢：</span><span class="sxs-lookup"><span data-stu-id="f0ba1-118">Run the following query:</span></span>

```python
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

- <span data-ttu-id="f0ba1-119">架構包含查詢結果的架構</span><span class="sxs-lookup"><span data-stu-id="f0ba1-119">schema contains the schema of the results of your query</span></span>
- <span data-ttu-id="f0ba1-120">結果包含查詢的結果</span><span class="sxs-lookup"><span data-stu-id="f0ba1-120">results contain the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="f0ba1-121">複雜的查詢</span><span class="sxs-lookup"><span data-stu-id="f0ba1-121">Complex queries</span></span>

<span data-ttu-id="f0ba1-122">如果您想要執行複雜的查詢 (或多行查詢) ，請將查詢儲存在檔案中，而不是上述範例中的第一行，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f0ba1-122">If you want to run complex queries (or multiline queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```python
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a><span data-ttu-id="f0ba1-123">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="f0ba1-123">Work with query results</span></span>

<span data-ttu-id="f0ba1-124">您現在可以使用查詢結果。</span><span class="sxs-lookup"><span data-stu-id="f0ba1-124">You can now use the query results.</span></span>

<span data-ttu-id="f0ba1-125">若要迴圈查看結果，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f0ba1-125">To iterate over the results do the below:</span></span>

```python
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result
```

<span data-ttu-id="f0ba1-126">若要在 file 中以 CSV 格式輸出查詢結果 file1.csv 執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="f0ba1-126">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```python
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

<span data-ttu-id="f0ba1-127">若要在 file file1.js中輸出 JSON 格式的查詢結果，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f0ba1-127">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```python
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```

## <a name="related-topic"></a><span data-ttu-id="f0ba1-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="f0ba1-128">Related topic</span></span>

- [<span data-ttu-id="f0ba1-129">Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="f0ba1-129">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="f0ba1-130">進階搜捕 API</span><span class="sxs-lookup"><span data-stu-id="f0ba1-130">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="f0ba1-131">使用 PowerShell 進階搜尋</span><span class="sxs-lookup"><span data-stu-id="f0ba1-131">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
