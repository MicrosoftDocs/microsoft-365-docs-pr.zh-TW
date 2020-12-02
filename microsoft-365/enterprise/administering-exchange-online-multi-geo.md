---
title: 管理多地理位置環境中的 Exchange Online 信箱
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: 瞭解如何使用 PowerShell 在您的 Microsoft 365 環境中管理 Exchange Online 多地理位置設定。
ms.openlocfilehash: 63eb1957611fd57e216012435188a6ddd1b232d3
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552004"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>管理多地理位置環境中的 Exchange Online 信箱

Exchange Online PowerShell 是在您的 Microsoft 365 環境中查看及設定多地理屬性所需的。 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

您需要 [Microsoft Azure Active Directory PowerShell 模組](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) 1.1.166.0 版或使用 1.x 版的更新版本，才能查看使用者物件上的 **PreferredDataLocation** 屬性。 透過 AAD Connect 同步處理至 AAD 的使用者物件，您無法經由 AAD PowerShell 直接修改其 **PreferredDataLocation** 值。 您可以透過 AAD PowerShell 修改僅雲端的使用者物件。 若要連線到 Azure AD PowerShell，請參閱[連線至 PowerShell](connect-to-microsoft-365-powershell.md)。

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>使用 Exchange Online PowerShell 直接連線到地理位置

一般而言，Exchange Online PowerShell 將連線到中央地理位置。 不過，您也可以直接連線到衛星地理位置。 由於效能改善，當您僅管理該位置中的使用者時，建議您直接連線到衛星地理位置。

