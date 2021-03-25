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
ms.technology: mde
ms.openlocfilehash: 8f480a148d72428c6346930a91358d1e8b674ee7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200002"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a><span data-ttu-id="6e073-104">建立應用程式以存取 Microsoft Defender for Endpoint （不含使用者）</span><span class="sxs-lookup"><span data-stu-id="6e073-104">Create an app to access Microsoft Defender for Endpoint without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6e073-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6e073-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="6e073-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6e073-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6e073-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="6e073-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="6e073-108">此頁面說明如何建立應用程式，以在沒有使用者的情況下，取得端點的程式設計存取權。</span><span class="sxs-lookup"><span data-stu-id="6e073-108">This page describes how to create an application to get programmatic access to Defender for Endpoint without a user.</span></span> <span data-ttu-id="6e073-109">如果您需要代表使用者以程式設計方式存取 Defender for Endpoint，請參閱 [Get access with user coNtext](exposed-apis-create-app-nativeapp.md)。</span><span class="sxs-lookup"><span data-stu-id="6e073-109">If you need programmatic access to Defender for Endpoint on behalf of a user, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span> <span data-ttu-id="6e073-110">如果您不確定需要哪一種存取權，請參閱 [入門](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="6e073-110">If you are not sure which access you need, see [Get started](apis-intro.md).</span></span>

<span data-ttu-id="6e073-111">Microsoft Defender for Endpoint 會透過一組程式設計 APIs 公開其資料和動作。</span><span class="sxs-lookup"><span data-stu-id="6e073-111">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="6e073-112">這些 APIs 會協助您根據使用 Defender for Endpoint 功能自動化工作流程與創新。</span><span class="sxs-lookup"><span data-stu-id="6e073-112">Those APIs will help you automate work flows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="6e073-113">API 存取需要 OAuth 2.0 驗證。</span><span class="sxs-lookup"><span data-stu-id="6e073-113">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="6e073-114">如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="6e073-114">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="6e073-115">一般來講，您必須採取下列步驟，才能使用 APIs：</span><span class="sxs-lookup"><span data-stu-id="6e073-115">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="6e073-116">建立 Azure Active Directory (Azure AD) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="6e073-116">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="6e073-117">使用此應用程式取得存取權杖。</span><span class="sxs-lookup"><span data-stu-id="6e073-117">Get an access token using this application.</span></span>
- <span data-ttu-id="6e073-118">使用權杖來存取適用于 Endpoint API 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="6e073-118">Use the token to access Defender for Endpoint API.</span></span>

<span data-ttu-id="6e073-119">本文說明如何建立 Azure AD 應用程式、取得 Microsoft Defender for Endpoint 的存取權杖，以及驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="6e073-119">This article explains how to create an Azure AD application, get an access token to Microsoft Defender for Endpoint, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="6e073-120">建立應用程式</span><span class="sxs-lookup"><span data-stu-id="6e073-120">Create an app</span></span>

1. <span data-ttu-id="6e073-121">使用具有 **全域系統管理員** 角色的使用者登入 [Azure](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="6e073-121">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="6e073-122">流覽至 [ **Azure Active Directory**  >  **應用程式註冊**]  >  **新註冊**。</span><span class="sxs-lookup"><span data-stu-id="6e073-122">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 的影像及應用程式註冊導覽](images/atp-azure-new-app2.png)

