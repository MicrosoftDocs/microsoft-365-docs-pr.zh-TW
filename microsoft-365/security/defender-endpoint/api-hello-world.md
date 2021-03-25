---
title: Microsoft Defender for Endpoint API 的 Hello World
ms.reviewer: ''
description: 針對 Microsoft Defender ATP) API 建立 world' 至 Microsoft Defender for (Endpoint 的做法「Hello-style API 呼叫」。
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
ms.openlocfilehash: 3b076d0fa6e01be2a810e8fa810cc3e32955388e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199644"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a>Microsoft Defender for Endpoint API-Hello World 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：** 
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)


- 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a>使用簡單的 PowerShell 腳本取得提醒

### <a name="how-long-it-takes-to-go-through-this-example"></a>在這個範例中需要多久時間？
只需要5分鐘完成兩個步驟：
- 應用程式註冊
- 使用範例：只需要複製/貼上簡短的 PowerShell 腳本

### <a name="do-i-need-a-permission-to-connect"></a>我需要連線許可權嗎？
在 [應用程式註冊] 階段，您的 Azure Active Directory (Azure AD) 租使用者必須具有 **全域系統管理員** 角色。

### <a name="step-1---create-an-app-in-azure-active-directory"></a>步驟 1-在 Azure Active Directory 中建立應用程式

1. 使用您的 **全域系統管理員** 使用者登入 [Azure](https://portal.azure.com) 。

2. 流覽至 [ **Azure Active Directory**  >  **應用程式註冊**]  >  **新註冊**。 

   ![Microsoft Azure 的影像及應用程式註冊導覽](images/atp-azure-new-app2.png)

3. 在 [註冊] 表單中，選擇應用程式的名稱，然後按一下 [ **註冊**]。

4. 讓您的應用程式能夠存取使用者的 Defender，並指派「 **讀取所有警示** 」的許可權：

   - 在 [應用程式] 頁面上，按一下 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織] 使用**> type **WindowsDefenderATP** ，然後按一下 [ **WindowsDefenderATP**]。

   - **附注**： WindowsDefenderATP 不會出現在原始清單中。 您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。

   ![API 存取和 API selection1 的影像](images/add-permission.png)

   - 選擇 [**應用程式許可權**]  >  **警示。讀取。所有**> 按一下 [**新增許可權**]

   ![API 存取和 API selection2 的影像](images/application-permissions.png)

   **重要** 須知：您必須選取相關的許可權。 「讀取所有警示」只是範例！

     例如，

     - 若要 [執行高級查詢](run-advanced-query-api.md)，請選取「執行高級查詢」許可權
     - 若要 [隔離機器](isolate-machine.md)，請選取「隔離電腦」許可權
     - 若要決定您需要的許可權，請參閱您想要呼叫之 API 中的 [ **許可權** ] 區段。

5. 按一下 **[授與同意**]

    - **附注**：每次您新增許可權時，您必須按一下 **[授與同意** 才能讓新的許可權生效。

    ![授與許可權的影像](images/grant-consent.png)

6. 將密碼新增至應用程式。

    - 按一下 [ **憑證 & 機密**]，將 description 新增至密碼，然後按一下 [ **新增**]。

    **重要** 事項：按一下 [新增] 後，請 **複製產生的機密值**。 離開後，您將無法進行找回！

    ![建立應用程式機碼的影像](images/webapp-create-key2.png)

7. 記下來記錄應用程式識別碼和您的租使用者 ID:

   - 在 [應用程式] 頁面上，移至 **[簡介** ]，然後複製下列專案：

   ![建立之應用程式識別碼的影像](images/app-and-tenant-ids.png)


做！ 您已成功註冊應用程式！

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>步驟 2-使用此應用程式取得權杖，並使用此權杖來存取 API。

-   將下列腳本複製到 PowerShell ISE 或文字編輯器，並將其儲存為 "**Get-Token.ps1**"
-   執行此腳本會產生權杖，並將其儲存在工作資料夾中，名稱為 "**Latest-token.txt**" 的資料夾。

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

-   健全檢查：<br>
執行指令碼。<br>
在您的瀏覽器中，移至： https://jwt.ms/ <br>
將權杖複製 (Latest-token.txt 檔案) 的內容。<br>
貼上方框。<br>
尋找「角色」一節。 尋找警示。讀取。所有角色。

![影像 jwt.ms](images/api-jwt-ms.png)

### <a name="lets-get-the-alerts"></a>讓我們取得警示！

-   下列腳本將使用 **Get-Token.ps1** 來存取 API，並會收到過去48小時的警示。
-   將此腳本儲存在您儲存先前腳本 **Get-Token.ps1** 的相同資料夾中。 
-   此腳本會建立兩個檔案 (json 及 csv) 與腳本相同的資料夾中的資料。

```
# Returns Alerts created in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Alert from the last 48 hours. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")       

# The URL contains the type of query and the time filter we create above
# Read more about other query options and filters at   Https://TBD- add the documentation link
$url = "https://api.securitycenter.microsoft.com/api/alerts?`$filter=alertCreationTime ge $dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the alerts from the results. 
$alerts =  ($response | ConvertFrom-Json).value | ConvertTo-Json

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json and as csv
$outputJsonPath = "./Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "./Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
($alerts | ConvertFrom-Json) | Export-CSV $outputCsvPath -NoTypeInformation 
```

您已經完成了！ 您剛剛成功：
-   建立及註冊和應用程式
-   授與該應用程式讀取提醒的許可權
-   已連接 API
-   使用 PowerShell 腳本傳回過去48小時內建立的警示



## <a name="related-topic"></a>相關主題
- [Microsoft Defender for Endpoint APIs](exposed-apis-list.md)
- [使用應用程式內容存取 Microsoft Defender for Endpoint](exposed-apis-create-app-webapp.md)
- [使用使用者內容存取 Microsoft Defender for Endpoint](exposed-apis-create-app-nativeapp.md)
