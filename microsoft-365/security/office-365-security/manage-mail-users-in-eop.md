---
title: 管理 EOP 中的郵件使用者
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 定義郵件使用者是管理 Exchange Online Protection (EOP) 的重要環節。
ms.openlocfilehash: bdbc3cd54901d53b4a7d01bcf513a9b9a0df1c01
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633791"
---
# <a name="manage-mail-users-in-eop"></a>管理 EOP 中的郵件使用者

定義郵件使用者是管理 Exchange Online Protection (EOP) 的重要環節。在 EOP 中，您可以透過數種方式來管理使用者：

- **使用目錄同步處理來管理郵件使用者**：如果您的公司在內部部署 Active Directory 環境中有現有的使用者帳戶，您可將這些帳戶同步處理至 Azure Active Directory (AD)，此工具會將這些帳戶的複本儲存至雲端。將現有的使用者帳戶同步處理至 Azure Active Directory 時，您可以在 Exchange 系統管理中心 (EAC) 的 [**收件者**] 窗格中檢視這些使用者。建議使用目錄同步作業。

- **使用 EAC 管理郵件使用者**：在 EAC 中直接新增及管理郵件使用者。這是新增郵件使用者最簡單的方法，也很適合一次新增一位使用者。

- **使用 PowerShell 管理郵件使用者**：在 Exchange Online Protection PowerShell 中新增及管理郵件使用者。 這個方法適合用來新增多筆記錄和建立指令碼。

> [!NOTE]
> 您可以在 Microsoft 365 系統管理中心新增使用者，但是這些使用者不能做為郵件收件者使用。

## <a name="before-you-begin"></a>開始之前

- 若要開啟 Exchange 系統管理中心，請參閱 exchange [Online Protection 中的 exchange 系統管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)中的「使用者、連絡人和角色群組」項目。

- 請注意，使用 Exchange Online Protection PowerShell Cmdlet 建立郵件使用者時，您可能會遇到節流。

- 本主題中的 PowerShell 命令使用的批次處理方法，可導致幾分鐘的傳播延遲，使命令的結果看得見。

- 若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 有問題嗎？ 在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。

## <a name="use-directory-synchronization-to-manage-mail-users"></a>使用目錄同步處理來管理郵件使用者

本節提供使用目錄同步處理來管理電子郵件使用者的相關資訊。

**附註**：

- 如果您使用目錄同步處理來管理收件者，您仍然可以新增及管理 Microsoft 365 系統管理中心中的使用者，但不會與您的內部部署 Active Directory 同步處理。 這是因為目錄同步處理只會將內部部署 Active Directory 中的收**件**者同步處理**至**雲端。

- 建議使用目錄同步處理，以搭配下列功能使用：

  - **Outlook 安全寄件者和封鎖的寄件者清單**：同步處理至服務時，這些清單將優先于服務中的垃圾郵件篩選。 這可讓使用者針對個別使用者或個別網域，管理他們自己的安全寄件者和封鎖的寄件者清單。

  - **目錄架構邊緣封鎖（DBEB）**：如需 DBEB 的詳細資訊，請參閱[使用目錄架構邊緣封鎖以拒絕傳送至無效收件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)者的郵件。

  - **使用者垃圾郵件隔離**：若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。 保護內部部署信箱的 EOP 客戶必須是有效的電子郵件使用者。

  - **郵件流程規則**：當您使用目錄同步處理時，您現有的 Active directory 使用者和群組會自動上傳至雲端，然後您可以建立郵件流程規則（也稱為傳輸規則），該規則會以特定使用者和/或群組為目標，而不需要透過 EAC 或 Exchange Online Protection PowerShell 手動新增。 請注意， [動態通訊群組](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)無法透過目錄同步作業進行同步處理。

取得必要的許可權並準備目錄同步處理，如[與 Azure Active directory 混合身分識別的功能](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)所述。

### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a>使用 Azure Active Directory Connect （AAD 連接）同步使用者目錄

若要將使用者同步處理至 Azure Active Directory （AAD），您必須先**啟用目錄同步**處理，如[Azure AD Connect 同步中所述：瞭解和自訂同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)處理。

接下來是安裝和設定內部部署電腦的安裝及設定，以執行 AAD 連線（如果您還沒有必要的預先檢查的話）。 [設定 Aad connect，直通方法](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)會告訴您如何設定您的帳戶，並將您的帳戶從內部部署與使用 AAD Connect 的 Azure AD 同步處理。

但在執行這項作業之前，請確定[您符合必要條件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)，然後[選擇安裝類型](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)。 較舊的連結是快速安裝的簡短文章。 您也可以在 [[自訂安裝](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)] 或 [必要時[傳遞驗證](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)] 中尋找文章。

> [!IMPORTANT]
> 完成 Azure Active Directory 同步處理工具設定精靈 之後，您的 Active Directory 樹系中會建立 **MSOL_AD_SYNC** 帳戶。此帳戶將用來讀取和同步處理您的內部部署 Active Directory 資訊。為了讓目錄同步作業能夠正確運作，請確定有開啟您的本機目錄同步作業伺服器上的 TCP 443。

