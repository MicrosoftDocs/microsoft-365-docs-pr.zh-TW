---
title: 使用 PowerShell 以網際網路訊息存取通訊設定移轉至 Microsoft 365
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
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: 瞭解如何使用 PowerShell 來執行網際網路郵件存取通訊協定 (IMAP) 遷移至 Microsoft 365。
ms.openlocfilehash: fbfc0340e80ce70aa8a706d89a4d27729b91535b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924765"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>使用 PowerShell 以網際網路訊息存取通訊設定移轉至 Microsoft 365

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

在部署 Microsoft 365 的過程中，您可以選擇將使用者信箱的內容從網際網路郵件存取通訊協定（ (IMAP) 電子郵件服務）遷移到 Microsoft 365。 本文會引導您使用 Exchange Online PowerShell 來進行電子郵件 IMAP 移轉的工作。 
  
> [!NOTE]
> 您也可以使用 Exchange 系統管理中心來執行 IMAP 移轉。 請參閱 [遷移 IMAP 信箱](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes)。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

完成此工作的預估時間：2-5 分鐘來建立遷移批次。 啟動移轉批次之後，移轉所需的時間會依批次中的信箱數目、每個信箱的大小和可用的網路容量而有所不同。 如需其他影響將信箱遷移至 Microsoft 365 的因素的詳細資訊，請參閱 [遷移效能](/Exchange/mailbox-migration/office-365-migration-best-practices)。
  
您必須已獲指派的權限，才能執行此程序。若要查看您需要哪些權限，請參閱[收件者權限](/exchange/recipients-permissions-exchange-2013-help)主題中所含表格的「移轉」項目。
  
若要使用 Exchange Online PowerShell Cmdlet，您需要登入系統，並將 Cmdlet 匯入您的本機 Windows PowerShell 工作階段。請參閱[使用遠端 PowerShell 連線到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) 的指示。
  
若需要移轉命令的完整清單，請參閱[移動與移轉 Cmdlet](/powershell/exchange/)。
  
下列限制適用於 IMAP 移轉：
  
- 僅能移轉使用者收件匣或其他郵件資料夾中的項目。您無法移轉連絡人、行事曆項目或工作。
    
- 最多只能從使用者信箱移轉 500,000 個項目。
    
- 可移轉的郵件大小上限為 35 MB。
    
## <a name="migration-steps"></a>移轉步驟

### <a name="step-1-prepare-for-an-imap-migration"></a>步驟 1：準備進行 IMAP 移轉
<a name="BK_Step1"> </a>

- **如果您有 IMAP 組織的網域，請將其新增為 Microsoft 365 組織的公認網域。** 如果您想要使用您的 Microsoft 365 信箱已經擁有的相同網域，您必須先將其新增為 Microsoft 365 的公認網域。 新增後，您可以在 Microsoft 365 中建立使用者。 如需詳細資訊，請參閱[驗證您的網域](../admin/setup/add-domain.md)。
    
- **將每位使用者新增至 Microsoft 365，讓他們擁有信箱。** 如需相關指示，請參閱[將使用者新增至 Microsoft 365 for business](../admin/add-users/add-users.md)。
    
- **取得 IMAP 伺服器的 FQDN**。您必須提供 IMAP 伺服器的完整網域名稱 (FQDN) (也稱為「完整電腦名稱」)，當您建立 IMAP 移轉端點時，將會從此伺服器移轉信箱資料。使用 IMAP 用戶端或 PING 命令，確認是否可以使用 FQDN，透過網際網路與 IMAP 伺服器通訊。
    
- **設定防火牆來允許 IMAP 連線**。您可能必須開啟主控 IMAP 伺服器之組織的防火牆中的通訊埠，以便允許移轉期間源自 Microsoft 資料中心的網路流量進入主控 IMAP 伺服器的組織。如需 Microsoft 資料中心所使用的 IP 位址清單，請參閱 [Office 365 URL 與 IP 位址範圍](./urls-and-ip-address-ranges.md)。
    
- **指派系統管理員帳戶權限來存取 IMAP 組織中的信箱**。如果您在 CSV 檔案中使用系統管理員認證，您所使用的帳戶必須具有能存取內部部署信箱的必要權限。存取使用者信箱所需的權限是由特定的 IMAP 伺服器決定。 
    
- **若要使用 Exchange Online PowerShell Cmdlet**，您需要登入系統，並將 Cmdlet 匯入您的本機 Windows PowerShell 工作階段。請參閱 [使用遠端 PowerShell 連線到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) 的指示。
    
    若需要移轉命令的完整清單，請參閱[移動與移轉 Cmdlet](/powershell/exchange/)。
    
