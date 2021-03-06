---
title: 滾動或旋轉客戶金鑰或可用性金鑰
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
description: 瞭解如何在與客戶金鑰搭配使用的 Azure Key Vault 中，進行儲存的客戶根機碼的匯總。 服務包括 Exchange Online、商務用 Skype、SharePoint 線上、商務用 OneDrive 及 Teams 檔案。
ms.openlocfilehash: 892d77959bec1fb33b0ea6bcfaa8c530dd9b8911
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345115"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>滾動或旋轉客戶金鑰或可用性金鑰

> [!CAUTION]
> 當您的安全性或規範需求規定必須擲上金鑰時，請只擲出您搭配客戶金鑰使用的加密金鑰。 此外，請勿刪除任何或與原則相關聯的機碼。 當您翻轉機碼時，會使用先前的金鑰來加密內容。 例如，當作用中的信箱經常會以先前的金鑰加密，而非使用中的信箱或已停用的信箱仍會進行加密。 SharePoint線上會執行內容的備份，以進行還原及復原，所以可能仍然有已封存的內容使用舊的金鑰。

## <a name="about-rolling-the-availability-key"></a>關於滾動可用性機碼

Microsoft 不會公開對客戶可用性機碼的直接控制權。 例如，您只能 (旋轉) 您在 Azure Key Vault 中擁有的金鑰。 Microsoft 365 會以內部定義的排程來擲出可用性機碼。 這些金鑰擲出的服務層級協定 (SLA) 不具用戶端。 Microsoft 365 在自動化的非手動程式中使用 Microsoft 365 服務程式代碼來旋轉可用性金鑰。 Microsoft 系統管理員可能會開機磁碟區流程。 該鍵是使用自動化機制來擲下，不需直接存取機碼存放區。 未將存取可用性金鑰機密存放區提供給 Microsoft 系統管理員。 可用性金鑰滾動利用與最初產生機碼時所用的相同機制。 如需可用性機碼的相關資訊，請參閱 [瞭解可用性金鑰](customer-key-availability-key-understand.md)。

> [!IMPORTANT]
> 建立新的 dep 時，客戶可以有效地展開 Exchange Online 和商務用 Skype 可用性機碼，因為為您建立的每個 DEP 產生唯一的可用性金鑰。 SharePoint 線上、商務用 OneDrive 和 Teams 檔案的可用性機碼都存在於樹系層級，而且會在 DEPs 和客戶之間共用，這表示只會在 Microsoft 內部定義的排程上進行滾動。 若要降低每次建立新的 dep 時不會擲出可用性機碼的風險，請 SharePoint、OneDrive 及 Teams 滾租使用者中間機碼 (TIK) ，每次建立新的 dep 時，都會依客戶根金鑰和可用性機碼包裝的金鑰。

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>針對您要進行第一次的現有根機碼要求新版本

當您滾機碼時，會要求新版本的現有金鑰。 若要要求新版本的現有機碼，您可以使用相同的指令 [程式 AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)，其語法與您在第一個位置建立金鑰時所用的語法相同。 在您完成所有與資料加密原則相關聯的按鍵 (DEP) 後，您就可以執行另一個 Cmdlet，以確保客戶機碼開始使用新金鑰。 在每個 Azure Key Vault (AKV) 中執行此步驟。

例如：

1. 使用 Azure PowerShell 登入您的 Azure 訂閱。 如需相關指示，請參閱[使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。

2. 如下列範例所示，執行 Add-AzKeyVaultKey Cmdlet：

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   在此範例中，由於 **contoso-CK-** CK-NA-Na-VaultA1 vault 中已存在名為 **contoso-na-na** 的金鑰，所以 Cmdlet 會建立新版本的金鑰。 此作業會在金鑰的版本歷程記錄中保留舊的金鑰版本。 您需要舊的金鑰版本來解密仍加密的資料。 當您完成所有與 DEP 相關的按鍵之後，請執行額外的指令程式，以確保客戶機碼開始使用新金鑰。 下列各節將更詳細地說明 Cmdlet。
  
## <a name="update-the-keys-for-multi-workload-deps"></a>更新多工作負載 DEPs 的機碼

當您滾出與多個工作負載搭配使用的 DEP 相關聯的其中一個 Azure 金鑰保存庫金鑰時，必須更新 DEP 以指向新的機碼。 此處理程式不會旋轉可用性金鑰。

若要指示客戶金鑰使用新金鑰來加密多個工作負載，請完成下列步驟：

1. 在您的本機電腦上，使用組織中具有全域系統管理員或合規性系統管理員許可權的工作或學校帳戶，連接至 Windows PowerShell 視窗中的[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 。

2. 執行 Set-M365DataAtRestEncryptionPolicy Cmdlet。
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

其中 *PolicyName* 是原則的名稱或唯一識別碼。 例如，Contoso_Global。

範例：

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a>更新 Exchange Online DEPs 的機碼

當您滾出與 Exchange Online 和商務用 Skype 使用之 DEP 相關聯的其中一個 Azure 金鑰保存庫金鑰時，必須更新 DEP 以指向新的機碼。 這不會旋轉可用性機碼。

若要指示客戶金鑰使用新金鑰來加密信箱，請執行 Set-DataEncryptionPolicy Cmdlet，如下所示：

1. 在 Azure PowerShell 中執行 Set-DataEncryptionPolicy Cmdlet：
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. 若要檢查信箱的 DataEncryptionPolicyID 屬性值，請使用 [決定指派給信箱的 DEP](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)中的步驟。 此屬性的值會隨著服務套用更新的金鑰而變更。
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>更新 SharePoint 線上、商務用 OneDrive 及 Teams 檔的機碼

SharePoint[僅限線上] 可讓您一次滾一個機碼。 如果您想要在 key vault 中同時執行這兩個按鍵，請等候第一個作業完成。 Microsoft 建議您交錯作業，以避免發生此問題。 當您滾出與 SharePoint Online 和商務用 OneDrive 使用之 DEP 相關聯的其中一個 Azure 金鑰保存庫金鑰時，必須更新 DEP 以指向新的機碼。 這不會旋轉可用性機碼。

1. 依下列方式執行 Update-SPODataEncryptionPolicy Cmdlet：
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   雖然此 Cmdlet 會為線上及商務用 OneDrive 的 SharePoint 啟動金鑰執行，但動作不會立即完成。

2. 若要查看主要卷序作業的進度，請執行 Get-SPODataEncryptionPolicy Cmdlet，如下所示：

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>相關文章

- [Office 365 的客戶機碼服務加密](customer-key-overview.md)

- [設定 Office 365 客戶金鑰](customer-key-set-up.md)

- [管理 Office 365 客戶金鑰](customer-key-manage.md)

- [深入瞭解可用性金鑰](customer-key-availability-key-understand.md)