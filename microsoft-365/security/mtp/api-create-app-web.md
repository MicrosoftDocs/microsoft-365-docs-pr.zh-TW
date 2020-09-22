---
title: 建立應用程式，以在沒有使用者的情況下存取 Microsoft 威脅防護
description: 瞭解如何建立應用程式，以在沒有使用者的情況下存取 Microsoft 威脅防護
keywords: 應用程式、access、api、create
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
ms.openlocfilehash: 57ba0eb77ccb855cc0c0224b5321f11809e21ae8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201416"
---
# <a name="create-an-app-to-access-microsoft-threat-protection-without-a-user"></a>建立應用程式，以在沒有使用者的情況下存取 Microsoft 威脅防護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：****
- Microsoft 威脅防護

>[!IMPORTANT] 
>一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

此頁面說明如何建立應用程式，以在沒有使用者的情況下，以程式設計方式存取 Microsoft 威脅防護。 如果您需要以程式設計方式代表使用者存取 Microsoft 威脅防護，請參閱 [Get access with user coNtext](api-create-app-user-context.md)。 如果您不確定需要哪一種存取權，請參閱 [入門](api-access.md)。

Microsoft 威脅防護會透過一組程式設計 APIs 來公開其資料和動作。 這些 APIs 會協助您根據 Microsoft 威脅防護功能來自動化工作流程與創新。 API 存取需要 OAuth 2.0 驗證。 如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

一般來講，您必須採取下列步驟，才能使用 APIs：
- 建立 Azure Active Directory (Azure AD) 應用程式。
- 使用此應用程式取得存取權杖。
- 使用權杖來存取 Microsoft 威脅防護 API。

本文說明如何建立 Azure AD 應用程式、取得 Microsoft 威脅防護的存取權杖，以及驗證權杖。

## <a name="create-an-app"></a>建立應用程式

1. 使用具有**全域系統管理員**角色的使用者登入[Azure](https://portal.azure.com) 。

2. 流覽至 [ **Azure Active Directory**  >  **應用程式註冊**]  >  **新註冊**。 

   ![Microsoft Azure 的影像及應用程式註冊導覽](../../media/atp-azure-new-app2.png)

3. 在 [註冊] 表單中，選擇應用程式的名稱，然後選取 [ **註冊**]。

4. 若要讓您的應用程式能夠存取 Microsoft 威脅防護並指派 it 許可權，請在應用程式頁面上，選取 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織使用**>]，輸入 [ **microsoft 威脅防護**]，然後選取 [ **microsoft 威脅防護**]。

   > [!NOTE]
   > Microsoft 威脅防護不會出現在原始清單中。 您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。

   ![API 存取和 API 選取的影像](../../media/apis-in-my-org-tab.PNG)

   - 選取 [ **應用程式許可權** ] > 選擇您案例的相關許可權，例如 **Incident。 Read。 All**，然後選取 [ **新增許可權**]。

   ![API 存取和 API 選取的影像](../../media/request-api-permissions.PNG)

    >[!NOTE]
    >您需要為案例選取相關許可權，「 **讀取所有事件** 」只是一個範例。 若要決定您需要的許可權，請參閱您想要呼叫之 API 中的 [ **許可權** ] 區段。

5. 選取 **[授與同意**]。

     > [!NOTE]
     > 每當您新增許可權時，您必須選取 **[授與同意** ]，新許可權才會生效。

    ![授與許可權的影像](../../media/grant-consent.PNG)

6. 若要將機密新增至應用程式，請選取 [ **憑證 & 機密**]，新增 [密碼] 的描述，然後選取 [ **新增**]。

    > [!NOTE]
    > 選取 [ **新增**] 之後，選取 **[複製產生的機密值**]。 離開後，您將無法取回此值。

    ![建立應用程式機碼的影像](../../media/webapp-create-key2.png)

7. 記下來記錄應用程式識別碼和您的租使用者識別碼。 在 [應用程式] 頁面上，移至 **[簡介** ]，然後複製下列各項。

   ![建立之應用程式識別碼的影像](../../media/app-and-tenant-ids.png)

