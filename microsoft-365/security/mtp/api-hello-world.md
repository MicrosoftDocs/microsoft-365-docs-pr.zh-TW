---
title: Hello World for Microsoft 365 Defender REST API
description: 瞭解如何建立應用程式並使用權杖存取 Microsoft 365 Defender API
keywords: App， token， access， aad， app， application registration， powershell， script， global administrator， permission， microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 66afa27d0fa7a092d3f9e9ed6c3b6abc6020cb8d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928375"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World for Microsoft 365 Defender REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 365 Defender

> [!IMPORTANT]
> 部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="get-incidents-using-a-simple-powershell-script"></a>使用簡單的 PowerShell 腳本取得事件

完成此專案需要 5 到 10 分鐘。 預估的這個時間包括註冊應用程式，以及從 PowerShell 範例腳本中應用程式代碼。

### <a name="register-an-app-in-azure-active-directory"></a>在 Azure Active Directory 中註冊應用程式

1. 以具有 [全域系統管理員](https://portal.azure.com) 角色的使用者之名 **來簽署** Azure。

2. 流覽至 **Azure Active Directory**  >  **App 註冊**  >  **新增註冊**。

   ![Microsoft Azure 的影像和應用程式註冊的流覽](../../media/atp-azure-new-app2.png)

3. 在註冊表單中，選擇應用程式的名稱， **然後選取註冊**。 選取重新導向 URI 是選擇性的。 完成此範例不需要一個。

4. 在您的應用程式頁面上，選取我的組織使用的 **API** 許可權新增許可權 API > Microsoft 威脅防護，然後選取  >    >  **** **Microsoft 威脅防護**。  您的應用程式現在可以存取 Microsoft 365 Defender。

   > [!TIP]
   > *Microsoft 威脅防護* 是 Microsoft 365 Defender 的前一個名稱，不會顯示在原始清單中。 您必須開始在文字方塊中撰寫其名稱，它就會出現。
   ![API 許可權選取的影像](../../media/apis-in-my-org-tab.PNG)

   - 選擇 **應用程式許可權**  >  **事件。讀取。全部**，然後選取 **新增許可權**。

   ![API 存取和 API 選取的影像](../../media/request-api-permissions.PNG)

5. 選取 **授予系統管理員同意**。 每次您新增許可權時，都必須選取授予 **系統管理員同意** ，該同意才能生效。

    ![授予許可權的影像](../../media/grant-consent.PNG)

6. 在應用程式中新增密碼。 選取 **&秘訣、** 新增描述至機密，然後選取新增 **。**

    > [!TIP]
    > 選取新增 **後，** 選取 **複製產生的密碼值**。 您離開後將無法取回密碼值。

    ![建立應用程式金鑰的影像](../../media/webapp-create-key2.png)

7. 在安全的地方記錄您的應用程式識別碼和租使用者識別碼。 這些清單會列在應用程式 **頁面的** 概覽下。

   ![已建立應用程式識別碼的影像](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>使用應用程式取得權杖，並使用權杖存取 API

有關 Azure Active Directory 權杖詳細資訊，請參閱 [Azure AD 教學課程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

> [!IMPORTANT]
> 雖然本示範應用程式中的範例會鼓勵您貼上密碼值以進行測試，但您絕對不應該將秘訣貼入實際執行中的應用程式。 協力廠商可能會使用您的密碼存取資源。 您可以使用 Azure 金鑰保存庫，協助保護您 [App 的秘訣安全](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)。 有關如何保護應用程式的實用範例，請參閱使用 Azure 金鑰庫管理伺服器 [應用程式中的秘訣](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)。

1. 複製下列腳本，並貼到您最愛的文字編輯器中。 另存 **新Get-Token.ps1。** 您也可以在 PowerShell ISE 中就地執行程式碼，但您應儲存程式碼，因為當我們使用下一節的事件提取腳本時，必須再次執行。

    此腳本會產生權杖，並將其儲存在工作資料夾的名稱下 *，Latest-token.txt。*

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

    $resourceAppIdUri = 'https://api.security.microsoft.com'
    $oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"
    $authBody = [Ordered] @{
      resource = $resourceAppIdUri
      client_id = $clientId
      client_secret = $appSecret
      grant_type = 'client_credentials'
    }
    $authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
    $token = $authResponse.access_token
    Out-File -FilePath "./Latest-token.txt" -InputObject $token
    return $token
    ```

#### <a name="validate-the-token"></a>驗證權杖

1. 將您收到的權杖複製並貼到 [JWT](https://jwt.ms) 進行解碼。
1. *JWT* 代表 *JSON Web Token。* 解碼權杖會包含數個 JSON 格式的專案或領取。 確認在 *解碼* 權杖中要求的角色包含所需的許可權。

    在下列影像中，您可以看見從應用程式取得、具有 、及許可權 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` 的譯 ```AdvancedHunting.Read.All``` 碼權杖：

    ![影像jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>取得最近事件的清單

下列腳本 **將使用Get-Token.ps1存取** API。 然後，它會取回過去 48 小時內更新的事件清單，然後將清單另存為 JSON 檔案。

> [!IMPORTANT]
> 將這個腳本儲存在您儲存該腳本的 **Get-Token.ps1。**

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

大完成了！ 您已成功：

- 建立並登錄應用程式。
- 已授予該應用程式讀取警示的許可權。
- 已連接至 API。
- 使用 PowerShell 腳本來退回過去 48 小時內更新的事件。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender API 概觀](api-overview.md)
- [存取 Microsoft 365 Defender API](api-access.md)
- [建立應用程式以在沒有使用者的情況下存取 Microsoft 365 Defender](api-create-app-web.md)
- [建立應用程式以代表使用者存取 Microsoft 365 Defender API](api-create-app-user-context.md)
- [建立具有 Microsoft 365 Defender API 多租使用者合作夥伴存取權的應用程式](api-partner-access.md)
- [使用 Azure 金鑰庫管理伺服器應用程式中的秘訣](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0 使用者簽署和 API 存取的授權](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