- **確認您可以連線至 IMAP 伺服器**。在 Exchange Online PowerShell 中執行下列命令，測試 IMAP 伺服器的連線設定。
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    對於 **Port** 參數的值，通常是使用 143 來進行未加密或傳輸層安全性 (TLS) 連線，以及使用 993 來進行 SSL 連線。
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>步驟 2：建立 CSV 檔案供 IMAP 移轉批次使用
<a name="BK_Step2"> </a>

識別您想要在 IMAP 移轉批次中移轉其信箱的使用者群組。CSV 檔案中的每一列包含連線至 IMAP 郵件系統中的信箱所需的資訊。
  
以下是供每個使用者使用的必要屬性。 
  
- **EmailAddress** 會指定使用者的 Microsoft 365 信箱的使用者識別碼。
    
- **UserName** 會指定帳戶在存取 IMAP 伺服器上的信箱時所使用的登入名稱。
    
- **Password** 會指定 **UserName** 欄中之帳戶的密碼。
    
以下是 CSV 檔案的格式範例：在此範例中，會移轉三個信箱：
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

若是 **UserName** 屬性，除了使用者名稱，您還可以使用已指派必要權限的帳戶認證來存取 IMAP 伺服器上的信箱，以下是一些 IMAP 伺服器使用的特定格式：
  
 **Microsoft Exchange：**
  
如果您要從 Microsoft Exchange 的 IMAP 實作中移轉電子郵件，請針對 CSV 檔案中的 **UserName** 屬性使用 **Domain/Admin_UserName/User_UserName** 格式。 假設您要從 Exchange 移轉 Terry Adams、Ann Beebe 及 Paul Cannon 的電子郵件。 您有郵件系統管理員帳戶，其中使用者名稱是 **mailadmin** ，密碼是 **P \@ ssw0rd**。 以下是您 CSV 檔的外觀：
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot：**
  
若為支援簡單驗證及安全性階層 (SASL) 的 IMAP 伺服器 (例如 Dovecot IMAP 伺服器)，請使用 **User_UserName*Admin_UserName** 格式，其中星號 (*) 是可設定的分隔字元。 假設您要使用系統管理員認證 **mailadmin** 和 **P \@ SSW0RD**，從 Dovecot IMAP 伺服器遷移這些相同使用者的電子郵件。 以下是您 CSV 檔的外觀：
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint：**
  
如果您要從 Mirapoint 郵件伺服器遷移電子郵件，請使用 format **#user \@ domain # Admin_UserName #** 以取得系統管理員認證。 若要使用系統管理員認證 **mailadmin** 和 **P \@ ssw0rd** 從 Mirapoint 遷移電子郵件，您的 CSV 檔如下所示：
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier-IMAP：**
  
