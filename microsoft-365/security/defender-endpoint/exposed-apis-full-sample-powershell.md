---
title: 使用 PowerShell API 指南的高級搜尋
ms.reviewer: ''
description: 使用這些程式碼範例，查詢多個 Microsoft Defender for Endpoint APIs。
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
ms.date: 09/24/2018
ms.technology: mde
ms.openlocfilehash: 9913d1b0b0d5d0462fdee0b9c576a590bd3ddbc9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198317"
---
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a><span data-ttu-id="a779e-104">Microsoft Defender for Endpoint APIs 使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a779e-104">Microsoft Defender for Endpoint APIs using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a779e-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a779e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="a779e-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a779e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a779e-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a779e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

><span data-ttu-id="a779e-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a779e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a779e-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a779e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="a779e-110">使用 Microsoft Defender for Endpoint 中的多個 APIs 的完整案例。</span><span class="sxs-lookup"><span data-stu-id="a779e-110">Full scenario using multiple APIs from Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="a779e-111">在本節中，我們會分享 PowerShell 範例，以</span><span class="sxs-lookup"><span data-stu-id="a779e-111">In this section, we share PowerShell samples to</span></span> 
- <span data-ttu-id="a779e-112">取得 token</span><span class="sxs-lookup"><span data-stu-id="a779e-112">Retrieve a token</span></span> 
- <span data-ttu-id="a779e-113">使用 token 在 Microsoft Defender for Endpoint 中檢索最新的警示</span><span class="sxs-lookup"><span data-stu-id="a779e-113">Use token to retrieve the latest alerts in Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="a779e-114">針對每個警示，如果警示有中低或高優先順序且仍在進行中，請檢查裝置連線至可疑 URL 的次數。</span><span class="sxs-lookup"><span data-stu-id="a779e-114">For each alert, if the alert has medium or high priority and is still in progress, check how many times the device has connected to suspicious URL.</span></span>

<span data-ttu-id="a779e-115">必要條件 **：您** 必須先 [建立應用程式](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="a779e-115">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="a779e-116">準備指示</span><span class="sxs-lookup"><span data-stu-id="a779e-116">Preparation instructions</span></span>

- <span data-ttu-id="a779e-117">開啟 PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="a779e-117">Open a PowerShell window.</span></span>
- <span data-ttu-id="a779e-118">如果您的原則不允許您執行 PowerShell 命令，您可以執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a779e-118">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

<span data-ttu-id="a779e-119">如需詳細資訊，請參閱 [PowerShell 檔](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="a779e-119">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="a779e-120">取得 token</span><span class="sxs-lookup"><span data-stu-id="a779e-120">Get token</span></span>

<span data-ttu-id="a779e-121">執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="a779e-121">Run the below:</span></span>

- <span data-ttu-id="a779e-122">$tenantId：代表您要執行查詢的承租人識別碼 (也就是說，將在此租使用者的資料上執行查詢) </span><span class="sxs-lookup"><span data-stu-id="a779e-122">$tenantId: ID of the tenant on behalf of which you want to run the query (i.e., the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="a779e-123">$appId： AAD 應用程式的識別碼 (應用程式必須具有 Endpoint for Endpoint 的「執行高級查詢」許可權) </span><span class="sxs-lookup"><span data-stu-id="a779e-123">$appId: ID of your AAD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="a779e-124">$appSecret： Azure AD 應用程式的機密</span><span class="sxs-lookup"><span data-stu-id="a779e-124">$appSecret: Secret of your Azure AD app</span></span>

- <span data-ttu-id="a779e-125">$suspiciousUrl： URL</span><span class="sxs-lookup"><span data-stu-id="a779e-125">$suspiciousUrl: The URL</span></span>


```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here
$suspiciousUrl = 'www.suspiciousUrl.com' # Paste your own URL here

$resourceAppIdUri = 'https://securitycenter.onmicrosoft.com/windowsatpservice'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$aadToken = $authResponse.access_token


#Get latest alert
$alertUrl = "https://api.securitycenter.microsoft.com/api/alerts?`$top=10"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$alertResponse = Invoke-WebRequest -Method Get -Uri $alertUrl -Headers $headers -ErrorAction Stop
$alerts =  ($alertResponse | ConvertFrom-Json).value

$machinesToInvestigate = New-Object System.Collections.ArrayList

Foreach($alert in $alerts)
{
    #echo $alert.id $alert.machineId    $alert.severity $alert.status

    $isSevereAlert = $alert.severity -in 'Medium', 'High'
    $isOpenAlert = $alert.status -in 'InProgress', 'New'
    if($isOpenAlert -and $isSevereAlert)
    {
        if (-not $machinesToInvestigate.Contains($alert.machineId))
        {
            $machinesToInvestigate.Add($alert.machineId) > $null
        }
    }
}

$commaSeparatedMachines = '"{0}"' -f ($machinesToInvestigate -join '","')

$query = "NetworkCommunicationEvents
| where MachineId in ($commaSeparatedMachines)
| where RemoteUrl  == `"$suspiciousUrl`"
| summarize ConnectionsCount = count() by MachineId"

$queryUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"

$queryBody = ConvertTo-Json -InputObject @{ 'Query' = $query }
$queryResponse = Invoke-WebRequest -Method Post -Uri $queryUrl -Headers $headers -Body $queryBody -ErrorAction Stop
$response =  ($queryResponse | ConvertFrom-Json).Results
$response
```


## <a name="see-also"></a><span data-ttu-id="a779e-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a779e-126">See also</span></span>
- [<span data-ttu-id="a779e-127">Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="a779e-127">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="a779e-128">進階搜捕 API</span><span class="sxs-lookup"><span data-stu-id="a779e-128">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="a779e-129">使用 Python 的高級搜尋</span><span class="sxs-lookup"><span data-stu-id="a779e-129">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
