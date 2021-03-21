---
title: 跨租用戶信箱移轉
description: 如何在 Microsoft 365 或 Office 365 承租人之間移動信箱。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 7c3b4f82d94888cfa6c63b25f20130a38f8b4c9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919197"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>跨承租人信箱遷移 (預覽) 

先前，當 Exchange Online 承租人需要將信箱移至相同 Exchange Online 服務中的其他租使用者時，他們必須將其完全下架至內部部署，然後再將其上架至新的租使用者。 使用新的跨租使用者信箱遷移功能，來源和目標承租人中的租使用者管理員可以在租使用者內部部署系統中的基礎結構相依性之間移動信箱。 這樣就不再需要離線和上架信箱。

通常，在合併或 divestitures 期間，您必須能夠將使用者和內容移至新的承租人。 當目標租使用者管理員執行移動時，它稱為「拉入移動」，類似于雲端上架遷移的內部部署。

租使用者 Exchange 信箱移動可由租使用者系統管理員完全自行服務，其使用的已知介面，可以編寫成將使用者轉換為新組織所需的較大型工作流程。 系統管理員可以使用「 `New-MigrationBatch` 移動信箱」管理角色提供的指令程式，以執行跨承租人移動。 移動程式會在信箱同步處理和完成期間包含租使用者授權檢查。 
 
遷移的使用者必須在目標租使用者 Exchange Online 系統中呈現為 MailUsers，並以特定屬性標示，以啟用跨承租人的移動。 系統會針對未在目標租使用者中正確設定的使用者，移動系統會失敗。  

