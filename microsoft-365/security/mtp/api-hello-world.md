---
title: Microsoft 365 Defender REST API 的 Hello World 版
description: 瞭解如何建立應用程式，並使用權杖來存取 Microsoft 365 Defender APIs
keywords: 應用程式、權杖、存取、aad、app、application registration、powershell、script、全域管理員、許可權
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
ms.openlocfilehash: bd4f7e5485d67cf74477900ae2cc5c77f1a6ee41
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844041"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="8a14c-104">Microsoft 365 Defender REST API 的 Hello World 版</span><span class="sxs-lookup"><span data-stu-id="8a14c-104">Hello World for Microsoft 365 Defender REST API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8a14c-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="8a14c-105">**Applies to:**</span></span>
- <span data-ttu-id="8a14c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a14c-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="8a14c-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="8a14c-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8a14c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="8a14c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="8a14c-109">使用簡單的 PowerShell 腳本取得事件</span><span class="sxs-lookup"><span data-stu-id="8a14c-109">Get incidents using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="8a14c-110">在這個範例中需要多久時間？</span><span class="sxs-lookup"><span data-stu-id="8a14c-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="8a14c-111">只需要5分鐘完成兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="8a14c-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="8a14c-112">應用程式註冊</span><span class="sxs-lookup"><span data-stu-id="8a14c-112">Application registration</span></span>
- <span data-ttu-id="8a14c-113">使用範例：只需要複製/貼上簡短的 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="8a14c-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="8a14c-114">我需要連線許可權嗎？</span><span class="sxs-lookup"><span data-stu-id="8a14c-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="8a14c-115">在 [應用程式註冊] 階段，您的 Azure Active Directory (Azure AD) 租使用者必須具有 **全域系統管理員** 角色。</span><span class="sxs-lookup"><span data-stu-id="8a14c-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="8a14c-116">步驟 1-在 Azure Active Directory 中建立應用程式</span><span class="sxs-lookup"><span data-stu-id="8a14c-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="8a14c-117">使用您的 **全域系統管理員** 使用者登入 [Azure](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="8a14c-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="8a14c-118">流覽至 [ **Azure Active Directory**  >  **應用程式註冊** ]  >  **新註冊** 。</span><span class="sxs-lookup"><span data-stu-id="8a14c-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 的影像及應用程式註冊導覽](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="8a14c-120">在 [註冊] 表單中，選擇應用程式的名稱，然後選取 [ **註冊** ]。</span><span class="sxs-lookup"><span data-stu-id="8a14c-120">In the registration form, choose a name for your application and then select **Register**.</span></span>

4. <span data-ttu-id="8a14c-121">允許應用程式存取 Microsoft Defender for Endpoint，並指派它 **讀取所有的事件** 許可權：</span><span class="sxs-lookup"><span data-stu-id="8a14c-121">Allow your Application to access Microsoft Defender for Endpoint and assign it **Read all incidents** permission:</span></span>

   - <span data-ttu-id="8a14c-122">在 [應用程式] 頁面上，選取 [ **API 許可權**  >  **新增許可權** ]  >  **APIs 我的組織使用** > 輸入 **microsoft 365 defender** ，然後在 **microsoft 365 defender** 上選取。</span><span class="sxs-lookup"><span data-stu-id="8a14c-122">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **Microsoft 365 Defender** and select on **Microsoft 365 Defender**.</span></span>

   >[!NOTE]
   ><span data-ttu-id="8a14c-123">Microsoft 365 Defender 未出現在原始清單中。</span><span class="sxs-lookup"><span data-stu-id="8a14c-123">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="8a14c-124">您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。</span><span class="sxs-lookup"><span data-stu-id="8a14c-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 存取和 API 選取的影像](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="8a14c-126">選擇 [ **應用程式許可權** ]  >  **事件。讀取。所有** > 在 [ **新增] 許可權** 上選取</span><span class="sxs-lookup"><span data-stu-id="8a14c-126">Choose **Application permissions** > **Incident.Read.All** > Select on **Add permissions**</span></span>

   ![API 存取和 API 選取的影像](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   ><span data-ttu-id="8a14c-128">您必須選取相關的許可權。</span><span class="sxs-lookup"><span data-stu-id="8a14c-128">You need to select the relevant permissions.</span></span> 

     <span data-ttu-id="8a14c-129">例如，</span><span class="sxs-lookup"><span data-stu-id="8a14c-129">For instance,</span></span>

     - <span data-ttu-id="8a14c-130">若要決定您需要的許可權，請參閱您想要呼叫之 API 中的 [ **許可權** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="8a14c-130">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="8a14c-131">選取 **[授與系統管理員同意** ]</span><span class="sxs-lookup"><span data-stu-id="8a14c-131">Select **Grant admin consent**</span></span>

    - >[!NOTE]
      > <span data-ttu-id="8a14c-132">每次您新增許可權時，您必須選取 **[授與同意** 才能讓新許可權同意] 生效。</span><span class="sxs-lookup"><span data-stu-id="8a14c-132">Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

    ![授與許可權的影像](../../media/grant-consent.PNG)

6. <span data-ttu-id="8a14c-134">將密碼新增至應用程式。</span><span class="sxs-lookup"><span data-stu-id="8a14c-134">Add a secret to the application.</span></span>

    - <span data-ttu-id="8a14c-135">選取 [ **& 密碼的憑證** ]，將 description 新增至 [密碼]，然後選取 [ **新增** ]。</span><span class="sxs-lookup"><span data-stu-id="8a14c-135">Select **Certificates & secrets** , add description to the secret and select **Add**.</span></span>

    >[!IMPORTANT]
    > <span data-ttu-id="8a14c-136">選取 [ **新增** ] 之後，請 **複製產生的密碼值** 。</span><span class="sxs-lookup"><span data-stu-id="8a14c-136">After selecting **Add** , **copy the generated secret value**.</span></span> <span data-ttu-id="8a14c-137">離開後，您將無法進行找回！</span><span class="sxs-lookup"><span data-stu-id="8a14c-137">You won't be able to retrieve after you leave!</span></span>

    ![建立應用程式機碼的影像](../../media/webapp-create-key2.png)

7. <span data-ttu-id="8a14c-139">記下來記錄應用程式識別碼和您的租使用者 ID:</span><span class="sxs-lookup"><span data-stu-id="8a14c-139">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="8a14c-140">在 [應用程式] 頁面上，移至 **[簡介** ]，然後複製下列專案：</span><span class="sxs-lookup"><span data-stu-id="8a14c-140">On your application page, go to **Overview** and copy the following:</span></span>

   ![建立之應用程式識別碼的影像](../../media/app-and-tenant-ids.png)


<span data-ttu-id="8a14c-142">做！</span><span class="sxs-lookup"><span data-stu-id="8a14c-142">Done!</span></span> <span data-ttu-id="8a14c-143">您已成功註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="8a14c-143">You have successfully registered an application.</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="8a14c-144">步驟 2-使用此應用程式取得權杖，並使用此權杖來存取 API。</span><span class="sxs-lookup"><span data-stu-id="8a14c-144">Step 2 - Get a token using the App and use this token to access the API.</span></span>

-   <span data-ttu-id="8a14c-145">將下列腳本複製到 PowerShell ISE 或文字編輯器，並將其儲存為 " **Get-Token.ps1** "</span><span class="sxs-lookup"><span data-stu-id="8a14c-145">Copy the script below to PowerShell ISE or to a text editor, and save it as " **Get-Token.ps1** "</span></span>
-   <span data-ttu-id="8a14c-146">執行此腳本會產生權杖，並將其儲存在工作資料夾中，名稱為 " **Latest-token.txt** " 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="8a14c-146">Running this script will generate a token and will save it in the working folder under the name " **Latest-token.txt** ".</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

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

-   <span data-ttu-id="8a14c-147">健全檢查：</span><span class="sxs-lookup"><span data-stu-id="8a14c-147">Sanity Check:</span></span><br>
<span data-ttu-id="8a14c-148">執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="8a14c-148">Run the script.</span></span><br>
<span data-ttu-id="8a14c-149">在您的瀏覽器中，移至： https://jwt.ms/</span><span class="sxs-lookup"><span data-stu-id="8a14c-149">In your browser go to: https://jwt.ms/</span></span> <br>
<span data-ttu-id="8a14c-150">將權杖複製 (Latest-token.txt 檔案) 的內容。</span><span class="sxs-lookup"><span data-stu-id="8a14c-150">Copy the token (the content of the Latest-token.txt file).</span></span><br>
<span data-ttu-id="8a14c-151">貼上方框。</span><span class="sxs-lookup"><span data-stu-id="8a14c-151">Paste in the top box.</span></span><br>
<span data-ttu-id="8a14c-152">尋找「角色」一節。</span><span class="sxs-lookup"><span data-stu-id="8a14c-152">Look for the "roles" section.</span></span> <span data-ttu-id="8a14c-153">尋找 ```Incidents.Read.All``` 角色。</span><span class="sxs-lookup"><span data-stu-id="8a14c-153">Find the ```Incidents.Read.All``` role.</span></span><br>
<span data-ttu-id="8a14c-154">下列範例來自具有和許可權的應用程式 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` 。</span><span class="sxs-lookup"><span data-stu-id="8a14c-154">The below example is from an app that has ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions.</span></span>

![影像 jwt.ms](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a><span data-ttu-id="8a14c-156">讓我們能夠取得事件！</span><span class="sxs-lookup"><span data-stu-id="8a14c-156">Lets get the Incidents!</span></span>

-   <span data-ttu-id="8a14c-157">下列腳本將使用 **Get-Token.ps1** 來存取 API，並在過去48小時內取得最後一次更新的事件。</span><span class="sxs-lookup"><span data-stu-id="8a14c-157">The script below will use **Get-Token.ps1** to access the API and will get the incidents last updated in past 48 hours.</span></span>
-   <span data-ttu-id="8a14c-158">將此腳本儲存在您儲存先前腳本 **Get-Token.ps1** 的相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="8a14c-158">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span> 
-   <span data-ttu-id="8a14c-159">編寫 json 檔案的腳本，該檔案與腳本位於相同的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="8a14c-159">The script a json file with the data in the same folder as the scripts.</span></span>

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

<span data-ttu-id="8a14c-160">您已經完成了！</span><span class="sxs-lookup"><span data-stu-id="8a14c-160">You're all done!</span></span> <span data-ttu-id="8a14c-161">您剛剛成功：</span><span class="sxs-lookup"><span data-stu-id="8a14c-161">You have just successfully:</span></span>
-   <span data-ttu-id="8a14c-162">建立及註冊和應用程式</span><span class="sxs-lookup"><span data-stu-id="8a14c-162">Created and registered and application</span></span>
-   <span data-ttu-id="8a14c-163">授與該應用程式讀取提醒的許可權</span><span class="sxs-lookup"><span data-stu-id="8a14c-163">Granted permission for that application to read alerts</span></span>
-   <span data-ttu-id="8a14c-164">已連接 API</span><span class="sxs-lookup"><span data-stu-id="8a14c-164">Connected the API</span></span>
-   <span data-ttu-id="8a14c-165">使用 PowerShell 腳本傳回過去48小時內建立的事件</span><span class="sxs-lookup"><span data-stu-id="8a14c-165">Used a PowerShell script to return incidents created in the past 48 hours</span></span>



## <a name="related-topic"></a><span data-ttu-id="8a14c-166">相關主題</span><span class="sxs-lookup"><span data-stu-id="8a14c-166">Related topic</span></span>
- [<span data-ttu-id="8a14c-167">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="8a14c-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="8a14c-168">使用應用程式內容存取 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a14c-168">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="8a14c-169">使用使用者內容存取 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a14c-169">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
