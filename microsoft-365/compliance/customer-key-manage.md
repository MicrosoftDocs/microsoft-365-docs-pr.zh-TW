---
title: 管理客戶金鑰
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 在您設定客戶金鑰之後，請瞭解如何透過還原 AKV 機碼來管理它，以及管理許可權，以及建立和指派資料加密原則。
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345055"
---
# <a name="manage-customer-key"></a>管理客戶金鑰

在您設定 Office 365 的客戶金鑰之後，您必須建立並指派一或多個資料加密原則 (DEP) 。 一旦您指派 DEPs，您就可以像本文所述的方式來管理您的金鑰。 深入瞭解相關主題中的客戶金鑰。

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>建立 DEP 以搭配所有租使用者的多個工作負載使用

開始之前，請先確定您已完成設定客戶所需的工作。 如需詳細資訊，請參閱 [設定客戶金鑰](customer-key-set-up.md)。 若要建立 DEP，您需要在安裝過程中取得的主要 Vault URIs。 如需詳細資訊，請參閱 [取得每個 Azure Key Vault 機碼的 URI](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。

若要建立多工作負載 DEP，請遵循下列步驟：
  
1. 在您的本機電腦上，使用組織中具有全域系統管理員或合規性系統管理員許可權的工作或學校帳戶，連接至 Windows PowerShell 視窗中的[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 。

2. 若要建立 DEP，請使用 New-M365DataAtRestEncryptionPolicy Cmdlet。

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   其中：

   - *PolicyName* 是您要用於原則的名稱。 名稱不能包含空格。 例如，Contoso_Global。

   - *KeyVaultURI1* 是原則中第一個索引鍵的 URI。 例如，<https://contosoWestUSvault1.vault.azure.net/keys/Key_01>。

   - *KeyVaultURI2* 是原則中的第二個索引鍵的 URI。 例如，<https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>。 以逗號和空格分隔兩個 URIs。

   - *原則描述* 是可協助您記起原則之原則的方便使用描述。 您可以在描述中包含空格。 例如，「承租人中所有使用者的多個工作負載的根原則」。

範例：

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>指派多工作負載原則

使用 Set-M365DataAtRestEncryptionPolicyAssignment Cmdlet 指派 DEP。 一旦您指派原則之後，Microsoft 365 會以 DEP 中識別的金鑰來加密資料。

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 其中 *PolicyName* 是原則的名稱。 例如，Contoso_Global。

範例：

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>建立與 Exchange Online 信箱搭配使用的 DEP

開始之前，請確定您已完成設定 Azure Key Vault 所需的工作。 如需詳細資訊，請參閱 [設定客戶金鑰](customer-key-set-up.md)。 使用 Windows PowerShell 以遠端方式連線至 Exchange Online，即可完成這些步驟。

DEP 與儲存在 Azure Key Vault 中的一組機碼相關聯。 您為 Microsoft 365 中的信箱指派 DEP。 Microsoft 365 會使用原則中識別的金鑰來加密信箱。 若要建立 DEP，您需要在安裝過程中取得的主要 Vault URIs。 如需詳細資訊，請參閱 [取得每個 Azure Key Vault 機碼的 URI](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。

記得！ 當您建立 DEP 時，您會在兩個不同的 Azure Key 保存庫中指定兩個金鑰。 在兩個不同的 Azure 區域中建立這些機碼，以確保異地冗余。

若要建立與信箱搭配使用的 DEP，請遵循下列步驟：
  
1. 在您的本機電腦上，使用組織內具有全域管理員或 Exchange Online 系統管理員許可權的工作或學校帳戶，在 Windows PowerShell 視窗中連線[至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 。

2. 若要建立 DEP，請輸入下列命令，以使用 New-DataEncryptionPolicy Cmdlet。

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   其中：

   - *PolicyName* 是您要用於原則的名稱。 名稱不能包含空格。 例如，USA_mailboxes。

   - *原則描述* 是可協助您記起原則之原則的方便使用描述。 您可以在描述中包含空格。 例如，「美國信箱的根鍵和其區域」。

   - *KeyVaultURI1* 是原則中第一個索引鍵的 URI。 例如，<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>。

   - *KeyVaultURI2* 是原則中的第二個索引鍵的 URI。 例如，<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>。 以逗號和空格分隔兩個 URIs。

   範例：
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

如需詳細的語法及參數資訊，請參閱 [DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy)。

### <a name="assign-a-dep-to-a-mailbox"></a>將 DEP 指派給信箱

使用 Set-Mailbox Cmdlet 將 DEP 指派給信箱。 一旦您指派原則之後，Microsoft 365 便可使用 DEP 中所識別的金鑰來加密信箱。
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中 *MailboxIdParameter* 指定使用者信箱。 如需 Set-Mailbox Cmdlet 的詳細資訊，請參閱 [Set-Mailbox](/powershell/module/exchange/set-mailbox)。

在混合式環境中，您可以將 DEP 指派給已同步處理至 Exchange Online 租使用者的內部部署信箱資料。 若要將 DEP 指派給此同步處理的信箱資料，您將使用 Set-MailUser Cmdlet。 如需混合式環境中信箱資料的詳細資訊，請參閱[使用 Outlook iOS 和 Android 搭配混合式新式驗證的內部部署信箱](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中 *MailUserIdParameter* 指定郵件使用者 (也稱為啟用郵件功能的使用者) 。 如需 Set-MailUser Cmdlet 的詳細資訊，請參閱 [Set-MailUser](/powershell/module/exchange/set-mailuser)。

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>建立與 SharePoint 線上、商務用 OneDrive 及 Teams 檔案搭配使用的 DEP

開始之前，請確定您已完成設定 Azure Key Vault 所需的工作。 如需詳細資訊，請參閱 [設定客戶金鑰](customer-key-set-up.md)。
  
若要設定 SharePoint 線上、商務用 OneDrive 和 Teams 檔案的客戶機碼，請透過遠端連線至 SharePoint 線上使用 Windows PowerShell，以完成這些步驟。
  
您可以將 DEP 與儲存在 Azure Key Vault 中的一組機碼產生關聯。 您將 DEP 套用到一個地理位置（也稱為地理位置）上的所有資料。 如果您使用 Office 365 的多地理位置功能，您可以為每個地理位置建立一個 DEP，使每個地理位置使用不同的金鑰。 如果您不是使用多地理位置，您可以在組織中建立一個 DEP，以用於 SharePoint 線上、商務用 OneDrive 及 Teams 檔案。 Microsoft 365 會使用 DEP 中識別的金鑰來加密該地理中的資料。 若要建立 DEP，您需要在安裝過程中取得的主要 Vault URIs。 如需詳細資訊，請參閱 [取得每個 Azure Key Vault 機碼的 URI](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。
  
記得！ 當您建立 DEP 時，您會在兩個不同的 Azure Key 保存庫中指定兩個金鑰。 在兩個不同的 Azure 區域中建立這些機碼，以確保異地冗余。
  
若要建立 DEP，您必須使用 Windows PowerShell 遠端連線至 SharePoint。
  
1. 在您的本機電腦上，使用組織中具有全域系統管理員許可權的公司或學校帳戶，[連線 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)。

2. 在 Microsoft Office SharePoint Online 管理命令介面中，執行 Register-SPODataEncryptionPolicy Cmdlet，如下所示：

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   範例：
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   當您註冊 DEP 時，加密會從 geo 中的資料開始。 加密可能需要一些時間。 如需使用此參數的詳細資訊，請參閱 [SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)。

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>查看您為 Exchange Online 信箱建立的 DEPs

若要查看您為信箱建立的所有 DEPs 清單，請使用 Get-DataEncryptionPolicy PowerShell Cmdlet。

1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，[連接至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 若要傳回組織中的所有 DEPs，請執行不含任何參數的 Get-DataEncryptionPolicy Cmdlet。

   ```powershell
   Get-DataEncryptionPolicy
   ```

   如需 Get-DataEncryptionPolicy Cmdlet 的詳細資訊，請參閱 [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy)。

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>將信箱遷移至雲端之前，請先指派 DEP

當您指派 dep 時，Microsoft 365 會在遷移期間使用指派的 DEP 來加密信箱的內容。 這種處理常式比遷移信箱、指派 DEP，然後等候進行加密更有效率，可能需要數小時或數天。

若要在將 DEP 遷移至 Office 365 之前將其指派給該信箱，請在 Exchange Online 中執行 Set-MailUser Cmdlet PowerShell:

1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，[連接至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 執行 Set-MailUser Cmdlet。

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   其中 *GeneralMailboxOrMailUserIdParameter* 指定信箱，且 *DataEncryptionPolicyIdParameter* 是 DEP 的識別碼。 如需 Set-MailUser Cmdlet 的詳細資訊，請參閱 [Set-MailUser](/powershell/module/exchange/set-mailuser)。

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>決定指派給信箱的 DEP

若要判斷指派給信箱的 DEP，請使用 Get-MailboxStatistics Cmdlet。 Cmdlet 會傳回唯一識別碼 (GUID) 。
  
1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，[連接至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   其中 *GeneralMailboxOrMailUserIdParameter* 指定信箱和 DataEncryptionPolicyID 會傳回 DEP 的 GUID。 如需 Get-MailboxStatistics Cmdlet 的詳細資訊，請參閱 [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics)。
  
2. 執行 Get-DataEncryptionPolicy Cmdlet，以找出信箱所指派的 DEP 好記名稱。
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   其中， *guid* 是上一個步驟中 Get-MailboxStatistics Cmdlet 所傳回的 guid。

## <a name="verify-that-customer-key-has-finished-encryption"></a>確認客戶金鑰已完成加密

不論您是否已滾出客戶金鑰、指派新的 DEP 或遷移的信箱，請使用本節中的步驟，以確保加密完成。

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>驗證 Exchange Online 信箱的加密是否已完成

加密信箱可能需要一些時間。 在第一次加密中，信箱也必須完全從一個資料庫移至另一個資料庫，此服務才能加密信箱。
  
使用 Get-MailboxStatistics Cmdlet 來判斷信箱是否已加密。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果信箱已加密，IsEncrypted 屬性會傳回 **true** 值，如果信箱未加密，則傳回 **false** 的值。 完成信箱移動的時間取決於第一次指派 DEP 的信箱數目，以及信箱的大小。 如果信箱在您指派 DEP 的時間之後，一星期內尚未加密，請與 Microsoft 聯繫。

無法再使用 New-MoveRequest Cmdlet 進行本機信箱移動。 如需詳細資訊，請參閱本次 [宣告](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 。

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>驗證 SharePoint 線上、商務用 OneDrive 及 Teams 檔案的加密是否已完成

執行 Get-SPODataEncryptionPolicy Cmdlet 以檢查加密的狀態，如下所示：

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

此 Cmdlet 的輸出包含：
  
- Primary key 的 URI。

- 輔助機碼的 URI。

- 地理位置的加密狀態。 可能的狀態包括：

  - 取消 **註冊：** 尚未套用客戶金鑰加密。

  - **註冊：** 已套用客戶金鑰加密，且您的檔案正處於加密過程中。 如果地理位置註冊，您也會顯示地理位置的網站百分比已完成的資訊，讓您可以監視加密進度。

  - **註冊：** 已套用客戶金鑰加密，且所有網站中的所有檔案都已加密。

  - **滾動：** 正在進行金鑰擲入。 如果地理位置的機碼正在進行滾動，您也會在網站的多少百分比上顯示完成金鑰滾動作業的資訊，讓您能夠監控進度。

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>取得與多個工作負載搭配使用的 DEPs 詳細資料

若要取得您已建立以用於多個工作負載之所有 DEPs 的詳細資料，請完成下列步驟：

1. 在您的本機電腦上，使用組織中具有全域系統管理員或合規性系統管理員許可權的工作或學校帳戶，連接至 Windows PowerShell 視窗中的[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 。

   - 若要傳回組織中所有多工作負荷 DEPs 的清單，請執行此命令。

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - 若要傳回特定 DEP 的詳細資料，請執行此命令。 此範例會傳回名為 "Contoso_Global" 之 DEP 的詳細資訊。

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>取得多工作負載 DEP 指派資訊

若要找出目前指派給租使用者的 DEP，請遵循下列步驟。 

1. 在您的本機電腦上，使用組織中具有全域系統管理員或合規性系統管理員許可權的工作或學校帳戶，連接至 Windows PowerShell 視窗中的[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 。

2. 輸入此命令。

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>停用多工作負載 DEP

在您停用多工作負載 DEP 之前，請從您租使用者中的工作負載取消指派 DEP。 若要停用用於多個工作負載的 DEP，請完成下列步驟：

1. 在您的本機電腦上，使用組織中具有全域系統管理員或合規性系統管理員許可權的工作或學校帳戶，連接至 Windows PowerShell 視窗中的[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 。

2. 執行 Set-M365DataAtRestEncryptionPolicy Cmdlet。
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

其中 *PolicyName* 是原則的名稱或唯一識別碼。 例如，Contoso_Global。

範例：

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a>還原 Azure 金鑰保存庫金鑰

執行還原之前，請使用 soft delete 所提供的復原功能。 所有與客戶金鑰搭配使用的金鑰，都必須啟用 [虛刪除]。 虛刪除的運作方式像是回收站，可在不需要還原的情況下，最多可恢復90天。 只需要在極大或不尋常的情況下進行還原，例如，金鑰或金鑰 vault 遺失。 如果您必須還原機碼以用於客戶機碼，請在 Azure PowerShell 中執行 Restore-AzureKeyVaultKey Cmdlet，如下所示：
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

例如：
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

若機碼 vault 已包含具有相同名稱的金鑰，還原作業就會失敗。 Restore-AzKeyVaultKey 會還原機碼的所有重要版本及所有中繼資料（包括金鑰名稱）。
  
## <a name="manage-key-vault-permissions"></a>管理主要 vault 許可權

有幾個 Cmdlet 可用，可讓您查看並視需要移除重要 vault 的許可權（如有必要）。 您可能需要移除許可權，例如，當員工離開團隊時。 針對上述每項工作，您將使用 Azure PowerShell。 如需 Azure PowerShell 的相關資訊，請參閱[Azure PowerShell 簡介](/powershell/azure/)。

若要查看主要 vault 許可權，請執行 Get-AzKeyVault Cmdlet。

```powershell
Get-AzKeyVault -VaultName <vault name>
```

例如：

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

若要移除系統管理員的許可權，請執行 Remove-AzKeyVaultAccessPolicy Cmdlet：
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

例如：

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>從客戶金鑰回復至 Microsoft 受管理的金鑰

如果您需要回復至 Microsoft 受管理的金鑰，您可以。 當您下架時，會使用每個個別工作負載支援的預設加密來重新加密您的資料。 例如，Exchange Online 支援使用 Microsoft 管理金鑰的預設加密。

> [!IMPORTANT]
> 脫離會與資料清除相同。 資料清除會永久加密-從 Microsoft 365 中刪除組織的資料，而脫離。 您無法執行多個工作負載原則的資料清除。

如果您決定不使用客戶金鑰指派多工作負載 DEPs，您就需要使用客戶金鑰組「下架」的要求與 Microsoft 支援聯繫。 要求支援小組將服務要求與 Microsoft 365 客戶重要小組一起歸檔。 如有任何問題，請移至 m365-ck@service.microsoft.com。

如果您不想要再使用信箱層級 DEPs 加密個別的信箱，您可以從所有信箱取消指派信箱等級 DEPs。

若要取消指派信箱 DEPs，請使用 Set-Mailbox PowerShell Cmdlet。

1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，[連接至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 執行 Set-Mailbox Cmdlet。

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

執行此 Cmdlet unassigns 目前指派的 DEP，並使用與預設 Microsoft 管理金鑰相關聯的 DEP 來 reencrypts 信箱。 您無法取消指派 Microsoft managed 機碼所用的 DEP。 如果您不想使用 Microsoft 受管理的金鑰，您可以將其他客戶金鑰 DEP 指派給信箱。

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>撤銷您的金鑰，並啟動資料清除路徑處理常式

您可以控制所有根機碼（包括可用性機碼）的吊銷。 客戶金鑰可讓您控制法規需求對您的結束規劃方面。 如果您決定撤銷您的金鑰以清除您的資料並退出服務，服務會在資料清除程式完成之後刪除可用性金鑰。 這對於指派給個別信箱的客戶機碼 DEPs 是支援的。

Microsoft 365 審核和驗證資料清除路徑。 如需詳細資訊，請參閱 [服務信任入口網站](https://servicetrust.microsoft.com/)上可用的 SSAE 18 SOC 2 報告。 此外，Microsoft 建議下列檔：

- [Microsoft Cloud 中金融機構的風險評估與規範指南](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 退出規劃考慮](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Microsoft 365 的客戶機碼不支援清除多工作負載 DEP。 多工作負載 DEP 是用來跨所有租使用者的多個工作負載來加密資料。 清除這類 DEP 會導致無法存取多個工作負載中的資料。 如果您決定完全退出 Microsoft 365 服務，您可以根據已記錄的程式來追蹤租使用者刪除的路徑。 請參閱 how [to delete a 租使用者 In Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto)。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>撤銷您的客戶金鑰和 Exchange Online 及商務用 Skype 的可用性金鑰

當您為 Exchange Online 和商務用 Skype 初始化資料清除路徑時，您會在 DEP 上設定永久的資料清除要求。 這樣做會永久刪除此 DEP 所指派的信箱中的加密資料。

因為您一次只能對一個 DEP 執行 PowerShell Cmdlet，請考慮在您啟動資料清除路徑之前，先將單一 DEP 重新指派給所有信箱。

> [!WARNING]
> 請勿使用資料清除路徑來刪除信箱的子集。 此程式僅適用于即將退出服務的客戶。

若要啟動資料清除路徑，請完成下列步驟：

1. 從 Azure Key 保存庫中移除 "O365 Exchange Online" 的自動換行和解包許可權。

2. 在您的組織中使用具有全域系統管理員許可權的工作或學校帳戶，[連接至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

3. 針對包含您要刪除之信箱的每個 DEP，執行 [DataEncryptionPolicy 指令程式](/powershell/module/exchange/set-dataencryptionpolicy) ，如下所示。

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   若命令失敗，請確定您已從 Azure Key Vault 的兩個金鑰中移除 Exchange Online 許可權（如本工作先前所指定）。當您使用 Set-DataEncryptionPolicy Cmdlet 設定 PermanentDataPurgeRequested 參數之後，就無法再將此 DEP 指派給信箱。

4. 請與 Microsoft 支援人員聯繫並要求資料清除 eDocument。

    在您提出要求時，Microsoft 會傳送您的法律檔，以確認和授權資料刪除。 在上架中，以 FastTrack 提供的核准者簽署的組織中的人員必須簽署此檔。 一般來說，這是公司中執行法律授權的人員或其他指定人員，可代表您的組織簽署書面。

5. 當您的代理人簽署法律檔時，通常會透過 eDoc 簽章) 將其退回 Microsoft (。

    Microsoft 收到法律檔之後，Microsoft 會執行 Cmdlet 以觸發資料清除，這會先刪除原則，並將信箱標記為永久刪除，然後刪除可用性金鑰。 資料清除程式完成後，就無法存取已清除的資料、無法存取 Exchange Online，且無法復原。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>撤銷您的客戶金鑰和 SharePoint 線上、商務用 OneDrive 及 Teams 檔案的可用性金鑰

若要啟動 SharePoint 線上、商務用 OneDrive 及 Teams 檔案的資料清除路徑，請完成下列步驟：

1. 撤銷 Azure 金鑰 Vault 存取權。 所有的主要 vault 管理員都必須同意撤銷存取權。

   您不會在 SharePoint Online 中刪除 Azure 金鑰 Vault。 主要保險共用可以在數個 SharePoint 線上承租人和 DEPs 之間共用。

2. 請與 Microsoft 聯繫以刪除可用性金鑰。

    當您與 Microsoft 聯繫以刪除可用性金鑰時，我們會傳送您的法律檔。 在上架中，以 FastTrack 提供的核准者簽署的組織中的人員必須簽署此檔。 一般來說，這是貴公司中的主管人員或其他指定人員，其法律上會有法律授權，代表您的組織簽署書面工作。

3. 當您的代理人簽署法律檔之後，通常會透過 eDoc 的簽章) ，將其退回 Microsoft (。

   一旦 Microsoft 收到法律檔，我們便會執行 Cmdlet，以觸發資料清除，該資料清除會執行租使用者金鑰、網站金鑰和所有個別檔金鑰的加密刪除，irrevocably 打破主要階層。 資料清除指令程式完成後，您的資料已清除。

## <a name="related-articles"></a>相關文章

- [客戶金鑰服務加密](customer-key-overview.md)

- [深入瞭解可用性金鑰](customer-key-availability-key-understand.md)

- [設定客戶金鑰](customer-key-set-up.md)

- [滾動或旋轉客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)

- [客戶加密箱](customer-lockbox-requests.md)

- [服務加密](office-365-service-encryption.md)