在設定同步處理之後，請務必確認 EOP 已正確地進行同步處理。 In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.

## <a name="use-the-eac-to-manage-mail-users"></a>使用 EAC 管理郵件使用者

本節提供直接在 EAC 中新增及管理電子郵件使用者的相關資訊。

### <a name="use-the-eac-to-add-a-mail-user"></a>使用 EAC 新增郵件使用者

1. 移至 EAC 中的 [ **收件者**] \> [ **連絡人**]，然後按一下 [ **新增 +**]，以建立電子郵件使用者。

2. 在 [ **新增郵件使用者**] 頁面上，輸入使用者的資訊，包括下列項目：

   ****

   |**郵件使用者內容**|**描述**|
   |:-----|:-----|
   |**名字**、 **縮寫**和 **姓氏**|在適當的方塊中輸入使用者的完整名稱。|
   |**顯示名稱**|輸入名稱，最多 64 個字元。根據預設，此方塊會顯示 [**名字**]、[**縮寫**] 和 [**姓氏**] 方塊中的名稱 (如果有的話)。顯示名稱是必要項目。  |
   |**別名**|輸入使用者的唯一別名，最多 64 個字元。別名是必要項目。|
   |**外部電子郵件地址**|輸入使用者的外部電子郵件地址。|
   |**使用者識別碼**|輸入郵件使用者將用來登入服務的名稱。使用者登入名稱由 @ 符號左側的使用者名稱和右側的尾碼所組成。一般來說，尾碼是使用者帳戶所在的網域名稱。|
   |**新密碼**|輸入郵件使用者將用來登入服務的密碼。請確定您提供的密碼符合您正在其中建立使用者帳戶之網域的密碼長度、複雜性和歷程記錄需求。|
   |**確認密碼**|重新輸入密碼加以確認。|

3. 按一下 [ **儲存**]，以建立新的郵件使用者。新的使用者應會出現在使用者清單中。

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a>使用 EAC 來編輯或移除郵件使用者

- In the EAC, go to **Recipients** \> **Contacts**. 在使用者清單中，按一下您要查看或變更的使用者，然後選取 [**編輯** ![編輯圖示](../../media/ITPro-EAC-EditIcon.gif) ] 以根據需要更新使用者設定。 You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization. 您也可以選取使用者，然後選擇 [**移除** ![移除]](../../media/ITPro-EAC-RemoveIcon.gif)圖示加以刪除。

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a>使用 Exchange Online Protection PowerShell 管理郵件使用者

本節提供使用遠端 Windows PowerShell 來新增和管理郵件使用者的相關資訊。

### <a name="use-eop-powershell-to-add-a-mail-user"></a>使用 EOP PowerShell 新增郵件使用者

此範例使用 [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) 在 EOP 中為 Jeffrey Zeng 建立具有郵件功能的使用者帳戶，詳細資料如下：

- 名字為 Jeffrey，姓氏為 Zeng。

- 名稱是 Jeffrey，而顯示名稱是 Jeffrey Zeng。

- 別名為 jeffreyz。

- 外部電子郵件地址為 jzeng@tailspintoys.com。

- Office 365 登入名稱是 jeffreyz@contoso.onmicrosoft.com。

- 密碼為 Pa$$word1。

```PowerShell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

若要確認這是否正常運作，請執行下列命令，以顯示新郵件使用者 Jeffrey Zeng 的相關資訊：

```PowerShell
Get-User -Identity "Jeffrey Zeng"
```

如需詳細的語法及參數資訊，請參閱[Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)。

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a>使用 EOP PowerShell 編輯郵件使用者的屬性

使用 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) 和 [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) 指令程式來檢視或變更郵件使用者的屬性。

此範例會設定 Pilar Pinilla 的外部電子郵件地址。

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

此範例會將所有郵件使用者的 [公司] 內容設定為 [Contoso]。

```PowerShell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

若要確認這是否正常運作，請使用[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) Cmdlet 來驗證變更。 （請注意，您可以為多個郵件連絡人查看多個屬性。）

```PowerShell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

在上述範例中，所有郵件使用者的 [公司] 屬性設為 [Contoso]，請執行下列命令來驗證變更：

```PowerShell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> 此指令程式採用批次處理方法，因此導致幾分鐘的傳播延遲，然後才能看到指令程式的結果。

### <a name="use-eop-powershell-to-remove-a-mail-user"></a>使用 EOP PowerShell 移除郵件使用者

此範例使用 [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser) 指令程式來刪除使用者 Jeffrey Zeng：

```PowerShell
Remove-EOPMailUser -Identity Jeffrey
```
若要確認這是否正常運作，請執行[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) Cmdlet，以確認郵件使用者已不存在。

```PowerShell
Get-Recipient Jeffrey | Format-List
```
