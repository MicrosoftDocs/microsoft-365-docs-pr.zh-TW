---
title: 管理客戶金鑰
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 在您設定客戶金鑰之後，請瞭解如何透過還原 AKV 機碼來管理它，以及管理許可權和您的資料加密原則。
ms.openlocfilehash: 284a8ff24fef2f7e8b807477c99e20aaf593552e
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394663"
---
# <a name="manage-customer-key"></a>管理客戶金鑰

在您設定 Office 365 的客戶金鑰之後，您可以依照本文所述管理您的金鑰。 深入瞭解相關主題中的客戶金鑰。

## <a name="restore-azure-key-vault-keys"></a>還原 Azure 金鑰保存庫金鑰

執行還原之前，請使用 soft delete 所提供的復原功能。 所有與客戶金鑰搭配使用的金鑰，都必須啟用 [虛刪除]。 虛刪除的運作方式像是回收站，可在不需要還原的情況下，最多可恢復90天。 只需要在極大或不尋常的情況下進行還原，例如，金鑰或金鑰 vault 遺失。 如果您必須還原金鑰以與客戶金鑰搭配使用，請在 Azure PowerShell 中執行 Restore-AzureKeyVaultKey Cmdlet，如下所示：
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

例如：
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

若機碼 vault 已包含具有相同名稱的金鑰，還原作業就會失敗。 Restore-AzKeyVaultKey 會還原機碼的所有重要版本及所有中繼資料（包括金鑰名稱）。
  
## <a name="manage-key-vault-permissions"></a>管理主要 vault 許可權

有幾個 Cmdlet 可用，可讓您查看並視需要移除重要 vault 的許可權（如有必要）。 您可能需要移除許可權，例如，當員工離開團隊時。 針對上述每項工作，您將使用 Azure PowerShell。 如需 Azure Powershell 的相關資訊，請參閱 [Azure PowerShell 的概述](/powershell/azure/)。

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

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>使用客戶金鑰 (DEPs) 管理資料加密原則

客戶金鑰處理不同服務間的 DEPs 有所不同。 例如，您可以為不同的服務建立不同數目的 DEPs。

**Exchange Online 和商務用 Skype：** 您最多可以建立 50 DEPs。 如需相關指示，請參閱 [Create a data encryption policy (DEP) 以搭配 Exchange Online 和商務用 Skype 使用](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)。

**SharePoint 線上、商務 OneDrive 及小組檔案：** DEP 適用于一個地理位置（也稱為 _地理_ 位置）中的資料。 如果您使用 Office 365 的多地理位置功能，您可以為每個地理位置建立一個 DEP。 如果您不是使用多地理位置，您可以建立一個 DEP。 一般來說，當您設定客戶金鑰時，您會建立 DEP。 如需相關指示，請參閱為 [商務地區的每一個 SharePoint 線上及 OneDrive 建立資料加密原則 (DEP) ](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)。

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>查看您為 Exchange Online 和商務用 Skype 建立的 DEPs

若要查看您使用 Get-DataEncryptionPolicy PowerShell Cmdlet 為 Exchange Online 和商務用 Skype 建立的所有 DEPs 清單，請完成下列步驟。

