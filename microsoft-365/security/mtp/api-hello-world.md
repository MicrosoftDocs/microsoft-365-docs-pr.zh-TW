---
title: Microsoft 365 Defender REST API 的 Hello World 版
description: 瞭解如何建立應用程式，並使用權杖來存取 Microsoft 365 Defender APIs
keywords: 應用程式、權杖、存取、aad、app、application registration、powershell、script、全域管理員、許可權
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bd4f7e5485d67cf74477900ae2cc5c77f1a6ee41
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844041"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Microsoft 365 Defender REST API 的 Hello World 版 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

>[!IMPORTANT] 
>一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="get-incidents-using-a-simple-powershell-script"></a>使用簡單的 PowerShell 腳本取得事件

### <a name="how-long-it-takes-to-go-through-this-example"></a>在這個範例中需要多久時間？
只需要5分鐘完成兩個步驟：
- 應用程式註冊
- 使用範例：只需要複製/貼上簡短的 PowerShell 腳本

### <a name="do-i-need-a-permission-to-connect"></a>我需要連線許可權嗎？
在 [應用程式註冊] 階段，您的 Azure Active Directory (Azure AD) 租使用者必須具有 **全域系統管理員** 角色。

### <a name="step-1---create-an-app-in-azure-active-directory"></a>步驟 1-在 Azure Active Directory 中建立應用程式

1. 使用您的 **全域系統管理員** 使用者登入 [Azure](https://portal.azure.com) 。

2. 流覽至 [ **Azure Active Directory**  >  **應用程式註冊** ]  >  **新註冊** 。 

   ![Microsoft Azure 的影像及應用程式註冊導覽](../../media/atp-azure-new-app2.png)

3. 在 [註冊] 表單中，選擇應用程式的名稱，然後選取 [ **註冊** ]。

4. 允許應用程式存取 Microsoft Defender for Endpoint，並指派它 **讀取所有的事件** 許可權：

   - 在 [應用程式] 頁面上，選取 [ **API 許可權**  >  **新增許可權** ]  >  **APIs 我的組織使用** > 輸入 **microsoft 365 defender** ，然後在 **microsoft 365 defender** 上選取。

   >[!NOTE]
   >Microsoft 365 Defender 未出現在原始清單中。 您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。

   ![API 存取和 API 選取的影像](../../media/apis-in-my-org-tab.PNG)

   - 選擇 [ **應用程式許可權** ]  >  **事件。讀取。所有** > 在 [ **新增] 許可權** 上選取

   ![API 存取和 API 選取的影像](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   >您必須選取相關的許可權。 

     例如，

     - 若要決定您需要的許可權，請參閱您想要呼叫之 API 中的 [ **許可權** ] 區段。

5. 選取 **[授與系統管理員同意** ]

    - >[!NOTE]
      > 每次您新增許可權時，您必須選取 **[授與同意** 才能讓新許可權同意] 生效。

    ![授與許可權的影像](../../media/grant-consent.PNG)

6. 將密碼新增至應用程式。

    - 選取 [ **& 密碼的憑證** ]，將 description 新增至 [密碼]，然後選取 [ **新增** ]。

    >[!IMPORTANT]
    > 選取 [ **新增** ] 之後，請 **複製產生的密碼值** 。 離開後，您將無法進行找回！

    ![建立應用程式機碼的影像](../../media/webapp-create-key2.png)

7. 記下來記錄應用程式識別碼和您的租使用者 ID:

   - 在 [應用程式] 頁面上，移至 **[簡介** ]，然後複製下列專案：

   ![建立之應用程式識別碼的影像](../../media/app-and-tenant-ids.png)


做！ 您已成功註冊應用程式。

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>步驟 2-使用此應用程式取得權杖，並使用此權杖來存取 API。

-   將下列腳本複製到 PowerShell ISE 或文字編輯器，並將其儲存為 " **Get-Token.ps1** "
-   執行此腳本會產生權杖，並將其儲存在工作資料夾中，名稱為 " **Latest-token.txt** " 的資料夾。

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
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
尋找「角色」一節。 尋找 ```Incidents.Read.All``` 角色。<br>
下列範例來自具有和許可權的應用程式 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` 。

![影像 jwt.ms](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a>讓我們能夠取得事件！

-   下列腳本將使用 **Get-Token.ps1** 來存取 API，並在過去48小時內取得最後一次更新的事件。
-   將此腳本儲存在您儲存先前腳本 **Get-Token.ps1** 的相同資料夾中。 
-   編寫 json 檔案的腳本，該檔案與腳本位於相同的資料夾中。

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

您已經完成了！ 您剛剛成功：
-   建立及註冊和應用程式
-   授與該應用程式讀取提醒的許可權
-   已連接 API
-   使用 PowerShell 腳本傳回過去48小時內建立的事件



## <a name="related-topic"></a>相關主題
- [存取 Microsoft 365 Defender APIs](api-access.md)
- [使用應用程式內容存取 Microsoft 365 Defender](api-create-app-web.md)
- [使用使用者內容存取 Microsoft 365 Defender](api-create-app-user-context.md)
