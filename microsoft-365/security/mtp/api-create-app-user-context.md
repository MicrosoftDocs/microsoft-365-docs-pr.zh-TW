---
title: 以使用者的名義存取 Microsoft 威脅防護 APIs
description: 瞭解如何使用代表使用者存取 Microsoft 威脅防護 APIs
keywords: 代表使用者、api、應用程式、使用者、存取權杖、token 等存取
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
ms.openlocfilehash: a62d90004d00e8c553f1b011e77b871df7cd94f4
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197794"
---
# <a name="access-microsoft-threat-protection-apis-on-behalf-of-user"></a>代表使用者存取 Microsoft 威脅防護 APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：****
- Microsoft 威脅防護

>[!IMPORTANT] 
>一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


此頁面說明如何建立應用程式，以讓使用者能夠以程式設計方式存取 Microsoft 威脅防護。

如果您需要以程式設計方式存取 Microsoft 威脅防護，但沒有使用者，請參閱 [Create a app to Access Microsoft 威脅 protection （沒有使用者](api-create-app-web.md)）。

如果您不確定需要哪種存取權，請閱讀 [Access Microsoft 威脅防護 APIs](api-access.md)。

Microsoft 威脅防護會透過一組程式設計 APIs 來公開其資料和動作。 這些 APIs 可讓您根據 Microsoft 威脅防護功能來自動化工作流程及創新。 API 存取需要 OAuth 2.0 驗證。 如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

一般來講，您必須採取下列步驟，才能使用 APIs：
- 建立 AAD 應用程式
- 使用此應用程式取得存取 token
- 使用權杖存取 Microsoft 威脅防護 API

此頁面說明如何建立 AAD 應用程式、取得 Microsoft 威脅防護的存取權杖，以及驗證權杖。

>[!NOTE]
> 代表使用者存取 Microsoft 威脅防護 API 時，您將需要正確的應用程式許可權和使用者許可權。


>[!TIP]
> 如果您有許可權執行入口網站中的動作，您就具有在 API 中執行該動作的許可權。

## <a name="create-an-app"></a>建立應用程式

1. 使用具有**全域系統管理員**角色的使用者登入[Azure](https://portal.azure.com) 。

2. 流覽至 [ **Azure Active Directory**  >  **應用程式註冊**]  >  **新註冊**。 

   ![Microsoft Azure 的影像及應用程式註冊導覽](../../media/atp-azure-new-app2.png)

3. 在註冊中，輸入下列資訊，然後按一下 [ **註冊**]。

   ![建立應用程式視窗的影像](../../media/nativeapp-create2.PNG)

   - **名稱：** 您的應用程式名稱
   - **應用程式類型：** 公用用戶端
   - 重新**導向 URI：**https://portal.azure.com

4. 若要讓您的應用程式能夠存取 Microsoft 威脅防護並指派 it 許可權，請在應用程式頁面上，選取 [ **API 許可權**  >  **新增許可權**  >  **APIs 我的組織使用**>]，輸入 [ **microsoft 威脅防護**]，然後選取 [ **microsoft 威脅防護**]。

    >[!NOTE]
    > Microsoft 威脅防護不會出現在原始清單中。 您必須先在文字方塊中寫入其名稱，才能看到顯示的名稱。

      ![API 存取和 API 選取的影像](../../media/apis-in-my-org-tab.PNG)

    - 選擇 [ **委派的許可權** ] > 選擇您案例的相關許可權，例如 Incident、 **Read**，然後選取 [ **新增許可權**]。

      ![API 存取和 API 選取的影像](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     >您必須選取相關的許可權。 

    -  若要決定您需要的許可權，請參閱您想要呼叫之 API 中的 [ **許可權** ] 區段。

    - 按一下 **[授與同意**]

      >[!NOTE]
      >每次您新增許可權時，您必須按一下 **[授與同意** 才能讓新的許可權生效。

      ![授與許可權的影像](../../media/grant-consent-delegated.PNG)

6. 記下來記錄應用程式識別碼和您的租使用者 ID:

   - 在 [應用程式] 頁面上，移至 **[簡介** ]，然後複製下列專案：

   ![建立之應用程式識別碼的影像](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a>使用 PowerShell 取得存取權杖

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a>相關主題
- [存取 Microsoft 威脅防護 APIs](api-access.md)
- [使用應用程式內容存取 Microsoft 威脅防護](api-create-app-web.md)
