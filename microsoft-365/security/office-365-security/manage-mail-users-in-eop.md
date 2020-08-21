---
title: 在獨立版 EOP 中管理郵件使用者
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 瞭解如何在 Exchange Online Protection (EOP) 中管理郵件使用者，包括使用目錄同步處理、EAC 和 PowerShell 來管理使用者。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64b7effadd96b6dc025677139c4303acd538dadb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827072"
---
# <a name="manage-mail-users-in-standalone-eop"></a>在獨立版 EOP 中管理郵件使用者

在獨立 Exchange Online Protection (EOP 中) 沒有 Exchange Online 信箱的組織，郵件使用者是使用者帳戶的基本類型。 郵件使用者在獨立 EOP 組織中具有帳號憑證，而且可以存取) 具有指派許可權的資源 (。 郵件使用者的電子郵件地址為外部 (例如，在您的內部部署電子郵件環境) 中。

> [!NOTE]
> 當您建立郵件使用者時，可在 Microsoft 365 系統管理中心使用對應的使用者帳戶。 當您在 Microsoft 365 系統管理中心中建立使用者帳戶時，將無法使用該帳戶來建立郵件使用者。

在獨立 EOP 中建立及管理郵件使用者的建議方法是使用目錄同步處理，如本主題稍後的 [使用目錄同步處理來管理郵件使用者](#use-directory-synchronization-to-manage-mail-users) 一節所述。

針對具有少量使用者的獨立 EOP 組織，您可以在 Exchange 系統管理中心中新增及管理郵件使用者 (EAC) 或獨立 EOP PowerShell （如本主題所述）。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 若要 (EAC) 開啟 Exchange 系統管理中心，請參閱 [exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 當您在 EOP PowerShell 中建立郵件使用者時，可能會遇到節流。 此外，EOP PowerShell Cmdlet 使用的批次處理方法，可導致幾分鐘的傳播延遲，使命令的結果看得見。

- 您必須已獲指派權限，才能執行這些程序。 具體而言，您需要建立郵件收件者 (建立) 和郵件收件者， (修改) 角色，預設會指派給 OrganizationManagement (全域系統管理員) 和 RecipientManagement 角色群組。 如需詳細資訊，請參閱 [獨立 EOP 中的許可權](feature-permissions-in-eop.md) 和 [使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 有問題嗎？ 在 Exchange 論壇中尋求協助。 請造訪 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇。

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>使用 Exchange 系統管理中心管理郵件使用者

### <a name="use-the-eac-to-create-mail-users"></a>使用 EAC 來建立郵件使用者

1. 在 EAC 中，**移至 [** 收件者] [ \> **連絡人**]

2. 按一下 [ **新增** ![ 新圖示] ](../../media/ITPro-EAC-AddIcon.png) 。 在開啟的 [ **新增郵件使用者** ] 頁面中，設定下列設定。 以必要標出的設定 <sup>\*</sup> 。

   - **名字**   使用此方塊輸入使用者的名字。

   - **縮寫**：人員的中間名首字母。

   - **姓氏**   使用此方塊輸入使用者的姓氏。

   - <sup>\*</sup>**顯示名稱**：根據預設，此方塊會顯示 [ **名字**]、[ **縮寫**] 和 [ **姓氏** ] 方塊中的值。 您可以接受此值或加以變更。 該值應該是唯一的，且長度上限為64個字元。

   - <sup>\*</sup>**Alias**：針對使用者輸入唯一的別名，使用最多64個字元。

   - **外部電子郵件地址**：輸入使用者的電子郵件地址。 網域應該位於雲端架構組織的外部。

   - <sup>\*</sup>**使用者識別碼**：輸入人員將用來登入服務的帳戶。 使用者識別碼包含在 ( @ ) 符號 ( @ ) 左邊的使用者名稱，以及右側的網域。

   - <sup>\*</sup>**新增密碼**和 <sup>\*</sup> **確認密碼**：輸入並重新輸入帳戶密碼。 請確認密碼符合您組織的密碼長度、複雜性和歷程記錄需求。

3. 完成作業後，按一下 [ **儲存** ] 以建立郵件使用者。

### <a name="use-the-eac-to-modify-mail-users"></a>使用 EAC 修改郵件使用者

1. In the EAC, go to **Recipients** \> **Contacts**.

2. 選取您要修改的郵件使用者，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-AddIcon.png) 。

3. 在開啟的 [郵件使用者屬性] 頁面上，按一下下列其中一個索引標籤以查看或變更屬性。

   完成後，按一下 [儲存]****。

#### <a name="general"></a>一般

使用 [ **一般** ] 索引標籤可查看或變更郵件使用者的基本資訊。

- **名字**   使用此方塊輸入使用者的名字。

- **縮寫**

- **姓氏**   使用此方塊輸入使用者的姓氏。

- **顯示名稱**：這個名稱會出現在組織的通訊錄、電子郵件中的 [To：] 和 [寄件者：] 行，以及 EAC 中的連絡人清單中。 這個顯示名稱前後不可包含空格。

- **使用者識別碼**：這是 Microsoft 365 中的使用者帳戶。 您無法在這裡修改此值。

#### <a name="contact-information"></a>連絡人資訊

使用 [ **連絡人資訊** ] 索引標籤來查看或變更使用者的連絡人資訊。 此頁的資訊顯示於通訊錄中。

- **街**
- **City**
- **縣/市**
- **郵遞區號**
- **國家/地區**
- **公司電話**
- **行動電話**
- **傳真**
- **更多選項**

  - **Office**
  - **住家電話**
  - **網頁**
  - **附註**

#### <a name="organization"></a>組織

使用 [ **組織** ] 索引標籤，記錄組織中使用者角色的詳細資訊。

- **Title**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>使用 EAC 來移除郵件使用者

1. In the EAC, go to **Recipients** \> **Contacts**.

2. 選取您要移除的郵件使用者，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-mail-users"></a>使用 PowerShell 管理郵件使用者

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>使用獨立 EOP PowerShell 來查看郵件使用者

若要傳回獨立 EOP PowerShell 中所有郵件使用者的摘要清單，請執行下列命令：

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

若要查看特定郵件使用者的詳細資訊，請 \<MailUserIdentity\> 以郵件使用者的名稱、別名或帳戶名稱取代，並執行下列命令：

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

如需詳細的語法及參數資訊，請參閱 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) 和 [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user)。

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>使用獨立 EOP PowerShell 建立郵件使用者

若要在獨立 EOP PowerShell 中建立郵件使用者，請使用下列語法：

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**附註**：

- _Name_參數是必要的，最大長度為64個字元，且必須是唯一的。 如果您未使用 _DisplayName_ 參數，則 _Name_ 參數的值會用於顯示名稱。
- 如果您未使用 _alias_ 參數，則會使用 _MicrosoftOnlineServicesID_ 參數的左側作為別名。
- 如果您未使用 _ExternalEmailAddress_ 參數， _MicrosoftOnlineServicesID_ 值會用於外部電子郵件地址。

本範例會建立具有下列設定的郵件使用者：

- 名稱為 JeffreyZeng，顯示名稱為 Jeffrey Zeng。
- 名字為 Jeffrey，姓氏為 Zeng。
- 別名為 jeffreyz。
- 外部電子郵件地址為 jzeng@tailspintoys.com。
- 帳戶名稱是 jeffreyz@contoso.onmicrosoft.com。
- 密碼為 Pa$$word1。

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

如需詳細的語法及參數資訊，請參閱 [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)。

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>使用獨立 EOP PowerShell 修改郵件使用者

若要在獨立 EOP PowerShell 中修改現有的郵件使用者，請使用下列語法：

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

此範例會設定 Pilar Pinilla 的外部電子郵件地址。

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

此範例會將所有郵件使用者的 [公司] 內容設定為 [Contoso]。

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

如需詳細的語法及參數資訊，請參閱 [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)。

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>使用獨立 EOP PowerShell 移除郵件使用者

若要在獨立 EOP PowerShell 中移除郵件使用者，請以 \<MailUserIdentity\> 郵件使用者的名稱、別名或帳戶名稱取代，並執行下列命令：

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

此範例會移除 Jeffrey Zeng 的郵件使用者。

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

如需詳細的語法及參數資訊，請參閱 [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已在獨立 EOP 中成功建立、修改或移除郵件使用者，請使用下列任一程式：

- In the EAC, go to **Recipients** \> **Contacts**. 請確認郵件使用者已列出 (或未列出) 。 選取郵件使用者，然後在詳細資料窗格中查看資訊，或按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-AddIcon.png) 以查看設定。

- 在 [獨立 EOP PowerShell] 中，執行下列命令來確認郵件使用者已列出 (或未列出) ：

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- \<MailUserIdentity\>以郵件使用者的名稱、別名或帳戶名稱取代，並執行下列命令來確認設定：

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>使用目錄同步處理來管理郵件使用者

在獨立 EOP 中，具有內部部署 Active Directory 的客戶可以使用目錄同步作業。 您可以將這些帳戶同步處理至 Azure Active Directory (Azure AD) ，以將帳戶副本儲存在雲端中。 當您將現有的使用者帳戶同步處理至 Azure Active Directory 時，您可以在 Exchange 系統管理中心的 [收件 **者] 窗格** 中， (EAC) 或獨立 EOP PowerShell 中查看那些使用者。

**附註**：

- 如果您使用目錄同步處理來管理收件者，您仍然可以新增及管理 Microsoft 365 系統管理中心中的使用者，但不會與您的內部部署 Active Directory 同步處理。 這是因為目錄同步作業只會從內部部署 Active Directory 同步收件者至雲端。

- 建議搭配下列功能一起使用目錄同步處理：

  - **Outlook 安全寄件者清單和封鎖的寄件者清單**：同步處理至服務時，這些清單將優先于服務中的垃圾郵件篩選。 這可讓使用者管理其個人的安全寄件者清單和封鎖的寄件者清單和個別寄件者和網域專案。 如需詳細資訊，請參閱[設定 Exchange Online 信箱的垃圾郵件設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes)。

  - **目錄架構邊緣封鎖 (DBEB) **：如需 DBEB 的詳細資訊，請參閱 [使用目錄架構邊緣封鎖以拒絕傳送至無效收件](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)者的郵件。

  - **使用者存取隔離**：若要存取隔離的郵件，收件者的服務中必須具有有效的使用者識別碼和密碼。 如需隔離的詳細資訊，請參閱 [尋找及發行隔離的郵件為使用者](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)。

  - **郵件流程規則 (也稱為傳輸規則) **：使用目錄同步處理時，您現有的 Active directory 使用者和群組會自動上傳至雲端，您也可以建立特定使用者和/或群組的郵件流程規則，而不必手動將其新增至服務中。 請注意， [動態通訊群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)無法透過目錄同步作業進行同步處理。

取得必要的許可權並準備目錄同步處理，如 [與 Azure Active directory 混合身分識別的功能](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)所述。

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>同步處理目錄與 Azure Active Directory Connect (AAD Connect) 

1. 啟動目錄同步處理，如 [AZURE AD Connect sync 中所述：瞭解及自訂同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)處理。

2. 依照 [AZURE AD Connect 先決條件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)中所述，安裝及設定內部部署電腦以執行 AAD connect。

3. [選取要用於 AZURE AD Connect 的安裝類型](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)：

   - [表達](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [自訂](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [傳遞驗證](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> 完成 Azure Active Directory 同步處理工具設定精靈 之後，您的 Active Directory 樹系中會建立 **MSOL_AD_SYNC** 帳戶。此帳戶將用來讀取和同步處理您的內部部署 Active Directory 資訊。為了讓目錄同步作業能夠正確運作，請確定有開啟您的本機目錄同步作業伺服器上的 TCP 443。

在設定同步處理之後，請務必確認 AAD 連線已正確同步處理。 In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.
