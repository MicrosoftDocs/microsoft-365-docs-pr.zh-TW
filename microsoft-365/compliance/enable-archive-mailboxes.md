---
title: 啟用「安全性與合規性中心」的封存信箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: 使用 Office 365 中的「安全性與合規性中心」來啟用封存信箱，以便支援組織的郵件保留、電子文件探索和保留需求。
ms.openlocfilehash: 6ff4e0eda616e9bdd5fe10832ae334c9337272f0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631738"
---
# <a name="enable-archive-mailboxes-in-the-security--compliance-center"></a>啟用「安全性與合規性中心」的封存信箱
  
Office 365 中的封存 (稱為就地封存) 可為使用者提供額外的信箱儲存空間。 開啟封存信箱後，使用者只要使用 Microsoft Outlook 和 Outlook 網頁版 (其前身為 Outlook Web App) 即可存取及儲存封存信箱中的郵件。 使用者也可以在其主要信箱和封存信箱之間移動或複製郵件。 除此之外，他們也可以使用「復原刪除的郵件」工具復原其封存信箱的 [可復原的項目] 資料夾中的已刪除郵件。 
  
> [!NOTE]
> Office 365 中的自動展開封存功能提供封存信箱的額外儲存空間。 如果已開啟自動展開封存功能，當使用者封存信箱的初始儲存配額已滿時，Office 365 會自動新增額外的儲存空間。 也就是說，使用者的信箱儲存空間將不會用盡，若您一開始就啟用封存信箱並為組織開啟自動展開封存功能，之後就能高枕無憂。 如需詳細資訊，請參閱[在 Office 365 中的無限制封存的概觀](unlimited-archiving.md)。 
  
## <a name="before-you-begin"></a>開始之前

您必須在 Exchange Online 中獲派郵件收件者角色，以便啟用或停用封存信箱。 根據預設，系統會將這個角色指派給 Exchange 系統管理中心 [權限]**** 頁面上的 [收件者管理] 和 [組織管理] 角色群組。 如果您在「安全性與合規性中心」看不到 [封存]**** 頁面，請要求系統管理員指派必要權限給您。 
  
## <a name="enable-an-archive-mailbox"></a>啟用封存信箱
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用您的公司或學校帳戶登入。
    
3. 在「安全性與合規性中心」的左窗格中，按一下 **[資料控管]** \> **[封存]**。
    
    [封存]**** 頁面隨即出現。[封存信箱] **** 欄會指出每個使用者的封存信箱是啟用還是停用。 
    
