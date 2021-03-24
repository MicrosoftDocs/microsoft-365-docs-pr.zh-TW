---
title: 建立應用程式以存取沒有使用者的 Microsoft 365 Defender
description: 瞭解如何建立應用程式，以在沒有使用者的情況下存取 Microsoft 365 Defender。
keywords: 應用程式、access、api、create
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8ffa04492f42f7e1ee5f3fc7fadad963e6bb7fbe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059640"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="60fb3-104">建立應用程式以存取沒有使用者的 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60fb3-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="60fb3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="60fb3-105">**Applies to:**</span></span>

- <span data-ttu-id="60fb3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60fb3-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60fb3-107">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="60fb3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="60fb3-108">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="60fb3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="60fb3-109">此頁面說明如何建立應用程式，以在沒有定義的使用者的情況下，取得 Microsoft 365 Defender 的程式存取權，例如，如果您要建立守護程式或後臺服務。</span><span class="sxs-lookup"><span data-stu-id="60fb3-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a defined user—for example, if you're creating a daemon or background service.</span></span>

<span data-ttu-id="60fb3-110">如果您需要以程式設計方式代替一或多個使用者存取 Microsoft 365 Defender，請參閱 [create a app to an a app to Access microsoft 365 Defender APIs 代表使用者](api-create-app-user-context.md) ，並 [建立具有對 Microsoft 365 Defender APIs 的合作夥伴存取的應用程式](api-partner-access.md)。</span><span class="sxs-lookup"><span data-stu-id="60fb3-110">If you need programmatic access to Microsoft 365 Defender on behalf of one or more users, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md) and [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).</span></span> <span data-ttu-id="60fb3-111">如果您不確定需要哪種類型的存取，請參閱 [入門](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="60fb3-111">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="60fb3-112">Microsoft 365 Defender 會透過一組程式設計 APIs 來公開其大部分資料和動作。</span><span class="sxs-lookup"><span data-stu-id="60fb3-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="60fb3-113">這些 APIs 可協助您自動化工作流程，並使用 Microsoft 365 Defender 的功能。</span><span class="sxs-lookup"><span data-stu-id="60fb3-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="60fb3-114">此 API access 需要 OAuth 2.0 驗證。</span><span class="sxs-lookup"><span data-stu-id="60fb3-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="60fb3-115">如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="60fb3-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="60fb3-116">一般來講，您必須採取下列步驟，才能使用這些 APIs：</span><span class="sxs-lookup"><span data-stu-id="60fb3-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="60fb3-117">建立 Azure Active Directory (Azure AD) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="60fb3-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="60fb3-118">使用此應用程式取得存取權杖。</span><span class="sxs-lookup"><span data-stu-id="60fb3-118">Get an access token using this application.</span></span>
- <span data-ttu-id="60fb3-119">使用權杖來存取 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="60fb3-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="60fb3-120">本文將說明如何：</span><span class="sxs-lookup"><span data-stu-id="60fb3-120">This article explains how to:</span></span>

- <span data-ttu-id="60fb3-121">建立 Azure AD 應用程式</span><span class="sxs-lookup"><span data-stu-id="60fb3-121">Create an Azure AD application</span></span>
- <span data-ttu-id="60fb3-122">取得 Microsoft 365 Defender 的存取權杖</span><span class="sxs-lookup"><span data-stu-id="60fb3-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="60fb3-123">驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="60fb3-123">Validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="60fb3-124">建立應用程式</span><span class="sxs-lookup"><span data-stu-id="60fb3-124">Create an app</span></span>

1. <span data-ttu-id="60fb3-125">以 **全域系統管理員** 角色的使用者身分登入 [Azure](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="60fb3-125">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="60fb3-126">流覽至 [ **Azure Active Directory**  >  **應用程式註冊**]  >  **新註冊**。</span><span class="sxs-lookup"><span data-stu-id="60fb3-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure 的影像及應用程式註冊導覽](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="60fb3-128">在表單中，選擇應用程式的名稱，然後選取 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="60fb3-128">In the form, choose a name for your application, then select **Register**.</span></span>

4. <span data-ttu-id="60fb3-129">在 [應用程式] 頁面上，選取 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織使用**>]，輸入 **microsoft 威脅防護**，然後選取 [ **microsoft 威脅防護**]。</span><span class="sxs-lookup"><span data-stu-id="60fb3-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="60fb3-130">您的應用程式現在可以存取 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="60fb3-130">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="60fb3-131">*Microsoft 威脅防護* 是 Microsoft 365 Defender 的先前名稱，因此不會出現在原始清單中。</span><span class="sxs-lookup"><span data-stu-id="60fb3-131">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="60fb3-132">您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。</span><span class="sxs-lookup"><span data-stu-id="60fb3-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 許可權選取的影像](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="60fb3-134">選取 [ **應用程式許可權**]。</span><span class="sxs-lookup"><span data-stu-id="60fb3-134">Select **Application permissions**.</span></span> <span data-ttu-id="60fb3-135">為您的案例選擇相關許可權 (例如， **Incident。 Read。 All**) ，然後選取 [ **新增許可權**]。</span><span class="sxs-lookup"><span data-stu-id="60fb3-135">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![API 存取和 API 選取的影像](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="60fb3-137">您必須選取案例的相關許可權。</span><span class="sxs-lookup"><span data-stu-id="60fb3-137">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="60fb3-138">*讀取所有的事件* 只是一個範例。</span><span class="sxs-lookup"><span data-stu-id="60fb3-138">*Read all incidents* is just an example.</span></span> <span data-ttu-id="60fb3-139">若要決定您需要的許可權，請參閱您想要呼叫之 API 中的 [ **許可權** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="60fb3-139">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="60fb3-140">例如，若要 [執行高級查詢](api-advanced-hunting.md)，請選取「執行高級查詢」許可權;若要 [隔離裝置](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)，請選取「隔離電腦」許可權。</span><span class="sxs-lookup"><span data-stu-id="60fb3-140">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="60fb3-141">選取 **[授與系統管理員同意**]。</span><span class="sxs-lookup"><span data-stu-id="60fb3-141">Select **Grant admin consent**.</span></span> <span data-ttu-id="60fb3-142">每次您新增許可權時，都必須選取 **[授與系統管理員同意** ]，才會生效。</span><span class="sxs-lookup"><span data-stu-id="60fb3-142">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![授與許可權的影像](../../media/grant-consent.PNG)

7. <span data-ttu-id="60fb3-144">若要將機密新增至應用程式，請選取 [ **憑證 & 密碼**]，新增描述至密碼，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="60fb3-144">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="60fb3-145">選取 [ **新增**] 之後，選取 **[複製產生的機密值**]。</span><span class="sxs-lookup"><span data-stu-id="60fb3-145">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="60fb3-146">離開後，您將無法取得密碼值。</span><span class="sxs-lookup"><span data-stu-id="60fb3-146">You won't be able to retrieve the secret value after you leave.</span></span>

    ![建立應用程式機碼的影像](../../media/webapp-create-key2.png)

8. <span data-ttu-id="60fb3-148">將您的應用程式識別碼和租使用者識別碼記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="60fb3-148">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="60fb3-149">在 [應用程式] 頁面的 **[一覽** ] 底下會列出它們。</span><span class="sxs-lookup"><span data-stu-id="60fb3-149">They're listed under **Overview** on your application page.</span></span>

   ![建立之應用程式識別碼的影像](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="60fb3-151">**僅適用于 microsoft 365 Defender 合作夥伴**： [請遵循下列指示](./api-partner-access.md) ，透過 microsoft 365 Defender APIs 取得合作夥伴存取權，將您的應用程式設定為多租使用者，以便在您收到系統管理員同意後，可在所有承租人中使用。</span><span class="sxs-lookup"><span data-stu-id="60fb3-151">**For Microsoft 365 Defender Partners only**: [Follow these instructions](./api-partner-access.md) for partner access through the Microsoft 365 Defender APIs, set your app to be multi-tenant, so it can be available in all tenants once you receive admin consent.</span></span> <span data-ttu-id="60fb3-152">協力廠商應用程式 **需要** 合作夥伴存取，例如，如果您要建立的應用程式要在多個客戶的承租人中執行。</span><span class="sxs-lookup"><span data-stu-id="60fb3-152">Partner access is **required** for third-party apps—for example, if you create an app that is intended to run in multiple customers' tenants.</span></span> <span data-ttu-id="60fb3-153">如果您建立只想要在租使用者中執行的服務（例如您自己使用的應用程式，只會與您自己的資料互動），就 **不需要** 這樣做。</span><span class="sxs-lookup"><span data-stu-id="60fb3-153">It is **not required** if you create a service that you want to run in your tenant only, such as an application for your own usage that will only interact with your own data.</span></span> <span data-ttu-id="60fb3-154">若要將您的應用程式設為多租使用者：</span><span class="sxs-lookup"><span data-stu-id="60fb3-154">To set your app to be multi-tenant:</span></span>

    - <span data-ttu-id="60fb3-155">移至 [ **驗證**]，然後新增 https://portal.azure.com 為重新 **導向 URI**。</span><span class="sxs-lookup"><span data-stu-id="60fb3-155">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="60fb3-156">在頁面底部的 [ **支援的帳戶類型**] 底下，選取您的多租使用者應用程式的 **任何組織目錄** 應用程式中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="60fb3-156">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="60fb3-157">因為您的應用程式代表您的使用者與 Microsoft 365 Defender 互動，所以需要針對您想要使用它的每一個承租人進行核准。</span><span class="sxs-lookup"><span data-stu-id="60fb3-157">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

    <span data-ttu-id="60fb3-158">每個租使用者的 Active Directory 全域系統管理員都必須選取同意連結並核准您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="60fb3-158">The Active Directory global admin for each tenant needs to select the consent link and approve your app.</span></span>

    <span data-ttu-id="60fb3-159">同意連結的結構如下：</span><span class="sxs-lookup"><span data-stu-id="60fb3-159">The consent link has the following structure:</span></span>

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="60fb3-160">`00000000-0000-0000-0000-000000000000`應以您的應用程式識別碼取代位數。</span><span class="sxs-lookup"><span data-stu-id="60fb3-160">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>  

<span data-ttu-id="60fb3-161">**做！**</span><span class="sxs-lookup"><span data-stu-id="60fb3-161">**Done!**</span></span> <span data-ttu-id="60fb3-162">您已成功註冊應用程式！</span><span class="sxs-lookup"><span data-stu-id="60fb3-162">You've successfully registered an application!</span></span> <span data-ttu-id="60fb3-163">請參閱下列範例以取得及驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="60fb3-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="60fb3-164">取得存取權杖</span><span class="sxs-lookup"><span data-stu-id="60fb3-164">Get an access token</span></span>

<span data-ttu-id="60fb3-165">如需 Azure Active Directory 標記的詳細資訊，請參閱 [AZURE AD 教學](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)課程。</span><span class="sxs-lookup"><span data-stu-id="60fb3-165">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60fb3-166">雖然本節中的範例會鼓勵您貼上用於測試目的的機密值，否則您 **不應該將機密硬編碼** 成實際執行中執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="60fb3-166">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="60fb3-167">協力廠商可以使用您的機密存取資源。</span><span class="sxs-lookup"><span data-stu-id="60fb3-167">A third party could use your secret to access resources.</span></span> <span data-ttu-id="60fb3-168">您可以使用 [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates)，協助保護應用程式的機密。</span><span class="sxs-lookup"><span data-stu-id="60fb3-168">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="60fb3-169">如需如何保護應用程式的實際範例，請參閱 [使用 Azure Key Vault 管理伺服器應用程式中的機密](/learn/modules/manage-secrets-with-azure-key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="60fb3-169">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="60fb3-170">使用 PowerShell 取得存取權杖</span><span class="sxs-lookup"><span data-stu-id="60fb3-170">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="60fb3-171">使用 C 取得存取 token\#</span><span class="sxs-lookup"><span data-stu-id="60fb3-171">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="60fb3-172">下列程式碼已使用 Nuget Windows.identitymodel.extensions.dll 進行測試。 ActiveDirectory 3.19.8。</span><span class="sxs-lookup"><span data-stu-id="60fb3-172">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="60fb3-173">建立新的主控台應用程式。</span><span class="sxs-lookup"><span data-stu-id="60fb3-173">Create a new console application.</span></span>

1. <span data-ttu-id="60fb3-174">安裝 NuGet [windows.identitymodel.extensions.dll。 ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。</span><span class="sxs-lookup"><span data-stu-id="60fb3-174">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>

1. <span data-ttu-id="60fb3-175">新增下列行：</span><span class="sxs-lookup"><span data-stu-id="60fb3-175">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="60fb3-176">將下列程式碼複製並貼到您的應用程式中 (不要忘記更新這三個變數： `tenantId` ， `clientId` ， `appSecret`) ：</span><span class="sxs-lookup"><span data-stu-id="60fb3-176">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="60fb3-177">使用 Python 取得存取權杖</span><span class="sxs-lookup"><span data-stu-id="60fb3-177">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.security.microsoft.com'

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="60fb3-178">使用曲線取得存取權杖</span><span class="sxs-lookup"><span data-stu-id="60fb3-178">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="60fb3-179">在 Windows 10 版本1803和更新版本上都預先安裝了卷。</span><span class="sxs-lookup"><span data-stu-id="60fb3-179">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="60fb3-180">若為其他版本的 Windows，請直接從 [官方卷網站](https://curl.haxx.se/windows/)下載並安裝工具。</span><span class="sxs-lookup"><span data-stu-id="60fb3-180">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="60fb3-181">開啟命令提示字元，並將 CLIENT_ID 設定為您的 Azure 應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="60fb3-181">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>

1. <span data-ttu-id="60fb3-182">將 CLIENT_SECRET 設定為您的 Azure 應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="60fb3-182">Set CLIENT_SECRET to your Azure application secret.</span></span>

1. <span data-ttu-id="60fb3-183">將 TENANT_ID 設定為要使用您的應用程式存取 Microsoft 365 Defender 之客戶的 Azure 租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="60fb3-183">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>

1. <span data-ttu-id="60fb3-184">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="60fb3-184">Run the following command:</span></span>

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   <span data-ttu-id="60fb3-185">成功的回應如下所示：</span><span class="sxs-lookup"><span data-stu-id="60fb3-185">A successful response will look like this:</span></span>

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a><span data-ttu-id="60fb3-186">驗證 token</span><span class="sxs-lookup"><span data-stu-id="60fb3-186">Validate the token</span></span>

1. <span data-ttu-id="60fb3-187">將權杖複製並貼到 [JSON web token 驗證者網站（JWT）](https://jwt.ms) 以進行解碼。</span><span class="sxs-lookup"><span data-stu-id="60fb3-187">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>

1. <span data-ttu-id="60fb3-188">請確定已解碼權杖中的 *角色* 宣告包含所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="60fb3-188">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

   <span data-ttu-id="60fb3-189">在下列影像中，您可以看到從應用程式取得的解碼標記，具有 `Incidents.Read.All` 、 `Incidents.ReadWrite.All` 和 `AdvancedHunting.Read.All` 許可權：</span><span class="sxs-lookup"><span data-stu-id="60fb3-189">In the following image, you can see a decoded token acquired from an app, with `Incidents.Read.All`, `Incidents.ReadWrite.All`, and `AdvancedHunting.Read.All` permissions:</span></span>

   ![權杖驗證的影像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="60fb3-191">使用權杖來存取 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="60fb3-191">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="60fb3-192">選擇您想要使用 (事件或「高級搜尋) 的 API。</span><span class="sxs-lookup"><span data-stu-id="60fb3-192">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="60fb3-193">如需詳細資訊，請參閱 [支援的 Microsoft 365 Defender APIs](api-supported.md)。</span><span class="sxs-lookup"><span data-stu-id="60fb3-193">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="60fb3-194">在您要傳送的 HTTP 要求中，將授權標頭設定為 `"Bearer" <token>` ， *持有* 者為授權配置，而 *token* 為您驗證的權杖。</span><span class="sxs-lookup"><span data-stu-id="60fb3-194">In the http request you are about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>

3. <span data-ttu-id="60fb3-195">權杖會在一小時內到期。</span><span class="sxs-lookup"><span data-stu-id="60fb3-195">The token will expire within one hour.</span></span> <span data-ttu-id="60fb3-196">在此期間，您可以使用相同的權杖傳送一個以上的要求。</span><span class="sxs-lookup"><span data-stu-id="60fb3-196">You can send more than one request during this time with the same token.</span></span>

<span data-ttu-id="60fb3-197">下列範例顯示如何 **使用 c #** 傳送要求以取得事件清單。</span><span class="sxs-lookup"><span data-stu-id="60fb3-197">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="60fb3-198">相關文章</span><span class="sxs-lookup"><span data-stu-id="60fb3-198">Related articles</span></span>

- [<span data-ttu-id="60fb3-199">Microsoft 365 Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="60fb3-199">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="60fb3-200">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="60fb3-200">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="60fb3-201">建立 "Hello world" 應用程式</span><span class="sxs-lookup"><span data-stu-id="60fb3-201">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="60fb3-202">建立應用程式以代表使用者存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="60fb3-202">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="60fb3-203">建立具有對 Microsoft 365 Defender APIs 的多承租人合作夥伴存取權的應用程式</span><span class="sxs-lookup"><span data-stu-id="60fb3-203">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="60fb3-204">深入瞭解 API 限制和授權</span><span class="sxs-lookup"><span data-stu-id="60fb3-204">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="60fb3-205">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="60fb3-205">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="60fb3-206">使用 Azure Key Vault 管理伺服器應用程式中的機密</span><span class="sxs-lookup"><span data-stu-id="60fb3-206">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="60fb3-207">OAuth 2.0 使用者登入和 API 存取的授權</span><span class="sxs-lookup"><span data-stu-id="60fb3-207">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)