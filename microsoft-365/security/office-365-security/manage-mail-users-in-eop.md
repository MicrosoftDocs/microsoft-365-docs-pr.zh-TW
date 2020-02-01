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
ms.openlocfilehash: 53d47452979c42273fd485fa89642eea881bb21a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598980"
---
# <a name="manage-mail-users-in-eop"></a>管理 EOP 中的郵件使用者

定義郵件使用者是管理 Exchange Online Protection (EOP) 的重要環節。在 EOP 中，您可以透過數種方式來管理使用者：

- **使用目錄同步處理來管理郵件使用者**：如果您的公司在內部部署 Active Directory 環境中有現有的使用者帳戶，您可將這些帳戶同步處理至 Azure Active Directory (AD)，此工具會將這些帳戶的複本儲存至雲端。將現有的使用者帳戶同步處理至 Azure Active Directory 時，您可以在 Exchange 系統管理中心 (EAC) 的 [**收件者**] 窗格中檢視這些使用者。建議使用目錄同步作業。

- **使用 EAC 管理郵件使用者**：在 EAC 中直接新增及管理郵件使用者。這是新增郵件使用者最簡單的方法，也很適合一次新增一位使用者。

- **使用 PowerShell 來管理郵件使用者**： 新增及管理郵件使用者在 Exchange Online Protection PowerShell。 這個方法適合用來新增多筆記錄和建立指令碼。

> [!NOTE]
> 您可以在 Microsoft 365 系統管理中心中，新增使用者，不過，這些使用者不能當成郵件收件者。

## <a name="before-you-begin"></a>開始之前

- 若要開啟 Exchange 系統管理中心，請參閱[Exchange 系統管理中心在 Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)中的「使用者、連絡人和角色群組」項目。

- 請注意，當使用 Exchange Online Protection PowerShell cmdlet 建立郵件使用者，您可能會遇到節流問題。

- 本主題中的命令使用批次處理方法會導致前一個命令的結果數分鐘的傳播延遲的 PowerShell 是可見。

- 若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 有問題嗎？ 在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。

## <a name="use-directory-synchronization-to-manage-mail-users"></a>使用目錄同步處理來管理郵件使用者

本節提供使用目錄同步處理來管理電子郵件使用者的相關資訊。

**附註**：

- 如果您使用目錄同步作業管理收件者時，您仍然可以新增及管理使用者在 Microsoft 365 系統管理中心中，但它們不會與您在內部部署 Active Directory 同步。 這是因為目錄同步作業只會同步收件者**從**您內部部署 Active Directory**至**雲端。

- 目錄同步作業被建議使用下列功能：

  - **Outlook 安全寄件者和封鎖寄件者清單**： 這些清單時進行同步處理至服務，將會優先於垃圾郵件篩選服務中。 這可讓使用者針對個別使用者或個別網域，管理他們自己的安全寄件者和封鎖的寄件者清單。

  - **目錄架構邊緣封鎖 (DBEB)**: 如需 DBEB 的詳細資訊，請參閱[使用 Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

  - **使用者垃圾郵件隔離區**： 若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。 保護內部部署信箱的 EOP 客戶必須是有效的電子郵件使用者。

  - **郵件流程規則**： 當您使用目錄同步處理，您現有的 Active Directory 使用者和群組會自動上傳至雲端，您可以再建立郵件流程規則 （也稱為傳輸規則），而不必手動新增他們透過針對特定使用者和/或群組的 EAC 或 Exchange Online Protection PowerShell。 請注意， [動態通訊群組](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)無法透過目錄同步作業進行同步處理。

取得必要權限，並做好目錄同步處理，如所述[什麼是混合式身分識別與 Azure Active Directory？](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)。

### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a>若要同步處理使用者目錄與 Azure Active Directory Connect (AAD Connect)

若要同步處理至 Azure Active Directory (AAD) 您必須先**啟動目錄同步處理**，如所述的使用者[Azure AD Connect 同步處理： 了解及自訂同步處理](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

下一步是安裝及設定的內部電腦執行 AAD Connect （如果您還沒有一個--一些值得檢查事先）。 [設定 AAD Connect，快速方式](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)主題會告訴您如何安裝及與 AAD 連線同步到 Azure AD 從內部部署帳戶。

但在執行該工作之前，讓某些[您符合必要條件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)，然後[選擇 [安裝類型](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)。 快速安裝簡短文章是前面的連結。 如果時需要這些，您也可以找到[自訂的安裝](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)或[通過驗證](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)的文章。

> [!IMPORTANT]
> 完成 Azure Active Directory 同步處理工具設定精靈 之後，您的 Active Directory 樹系中會建立 **MSOL_AD_SYNC** 帳戶。此帳戶將用來讀取和同步處理您的內部部署 Active Directory 資訊。為了讓目錄同步作業能夠正確運作，請確定有開啟您的本機目錄同步作業伺服器上的 TCP 443。

設定後您同步處理，請務必確認，則 EOP 會正確同步處理。 In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.

## <a name="use-the-eac-to-manage-mail-users"></a>使用 EAC 管理郵件使用者

本節提供直接在 EAC 中新增及管理電子郵件使用者的相關資訊。

### <a name="use-the-eac-to-add-a-mail-user"></a>使用 EAC 來新增郵件使用者

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

- In the EAC, go to **Recipients** \> **Contacts**. 在使用者清單中，按一下您要檢視或變更的使用者，然後選取 [**編輯**![編輯圖示](../media/ITPro-EAC-EditIcon.gif)以視需要更新使用者設定。 You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization. 您可以也選取使用者，然後選擇 [**移除**![移除圖示](../media/ITPro-EAC-RemoveIcon.gif)將它刪除。

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a>使用 Exchange Online Protection PowerShell 來管理郵件使用者

本節提供使用遠端 Windows PowerShell 來新增和管理郵件使用者的相關資訊。

### <a name="use-eop-powershell-to-add-a-mail-user"></a>使用 EOP PowerShell 來新增郵件使用者

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

若要確認此作業正常運作，請執行下列命令，以顯示新郵件使用者 Jeffrey Zeng 的相關資訊：

```PowerShell
Get-User -Identity "Jeffrey Zeng"
```

如需詳細的語法及參數資訊，請參閱[Get-user](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)。

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

若要確認此作業正常運作，請使用[Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)指令程式來驗證變更。 （請注意，您可以檢視多個郵件連絡人的多個屬性）。

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
若要確認此作業正常運作，請執行[Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)指令程式，來確認郵件使用者不再存在。

```PowerShell
Get-Recipient Jeffrey | Format-List
```
