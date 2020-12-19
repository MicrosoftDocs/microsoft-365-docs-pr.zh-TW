---
title: Microsoft 365 Defender REST API 的 Hello World 版
description: 瞭解如何建立應用程式，並使用權杖來存取 Microsoft 365 Defender APIs
keywords: 應用程式、權杖、存取、aad、應用程式、應用程式註冊、powershell、腳本、全域管理員、許可權、microsoft 365 defender
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
ms.openlocfilehash: b36a6acca5880a455a66b03b5355cdf1fb85b29b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719307"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="eadab-104">Microsoft 365 Defender REST API 的 Hello World 版</span><span class="sxs-lookup"><span data-stu-id="eadab-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="eadab-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="eadab-105">**Applies to:**</span></span>

- <span data-ttu-id="eadab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eadab-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eadab-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="eadab-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="eadab-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="eadab-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="eadab-109">使用簡單的 PowerShell 腳本取得事件</span><span class="sxs-lookup"><span data-stu-id="eadab-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="eadab-110">完成此專案需要5到10分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="eadab-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="eadab-111">這次預估包括註冊應用程式，以及從 PowerShell 範例腳本套用程式碼。</span><span class="sxs-lookup"><span data-stu-id="eadab-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="eadab-112">在 Azure Active Directory 中註冊應用程式</span><span class="sxs-lookup"><span data-stu-id="eadab-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="eadab-113">以 **全域系統管理員** 角色的使用者身分登入 [Azure](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="eadab-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="eadab-114">流覽至 [ **Azure Active Directory**  >  **應用程式註冊**]  >  **新註冊**。</span><span class="sxs-lookup"><span data-stu-id="eadab-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure 的影像及應用程式註冊導覽](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="eadab-116">在 [註冊] 表單中，選擇應用程式的名稱，然後選取 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="eadab-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="eadab-117">選取重新導向 URI 是選用的。</span><span class="sxs-lookup"><span data-stu-id="eadab-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="eadab-118">您不需要其中一個，即可完成此範例。</span><span class="sxs-lookup"><span data-stu-id="eadab-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="eadab-119">在 [應用程式] 頁面上，選取 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織使用**>]，輸入 **microsoft 威脅防護**，然後選取 [ **microsoft 威脅防護**]。</span><span class="sxs-lookup"><span data-stu-id="eadab-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="eadab-120">您的應用程式現在可以存取 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="eadab-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="eadab-121">*Microsoft 威脅防護* 是 Microsoft 365 Defender 的先前名稱，因此不會出現在原始清單中。</span><span class="sxs-lookup"><span data-stu-id="eadab-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="eadab-122">您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。</span><span class="sxs-lookup"><span data-stu-id="eadab-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="eadab-123">![API 許可權選取的影像](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="eadab-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="eadab-124">選擇 [**應用程式許可權**]  >  **事件。讀取。 [全部**] 並選取 [**新增許可權**]。</span><span class="sxs-lookup"><span data-stu-id="eadab-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![API 存取和 API 選取的影像](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="eadab-126">選取 **[授與系統管理員同意**]。</span><span class="sxs-lookup"><span data-stu-id="eadab-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="eadab-127">每次您新增許可權時，都必須選取 **[授與系統管理員同意** ]，才會生效。</span><span class="sxs-lookup"><span data-stu-id="eadab-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![授與許可權的影像](../../media/grant-consent.PNG)

6. <span data-ttu-id="eadab-129">將密碼新增至應用程式。</span><span class="sxs-lookup"><span data-stu-id="eadab-129">Add a secret to the application.</span></span> <span data-ttu-id="eadab-130">選取 [ **& 密碼的憑證**]，新增描述至密碼，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="eadab-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="eadab-131">選取 [ **新增**] 之後，選取 **[複製產生的機密值**]。</span><span class="sxs-lookup"><span data-stu-id="eadab-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="eadab-132">離開後，您將無法取得密碼值。</span><span class="sxs-lookup"><span data-stu-id="eadab-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![建立應用程式機碼的影像](../../media/webapp-create-key2.png)

7. <span data-ttu-id="eadab-134">將您的應用程式識別碼和租使用者識別碼記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="eadab-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="eadab-135">在 [應用程式] 頁面的 **[一覽** ] 底下會列出它們。</span><span class="sxs-lookup"><span data-stu-id="eadab-135">They're listed under **Overview** on your application page.</span></span>

   ![建立之應用程式識別碼的影像](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="eadab-137">使用應用程式取得權杖，並使用權杖存取 API</span><span class="sxs-lookup"><span data-stu-id="eadab-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="eadab-138">如需 Azure Active Directory 標記的詳細資訊，請參閱 [AZURE AD 教學](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)課程。</span><span class="sxs-lookup"><span data-stu-id="eadab-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eadab-139">雖然此演示程式中的範例會鼓勵您貼上機密值以用於測試目的，您決不應該將 **機密硬編碼** 到生產中執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="eadab-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="eadab-140">協力廠商可以使用您的機密存取資源。</span><span class="sxs-lookup"><span data-stu-id="eadab-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="eadab-141">您可以使用 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)，協助保護應用程式的機密。</span><span class="sxs-lookup"><span data-stu-id="eadab-141">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="eadab-142">如需如何保護應用程式的實際範例，請參閱 [使用 Azure Key Vault 管理伺服器應用程式中的機密](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="eadab-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="eadab-143">複製下列腳本，並將其貼到您喜愛的文字編輯器中。</span><span class="sxs-lookup"><span data-stu-id="eadab-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="eadab-144">[另存新檔] **Get-Token.ps1**。</span><span class="sxs-lookup"><span data-stu-id="eadab-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="eadab-145">您也可以在 PowerShell ISE 中執行程式碼，但您應該將其儲存，因為在下一節中使用事件提取腳本時，我們需要重新執行。</span><span class="sxs-lookup"><span data-stu-id="eadab-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="eadab-146">此腳本會產生權杖，並將其儲存在 [名稱] 下的工作資料夾中 *Latest-token.txt*。</span><span class="sxs-lookup"><span data-stu-id="eadab-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

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

#### <a name="validate-the-token"></a><span data-ttu-id="eadab-147">驗證 token</span><span class="sxs-lookup"><span data-stu-id="eadab-147">Validate the token</span></span>

1. <span data-ttu-id="eadab-148">複製並貼上您收到的權杖 [以進行](https://jwt.ms) 解碼。</span><span class="sxs-lookup"><span data-stu-id="eadab-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="eadab-149">在 *JSON Web Token* 中， *JWT* 代表。</span><span class="sxs-lookup"><span data-stu-id="eadab-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="eadab-150">解碼的權杖會包含一些 JSON 格式專案或宣告。</span><span class="sxs-lookup"><span data-stu-id="eadab-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="eadab-151">請確定已解碼權杖中的 *角色* 宣告包含所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="eadab-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="eadab-152">在下列影像中，您可以看到從應用程式取得的解碼標記，具有 ```Incidents.Read.All``` 、 ```Incidents.ReadWrite.All``` 和 ```AdvancedHunting.Read.All``` 許可權：</span><span class="sxs-lookup"><span data-stu-id="eadab-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![影像 jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="eadab-154">取得最近事件的清單</span><span class="sxs-lookup"><span data-stu-id="eadab-154">Get a list of recent incidents</span></span>

<span data-ttu-id="eadab-155">下列腳本將使用 **Get-Token.ps1** 來存取 API。</span><span class="sxs-lookup"><span data-stu-id="eadab-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="eadab-156">然後，它會檢索過去48小時內最後更新的事件清單，並將清單儲存為 JSON 檔案。</span><span class="sxs-lookup"><span data-stu-id="eadab-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eadab-157">將此腳本儲存在您儲存 **Get-Token.ps1** 的相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="eadab-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

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

<span data-ttu-id="eadab-158">您已經完成了！</span><span class="sxs-lookup"><span data-stu-id="eadab-158">You're all done!</span></span> <span data-ttu-id="eadab-159">您已成功：</span><span class="sxs-lookup"><span data-stu-id="eadab-159">You've successfully:</span></span>

- <span data-ttu-id="eadab-160">建立及註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="eadab-160">Created and registered an application.</span></span>
- <span data-ttu-id="eadab-161">授與該應用程式讀取提醒的許可權。</span><span class="sxs-lookup"><span data-stu-id="eadab-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="eadab-162">連接至 API。</span><span class="sxs-lookup"><span data-stu-id="eadab-162">Connected to the API.</span></span>
- <span data-ttu-id="eadab-163">使用 PowerShell 腳本，傳回過去48小時更新的事件。</span><span class="sxs-lookup"><span data-stu-id="eadab-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="eadab-164">相關文章</span><span class="sxs-lookup"><span data-stu-id="eadab-164">Related articles</span></span>

- [<span data-ttu-id="eadab-165">Microsoft 365 Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="eadab-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="eadab-166">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="eadab-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="eadab-167">建立應用程式以存取沒有使用者的 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eadab-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="eadab-168">建立應用程式以代表使用者存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="eadab-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="eadab-169">建立具有對 Microsoft 365 Defender APIs 的多承租人合作夥伴存取權的應用程式</span><span class="sxs-lookup"><span data-stu-id="eadab-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="eadab-170">使用 Azure Key Vault 管理伺服器應用程式中的機密</span><span class="sxs-lookup"><span data-stu-id="eadab-170">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="eadab-171">OAuth 2.0 使用者登入和 API 存取的授權</span><span class="sxs-lookup"><span data-stu-id="eadab-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
