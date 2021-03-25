---
title: 使用 REST API 提取 Microsoft Defender for Endpoint 偵測
description: 瞭解如何使用 SIEM REST API 呼叫 Microsoft Defender for Endpoint API 端點以提取 JSON 格式的偵測。
keywords: 偵測、拉入檢測、rest api、要求、回應
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: a7d13da6abfb2cd6c829b6fd04fdf94de8cd20b8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186866"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a>使用 SIEM REST API 拉入 Microsoft Defender for Endpoint 偵測

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- [Microsoft Defender For Endpoint Alert](alerts.md) 是由一或多個偵測所組成。
>- [Microsoft Defender For Endpoint 偵測](api-portal-mapping.md) 是由裝置上發生的可疑事件及其相關警示詳細資料所組成。
>-Microsoft Defender for Endpoint Alert API 是最新的警示消耗 API，且包含每個警示的相關證據的詳細清單。 如需詳細資訊，請參閱 [Alert 方法和屬性](alerts.md) 和 [清單警示](get-alerts.md)。

Microsoft Defender for Endpoint 支援 OAuth 2.0 通訊協定，以從 API 提取偵測。

一般說來，OAuth 2.0 通訊協定支援四種類型的流量：
- 授權授與流程
- 隱含流程
- 用戶端認證流程
- 資源擁有者流程

