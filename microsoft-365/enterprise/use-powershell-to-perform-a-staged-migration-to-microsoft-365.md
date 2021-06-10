---
title: 使用 PowerShell 以階段移轉至 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: 瞭解如何使用 PowerShell，隨著時間使用分段遷移將內容移 Microsoft 365 至來源電子郵件系統。
ms.openlocfilehash: 0c93de181c54fb1c4021d23d787b63577317aad4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924789"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>使用 PowerShell 以階段移轉至 Microsoft 365

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

您可以使用分段遷移，將使用者信箱的內容從來源電子郵件系統移轉至 Microsoft 365 一段時間。
  
本文將引導您完成使用 Exchange Online PowerShell 進行分段電子郵件遷移所涉及的工作。 主題是 [分步電子郵件遷移所需注意的事項](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration)，可讓您瞭解遷移程式。 在熟悉該文章的內容後，請使用此主題來開始在不同電子郵件系統中移轉信箱。
  
> [!NOTE]
> 您也可以使用 Exchange 系統管理中心來執行分段移轉。 請參閱[執行將電子郵件分段遷移至 Microsoft 365](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration)。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

完成此工作的預估時間：2-5 分鐘來建立遷移批次。 啟動移轉批次之後，移轉所需的時間會依批次中的信箱數目、每個信箱的大小和可用的網路容量而有所不同。 如需其他影響將信箱遷移至 Microsoft 365 所需時間的因素的詳細資訊，請參閱[遷移效能](/Exchange/mailbox-migration/office-365-migration-best-practices)。
  
您必須已獲指派的權限，才能執行此程序。若要查看您需要哪些權限，請參閱[收件者權限](/exchange/recipients-permissions-exchange-2013-help)主題中的「移轉」項目。
  
若要使用 Exchange Online PowerShell Cmdlet，您需要登入系統，並將 Cmdlet 匯入您的本機 Windows PowerShell 工作階段。請參閱[使用遠端 PowerShell 連線到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) 的指示。
  
若需要移轉命令的完整清單，請參閱[移動與移轉 Cmdlet](/powershell/exchange/)。
  
## <a name="migration-steps"></a>移轉步驟

### <a name="step-1-prepare-for-a-staged-migration"></a>步驟 1：準備分段移轉

使用分段遷移將信箱遷移至 Microsoft 365 之前，您必須對 Exchange 環境進行一些變更。
  
 在您的內部部署 Exchange Server 上 **設定** Outlook 無所不在 電子郵件移轉服務會使用 Outlook 無所不在 (也稱為 RPC over HTTP) 來連線至您的內部部署 Exchange Server。如需如何針對 Exchange Server 2007 和 Exchange 2003 設定 Outlook 無所不在 的資訊，請參閱下列文章：
  
- [Exchange 2007：如何啟用 Outlook 無所不在](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))
    
- [如何使用 Exchange 2003 設定 Outlook 無所不在](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))
    
> [!IMPORTANT]
> 您必須在設定 Outlook 無所不在時使用信任的憑證授權單位 (CA) 所發行的憑證。您無法使用自我簽署憑證設定 Outlook 無所不在。如需詳細資訊，請參閱[如何為 Outlook 無所不在設定 SSL](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80))。 
  
 **選擇性：確認可以使用 Outlook 無所不在** 連線至您的 Exchange 組織 嘗試使用下列其中一種方法來測試連線設定。
  
- 從公司網路之外使用 Outlook 連線至您的內部部署 Exchange 信箱。
    
- 使用 [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) 來測試您的連線設定。 使用 Outlook 無所不在 (RPC over HTTP) 或 Outlook 自動探索測試。
    
- 在 Exchange Online PowerShell 中執行下列命令：
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **設定許可權** 您用來連線至內部部署 Exchange 組織的內部部署使用者帳戶 (也稱為「遷移系統管理員) ，必須具備必要的許可權，才能存取您要遷移到 Microsoft 365 的內部部署信箱。 當您在此程序稍後建立移轉端點以連線到電子郵件系統時，將會用到此使用者帳戶 ([步驟 3：建立移轉端點](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint))。
  
