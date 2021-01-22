---
title: Hello World for Microsoft 365 Defender REST API
description: 瞭解如何建立應用程式並使用權杖存取 Microsoft 365 Defender API
keywords: App， token， access， aad， app， application registration， powershell， script， global administrator， permission， microsoft 365 defender
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
ms.openlocfilehash: 66afa27d0fa7a092d3f9e9ed6c3b6abc6020cb8d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928375"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="628aa-104">Hello World for Microsoft 365 Defender REST API</span><span class="sxs-lookup"><span data-stu-id="628aa-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="628aa-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="628aa-105">**Applies to:**</span></span>

- <span data-ttu-id="628aa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="628aa-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="628aa-107">部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。</span><span class="sxs-lookup"><span data-stu-id="628aa-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="628aa-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="628aa-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="628aa-109">使用簡單的 PowerShell 腳本取得事件</span><span class="sxs-lookup"><span data-stu-id="628aa-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="628aa-110">完成此專案需要 5 到 10 分鐘。</span><span class="sxs-lookup"><span data-stu-id="628aa-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="628aa-111">預估的這個時間包括註冊應用程式，以及從 PowerShell 範例腳本中應用程式代碼。</span><span class="sxs-lookup"><span data-stu-id="628aa-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="628aa-112">在 Azure Active Directory 中註冊應用程式</span><span class="sxs-lookup"><span data-stu-id="628aa-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="628aa-113">以具有 [全域系統管理員](https://portal.azure.com) 角色的使用者之名 **來簽署** Azure。</span><span class="sxs-lookup"><span data-stu-id="628aa-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="628aa-114">流覽至 **Azure Active Directory**  >  **App 註冊**  >  **新增註冊**。</span><span class="sxs-lookup"><span data-stu-id="628aa-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure 的影像和應用程式註冊的流覽](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="628aa-116">在註冊表單中，選擇應用程式的名稱， **然後選取註冊**。</span><span class="sxs-lookup"><span data-stu-id="628aa-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="628aa-117">選取重新導向 URI 是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="628aa-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="628aa-118">完成此範例不需要一個。</span><span class="sxs-lookup"><span data-stu-id="628aa-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="628aa-119">在您的應用程式頁面上，選取我的組織使用的 **API** 許可權新增許可權 API > Microsoft 威脅防護，然後選取  >    >  \*\*\*\* **Microsoft 威脅防護**。 </span><span class="sxs-lookup"><span data-stu-id="628aa-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="628aa-120">您的應用程式現在可以存取 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="628aa-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="628aa-121">*Microsoft 威脅防護* 是 Microsoft 365 Defender 的前一個名稱，不會顯示在原始清單中。</span><span class="sxs-lookup"><span data-stu-id="628aa-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="628aa-122">您必須開始在文字方塊中撰寫其名稱，它就會出現。</span><span class="sxs-lookup"><span data-stu-id="628aa-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="628aa-123">![API 許可權選取的影像](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="628aa-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="628aa-124">選擇 **應用程式許可權**  >  **事件。讀取。全部**，然後選取 **新增許可權**。</span><span class="sxs-lookup"><span data-stu-id="628aa-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![API 存取和 API 選取的影像](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="628aa-126">選取 **授予系統管理員同意**。</span><span class="sxs-lookup"><span data-stu-id="628aa-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="628aa-127">每次您新增許可權時，都必須選取授予 **系統管理員同意** ，該同意才能生效。</span><span class="sxs-lookup"><span data-stu-id="628aa-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![授予許可權的影像](../../media/grant-consent.PNG)

6. <span data-ttu-id="628aa-129">在應用程式中新增密碼。</span><span class="sxs-lookup"><span data-stu-id="628aa-129">Add a secret to the application.</span></span> <span data-ttu-id="628aa-130">選取 **&秘訣、** 新增描述至機密，然後選取新增 **。**</span><span class="sxs-lookup"><span data-stu-id="628aa-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="628aa-131">選取新增 **後，** 選取 **複製產生的密碼值**。</span><span class="sxs-lookup"><span data-stu-id="628aa-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="628aa-132">您離開後將無法取回密碼值。</span><span class="sxs-lookup"><span data-stu-id="628aa-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![建立應用程式金鑰的影像](../../media/webapp-create-key2.png)

7. <span data-ttu-id="628aa-134">在安全的地方記錄您的應用程式識別碼和租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="628aa-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="628aa-135">這些清單會列在應用程式 **頁面的** 概覽下。</span><span class="sxs-lookup"><span data-stu-id="628aa-135">They're listed under **Overview** on your application page.</span></span>

   ![已建立應用程式識別碼的影像](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="628aa-137">使用應用程式取得權杖，並使用權杖存取 API</span><span class="sxs-lookup"><span data-stu-id="628aa-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="628aa-138">有關 Azure Active Directory 權杖詳細資訊，請參閱 [Azure AD 教學課程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。</span><span class="sxs-lookup"><span data-stu-id="628aa-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="628aa-139">雖然本示範應用程式中的範例會鼓勵您貼上密碼值以進行測試，但您絕對不應該將秘訣貼入實際執行中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="628aa-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="628aa-140">協力廠商可能會使用您的密碼存取資源。</span><span class="sxs-lookup"><span data-stu-id="628aa-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="628aa-141">您可以使用 Azure 金鑰保存庫，協助保護您 [App 的秘訣安全](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)。</span><span class="sxs-lookup"><span data-stu-id="628aa-141">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="628aa-142">有關如何保護應用程式的實用範例，請參閱使用 Azure 金鑰庫管理伺服器 [應用程式中的秘訣](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="628aa-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="628aa-143">複製下列腳本，並貼到您最愛的文字編輯器中。</span><span class="sxs-lookup"><span data-stu-id="628aa-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="628aa-144">另存 **新Get-Token.ps1。**</span><span class="sxs-lookup"><span data-stu-id="628aa-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="628aa-145">您也可以在 PowerShell ISE 中就地執行程式碼，但您應儲存程式碼，因為當我們使用下一節的事件提取腳本時，必須再次執行。</span><span class="sxs-lookup"><span data-stu-id="628aa-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="628aa-146">此腳本會產生權杖，並將其儲存在工作資料夾的名稱下 *，Latest-token.txt。*</span><span class="sxs-lookup"><span data-stu-id="628aa-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

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

#### <a name="validate-the-token"></a><span data-ttu-id="628aa-147">驗證權杖</span><span class="sxs-lookup"><span data-stu-id="628aa-147">Validate the token</span></span>

1. <span data-ttu-id="628aa-148">將您收到的權杖複製並貼到 [JWT](https://jwt.ms) 進行解碼。</span><span class="sxs-lookup"><span data-stu-id="628aa-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="628aa-149">*JWT* 代表 *JSON Web Token。*</span><span class="sxs-lookup"><span data-stu-id="628aa-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="628aa-150">解碼權杖會包含數個 JSON 格式的專案或領取。</span><span class="sxs-lookup"><span data-stu-id="628aa-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="628aa-151">確認在 *解碼* 權杖中要求的角色包含所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="628aa-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="628aa-152">在下列影像中，您可以看見從應用程式取得、具有 、及許可權 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` 的譯 ```AdvancedHunting.Read.All``` 碼權杖：</span><span class="sxs-lookup"><span data-stu-id="628aa-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![影像jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="628aa-154">取得最近事件的清單</span><span class="sxs-lookup"><span data-stu-id="628aa-154">Get a list of recent incidents</span></span>

<span data-ttu-id="628aa-155">下列腳本 **將使用Get-Token.ps1存取** API。</span><span class="sxs-lookup"><span data-stu-id="628aa-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="628aa-156">然後，它會取回過去 48 小時內更新的事件清單，然後將清單另存為 JSON 檔案。</span><span class="sxs-lookup"><span data-stu-id="628aa-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="628aa-157">將這個腳本儲存在您儲存該腳本的 **Get-Token.ps1。**</span><span class="sxs-lookup"><span data-stu-id="628aa-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

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

<span data-ttu-id="628aa-158">大完成了！</span><span class="sxs-lookup"><span data-stu-id="628aa-158">You're all done!</span></span> <span data-ttu-id="628aa-159">您已成功：</span><span class="sxs-lookup"><span data-stu-id="628aa-159">You've successfully:</span></span>

- <span data-ttu-id="628aa-160">建立並登錄應用程式。</span><span class="sxs-lookup"><span data-stu-id="628aa-160">Created and registered an application.</span></span>
- <span data-ttu-id="628aa-161">已授予該應用程式讀取警示的許可權。</span><span class="sxs-lookup"><span data-stu-id="628aa-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="628aa-162">已連接至 API。</span><span class="sxs-lookup"><span data-stu-id="628aa-162">Connected to the API.</span></span>
- <span data-ttu-id="628aa-163">使用 PowerShell 腳本來退回過去 48 小時內更新的事件。</span><span class="sxs-lookup"><span data-stu-id="628aa-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="628aa-164">相關文章</span><span class="sxs-lookup"><span data-stu-id="628aa-164">Related articles</span></span>

- [<span data-ttu-id="628aa-165">Microsoft 365 Defender API 概觀</span><span class="sxs-lookup"><span data-stu-id="628aa-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="628aa-166">存取 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="628aa-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="628aa-167">建立應用程式以在沒有使用者的情況下存取 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="628aa-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="628aa-168">建立應用程式以代表使用者存取 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="628aa-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="628aa-169">建立具有 Microsoft 365 Defender API 多租使用者合作夥伴存取權的應用程式</span><span class="sxs-lookup"><span data-stu-id="628aa-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="628aa-170">使用 Azure 金鑰庫管理伺服器應用程式中的秘訣</span><span class="sxs-lookup"><span data-stu-id="628aa-170">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="628aa-171">OAuth 2.0 使用者簽署和 API 存取的授權</span><span class="sxs-lookup"><span data-stu-id="628aa-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