如需 OAuth 規格的詳細資訊，請參閱 [OAuth 網站](http://www.oauth.net)。

Microsoft Defender for Endpoint 支援 _授權授_ 與 _用戶端認證流程_ ，以取得提取偵測的存取權，AZURE Active Directory (AAD) 做為授權伺服器。

_授權授與流程_ 會使用使用者認證取得授權碼，然後用來取得存取權杖。

_用戶端認證流程_ 會使用用戶端認證，以進行 Microsoft Defender for ENDPOINT 端點 URL 的驗證。 當 OAuth 用戶端建立不需要使用者認證之 API 的要求時，此流程適用案例。

在 Microsoft Defender for Endpoint API 中使用下列方法，以 JSON 格式提取偵測結果。

>[!NOTE]
>Microsoft Defender 安全中心會將類似的警示偵測合併成單一警示。 此 API 會根據您設定的查詢參數，在其原始表單中拉入警示偵測，讓您能夠套用您自己的群組和篩選。 

## <a name="before-you-begin"></a>開始之前
- 呼叫 Microsoft Defender for Endpoint 端點以提取偵測之前，您需要在 Azure Active Directory (AAD) 中啟用 SIEM 整合應用程式。 如需詳細資訊，請參閱 [ENABLE SIEM integration In Microsoft Defender For Endpoint](enable-siem-integration.md)。

- 請記下 Azure 應用程式註冊中的下列值。 您需要這些值來設定您的服務或守護程式應用程式中的 OAuth 流量：
  - 您的應用程式獨有的應用程式識別碼 () 
  - 您的應用程式) 的應用程式金鑰或機密 (
  - 您的應用程式的 OAuth 2.0 token 端點
    - 在應用程式頁面中，按一下 Azure 管理入口網站底部的 [ **查看端點** ]，以尋找此值。 端點會類似 `https://login.microsoftonline.com/{tenantId}/oauth2/token` 。

## <a name="get-an-access-token"></a>取得存取權杖
在建立端點的呼叫之前，您必須取得存取權杖。

您將使用存取權杖來存取受保護的資源，這是 Microsoft Defender for Endpoint 中的偵測。

若要取得存取權杖，您必須對「簽發」端點執行 POST 要求。 以下是範例要求：

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
回應會包含存取權杖和到期資訊。

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
您現在可以在要求中使用 Defender for Endpoint API 的 *access_token* 欄位中的值。

## <a name="request"></a>請求
使用存取權杖，您的應用程式可以對 Microsoft Defender for Endpoint API 進行驗證要求。 您的應用程式必須將存取權杖附加至每個要求的授權標頭。

### <a name="request-syntax"></a>要求語法
方法 | 要求 URI
:---|:---|
GET| 使用適用于您所在地區的 URI。 <br><br> **對於歐盟**： `https://wdatp-alertexporter-eu.windows.com/api/alerts` </br> **我們**： `https://wdatp-alertexporter-us.windows.com/api/alerts` <br> 若 **為 UK**：`https://wdatp-alertexporter-uk.windows.com/api/alerts` 

### <a name="request-header"></a>要求標頭
Header | 類型 | 描述|
:--|:--|:--
授權 | string | 必要。 表單 **持有** 者權杖中的 Azure AD 存取權杖 &lt;  &gt; 。 |

### <a name="request-parameters"></a>要求參數

使用選用的查詢參數來指定及控制回應中傳回的資料量。 如果您呼叫此方法但未參數，則此回應會包含您的組織中過去2小時內的所有警示。

名稱 | 值| 描述
:---|:---|:---
sinceTimeUtc | DateTime | 根據欄位，定義從下列位置檢索的綁定警示下限： <br> `LastProcessedTimeUtc` <br> 時間範圍將會是：從 sinceTimeUtc 時間到目前時間。 <br><br> **附注**：如果未指定，則會檢索過去兩小時內產生的所有警示。
untilTimeUtc | DateTime | 定義要檢索的上限時間限制。 <br> 時間範圍將會是：開始時間 `sinceTimeUtc` `untilTimeUtc` 。 <br><br> **附注**：如果未指定，預設值將會是目前的時間。
前 | string | 在下列時間範圍內拉入警示：「開始 `(current_time - ago)` `current_time` 時間。 <br><br> 值應該根據 **ISO 8601** 的持續時間格式設定 <br> 範例： `ago=PT10M` 會在過去10分鐘內提取接收到的提醒。
限制 | int | 會定義要檢索的提醒數目。 會根據定義的數目來檢索最新的警示。<br><br> **附注**：如果未指定，則會檢索時間範圍內的所有可用警示。
machinegroups | string | 指定要從中接收警示的裝置群組。 <br><br> **附注**：如果未指定，則會從所有裝置群組中檢索警示。 <br><br> 範例： <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/Alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
DeviceCreatedMachineTags | string | 登錄中的單一裝置標記。
CloudCreatedMachineTags | string | 在 Microsoft Defender Security Center 中建立的裝置標記。

### <a name="request-example"></a>要求範例
下列範例會示範如何在您的組織中取得所有的偵測。

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

下列範例會示範自 2016-09-12 00:00:00 起取得最後20項檢測的要求。

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a>回應
傳回值是以 JSON 格式的警示物件陣列。

以下是範例傳回值：

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a>程式碼範例
### <a name="get-access-token"></a>取得存取權杖
下列程式碼範例會示範如何取得存取權杖，以呼叫 Microsoft Defender for Endpoint SIEM API。

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a>使用 token 連接至偵測端點
下列程式碼範例會示範如何使用存取權杖來呼叫 Defender for Endpoint SIEM API，以取得警示。

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a>錯誤碼
Microsoft Defender for Endpoint REST API 傳回下列由無效要求所造成的錯誤代碼。

HTTP 錯誤碼 | 描述
:---|:---
401 | 格式不良的要求或不正確 token。
403 | 未經授權的例外狀況-已刪除任何網域，而不是由租使用者管理員或租使用者狀態所管理。
500 | 服務中的錯誤。

## <a name="related-topics"></a>相關主題
- [在 Microsoft Defender for Endpoint 中啟用 SIEM 整合](enable-siem-integration.md)
- [設定 ArcSight 以拉入 Microsoft Defender for Endpoint 偵測](configure-arcsight.md)
- [向 SIEM 工具提取偵測](configure-siem.md)
- [Microsoft Defender for Endpoint 偵測欄位](api-portal-mapping.md)
- [疑難排解 SIEM 工具整合問題](troubleshoot-siem.md)
