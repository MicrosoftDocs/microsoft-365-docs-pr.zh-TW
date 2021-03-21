---
title: Microsoft 365 Defender REST API 的 Hello World 版
description: 瞭解如何建立應用程式，並使用權杖來存取 Microsoft 365 Defender APIs
keywords: 應用程式、權杖、存取、aad、應用程式、應用程式註冊、powershell、腳本、全域管理員、許可權、microsoft 365 defender
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
ms.openlocfilehash: 65319d46871282c454287af225647f89e3535c78
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924335"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Microsoft 365 Defender REST API 的 Hello World 版

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 365 Defender

> [!IMPORTANT]
> 一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="get-incidents-using-a-simple-powershell-script"></a>使用簡單的 PowerShell 腳本取得事件

完成此專案需要5到10分鐘的時間。 這次預估包括註冊應用程式，以及從 PowerShell 範例腳本套用程式碼。

### <a name="register-an-app-in-azure-active-directory"></a>在 Azure Active Directory 中註冊應用程式

1. 以 **全域系統管理員** 角色的使用者身分登入 [Azure](https://portal.azure.com) 。

2. 流覽至 [ **Azure Active Directory**  >  **應用程式註冊**]  >  **新註冊**。

   ![Microsoft Azure 的影像及應用程式註冊導覽](../../media/atp-azure-new-app2.png)

3. 在 [註冊] 表單中，選擇應用程式的名稱，然後選取 [ **註冊**]。 選取重新導向 URI 是選用的。 您不需要其中一個，即可完成此範例。

4. 在 [應用程式] 頁面上，選取 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織使用**>]，輸入 **microsoft 威脅防護**，然後選取 [ **microsoft 威脅防護**]。 您的應用程式現在可以存取 Microsoft 365 Defender。

   > [!TIP]
   > *Microsoft 威脅防護* 是 Microsoft 365 Defender 的先前名稱，因此不會出現在原始清單中。 您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。
   ![API 許可權選取的影像](../../media/apis-in-my-org-tab.PNG)

   - 選擇 [**應用程式許可權**]  >  **事件。讀取。 [全部**] 並選取 [**新增許可權**]。

   ![API 存取和 API 選取的影像](../../media/request-api-permissions.PNG)

5. 選取 **[授與系統管理員同意**]。 每次您新增許可權時，都必須選取 **[授與系統管理員同意** ]，才會生效。

    ![授與許可權的影像](../../media/grant-consent.PNG)

6. 將密碼新增至應用程式。 選取 [ **& 密碼的憑證**]，新增描述至密碼，然後選取 [ **新增**]。

    > [!TIP]
    > 選取 [ **新增**] 之後，選取 **[複製產生的機密值**]。 離開後，您將無法取得密碼值。

    ![建立應用程式機碼的影像](../../media/webapp-create-key2.png)

7. 將您的應用程式識別碼和租使用者識別碼記錄在安全的位置。 在 [應用程式] 頁面的 **[一覽** ] 底下會列出它們。

   ![建立之應用程式識別碼的影像](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>使用應用程式取得權杖，並使用權杖存取 API

如需 Azure Active Directory 標記的詳細資訊，請參閱 [AZURE AD 教學](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)課程。

> [!IMPORTANT]
> 雖然此演示程式中的範例會鼓勵您貼上機密值以用於測試目的，您決不應該將 **機密硬編碼** 到生產中執行的應用程式。 協力廠商可以使用您的機密存取資源。 您可以使用 [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates)，協助保護應用程式的機密。 如需如何保護應用程式的實際範例，請參閱 [使用 Azure Key Vault 管理伺服器應用程式中的機密](/learn/modules/manage-secrets-with-azure-key-vault/)。

1. 複製下列腳本，並將其貼到您喜愛的文字編輯器中。 [另存新檔] **Get-Token.ps1**。 您也可以在 PowerShell ISE 中執行程式碼，但您應該將其儲存，因為在下一節中使用事件提取腳本時，我們需要重新執行。

    此腳本會產生權杖，並將其儲存在 [名稱] 下的工作資料夾中 *Latest-token.txt*。

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

#### <a name="validate-the-token"></a>驗證 token

1. 複製並貼上您收到的權杖 [以進行](https://jwt.ms) 解碼。
1. 在 *JSON Web Token* 中， *JWT* 代表。 解碼的權杖會包含一些 JSON 格式專案或宣告。 請確定已解碼權杖中的 *角色* 宣告包含所需的許可權。

    在下列影像中，您可以看到從應用程式取得的解碼標記，具有 ```Incidents.Read.All``` 、 ```Incidents.ReadWrite.All``` 和 ```AdvancedHunting.Read.All``` 許可權：

    ![影像 jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>取得最近事件的清單

下列腳本將使用 **Get-Token.ps1** 來存取 API。 然後，它會檢索過去48小時內最後更新的事件清單，並將清單儲存為 JSON 檔案。

> [!IMPORTANT]
> 將此腳本儲存在您儲存 **Get-Token.ps1** 的相同資料夾中。

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

您已經完成了！ 您已成功：

- 建立及註冊應用程式。
- 授與該應用程式讀取提醒的許可權。
- 連接至 API。
- 使用 PowerShell 腳本，傳回過去48小時更新的事件。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender APIs 概述](api-overview.md)
- [存取 Microsoft 365 Defender APIs](api-access.md)
- [建立應用程式以存取沒有使用者的 Microsoft 365 Defender](api-create-app-web.md)
- [建立應用程式以代表使用者存取 Microsoft 365 Defender APIs](api-create-app-user-context.md)
- [建立具有對 Microsoft 365 Defender APIs 的多承租人合作夥伴存取權的應用程式](api-partner-access.md)
- [使用 Azure Key Vault 管理伺服器應用程式中的機密](/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0 使用者登入和 API 存取的授權](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)