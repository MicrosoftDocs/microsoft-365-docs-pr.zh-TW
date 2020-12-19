---
title: 透過 Microsoft 365 Defender APIs 的合作夥伴存取
description: 瞭解如何建立可讓使用者以程式設計方式存取 Microsoft 365 Defender 的應用程式。
keywords: partner，access，api，多租使用者，同意，存取權杖，應用程式
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
ms.openlocfilehash: 5de113c8f8419b3af2a287bd7ba7e41dc06b4121
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719437"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>建立具有對 Microsoft 365 Defender APIs 的合作夥伴存取權的應用程式

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 365 Defender

> [!IMPORTANT]
> 一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

此頁面說明如何建立可以以程式設計方式存取 Microsoft 365 Defender 的 Azure Active Directory 應用程式，代表使用者跨多個承租人。 多租使用者應用程式對於提供大量使用者十分有用。

如果您需要以程式設計方式代表單一使用者存取 Microsoft 365 Defender，請參閱 [建立應用程式以代表使用者存取 microsoft 365 defender APIs](api-create-app-user-context.md)。 如果您需要在未明確定義的使用者的情況下存取 (例如，如果您正在撰寫後臺應用程式或幕後程式) ，請參閱 [Create a app to Access Microsoft 365 Defender （沒有使用者](api-create-app-web.md)）。 如果您不確定需要哪種類型的存取，請參閱 [入門](api-access.md)。

Microsoft 365 Defender 會透過一組程式設計 APIs 來公開其大部分資料和動作。 這些 APIs 可協助您自動化工作流程，並使用 Microsoft 365 Defender 的功能。 此 API access 需要 OAuth 2.0 驗證。 如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

一般來講，您必須採取下列步驟，才能使用這些 APIs：

- 建立 Azure Active Directory (Azure AD) 應用程式。
- 使用此應用程式取得存取權杖。
- 使用權杖來存取 Microsoft 365 Defender API。