3. <span data-ttu-id="6e073-124">在 [註冊] 表單中，選擇應用程式的名稱，然後選取 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="6e073-124">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="6e073-125">若要讓您的應用程式能夠存取使用者的 Defender，並指派「**讀取所有的提醒**」許可權，請在您的應用程式頁面上，選取 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織使用**>]，輸入 **WindowsDefenderATP**，然後選取 [ **WindowsDefenderATP**]。</span><span class="sxs-lookup"><span data-stu-id="6e073-125">To enable your app to access Defender for Endpoint and assign it **'Read all alerts'** permission, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **WindowsDefenderATP**, and then select **WindowsDefenderATP**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6e073-126">*WindowsDefenderATP* 不會出現在原始清單中。</span><span class="sxs-lookup"><span data-stu-id="6e073-126">*WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="6e073-127">開始在文字方塊中寫入其名稱，以查看顯示。</span><span class="sxs-lookup"><span data-stu-id="6e073-127">Start writing its name in the text box to see it appear.</span></span>

   ![新增許可權](images/add-permission.png)

   - <span data-ttu-id="6e073-129">選取 [**應用程式許可權**] [已讀取]。 [  >  **全部**]，然後選取 [**新增許可權**]。</span><span class="sxs-lookup"><span data-stu-id="6e073-129">Select **Application permissions** > **Alert.Read.All**, and then select **Add permissions**.</span></span>

   ![應用程式許可權](images/application-permissions.png)

     <span data-ttu-id="6e073-131">您必須選取相關的許可權。</span><span class="sxs-lookup"><span data-stu-id="6e073-131">You need to select the relevant permissions.</span></span> <span data-ttu-id="6e073-132">「讀取所有警示」只是範例。</span><span class="sxs-lookup"><span data-stu-id="6e073-132">'Read All Alerts' is only an example.</span></span> <span data-ttu-id="6e073-133">例如：</span><span class="sxs-lookup"><span data-stu-id="6e073-133">For instance:</span></span>

     - <span data-ttu-id="6e073-134">若要 [執行高級查詢](run-advanced-query-api.md)，請選取「執行高級查詢」許可權。</span><span class="sxs-lookup"><span data-stu-id="6e073-134">To [run advanced queries](run-advanced-query-api.md), select the 'Run advanced queries' permission.</span></span>
     - <span data-ttu-id="6e073-135">若要 [隔離裝置](isolate-machine.md)，請選取「隔離電腦」許可權。</span><span class="sxs-lookup"><span data-stu-id="6e073-135">To [isolate a device](isolate-machine.md), select the 'Isolate machine' permission.</span></span>
     - <span data-ttu-id="6e073-136">若要決定您需要的許可權，請參閱您想要呼叫之 API 中的 [ **許可權** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="6e073-136">To determine which permission you need, look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="6e073-137">選取 **[授與同意**]。</span><span class="sxs-lookup"><span data-stu-id="6e073-137">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="6e073-138">每當您新增許可權時，您必須選取 **[授與同意** ]，新許可權才會生效。</span><span class="sxs-lookup"><span data-stu-id="6e073-138">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![授與權限](images/grant-consent.png)

6. <span data-ttu-id="6e073-140">若要將機密新增至應用程式，請選取 [ **憑證 & 機密**]，新增 [密碼] 的描述，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="6e073-140">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6e073-141">選取 [ **新增**] 之後，選取 **[複製產生的機密值**]。</span><span class="sxs-lookup"><span data-stu-id="6e073-141">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="6e073-142">離開後，您將無法取回此值。</span><span class="sxs-lookup"><span data-stu-id="6e073-142">You won't be able to retrieve this value after you leave.</span></span>

    ![建立應用程式機碼的影像](images/webapp-create-key2.png)

7. <span data-ttu-id="6e073-144">記下來記錄應用程式識別碼和您的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="6e073-144">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="6e073-145">在 [應用程式] 頁面上，移至 **[簡介** ]，然後複製下列各項。</span><span class="sxs-lookup"><span data-stu-id="6e073-145">On your application page, go to **Overview** and copy the following.</span></span>

   ![建立之應用程式識別碼的影像](images/app-and-tenant-ids.png)

8. <span data-ttu-id="6e073-147">**僅適用于 Microsoft Defender For Endpoint 合作夥伴**。</span><span class="sxs-lookup"><span data-stu-id="6e073-147">**For Microsoft Defender for Endpoint Partners only**.</span></span> <span data-ttu-id="6e073-148">將您的應用程式設為多 tenanted (在同意) 後，所有承租人皆可使用。</span><span class="sxs-lookup"><span data-stu-id="6e073-148">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="6e073-149">這是協力廠商應用程式 **所需** 的 (例如，如果您建立要在多個客戶的承租人) 中執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6e073-149">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="6e073-150">如果您建立只想要在租使用者中執行的服務，這 **不是必要** 的 (例如，如果您為自己的使用方式建立應用程式，只會與您自己的資料) 互動。</span><span class="sxs-lookup"><span data-stu-id="6e073-150">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="6e073-151">若要將您的應用程式設為多 tenanted：</span><span class="sxs-lookup"><span data-stu-id="6e073-151">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="6e073-152">移至 [ **驗證**]，然後新增 `https://portal.azure.com` 為重新 **導向 URI**。</span><span class="sxs-lookup"><span data-stu-id="6e073-152">Go to **Authentication**, and add `https://portal.azure.com` as the **Redirect URI**.</span></span>

    - <span data-ttu-id="6e073-153">在頁面底部的 [ **支援的帳戶類型**] 底下，選取您的多租使用者應用程式的 **任何組織目錄** 應用程式中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="6e073-153">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="6e073-154">您必須在您要使用的每個承租人中核准您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6e073-154">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="6e073-155">這是因為您的應用程式代表您的客戶與 Defender for Endpoint 互動。</span><span class="sxs-lookup"><span data-stu-id="6e073-155">This is because your application interacts Defender for Endpoint on behalf of your customer.</span></span>

    <span data-ttu-id="6e073-156">當您撰寫協力廠商應用程式時，您 (或客戶) 必須選取同意連結並核准您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6e073-156">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="6e073-157">使用 Active Directory 中具有系統管理許可權的使用者，應進行同意。</span><span class="sxs-lookup"><span data-stu-id="6e073-157">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="6e073-158">「同意」連結的成形如下：</span><span class="sxs-lookup"><span data-stu-id="6e073-158">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="6e073-159">其中00000000-0000-0000-0000-000000000000 會取代為您的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="6e073-159">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="6e073-160">**做！**</span><span class="sxs-lookup"><span data-stu-id="6e073-160">**Done!**</span></span> <span data-ttu-id="6e073-161">您已成功註冊應用程式！</span><span class="sxs-lookup"><span data-stu-id="6e073-161">You have successfully registered an application!</span></span> <span data-ttu-id="6e073-162">請參閱下列範例以取得及驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="6e073-162">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="6e073-163">取得存取權杖</span><span class="sxs-lookup"><span data-stu-id="6e073-163">Get an access token</span></span>

<span data-ttu-id="6e073-164">如需 Azure AD 標記的詳細資訊，請參閱 [AZURE ad 教學](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)課程。</span><span class="sxs-lookup"><span data-stu-id="6e073-164">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="6e073-165">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e073-165">Use PowerShell</span></span>

```powershell
# This script acquires the App Context Token and stores it in the variable $token for later use in the script.
# Paste your Tenant ID, App ID, and App Secret (App key) into the indicated quotes below.

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
```

### <a name="use-c"></a><span data-ttu-id="6e073-166">使用 c #：</span><span class="sxs-lookup"><span data-stu-id="6e073-166">Use C#:</span></span>

<span data-ttu-id="6e073-167">下列程式碼是使用 NuGet 的 Windows.identitymodel.extensions.dll 測試。 ActiveDirectory 3.19.8。</span><span class="sxs-lookup"><span data-stu-id="6e073-167">The following code was tested with NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="6e073-168">建立新的主控台應用程式。</span><span class="sxs-lookup"><span data-stu-id="6e073-168">Create a new console application.</span></span>
1. <span data-ttu-id="6e073-169">安裝 NuGet [windows.identitymodel.extensions.dll。 ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。</span><span class="sxs-lookup"><span data-stu-id="6e073-169">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="6e073-170">新增下列專案：</span><span class="sxs-lookup"><span data-stu-id="6e073-170">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="6e073-171">在應用程式中複製並貼上下列程式碼 (請勿忘記更新三個變數： ```tenantId, appId, appSecret```) ：</span><span class="sxs-lookup"><span data-stu-id="6e073-171">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

    ```
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


### <a name="use-python"></a><span data-ttu-id="6e073-172">使用 Python</span><span class="sxs-lookup"><span data-stu-id="6e073-172">Use Python</span></span>

<span data-ttu-id="6e073-173">請參閱 [使用 Python 取得 token](run-advanced-query-sample-python.md#get-token)。</span><span class="sxs-lookup"><span data-stu-id="6e073-173">See [Get token using Python](run-advanced-query-sample-python.md#get-token).</span></span>

### <a name="use-curl"></a><span data-ttu-id="6e073-174">使用捲曲</span><span class="sxs-lookup"><span data-stu-id="6e073-174">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="6e073-175">下列程式假設已在您的電腦上安裝了 Windows 的卷。</span><span class="sxs-lookup"><span data-stu-id="6e073-175">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="6e073-176">開啟命令提示字元，並將 CLIENT_ID 設定為您的 Azure 應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="6e073-176">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="6e073-177">將 CLIENT_SECRET 設定為您的 Azure 應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="6e073-177">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="6e073-178">將 TENANT_ID 設定為想要使用您的應用程式來存取端點之使用者的 Azure 租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="6e073-178">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Defender for Endpoint.</span></span>
1. <span data-ttu-id="6e073-179">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6e073-179">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="6e073-180">您會收到下列形式的答案：</span><span class="sxs-lookup"><span data-stu-id="6e073-180">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="6e073-181">驗證 token</span><span class="sxs-lookup"><span data-stu-id="6e073-181">Validate the token</span></span>

<span data-ttu-id="6e073-182">確定您獲得正確的權杖：</span><span class="sxs-lookup"><span data-stu-id="6e073-182">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="6e073-183">將您在上一個步驟中所掌握的權杖複製並貼上至 [JWT](https://jwt.ms) ，以便進行解碼。</span><span class="sxs-lookup"><span data-stu-id="6e073-183">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="6e073-184">確認您取得了所需許可權的「role」宣告</span><span class="sxs-lookup"><span data-stu-id="6e073-184">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="6e073-185">在下列影像中，您可以看到從應用程式取得的解碼標記，該權杖具有所有 Microsoft Defender for Endpoint role 的許可權：</span><span class="sxs-lookup"><span data-stu-id="6e073-185">In the following image, you can see a decoded token acquired from an app with permissions to all of  Microsoft Defender for Endpoint's roles:</span></span>

![權杖驗證的影像](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="6e073-187">使用權杖來存取 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="6e073-187">Use the token to access Microsoft Defender for Endpoint API</span></span>

1. <span data-ttu-id="6e073-188">選擇您要使用的 API。</span><span class="sxs-lookup"><span data-stu-id="6e073-188">Choose the API you want to use.</span></span> <span data-ttu-id="6e073-189">如需詳細資訊，請參閱 [支援的 Defender For Endpoint APIs](exposed-apis-list.md)。</span><span class="sxs-lookup"><span data-stu-id="6e073-189">For more information, see [Supported Defender for Endpoint APIs](exposed-apis-list.md).</span></span>
1. <span data-ttu-id="6e073-190">在您傳送至 "載荷 {token}" 的 HTTP 要求中設定授權標頭。 (載荷是授權配置) 。</span><span class="sxs-lookup"><span data-stu-id="6e073-190">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>
1. <span data-ttu-id="6e073-191">權杖的到期時間是一小時。</span><span class="sxs-lookup"><span data-stu-id="6e073-191">The expiration time of the token is one hour.</span></span> <span data-ttu-id="6e073-192">您可以使用相同的權杖傳送一個以上的要求。</span><span class="sxs-lookup"><span data-stu-id="6e073-192">You can send more than one request with the same token.</span></span>

<span data-ttu-id="6e073-193">以下是 **使用 c #** 傳送要求以取得警示清單的範例：</span><span class="sxs-lookup"><span data-stu-id="6e073-193">The following is an example of sending a request to get a list of alerts **using C#**:</span></span> 
```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="see-also"></a><span data-ttu-id="6e073-194">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6e073-194">See also</span></span>
- [<span data-ttu-id="6e073-195">支援的 Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="6e073-195">Supported Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="6e073-196">代表使用者存取 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6e073-196">Access Microsoft Defender for Endpoint on behalf of a user</span></span>](exposed-apis-create-app-nativeapp.md)
