---
title: 租用戶等級的 Microsoft 365 客戶金鑰 (公開預覽)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/17/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: 瞭解如何為您的 Microsoft 365 租使用者中的所有資料設定客戶金鑰。
ms.openlocfilehash: f50986b4e72808d4a1cd4dc8ee0182eb9c0a2455
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922687"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>在承租人層級 (公開預覽的 Microsoft 365 客戶金鑰概述) 

使用您提供的金鑰，您可以建立資料加密原則 (DEP) 並指派給租使用者。 DEP 會針對這些工作負載在租使用者上進行資料加密：

- 小組聊天訊息 (1:1 聊天、群組交談、會議聊天及通道交談) 
- 小組媒體郵件 (影像、程式碼片段、影片郵件、音訊訊息、wiki 影像) 
- 小組儲存中儲存的小組通話和會議錄製
- 小組聊天通知
- 小娜的小組聊天建議
- 小組狀態郵件
- Exchange Online 的使用者和信號資訊
- Exchange Online 信箱，但在應用層級尚未加密客戶金鑰 DEPs

針對 Microsoft 小組，租使用者層級的客戶機碼會從 DEP 指派給租使用者時，加密新的資料。 公開預覽不支援加密過去的資料。 針對 Exchange Online，客戶金鑰會加密所有現有和新的資料。

您可以為每個租使用者建立多個 DEPs，但在任何時間點都只能指定一個 DEP。 當您指派 DEP 時，系統會自動開始加密，但可能需要一些時間才能完成，具體取決於您的承租人的大小。

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>承租人層級原則新增更多控制至 Microsoft 365 的客戶機碼

如果您已設定 Exchange Online 和 Sharepoint Online 的客戶金鑰，以下是新租使用者層級公開預覽的方式。

您建立的承租人層級加密原則會加密 microsoft 團隊和 Microsoft 365 中的 Exchange Online 工作負載的所有資料。 不過，對於 Exchange Online，如果您已將客戶金鑰 DEPs 指派給個別信箱，則租使用者層級原則不會覆寫這些 DEPs。 租使用者層級原則只會加密尚未指定信箱層級客戶金鑰 DEP 的信箱。

例如，Microsoft 小組檔案和部分小組的呼叫和會議錄製會儲存在商務用 OneDrive 中，SharePoint 是由 SharePoint 線上 DEP 加密。 單一 SharePoint 線上 DEP 會加密單一地理位置內的內容。

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>在承租人層級設定客戶機碼 (公開預覽) 