4. 在信箱清單中，選取要為其啟用封存信箱的使用者。
    
    ![在選取使用者的詳細資料窗格中按一下 [啟用]，以啟用封存信箱](../media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. 在所選使用者的詳細資料窗格中按一下 [啟用]****。 
    
    系統會顯示警告訊息，提醒您如果啟用封存信箱，系統會將使用者信箱中超過指派給信箱之封存原則的郵件移至新的封存信箱。 預設的封存原則 (該原則屬於指派給 Exchange Online 信箱之保留原則的一部分) 會在將郵件傳遞至信箱或使用者建立郵件當日的兩年後，將郵件移至封存信箱。 如需詳細資訊，請參閱本文中的 [其他資訊]****。 
    
6. 按一下 [是] 啟用封存信箱。 
    
    可能需要一些時間才能建立封存信箱。 建立封存信箱後，您可在選取使用者的詳細資料窗格中看到 [封存信箱：已啟用]****。 您可能需要按一下 [重新整理]**** ![重新整理圖示](../media/O365-MDM-Policy-RefreshIcon.gif)，以便更新詳細資料窗格中的資訊。 
    
> [!TIP]
> 您也可以選取多個信箱 (使用 Shift 或 Ctrl 鍵) 來大量啟用封存。選取多個信箱後，按一下詳細資料窗格中的 [啟用]。 
  
## <a name="disable-an-archive-mailbox"></a>停用封存信箱
  
您也可以使用「安全性與合規性中心」中的 [封存]**** 頁面來停用使用者的封存信箱。 停用封存信箱之後，可以在停用它的 30 天內重新連線至使用者的主要信箱。 在此情況下，系統會還原封存信箱的原始內容。 30 天後，便會永久刪除原始封存信箱的內容，無法再復原。 因此，如果您在停用封存超過 30 天之後才重新啟用它，系統會建立新的封存信箱。 
  
請注意，在郵件傳遞當日的兩年後，指派給使用者信箱的預設封存原則會將郵件移至封存信箱。 即使您將使用者的封存信箱停用，也不會對信箱郵件造成影響，系統會將這些郵件保留在使用者的主要信箱中。
  
若要停用封存信箱：
  
1. 請移至 [https://protection.office.com](https://protection.office.com)。
    
2. 使用您的公司或學校帳戶登入。
    
3. 在「安全性與合規性中心」的左窗格中，按一下 **[資料控管]** \> **[封存]**。
    
    [封存]**** 頁面隨即出現。[封存信箱] **** 欄會指出每個使用者的封存信箱是啟用還是停用。 
    
4. 在信箱清單中，選取要為其停用封存信箱的使用者。
    
5. 在詳細資料窗格中，按一下 [停用]****。 
    
    系統會顯示警告訊息，提醒您有 30 天的時間可以重新啟用封存信箱，30 天之後，系統將會永久刪除封存中的所有資訊。 
    
6. 按一下 [是] 停用封存信箱。 
    
    可能需要一些時間才能停用封存信箱。 停用封存信箱後，您可在選取使用者的詳細資料窗格中看到 [封存信箱：已停用]****。 您可能需要按一下 [重新整理]**** ![重新整理圖示](../media/O365-MDM-Policy-RefreshIcon.gif)，以便更新詳細資料窗格中的資訊。 
    
> [!TIP]
> 您也可以選取多個已啟用封存信箱的使用者 (使用 Shift 或 Ctrl 鍵) 來大量停用封存信箱。選取多個信箱後，按一下詳細資料窗格中的 [停用]****。 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>使用 Exchange Online PowerShell 來啟用或停用封存信箱

您也可以使用 Exchange Online PowerShell 來啟用封存信箱。 使用 PowerShell 的主要原因是您可以為組織中的所有使用者快速啟用封存信箱。

第一個步驟是連線至 Exchange Online PowerShell。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

連線到 Exchange Online 後，您可以執行下列各節中的命令，以便啟用或停用封存信箱。

### <a name="enable-archive-mailboxes"></a>啟用封存信箱

執行下列命令，以便啟用單一使用者的封存信箱。
    
  ```powershell
  Enable-Mailbox -Identity <username> -Archive
  ```

執行下列命令，以便啟用組織中所有使用者的封存信箱 (針對目前尚未啟用封存信箱者)。
    
  ```powershell
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```

### <a name="disable-archive-mailboxes"></a>停用封存信箱

執行下列命令，以便停用單一使用者的封存信箱。
    
  ```powershell
  Disable-Mailbox -Identity <username> -Archive
  ```

執行下列命令，以便停用組織中所有使用者的封存信箱 (針對目前已啟用封存信箱者)。
    
  ```powershell
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a>詳細資訊
  
- 當封存信箱啟用時，使用者可以將郵件儲存在其封存信箱中。 使用者可以使用 Microsoft Outlook 和 Outlook 網頁版來存取其封存信箱。 只要使用這些用戶端應用程式，使用者就能檢視其封存信箱中的郵件，並且在其主要信箱與其封存信箱之間移動或複製郵件。 使用者也可以使用「復原刪除的郵件」工具復原其封存信箱的 [可復原的項目] 資料夾中的已刪除郵件。

   如需支援就地封存的 Outlook 授權清單，請參閱[Exchange 功能的 Outlook 授權需求](https://support.office.com/article/outlook-license-requirements-for-exchange-features-46b6b7c5-c3ca-43e5-8424-1e2807917c99)。

- 封存信箱可協助您和您的使用者符合組織的保留、電子文件探索和保留需求。 例如，您可以使用組織的 Exchange 保留原則，將信箱內容移至使用者的封存信箱。 使用「安全性與合規性中心」的「內容搜尋」工具搜尋使用者信箱的特定內容時，系統也會一併搜尋使用者的封存信箱。 此外，當您採行訴訟資料暫留或是將保留原則套用至使用者的信箱時，系統也會保留封存信箱中的郵件。
  
- 啟用封存信箱後，您的組織即可使用自動指派給每個信箱的預設 Exchange 保留原則 (也稱為「通訊記錄管理」或 MRM 原則)。 啟用封存信箱時，預設 Exchange 保留原則會自動執行下列動作： 
  
    - 將使用者主要信箱中兩年以上的郵件移到其封存信箱。 
    
    - 將使用者主要信箱的 [可復原的項目] 資料夾中 14 天以上的郵件移至其封存信箱的 [可復原的項目] 資料夾。
    
- 如需封存信箱及 Exchange 保留原則的詳細資訊，請參閱：
    
  - [保留標記和保留原則](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [Exchange Online 中的預設保留原則](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [設定組織中的信箱封存和刪除原則](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