安裝和使用 EXO V2 模組的需求，請參閱 [安裝及維護 EXO V2 模組](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。

若要將 Exchange Online PowerShell 連線到特定地理位置， *ConnectionUri* 參數與一般連線指示不同。 其餘命令和值則是相同的。

具體說來，您必須將此 `?email=<emailaddress>` 值新增至 _ConnectionUri_ 值的結尾。 `<emailaddress>` 是目標地理位置中 **任何** 信箱的電子郵件地址。 您對該信箱的許可權或您的認證的關聯性不是因素;電子郵件地址只會告訴 Exchange Online PowerShell 要連接的地方。

Microsoft 365 或 Microsoft 365 GCC 客戶通常不需要使用 _ConnectionUri_ 參數以連線至 Exchange Online PowerShell。 不過，若要連線至特定地理位置，您必須使用 _ConnectionUri_ 參數，這樣您就可以 `?email=<emailaddress>` 在值中使用。

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a>連接至 Exchange Online 中的地理位置 PowerShell

下列連線指示適用于已設定或未針對多重要素驗證 (MFA) 進行的帳戶。

1. 在 Windows PowerShell 視窗中，執行下列命令來載入 EXO V2 模組：

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. 在下列範例中，admin@contoso.onmicrosoft.com 是系統管理員帳戶，而目標地理位置是信箱 olga@contoso.onmicrosoft.com 所在的位置。

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. 在出現的提示中輸入 admin@contoso.onmicrosoft.com 的密碼。 如果為 MFA 設定帳戶，您也需要輸入安全性代碼。

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>檢視您的 Exchange Online 組織中設定的可用地理位置

若要查看 Microsoft 365 多地理位置中設定的地理位置清單，請在 Exchange Online PowerShell 中執行下列命令：

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>檢視您的 Exchange Online 組織的中央地理位置

若要檢視您的租用戶的中央地理位置，請在 Exchange Online PowerShell 中執行下列命令：

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>尋找信箱的地理位置

Exchange Online PowerShell 中的 **Get-Mailbox** Cmdlet 會顯示信箱上的下列多地理位置相關屬性：

- **資料庫**：與地理位置代碼對應的資料庫名稱前 3 個字母，它會告知您信箱目前所在的位置。 若為線上封存信箱，則應該使用 **ArchiveDatabase** 屬性。

- **MailboxRegion**：指定系統管理員所設定的地理位置代碼 (從 Azure AD 中的 **PreferredDataLocation** 同步處理)。

- **MailboxRegionLastUpdateTime**：指出 MailboxRegion 的上次更新時間 (自動或手動)。

若要查看信箱的這些屬性，請使用下列語法：

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

例如，若要查看信箱 chris@contoso.onmicrosoft.com 的地理位置資訊，請執行下列命令：

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

此命令的輸出看起來像這樣：

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> 如果資料庫名稱中的地理位置代碼不符合 **MailboxRegion** 值，則信箱將會自動放入重新置放佇列中，並移至 **MailboxRegion** 值所指定的地理位置。 (Exchange Online 會在這些屬性值) 之間尋找不相符。

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>將現有僅雲端信箱移動至特定的地理位置

僅限雲端使用者是未透過 AAD Connect 同步處理至租用戶的使用者。 此使用者是直接在 Azure AD 中建立。 使用適用於 Windows PowerShell 的 Azure AD 模組中的 **Get-MsolUser** 和 **Set-MsolUser** Cmdlet 來檢視或指定將儲存僅雲端使用者信箱的地理位置。

若要檢視使用者的 **PreferredDataLocation** 值，請在 Azure AD PowerShell 中使用此語法：

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

例如，若要查看使用者 michelle@contoso.onmicrosoft.com 的 **PreferredDataLocation** 值，請執行下列命令：

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

若要修改僅雲端使用者物件的 **PreferredDataLocation** 值，請在 Azure AD PowerShell 中使用下列語法：

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

例如，若要將使用者 michelle@contoso.onmicrosoft.com 的 **PreferredDataLocation** 值設定為歐盟 (EUR) 地理位置，請執行下列命令：

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - 如先前所述，您無法對內部部署 Active Directory 的同步處理使用者物件使用此程式。 您必須變更 Active Directory 中的 **PreferredDataLocation** 值，並使用 AAD Connect 將它同步處理。 如需詳細資訊，請參閱 [Azure Active Directory Connect 同步處理：設定 Microsoft 365 資源的慣用資料位置](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)。
>
> - 將信箱重新定位到新的地理位置所需的時間取決於數個因素：
>
>   - 信箱的大小和類型。
>   - 要移動的信箱數量。
>   - 移動資源的可用性。

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a>將非使用中的信箱移至特定地理位置

您無法移動出於相容性目的所保留的非使用中信箱 (例如，使用訴訟暫止) 中的信箱變更其 **PreferredDataLocation** 值。 若要將非使用中的信箱移至不同的地理位置，請執行下列步驟：

1. 復原非使用中的信箱。 如需相關指示，請參閱 [復原非使用中的信箱](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)。

2. 以信箱的名稱、別名、帳戶或電子郵件地址取代，以防止受管理的資料夾助理處理復原的信箱， \<MailboxIdentity\> 並在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中執行下列命令：

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. 將 **Exchange Online Plan 2** 授權指派給復原的信箱。 您必須執行此步驟，才能將信箱還原為訴訟暫止狀態。 如需相關指示，請參閱 [將授權指派給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

4. 如前一節所述，在信箱上設定 **PreferredDataLocation** 值。

5. 在您確認信箱已經移至新的地理位置之後，請將復原的信箱回復回訴訟暫止狀態。 如需相關指示，請參閱 [將信箱設為訴訟暫止狀態](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold)。

6. 確認訴訟暫止已到位之後，讓受管理的資料夾助理以 \<MailboxIdentity\> 信箱的名稱、別名、帳戶或電子郵件地址取代，並在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中執行下列命令，以再次處理信箱：

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. 移除與信箱相關聯的使用者帳戶，將信箱停用停用。 如需相關指示，請參閱 [刪除組織中的使用者](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)。 此步驟也會為其他用途發佈 Exchange Online Plan 2 授權。

**附注**：當您將非使用中的信箱移至不同的地理位置時，您可能會影響內容的搜尋結果，或從先前的地理位置搜尋該信箱的功能。 如需詳細資訊，請參閱 [在多地理位置環境中搜尋和匯出內容](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)。

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>在特定地理位置建立新的雲端信箱

若要在特定地理位置建立新的信箱，您必須執行下列其中一個步驟：

- 如先前所述，設定 **PreferredDataLocation** 值。在 Exchange Online 中建立信箱 *之前，先*[將現有的雲端信箱移至特定地理位置](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location)區段。 例如，在您指派授權之前，請先在使用者上設定 **PreferredDataLocation** 值。

- 在設定 **PreferredDataLocation** 值的同時指派授權。

若要在特定地理位置建立新的僅雲端授權使用者 (未使用 AAD Connect 同步處理)，請在 Azure AD PowerShell 中使用下列語法：

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

此範例會使用下列值為 Elizabeth Brunner 建立新的使用者帳戶：

- 使用者主體名稱：ebrunner@contoso.onmicrosoft.com
- 名字：Elizabeth
- 姓氏：Brunner
- 顯示名稱：Elizabeth Brunner
- 密碼：隨機產生並在命令的結果中顯示 (因為我們未使用 *Password* 參數)
- 授權：`contoso:ENTERPRISEPREMIUM` (E5)
- 位置：澳洲 (AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

如需建立新的使用者帳戶和在 Azure AD PowerShell 中尋找 LicenseAssignment 值的詳細資訊，請參閱[使用 PowerShell 建立使用者帳戶](create-user-accounts-with-microsoft-365-powershell.md)和[使用 PowerShell 檢視授權與服務](view-licenses-and-services-with-microsoft-365-powershell.md)。

> [!NOTE]
> 如果您使用 Exchange Online PowerShell 來啟用信箱，並且需要直接在 **PreferredDataLocation** 中指定的地理位置建立信箱，則必須直接對雲端服務使用 Exchange Online Cmdlet，例如 **Enable-Mailbox** 或 **New-Mailbox**。 如果您使用內部部署 Exchange PowerShell 中的 **Enable-RemoteMailbox** Cmdlet，則會在中央地理位置建立信箱。

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>將特定地理位置中的現有內部部署信箱上線

您可以使用標準的上線工具和程序，將信箱從內部部署 Exchange 組織移轉至 Exchange Online，包括 [EAC 中的移轉儀表板](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)，以及 Exchange Online PowerShell 中的 [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) Cmdlet。

第一個步驟是驗證要上線的每個信箱均存在使用者物件，並驗證已在 Azure AD 中設定正確的 **PreferredDataLocation** 值。 上線工具會使用 **PreferredDataLocation** 值，並將信箱直接移轉至指定的地理位置。

或者，您可以使用下列步驟，在特定地理位置直接將信箱上線，方法是在 Exchange Online PowerShell 中使用 [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) Cmdlet。

1. 驗證要上線的每個信箱均存在使用者物件，並且 Azure AD 中的 **PreferredDataLocation** 已設定為需要的值。 **PreferredDataLocation** 的值會同步處理至 Exchange Online 中對應郵件使用者物件的 **MailboxRegion** 屬性。

2. 使用稍早在本主題中的連線指示，直接連線至特定衛星地理位置。

3. 在 Exchange Online PowerShell 中，執行下列命令，將用來執行信箱移轉的內部部署系統管理員認證儲存在變數中：

   ```powershell
   $RC = Get-Credential
   ```

4. 在 Exchange Online PowerShell 中，建立新的 **New-MoveRequest**，類似以下範例：

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. 針對您要從內部部署 Exchange 移轉至您目前連線的衛星地理位置的每一個信箱重複步驟 4。

6. 如果您需要將其他信箱移轉到其他衛星地理位置，請對每個特定衛星地理位置重複步驟 2 到 4。

## <a name="multi-geo-reporting"></a>多地理位置報告

Microsoft 365 系統管理中心的 **多地理位置使用報告** 會依地理位置顯示使用者計數。 該報告會顯示目前月份的使用者分佈，並提供過去 6 個月的歷史資料。

## <a name="see-also"></a>另請參閱

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
