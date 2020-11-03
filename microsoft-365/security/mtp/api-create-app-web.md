---
title: 建立應用程式以存取沒有使用者的 Microsoft 365 Defender
description: 瞭解如何建立應用程式以存取未使用使用者的 Microsoft 365 Defender
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
ms.openlocfilehash: 446db803cc47bfd519642928a4a0257c4b3d57c8
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846065"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="7d23c-104">建立應用程式以存取沒有使用者的 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d23c-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7d23c-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="7d23c-105">**Applies to:**</span></span>
- <span data-ttu-id="7d23c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d23c-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="7d23c-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="7d23c-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7d23c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="7d23c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="7d23c-109">此頁面說明如何建立應用程式，以在沒有使用者的情況下，取得 Microsoft 365 Defender 的程式設計存取權。</span><span class="sxs-lookup"><span data-stu-id="7d23c-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a user.</span></span> <span data-ttu-id="7d23c-110">如果您需要以程式設計方式代表使用者存取 Microsoft 365 Defender，請參閱 [Get access with user coNtext](api-create-app-user-context.md)。</span><span class="sxs-lookup"><span data-stu-id="7d23c-110">If you need programmatic access to Microsoft 365 Defender on behalf of a user, see [Get access with user context](api-create-app-user-context.md).</span></span> <span data-ttu-id="7d23c-111">如果您不確定需要哪一種存取權，請參閱 [入門](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="7d23c-111">If you are not sure which access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="7d23c-112">Microsoft 365 Defender 會透過一組程式設計 APIs 來公開其大部分資料和動作。</span><span class="sxs-lookup"><span data-stu-id="7d23c-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="7d23c-113">這些 APIs 會協助您根據 Microsoft 365 Defender 功能自動化工作流程與創新。</span><span class="sxs-lookup"><span data-stu-id="7d23c-113">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="7d23c-114">API 存取需要 OAuth 2.0 驗證。</span><span class="sxs-lookup"><span data-stu-id="7d23c-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="7d23c-115">如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="7d23c-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="7d23c-116">一般來講，您必須採取下列步驟，才能使用 APIs：</span><span class="sxs-lookup"><span data-stu-id="7d23c-116">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="7d23c-117">建立 Azure Active Directory (Azure AD) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7d23c-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="7d23c-118">使用此應用程式取得存取權杖。</span><span class="sxs-lookup"><span data-stu-id="7d23c-118">Get an access token using this application.</span></span>
- <span data-ttu-id="7d23c-119">使用權杖來存取 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="7d23c-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="7d23c-120">本文說明如何建立 Azure AD 應用程式、取得 Microsoft 365 Defender 的存取權杖，以及驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="7d23c-120">This article explains how to create an Azure AD application, get an access token to Microsoft 365 Defender, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="7d23c-121">建立應用程式</span><span class="sxs-lookup"><span data-stu-id="7d23c-121">Create an app</span></span>

