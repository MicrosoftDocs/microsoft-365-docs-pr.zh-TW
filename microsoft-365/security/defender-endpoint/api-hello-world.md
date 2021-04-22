---
title: Microsoft Defender for Endpoint API 的 Hello World
ms.reviewer: ''
description: 建立 Microsoft Defender for Endpoint API 的做法「Hello world'-style API 呼叫」。
keywords: api、支援的 api、高級搜尋、查詢
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
ms.openlocfilehash: f4571607181fc96d87934ff60801643f5969e7e9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929248"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a><span data-ttu-id="f8fa1-104">Microsoft Defender for Endpoint API-Hello World</span><span class="sxs-lookup"><span data-stu-id="f8fa1-104">Microsoft Defender for Endpoint API - Hello World</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f8fa1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f8fa1-105">**Applies to:**</span></span> 
- [<span data-ttu-id="f8fa1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f8fa1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


- <span data-ttu-id="f8fa1-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="f8fa1-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f8fa1-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a><span data-ttu-id="f8fa1-109">使用簡單的 PowerShell 腳本取得提醒</span><span class="sxs-lookup"><span data-stu-id="f8fa1-109">Get Alerts using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="f8fa1-110">在這個範例中需要多久時間？</span><span class="sxs-lookup"><span data-stu-id="f8fa1-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="f8fa1-111">只需要5分鐘完成兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="f8fa1-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="f8fa1-112">應用程式註冊</span><span class="sxs-lookup"><span data-stu-id="f8fa1-112">Application registration</span></span>
- <span data-ttu-id="f8fa1-113">使用範例：只需要複製/貼上簡短的 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="f8fa1-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="f8fa1-114">我需要連線許可權嗎？</span><span class="sxs-lookup"><span data-stu-id="f8fa1-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="f8fa1-115">在 [應用程式註冊] 階段，您的 Azure Active Directory (Azure AD) 租使用者必須具有 **全域系統管理員** 角色。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="f8fa1-116">步驟 1-在 Azure Active Directory 中建立應用程式</span><span class="sxs-lookup"><span data-stu-id="f8fa1-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="f8fa1-117">使用您的 **全域系統管理員** 使用者登入 [Azure](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="f8fa1-118">流覽至 [ **Azure Active Directory**  >  **應用程式註冊**]  >  **新註冊**。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 的影像及應用程式註冊導覽](images/atp-azure-new-app2.png)

3. <span data-ttu-id="f8fa1-120">在 [註冊] 表單中，選擇應用程式的名稱，然後按一下 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-120">In the registration form, choose a name for your application and then click **Register**.</span></span>

4. <span data-ttu-id="f8fa1-121">讓您的應用程式能夠存取使用者的 Defender，並指派「 **讀取所有警示** 」的許可權：</span><span class="sxs-lookup"><span data-stu-id="f8fa1-121">Allow your Application to access Defender for Endpoint and assign it **'Read all alerts'** permission:</span></span>

   - <span data-ttu-id="f8fa1-122">在 [應用程式] 頁面上，按一下 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織] 使用**> type **WindowsDefenderATP** ，然後按一下 [ **WindowsDefenderATP**]。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-122">On your application page, click **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and click on **WindowsDefenderATP**.</span></span>

   - <span data-ttu-id="f8fa1-123">**附注**： WindowsDefenderATP 不會出現在原始清單中。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-123">**Note**: WindowsDefenderATP does not appear in the original list.</span></span> <span data-ttu-id="f8fa1-124">您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 存取和 API selection1 的影像](images/add-permission.png)

   - <span data-ttu-id="f8fa1-126">選擇 [**應用程式許可權**]  >  **警示。讀取。所有**> 按一下 [**新增許可權**]</span><span class="sxs-lookup"><span data-stu-id="f8fa1-126">Choose **Application permissions** > **Alert.Read.All** > Click on **Add permissions**</span></span>

   ![API 存取和 API selection2 的影像](images/application-permissions.png)

   <span data-ttu-id="f8fa1-128">**重要** 須知：您必須選取相關的許可權。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-128">**Important note**: You need to select the relevant permissions.</span></span> <span data-ttu-id="f8fa1-129">「讀取所有警示」只是範例！</span><span class="sxs-lookup"><span data-stu-id="f8fa1-129">'Read All Alerts' is only an example!</span></span>

     <span data-ttu-id="f8fa1-130">例如，</span><span class="sxs-lookup"><span data-stu-id="f8fa1-130">For instance,</span></span>

     - <span data-ttu-id="f8fa1-131">若要 [執行高級查詢](run-advanced-query-api.md)，請選取「執行高級查詢」許可權</span><span class="sxs-lookup"><span data-stu-id="f8fa1-131">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
     - <span data-ttu-id="f8fa1-132">若要 [隔離機器](isolate-machine.md)，請選取「隔離電腦」許可權</span><span class="sxs-lookup"><span data-stu-id="f8fa1-132">To [isolate a machine](isolate-machine.md), select 'Isolate machine' permission</span></span>
     - <span data-ttu-id="f8fa1-133">若要決定您需要的許可權，請參閱您想要呼叫之 API 中的 [ **許可權** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="f8fa1-134">按一下 **[授與同意**]</span><span class="sxs-lookup"><span data-stu-id="f8fa1-134">Click **Grant consent**</span></span>

    - <span data-ttu-id="f8fa1-135">**附注**：每次您新增許可權時，您必須按一下 **[授與同意** 才能讓新的許可權生效。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-135">**Note**: Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

    ![授與許可權的影像](images/grant-consent.png)

6. <span data-ttu-id="f8fa1-137">將密碼新增至應用程式。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-137">Add a secret to the application.</span></span>

    - <span data-ttu-id="f8fa1-138">按一下 [ **憑證 & 機密**]，將 description 新增至密碼，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-138">Click **Certificates & secrets**, add description to the secret and click **Add**.</span></span>

    <span data-ttu-id="f8fa1-139">**重要** 事項：按一下 [新增] 後，請 **複製產生的機密值**。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-139">**Important**: After click Add, **copy the generated secret value**.</span></span> <span data-ttu-id="f8fa1-140">離開後，您將無法進行找回！</span><span class="sxs-lookup"><span data-stu-id="f8fa1-140">You won't be able to retrieve after you leave!</span></span>

    ![建立應用程式機碼的影像](images/webapp-create-key2.png)

7. <span data-ttu-id="f8fa1-142">記下來記錄應用程式識別碼和您的租使用者 ID:</span><span class="sxs-lookup"><span data-stu-id="f8fa1-142">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="f8fa1-143">在 [應用程式] 頁面上，移至 **[簡介** ]，然後複製下列專案：</span><span class="sxs-lookup"><span data-stu-id="f8fa1-143">On your application page, go to **Overview** and copy the following:</span></span>

   ![建立之應用程式識別碼的影像](images/app-and-tenant-ids.png)


<span data-ttu-id="f8fa1-145">做！</span><span class="sxs-lookup"><span data-stu-id="f8fa1-145">Done!</span></span> <span data-ttu-id="f8fa1-146">您已成功註冊應用程式！</span><span class="sxs-lookup"><span data-stu-id="f8fa1-146">You have successfully registered an application!</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="f8fa1-147">步驟 2-使用此應用程式取得權杖，並使用此權杖來存取 API。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-147">Step 2 - Get a token using the App and use this token to access the API.</span></span>

-   <span data-ttu-id="f8fa1-148">將下列腳本複製到 PowerShell ISE 或文字編輯器，並將其儲存為 "**Get-Token.ps1**"</span><span class="sxs-lookup"><span data-stu-id="f8fa1-148">Copy the script below to PowerShell ISE or to a text editor, and save it as "**Get-Token.ps1**"</span></span>
-   <span data-ttu-id="f8fa1-149">執行此腳本會產生權杖，並將其儲存在工作資料夾中，名稱為 "**Latest-token.txt**" 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-149">Running this script will generate a token and will save it in the working folder under the name "**Latest-token.txt**".</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

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

-   <span data-ttu-id="f8fa1-150">健全檢查：</span><span class="sxs-lookup"><span data-stu-id="f8fa1-150">Sanity Check:</span></span><br>
<span data-ttu-id="f8fa1-151">執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-151">Run the script.</span></span><br>
<span data-ttu-id="f8fa1-152">在您的瀏覽器中，移至： https://jwt.ms/</span><span class="sxs-lookup"><span data-stu-id="f8fa1-152">In your browser go to: https://jwt.ms/</span></span> <br>
<span data-ttu-id="f8fa1-153">將權杖複製 (Latest-token.txt 檔案) 的內容。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-153">Copy the token (the content of the Latest-token.txt file).</span></span><br>
<span data-ttu-id="f8fa1-154">貼上方框。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-154">Paste in the top box.</span></span><br>
<span data-ttu-id="f8fa1-155">尋找「角色」一節。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-155">Look for the "roles" section.</span></span> <span data-ttu-id="f8fa1-156">尋找警示。讀取。所有角色。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-156">Find the Alert.Read.All role.</span></span>

![影像 jwt.ms](images/api-jwt-ms.png)

### <a name="lets-get-the-alerts"></a><span data-ttu-id="f8fa1-158">讓我們取得警示！</span><span class="sxs-lookup"><span data-stu-id="f8fa1-158">Lets get the Alerts!</span></span>

-   <span data-ttu-id="f8fa1-159">下列腳本將使用 **Get-Token.ps1** 來存取 API，並會收到過去48小時的警示。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-159">The script below will use **Get-Token.ps1** to access the API and will get the past 48 hours Alerts.</span></span>
-   <span data-ttu-id="f8fa1-160">將此腳本儲存在您儲存先前腳本 **Get-Token.ps1** 的相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-160">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span> 
-   <span data-ttu-id="f8fa1-161">此腳本會建立兩個檔案 (json 及 csv) 與腳本相同的資料夾中的資料。</span><span class="sxs-lookup"><span data-stu-id="f8fa1-161">The script creates two files (json and csv) with the data in the same folder as the scripts.</span></span>

```
# Returns Alerts created in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Alert from the last 48 hours. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")       

# The URL contains the type of query and the time filter we create above
# Read more about other query options and filters at   Https://TBD- add the documentation link
$url = "https://api.securitycenter.microsoft.com/api/alerts?`$filter=alertCreationTime ge $dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the alerts from the results. 
$alerts =  ($response | ConvertFrom-Json).value | ConvertTo-Json

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json and as csv
$outputJsonPath = "./Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "./Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
($alerts | ConvertFrom-Json) | Export-CSV $outputCsvPath -NoTypeInformation 
```

<span data-ttu-id="f8fa1-162">您已經完成了！</span><span class="sxs-lookup"><span data-stu-id="f8fa1-162">You’re all done!</span></span> <span data-ttu-id="f8fa1-163">您剛剛成功：</span><span class="sxs-lookup"><span data-stu-id="f8fa1-163">You have just successfully:</span></span>
-   <span data-ttu-id="f8fa1-164">建立及註冊和應用程式</span><span class="sxs-lookup"><span data-stu-id="f8fa1-164">Created and registered and application</span></span>
-   <span data-ttu-id="f8fa1-165">授與該應用程式讀取提醒的許可權</span><span class="sxs-lookup"><span data-stu-id="f8fa1-165">Granted permission for that application to read alerts</span></span>
-   <span data-ttu-id="f8fa1-166">已連接 API</span><span class="sxs-lookup"><span data-stu-id="f8fa1-166">Connected the API</span></span>
-   <span data-ttu-id="f8fa1-167">使用 PowerShell 腳本傳回過去48小時內建立的警示</span><span class="sxs-lookup"><span data-stu-id="f8fa1-167">Used a PowerShell script to return alerts created in the past 48 hours</span></span>



## <a name="related-topic"></a><span data-ttu-id="f8fa1-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="f8fa1-168">Related topic</span></span>
- [<span data-ttu-id="f8fa1-169">Microsoft Defender for Endpoint APIs</span><span class="sxs-lookup"><span data-stu-id="f8fa1-169">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="f8fa1-170">使用應用程式內容存取 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f8fa1-170">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="f8fa1-171">使用使用者內容存取 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f8fa1-171">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