因為此應用程式是多租使用者，所以您也需要每個租使用者代表其使用者的系統 [管理員同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 。

本文將說明如何：

- 建立 **多承租人** Azure AD 應用程式
- 取得您的應用程式的使用者管理員授權，以存取其所需資源的 Microsoft 365 Defender。
- 取得 Microsoft 365 Defender 的存取權杖
- 驗證 token

Microsoft 365 Defender 會透過一組程式設計 APIs 來公開其大部分資料和動作。 這些 APIs 會協助您根據 Microsoft 365 Defender 功能自動化工作流程與創新。 API 存取需要 OAuth 2.0 驗證。 如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

一般來講，您必須採取下列步驟，才能使用 APIs：

- 建立 **多承租人** Azure AD 應用程式。
- 取得授權的 (同意) 您的應用程式的使用者管理員存取其所需的 Microsoft 365 Defender 資源。
- 使用此應用程式取得存取權杖。
- 使用權杖來存取 Microsoft 365 Defender API。

下列步驟可協助您建立多承租人 Azure AD 應用程式、取得 Microsoft 365 Defender 的存取權杖，以及驗證權杖。

## <a name="create-the-multi-tenant-app"></a>建立多租使用者應用程式

1. 以 **全域系統管理員** 角色的使用者身分登入 [Azure](https://portal.azure.com) 。

2. 流覽至 [ **Azure Active Directory**  >  **應用程式註冊**]  >  **新註冊**。

   ![Microsoft Azure 的影像及應用程式註冊導覽](../../media/atp-azure-new-app2.png)

3. 在 [註冊] 表單中：

   - 選擇應用程式的名稱。
   - 在 [ **支援的帳戶類型**] 中，選取 **任何組織目錄中的 [帳戶] (任何 Azure AD 目錄) -多租戶**。
   - 填寫 [重新 **導向 URI** ] 區段。 選取 [輸入 **Web** ]，並提供重新導向 URI 為 **https://portal.azure.com** 。

   完成表單填寫後，請選取 [ **註冊**]。

   ![[註冊應用程式] 表單的影像](../..//media/atp-api-new-app-partner.png)

4. 在 [應用程式] 頁面上，選取 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織使用**>]，輸入 **microsoft 威脅防護**，然後選取 [ **microsoft 威脅防護**]。 您的應用程式現在可以存取 Microsoft 365 Defender。

   > [!TIP]
   > *Microsoft 威脅防護* 是 Microsoft 365 Defender 的先前名稱，因此不會出現在原始清單中。 您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。

   ![API 許可權選取的影像](../../media/apis-in-my-org-tab.PNG)

5. 選取 [ **應用程式許可權**]。 為您的案例選擇相關許可權 (例如， **Incident。 Read。 All**) ，然後選取 [ **新增許可權**]。

   ![API 存取和 API 選取的影像](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > 您必須選取案例的相關許可權。 *讀取所有的事件* 只是一個範例。 若要決定您需要的許可權，請參閱您想要呼叫之 API 中的 [ **許可權** ] 區段。
    >
    > 例如，若要 [執行高級查詢](api-advanced-hunting.md)，請選取「執行高級查詢」許可權;若要 [隔離裝置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)，請選取「隔離電腦」許可權。

6. 選取 **[授與系統管理員同意**]。 每次您新增許可權時，都必須選取 **[授與系統管理員同意** ]，才會生效。

    ![授與許可權的影像](../../media/grant-consent.PNG)

7. 若要將機密新增至應用程式，請選取 [ **憑證 & 密碼**]，新增描述至密碼，然後選取 [ **新增**]。

    > [!TIP]
    > 選取 [ **新增**] 之後，選取 **[複製產生的機密值**]。 離開後，您將無法取得密碼值。

    ![建立應用程式機碼的影像](../../media/webapp-create-key2.png)

8. 將您的應用程式識別碼和租使用者識別碼記錄在安全的位置。 在 [應用程式] 頁面的 **[一覽** ] 底下會列出它們。

   ![建立之應用程式識別碼的影像](../../media/app-and-tenant-ids.png)

9. 將應用程式新增至使用者的租使用者。

   因為您的應用程式代表您的使用者與 Microsoft 365 Defender 互動，所以需要針對您想要使用它的每一個承租人進行核准。

   使用者租使用者的 **全域系統管理員** 必須查看同意連結並核准您的應用程式。

   「同意」連結的格式如下：

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   `00000000-0000-0000-0000-000000000000`應以您的應用程式識別碼取代位數。

   按一下 [同意] 連結後，請使用使用者租使用者的全域管理員登入，並同意該應用程式。

   ![同意影像](../../media/app-consent-partner.png)

   您也需要向您的使用者索要其租使用者識別碼。 租使用者識別碼是用來取得存取權杖的其中一個識別碼。

- **做！** 您已成功註冊應用程式！
- 請參閱下列範例以取得及驗證權杖。

## <a name="get-an-access-token"></a>取得存取權杖

如需 Azure AD 標記的詳細資訊，請參閱 [AZURE ad 教學](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)課程。

> [!IMPORTANT]
> 雖然本節中的範例會鼓勵您貼上用於測試目的的機密值，否則您 **不應該將機密硬編碼** 成實際執行中執行的應用程式。 協力廠商可以使用您的機密存取資源。 您可以使用 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)，協助保護應用程式的機密。 如需如何保護應用程式的實際範例，請參閱 [使用 Azure Key Vault 管理伺服器應用程式中的機密](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)。

> [!TIP]
> 在下列範例中，請使用使用者的租使用者識別碼來測試腳本是否正常運作。

### <a name="get-an-access-token-using-powershell"></a>使用 PowerShell 取得存取權杖

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

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

### <a name="get-an-access-token-using-c"></a>使用 C 取得存取 token\#

> [!NOTE]
> 下列程式碼已使用 Nuget Windows.identitymodel.extensions.dll 進行測試。 ActiveDirectory 3.19.8。

1. 建立新的主控台應用程式。
1. 安裝 NuGet [windows.identitymodel.extensions.dll。 ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。
1. 新增下列行：

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 將下列程式碼複製並貼到您的應用程式中 (不要忘記更新這三個變數： `tenantId` ， `clientId` ， `appSecret`) ：

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a>使用 Python 取得存取權杖

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a>使用曲線取得存取權杖

> [!NOTE]
> 在 Windows 10 版本1803和更新版本上都預先安裝了卷。 若為其他版本的 Windows，請直接從 [官方卷網站](https://curl.haxx.se/windows/)下載並安裝工具。

1. 開啟命令提示字元，並將 CLIENT_ID 設定為您的 Azure 應用程式識別碼。
1. 將 CLIENT_SECRET 設定為您的 Azure 應用程式密碼。
1. 將 TENANT_ID 設定為要使用您的應用程式存取 Microsoft 365 Defender 之使用者的 Azure 租使用者識別碼。
1. 執行下列命令：

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

成功的回應如下所示：

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>驗證 token

1. 將權杖複製並貼到 [JSON web token 驗證者網站（JWT）](https://jwt.ms) 以進行解碼。
1. 請確定已解碼權杖中的 *角色* 宣告包含所需的許可權。

在下列影像中，您可以看到從應用程式取得的解碼標記，具有 ```Incidents.Read.All``` 、 ```Incidents.ReadWrite.All``` 和 ```AdvancedHunting.Read.All``` 許可權：

![權杖驗證的影像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>使用權杖來存取 Microsoft 365 Defender API

1. 選擇您想要使用 (事件或「高級搜尋) 的 API。 如需詳細資訊，請參閱 [支援的 Microsoft 365 Defender APIs](api-supported.md)。
2. 在您要傳送的 HTTP 要求中，將授權標頭設定為 `"Bearer" <token>` ， *持有* 者為授權配置，而 *token* 為您驗證的權杖。
3. 權杖會在一小時內到期。 在此期間，您可以使用相同的權杖傳送一個以上的要求。

下列範例顯示如何 **使用 c #** 傳送要求以取得事件清單。

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender APIs 概述](api-overview.md)
- [存取 Microsoft 365 Defender APIs](api-access.md)
- [建立 "Hello world" 應用程式](api-hello-world.md)
- [建立應用程式以存取沒有使用者的 Microsoft 365 Defender](api-create-app-web.md)
- [建立應用程式以代表使用者存取 Microsoft 365 Defender APIs](api-create-app-user-context.md)
- [深入瞭解 API 限制和授權](api-terms.md)
- [瞭解錯誤碼](api-error-codes.md)
- [使用 Azure Key Vault 管理伺服器應用程式中的機密](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0 使用者登入和 API 存取的授權](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