這些步驟類似，但與在應用層級設定客戶機碼的步驟並不相同。 您應只對測試承租人中的測試資料使用此公開預覽。 請勿在生產資料或您的實際執行環境中使用此版本。 如果您已具備客戶金鑰的實際執行部署，請使用下列步驟，在測試環境中的承租人層級設定客戶機碼。 指派租使用者層級的 DEP 給租使用者後，您就可以開始驗證程式並 m365ck@microsoft.com 任何問題或考慮事項。 您也可以在 [Microsoft 365 的靜態加密驗證指示](https://aka.ms/CustomerKey/PublicPreviewValidation)的公開預覽中，找到已記錄的驗證步驟。

您可以遠端連線至 Azure PowerShell，以完成大部分的工作。 為了獲得最佳結果，請使用版本4.4.0 或更新版本的 Azure PowerShell。

開始之前，請確定下列各項：

- 您必須使用具有合規性系統管理員角色的工作或學校帳戶，以在租使用者層級設定客戶金鑰。
- 確定您的組織有適當的授權。 使用企業合約或雲端服務提供者，以支付已開發票的 Azure 訂閱。 客戶機碼不支援使用「隨付」方案或信用卡使用信用卡購買的 Azure 訂閱。 從 office 365 的2020年4月1日開始，于 office 365 E5，M365 E5，M365 E5 規範，以及 M365 E5 & 控管 SKUs 中提供的資訊保護。 Office 365 Advanced 相容性 SKU 已無法再提供購置新的授權。 現有的 Office 365 Advanced 相容性授權會繼續受到支援。 雖然在具有適當授權的承租人下可以啟用服務，但您仍然應該確定所有從服務受益的使用者都有適當的授權。

### <a name="create-two-new-azure-subscriptions"></a>建立兩個新的 Azure 訂閱

客戶金鑰需要每個資料加密原則 (DEP) 的兩個金鑰。 若要做到這一點，您必須建立兩個 Azure 訂閱。 建議的最佳作法是，您組織中的個別成員可以在每個訂閱中設定一個金鑰。 請只使用這些 Azure 訂閱來管理 Microsoft 365 的加密金鑰。 這會保護您的組織，以防其中一個操作員意外、故意或惡意刪除，或 mismanages 其負責的金鑰。

您可以為組織建立的 Azure 訂閱數目沒有實際的限制。 遵循這項最佳作法可協助將「因人」錯誤所造成的影響降至最低，以協助管理客戶金鑰所使用的資源。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>註冊 Azure 訂閱以使用強制保留期間

暫時或永久遺失根加密金鑰的功能可能會造成中斷，甚至可能造成資料遺失。 因此，與客戶金鑰搭配使用的資源需要加強保護。 與客戶金鑰搭配使用的所有 Azure 資源，除了預設設定之外，還提供保護機制。 您可以使用 Azure 訂閱進行標記或註冊，以防止立即和不可撤銷的取消。 這稱為註冊強制保留期間。 在必要保留期間內註冊 Azure 訂閱所需的步驟，必須與 Microsoft 共同作業。 此程式最多可長達五個工作日。 先前，這有時候稱為「不要取消」。
  
在聯繫 Microsoft 365 團隊之前，您必須針對每個用客戶金鑰使用的 Azure 訂閱執行下列步驟。 開始之前，請確定您已安裝 [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) 模組。

1. 使用 Azure PowerShell 登入。 如需相關指示，請參閱 [使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。

2. 執行 Register-AzProviderFeature Cmdlet 註冊您的訂閱，以使用強制保留期間。 針對每個訂閱執行此動作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. 請與 Microsoft 聯繫以在 [m365ck@microsoft.com](mailto:m365ck@microsoft.com)完成此程式。 在您的電子郵件中包含下列專案：

   主旨 **：客戶** 金鑰\<*Your tenant's fully-qualified domain name*\>

   **Body**：訂閱 IDs，您想要完成其強制保留期間。
   每個訂閱的 Get-AzProviderFeature 輸出。

   完成此程式的服務等級協定 (SLA) 一天之後，Microsoft 會 (通知您已註冊訂閱，) 您已註冊訂閱，以使用強制保留期間。

4. 當您收到來自 Microsoft 的通知，表明已完成註冊後，請執行 Get-AzProviderFeature 命令，按下列方式，以確認註冊的狀態。 若驗證，Get-AzProviderFeature 命令會傳回登錄 **狀態** 屬性的 **註冊** 值。 針對每個訂閱執行此動作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. 若要完成此程式，請執行 Register-AzResourceProvider 命令。 針對每個訂閱執行此動作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每個訂閱中建立高級 Azure 金鑰 Vault

建立主要 vault 的步驟會在 [開始使用 Azure Key vault](/azure/key-vault/general/overview)時記錄下來，可引導您安裝及啟動 azure PowerShell、連線至 azure 訂閱、建立資源群組，以及在該資源群組中建立金鑰 vault。
  
當您建立金鑰 vault 時，您必須選擇 SKU： [標準] 或 [特優]。 Standard SKU 允許使用軟體來保護 Azure 金鑰 Vault 金鑰-沒有硬體安全性模組 (HSM) 金鑰保護-而且特優 SKU 允許使用 Hsm 來保護主要 Vault 金鑰。 客戶金鑰可接受使用任一 SKU 的金鑰電子倉庫，但 Microsoft 強烈建議您只使用特優 SKU。 使用任何一種類型之機碼的作業成本是相同的，所以每個受 HSM 保護的金鑰只會有每個月的成本差異。 如需詳細資訊，請參閱 [主要 Vault 定價](https://azure.microsoft.com/pricing/details/key-vault/) 。
  
> [!IMPORTANT]
> 針對實際執行資料使用特優 SKU 金鑰保存庫和受版權保護的金鑰，只使用標準的 SKU 金鑰保存庫和金鑰進行測試和驗證。

使用主要保管區的一般前置詞，並包含主要 vault 和機碼的使用和範圍的縮寫。 例如，針對存放庫在北美的 Contoso 服務，可能的名稱成對為 Contoso-O365-NA-VaultA1 和 Contoso-O365-NA-VaultA2。 保存庫名稱是 Azure 內全域唯一的字串，因此，您可能需要嘗試所需名稱的變化，以防其他 Azure 客戶已索取所需的名稱。 設定後，就無法變更保存庫名稱，因此最佳作法是設定安裝的書面計畫，然後使用第二個人驗證計畫是否正確執行。

如果可能，請在非成對區域中建立您的電子倉庫。 配對的 Azure 區域可提供跨服務失敗網域的高可用性。 因此，區域配對可以視為彼此的備份區域。 這表示位於某個地區的 Azure 資源會透過成對區域自動取得容錯。 基於此原因，針對在地區是成對的資料加密原則中所使用的兩個保存庫選擇地區時，只會使用兩個可用區域的可用性。 大多數地理有兩個地區，所以尚不能選取非成對區域。 如有可能，請選擇兩個不成對的區域，以用於資料加密原則的兩個保存庫。 其優點是共有四個地區的可用性。 如需詳細資訊，請參閱 [Business 持續性和嚴重損壞修復 (BCDR) ： Azure 成對區域](/azure/best-practices-availability-paired-regions) 的目前區域配對清單。

### <a name="assign-permissions-to-each-key-vault"></a>將許可權指派給每個金鑰保存庫

針對每個金鑰保存庫，您必須根據您的實施，為客戶機碼定義三組不同的許可權。 例如，您必須為下列各項專案定義一組許可權：
  
- **主要 vault 系統管理員** ，會針對您的組織執行重要 vault 的日常管理。 這些工作包括備份、建立、取得、匯入、清單及還原。

  > [!IMPORTANT]
  > 指派給主要 vault 管理員的許可權集不包含刪除金鑰的許可權。 這是故意和重要的作法。 刪除加密金鑰通常不會這麼做，因為這樣做會永久銷毀資料。 根據預設，請勿將此許可權授與主要 vault 管理員的最佳作法。 相反地，針對主要 vault 投稿人保留這種情況，而且只要清楚瞭解對結果的瞭解，就只需在短期內將其指派給系統管理員。
  
  若要將這些許可權指派給組織中的使用者，請使用 Azure PowerShell 登入您的 Azure 訂閱。 如需相關指示，請參閱 [使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。

   執行 Set-AzKeyVaultAccessPolicy Cmdlet 指派必要的許可權。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   例如：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- 可以變更 Azure Key Vault 自身許可權的 **主要 vault 參與者**。 您必須變更這些許可權，因為員工離職或加入您的小組，或是主要 vault 管理員合法需要刪除或還原機碼的少數情況。 這組重要的 vault 投稿人員必須授與主要 vault 上的投稿人角色。 您可以使用 Azure 資源管理員指派此角色。 如需詳細步驟，請參閱 [Use Role-Based Access Control](/azure/active-directory/role-based-access-control-configure) ，以管理您的 Azure 訂閱資源的存取權。 建立訂閱的系統管理員預設具有這種存取權，以及將其他管理員指派給參與者角色的能力。

- Microsoft 365 在租使用者層級執行客戶金鑰工作的 **rest 加密服務資料**。 若要授與 Microsoft 365 的許可權，請使用下列語法執行 **AzKeyVaultAccessPolicy** Cmdlet：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  其中：

  - *保存庫名稱* 是您建立的主要 vault 名稱。

  範例：針對靜態加密服務的 Microsoft 365 資料，請將  *microsoft 365 appID* 取代為 `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>在金鑰保存庫上啟用然後確認虛刪除

當您可以快速復原金鑰時，由於意外或惡意刪除的金鑰，您很可能會因意外或惡意刪除的金鑰而經歷長時間的服務中斷。 啟用此設定（稱為「虛刪除」），才能搭配客戶機碼使用金鑰。 啟用 [虛刪除] 可讓您在刪除90天內復原金鑰或存放庫，而不需要從備份中還原。
  
若要在金鑰保存庫上啟用虛刪除，請完成下列步驟：
  
1. 使用 Windows PowerShell 登入您的 Azure 訂閱。 如需相關指示，請參閱 [使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。

2. 執行 [AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) Cmdlet。 在此範例中， *保存庫名稱* 是您要啟用 soft delete 之主要 vault 的名稱：

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. 執行 **AzKeyVault** 指令程式，確認已為金鑰保存庫設定 soft delete。 如果已正確設定 key vault 的 [虛刪除]，則 _Soft Delete Enabled_ 屬性會傳回 **True** 值：

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>透過建立或匯入機碼，將機碼新增到每個機碼 vault

有兩種方法可以將機碼新增到 Azure Key Vault;您可以直接在 Key Vault 中建立金鑰，也可以匯入金鑰。 直接在 Key Vault 中建立金鑰是不夠複雜的方法，而匯入金鑰會提供如何產生機碼的整體控制權。 使用 RSA 機碼。 Azure 金鑰 Vault 不支援使用橢圓曲線鍵進行換行及解換。
  
若要直接在金鑰保存庫中建立金鑰，請執行 AzKeyVaultKey 指令 [程式](/powershell/module/az.keyvault/add-azkeyvaultkey) ，如下所示：
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

其中：

- *vault 名稱* 是您要在其中建立機碼的金鑰 vault 名稱。

- *key name* 是您要給予新機碼的名稱。

  > [!TIP]
  > 使用主要保險檔的上述命名慣例，以前面所述的名稱慣例命名機碼。 如此一來，在僅顯示金鑰名稱的工具中，該字串是自我描述的。
  
如果您想要使用 HSM 來保護機碼，請確定您將 **hsm** 指定為 _Destination_ 參數的值，否則請指定 **軟體**。

例如：
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>檢查機碼的恢復層級

Microsoft 365 要求 Azure Key Vault 訂閱設定為 [不要取消]，且客戶機碼使用的金鑰已啟用 [虛刪除]。 您可以查看金鑰上的復原層級，確認這一點。
  
若要檢查機碼的復原層級，請在 Azure PowerShell 中執行 Get-AzKeyVaultKey Cmdlet，如下所示：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

若 _Recovery Level_ 屬性傳回的值不是可復原的 **+ ProtectedSubscription**，您必須查看這篇文章，並確定您已遵循將訂閱置於 [不要取消] 清單中的所有步驟，以及您已在每個主要存放庫上啟用「虛刪除」。 接下來，將電子郵件輸出的螢幕擷取畫面傳送 `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` 至 m365ck@microsoft.com。

### <a name="back-up-azure-key-vault"></a>備份 Azure Key Vault

立即建立或變更索引鍵，執行備份及儲存備份的備份，不論是線上還是離線。 不要將離線副本連線到任何網路。 請改為將它們儲存在實體安全或商業儲存設施中。 至少應有一個備份副本儲存在發生嚴重損壞時可存取的位置。 備份 blob 是一種還原重要材料的唯一方法，應永久銷毀主要 Vault 金鑰，否則無法使用。 Azure Key Vault 外部的金鑰和匯入到 Azure Key Vault 的金鑰不會做為備份，因為客戶金鑰使用金鑰所需的中繼資料不存在於外部金鑰。 只有從 Azure 金鑰保存庫取得的備份可用於使用客戶金鑰進行還原作業。 因此，請務必在上載或建立金鑰時進行 Azure 金鑰 Vault 備份。
  
若要建立 Azure Key Vault 機碼的備份，請執行 [AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) Cmdlet，如下所示：

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

確定您的輸出檔案使用尾碼 `.backup` 。
  
由此 Cmdlet 所產生的輸出檔已加密，且無法用於 Azure Key Vault 之外。 備份只能還原至執行備份的來源 Azure 訂閱。
  
例如：
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>驗證 Azure 金鑰 Vault 設定設定

在 DEP 中使用金鑰之前執行驗證是選用的，但是強烈建議您這麼做。 尤其是，如果您使用步驟來設定您的金鑰和保險庫（如本主題所述），您應該先驗證 Azure 金鑰 Vault 資源的健康情況，再設定客戶金鑰。
  
若要確認您的機碼已啟用 get、wrapKey 及 unwrapKey 作業，請執行下列動作：
  
執行 [AzKeyVault 指令程式](/powershell/module/az.keyvault/get-azkeyvault) ，如下所示：
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

在 [輸出] 中，視需要尋找存取原則及 Microsoft 365 應用程式識別碼 (GUID) 。 所有三個作業、get、wrapKey 及 unwrapKey 都必須顯示在 [索引鍵的許可權] 底下。
  
如果存取原則設定不正確，請執行 Set-AzKeyVaultAccessPolicy Cmdlet，如下所示：
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

範例：針對靜態加密服務的 Microsoft 365 資料，請將  *microsoft 365 appID* 取代為 `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

若要確認沒有為您的金鑰設定到期日，請執行 [AzKeyVaultKey 指令程式](/powershell/module/az.keyvault/get-azkeyvault) ，如下所示：
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

已到期的金鑰無法由客戶金鑰使用，而且嘗試使用到期金鑰會失敗，而且可能會造成服務中斷。 強烈建議使用與客戶金鑰搭配使用的金鑰沒有到期日。 到期日一經設定，便無法移除，但可以變更為不同的日期。 如果必須使用具有到期日期設定的金鑰，請將 [到期] 值變更為12/31/9999。 到期日設定為日期12/31/9999 以外的金鑰將不會通過 Microsoft 365 驗證。
  
若要變更已設定為12/31/9999 以外任何值的到期日，請執行 AzKeyVaultKey 指令 [程式](/powershell/module/az.keyvault/update-azkeyvaultkey) ，如下所示：
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>取得每個 Azure 金鑰保存庫機碼的 URI

當您在 Azure 中完成所有步驟以設定金鑰保存庫並新增金鑰之後，請執行下列命令，以取得每個 key vault 中的金鑰的 URI。 當您稍後建立並指派每個 DEP 時，您將需要使用這些 URIs，因此請將此資訊儲存在安全的位置。 請記得對每一個按鍵 vault 執行一次此指令。
  
Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>為您的租使用者設定客戶金鑰加密原則

您必須已獲指派許可權，才能執行這些 Cmdlet。 雖然這篇文章列出指令程式的所有參數，但如果不包含在指派給您的許可權中，您可能無法存取某些參數。 若要尋找在組織中執行任何 Cmdlet 或參數所需的權限，請參閱 [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)。

### <a name="create-policy"></a>建立原則

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

描述：使用兩個 AKV 根機碼，啟用相容性管理員以建立新的資料加密原則 (DEP) 。 一旦建立後，便可使用 Set-M365DataAtRestEncryptionPolicyAssignment Cmdlet 指派原則。 在初次指派按鍵或旋轉按鍵後，新的機碼可能需要長達24小時才會生效。 如果新的 DEP 需要24小時以上才能生效，請與 Microsoft 聯繫。

範例：

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

參數：

| 名稱 | 描述 | 選用 (Y/N)  |
|----------|----------|---------|
|姓名|資料加密原則的易記名稱|N|
|AzureKeyIDs|指定 Azure Key Vault 機碼的兩個 URI 值，以逗號分隔，以與資料加密原則產生關聯|N|
|描述|資料加密原則的描述|N|

### <a name="assign-policy"></a>指派原則

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "<Default_PolicyName or Default_PolicyID>"
```

描述：此指令程式用於設定預設資料加密原則。 這個原則將用來加密所有支援工作負載中的資料。 

範例：

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Default_PolicyName"
```

參數：

| 名稱 | 描述 | 選用 (Y/N)  |
|----------|----------|---------|
-DataEncryptionPolicy|指定需要指派的資料加密原則;請指定原則名稱或原則識別碼。|N|

### <a name="modify-or-refresh-policy"></a>修改或重新整理原則

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

描述：此 Cmdlet 可用於修改或重新整理現有的原則。 也可以用來啟用或停用原則。 在初次指派按鍵或旋轉按鍵後，新的機碼可能需要長達24小時才會生效。 如果新的 DEP 需要24小時以上才能生效，請與 Microsoft 聯繫。

範例：

停用資料加密原則。

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

重新整理資料加密原則。

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "EUR Policy" -Refresh
```

參數：

| 名稱 | 描述 | 選用 (Y/N)  |
|----------|----------|---------|
|-Identity|指定您要修改的資料加密原則。|N|
|-重新整理|在您旋轉 Azure Key Vault 中的任何相關機碼之後，請使用重新整理參數來更新資料加密原則。 您不需要使用此參數指定值。|Y|
|-已啟用|Enabled 參數會啟用或停用資料加密原則。 停用原則之前，必須先將其指派給您的租使用者。 有效值為：</br > $true：已啟用原則</br > $true：已啟用原則。此為預設值。|Y|
|-名稱|Name 參數會指定資料加密原則的唯一名稱。|Y|
|-描述|Description 參數會指定資料加密原則的選擇性描述。|Y|

### <a name="get-policy-details"></a>取得原則詳細資料

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

描述：此 Cmdlet 會列出針對租使用者或特定原則的詳細資料所建立的所有 M365DataAtRest 加密原則。

範例：

此範例會傳回組織中 M365DatAtRest 加密原則的摘要清單。

```powershell
Get-M365DataAtRestEncryptionPolicy
```

此範例會傳回名為 "名稱 Policy" 的資料加密原則的詳細資訊。

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

參數：

| 名稱 | 描述 | 選用 (Y/N)  |
|----------|----------|---------|
|-Identity|指定您要列出詳細資料的資料加密原則。|Y|

### <a name="get-policy-assignment-info"></a>取得原則指派資訊

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

描述：此 Cmdlet 會列出目前指派給承租人的原則。

## <a name="offboarding-from-customer-key"></a>從客戶金鑰脫離

如果您需要回復至 Microsoft 受管理的金鑰，您可以。 當您下架時，會使用每個個別工作負載支援的預設加密來重新加密您的資料。 例如，Exchange Online 支援使用 Microsoft 管理金鑰的預設加密。

如果您決定在承租人層級從客戶機碼下架租使用者，請透過電子郵件要求 [停用] [m365ck@microsoft.com](mailto:m365ck@microsoft.com)的承租人服務。

> [!IMPORTANT]
> 脫離會與資料清除相同。 資料清除會永久加密-從 Microsoft 365 刪除您組織的資料，而脫離不會。 您無法執行租使用者層級原則的資料清除。 如需資料清除路徑的詳細資訊，請參閱 [撤銷您的金鑰及開始資料清除路徑](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)程式。

## <a name="about-the-availability-key"></a>關於可用性金鑰

如需可用性機碼的相關資訊，請參閱 [瞭解可用性金鑰](customer-key-availability-key-understand.md)。

## <a name="key-rotation"></a>金鑰輪替

如需隨客戶金鑰使用的旋轉或滾動機碼的相關資訊，請參閱 [滾或輪替客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)。 當您更新 DEP 以使用新版本的金鑰時，會執行 Set-M365DataAtRestEncryptionPolicy Cmdlet，如本文稍早所述。

## <a name="related-articles"></a>相關文章：

- [客戶金鑰服務加密](customer-key-overview.md)

- [滾動或旋轉客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)

- [深入瞭解可用性金鑰](customer-key-availability-key-understand.md)

- [服務加密](office-365-service-encryption.md)