8. **僅適用于 Microsoft 威脅防護合作夥伴**。 [請依照這裡的指示](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access)進行。 將您的應用程式設為多 tenanted (在同意) 後，所有承租人皆可使用。 這是協力廠商應用程式 **所需** 的 (例如，如果您建立要在多個客戶的承租人) 中執行的應用程式。 如果您建立只想要在租使用者中執行的服務，這 **不是必要** 的 (例如，如果您為自己的使用方式建立應用程式，只會與您自己的資料) 互動。 若要將您的應用程式設為多 tenanted：

    - 移至 [ **驗證**]，然後新增 https://portal.azure.com 為重新 **導向 URI**。

    - 在頁面底部的 [ **支援的帳戶類型**] 底下，選取您的多租使用者應用程式的 **任何組織目錄** 應用程式中的帳戶。

    您必須在您要使用的每個承租人中核准您的應用程式。 這是因為您的應用程式代表客戶互動 Microsoft 威脅防護。

    當您撰寫協力廠商應用程式時，您 (或客戶) 必須選取同意連結並核准您的應用程式。 使用 Active Directory 中具有系統管理許可權的使用者，應進行同意。

    「同意」連結的成形如下： 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    其中00000000-0000-0000-0000-000000000000 會取代為您的應用程式識別碼。


**做！** 您已成功註冊應用程式！ 請參閱下列範例以取得及驗證權杖。

## <a name="get-an-access-token"></a>取得存取權杖

如需 Azure AD 標記的詳細資訊，請參閱 [AZURE ad 教學](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)課程。

### <a name="use-powershell"></a>使用 PowerShell

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

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

### <a name="use-c"></a>使用 c #：

下列程式碼已使用 Nuget Windows.identitymodel.extensions.dll 進行測試。 ActiveDirectory 3.19.8。

1. 建立新的主控台應用程式。
1. 安裝 Nuget [windows.identitymodel.extensions.dll ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。
1. 新增下列專案：

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 在應用程式中複製並貼上下列程式碼 (請勿忘記更新三個變數： ```tenantId, appId, appSecret```) ：

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a>使用 Python 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

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
### <a name="use-curl"></a>使用捲曲

> [!NOTE]
> 下列程式假設已在您的電腦上安裝了 Windows 的卷。

1. 開啟命令提示字元，並將 CLIENT_ID 設定為您的 Azure 應用程式識別碼。
1. 將 CLIENT_SECRET 設定為您的 Azure 應用程式密碼。
1. 將 TENANT_ID 設定為要使用您的應用程式存取 Microsoft 威脅防護之客戶的 Azure 租使用者識別碼。
1. 執行下列命令：

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

您會收到下列形式的答案：

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>驗證 token

確定您獲得正確的權杖：

1. 將您在上一個步驟中所掌握的權杖複製並貼上至 [JWT](https://jwt.ms) ，以便進行解碼。
1. 確認您取得了所需許可權的「role」宣告
1. 在下列影像中，您可以看到使用的應用程式取得的解碼標記 ```Incidents.Read.All``` ， ```Incidents.ReadWrite.All``` 以及 ```AdvancedHunting.Read.All``` 許可權：

![權杖驗證的影像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a>使用權杖存取 Microsoft 威脅防護 API

1. 選擇您要使用的 API。 如需詳細資訊，請參閱 [支援的 Microsoft 威脅防護 APIs](api-supported.md)。

2. 在您傳送至 "載荷 {token}" 的 HTTP 要求中設定授權標頭。 (載荷是授權配置) 。

3. 權杖的到期時間是一小時。 您可以使用相同的權杖傳送一個以上的要求。

以下是 **使用 c #** 傳送要求以取得事件清單的範例： 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a>相關主題
- [存取 Microsoft 威脅防護 APIs](api-access.md)
- [使用應用程式內容存取 Microsoft 威脅防護](api-create-app-web.md)
- [使用使用者內容存取 Microsoft 威脅防護](api-create-app-user-context.md)
