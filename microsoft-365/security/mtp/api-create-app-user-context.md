---
title: 建立應用程式以代表使用者存取 Microsoft 365 Defender APIs
description: 瞭解如何代表使用者存取 Microsoft 365 Defender APIs。
keywords: 代表使用者、api、應用程式、使用者、存取權杖、token 等存取
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
ms.openlocfilehash: d443334a00b5247525a2cdba98a11cfe0f515193
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928450"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="43b37-104">建立應用程式以代表使用者存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="43b37-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="43b37-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="43b37-105">**Applies to:**</span></span>

- <span data-ttu-id="43b37-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43b37-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43b37-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="43b37-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="43b37-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="43b37-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="43b37-109">此頁面會說明如何建立應用程式，以讓單一使用者以程式設計方式存取 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="43b37-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="43b37-110">如果您需要以程式設計方式存取沒有定義之使用者的 Microsoft 365 Defender (例如，如果您正在撰寫後臺應用程式或幕後程式) ，請參閱 [Create a app to Access Microsoft 365 Defender （沒有使用者](api-create-app-web.md)）。</span><span class="sxs-lookup"><span data-stu-id="43b37-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="43b37-111">如果您需要為多個承租人提供存取權，例如，如果您正在服務大型組織或客戶群組，請參閱 Create a [app with a app to access to To Microsoft 365 Defender APIs](api-partner-access.md)。如果您不確定需要哪種類型的存取，請參閱 [入門](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="43b37-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="43b37-112">Microsoft 365 Defender 會透過一組程式設計 APIs 來公開其大部分資料和動作。</span><span class="sxs-lookup"><span data-stu-id="43b37-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="43b37-113">這些 APIs 可協助您自動化工作流程，並使用 Microsoft 365 Defender 的功能。</span><span class="sxs-lookup"><span data-stu-id="43b37-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="43b37-114">此 API access 需要 OAuth 2.0 驗證。</span><span class="sxs-lookup"><span data-stu-id="43b37-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="43b37-115">如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="43b37-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="43b37-116">一般來講，您必須採取下列步驟，才能使用這些 APIs：</span><span class="sxs-lookup"><span data-stu-id="43b37-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="43b37-117">建立 Azure Active Directory (Azure AD) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="43b37-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="43b37-118">使用此應用程式取得存取權杖。</span><span class="sxs-lookup"><span data-stu-id="43b37-118">Get an access token using this application.</span></span>
- <span data-ttu-id="43b37-119">使用權杖來存取 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="43b37-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="43b37-120">本文將說明如何：</span><span class="sxs-lookup"><span data-stu-id="43b37-120">This article explains how to:</span></span>

- <span data-ttu-id="43b37-121">建立 Azure AD 應用程式</span><span class="sxs-lookup"><span data-stu-id="43b37-121">Create an Azure AD application</span></span>
- <span data-ttu-id="43b37-122">取得 Microsoft 365 Defender 的存取權杖</span><span class="sxs-lookup"><span data-stu-id="43b37-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="43b37-123">驗證 token</span><span class="sxs-lookup"><span data-stu-id="43b37-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="43b37-124">當您代表使用者存取 Microsoft 365 Defender API 時，您將需要正確的應用程式許可權和使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="43b37-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="43b37-125">如果您有許可權執行入口網站中的動作，您就具有在 API 中執行該動作的許可權。</span><span class="sxs-lookup"><span data-stu-id="43b37-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="43b37-126">建立應用程式</span><span class="sxs-lookup"><span data-stu-id="43b37-126">Create an app</span></span>

1. <span data-ttu-id="43b37-127">以 **全域系統管理員** 角色的使用者身分登入 [Azure](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="43b37-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="43b37-128">流覽至 [ **Azure Active Directory**  >  **應用程式註冊**]  >  **新註冊**。</span><span class="sxs-lookup"><span data-stu-id="43b37-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure 的影像及應用程式註冊導覽](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="43b37-130">在表單中，為您的應用程式選擇一個名稱，並輸入下列重新導向 URI 的資訊，然後選取 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="43b37-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![建立應用程式視窗的影像](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="43b37-132">**應用程式類型：** 公用用戶端</span><span class="sxs-lookup"><span data-stu-id="43b37-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="43b37-133">重新 **導向 URI：**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="43b37-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="43b37-134">在 [應用程式] 頁面上，選取 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織使用**>]，輸入 **microsoft 威脅防護**，然後選取 [ **microsoft 威脅防護**]。</span><span class="sxs-lookup"><span data-stu-id="43b37-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="43b37-135">您的應用程式現在可以存取 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="43b37-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="43b37-136">*Microsoft 威脅防護* 是 Microsoft 365 Defender 的先前名稱，因此不會出現在原始清單中。</span><span class="sxs-lookup"><span data-stu-id="43b37-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="43b37-137">您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。</span><span class="sxs-lookup"><span data-stu-id="43b37-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 許可權選取的影像](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="43b37-139">選擇 [ **委派許可權**]。</span><span class="sxs-lookup"><span data-stu-id="43b37-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="43b37-140">為案例選擇相關許可權 (例如 **事件。 Read**) ，然後選取 [ **新增許可權**]。</span><span class="sxs-lookup"><span data-stu-id="43b37-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![API 存取和 API 選取的影像](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="43b37-142">您必須選取案例的相關許可權。</span><span class="sxs-lookup"><span data-stu-id="43b37-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="43b37-143">*讀取所有的事件* 只是一個範例。</span><span class="sxs-lookup"><span data-stu-id="43b37-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="43b37-144">若要決定您需要的許可權，請參閱您想要呼叫之 API 中的 [ **許可權** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="43b37-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="43b37-145">例如，若要 [執行高級查詢](api-advanced-hunting.md)，請選取「執行高級查詢」許可權;若要 [隔離裝置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)，請選取「隔離電腦」許可權。</span><span class="sxs-lookup"><span data-stu-id="43b37-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="43b37-146">選取 **[授與系統管理員同意**]。</span><span class="sxs-lookup"><span data-stu-id="43b37-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="43b37-147">每次您新增許可權時，都必須選取 **[授與系統管理員同意** ]，才會生效。</span><span class="sxs-lookup"><span data-stu-id="43b37-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![授與許可權的影像](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="43b37-149">將您的應用程式識別碼和租使用者識別碼記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="43b37-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="43b37-150">在 [應用程式] 頁面的 **[一覽** ] 底下會列出它們。</span><span class="sxs-lookup"><span data-stu-id="43b37-150">They're listed under **Overview** on your application page.</span></span>

   ![建立之應用程式識別碼的影像](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="43b37-152">取得存取權杖</span><span class="sxs-lookup"><span data-stu-id="43b37-152">Get an access token</span></span>

<span data-ttu-id="43b37-153">如需 Azure Active Directory 標記的詳細資訊，請參閱 [AZURE AD 教學](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)課程。</span><span class="sxs-lookup"><span data-stu-id="43b37-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="43b37-154">使用 PowerShell 取得存取權杖</span><span class="sxs-lookup"><span data-stu-id="43b37-154">Get an access token using PowerShell</span></span>

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a><span data-ttu-id="43b37-155">驗證 token</span><span class="sxs-lookup"><span data-stu-id="43b37-155">Validate the token</span></span>

1. <span data-ttu-id="43b37-156">將權杖複製並貼到 [JWT](https://jwt.ms) ，以進行解碼。</span><span class="sxs-lookup"><span data-stu-id="43b37-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="43b37-157">請確定已解碼權杖中的 *角色* 宣告包含所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="43b37-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="43b37-158">在下列影像中，您可以看到從應用程式取得的解碼標記，具有 ```Incidents.Read.All``` 、 ```Incidents.ReadWrite.All``` 和 ```AdvancedHunting.Read.All``` 許可權：</span><span class="sxs-lookup"><span data-stu-id="43b37-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![權杖驗證的影像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="43b37-160">使用權杖來存取 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="43b37-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="43b37-161">選擇您想要使用 (事件或「高級搜尋) 的 API。</span><span class="sxs-lookup"><span data-stu-id="43b37-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="43b37-162">如需詳細資訊，請參閱 [支援的 Microsoft 365 Defender APIs](api-supported.md)。</span><span class="sxs-lookup"><span data-stu-id="43b37-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="43b37-163">在您要傳送的 HTTP 要求中，將授權標頭設定為 `"Bearer" <token>` ， *持有* 者為授權配置，而 *token* 為您驗證的權杖。</span><span class="sxs-lookup"><span data-stu-id="43b37-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="43b37-164">權杖會在一小時內到期。</span><span class="sxs-lookup"><span data-stu-id="43b37-164">The token will expire within one hour.</span></span> <span data-ttu-id="43b37-165">在此期間，您可以使用相同的權杖傳送一個以上的要求。</span><span class="sxs-lookup"><span data-stu-id="43b37-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="43b37-166">下列範例顯示如何 **使用 c #** 傳送要求以取得事件清單。</span><span class="sxs-lookup"><span data-stu-id="43b37-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="43b37-167">相關文章</span><span class="sxs-lookup"><span data-stu-id="43b37-167">Related articles</span></span>

- [<span data-ttu-id="43b37-168">Microsoft 365 Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="43b37-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="43b37-169">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="43b37-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="43b37-170">建立 "Hello world" 應用程式</span><span class="sxs-lookup"><span data-stu-id="43b37-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="43b37-171">建立應用程式以存取沒有使用者的 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43b37-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="43b37-172">建立具有對 Microsoft 365 Defender APIs 的多承租人合作夥伴存取權的應用程式</span><span class="sxs-lookup"><span data-stu-id="43b37-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="43b37-173">深入瞭解 API 限制和授權</span><span class="sxs-lookup"><span data-stu-id="43b37-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="43b37-174">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="43b37-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="43b37-175">OAuth 2.0 使用者登入和 API 存取的授權</span><span class="sxs-lookup"><span data-stu-id="43b37-175">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
