---
title: 設定客戶金鑰
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
description: 瞭解如何設定 Microsoft 365 的客戶金鑰。
ms.openlocfilehash: e187c01a355cc9b926e892cb3326b5a527c714a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344671"
---
# <a name="set-up-customer-key"></a>設定客戶金鑰

使用客戶金鑰，您可以控制組織的加密金鑰，然後設定 Microsoft 365，使用這些金鑰在 Microsoft 資料中心內加密您的資料。 換句話說，客戶金鑰可讓客戶新增屬於其金鑰的加密層級。

設定 Azure，然後才能將客戶金鑰用於 Office 365。 本文說明建立及設定必要 Azure 資源所需遵循的步驟，並提供在 Office 365 中設定客戶機碼的步驟。 在您設定 Azure 之後，您可以決定要指派哪一個原則，以在組織中的各種 Microsoft 365 工作負載中，指派哪些機碼來加密資料。 如需客戶機碼的相關資訊，或有關一般概述，請參閱[Office 365 中的客戶金鑰服務加密](customer-key-overview.md)。
  
> [!IMPORTANT]
> 強烈建議您遵循本文中的最佳作法。 這些是以 **TIP** 和 **重要** 的方式呼叫。 客戶金鑰可讓您控制根加密金鑰，其範圍可以像整個組織一樣大。 這表示對這些機碼所做的錯誤可能會產生很大的影響，而且可能會導致服務中斷或資料遺失。
  
## <a name="before-you-set-up-customer-key"></a>在您設定客戶機碼之前

開始之前，請先確定您的組織具備適當的 Azure 訂閱和授權。 使用 Enterprise 合約或雲端服務提供者的付費 Azure 訂閱。 不接受信用卡支付。 核准和設定發票的帳戶需求。 您透過免費、試用、Sponsorships、MSDN 訂閱和舊版支援所提供的訂閱並無資格。

Office 365E5、Microsoft 365 E5、Microsoft 365 E5 合規性及 Microsoft 365 E5 資訊保護 & 控管 SKUs 提供客戶金鑰。 Office 365 進階合規性SKU 已不再提供購置新的授權。 將繼續支援現有的 Office 365 進階合規性授權。

若要瞭解本文中的概念和程式，請參閱 [Azure 重要保險庫](/azure/key-vault/) 檔。 此外，熟悉 Azure 中使用的條款，例如 [AZURE AD 租](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)使用者。
  
如果您需要檔以外的其他支援，請與 Microsoft 諮詢服務 (MCS) 、Premier Field 工程 (PFE) 或 Microsoft 合作夥伴以取得協助。 若要提供對客戶機碼的意見反應（包括檔），請將您的想法、建議和觀點傳送至 customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>設定客戶機碼的步驟概述

若要設定客戶機碼，請依所列順序完成這些工作。 本文的其餘部分提供每項工作的詳細指示，或連結至程式中每個步驟的詳細資訊。
  
**在 Azure 和 Microsoft FastTrack：**
  
您可以遠端連線至 Azure PowerShell，以完成大部分的工作。 為了獲得最佳結果，請使用 Azure PowerShell 版本4.4.0 或更新版本。
  
