---
title: 透過 Microsoft 威脅防護進行夥伴存取 APIs
description: 瞭解如何建立 AAD 應用程式，以對客戶以程式設計方式存取 Microsoft 威脅防護
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
ms.openlocfilehash: d78996c0cd37a6b82edde52367b04647560d5cf7
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650189"
---
# <a name="partner-access-through-microsoft-threat-protection-apis"></a><span data-ttu-id="dd97e-104">透過 Microsoft 威脅防護進行夥伴存取 APIs</span><span class="sxs-lookup"><span data-stu-id="dd97e-104">Partner access through Microsoft Threat Protection APIs</span></span>

<span data-ttu-id="dd97e-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="dd97e-105">**Applies to:**</span></span>
- <span data-ttu-id="dd97e-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="dd97e-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="dd97e-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="dd97e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="dd97e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="dd97e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="dd97e-109">此頁面說明如何建立 AAD 應用程式，以對客戶進行以程式設計方式存取 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="dd97e-109">This page describes how to create an AAD application to get programmatic access to Microsoft Threat Protection on behalf of your customers.</span></span>

<span data-ttu-id="dd97e-110">Microsoft 威脅防護會透過一組程式設計 APIs 來公開其資料和動作。</span><span class="sxs-lookup"><span data-stu-id="dd97e-110">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="dd97e-111">這些 APIs 會協助您根據 Microsoft 威脅防護功能來自動化工作流程與創新。</span><span class="sxs-lookup"><span data-stu-id="dd97e-111">Those APIs will help you automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="dd97e-112">API 存取需要 OAuth 2.0 驗證。</span><span class="sxs-lookup"><span data-stu-id="dd97e-112">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="dd97e-113">如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="dd97e-113">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="dd97e-114">一般來講，您必須採取下列步驟，才能使用 APIs：</span><span class="sxs-lookup"><span data-stu-id="dd97e-114">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="dd97e-115">建立 **多租** 使用者 AAD 應用程式。</span><span class="sxs-lookup"><span data-stu-id="dd97e-115">Create a **multi-tenant** AAD application.</span></span>
- <span data-ttu-id="dd97e-116">取得授權 (，由您的應用程式的客戶管理員) ，以存取所需的 Microsoft 威脅防護資源。</span><span class="sxs-lookup"><span data-stu-id="dd97e-116">Get authorized (consent) by your customer administrator for your application to access Microsoft Threat Protection resources it needs.</span></span>
- <span data-ttu-id="dd97e-117">使用此應用程式取得存取權杖。</span><span class="sxs-lookup"><span data-stu-id="dd97e-117">Get an access token using this application.</span></span>
- <span data-ttu-id="dd97e-118">使用權杖來存取 Microsoft 威脅防護 API。</span><span class="sxs-lookup"><span data-stu-id="dd97e-118">Use the token to access Microsoft Threat Protection API.</span></span>

<span data-ttu-id="dd97e-119">下列步驟會指導您如何建立 AAD 應用程式、取得 Microsoft 威脅防護的存取權杖，以及驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="dd97e-119">The following steps with guide you how to create an AAD application, get an access token to Microsoft Threat Protection and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="dd97e-120">建立多租使用者應用程式</span><span class="sxs-lookup"><span data-stu-id="dd97e-120">Create the multi-tenant app</span></span>

