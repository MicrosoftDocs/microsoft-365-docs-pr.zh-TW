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
ms.custom: api
ms.openlocfilehash: 456507533265bc085adc1008f3264e123569a6ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770766"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a>從 MSSP 客戶租使用者提取警示

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
>MSSP 會採取此動作。


有兩種方法可供您提取提醒：
- 使用 SIEM 方法
- 使用 APIs

## <a name="fetch-alerts-into-your-siem"></a>將提醒提取至您的 SIEM

若要將提醒回遷至 SIEM 系統，您必須採取下列步驟：

步驟1：建立協力廠商應用程式

步驟2：從客戶的承租人取得存取和重新整理權杖
 
步驟3：允許 Microsoft Defender 資訊安全中心的應用程式
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>步驟1：在 Azure Active Directory (Azure AD) 中建立應用程式
 
您將需要建立應用程式，並授與其許可權，以取得客戶的 Microsoft Defender for Endpoint 租使用者的提醒。

1. 登入 [AZURE AD 入口網站](https://aad.portal.azure.com/)。

2. 選取 [ **Azure Active Directory**  >  **應用程式註冊**]。
 
3. 按一下 [ **新增註冊**]。

4. 指定下列值：

    - Name： \<Tenant_name\> SIEM MSSP Connector (以租使用者顯示名稱取代 Tenant_name) 
 
    - 支援的帳戶類型：僅限此組織目錄中的帳戶 
    - 重新導向 URI：選取 Web 並輸入 `https://<domain_name>/SiemMsspConnector` (以租使用者名稱取代 <domain_name>) 

5. 按一下 [ **註冊**]。 應用程式會顯示在您所擁有的應用程式清單中。

6. 選取應用程式，然後按一下 **[概述**]。

7. 將 [ **Application (client) ID** ] 欄位中的值複製到安全的地方，您必須在下一個步驟中使用此值。

8. 在 [新增應用程式] 面板中選取 **憑證 & 密碼** 。

9. 按一下 [ **新增用戶端密碼**]。

    - 描述：輸入機碼的描述。
    - 到期：選取 **1 年**

 
10. 按一下 [ **新增**]，將用戶端密碼的值複製到安全的地方，您必須在下一個步驟中執行此操作。
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>步驟2：從客戶的承租人取得存取和重新整理權杖
本節會引導您瞭解如何使用 PowerShell 腳本，從客戶的承租人取得標記。 此腳本會利用上一個步驟中的應用程式，使用 OAuth 的授權碼 Flow 來取得存取和重新整理權杖。

在提供認證之後，您必須授與應用程式的同意，以便在客戶的承租人中布建該應用程式。


1. 建立新的資料夾並為其命名： `MsspTokensAcquisition` 。

2. 下載 [LoginBrowser sharepointsync.psm1 模組](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) ，並將它儲存在 `MsspTokensAcquisition` 資料夾中。

    >[!NOTE]
    >在30行，取代 `authorzationUrl` `authorizationUrl` 。

3. 使用下列內容建立檔案，並將其儲存為 `MsspTokensAcquisition.ps1` 資料夾中的名稱：
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
4. 在資料夾中開啟提升許可權的 PowerShell 命令提示字元 `MsspTokensAcquisition` 。

5. 執行下列命令：`Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. 輸入下列命令： `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`
 
    - \<client_id\>以您從上一個步驟獲得的 **應用程式 (用戶端) 識別碼** 取代。
    - 取代 \<app_key\> 您在上一個步驟中建立的 **用戶端密碼** 。
    - 取代 \<customer_tenant_id\> 您的客戶 **租使用者識別碼**。 
 

7. 系統會要求您提供您的認證與同意。 忽略頁面重新導向。

8. 在 [PowerShell] 視窗中，您將會收到存取權杖和重新整理權杖。 儲存重新整理權杖以設定您的 SIEM 連接器。 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a>步驟3：允許 Microsoft Defender 資訊安全中心的應用程式
您將需要允許在 Microsoft Defender 資訊安全中心中建立的應用程式。
 
您必須具有「 **管理入口系統設定** 」許可權，才能允許應用程式。 否則，您必須要求客戶允許您的應用程式。

1. 移至 `https://securitycenter.windows.com?tid=<customer_tenant_id>` (會 \<customer_tenant_id\> 以客戶的租使用者識別碼取代。

2. 按一下 [**設定**  >  **SIEM**]。 

3. 選取 [ **MSSP** ] 索引標籤。

4. 從第一個步驟和您的 **租使用者識別碼** 輸入 **應用程式識別碼**。

5. 按一下 [ **授權應用程式**]。 

 
您現在可以下載 SIEM 的相關設定檔，並連接到 Endpoint for Endpoint API。 如需詳細資訊，請參閱 [SIEM 工具的「拉入警示](configure-siem.md)」。
 

- 在 [ArcSight 設定檔/Splunk 驗證屬性] 檔案中，透過設定機密值手動寫入您的應用程式金鑰。
- 除了在入口網站中取得重新整理權杖之外，您還可以使用上一個步驟中的腳本來取得重新整理權杖 (或透過其他方式) 取得更新。

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>使用 APIs 從 MSSP 客戶的承租人取得警示
 
如需如何使用 REST API 提取提醒的詳細資訊，請參閱 [使用 REST api 的 Pull 警示](pull-alerts-using-rest-api.md)。


## <a name="see-also"></a>請參閱
- [將入口網站存取權授予 MSSP](grant-mssp-access.md)
- [存取 MSSP 客戶入口網站](access-mssp-portal.md)
- [設定警示通知](configure-mssp-notifications.md)
