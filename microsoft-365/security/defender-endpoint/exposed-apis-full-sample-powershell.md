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
ms.openlocfilehash: ef6d05bb27018bb72f731da2e8b7837c9d9f0127
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842059"
---
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a><span data-ttu-id="32ff9-104">Microsoft Defender for Endpoint APIs 使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="32ff9-104">Microsoft Defender for Endpoint APIs using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="32ff9-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="32ff9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="32ff9-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="32ff9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="32ff9-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="32ff9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

><span data-ttu-id="32ff9-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="32ff9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="32ff9-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="32ff9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="32ff9-110">使用 Microsoft Defender for Endpoint 中的多個 APIs 的完整案例。</span><span class="sxs-lookup"><span data-stu-id="32ff9-110">Full scenario using multiple APIs from Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="32ff9-111">在本節中，我們會分享 PowerShell 範例，以</span><span class="sxs-lookup"><span data-stu-id="32ff9-111">In this section, we share PowerShell samples to</span></span> 
- <span data-ttu-id="32ff9-112">取得 token</span><span class="sxs-lookup"><span data-stu-id="32ff9-112">Retrieve a token</span></span> 
- <span data-ttu-id="32ff9-113">使用 token 在 Microsoft Defender for Endpoint 中檢索最新的警示</span><span class="sxs-lookup"><span data-stu-id="32ff9-113">Use token to retrieve the latest alerts in Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="32ff9-114">針對每個警示，如果警示有中低或高優先順序且仍在進行中，請檢查裝置連線至可疑 URL 的次數。</span><span class="sxs-lookup"><span data-stu-id="32ff9-114">For each alert, if the alert has medium or high priority and is still in progress, check how many times the device has connected to suspicious URL.</span></span>

<span data-ttu-id="32ff9-115">必要條件 **：您** 必須先 [建立應用程式](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="32ff9-115">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="32ff9-116">準備指示</span><span class="sxs-lookup"><span data-stu-id="32ff9-116">Preparation instructions</span></span>

- <span data-ttu-id="32ff9-117">開啟 PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="32ff9-117">Open a PowerShell window.</span></span>
- <span data-ttu-id="32ff9-118">如果您的原則不允許您執行 PowerShell 命令，您可以執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="32ff9-118">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

<span data-ttu-id="32ff9-119">如需詳細資訊，請參閱 [PowerShell 檔](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="32ff9-119">For more information, see [PowerShell documentation](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="32ff9-120">取得 token</span><span class="sxs-lookup"><span data-stu-id="32ff9-120">Get token</span></span>

<span data-ttu-id="32ff9-121">執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="32ff9-121">Run the below:</span></span>

- <span data-ttu-id="32ff9-122">$tenantId：代表您要執行查詢的承租人識別碼 (也就是說，將在此租使用者的資料上執行查詢) </span><span class="sxs-lookup"><span data-stu-id="32ff9-122">$tenantId: ID of the tenant on behalf of which you want to run the query (i.e., the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="32ff9-123">$appId： AAD 應用程式的識別碼 (應用程式必須具有 Endpoint for Endpoint 的「執行高級查詢」許可權) </span><span class="sxs-lookup"><span data-stu-id="32ff9-123">$appId: ID of your AAD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="32ff9-124">$appSecret： Azure AD 應用程式的機密</span><span class="sxs-lookup"><span data-stu-id="32ff9-124">$appSecret: Secret of your Azure AD app</span></span>

- <span data-ttu-id="32ff9-125">$suspiciousUrl： URL</span><span class="sxs-lookup"><span data-stu-id="32ff9-125">$suspiciousUrl: The URL</span></span>


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


## <a name="see-also"></a><span data-ttu-id="32ff9-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="32ff9-126">See also</span></span>
- [<span data-ttu-id="32ff9-127">Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="32ff9-127">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="32ff9-128">進階搜捕 API</span><span class="sxs-lookup"><span data-stu-id="32ff9-128">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="32ff9-129">使用 Python 進階搜尋</span><span class="sxs-lookup"><span data-stu-id="32ff9-129">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