1. <span data-ttu-id="dd97e-121">使用具有**全域系統管理員**角色的使用者登入您的[Azure 租](https://portal.azure.com)使用者。</span><span class="sxs-lookup"><span data-stu-id="dd97e-121">Log on to your [Azure tenant](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="dd97e-122">流覽至 [ **Azure Active Directory**  >  **應用程式註冊**]  >  **新註冊**。</span><span class="sxs-lookup"><span data-stu-id="dd97e-122">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 的影像及應用程式註冊導覽](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="dd97e-124">在 [註冊] 表單中：</span><span class="sxs-lookup"><span data-stu-id="dd97e-124">In the registration form:</span></span>

    - <span data-ttu-id="dd97e-125">選擇應用程式的名稱。</span><span class="sxs-lookup"><span data-stu-id="dd97e-125">Choose a name for your application.</span></span>

    - <span data-ttu-id="dd97e-126">支援的帳戶類型-任何組織目錄中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="dd97e-126">Supported account types - accounts in any organizational directory.</span></span>

    - <span data-ttu-id="dd97e-127">重新導向 URI-類型： Web，URI： https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="dd97e-127">Redirect URI - type: Web, URI: https://portal.azure.com</span></span>

    ![Microsoft Azure partner application 註冊的影像](../../media/atp-api-new-app-partner.png)


4. <span data-ttu-id="dd97e-129">讓您的應用程式能夠存取 Microsoft 威脅防護，並將其指派給完成整合所需的最少一組許可權。</span><span class="sxs-lookup"><span data-stu-id="dd97e-129">Allow your Application to access Microsoft Threat Protection and assign it with the minimal set of permissions required to complete the integration.</span></span>

   - <span data-ttu-id="dd97e-130">在 [應用程式] 頁面上，按一下 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織] 使用**> 輸入**microsoft 威脅防護**，然後按一下 [ **microsoft 威脅防護**]。</span><span class="sxs-lookup"><span data-stu-id="dd97e-130">On your application page, click **API Permissions** > **Add permission** > **APIs my organization uses** > type **Microsoft Threat Protection** and click on **Microsoft Threat Protection**.</span></span>

   >[!NOTE]
   ><span data-ttu-id="dd97e-131">Microsoft 威脅防護不會出現在原始清單中。</span><span class="sxs-lookup"><span data-stu-id="dd97e-131">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="dd97e-132">您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。</span><span class="sxs-lookup"><span data-stu-id="dd97e-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 存取和 API 選取的影像](../../media/apis-in-my-org-tab.PNG)
   
   ### <a name="request-api-permissions"></a><span data-ttu-id="dd97e-134">要求 API 許可權</span><span class="sxs-lookup"><span data-stu-id="dd97e-134">Request API permissions</span></span>

   <span data-ttu-id="dd97e-135">若要決定您需要的許可權，請參閱您想要呼叫之 API 中的 [ **許可權** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="dd97e-135">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span> 

   <span data-ttu-id="dd97e-136">在下列範例中，我們將使用「 **讀取所有事件** 」許可權：</span><span class="sxs-lookup"><span data-stu-id="dd97e-136">In the following example we will use **'Read all incidents'** permission:</span></span>

   <span data-ttu-id="dd97e-137">選擇**應用程式許可權**  >  **事件。讀取。所有**> 按一下 [**新增許可權**]</span><span class="sxs-lookup"><span data-stu-id="dd97e-137">Choose **Application permissions** > **Incidents.Read.All** > Click on **Add permissions**</span></span>

   ![API 存取和 API 選取的影像](../../media/request-api-permissions.PNG)


5. <span data-ttu-id="dd97e-139">按一下 **[授與同意**]</span><span class="sxs-lookup"><span data-stu-id="dd97e-139">Click **Grant consent**</span></span>

    >[!NOTE]
    ><span data-ttu-id="dd97e-140">每次您新增許可權時，您必須按一下 **[授與同意** 才能讓新的許可權生效。</span><span class="sxs-lookup"><span data-stu-id="dd97e-140">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

    ![授與許可權的影像](../../media/grant-consent.PNG)

6. <span data-ttu-id="dd97e-142">將密碼新增至應用程式。</span><span class="sxs-lookup"><span data-stu-id="dd97e-142">Add a secret to the application.</span></span>

    - <span data-ttu-id="dd97e-143">按一下 [ **憑證 & 機密**]，將 description 新增至密碼，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="dd97e-143">Click **Certificates & secrets**, add description to the secret and click **Add**.</span></span>

    >[!IMPORTANT]
    > <span data-ttu-id="dd97e-144">選取 [ **新增**] 之後，請 **複製產生的密碼值**。</span><span class="sxs-lookup"><span data-stu-id="dd97e-144">After selecting **Add**, **copy the generated secret value**.</span></span> <span data-ttu-id="dd97e-145">離開後，您將無法進行找回！</span><span class="sxs-lookup"><span data-stu-id="dd97e-145">You won't be able to retrieve after you leave!</span></span>

    ![建立應用程式機碼的影像](../../media/webapp-create-key2.png)

7. <span data-ttu-id="dd97e-147">記下來記錄應用程式 ID:</span><span class="sxs-lookup"><span data-stu-id="dd97e-147">Write down your application ID:</span></span>

   - <span data-ttu-id="dd97e-148">在 [應用程式] 頁面上，移至 **[簡介** ]，然後複製下列專案：</span><span class="sxs-lookup"><span data-stu-id="dd97e-148">On your application page, go to **Overview** and copy the following:</span></span>

   ![建立之應用程式識別碼的影像](../../media/app-id.png)

8. <span data-ttu-id="dd97e-150">將應用程式新增至客戶的承租人。</span><span class="sxs-lookup"><span data-stu-id="dd97e-150">Add the application to your customer's tenant.</span></span>

    <span data-ttu-id="dd97e-151">您必須在您要使用的每個客戶承租人中核准您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="dd97e-151">You need your application to be approved in each customer tenant where you intend to use it.</span></span> <span data-ttu-id="dd97e-152">這是因為您的應用程式代表客戶與 Microsoft 威脅防護應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="dd97e-152">This is because your application interacts with Microsoft Threat Protection application on behalf of your customer.</span></span>

    <span data-ttu-id="dd97e-153">擁有客戶之租使用者之 **全域管理員** 的使用者，必須按一下 [同意] 連結並核准您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="dd97e-153">A user with **Global Administrator** from your customer's tenant need to click the consent link and approve your application.</span></span>

    <span data-ttu-id="dd97e-154">「同意」連結的格式如下：</span><span class="sxs-lookup"><span data-stu-id="dd97e-154">Consent link is of the form:</span></span>

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="dd97e-155">其中00000000-0000-0000-0000-000000000000 應該會取代為您的應用程式識別碼</span><span class="sxs-lookup"><span data-stu-id="dd97e-155">Where 00000000-0000-0000-0000-000000000000 should be replaced with your Application ID</span></span>

    <span data-ttu-id="dd97e-156">按一下 [同意] 連結後，請使用客戶租使用者的全域管理員登入，並同意該應用程式。</span><span class="sxs-lookup"><span data-stu-id="dd97e-156">After clicking on the consent link, login with the Global Administrator of the customer's tenant and consent the application.</span></span>

    ![同意影像](../../media/app-consent-partner.png)

    <span data-ttu-id="dd97e-158">此外，您需要向客戶尋求其租使用者識別碼，並將其儲存以供日後用於取得權杖。</span><span class="sxs-lookup"><span data-stu-id="dd97e-158">In addition, you will need to ask your customer for their tenant ID and save it for future use when acquiring the token.</span></span>

- <span data-ttu-id="dd97e-159">**做！**</span><span class="sxs-lookup"><span data-stu-id="dd97e-159">**Done!**</span></span> <span data-ttu-id="dd97e-160">您已成功註冊應用程式！</span><span class="sxs-lookup"><span data-stu-id="dd97e-160">You have successfully registered an application!</span></span> 
- <span data-ttu-id="dd97e-161">請參閱下列範例以取得及驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="dd97e-161">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token-examples"></a><span data-ttu-id="dd97e-162">取得存取 token 範例：</span><span class="sxs-lookup"><span data-stu-id="dd97e-162">Get an access token examples:</span></span>

>[!NOTE]
> <span data-ttu-id="dd97e-163">若要代表客戶取得存取權杖，請在下列標記上使用客戶的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="dd97e-163">To get access token on behalf of your customer, use the customer's tenant ID on the following token acquisitions.</span></span>

<br><span data-ttu-id="dd97e-164">如需 AAD 權杖的詳細資訊，請參閱[AAD 教學](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)課程</span><span class="sxs-lookup"><span data-stu-id="dd97e-164">For more details on AAD token, refer to [AAD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span></span>

### <a name="using-powershell"></a><span data-ttu-id="dd97e-165">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd97e-165">Using PowerShell</span></span>

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

### <a name="using-c"></a><span data-ttu-id="dd97e-166">使用 c #：</span><span class="sxs-lookup"><span data-stu-id="dd97e-166">Using C#:</span></span>

><span data-ttu-id="dd97e-167">下列程式碼已使用 Nuget Windows.identitymodel.extensions.dll 進行測試。 ActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="dd97e-167">The below code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory</span></span>

- <span data-ttu-id="dd97e-168">建立新的主控台應用程式</span><span class="sxs-lookup"><span data-stu-id="dd97e-168">Create a new Console Application</span></span>
- <span data-ttu-id="dd97e-169">安裝 Nuget [windows.identitymodel.extensions.dll ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span><span class="sxs-lookup"><span data-stu-id="dd97e-169">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span></span>
- <span data-ttu-id="dd97e-170">使用下列新增</span><span class="sxs-lookup"><span data-stu-id="dd97e-170">Add the below using</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- <span data-ttu-id="dd97e-171">在應用程式中複製/貼上下列程式碼 (請勿忘記更新3個變數： ```tenantId, appId, appSecret```) </span><span class="sxs-lookup"><span data-stu-id="dd97e-171">Copy/Paste the below code in your application (do not forget to update the 3 variables: ```tenantId, appId, appSecret```)</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string mtpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(mtpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```



### <a name="using-curl"></a><span data-ttu-id="dd97e-172">使用捲曲</span><span class="sxs-lookup"><span data-stu-id="dd97e-172">Using Curl</span></span>

> [!NOTE]
> <span data-ttu-id="dd97e-173">下列程式會在您的電腦上安裝已安裝 Windows 的卷</span><span class="sxs-lookup"><span data-stu-id="dd97e-173">The below procedure supposed Curl for Windows is already installed on your computer</span></span>

- <span data-ttu-id="dd97e-174">開啟命令視窗</span><span class="sxs-lookup"><span data-stu-id="dd97e-174">Open a command window</span></span>
- <span data-ttu-id="dd97e-175">將 CLIENT_ID 設定為您的 Azure 應用程式識別碼</span><span class="sxs-lookup"><span data-stu-id="dd97e-175">Set CLIENT_ID to your Azure application ID</span></span>
- <span data-ttu-id="dd97e-176">將 CLIENT_SECRET 設定為您的 Azure 應用程式機密</span><span class="sxs-lookup"><span data-stu-id="dd97e-176">Set CLIENT_SECRET to your Azure application secret</span></span>
- <span data-ttu-id="dd97e-177">將 TENANT_ID 設定為想要使用應用程式來存取 Microsoft 威脅防護應用程式之客戶的 Azure 租使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="dd97e-177">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your application to access Microsoft Threat Protection application</span></span>
- <span data-ttu-id="dd97e-178">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dd97e-178">Run the below command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="dd97e-179">您會收到下列表單的答案：</span><span class="sxs-lookup"><span data-stu-id="dd97e-179">You will get an answer of the form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="dd97e-180">驗證 token</span><span class="sxs-lookup"><span data-stu-id="dd97e-180">Validate the token</span></span>

<span data-ttu-id="dd97e-181">健全檢查以確認您獲得正確的權杖：</span><span class="sxs-lookup"><span data-stu-id="dd97e-181">Sanity check to make sure you got a correct token:</span></span>

- <span data-ttu-id="dd97e-182">複製/貼上您在上一個步驟中 [取得的標記](https://jwt.ms) ，以便進行解碼</span><span class="sxs-lookup"><span data-stu-id="dd97e-182">Copy/paste into [JWT](https://jwt.ms) the token you get in the previous step in order to decode it</span></span>
- <span data-ttu-id="dd97e-183">驗證您取得所需許可權的「role」宣告</span><span class="sxs-lookup"><span data-stu-id="dd97e-183">Validate you get a 'roles' claim with the desired permissions</span></span>
- <span data-ttu-id="dd97e-184">在下列螢幕擷取畫面中，您可以看到從應用程式取得的解碼標記，具有對 Microsoft 威脅防護的多個許可權：</span><span class="sxs-lookup"><span data-stu-id="dd97e-184">In the screenshot below, you can see a decoded token acquired from an Application with multiple permissions to Microsoft Threat Protection:</span></span>
- <span data-ttu-id="dd97e-185">「Tid」宣告是識別碼所屬的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="dd97e-185">The "tid" claim is the tenant ID the token belongs to.</span></span>

![權杖驗證的影像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a><span data-ttu-id="dd97e-187">使用權杖存取 Microsoft 威脅防護 API</span><span class="sxs-lookup"><span data-stu-id="dd97e-187">Use the token to access Microsoft Threat Protection API</span></span>

- <span data-ttu-id="dd97e-188">選擇您要使用的 API，如需詳細資訊，請參閱 [支援的 Microsoft 威脅防護 APIs](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="dd97e-188">Choose the API you want to use, for more information, see [Supported Microsoft Threat Protection APIs](api-supported.md)</span></span>
- <span data-ttu-id="dd97e-189">在您傳送至 "載荷 {token}" 的 Http 要求中設定授權標頭 (載荷是授權配置) </span><span class="sxs-lookup"><span data-stu-id="dd97e-189">Set the Authorization header in the Http request you send to "Bearer {token}" (Bearer is the Authorization scheme)</span></span>
- <span data-ttu-id="dd97e-190">權杖的到期時間是1小時 (您可以使用相同的權杖傳送一個以上的要求) </span><span class="sxs-lookup"><span data-stu-id="dd97e-190">The Expiration time of the token is 1 hour (you can send more then one request with the same token)</span></span>

- <span data-ttu-id="dd97e-191">**使用 c #** 傳送要求以取得事件清單的範例</span><span class="sxs-lookup"><span data-stu-id="dd97e-191">Example of sending a request to get a list of incidents **using C#**</span></span> 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="related-topics"></a><span data-ttu-id="dd97e-192">相關主題</span><span class="sxs-lookup"><span data-stu-id="dd97e-192">Related topics</span></span> 

- [<span data-ttu-id="dd97e-193">存取 Microsoft 威脅防護 APIs</span><span class="sxs-lookup"><span data-stu-id="dd97e-193">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="dd97e-194">使用應用程式內容存取 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="dd97e-194">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="dd97e-195">使用使用者內容存取 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="dd97e-195">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