若要移轉信箱，系統管理員必須具備下列其中一組權限：
  
- 屬於內部部署組織中 Active Directory 內的 **Domain Admins** 群組成員。
    
    或 
    
- 獲得每個內部部署信箱的 **FullAccess** 權限，以及用來修改內部部署使用者帳戶的 **TargetAddress** 內容的 **WriteProperty** 權限。
    
    或 
    
- 獲得儲存使用者信箱的內部部署信箱資料庫的 **Receive As** 權限，以及用來修改內部部署使用者帳戶的 **TargetAddress** 內容的 **WriteProperty** 權限。
    
如需如何設定這些許可權的指示，請參閱[指派將信箱遷移至 Microsoft 365 的許可權](/Exchange/mailbox-migration/assign-permissions-for-migration)。
  
 **停用整合通訊 (UM)** 如果您要移轉的內部部署信箱已開啟 UM，請先關閉 UM 再進行移轉。移轉完成後再開啟信箱的 UM。如需操作步驟，請參閱 [如何對使用者停用整合通訊](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80))。
  
 **使用目錄同步處理在 Microsoft 365 中建立新使用者。** 您可以使用目錄同步處理，在 Microsoft 365 組織中建立所有的內部部署使用者。
  
您必須授權已建立的使用者。您必須在建立使用者後的 30 天內增加授權。若要增加授權的步驟，請參閱[步驟 8：完成移轉後工作](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration)。
  
 您可以使用 Microsoft Azure Active Directory (Azure AD) 同步處理工具或 Microsoft Azure AD 同步服務，在 Microsoft 365 中同步處理及建立內部部署使用者。 將信箱遷移至 Microsoft 365 後，您可以在內部部署組織中管理使用者帳戶，並將其與您的 Microsoft 365 組織同步。 如需詳細資訊，請參閱[目錄整合](/previous-versions/azure/azure-services/jj573653(v=azure.100))。
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>步驟 2：建立分段移轉批次所需的 CSV 檔案

在您識別想要將其內部部署信箱遷移至 Microsoft 365 的使用者之後，您可以使用以逗號分隔的值 (CSV ) 檔案來建立遷移批次。 CSV 檔案中的每一列（由 Microsoft 365 用來執行遷移）包含內部部署信箱的相關資訊。 
  
> [!NOTE]
> 使用分段遷移時，您可以遷移至 Microsoft 365 的信箱數目不受限制。 移轉批次的 CSV 檔案最多可包含 2,000 列。 若要移轉超過 2,000 個信箱，請建立其他 CSV 檔案並使用各個檔案建立新的移轉批次。 
  
 **支援的屬性**
  
分段移轉的 CSV 檔案支援下列三個屬性。CSV 檔案中的每一列都對應至一個信箱，而且必須包含這些屬性的值。
  
|**屬性**|**描述**|**Required?**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |指定內部部署信箱的主要 SMTP 電子郵件地址，例如 pilarp@contoso.com。  <br/> 使用內部部署信箱的主要 SMTP 位址，而不是 Microsoft 365 的使用者 IDs。 例如，如果內部部署網域命名為 contoso.com，但 Microsoft 365 的電子郵件網域命名為 service.contoso.com，則會使用 CSV 檔案中的電子郵件地址的 contoso.com 功能變數名稱。  <br/> |必要  <br/> |
|密碼  <br/> |要為新 Microsoft 365 信箱設定的密碼。 適用于 Microsoft 365 組織的任何密碼限制也適用于 CSV 檔案中包含的密碼。  <br/> |選用  <br/> |
|ForceChangePassword  <br/> |指定使用者第一次登入新 Microsoft 365 信箱時，是否必須變更密碼。 使用 **True** 或 **False** 作為此參數的值。 <br/> > [!NOTE]> 如果您已在內部部署組織中部署 Active Directory Federation Services (AD FS) 或更新版本來實作單一登入 (SSO) 解決方案，則必須使用 **False** 作為 **ForceChangePassword** 屬性的值。          |選用  <br/> |
   
 **CSV 檔案格式**
  
以下是 CSV 檔案的格式範例： 在此範例中，會將三個內部部署信箱遷移至 Microsoft 365。
  
