---
title: 從 MSSP 客戶租使用者提取警示
description: 瞭解如何從客戶租使用者中回遷提醒
keywords: 受管理的安全性服務提供者、mssp、configure、integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: ee2a5e1815dd552753ac7f3dee30df11ac4332e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060547"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a><span data-ttu-id="bba4d-104">從 MSSP 客戶租使用者提取警示</span><span class="sxs-lookup"><span data-stu-id="bba4d-104">Fetch alerts from MSSP customer tenant</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bba4d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="bba4d-105">**Applies to:**</span></span>
- [<span data-ttu-id="bba4d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bba4d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="bba4d-107">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="bba4d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bba4d-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="bba4d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
><span data-ttu-id="bba4d-109">MSSP 會採取此動作。</span><span class="sxs-lookup"><span data-stu-id="bba4d-109">This action is taken by the MSSP.</span></span>


<span data-ttu-id="bba4d-110">有兩種方法可供您提取提醒：</span><span class="sxs-lookup"><span data-stu-id="bba4d-110">There are two ways you can fetch alerts:</span></span>
- <span data-ttu-id="bba4d-111">使用 SIEM 方法</span><span class="sxs-lookup"><span data-stu-id="bba4d-111">Using the SIEM method</span></span>
- <span data-ttu-id="bba4d-112">使用 APIs</span><span class="sxs-lookup"><span data-stu-id="bba4d-112">Using APIs</span></span>

## <a name="fetch-alerts-into-your-siem"></a><span data-ttu-id="bba4d-113">將提醒提取至您的 SIEM</span><span class="sxs-lookup"><span data-stu-id="bba4d-113">Fetch alerts into your SIEM</span></span>

<span data-ttu-id="bba4d-114">若要將提醒回遷至 SIEM 系統，您必須採取下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bba4d-114">To fetch alerts into your SIEM system, you'll need to take the following steps:</span></span>

<span data-ttu-id="bba4d-115">步驟1：建立協力廠商應用程式</span><span class="sxs-lookup"><span data-stu-id="bba4d-115">Step 1: Create a third-party application</span></span>

<span data-ttu-id="bba4d-116">步驟2：從客戶的承租人取得存取和重新整理權杖</span><span class="sxs-lookup"><span data-stu-id="bba4d-116">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
 
<span data-ttu-id="bba4d-117">步驟3：允許 Microsoft Defender Security Center 上的應用程式</span><span class="sxs-lookup"><span data-stu-id="bba4d-117">Step 3: allow your application on Microsoft Defender Security Center</span></span>
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a><span data-ttu-id="bba4d-118">步驟1：在 Azure Active Directory 中建立應用程式 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="bba4d-118">Step 1: Create an application in Azure Active Directory (Azure AD)</span></span>
 
<span data-ttu-id="bba4d-119">您將需要建立應用程式，並授與其許可權，以取得客戶的 Microsoft Defender for Endpoint 租使用者的提醒。</span><span class="sxs-lookup"><span data-stu-id="bba4d-119">You'll need to create an application and grant it permissions to fetch alerts from your customer's Microsoft Defender for Endpoint tenant.</span></span>

1. <span data-ttu-id="bba4d-120">登入 [AZURE AD 入口網站](https://aad.portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="bba4d-120">Sign in to the [Azure AD portal](https://aad.portal.azure.com/).</span></span>

2. <span data-ttu-id="bba4d-121">選取 [ **Azure Active Directory**  >  **應用程式註冊**]。</span><span class="sxs-lookup"><span data-stu-id="bba4d-121">Select **Azure Active Directory** > **App registrations**.</span></span>
 
3. <span data-ttu-id="bba4d-122">按一下 [ **新增註冊**]。</span><span class="sxs-lookup"><span data-stu-id="bba4d-122">Click **New registration**.</span></span>

4. <span data-ttu-id="bba4d-123">指定下列值：</span><span class="sxs-lookup"><span data-stu-id="bba4d-123">Specify the following values:</span></span>

    - <span data-ttu-id="bba4d-124">Name： \<Tenant_name\> SIEM MSSP Connector (以租使用者顯示名稱取代 Tenant_name) </span><span class="sxs-lookup"><span data-stu-id="bba4d-124">Name: \<Tenant_name\> SIEM MSSP Connector (replace Tenant_name with the tenant display name)</span></span>
 
    - <span data-ttu-id="bba4d-125">支援的帳戶類型：僅限此組織目錄中的帳戶</span><span class="sxs-lookup"><span data-stu-id="bba4d-125">Supported account types: Account in this organizational directory only</span></span> 
    - <span data-ttu-id="bba4d-126">重新導向 URI：選取 Web 並輸入 `https://<domain_name>/SiemMsspConnector` (以租使用者名稱取代 <domain_name>) </span><span class="sxs-lookup"><span data-stu-id="bba4d-126">Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector`(replace <domain_name> with the tenant name)</span></span>

5. <span data-ttu-id="bba4d-127">按一下 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="bba4d-127">Click **Register**.</span></span> <span data-ttu-id="bba4d-128">應用程式會顯示在您所擁有的應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="bba4d-128">The application is displayed in the list of applications you own.</span></span>

6. <span data-ttu-id="bba4d-129">選取應用程式，然後按一下 **[概述**]。</span><span class="sxs-lookup"><span data-stu-id="bba4d-129">Select the application, then click **Overview**.</span></span>

7. <span data-ttu-id="bba4d-130">將 [ **Application (client) ID** ] 欄位中的值複製到安全的地方，您必須在下一個步驟中使用此值。</span><span class="sxs-lookup"><span data-stu-id="bba4d-130">Copy the value from the **Application (client) ID** field to a safe place, you will need this in the next step.</span></span>

8. <span data-ttu-id="bba4d-131">在 [新增應用程式] 面板中選取 **憑證 & 密碼** 。</span><span class="sxs-lookup"><span data-stu-id="bba4d-131">Select **Certificate & secrets** in the new application panel.</span></span>

9. <span data-ttu-id="bba4d-132">按一下 [ **新增用戶端密碼**]。</span><span class="sxs-lookup"><span data-stu-id="bba4d-132">Click **New client secret**.</span></span>

    - <span data-ttu-id="bba4d-133">描述：輸入機碼的描述。</span><span class="sxs-lookup"><span data-stu-id="bba4d-133">Description: Enter a description for the key.</span></span>
    - <span data-ttu-id="bba4d-134">到期：選取 **1 年**</span><span class="sxs-lookup"><span data-stu-id="bba4d-134">Expires: Select **In 1 year**</span></span>

 
10. <span data-ttu-id="bba4d-135">按一下 [ **新增**]，將用戶端密碼的值複製到安全的地方，您必須在下一個步驟中執行此操作。</span><span class="sxs-lookup"><span data-stu-id="bba4d-135">Click **Add**, copy the value of the client secret to a safe place, you will need this in the next step.</span></span>
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a><span data-ttu-id="bba4d-136">步驟2：從客戶的承租人取得存取和重新整理權杖</span><span class="sxs-lookup"><span data-stu-id="bba4d-136">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
<span data-ttu-id="bba4d-137">本節會引導您瞭解如何使用 PowerShell 腳本，從客戶的承租人取得標記。</span><span class="sxs-lookup"><span data-stu-id="bba4d-137">This section guides you on how to use a PowerShell script to get the tokens from your customer's tenant.</span></span> <span data-ttu-id="bba4d-138">此腳本會利用上一個步驟中的應用程式，取得使用 OAuth 驗證程式代碼流程的存取和重新整理權杖。</span><span class="sxs-lookup"><span data-stu-id="bba4d-138">This script uses the application from the previous step to get the access and refresh tokens using the OAuth Authorization Code Flow.</span></span>

<span data-ttu-id="bba4d-139">在提供認證之後，您必須授與應用程式的同意，以便在客戶的承租人中布建該應用程式。</span><span class="sxs-lookup"><span data-stu-id="bba4d-139">After providing your credentials, you'll need to grant consent to the application so that the application is provisioned in the customer's tenant.</span></span>


1. <span data-ttu-id="bba4d-140">建立新的資料夾並為其命名： `MsspTokensAcquisition` 。</span><span class="sxs-lookup"><span data-stu-id="bba4d-140">Create a new folder and name it: `MsspTokensAcquisition`.</span></span>

2. <span data-ttu-id="bba4d-141">下載 [LoginBrowser sharepointsync.psm1 模組](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) ，並將它儲存在 `MsspTokensAcquisition` 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="bba4d-141">Download the [LoginBrowser.psm1 module](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) and save it in the `MsspTokensAcquisition` folder.</span></span>

    >[!NOTE]
    ><span data-ttu-id="bba4d-142">在30行，取代 `authorzationUrl` `authorizationUrl` 。</span><span class="sxs-lookup"><span data-stu-id="bba4d-142">In line 30, replace `authorzationUrl` with `authorizationUrl`.</span></span>

3. <span data-ttu-id="bba4d-143">使用下列內容建立檔案，並將其儲存為 `MsspTokensAcquisition.ps1` 資料夾中的名稱：</span><span class="sxs-lookup"><span data-stu-id="bba4d-143">Create a file with the following content and save it with the name `MsspTokensAcquisition.ps1` in the folder:</span></span>
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. <span data-ttu-id="bba4d-144">在資料夾中開啟提升許可權的 PowerShell 命令提示字元 `MsspTokensAcquisition` 。</span><span class="sxs-lookup"><span data-stu-id="bba4d-144">Open an elevated PowerShell command prompt in the `MsspTokensAcquisition` folder.</span></span>

5. <span data-ttu-id="bba4d-145">執行下列命令：`Set-ExecutionPolicy -ExecutionPolicy Bypass`</span><span class="sxs-lookup"><span data-stu-id="bba4d-145">Run the following command: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span></span>

6. <span data-ttu-id="bba4d-146">輸入下列命令： `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span><span class="sxs-lookup"><span data-stu-id="bba4d-146">Enter the following commands: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span></span>
 
    - <span data-ttu-id="bba4d-147">\<client_id\>以您從上一個步驟獲得的 **應用程式 (用戶端) 識別碼** 取代。</span><span class="sxs-lookup"><span data-stu-id="bba4d-147">Replace \<client_id\> with the **Application (client) ID** you got from the previous step.</span></span>
    - <span data-ttu-id="bba4d-148">取代 \<app_key\> 您在上一個步驟中建立的 **用戶端密碼** 。</span><span class="sxs-lookup"><span data-stu-id="bba4d-148">Replace \<app_key\> with the **Client Secret** you created from the previous step.</span></span>
    - <span data-ttu-id="bba4d-149">取代 \<customer_tenant_id\> 您的客戶 **租使用者識別碼**。</span><span class="sxs-lookup"><span data-stu-id="bba4d-149">Replace \<customer_tenant_id\> with your customer's **Tenant ID**.</span></span> 
 

7. <span data-ttu-id="bba4d-150">系統會要求您提供您的認證與同意。</span><span class="sxs-lookup"><span data-stu-id="bba4d-150">You'll be asked to provide your credentials and consent.</span></span> <span data-ttu-id="bba4d-151">忽略頁面重新導向。</span><span class="sxs-lookup"><span data-stu-id="bba4d-151">Ignore the page redirect.</span></span>

8. <span data-ttu-id="bba4d-152">在 [PowerShell] 視窗中，您將會收到存取權杖和重新整理權杖。</span><span class="sxs-lookup"><span data-stu-id="bba4d-152">In the PowerShell window, you'll receive an access token and a refresh token.</span></span> <span data-ttu-id="bba4d-153">儲存重新整理權杖以設定您的 SIEM 連接器。</span><span class="sxs-lookup"><span data-stu-id="bba4d-153">Save the refresh token to configure your SIEM connector.</span></span> 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a><span data-ttu-id="bba4d-154">步驟3：允許 Microsoft Defender Security Center 上的應用程式</span><span class="sxs-lookup"><span data-stu-id="bba4d-154">Step 3: Allow your application on Microsoft Defender Security Center</span></span>
<span data-ttu-id="bba4d-155">您將需要允許在 Microsoft Defender Security Center 中建立的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bba4d-155">You'll need to allow the application you created in Microsoft Defender Security Center.</span></span>
 
<span data-ttu-id="bba4d-156">您必須具有「 **管理入口系統設定** 」許可權，才能允許應用程式。</span><span class="sxs-lookup"><span data-stu-id="bba4d-156">You'll need to have **Manage portal system settings** permission to allow the application.</span></span> <span data-ttu-id="bba4d-157">否則，您必須要求客戶允許您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bba4d-157">Otherwise, you'll need to request your customer to allow the application for you.</span></span>

1. <span data-ttu-id="bba4d-158">移至 `https://securitycenter.windows.com?tid=<customer_tenant_id>` (會 \<customer_tenant_id\> 以客戶的租使用者識別碼取代。</span><span class="sxs-lookup"><span data-stu-id="bba4d-158">Go to `https://securitycenter.windows.com?tid=<customer_tenant_id>` (replace \<customer_tenant_id\> with the customer's tenant ID.</span></span>

2. <span data-ttu-id="bba4d-159">按一下 [**設定**  >  **SIEM**]。</span><span class="sxs-lookup"><span data-stu-id="bba4d-159">Click **Settings** > **SIEM**.</span></span> 

3. <span data-ttu-id="bba4d-160">選取 [ **MSSP** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bba4d-160">Select the **MSSP** tab.</span></span>

4. <span data-ttu-id="bba4d-161">從第一個步驟和您的 **租使用者識別碼** 輸入 **應用程式識別碼**。</span><span class="sxs-lookup"><span data-stu-id="bba4d-161">Enter the **Application ID** from the first step and your **Tenant ID**.</span></span>

5. <span data-ttu-id="bba4d-162">按一下 [ **授權應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="bba4d-162">Click **Authorize application**.</span></span> 

 
<span data-ttu-id="bba4d-163">您現在可以下載 SIEM 的相關設定檔，並連接到 Endpoint for Endpoint API。</span><span class="sxs-lookup"><span data-stu-id="bba4d-163">You can now download the relevant configuration file for your SIEM and connect to the Defender for Endpoint API.</span></span> <span data-ttu-id="bba4d-164">如需詳細資訊，請參閱 [SIEM 工具的「拉入警示](configure-siem.md)」。</span><span class="sxs-lookup"><span data-stu-id="bba4d-164">For more information, see, [Pull alerts to your SIEM tools](configure-siem.md).</span></span>
 

- <span data-ttu-id="bba4d-165">在 [ArcSight 設定檔/Splunk 驗證屬性] 檔案中，透過設定機密值手動寫入您的應用程式金鑰。</span><span class="sxs-lookup"><span data-stu-id="bba4d-165">In the ArcSight configuration file / Splunk Authentication Properties file, write your application key manually by setting the secret value.</span></span>
- <span data-ttu-id="bba4d-166">除了在入口網站中取得重新整理權杖之外，您還可以使用上一個步驟中的腳本來取得重新整理權杖 (或透過其他方式) 取得更新。</span><span class="sxs-lookup"><span data-stu-id="bba4d-166">Instead of acquiring a refresh token in the portal, use the script from the previous step to acquire a refresh token (or acquire it by other means).</span></span>

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a><span data-ttu-id="bba4d-167">使用 APIs 從 MSSP 客戶的承租人取得警示</span><span class="sxs-lookup"><span data-stu-id="bba4d-167">Fetch alerts from MSSP customer's tenant using APIs</span></span>
 
<span data-ttu-id="bba4d-168">如需如何使用 REST API 提取提醒的詳細資訊，請參閱 [使用 REST api 的 Pull 警示](pull-alerts-using-rest-api.md)。</span><span class="sxs-lookup"><span data-stu-id="bba4d-168">For information on how to fetch alerts using REST API, see [Pull alerts using REST API](pull-alerts-using-rest-api.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="bba4d-169">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bba4d-169">See also</span></span>
- [<span data-ttu-id="bba4d-170">授與 MSSP 存取入口網站</span><span class="sxs-lookup"><span data-stu-id="bba4d-170">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="bba4d-171">存取 MSSP 客戶入口網站</span><span class="sxs-lookup"><span data-stu-id="bba4d-171">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="bba4d-172">設定警示通知</span><span class="sxs-lookup"><span data-stu-id="bba4d-172">Configure alert notifications</span></span>](configure-mssp-notifications.md)