1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，連線 [至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 若要傳回組織中的所有 DEPs，請執行不含任何參數的 Get-DataEncryptionPolicy Cmdlet。

   ```powershell
   Get-DataEncryptionPolicy
   ```

   如需 Get-DataEncryptionPolicy Cmdlet 的詳細資訊，請參閱 [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy)。

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>將信箱遷移至雲端之前，請先指派 DEP

當您指派 DEP 時，Microsoft 365 會在遷移期間使用指派的 DEP 來加密信箱的內容。 這種處理常式比遷移信箱、指派 DEP，然後等候進行加密更有效率，可能需要數小時或數天。

若要在將 DEP 遷移至 Office 365 之前將其指派給該信箱，請在 Exchange Online 中執行 Set-MailUser Cmdlet PowerShell:

1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，連線 [至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 執行 Set-MailUser Cmdlet。

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   其中 *GeneralMailboxOrMailUserIdParameter* 指定信箱，且 *DataEncryptionPolicyIdParameter* 是 DEP 的識別碼。 如需 Set-MailUser Cmdlet 的詳細資訊，請參閱 [Set-MailUser](/powershell/module/exchange/set-mailuser)。

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>決定指派給信箱的 DEP

若要判斷指派給信箱的 DEP，請使用 Get-MailboxStatistics Cmdlet。 Cmdlet 會傳回唯一識別碼 (GUID) 。
  
1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，連線 [至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

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

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>驗證 Exchange Online 和商務用 Skype 的加密是否已完成

加密信箱可能需要一些時間。 建議您先等候72小時，再嘗試在變更 DEP 後，或第一次將 DEP 指派給信箱之後，再嘗試驗證加密。
  
使用 Get-MailboxStatistics Cmdlet 來判斷信箱是否已加密。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果信箱已加密，IsEncrypted 屬性會傳回 **true** 值，如果信箱未加密，則傳回 **false** 的值。

完成信箱移動的時間取決於信箱的大小。 若在您指派新的 DEP 後，客戶機碼尚未從72小時內完全加密，請與 Microsoft 支援部門聯繫以尋求協助。 無法再使用 New-MoveRequest Cmdlet 進行本機信箱移動。 如需詳細資訊，請參閱本次 [宣告](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 。

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>驗證 SharePoint 線上、商務 OneDrive 及小組檔案的加密是否已完成

執行 Get-SPODataEncryptionPolicy Cmdlet 以檢查加密的狀態，如下所示：

```powershell
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

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>從客戶金鑰回復至 Microsoft 受管理的金鑰

針對承租人層級的客戶機碼，您需要使用客戶金鑰中的「脫離」要求與 Microsoft 聯繫。 要求會由「呼叫工程小組」處理。

針對應用層級的用戶端機碼，您可以使用 [設定信箱] PowerShell Cmdlet，從信箱取消指派 DEP，然後將設定 `DataEncryptionPolicy` 為 `$NULL` 。 執行此 Cmdlet unassigns 目前指派的 DEP，並使用與預設 Microsoft 管理金鑰相關聯的 DEP 來 reencrypts 信箱。 您無法取消指派 Microsoft managed 機碼所用的 DEP。 如果您不想使用 Microsoft 受管理的金鑰，您可以將其他客戶金鑰 DEP 指派給信箱。

若要使用 Set-Mailbox PowerShell Cmdlet 從信箱中取消指派 DEP，請完成下列步驟。

1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，連線 [至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 執行 Set-Mailbox Cmdlet。

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>撤銷您的金鑰，並啟動資料清除路徑處理常式

您可以控制所有根機碼（包括可用性機碼）的吊銷。 客戶金鑰可讓您控制法規需求對您的結束規劃方面。 如果您決定撤銷您的金鑰以清除您的資料並退出服務，服務會在資料清除程式完成之後刪除可用性金鑰。 您無法執行租使用者層級原則的資料清除。

Microsoft 365 會審核和驗證資料清除路徑。 如需詳細資訊，請參閱 [服務信任入口網站](https://servicetrust.microsoft.com/)上可用的 SSAE 18 SOC 2 報告。 此外，Microsoft 建議下列檔：

- [Microsoft Cloud 中金融機構的風險評估與規範指南](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 退出規劃考慮](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

不同的服務之間的資料清除路徑稍有不同。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>吊銷您的客戶金鑰和 Exchange Online 和商務用 Skype 的可用性金鑰

當您啟動 Exchange Online 和商務用 Skype 的資料清除路徑時，您會在 DEP 上設定永久的資料清除要求。 這樣做會永久刪除此 DEP 所指派的信箱中的加密資料。

因為您一次只能對一個 DEP 執行 PowerShell Cmdlet，請考慮在您啟動資料清除路徑之前，先將單一 DEP 重新指派給所有信箱。

> [!WARNING]
> 請勿使用資料清除路徑來刪除信箱的子集。 此程式僅適用于即將退出服務的客戶。

若要啟動資料清除路徑，請完成下列步驟：

1. 從 Azure Key 保存庫移除 "O365 Exchange Online" 的自動換行及解出許可權。

2. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，連線 [至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

3. 針對包含您要刪除之信箱的每個 DEP，執行 [DataEncryptionPolicy 指令程式](/powershell/module/exchange/set-dataencryptionpolicy) ，如下所示。

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   若命令失敗，請確定您已從 Azure Key Vault 的兩個金鑰中移除 Exchange Online 許可權（如本工作先前所指定）。當您使用 Set-DataEncryptionPolicy Cmdlet 設定 PermanentDataPurgeRequested 參數之後，就無法再將此 DEP 指派給信箱。

4. 請與 Microsoft 支援人員聯繫並要求資料清除 eDocument。

    在您提出要求時，Microsoft 會傳送您的法律檔，以確認和授權資料刪除。 在上架中，以 FastTrack 提供的核准者簽署的組織中的人員必須簽署此檔。 一般來說，這是公司中執行法律授權的人員或其他指定人員，可代表您的組織簽署書面。

5. 當您的代理人簽署法律檔時，通常會透過 eDoc 簽章) 將其退回 Microsoft (。

    Microsoft 收到法律檔之後，Microsoft 會執行 Cmdlet 以觸發資料清除，這會先刪除原則，並將信箱標記為永久刪除，然後刪除可用性金鑰。 資料清除程式完成後，就無法存取 Exchange Online 中的資料，且無法復原。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>吊銷客戶金鑰和 SharePoint 線上、商務 OneDrive 與小組檔案的可用性金鑰

若要為 SharePoint 線上、商務用 OneDrive 或小組檔案啟動資料清除路徑，請完成下列步驟：

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