移動完成後，來源系統信箱會轉換成 MailUser，而且會將 Exchange) 中 ExternalEmailAddress 所顯示的 targetAddress (視為目的地租使用者的路由位址。 此程式會將 MailUser 舊版租使用者保留在來源租使用者中，並允許一段同時存在和郵件路由的情況。 當商務程式允許時，來源租使用者可能會移除來源 MailUser 或將其轉換為郵件連絡人。 

只有混合或雲端中的承租人或兩者的任何組合，才支援跨承租人 Exchange 信箱遷移。

本文說明跨承租人信箱移動的程式，並提供如何準備內容移動的來源和目標承租人的指導方針。  

## <a name="preparing-source-and-target-tenants"></a>準備來源和目標承租人

跨承租人 Exchange 信箱遷移功能需要授權和範圍進行跨承租人遷移。 租使用者使用 Azure Enterprise application 和 Key Vault 儲存解決方案，現在可管理 Exchange Online 信箱從一個承租人遷移至另一個承租人的授權和範圍。 跨承租人信箱移動支援邀請與同意模型，以建立 Azure Active Directory (Azure AD) 應用程式，以供租使用者對間的驗證使用。 也需要其他元件（例如，組織關聯性和遷移端點）。

本節不包含準備目標目錄中 MailUser 使用者物件所需的特定步驟，也不會包含用於提交遷移批次的範例命令。 請參閱 [準備目標使用者物件以供遷移](#prepare-target-user-objects-for-migration) 以取得此資訊。

## <a name="prerequisites"></a>必要條件

跨承租人信箱移動功能需要 [Azure Key Vault](/azure/key-vault/basic-concepts) 才能建立租使用者對特定的 Azure 應用程式，以安全地儲存和存取憑證/機密，以供從一個租使用者對另一個租使用者進行驗證及授權，並移除在承租人間共用憑證/機密的任何需求。 

開始之前，請確定您具備執行部署腳本所需的許可權，才能設定 Azure Key Vault、移動信箱應用程式、EXO 遷移端點，以及 EXO 組織關聯性。 通常，全域管理員具有執行所有設定步驟的許可權。

此外，在執行安裝程式之前，必須先在來源租使用者中啟用郵件功能的安全性群組。 這些群組是用來限定可從來源移動的信箱清單，或有時稱為「資源) 租使用者 (目標租使用者。 這可讓來源租使用者管理員限制或限制需要移動的特定信箱集，以防非預期的使用者進行遷移。 不支援嵌套的群組。

您也需要與您信任的協力廠商公司 (進行通訊，以供您將信箱移動) 取得其 Microsoft 365 租使用者識別碼。 在 [組織關聯] 欄位中使用此租使用者識別碼 `DomainName` 。

若要取得訂閱的租使用者識別碼，請登入 Microsoft 365 系統管理中心，然後移至 [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 。 按一下 [租使用者識別碼] 屬性的複製圖示，將其複製到剪貼簿。

以下是處理常式的運作方式。

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="信箱遷移的租使用者準備。":::

[請參閱較大版本的此影像](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)。

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>準備承租人

在高層次上執行安裝程式腳本時，會進行下列設定動作。

準備目標租使用者：

1. 若未提供現有的 Azure 資源群組，則會在 (SCRIPT) 中建立一個新的 Azure 資源群組。
2. 若未提供現有的 Key Vault， (腳本) 中建立新的按鍵 Vault。
3. 為 Office 365 Exchange Online 信箱遷移應用程式建立新的訪問原則 (腳本) 。
4. 如果指定) 將機密保存到遷移應用程式 (腳本) ，就會建立新的憑證 (或現有憑證。
5.  (SCRIPT) 中建立新的 Azure AD 應用程式。
6. 憑證/機密會上傳至遷移應用程式 (SCRIPT) 。
7. 信箱遷移許可權會指派給應用程式 (SCRIPT) 。
8. 部署腳本會暫停，直到 target admin consents 至自己的應用程式 (SCRIPT) 。
9. 目標承租人系統管理員 consents 指定給應用程式 (手動) 的許可權。
10. 組織關聯建立到目標租使用者 (SCRIPT) 。
11. 會建立遷移端點，將信箱拉入目標租使用者 (SCRIPT) 。

準備來源租使用者：

1. 來源租使用者管理員接受來自目標租使用者 (手動) 的信箱遷移應用程式邀請。
2. 來源租使用者系統管理員會在其承租人中建立擁有郵件功能的安全性群組，以包含允許遷移應用程式移動的信箱清單 (手動) 。
3. 組織關聯性建立于目標承租人，指定信箱遷移應用程式應該用於 OAuth 驗證，以接受 (腳本) 的移動要求。

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>目標承租人管理員的逐步指示

1. 從 [GitHub 存放庫](https://github.com/microsoft/cross-tenant/releases/tag/Preview)下載目標租使用者安裝程式的 SetupCrossTenantRelationshipForTargetTenant.ps1 腳本。 
2. 將腳本 (SetupCrossTenantRelationshipForTargetTenant.ps1) 儲存至您要執行腳本的電腦。
3. 建立與 Exchange Online 目標租使用者的遠端 PowerShell 連線。 此外，請務必具備執行部署腳本所需的許可權，才能設定 Azure 金鑰 Vault 儲存和憑證、移動信箱應用程式、EXO 遷移端點，以及 EXO 組織關聯性。
4. 將檔資料夾目錄變更為腳本位置，或確認腳本目前已儲存至遠端 PowerShell 會話中的目前位置。
5. 使用下列參數和值執行腳本。

    | 參數 | 值 | 必要或選用
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | 目標租使用者網域，例如 fabrikam \. onmicrosoft.com。 | 必要 |
    | -ResourceTenantDomain                       | 來源租使用者網域，例如 contoso \. onmicrosoft.com。 | 必要 |
    | -ResourceTenantAdminEmail                   | 來源承租人管理員的電子郵件地址。 這是來源承租人系統管理員，會同意使用從目標系統管理員傳送的信箱遷移應用程式。這是將會收到該應用程式之電子郵件邀請的系統管理員。 | 必要 |
    | -ResourceTenantId                           | 來源承租人組織識別碼 (GUID) 。 | 必要 |
    | -SubscriptionId                             | 用於建立資源的 Azure 訂閱。 | 必要 |
    | -ResourceGroup                              | 包含或將要包含金鑰存放區之 Azure 資源組名稱。 | 必要 |
    | -KeyVaultName                               | Azure Key Vault 實例，用來儲存您的信箱遷移應用程式憑證/機密。 | 必要 |
    | -CertificateName                            | 在金鑰保管中產生或搜尋憑證時的憑證名稱。 | 必要 |
    | -CertificateSubject                         | Azure 金鑰保存庫憑證主體名稱，例如 CN = contoso_fabrikam。 | 必要 |
    | -ExistingApplicationId                      | 若已建立郵件遷移應用程式，則使用該應用程式。 | 選用 |
    | -AzureAppPermissions                        | 指定給信箱遷移應用程式所需的許可權，例如 Exchange 或 Msgraph-sdk-ios-nxoauth2-adapter (Exchange 以移動信箱，Msgraph-sdk-ios-nxoauth2-adapter 用於使用此應用程式，將同意連結邀請傳送至資源租使用者) 。 | 必要 |
    | -UseAppAndCertGeneratedForSendingInvitation | 使用為遷移所建立的應用程式來傳送對來源承租人系統管理員的「同意」連結邀請的參數。如果不存在，將會提示目標管理員的認證連線至 Azure 邀請管理員，並以目標系統管理員身分傳送邀請。 | 選用 |
    | -KeyVaultAuditStorageAccountName            | 儲存主要存放區之審核記錄的儲存體帳戶。 | 選用 |
    | -KeyVaultAuditStorageResourceGroup          | 包含儲存金鑰 Vault 審核記錄的儲存帳戶的資源群組。 | 選用 |
    ||||

    >[!Note]
    > 在執行腳本之前，請確定您已安裝 Azure AD PowerShell 模組。 如需安裝步驟，請參閱 ![ 此處 ](/powershell/azure/install-az-ps?view=azps-5.1.0) 。

6. 腳本會暫停，並要求您接受或同意在此程式期間建立的 Exchange 信箱遷移應用程式。 範例如下。

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. 會在遠端 PowerShell 會話中顯示 URL。 複製為您的租使用者同意所提供的連結，並將其貼到網頁瀏覽器中。

8. 使用您的全域系統管理員認證登入。 當顯示下列畫面時，請選取 [ **接受**]。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="[接受許可權] 對話方塊":::

9. 切換回遠端 PowerShell 會話，然後按 Enter 繼續。

10. 腳本會設定其餘的安裝物件。 範例如下。

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

目標系統管理員設定現在已完成！

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>來源承租人管理員的逐步指示

1.  在設定期間，以目標系統管理員所指定的-ResourceTenantAdminEmail 登入您的信箱。 尋找來自目標租使用者的電子郵件邀請，然後選取 [ **快速入門** ] 按鈕。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="[您已被邀請] 對話方塊":::

2. 選取 [ **接受** ] 以接受邀請。

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="接受許可權的對話方塊":::

   > [!NOTE]
   > 如果您未收到這封電子郵件或找不到，則目標租使用者管理員會提供直接 URL，可供您用來接受邀請。 URL 應在目標租使用者 admin 的遠端 PowerShell 會話的成績單中。

3. 在 Microsoft 365 系統管理中心或遠端 PowerShell 會話中，建立一或多個擁有郵件功能的安全性群組，以控制目標租使用者所允許的信箱清單，以拉 (從來源租使用者) 移至目標租使用者。 您不需要事先填入此群組，但必須至少提供一個群組，才能執行安裝步驟 (script) 。 不支援嵌套群組。 

4. 從 GitHub 存放庫在以下位置下載來源承租人安裝程式的 SetupCrossTenantRelationshipForResourceTenant.ps1 腳本： [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 。 

5. 使用您的 Exchange 系統管理員許可權，建立與來源承租人的遠端 PowerShell 連線。 若要設定來源租使用者，則不需要全域系統管理員許可權，因為 Azure 應用程式的建立程式是由目標租使用者所組成。

6. 將目錄變更為腳本位置，或確認腳本目前已儲存至遠端 PowerShell 會話中的目前位置。

7. 使用下列必要的參數和值，執行腳本。

    | 參數 | 值 |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | 來源租使用者為屬於遷移範圍內之身分識別/信箱所建立的已啟用郵件功能的安全性群組。 |
    | -ResourceTenantDomain | 來源租使用者功能變數名稱，例如 contoso \. onmicrosoft.com。 |
    | -ApplicationId | 用於遷移之應用程式的 Azure 應用程式識別碼 (GUID) 。 可透過 Azure 入口網站取得的應用程式識別碼 (Azure AD、企業應用程式、應用程式名稱、應用程式識別碼) 或包含在您的邀請電子郵件中。  |
    | -TargetTenantDomain | 目標租使用者功能變數名稱，例如 fabrikam \. onmicrosoft.com。 |
    | -TargetTenantId | 目標租使用者的租使用者識別碼。 例如，contoso onmicrosoft.com 租使用者的 Azure AD 租使用者識別碼 \. 。 |
    |||

    範例如下。
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

來源系統管理員設定現在已完成！

### <a name="verify-setup"></a>驗證安裝程式

請確認已成功建立目標中的來源與目標承租人及遷移端點中的組織關聯性。

#### <a name="target-tenant"></a>目標租使用者

**組織關聯性**

使用此命令，確認已建立及設定組織關聯性物件。

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
範例如下：

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**遷移端點**

使用此命令，確認已建立並設定遷移端點物件。

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

範例如下。

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>來源租使用者

**組織關聯性**

使用此命令，確認已建立及設定組織關聯性物件。

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

範例如下。

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a>驗證安裝程式腳本

如果您在設定來源或目標承租人期間收到任何錯誤，您可以執行位於 [GitHub 上](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 的 VerifySetup.ps1 腳本，並複查輸出。

以下是在目標租使用者上執行 VerifySetup.ps1 的範例：

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

以下是來源承租人上 VerifySetup.ps1 的範例：

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>將信箱移回原始來源

若要將信箱移回原始來源租使用者，必須在新的來源和新的目標承租人中執行相同的一組步驟和腳本。 將會更新或新增現有的組織關聯性物件，而不會重新建立。

## <a name="prepare-target-user-objects-for-migration"></a>為遷移準備目標使用者物件

遷移的使用者必須存在於目標承租人和 Exchange Online 系統 (中，MailUsers) 會以特定屬性標示以啟用跨承租人的移動）。 系統會針對未在目標租使用者中正確設定的使用者，移動系統會失敗。 下列各節將詳細說明目標租使用者的 MailUser 物件需求。

### <a name="prerequisites"></a>必要條件
  
您必須確定在目標群組織中設定下列物件和屬性。  

1. 對於從來源組織移動的任何信箱，您必須在目標群組織中布建 MailUser 物件： 

   - 目標 MailUser 必須具有來自來源信箱的這些屬性，或是使用新的 User 物件進行指派：
      - ExchangeGUID (從源到目標) 的直接流程–信箱 GUID 必須相符。 若目標物件不存在，移動程式將不會繼續進行。 
      - ArchiveGUID 從來源到目標)  (直接流程–封存 GUID 必須相符。 若目標物件不存在，移動程式將不會繼續進行。  (只有當來源信箱啟用封存) 時，才需要此。 
      - LegacyExchangeDN (流向 proxyAddress，"x500： <LegacyExchangeDN> " ) – LegacyExchangeDN 必須存在於目標 MailUser 為 x500： proxyAddress。 若目標物件不存在，移動程式將不會繼續進行。 
      - UserPrincipalName – UPN 會對應至使用者的新身分識別或目標公司 (例如，user@northwindtraders.onmicrosoft.com) 。 
      - 主要 SMTPAddress –主要 SMTP 位址會對應至使用者的新公司 (例如，user@northwind.com) 。 
      - TargetAddress/ExternalEmailAddress – MailUser 會參考來源承租人中主控的使用者目前信箱 (例如 user@contoso.onmicrosoft.com) 。 指派此值時，請確認您具有/也指派 PrimarySMTPAddress，否則此值會設定 PrimarySMTPAddress 會造成移動失敗。 
      - 您無法從來源信箱將舊版 smtp proxy 位址新增至目標 MailUser。 例如，您無法在 fabrikam.onmicrosoft.com 租使用者物件) 中的 MEU 上維護 contoso.com。 網域只與一個 Azure AD 或 Exchange Online 租使用者相關聯。
 
     範例 **目標** MailUser 物件：
 
     | 屬性             | 值                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | 別名                 | LaraN                                                                                                                    |
     | RecipientType         | MailUser                                                                                                                 |
     | RecipientTypeDetails  | MailUser                                                                                                                 |
     | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
     | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
     | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
     | LegacyExchangeDN      | /o = First Organization/ou=Exchange 系統管理群組                                                                   |
     |                       |  (FYDIBOHF23SPDLT) /cn = 收件者/cn = 74e5385fce4b46d19006876949855035Lara                                                  |
     | EmailAddresses        | x500：/o = First Organization/ou=Exchange 系統管理群組 (FYDIBOHF23SPDLT) /cn = 收件者/cn = d11ec1a2cacd4f81858c8190  |
     |                       | 7273f1f9-Lara                                                                                                            |
     |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
     |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
     |||

     **來源** 信箱物件範例：

     | 屬性             | 值                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | 別名                 | LaraN                                                                    |
     | RecipientType         | UserMailbox                                                              |
     | RecipientTypeDetails  | UserMailbox                                                              |
     | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
     | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
     | LegacyExchangeDN      | /o = First Organization/ou=Exchange 系統管理群組                   |
     |                       |  (FYDIBOHF23SPDLT) /cn = 收件者/cn = d11ec1a2cacd4f81858c81907273f1f9Lara  |
     | EmailAddresses        | smtp:LaraN@contoso.onmicrosoft.com 
     |                       | SMTP:Lara.Newton@contoso.com          |
     |||

   - 其他屬性可能會包含在 Exchange 混合式寫回中。 如果不是，則應該包含這些使用者。 
   - msExchBlockedSendersHash –從用戶端向內部部署 Active Directory 中寫入線上安全及封鎖的寄件者資料。
   - msExchSafeRecipientsHash –從用戶端向內部部署 Active Directory 中寫入線上安全及封鎖的寄件者資料。
   - msExchSafeSendersHash –從用戶端向內部部署 Active Directory 中寫入線上安全及封鎖的寄件者資料。

2. 如果來源信箱位於 LitigationHold，且來源信箱可復原的專案大小大於我們的資料庫預設值 (30 GB) 中，因為目標配額小於來源信箱大小，所以移動不會繼續進行。 您可以更新 target MailUser 物件，將 ELC 信箱旗標從來源環境轉換到目標，這會觸發目標系統將 MailUser 的配額擴充為 100 GB，因此可讓使用者移至目標。 這些指示僅適用于執行 Azure AD Connect 的混合式身分識別，因為用於加蓋 ELC 旗標的命令不會公開給租使用者系統管理員。

    >[!Note]
    > 範例–無擔保<br/>此腳本會假設同時連線到來源信箱 (以取得來源值) 以及目標內部部署 Active Directory (，以標記 Microsoft.rtc.management.adconnect.schema.aduser 物件) 。 如果來源已啟用訴訟或單一專案復原，請在目的地帳戶上加以設定。  這會將目的地帳戶的暫放大小增加為 100 GB。

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. 非混合式目標租使用者可以在遷移之前，修改 MailUsers 的 [可復原的專案] 資料夾中的配額，方法是執行下列命令，以啟用 MailUser 物件的訴訟暫止，並將配額增加至 100 GB： `Set-MailUser -EnableLitigationHoldForMigration $TRUE` 。 附注：這不適用於混合中的承租人。

4. 目標群組織中的使用者必須具備適用于組織的適當 Exchange Online 訂閱的授權。 您可以在信箱移動之前套用授權，但只有在使用 ExchangeGUID 和 proxy 位址正確設定目標 MailUser 之後。 在套用 ExchangeGUID 之前套用授權，將會導致目標群組織中布建新的信箱。 

    > [!Note]
    > 當您在信箱或 MailUser 物件上套用授權時，會清理所有 SMTP 類型 proxyAddresses，以確保 Exchange EmailAddresses 陣列中只包含已驗證的網域。 

5. 您必須確定目標 MailUser 沒有與來源 ExchangeGuid 不符的先前 ExchangeGuid。 如果目標 MEU 先前已授權 Exchange Online 並已布建信箱，可能會發生這種情況。 若目標 MailUser 先前授權或具有與來源 ExchangeGuid 不符的 ExchangeGuid，您必須執行雲端 MEU 的清除。 針對這些雲端 Meu，您可以執行 `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` 。  

    > [!Caution]
    > 此程式不可逆。 如果物件有 softDeleted 信箱，就無法在此點之後還原。 不過，您可以將正確的 ExchangeGuid 與目標物件進行同步處理，MRS 會將來源信箱連線到新建立的目標信箱。  (在新參數上參照 EHLO 博客。 )   

    尋找先前使用此命令的信箱的物件。

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    範例如下。 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    使用此命令清除虛刪除的信箱。

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    範例如下。

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a>執行信箱遷移

跨承租人 Exchange 信箱的遷移會當作從目標租使用者起始的遷移批次提交。 這一點類似于從 Exchange 內部部署遷移至 Microsoft 365 時，使用中的遷移批次的運作方式。 

### <a name="create-migration-batches"></a>建立遷移批次

以下是開始 off 移動的範例遷移批次 Cmdlet。

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> CSV 檔案中的電子郵件地址必須是目標租使用者中所指定的位址，而非來源承租人。

選取 [跨承租人使用者] 選項時，也支援從新的 Exchange 系統管理中心進行遷移批次提交。

#### <a name="update-on-premises-mailusers"></a>更新內部部署 MailUsers

當信箱從來源移至目標之後，您應該確定內部部署郵件使用者（包括來源和目標）已更新為新的 targetAddress。 在此範例中，移動中使用的 targetDeliveryDomain 是 **contoso.onmicrosoft.com**。 使用此 targetAddress 更新郵件使用者。

## <a name="frequently-asked-questions"></a>常見問題集

**在移動之後，我們是否需要更新來源內部部署的 RemoteMailboxes？**

是的，您應該在來源租使用者信箱移至目標租使用者時，更新來源內部部署使用者的 targetAddress (RemoteRoutingAddress/ExternalEmailAddress) 。  雖然郵件路由可以追蹤多個具有不同 targetAddresses 之郵件使用者的參考，但 Free/Busy 郵件使用者的查閱，都必須以信箱使用者的位置為目標。 Free/Busy 查閱將不會跟蹤多個重新導向。 

**小組聊天資料夾內容是否要遷移跨承租人？**  

否，小組聊天資料夾內容不會遷移跨承租人。  

**如何看到跨承租人移動的移動，不是我的上架和離架移動？**

使用 `-flags` 參數。 範例如下。

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**您可以提供範例腳本，以用於複製測試中所用的屬性嗎？**

> [!Note]
> 範例–無擔保<br/>此腳本會假設同時連線到來源信箱 (以取得來源值) 以及目標內部部署 Active Directory 網域服務 (，以標記 Microsoft.rtc.management.adconnect.schema.aduser 物件) 。 如果來源已啟用訴訟或單一專案復原，請在目的地帳戶上加以設定。  這會將目的地帳戶的暫放大小增加為 100 GB。

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
**移動信箱之後，如何在第1天存取 Outlook？**

由於只有一個租使用者可以擁有網域，所以當信箱移動完成時，先前的主要 SMTPAddress 將不會與目標租使用者中的使用者產生關聯。僅限與新租使用者相關聯的網域。 Outlook 會使用使用者新的 UPN 向服務進行驗證，而 Outlook 設定檔預期會尋找舊版主要 SMTPAddress，以符合目標系統中的信箱。 因為舊版位址不在目標系統中，所以 outlook 設定檔不會連線以尋找新移動的信箱。 

在此初始部署中，使用者將需要以其新的 UPN、主要 SMTP 位址和重新同步處理 OST 內容來重新建立其設定檔。 

> [!Note]
> 當您批次使用者完成時，會據以進行規劃。 在建立 Outlook 用戶端設定檔，並將後續 OST 和 OAB 檔案下載至用戶端時，您需要考慮網路使用方式和容量。 
 
**我需要擁有哪些 Exchange RBAC 角色，才能設定或完成跨租使用者移動？**
 
根據在執行信箱移動時，假設委派的職責，會有一個角色矩陣。 目前需要兩個角色：  

- 第一個角色是針對執行將內容移入或移出承租人/組織界限的一次性設定工作。 當您將資料移出組織控制項時，對所有公司而言是一個重要的考慮，我們會選擇為組織管理員 (OrgAdmin) 中的最高指派角色。 此角色必須變更或設定定義遠端組織的-MailboxMoveCapability 的新 New-organizationrelationship。 只有 OrgAdmin 可以變更 MailboxMoveCapability 設定，而 OrganizationRelationhip 的其他屬性可由同盟共用系統管理員管理。 
 
- 執行實際 move 命令的角色可委派給較低層級的功能。 移動信箱的角色會指派使用參數將信箱移入或移出組織的功能 `-RemoteTenant` 。  

**我們要如何瞄準已轉換的信箱 (上為 targetAddress (所選取的 SMTP 位址 TargetDeliveryDomain) MailUser 轉換) ？**
 
Exchange 信箱使用 MRS 手工 MailUser 建立原始來源信箱上的 targetAddress 時，會將電子郵件地址與目標物件上的電子郵件地址 (proxyAddress) 相符。 程式會使用傳入移動命令中的-TargetDeliveryDomain 值，然後在目標端檢查該網域的相符 proxy。 當我們找到相符的 proxyAddress 時，會使用對應的設定已轉換信箱上的 ExternalEmailAddress (targetAddress)  (現在 MailUser) 物件。
 
**信箱許可權如何轉換？**

信箱許可權包括「代理傳送者」和「信箱存取」： 

- 「代理傳送者」 (AD： publicDelegates) 儲存收件者的 DN，以存取使用者的信箱做為代理人。 此值儲存在 Active Directory 中，而且目前不會移動做為信箱轉換的一部分。 如果來源信箱已設定 publicDelegates，您必須在目標信箱上 restamp publicDelegates，只要在目標環境中執行 MEU 至信箱轉換，便會執行 `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` 。 
 
- 當主體和代理人都移至目標系統時，信箱中儲存的信箱許可權會隨著信箱一起移動。 例如，使用者 TestUser_7 會被授與租使用者 SourceCompany.onmicrosoft.com 中的信箱 TestUser_8 FullAccess。 信箱移動完成 TargetCompany.onmicrosoft.com 後，就會在目標目錄中設定相同的許可權。 在來源與目標承租人中使用 *Get-MailboxPermission* TestUser_7 的範例如下所示。 Exchange Cmdlet 會據此為來源和目標加上首碼。 
 
以下是移動之前信箱許可權的輸出範例。 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
以下是移動後的信箱許可權輸出範例。 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> 不支援跨租使用者信箱和行事曆許可權。 您必須將主體和代理人組織成合併的移動批次，以便從來源租使用者同時從來源租使用者中轉換這些連線的信箱。 

**哪些 X500 proxy 應該新增至目標 MailUser proxy 位址以啟用遷移？**  

跨承租人信箱遷移要求在目標 MailUser 物件上，將來源信箱物件的 LegacyExchangeDN 值加蓋為 x500 電子郵件地址。  

範例：  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> 除了此 X500 proxy 之外，您還需要將來源信箱中的所有 X500 proxy，複製到目標中的信箱。  

**移動無法運作時，應從何處開始疑難排解？**  

先執行位於 [GitHub 上](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 的 VerifySetup.ps1 腳本，並複查輸出。

以下是在目標租使用者上執行 VerifySetup.ps1 的範例：

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

以下是在來源租使用者上執行 VerifySetup.ps1 的 eExample：

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**來源和目標租使用者是否可以使用相同功能變數名稱？**  

否。 來源和目標租使用者功能變數名稱必須是唯一的。 例如，contoso.com 的來源網域和 fourthcoffee.com 的目標網域。

**共用信箱會移動而且仍然可以運作嗎？**

是的，不過我們只會保留這些文章中所述的存放區許可權：

- [Microsoft 檔 |在 Exchange Online 中管理收件者的許可權](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Microsoft 支援 |如何在 Office 365 專屬中授與 Exchange 和 Outlook 信箱許可權](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**是否需要 Azure 金鑰 Vault，以及何時進行交易？**  

是的，若要使用金鑰保存庫來儲存憑證以授權遷移，必須有 Azure 訂閱。 與使用 username & 密碼驗證來源的上架遷移不同，跨租使用者信箱遷移使用 OAuth 和此憑證做為密碼。 存取機碼 Vault 必須維護于所有的信箱遷移，只要一開始和一次結束遷移，而且在增量同步處理期間，每24小時就會發生一次。 您可以在 [這裡]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)查看 AKV 成本的詳細資料。  

**您是否有批次的建議？**  

每批次請勿超過2000個信箱。 強烈建議在削減之前的兩周內提交批次，因為同步處理時不會對使用者造成影響。如果您需要的信箱數量超過50000的指導方針，您可以在 crosstenantmigrationpreview@service.microsoft.com 中找到工程的意見反應通訊群組清單。

**若要使用客戶金鑰進行服務加密，該怎麼辦？**

移動之前將會解密信箱。 若仍需要，請確定已在目標租使用者中設定客戶金鑰。 如需詳細資訊，請參閱 [此處](../compliance/customer-key-overview.md) 。  

**預計的遷移時間為何？**

為了協助您規劃遷移， [此處](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) 所顯示的表格會顯示何時應大量進行大量信箱遷移或個別遷移的指導方針。 這些評估是以先前客戶遷移的資料分析為基礎。 因為每個環境都是唯一的，所以您的實際遷移速度可能會不同。  

請記住，這項功能目前正在預覽中，而且 SLA 和任何適用的服務層級不會在此功能的預覽狀態時，套用至任何效能或可用性問題。

## <a name="known-issues"></a>已知問題  

-  **問題：無法遷移自動擴充的封存。** 跨承租人遷移功能支援特定使用者的主要信箱和封存信箱的遷移。 如果來源中的使用者具有自動擴充的封存功能（表示有一個以上的封存信箱），該功能就無法遷移其他的封存，因此應該會失敗。

- **問題：具有非擁有的 smtp proxyAddress block MRS 的雲端 MailUsers 會移動背景。** 建立目標租使用者 MailUser 物件時，您必須確定所有 SMTP proxy 位址都屬於目標租使用者組織。 如果 SMTP proxyAddress 存在於不屬於本機租使用者的目標郵件使用者上，則會禁止 MailUser 至信箱的轉換。 這是因為我們保證信箱物件只會從租使用者授權的網域傳送郵件，而該網域是租使用者) 所宣告的 (網域： 

   - 當您從使用 Azure AD Connect 的內部部署同步處理使用者時，您可以在內部部署 MailUser 物件上，ExternalEmailAddress 指向信箱所在的來源承租人 (laran@contoso.onmicrosoft.com) ，並將 PrimarySMTPAddress 標記為位於目標租使用者 (Lara.Newton@northwind.com) 的網域。 這些值會向外同步處理至租使用者，並已布建適當的郵件使用者，可供遷移。 這裡會顯示範例物件。
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > *Contoso.onmicrosoft.com* 位址 *不存在於* EmailAddresses/proxyAddresses 陣列中。

- **問題：將「外部」主要 SMTP 位址的 MailUser 物件修改/重設為「內部」公司所宣告的網域**

   MailUser 物件是指向非本機信箱的指標。 在跨租使用者信箱遷移的情況下，我們會使用 MailUser 物件，代表從目標群組織的觀點) 或目標信箱 (來源組織的觀點) 中的來源信箱 (。 MailUsers 將會有 ExternalEmailAddress (targetAddress) ，指向實際信箱 (ProxyTest@fabrikam.onmicrosoft.com) 的 smtp 位址，以及代表目錄中信箱使用者顯示的 SMTP 位址的 primarySMTP 位址。 有些組織會選擇將主要 SMTP 位址顯示為外部的 SMTP 位址，而不是本機租使用者所擁有/驗證的位址 (例如 fabrikam.com，而非 contoso.com) 。  不過，將 Exchange 服務計畫物件套用至 MailUser 透過授權作業之後，主要 SMTP 位址會修改成顯示為由本機組織 (contoso.com) 驗證的網域。 有兩個可能的原因：
   
   - 將任何 Exchange 服務計畫套用至 MailUser 時，Azure AD 程式都會開始強制執行 proxy 清理，以確保本機組織無法從其他租使用者傳送郵件、哄騙或郵件。 如果本機組織未驗證位址，將會移除具有這些服務方案之收件者物件上的任何 SMTP 位址。 就像範例中的情況，contoso.onmicrosoft.com 租使用者不會驗證 Fabikam.com 網域，因此清理會移除該 fabrikam.com 網域。 如果您想要在遷移或遷移之後的 MailUser 上保留這些外部網域，您必須在移動完成後或移動之前，變更遷移程式，以去除授權，以確保使用者已套用預期的外部品牌。 您必須確定信箱物件已正確授權，否則不會影響郵件服務。<br/><br/>若要在 Contoso.onmicrosoft.com 租使用者的 MailUser 中移除服務方案的範例腳本，如下所示。

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       ServicePlans 所指派的結果集如下所示。

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       使用者的 PrimarySMTPAddress 不再被清理。 Fabrikam.com 網域不是由 contoso.onmicrosoft.com 租使用者所擁有，將會以目錄中顯示的主要 SMTP 位址來保存。

       範例如下。

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - 當 msExchRemoteRecipientType 設定為 8 (DeprovisionMailbox) 時，針對遷移到目標租使用者的內部部署 MailUsers，Azure 中的 proxy 清理邏輯會移除 nonowned 網域，並將 primarySMTP 重設為擁有的網域。 清除內部部署 MailUser 中的 [msExchRemoteRecipientType]，便不再套用 proxy 清理邏輯。 <br/><br>以下是包括 Exchange Online 之一組可能的完整服務方案。

   | 姓名                                              |
   |---------------------------------------------------|
   | 高級 eDiscovery 儲存 (500GB)                |
   | 客戶加密箱                                  |
   | 資料外洩防護                              |
   | Exchange Enterprise CAL 服務 (EOP、DLP)        |
   | Exchange 基本版                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                               |
   | Exchange Online (計劃 1)                          |
   | Exchange Online (計劃 2)                          |
   | Exchange Online 適用的 Exchange Online 封存     |
   | Exchange Server 適用的 Exchange Online 封存     |
   | Exchange Online 非使用中使用者附加元件              |
   | Exchange Online Kiosk                             |
   | Exchange Online 多地理位置                         |
   | Exchange Online Plan 1                            |
   | Exchange Online POP                               |
   | Exchange Online Protection                        |
   | 資訊障礙                              |
   | Office 365 的資訊保護-精品   |
   | Office 365 的資訊保護-標準  |
   | 透過 MyAnalytics 的真知灼見                           |
   | Microsoft 365 高級審核                   |
   | Microsoft Bookings                                |
   | Microsoft 商務中心                         |
   | Microsoft MyAnalytics (完整)                       |
   | Office 365 進階電子文件探索                    |
   | Microsoft Defender for Office 365 (方案 1)     |
   | Microsoft Defender for Office 365 (方案 2)     |
   | Office 365 的特殊許可權存取管理           |
   | Office 365 中的高級加密                  |
