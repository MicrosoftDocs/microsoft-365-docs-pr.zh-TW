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
ms.technology: mde
ms.openlocfilehash: 20c63daaf61b85f35aaceccb540b6d50824c801d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198668"
---
# <a name="advanced-hunting-using-powershell"></a><span data-ttu-id="b085c-104">使用 PowerShell 的高級搜尋</span><span class="sxs-lookup"><span data-stu-id="b085c-104">Advanced Hunting using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b085c-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b085c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="b085c-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b085c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b085c-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b085c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b085c-108">使用 PowerShell 執行高級查詢，請參閱 [Advanced 搜尋 API](run-advanced-query-api.md)。</span><span class="sxs-lookup"><span data-stu-id="b085c-108">Run advanced queries using PowerShell, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="b085c-109">在本節中，我們會分享 PowerShell 範例，以檢索權杖，並使用它來執行查詢。</span><span class="sxs-lookup"><span data-stu-id="b085c-109">In this section, we share PowerShell samples to retrieve a token and use it to run a query.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b085c-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="b085c-110">Before you begin</span></span>
<span data-ttu-id="b085c-111">您必須先 [建立應用程式](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="b085c-111">You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="b085c-112">準備指示</span><span class="sxs-lookup"><span data-stu-id="b085c-112">Preparation instructions</span></span>

- <span data-ttu-id="b085c-113">開啟 PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="b085c-113">Open a PowerShell window.</span></span>
- <span data-ttu-id="b085c-114">如果您的原則不允許您執行 PowerShell 命令，您可以執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b085c-114">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

><span data-ttu-id="b085c-115">如需詳細資訊，請參閱 [PowerShell 檔](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="b085c-115">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="b085c-116">取得 token</span><span class="sxs-lookup"><span data-stu-id="b085c-116">Get token</span></span>

- <span data-ttu-id="b085c-117">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b085c-117">Run the following:</span></span>

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

<span data-ttu-id="b085c-118">那裡</span><span class="sxs-lookup"><span data-stu-id="b085c-118">where</span></span>
- <span data-ttu-id="b085c-119">$tenantId：代表您要執行查詢的承租人識別碼 (也就是說，將在此租使用者的資料上執行查詢) </span><span class="sxs-lookup"><span data-stu-id="b085c-119">$tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="b085c-120">$appId： Azure AD 應用程式的識別碼 (應用程式必須具有 Endpoint for Endpoint 的「執行高級查詢」許可權) </span><span class="sxs-lookup"><span data-stu-id="b085c-120">$appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="b085c-121">$appSecret： Azure AD 應用程式的機密</span><span class="sxs-lookup"><span data-stu-id="b085c-121">$appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="b085c-122">執行查詢</span><span class="sxs-lookup"><span data-stu-id="b085c-122">Run query</span></span>

<span data-ttu-id="b085c-123">執行下列查詢：</span><span class="sxs-lookup"><span data-stu-id="b085c-123">Run the following query:</span></span>

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

- <span data-ttu-id="b085c-124">包含查詢結果的 $results</span><span class="sxs-lookup"><span data-stu-id="b085c-124">$results contain the results of your query</span></span>
- <span data-ttu-id="b085c-125">$schema 包含查詢結果的架構</span><span class="sxs-lookup"><span data-stu-id="b085c-125">$schema contains the schema of the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="b085c-126">複雜的查詢</span><span class="sxs-lookup"><span data-stu-id="b085c-126">Complex queries</span></span>

<span data-ttu-id="b085c-127">如果您想要執行複雜查詢 (或 multilines 查詢) ，請將查詢儲存在檔案中，而不是上述範例中的第一行，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b085c-127">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a><span data-ttu-id="b085c-128">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="b085c-128">Work with query results</span></span>

<span data-ttu-id="b085c-129">您現在可以使用查詢結果。</span><span class="sxs-lookup"><span data-stu-id="b085c-129">You can now use the query results.</span></span>

<span data-ttu-id="b085c-130">若要在 file 中以 CSV 格式輸出查詢結果 file1.csv 執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="b085c-130">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

<span data-ttu-id="b085c-131">若要在 file file1.js中輸出 JSON 格式的查詢結果，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b085c-131">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a><span data-ttu-id="b085c-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="b085c-132">Related topic</span></span>
- [<span data-ttu-id="b085c-133">Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="b085c-133">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="b085c-134">進階搜捕 API</span><span class="sxs-lookup"><span data-stu-id="b085c-134">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="b085c-135">使用 Python 的高級搜尋</span><span class="sxs-lookup"><span data-stu-id="b085c-135">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