- [建立兩個新的 Azure 訂閱](#create-two-new-azure-subscriptions)

- [提交要求以啟用 Office 365 的客戶金鑰](#submit-a-request-to-activate-customer-key-for-office-365)
 
- [註冊 Azure 訂閱以使用強制保留期間](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  註冊可以花一到五個工作日。

- [在每個訂閱中建立高級 Azure 金鑰 Vault](#create-a-premium-azure-key-vault-in-each-subscription)

- [將許可權指派給每個金鑰保存庫](#assign-permissions-to-each-key-vault)

- [確定重要電子倉庫已啟用 soft delete](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [透過建立或匯入機碼，將機碼新增到每個機碼 vault](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [檢查機碼的恢復層級](#check-the-recovery-level-of-your-keys)

- [備份 Azure Key Vault](#back-up-azure-key-vault)

- [驗證 Azure 金鑰 Vault 設定設定](#validate-azure-key-vault-configuration-settings)

- [取得每個 Azure 金鑰保存庫機碼的 URI](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>完成 Azure Key Vault 中的工作及客戶機碼的 Microsoft FastTrack

在 Azure Key Vault 中完成這些工作。 您必須針對所有與客戶金鑰搭配使用的 DEPs，完成這些步驟。
  
### <a name="create-two-new-azure-subscriptions"></a>建立兩個新的 Azure 訂閱

客戶金鑰需要兩個 Azure 訂閱。 最佳作法是 Microsoft 建議您建立新的 Azure 訂閱，以與客戶金鑰搭配使用。 Azure Key Vault 金鑰只可在相同 Azure Active Directory 中的應用程式授權 (Microsoft Azure Active Directory) 租使用者，您必須使用與 DEPs 將會指派之組織搭配使用的相同 Azure AD 租使用者來建立新的訂閱。 例如，在您的組織中使用具有全域系統管理員許可權的公司或學校帳戶。 如需詳細步驟，請參閱 [註冊 Azure 做為組織](/azure/active-directory/fundamentals/sign-up-organization)。
  
> [!IMPORTANT]
> 客戶金鑰需要每個資料加密原則 (DEP) 的兩個金鑰。 為了達到此目的，您必須建立兩個 Azure 訂閱。 建議的最佳作法是，您組織中的個別成員可以在每個訂閱中設定一個金鑰。 您應只使用這些 Azure 訂閱來管理 Office 365 的加密金鑰。 這會保護您的組織，以防其中一個操作員意外、故意或惡意刪除，或 mismanages 其負責的金鑰。

您可以為組織建立的 Azure 訂閱數目沒有實際的限制。 遵循這些最佳作法，可在協助管理客戶金鑰所使用的資源時，將人為錯誤所造成的影響降至最低。
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>提交要求以啟用 Office 365 的客戶金鑰

建立兩個新的 Azure 訂閱後，您必須在 [Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)中提交適當的客戶金鑰提供要求。 您在組織內針對授權的稱號所做的選擇，在您的組織中所做的選擇，對完成客戶金鑰註冊是很重要且必要的。 組織內所選角色中的監察官員會確定任何要求的真偽，以吊銷和銷毀所有與客戶金鑰資料加密原則搭配使用的金鑰。 您需要針對您想要用於組織的每個客戶金鑰 DEP 類型執行一次此步驟。

**FastTrack 小組不會向客戶金鑰提供協助。Office 365 只會使用 FastTrack 入口網站，讓您提交表單，並協助我們追蹤客戶金鑰的相關提供者。在您提交 FastTrack 要求之後，請向對應的客戶金鑰上架小組以啟動上架程式。**
  
若要提交服務以啟用客戶金鑰，請完成下列步驟：
  
1. 在您的組織中使用具有全域系統管理員許可權的公司或學校帳戶，登入 [Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)。

2. 登入之後，請選取適當的網域。

3. 針對選取的網域，選擇上方導覽列中的 [ **要求服務** ]，並查看可用的提供方案清單。

4. 選擇適用于您的優惠資訊卡片：

   - **多個 Microsoft 365 工作負載：** 選擇 Microsoft 365 提議的 **要求加密金鑰** 說明。

   - **Exchange Online 和商務用 Skype：** 選擇 Exchange 提議的 **要求加密金鑰** 說明。

   - **SharePoint 線上、OneDrive 及 Teams 檔案：** 選擇 **SharePoint 和商務用 OneDrive 提供的要求加密金鑰** 說明。

5. 當您複習提供詳細資料之後，請選擇 [ **繼續] 步驟 2**。

6. 在 [服務] 表單上填寫所有適用的詳細資料和要求的資訊。 請特別注意您的組織中您要授權的監察官員，以核准加密金鑰和資料的永久和不可恢復的毀壞專案。 當您完成表單之後，請選擇 [ **提交**]。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>註冊 Azure 訂閱以使用強制保留期間

暫時或永久遺失根加密金鑰的功能可能會造成中斷，甚至可能造成資料遺失。 因此，與客戶金鑰搭配使用的資源需要加強保護。 與客戶金鑰搭配使用的所有 Azure 資源，除了預設設定之外，還提供保護機制。 您可以為 *強制保留期間* 標記或註冊 Azure 訂閱。 強制保留期間可防止對您的 Azure 訂閱進行立即和不可撤銷的取消。 在必要保留期間內註冊 Azure 訂閱所需的步驟，需要與 Microsoft 365 小組共同作業。 此程式可能會花費一到五個工作日。 先前，強制保留期間有時稱為「不要取消」。
  
在聯繫 Microsoft 365 小組之前，您必須針對每個搭配客戶金鑰使用的 Azure 訂閱執行下列步驟。 開始之前，請確定您已安裝[Azure PowerShell Az](/powershell/azure/new-azureps-module-az)模組。
  
1. 使用 Azure PowerShell 登入。 如需相關指示，請參閱[使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。

2. 執行 Register-AzProviderFeature Cmdlet 註冊您的訂閱，以使用強制保留期間。 請針對每個訂閱完成此動作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. 請與 Microsoft 聯繫完成此程式。

   - 若要讓客戶用機碼指派 DEP 給個別的 Exchange Online 信箱，請與[exock@microsoft.com](mailto:exock@microsoft.com)聯繫。

   - 若要讓客戶機碼指派 DEPs 以加密 SharePoint 線上及商務用 OneDrive 內容 (包括所有租使用者的 Teams 檔案) ，請與[spock@microsoft.com](mailto:spock@microsoft.com)聯繫。

   - 若要讓客戶機碼指派 DEPs 以加密多個 Microsoft 365 工作負載的內容 (Exchange Online、Teams、MIP EDM) 針對所有租使用者，請與[m365-ck@service.microsoft.com](mailto:m365-ck@service.microsoft.com)聯繫。

- 在您的電子郵件中包含下列資訊：

   主旨 **：客戶** 金鑰\<*Your tenant's fully qualified domain name*\>

   本文 **：包括** 您要為其完成必要保留期間的訂閱 IDs，以及每個訂閱的 Get-AzProviderFeature 輸出。

   完成此程式的服務等級協定 (SLA) 一天之後，Microsoft 會 (通知您已註冊訂閱，) 您已註冊訂閱，以使用強制保留期間。

4. 當您收到來自 Microsoft 的通知，表明已完成註冊後，請執行 Get-AzProviderFeature 命令，按下列方式，以確認註冊的狀態。 若驗證，Get-AzProviderFeature 命令會傳回登錄 **狀態** 屬性的 **註冊** 值。 請針對每個訂閱完成此步驟。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. 若要完成此程式，請執行 Register-AzResourceProvider 命令。 請針對每個訂閱完成此步驟。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每個訂閱中建立高級 Azure 金鑰 Vault

建立主要 vault 的步驟會在[開始使用 Azure key vault](/azure/key-vault/general/overview)時記錄下來，可引導您完成安裝和啟動 Azure PowerShell、連線至 Azure 訂閱、建立資源群組，以及在該資源群組中建立金鑰 vault。
  
當您建立金鑰 vault 時，您必須選擇 SKU： [標準] 或 [進階版]。 Standard SKU 允許使用軟體來保護 Azure 金鑰保存庫金鑰-沒有硬體安全性模組 (HSM) 金鑰保護-而且進階版 SKU 允許使用 Hsm 來保護主要 Vault 金鑰。 客戶金鑰可接受使用任一 SKU 的金鑰電子倉庫，但 Microsoft 強烈建議您只使用進階版 sku。 使用任何一種類型之機碼的作業成本是相同的，所以每個受 HSM 保護的金鑰只會有每個月的成本差異。 如需詳細資訊，請參閱 [主要 Vault 定價](https://azure.microsoft.com/pricing/details/key-vault/) 。
  
> [!IMPORTANT]
> 針對實際執行資料使用進階版 SKU 金鑰保存庫和受保護金鑰的金鑰，只使用標準的 SKU 金鑰保管，以進行測試及驗證。
  
針對每個您要使用客戶金鑰的 Microsoft 365 服務，在您建立的兩個 Azure 訂閱中建立金鑰 vault。 例如，若要將 DEPs 用於 Exchange Online、SharePoint 線上及多工作負載案例，以啟用客戶金鑰，您將會建立三個成對的主要保存庫。
  
使用金鑰保管的命名慣例，以反映要與保存庫建立關聯的 DEP 預定用途。 如需命名慣例建議，請參閱下列最佳作法一節。
  
為每個資料加密原則建立一組成對的保險集。 針對 Exchange Online，當您將原則指派給信箱時，會選取資料加密原則的範圍。 信箱只會指派一個原則，而且您可以建立最多50個原則。 SharePoint 線上原則的範圍包括地理位置或 _地理_ 位置中組織內的所有資料。 多重工作負載原則的範圍包括所有使用者支援之工作負載中的所有資料。

建立機碼 vault 也需要建立 Azure 資源群組，因為若啟用，主要電子倉庫需要儲存容量 (，) 但若啟用，也會產生儲存的資料。 最佳作法是 Microsoft 建議使用個別的系統管理員管理每個資源群組，並將其與一組系統管理員搭配使用，以管理所有相關客戶的重要資源。
  
> [!IMPORTANT]
> 若要使可用性最大化，請將主要存放庫放在接近 Microsoft 365 服務的區域中（例如，如果您的 Exchange Online 組織在北美，請將您的主要電子倉庫放在北美）。 如果您的 Exchange Online 組織位於歐洲，請將主要存放庫放在歐洲。
>
> 使用主要 vault 的一般前置詞，並包含主要存放區和機碼的使用和範圍的縮寫， (例如，針對存放庫在北美地區所用的 contoso SharePoint 服務，可能的一組名稱為 contoso-CK-na-na-VaultA1 和 contoso-CK--VaultA2。 保存庫名稱是 Azure 內全域唯一的字串，因此，您可能需要嘗試所需名稱的變化，以防其他 Azure 客戶已索取所需的名稱。 從2017年7月的電子倉庫名稱無法變更，因此最佳作法是使用書面計畫進行安裝，然後使用第二個人驗證計畫是否正確執行。
>
> 如果可能，請在非成對區域中建立您的電子倉庫。 配對的 Azure 區域可提供跨服務失敗網域的高可用性。 因此，區域配對可以視為彼此的備份區域。 這表示位於某個地區的 Azure 資源會透過成對區域自動取得容錯。 基於此原因，針對在地區是成對的資料加密原則中所使用的兩個保存庫選擇地區時，只會使用兩個可用區域的可用性。 大多數地理有兩個地區，所以尚不能選取非成對區域。 如有可能，請選擇兩個不成對的區域，以用於資料加密原則的兩個保存庫。 其優點是共有四個地區的可用性。 如需詳細資訊，請參閱 [Business 持續性和嚴重損壞修復 (BCDR) ： Azure 成對區域](/azure/best-practices-availability-paired-regions) 的目前區域配對清單。
  
### <a name="assign-permissions-to-each-key-vault"></a>將許可權指派給每個金鑰保存庫

根據您的實施，您必須為每個金鑰保存庫定義三組不同的許可權。 例如，您必須為下列各項專案定義一組許可權：
  
- **主要 vault 管理員** ，可對您的組織進行重要 vault 的日常管理工作。 這些工作包括備份、建立、取得、匯入、清單及還原。

  > [!IMPORTANT]
  > 指派給主要 vault 管理員的許可權集不包含刪除金鑰的許可權。 這是故意和重要的作法。 刪除加密金鑰通常不會這麼做，因為這樣做會永久銷毀資料。 根據預設，請勿將此許可權授與主要 vault 管理員的最佳作法。 相反地，針對主要 vault 投稿人保留這種情況，而且只要清楚瞭解對結果的瞭解，就只需在短期內將其指派給系統管理員。
  
  若要將這些許可權指派給組織中的使用者，請使用 Azure PowerShell 登入您的 Azure 訂閱。 如需相關指示，請參閱[使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。

- 執行 Set-AzKeyVaultAccessPolicy Cmdlet 指派必要的許可權。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   例如：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- 可以變更 Azure Key Vault 自身許可權的 **主要 vault 參與者**。 您必須在員工離職或加入您的小組時，變更這些許可權。 在極少數的情況下，主要 vault 管理員合法需要刪除或還原機碼的許可權，您也需要變更許可權。 這組重要的 vault 投稿人員必須授與主要 vault 上的 **投稿** 人角色。 您可以使用 Azure 資源管理員指派此角色。 如需詳細步驟，請參閱 [Use Role-Based Access Control，以管理您的 Azure 訂閱資源的存取權](/azure/active-directory/role-based-access-control-configure)。 建立訂閱的系統管理員會隱含此存取權，以及將其他管理員指派給參與者角色的能力。

- **Microsoft 365 應用程式的許可權**，以供客戶金鑰使用之每個主要保管區，您必須授與對應 Microsoft 365 服務主體的 wrapKey、unwrapKey 和 get 許可權。 

若要授與 Microsoft 365 服務主體的許可權，請使用下列語法執行 **AzKeyVaultAccessPolicy** Cmdlet：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   其中：

   - *保存庫名稱* 是您建立的主要 vault 名稱。
   - 若為 Exchange Online 和商務用 Skype，請將 *Office 365 appID* 取代為`00000002-0000-0ff1-ce00-000000000000`
   - 如需 SharePoint 線上、商務用 OneDrive 及 Teams 檔案，請將 *Office 365 appID* 取代為`00000003-0000-0ff1-ce00-000000000000`
   - 針對多工作負載原則 (Exchange、Teams、MIP EDM) 適用于所有租使用者的使用者，請將 *Office 365 appID* 取代為`c066d759-24ae-40e7-a56f-027002b5d3e4`

  範例：設定 Exchange Online 和商務用 Skype 的許可權：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  範例：設定 SharePoint 線上、商務用 OneDrive 及 Teams 檔案的許可權：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a>確定重要電子倉庫已啟用 soft delete

當您可以快速復原金鑰時，由於意外或惡意刪除的金鑰，您很可能會因意外或惡意刪除的金鑰而經歷長時間的服務中斷。 啟用此設定（稱為「虛刪除」），才能搭配客戶機碼使用金鑰。 啟用 [虛刪除] 可讓您在刪除90天內復原金鑰或存放庫，而不需要從備份中還原。
  
若要在金鑰保存庫上啟用虛刪除，請完成下列步驟：
  
1. 使用 Windows PowerShell 登入您的 Azure 訂閱。 如需相關指示，請參閱[使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。

2. 執行 [AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) Cmdlet。 在此範例中， *vault 名稱* 是您要啟用 soft delete 之主要 vault 的名稱：

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

有兩種方法可以將機碼新增到 Azure Key Vault;您可以直接在 Key Vault 中建立金鑰，也可以匯入金鑰。 直接在 Key Vault 中建立金鑰會變得更複雜，但匯入金鑰可讓您控制如何產生機碼的整體。 使用 RSA 機碼。 Azure 金鑰 Vault 不支援使用橢圓曲線鍵進行換行及解換。
  
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
Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

若要將機碼直接匯入到金鑰保存庫，您必須具有 nCipher nShield 硬體安全性模組。
  
有些組織喜歡使用此方法來建立其機碼的 provenance，然後此方法也會提供下列 attestations：
  
- 用於匯入的工具組包括 nCipher 的證明，金鑰 Exchange 金鑰 (KEK) 用來加密您所產生的金鑰無法匯出，而且會在 nCipher 所生產的正版 HSM 內產生。

- 工具組包含從 nCipher 證明，Azure 金鑰 Vault 安全性世界也會在 nCipher 所生產的正版 HSM 上產生。 此認證證明 Microsoft 也在使用正版 nCipher 硬體。

請與您的安全性群組核實，以判斷是否需要上述 attestations。 如需建立主要內部部署並將其匯入金鑰保存庫的詳細步驟，請參閱 how [to 針對 Azure Key vault 產生及轉移受保護性保護的金鑰](/azure/key-vault/keys/hsm-protected-keys)。 使用 Azure 指示在每個金鑰保存庫中建立金鑰。
  
### <a name="check-the-recovery-level-of-your-keys"></a>檢查機碼的恢復層級

Microsoft 365 要求 Azure Key Vault 訂閱設定為 [請勿取消]，且客戶機碼使用的金鑰已啟用 [虛刪除]。 您可以查看您機碼上的復原層級，以確認訂閱設定。
  
若要檢查機碼的復原層級，請在 Azure PowerShell 中執行 Get-AzKeyVaultKey Cmdlet，如下所示：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

若 _Recovery Level_ 屬性傳回的值不是 [可復原 **+ ProtectedSubscription**] 的值，請確定您已將訂閱置於 [不取消取消] 清單中，而且您已在每個金鑰存放庫上啟用虛刪除。
  
### <a name="back-up-azure-key-vault"></a>備份 Azure Key Vault

立即建立或變更索引鍵，執行備份及儲存備份的備份，不論是線上還是離線。 不要將離線副本連線到任何網路。 請改為將它們儲存在離線位置，例如在實體安全或商務儲存設施中。 至少應有一個備份副本儲存在發生嚴重損壞時可存取的位置。 備份 blob 是一種還原重要材料的唯一方法，應永久銷毀主要 Vault 金鑰，否則無法使用。 Azure Key Vault 外部的金鑰和匯入到 Azure Key Vault 的金鑰不會做為備份，因為客戶金鑰使用金鑰所需的中繼資料並不存在於外部金鑰。 只有從 Azure 金鑰保存庫取得的備份可用於使用客戶金鑰進行還原作業。 因此，您必須在上傳或建立金鑰之後，建立 Azure 金鑰 Vault 的備份。
  
若要建立 Azure Key Vault 機碼的備份，請執行 [AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) Cmdlet，如下所示：

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

確定您的輸出檔案使用尾碼 `.backup` 。
  
由此 Cmdlet 所產生的輸出檔已加密，且無法用於 Azure Key Vault 之外。 備份只能還原至執行備份的來源 Azure 訂閱。
  
> [!TIP]
> 針對輸出檔，選擇您的保存庫名稱和機碼名稱的組合。 這會使檔案名自我描述。 它也會確定備份檔案名稱不會發生衝突。
  
例如：
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -OutputFile Contoso-CK-EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>驗證 Azure 金鑰 Vault 設定設定

使用 DEP 中的金鑰之前進行驗證是選用的，但是強烈建議您這麼做。 如果您使用步驟來設定您的金鑰和電子倉庫（本文所述除外），請先驗證 Azure 金鑰 Vault 資源的健康情況，再設定客戶金鑰。
  
若要確認您的金鑰具有 `get` 、 `wrapKey` 和 `unwrapKey` 作業已啟用：
  
執行 [AzKeyVault 指令程式](/powershell/module/az.keyvault/get-azkeyvault) ，如下所示：
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

在 [輸出] 中，視需要尋找存取原則及 Exchange Online 身分識別 (guid) 或 SharePoint Online 身分識別 (guid) 。 上述所有三個許可權都必須顯示在 [索引鍵的許可權] 底下。
  
如果存取原則設定不正確，請執行 Set-AzKeyVaultAccessPolicy Cmdlet，如下所示：
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

例如，針對 Exchange Online 和商務用 Skype：
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

例如，對於線上 SharePoint 和商務用 OneDrive：
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

若要確認您的機碼未設定到期日，請執行 [AzKeyVaultKey 指令程式](/powershell/module/az.keyvault/get-azkeyvault) ，如下所示：
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

客戶金鑰不能使用到期金鑰。 使用到期金鑰所嘗試的作業會失敗，而且可能會造成服務中斷。 強烈建議使用與客戶金鑰搭配使用的金鑰沒有到期日。 到期日一經設定，便無法移除，但可以變更為不同的日期。 如果必須使用具有到期日期設定的金鑰，請將 [到期] 值變更為12/31/9999。 到期日期設定為12/31/9999 以外的日期，將不會通過 Microsoft 365 驗證。
  
若要變更已設定為12/31/9999 以外任何值的到期日，請執行 AzKeyVaultKey 指令 [程式](/powershell/module/az.keyvault/update-azkeyvaultkey) ，如下所示：
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 請勿設定與客戶金鑰搭配使用的加密金鑰上的到期日期。
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>取得每個 Azure 金鑰保存庫機碼的 URI

在您設定好金鑰保存庫並新增金鑰之後，請執行下列命令，以取得每個金鑰保存庫中的金鑰 URI。 當您稍後建立並指派每個 DEP 時，您將會使用這些 URIs，因此請將此資訊儲存在安全的位置。 請對每個金鑰保存庫執行一次此命令。
  
在 Azure PowerShell 中：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a>後續步驟

完成本文中的步驟之後，即可建立及指派 DEPs。 如需相關指示，請參閱 [管理客戶金鑰](customer-key-manage.md)。

## <a name="related-articles"></a>相關文章

- [客戶金鑰服務加密](customer-key-overview.md)

- [管理客戶金鑰](customer-key-manage.md)

- [滾動或旋轉客戶金鑰或可用性金鑰](customer-key-availability-key-roll.md)

- [深入瞭解可用性金鑰](customer-key-availability-key-understand.md)

- [服務加密](office-365-service-encryption.md)