CSV 檔案的第一個資料列 (也稱為「標題列」) 會列出在後續幾列上指定的屬性或欄位名稱。每個屬性名稱都會以逗號分隔。
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

標頭列底下的每一個資料列都代表一個使用者，而且會提供移轉該使用者信箱所使用的詳細資訊。每一個資料列中屬性值的順序必須與標頭列中所列屬性名稱的順序相同。 
  
使用任何文字編輯器或 Excel 之類的應用程式來建立 CSV 檔案。將檔案儲存為 .csv 或 .txt 檔。
  
> [!NOTE]
> 如果 CSV 檔案包含非 ASCII 或特殊字元，請以 UTF-8 或其他 Unicode 編碼儲存該 CSV 檔案。依應用程式而定，當電腦的系統地區設定與 CSV 檔中所用的語言相符時，以 UTF-8 或其他 Unicode 編碼儲存 CSV 檔可能會比較容易。 
  
### <a name="step-3-create-a-migration-endpoint"></a>步驟 3：建立移轉端點
<a name="BK_Endpoint"> </a>

若要成功遷移電子郵件，Microsoft 365 必須與來源電子郵件系統連線並進行通訊。 若要這麼做，Microsoft 365 會使用遷移端點。 若要使用 PowerShell 建立 Outlook 無所不在移轉端點以進行分段移轉，請先[連線至 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。 
  
若需要移轉命令的完整清單，請參閱[移動與移轉 Cmdlet](/powershell/exchange/)。
  
若要在 Exchange Online PowerShell 中建立名為 "StagedEndpoint" 的 Outlook 無所不在移轉端點，請執行下列命令：
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

如需 **New-MigrationEndpoint** Cmdlet 的詳細資訊，請參閱 [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)。
  
> [!NOTE]
> 藉由使用 **-TargetDatabase** 選項，可以使用 **New-MigrationEndpoint** Cmdlet 來指定要使用之服務的資料庫。否則系統會從管理信箱所在的 Active Directory Federation Services (AD FS) 2.0 網站隨機指派資料庫。
  
#### <a name="verify-it-worked"></a>確認是否正常運作

在 Exchange Online PowerShell 中執行下列命令來顯示 "StagedEndpoint" 移轉端點的資訊：
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a>步驟 4：建立並啟動分段移轉批次
<a name="BK_Endpoint"> </a>

您可以在 Exchange Online PowerShell 中使用 **New-MigrationBatch** Cmdlet，為完全移轉建立移轉批次。您可以建立移轉批次，並加上 _AutoStart_ 參數來自動啟動它。或者，您也可以先建立移轉批次，以後再手動使用 **Start-MigrationBatch** Cmdlet 啟動它。本範例會建立名為 "StagedBatch1" 的移轉批次，並使用上一個步驟中建立的移轉端點。
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

本範例也會建立名為 "StagedBatch1" 的移轉批次，並使用上一個步驟中建立的移轉端點。因為其中並未加上  _AutoStart_ 參數，所以需要在移轉儀表板上或使用 **Start-MigrationBatch** Cmdlet 來手動啟動此移轉批次。如前所述，一次只能有一個完全移轉批次。
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a>確認是否正常運作

在 Exchange Online PowerShell 中執行下列命令來顯示 "StagedBatch1" 的資訊：
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

您也可以執行下列命令來確認批次已啟動：
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

如需 **Get-MigrationBatch** Cmdlet 的詳細資訊，請參閱 [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)。
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a>步驟 5：將內部部署信箱轉換成擁有郵件功能的使用者
<a name="BK_Endpoint"> </a>

成功移轉信箱批次之後，您必須有方法能讓使用者存取他們的郵件。 已遷移信箱的使用者現在同時擁有內部部署信箱和 Microsoft 365 中的信箱。 在 Microsoft 365 中擁有信箱的使用者，將會停止接收內部部署信箱中的新郵件。 
  
因為您未進行遷移，所以尚未準備好讓所有使用者都能將其電子郵件 Microsoft 365。 所以該如何處理同時擁有兩個信箱的使用者？ 您可以變更已移轉至「啟用郵件功能的使用者」的內部部署信箱。 當您從信箱變更為擁有郵件功能的使用者時，您可以指導使用者 Microsoft 365 電子郵件，而不是移至其內部部署信箱。 
  
將內部部署信箱轉換成擁有郵件功能的使用者的另一個重要原因是，將 proxy 位址複製到啟用郵件功能的使用者，以保留 Microsoft 365 信箱的 proxy 位址。 如此可讓您使用 Active Directory 從內部部署組織管理雲端使用者。 此外，如果您決定將所有信箱遷移至 Microsoft 365 之後，將您的內部部署 Exchange Server 組織解除委任，您已複製到擁有郵件功能之使用者的 proxy 位址仍會保留在您的內部部署 Active Directory 中。
    
### <a name="step-6-delete-a-staged-migration-batch"></a>步驟 6：刪除分段移轉批次
<a name="BK_Endpoint"> </a>

 將移轉批次中的所有信箱順利移轉，並將批次中的內部部署信箱轉換成擁有郵件功能的使用者後，就可以刪除分段移轉批次。 請務必確認郵件會轉寄至遷移批次中的 Microsoft 365 信箱。 當您刪除分段移轉批次時，移轉服務會清除與該移轉批次相關的所有記錄，並刪除該移轉批次。
  
若要刪除 Exchange Online PowerShell 中的 "StagedBatch1" 移轉批次，請執行下列命令。
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

如需 **Remove-MigrationBatch** Cmdlet 的詳細資訊，請參閱 [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch)。
  
#### <a name="verify-it-worked"></a>確認是否正常運作

在 Exchange Online PowerShell 中執行下列命令來顯示 "IMAPBatch1" 的資訊：
  
```powershell
Get-MigrationBatch StagedBatch1
```

此命令會傳回狀態為 **Removing** 的移轉批次，或傳回錯誤，指出找不到移轉批次而需確認該批次是否已刪除。
  
如需 **Get-MigrationBatch** Cmdlet 的詳細資訊，請參閱 [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)。
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a>Step7：將授權指派給 Microsoft 365 使用者
<a name="BK_Endpoint"> </a>

指派授權，啟用已遷移帳戶的 Microsoft 365 使用者帳戶。 如果您未指派授權，則當寬限期 (30 天) 結束時就會停用信箱。 若要在 Microsoft 365 系統管理中心中指派授權，請參閱[指派或取消指派授權](../admin/manage/assign-licenses-to-users.md)。
  
### <a name="step-8-complete-post-migration-tasks"></a>步驟 8：完成移轉後工作
<a name="BK_Postmigration"> </a>

- **建立自動探索 DNS 記錄，讓使用者可以輕鬆存取信箱。** 將所有內部部署信箱遷移至 Microsoft 365 後，您就可以設定 Microsoft 365 組織的自動探索 DNS 記錄，讓使用者能夠使用 Outlook 和行動用戶端輕鬆地連接至其新的 Microsoft 365 信箱。 這個新的自動探索 DNS 記錄必須使用您的 Microsoft 365 組織所使用的相同命名空間。 舉例來說，如果您的雲端架構命名空間是 cloud.contoso.com，則您需要建立的自動探索 DNS 記錄是 autodiscover.cloud.contoso.com。
    
    Microsoft 365 使用 CNAME 記錄來執行 Outlook 和行動用戶端的自動探索服務。 自動探索 CNAME 記錄必須包含下列資訊：
    
  - **別名：** 自動探索
    
  - **目標：** autodiscover.outlook.com
    
    如需詳細資訊，請參閱 [新增 DNS 記錄以連接您的網域](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。
    
- **解除委任內部部署 Exchange 伺服器。** 在您確認所有電子郵件都直接路由傳送至 Microsoft 365 信箱，且您不再需要維護內部部署電子郵件組織，或不計畫執行 SSO 解決方案時，您可以從伺服器卸載 Exchange，然後移除內部部署 Exchange 組織。
    
    如需詳細資訊，請參閱下列各主題：
    
  - [修改及移除 Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))
    
  - [如何移除 Exchange 2007 組織](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))
    
  - [如何解除安裝 Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))