1. <span data-ttu-id="7d23c-122">使用具有 **全域系統管理員** 角色的使用者登入 [Azure](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="7d23c-122">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="7d23c-123">流覽至 [ **Azure Active Directory**  >  **應用程式註冊** ]  >  **新註冊** 。</span><span class="sxs-lookup"><span data-stu-id="7d23c-123">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 的影像及應用程式註冊導覽](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="7d23c-125">在 [註冊] 表單中，選擇應用程式的名稱，然後選取 [ **註冊** ]。</span><span class="sxs-lookup"><span data-stu-id="7d23c-125">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="7d23c-126">若要讓您的應用程式能夠存取 Microsoft 365 Defender 並指派 it 許可權，請在應用程式頁面上，選取 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織使用** >]，輸入 [ **microsoft 365 Defender** ]，然後選取 [ **microsoft 365 Defender** ]。</span><span class="sxs-lookup"><span data-stu-id="7d23c-126">To enable your app to access Microsoft 365 Defender and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft 365 Defender** , and then select **Microsoft 365 Defender**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7d23c-127">Microsoft 365 Defender 未出現在原始清單中。</span><span class="sxs-lookup"><span data-stu-id="7d23c-127">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="7d23c-128">您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。</span><span class="sxs-lookup"><span data-stu-id="7d23c-128">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 存取和 API 選取的影像](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="7d23c-130">選取 [ **應用程式許可權** ] > 選擇您案例的相關許可權，例如 **Incident。 Read。 All** ，然後選取 [ **新增許可權** ]。</span><span class="sxs-lookup"><span data-stu-id="7d23c-130">Select **Application permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read.All** , and then select **Add permissions**.</span></span>

   ![API 存取和 API 選取的影像](../../media/request-api-permissions.PNG)

    >[!NOTE]
    ><span data-ttu-id="7d23c-132">您需要為案例選取相關許可權，「 **讀取所有事件** 」只是一個範例。</span><span class="sxs-lookup"><span data-stu-id="7d23c-132">You need to select the relevant permissions for your scenario, **'Read all incidents'** is just an example.</span></span> <span data-ttu-id="7d23c-133">若要決定您需要的許可權，請參閱您想要呼叫之 API 中的 [ **許可權** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="7d23c-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="7d23c-134">選取 **[授與同意** ]。</span><span class="sxs-lookup"><span data-stu-id="7d23c-134">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="7d23c-135">每當您新增許可權時，您必須選取 **[授與同意** ]，新許可權才會生效。</span><span class="sxs-lookup"><span data-stu-id="7d23c-135">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![授與許可權的影像](../../media/grant-consent.PNG)

6. <span data-ttu-id="7d23c-137">若要將機密新增至應用程式，請選取 [ **憑證 & 機密** ]，新增 [密碼] 的描述，然後選取 [ **新增** ]。</span><span class="sxs-lookup"><span data-stu-id="7d23c-137">To add a secret to the application, select **Certificates & secrets** , add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d23c-138">選取 [ **新增** ] 之後，選取 **[複製產生的機密值** ]。</span><span class="sxs-lookup"><span data-stu-id="7d23c-138">After you select **Add** , select **copy the generated secret value**.</span></span> <span data-ttu-id="7d23c-139">離開後，您將無法取回此值。</span><span class="sxs-lookup"><span data-stu-id="7d23c-139">You won't be able to retrieve this value after you leave.</span></span>

    ![建立應用程式機碼的影像](../../media/webapp-create-key2.png)

7. <span data-ttu-id="7d23c-141">記下來記錄應用程式識別碼和您的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="7d23c-141">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="7d23c-142">在 [應用程式] 頁面上，移至 **[簡介** ]，然後複製下列各項。</span><span class="sxs-lookup"><span data-stu-id="7d23c-142">On your application page, go to **Overview** and copy the following.</span></span>

   ![建立之應用程式識別碼的影像](../../media/app-and-tenant-ids.png)

8. <span data-ttu-id="7d23c-144">**僅適用于 Microsoft 365 Defender 合作夥伴** 。</span><span class="sxs-lookup"><span data-stu-id="7d23c-144">**For Microsoft 365 Defender Partners only**.</span></span> <span data-ttu-id="7d23c-145">[請依照這裡的指示](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access)進行。</span><span class="sxs-lookup"><span data-stu-id="7d23c-145">[Follow the instructions here](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span></span> <span data-ttu-id="7d23c-146">將您的應用程式設為多 tenanted (在同意) 後，所有承租人皆可使用。</span><span class="sxs-lookup"><span data-stu-id="7d23c-146">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="7d23c-147">這是協力廠商應用程式 **所需** 的 (例如，如果您建立要在多個客戶的承租人) 中執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7d23c-147">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="7d23c-148">如果您建立只想要在租使用者中執行的服務，這 **不是必要** 的 (例如，如果您為自己的使用方式建立應用程式，只會與您自己的資料) 互動。</span><span class="sxs-lookup"><span data-stu-id="7d23c-148">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="7d23c-149">若要將您的應用程式設為多 tenanted：</span><span class="sxs-lookup"><span data-stu-id="7d23c-149">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="7d23c-150">移至 [ **驗證** ]，然後新增 https://portal.azure.com 為重新 **導向 URI** 。</span><span class="sxs-lookup"><span data-stu-id="7d23c-150">Go to **Authentication** , and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="7d23c-151">在頁面底部的 [ **支援的帳戶類型** ] 底下，選取您的多租使用者應用程式的 **任何組織目錄** 應用程式中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7d23c-151">On the bottom of the page, under **Supported account types** , select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="7d23c-152">您必須在您要使用的每個承租人中核准您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7d23c-152">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="7d23c-153">這是因為您的應用程式代表客戶與 Microsoft 365 Defender 互動。</span><span class="sxs-lookup"><span data-stu-id="7d23c-153">This is because your application interacts Microsoft 365 Defender on behalf of your customer.</span></span>

    <span data-ttu-id="7d23c-154">當您撰寫協力廠商應用程式時，您 (或客戶) 必須選取同意連結並核准您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7d23c-154">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="7d23c-155">使用 Active Directory 中具有系統管理許可權的使用者，應進行同意。</span><span class="sxs-lookup"><span data-stu-id="7d23c-155">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="7d23c-156">「同意」連結的成形如下：</span><span class="sxs-lookup"><span data-stu-id="7d23c-156">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="7d23c-157">其中00000000-0000-0000-0000-000000000000 會取代為您的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="7d23c-157">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="7d23c-158">**做！**</span><span class="sxs-lookup"><span data-stu-id="7d23c-158">**Done!**</span></span> <span data-ttu-id="7d23c-159">您已成功註冊應用程式！</span><span class="sxs-lookup"><span data-stu-id="7d23c-159">You have successfully registered an application!</span></span> <span data-ttu-id="7d23c-160">請參閱下列範例以取得及驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="7d23c-160">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="7d23c-161">取得存取權杖</span><span class="sxs-lookup"><span data-stu-id="7d23c-161">Get an access token</span></span>

<span data-ttu-id="7d23c-162">如需 Azure AD 標記的詳細資訊，請參閱 [AZURE ad 教學](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)課程。</span><span class="sxs-lookup"><span data-stu-id="7d23c-162">For more details on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="7d23c-163">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d23c-163">Use PowerShell</span></span>

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

### <a name="use-c"></a><span data-ttu-id="7d23c-164">使用 c #：</span><span class="sxs-lookup"><span data-stu-id="7d23c-164">Use C#:</span></span>

<span data-ttu-id="7d23c-165">下列程式碼已使用 Nuget Windows.identitymodel.extensions.dll 進行測試。 ActiveDirectory 3.19.8。</span><span class="sxs-lookup"><span data-stu-id="7d23c-165">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="7d23c-166">建立新的主控台應用程式。</span><span class="sxs-lookup"><span data-stu-id="7d23c-166">Create a new console application.</span></span>
1. <span data-ttu-id="7d23c-167">安裝 Nuget [windows.identitymodel.extensions.dll ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。</span><span class="sxs-lookup"><span data-stu-id="7d23c-167">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="7d23c-168">新增下列專案：</span><span class="sxs-lookup"><span data-stu-id="7d23c-168">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="7d23c-169">在應用程式中複製並貼上下列程式碼 (請勿忘記更新三個變數： ```tenantId, appId, appSecret```) ：</span><span class="sxs-lookup"><span data-stu-id="7d23c-169">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

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


### <a name="use-python"></a><span data-ttu-id="7d23c-170">使用 Python</span><span class="sxs-lookup"><span data-stu-id="7d23c-170">Use Python</span></span> 

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
### <a name="use-curl"></a><span data-ttu-id="7d23c-171">使用捲曲</span><span class="sxs-lookup"><span data-stu-id="7d23c-171">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="7d23c-172">下列程式假設已在您的電腦上安裝了 Windows 的卷。</span><span class="sxs-lookup"><span data-stu-id="7d23c-172">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="7d23c-173">開啟命令提示字元，並將 CLIENT_ID 設定為您的 Azure 應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="7d23c-173">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="7d23c-174">將 CLIENT_SECRET 設定為您的 Azure 應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="7d23c-174">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="7d23c-175">將 TENANT_ID 設定為要使用您的應用程式存取 Microsoft 365 Defender 之客戶的 Azure 租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="7d23c-175">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="7d23c-176">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7d23c-176">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="7d23c-177">您會收到下列形式的答案：</span><span class="sxs-lookup"><span data-stu-id="7d23c-177">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="7d23c-178">驗證 token</span><span class="sxs-lookup"><span data-stu-id="7d23c-178">Validate the token</span></span>

<span data-ttu-id="7d23c-179">確定您獲得正確的權杖：</span><span class="sxs-lookup"><span data-stu-id="7d23c-179">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="7d23c-180">將您在上一個步驟中所掌握的權杖複製並貼上至 [JWT](https://jwt.ms) ，以便進行解碼。</span><span class="sxs-lookup"><span data-stu-id="7d23c-180">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="7d23c-181">確認您取得了所需許可權的「role」宣告</span><span class="sxs-lookup"><span data-stu-id="7d23c-181">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="7d23c-182">在下列影像中，您可以看到使用的應用程式取得的解碼標記 ```Incidents.Read.All``` ， ```Incidents.ReadWrite.All``` 以及 ```AdvancedHunting.Read.All``` 許可權：</span><span class="sxs-lookup"><span data-stu-id="7d23c-182">In the following image, you can see a decoded token acquired from an app with ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions:</span></span>

![權杖驗證的影像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-365-defender-api"></a><span data-ttu-id="7d23c-184">使用權杖來存取 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="7d23c-184">Use the token to access Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="7d23c-185">選擇您要使用的 API。</span><span class="sxs-lookup"><span data-stu-id="7d23c-185">Choose the API you want to use.</span></span> <span data-ttu-id="7d23c-186">如需詳細資訊，請參閱 [支援的 Microsoft 365 Defender APIs](api-supported.md)。</span><span class="sxs-lookup"><span data-stu-id="7d23c-186">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="7d23c-187">在您傳送至 "載荷 {token}" 的 HTTP 要求中設定授權標頭。 (載荷是授權配置) 。</span><span class="sxs-lookup"><span data-stu-id="7d23c-187">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>

3. <span data-ttu-id="7d23c-188">權杖的到期時間是一小時。</span><span class="sxs-lookup"><span data-stu-id="7d23c-188">The expiration time of the token is one hour.</span></span> <span data-ttu-id="7d23c-189">您可以使用相同的權杖傳送一個以上的要求。</span><span class="sxs-lookup"><span data-stu-id="7d23c-189">You can send more then one request with the same token.</span></span>

<span data-ttu-id="7d23c-190">以下是 **使用 c #** 傳送要求以取得事件清單的範例：</span><span class="sxs-lookup"><span data-stu-id="7d23c-190">The following is an example of sending a request to get a list of incidents **using C#** :</span></span> 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a><span data-ttu-id="7d23c-191">相關主題</span><span class="sxs-lookup"><span data-stu-id="7d23c-191">Related topics</span></span>
- [<span data-ttu-id="7d23c-192">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="7d23c-192">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="7d23c-193">使用應用程式內容存取 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d23c-193">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="7d23c-194">使用使用者內容存取 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d23c-194">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
