---
title: 建立應用程式以存取 Microsoft Defender for Endpoint （不含使用者）
ms.reviewer: ''
description: 瞭解如何設計 web 應用程式，以在沒有使用者的情況下，對 Microsoft Defender for Endpoint 進行程式設計存取。
keywords: api，graph api，支援的 api，主角，警示，裝置，使用者，網域，ip，file，advanced 搜尋，查詢
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 695dfbec007b259b7daec2346201737d57c4ad30
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289772"
---
# <a name="partner-access-through-microsoft-defender-for-endpoint-apis"></a>透過 Microsoft Defender for Endpoint APIs 取得夥伴存取權

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

此頁面說明如何建立 Azure Active Directory (Azure AD) 應用程式，以將代表客戶以程式設計方式存取 Microsoft Defender for Endpoint。


Microsoft Defender for Endpoint 會透過一組程式設計 APIs 公開其資料和動作。 這些 APIs 會協助您根據 Microsoft Defender for Endpoint 功能來自動化工作流程與創新。 API 存取需要 OAuth 2.0 驗證。 如需詳細資訊，請參閱[OAuth 2.0 授權碼 Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

一般來講，您必須採取下列步驟，才能使用 APIs：
- 建立 **多承租人** Azure AD 應用程式。
- 取得授權 (您的客戶管理員為您的應用程式) 存取所需的端點資源的授權。
- 使用此應用程式取得存取權杖。
- 使用權杖來存取 Microsoft Defender for Endpoint API。

下列步驟會引導您如何建立 Azure AD 應用程式、取得 Microsoft Defender for Endpoint 的存取權杖，以及驗證權杖。

## <a name="create-the-multi-tenant-app"></a>建立多租使用者應用程式

1. 使用具有 **全域系統管理員** 角色的使用者登入您的 [Azure 租](https://portal.azure.com)使用者。

2. 流覽至 **Azure Active Directory**  >  **App 註冊**  >  **新註冊**。 

   ![Microsoft Azure 及流覽至應用程式註冊的影像](images/atp-azure-new-app2.png)

3. 在 [註冊] 表單中：

   - 選擇應用程式的名稱。

   - 支援的帳戶類型-任何組織目錄中的帳戶。

   - 重新導向 URI-類型： Web，URI： https://portal.azure.com

   ![Microsoft Azure 夥伴應用程式註冊的影像](images/atp-api-new-app-partner.png)


4. 讓您的應用程式能夠存取 Microsoft Defender for Endpoint，並將其指派為完成整合所需的最少一組許可權。

   - 在 [應用程式] 頁面上，選取 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織使用**> 類型 **WindowsDefenderATP** ]，然後選取 [ **WindowsDefenderATP**]。

   - **附注**： *WindowsDefenderATP* 不會出現在原始清單中。 開始在文字方塊中寫入其名稱，以查看顯示。

   ![新增許可權](images/add-permission.png)
   
   ### <a name="request-api-permissions"></a>要求 API 許可權

   若要決定您需要的許可權，請複查您要呼叫之 API 中的 [ **許可權** ] 區段。 例如：

   - 若要 [執行高級查詢](run-advanced-query-api.md)，請選取「執行高級查詢」許可權
   
   - 若要 [隔離裝置](isolate-machine.md)，請選取「隔離電腦」許可權

   在下列範例中，我們將使用「 **讀取所有警示** 」許可權：

   選擇 [**應用程式許可權**] [已  >  **讀取]。所有**> 在 [**新增] 許可權** 上選取

   ![應用程式許可權](images/application-permissions.png)


5. 選取 **[授與同意**]

   - **附注**：每次您新增許可權時，您必須選取 **[授與同意** 才能讓新許可權同意]。

   ![授與許可權的影像](images/grant-consent.png)

6. 將密碼新增至應用程式。

   - 選取 [ **& 密碼的憑證**]，將 description 新增至 [密碼]，然後選取 [ **新增**]。

    **重要** 事項：按一下 [新增] 後，請 **複製產生的機密值**。 離開後，您將無法進行找回！

    ![建立應用程式機碼的影像](images/webapp-create-key2.png)

7. 記下來記錄應用程式 ID:

   - 在 [應用程式] 頁面上，移至 **[簡介** ]，然後複製下列資訊：

   ![建立之應用程式識別碼的影像](images/app-id.png)

8. 將應用程式新增至客戶的承租人。

   您必須在您要使用的每個客戶承租人中核准您的應用程式。 這是因為您的應用程式代表客戶與 Microsoft Defender for Endpoint application 互動。

   具有客戶租使用者之 **全域管理員** 的使用者，必須選取同意連結並核准您的應用程式。

   「同意」連結的格式如下：

   ```http
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   其中00000000-0000-0000-0000-000000000000 應該會取代為您的應用程式識別碼

   按一下 [同意] 連結後，請使用客戶租使用者的全域管理員登入，並同意該應用程式。

   ![同意影像](images/app-consent-partner.png)

   此外，您需要向客戶尋求其租使用者識別碼，並將其儲存以供日後用於取得權杖。

- **做！** 您已成功註冊應用程式！
- 請參閱下列範例以取得及驗證權杖。

## <a name="get-an-access-token-example"></a>取得存取 token 範例

**附注：** 若要代表客戶取得存取權杖，請在下列標記上使用客戶的租使用者識別碼。

如需 AAD 權杖的詳細資訊，請參閱[aad 教學](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)課程

### <a name="using-powershell"></a>使用 PowerShell

```powershell
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

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

### <a name="using-c"></a>使用 C#

> 下列程式碼已使用 Nuget Windows.identitymodel.extensions.dll 進行測試。 ActiveDirectory

- 建立新的主控台應用程式
- 安裝 NuGet [windows.identitymodel.extensions.dll。 ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
- 使用下列新增

    ```console
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- 在應用程式中複製/貼上下列程式碼 (請勿忘記更新下列三個變數： `tenantId` 、 `appId` 和 `appSecret`) 

    ```console
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.microsoftonline.com";
    const string wdatpResourceId = "https://api.securitycenter.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="using-python"></a>使用 Python

[使用 Python 參考 Get token](run-advanced-query-sample-python.md#get-token)

### <a name="using-curl"></a>使用捲曲

> [!NOTE]
> 以下是已安裝在電腦上的 Windows 程式的卷

- 開啟命令視窗
- 將 CLIENT_ID 設定為您的 Azure 應用程式識別碼
- 將 CLIENT_SECRET 設定為您的 Azure 應用程式機密
- 將 TENANT_ID 設定為想要使用應用程式來存取 Microsoft Defender for Endpoint 應用程式之客戶的 Azure 租使用者識別碼
- 執行下列命令：

```curl
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

您會收到下列表單的答案：

```console
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>驗證 token

健全檢查以確認您獲得正確的權杖：

- 複製/貼上您在上一個步驟中 [取得的標記](https://jwt.ms) ，以便進行解碼
- 驗證您取得所需許可權的「role」宣告
- 在下列螢幕擷取畫面中，您可以看到從應用程式取得的解碼標記，具有對 Microsoft Defender for Endpoint 的多個許可權：
- 「Tid」宣告是識別碼所屬的租使用者識別碼。

![權杖驗證的影像](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>使用權杖來存取 Microsoft Defender for Endpoint API

- 選擇您要使用的 API，如需詳細資訊，請參閱 [支援的 Microsoft Defender For Endpoint APIs](exposed-apis-list.md)
- 在您傳送至 "載荷 {token}" 的 Http 要求中設定授權標頭 (載荷是授權配置) 
- 權杖的到期時間是1小時 (您可以使用相同的權杖傳送一個以上的要求) 

- **使用 c #** 傳送要求以取得警示清單的範例

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>另請參閱

- [受支援的適用於端點的 Microsoft Defender API](exposed-apis-list.md)
- [代表使用者存取 Microsoft Defender for Endpoint](exposed-apis-create-app-nativeapp.md)