有些來源電子郵件系統（例如「宋體」）不支援使用信箱系統管理員認證，將信箱遷移至 Microsoft 365。 相反地，您可以設定來源電子郵件系統來使用虛擬共用資料夾。 藉由使用虛擬共用資料夾，您可以使用信箱管理員認證來存取來源電子郵件系統上的使用者信箱。 如需如何設定適用於 Courier IMAP 的虛擬共用資料夾的詳細資訊，請參閱[共用資料夾](https://go.microsoft.com/fwlink/p/?LinkId=398870)。
  
若要在來源電子郵件系統上設定虛擬共用資料夾之後移轉信箱，您必須在移轉檔案中加入選擇性屬性 **UserRoot** 。此屬性會指定每個使用者信箱在來源電子郵件系統之虛擬共用資料夾結構中的位置。例如，前往 Terry 信箱的路徑是 /users/terry.adams。
  
以下是包含 **UserRoot** 屬性之 CSV 檔案的範例：
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>步驟 3：建立 IMAP 移轉端點
<a name="BK_Step3"> </a>

若要成功遷移電子郵件，Microsoft 365 必須連線到來源電子郵件系統，並與其通訊。 若要這樣做，Microsoft 365 會使用遷移端點。 移轉端點也會定義要同時移轉的信箱數目，以及要在每 24 小時執行一次的增量同步處理期間同時同步處理的信箱數目。 若要建立 IMAP 移轉的移轉端點，請先[連線至 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。 
  
若需要移轉命令的完整清單，請參閱[移動與移轉 Cmdlet](/powershell/exchange/)。
  
若要在 Exchange Online PowerShell 中建立名為 "IMAPEndpoint" 的 IMAP 移轉端點，請執行下列命令：
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

您也可以新增參數來指定同時移轉、同時增量移轉和要使用的通訊埠。下列 Exchange Online PowerShell 命令會建立名為 "IMAPEndpoint" 的 IMAP 移轉端點，該端點支援 50 件同時移轉，以及最多 25 件同時增量同步處理。它也會將端點設定為使用通訊埠 143 來進行 TLS 加密。
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

如需 **New-MigrationEndpoint** Cmdlet 的詳細資訊，請參閱 [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)。
  
#### <a name="verify-it-worked"></a>確認是否正常運作

在 Exchange Online PowerShell 中執行下列命令來顯示 "IMAPEndpoint" 的資訊：
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>步驟 4：建立並啟動 IMAP 移轉批次
<a name="BK_Step4"> </a>

您可以使用 [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) Cmdlet 來建立 IMAP 移轉的移轉批次。您可以建立移轉批次，並加上 _AutoStart_ 參數來自動啟動它。或者，您可以建立移轉批次，之後再使用 [Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch) Cmdlet 來啟動該批次。
  
下列 Exchange Online PowerShell 命令將會使用名為 "IMAPEndpoint" 的 IMAP 端點自動啟動名為 "IMAPBatch1" 的移轉批次：
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>確認是否正常運作

執行 [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) Cmdlet 來顯示 "IMAPBatch1" 的資訊：
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

您也可以執行下列命令來確認批次已啟動：
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>步驟5：將電子郵件路由傳送至 Microsoft 365
<a name="BK_Step5"> </a>

電子郵件系統使用稱為 MX 記錄的 DNS 記錄來找出要將電子郵件傳遞到哪裡。 在電子郵件移轉過程中，您的 MX 記錄指向來源電子郵件系統。 現在，已完成將電子郵件遷移至 Microsoft 365，您可以將您的 MX 記錄指向 Microsoft 365。 這可協助確定電子郵件已傳遞至您的 Microsoft 365 信箱。 藉由移動 MX 記錄，您也可以在準備好時關閉舊的電子郵件系統。 
  
我們針對許多 DNS 提供者提供變更 MX 記錄的特定指示。 如果您的 DNS 提供者不在其中，或如果您想要了解一般指示，我們也提供[在任一 DNS 主機服務提供者建立 Office 365 的 DNS 記錄](https://go.microsoft.com/fwlink/?LinkId=397449)。
  
您的客戶與合作夥伴的電子郵件系統最多可能需要 72 小時才能辨識已變更的 MX 記錄。請至少等待 72 小時，再繼續進行下一個工作：步驟 6：刪除 IMAP 移轉批次。 
  
### <a name="step-6-delete-imap-migration-batch"></a>步驟 6：刪除 IMAP 移轉批次
<a name="BK_Step6"> </a>

在您變更 MX 記錄，並確認所有電子郵件都會路由傳送至 Microsoft 365 信箱之後，請通知使用者他們的郵件即將移至 Microsoft 365。 在此之後，您便可以刪除 IMAP 移轉批次。 在刪除移轉批次之前，請先確認下列事項。
  
- 所有使用者都使用 Microsoft 365 信箱。 刪除批次之後，傳送至內部部署 Exchange 伺服器上之信箱的郵件不會複製到對應的 Microsoft 365 信箱。
    
- 當郵件開始直接傳送給他們之後，Microsoft 365 信箱會至少同步處理一次。 若要這麼做，請確定遷移批次的 [上次同步處理時間] 方塊中的值比直接路由傳送至 Microsoft 365 信箱的時間晚。
    
若要在 Exchange Online PowerShell 中刪除 "IMAPBatch1" 移轉批次，請執行下列命令：
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

如需 **Remove-MigrationBatch** Cmdlet 的詳細資訊，請參閱 [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch)。
  
#### <a name="verify-it-worked"></a>確認是否正常運作

在 Exchange Online PowerShell 中執行下列命令來顯示 "IMAPBatch1" 的資訊：
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

此命令會傳回狀態為 **Removing** 的移轉批次，或傳回錯誤，指出找不到移轉批次而需確認該批次是否已刪除。
  
如需 **Get-MigrationBatch** Cmdlet 的詳細資訊，請參閱 [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)。
  
## <a name="see-also"></a>另請參閱

[IMAP 移轉疑難排解員](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)