---
title: 管理 EOP 中的群組
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Admins in 獨立 Exchange Online Protection （EOP）組織可以瞭解如何在 Exchange 系統管理中心（EAC）和獨立 Exchange Online Protection （EOP） PowerShell 中建立、修改和移除通訊群組和擁有郵件功能的安全性群組。
ms.openlocfilehash: fc3f3807216b269a9868e87c5ec784d75385f878
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209016"
---
# <a name="manage-groups-in-eop"></a>管理 EOP 中的群組

在沒有 Exchange Online 信箱的獨立 Exchange Online Protection （EOP）組織中，您可以建立、修改及移除下列類型的群組：

- **通訊群組**：郵件使用者或其他通訊群組的集合。 例如，小組或其他需要在感興趣的常見區域接收或傳送電子郵件的群組。 通訊群組專用於散佈電子郵件，而不是安全主體（他們不能有指派許可權）。

- 擁有**郵件功能的安全性群組**：郵件使用者的集合，以及需要系統管理員角色存取許可權的其他安全性群組。 例如，您可能想要授與特定群組的使用者系統管理員許可權，讓他們可以設定反垃圾郵件和反惡意程式碼設定。

    > [!NOTE]
    > <ul><li>根據預設，啟用郵件功能的新安全性群組會拒絕來自外部（未驗證）寄件者的郵件。</li><li>不要將通訊群組新增至擁有郵件功能的安全性群組。</li></ul>.

您可以在 Exchange 系統管理中心（EAC）和獨立 EOP PowerShell 中管理群組。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 若要開啟 Exchange 系統管理中心，請參閱[exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要連線至獨立 EOP PowerShell，請參閱[connect To Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 當您在獨立 EOP PowerShell 中管理群組時，可能會遇到節流。 本主題中的 PowerShell 程式使用批次處理方法，可導致幾分鐘的傳播延遲，然後才會顯示命令的結果。

- 您必須已獲指派權限，才能執行這些程序。 具體說來，您需要「通訊群組」角色，預設會指派給 OrganizationManagement （全域系統管理員）和 RecipientManagement 角色群組。 如需詳細資訊，請參閱[獨立 EOP 中的許可權](feature-permissions-in-eop.md)和[使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 有問題嗎？ 在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>使用 Exchange 系統管理中心來管理通訊群組

### <a name="use-the-eac-to-create-groups"></a>使用 EAC 來建立群組

1. 在 EAC 中，**移至 [** 收件者 \> **群組**]。

2. 按一下**New** ![ [新增新圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後選取下列其中一個選項：

   - **通訊群組**

   - **擁有郵件功能的安全性群組**

3. 在開啟的 [新增群組] 頁面中，設定下列設定。 以必要標出的設定 <sup>\*</sup> 。

   - <sup>\*</sup>**顯示名稱**：此名稱會出現在組織的通訊錄、電子郵件傳送至此群組的 [收件者] 行，以及 EAC 的 [**群組**] 清單中。 顯示名稱是必要的，必須是唯一的，而且應該是方便使用的，讓人員能夠辨識其內容。

   - <sup>\*</sup>**別名**：使用此方塊可輸入群組的別名名稱。 別名不得超過64個字元，且必須是唯一的。 當使用者在電子郵件的 [我的那一行] 中輸入別名時，它會解析為群組的顯示名稱。

   - <sup>\*</sup>**電子郵件地址**：電子郵件地址是由 at （@）符號左側的別名及右側的網域所組成。 預設會**使用 alias 的**值作為別名值，但您可以變更它。 在 [網域] 值中，按一下下拉清單，然後選取組織中的 [已接受的網域]。

   - **描述**：此描述會顯示在通訊錄和 EAC 中的 [詳細資料] 窗格中。

   - <sup>\*</sup>**擁有**者：群組擁有者可以管理群組成員資格。 依預設，建立群組的人員為擁有者。 所有群組都必須至少一個擁有者。

     若要新增擁有者，請按一下 [**新增** ![ 新增] 圖示 ](../../media/ITPro-EAC-AddIcon.png) 。 在出現的對話方塊中，尋找並選取收件者或群組，然後按一下 [**載入 >**]。 視需要重複此步驟多次。 完成後，按一下 [確定]****。

     若要移除擁有者，請選取擁有者，然後按一下 [**移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。

   - **成員**：新增和移除群組成員。

     若要新增成員，請按一下 [**新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) 。 在出現的對話方塊中，尋找並選取收件者或群組，然後按一下 [**載入 >**]。 視需要重複此步驟多次。 完成後，按一下 [確定]****。

     若要移除成員，請選取成員，然後按一下 [**移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。

4. 完成作業後，按一下 [**儲存**] 以建立通訊群組。

### <a name="use-the-eac-to-modify-distribution-groups"></a>使用 EAC 修改通訊群組

1. 在 EAC 中，**移至 [** 收件者 \> **群組**]。

2. 在群組清單中，選取您要修改的通訊群組或擁有郵件功能的安全性群組，然後按一下 [**編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-AddIcon.png) 。

3. 在開啟的 [通訊群組內容] 頁面上，按一下下列其中一個索引標籤，以查看或變更屬性。

   完成後，按一下 [儲存]****。

#### <a name="general"></a>一般

使用此索引標籤可查看或變更群組的基本資訊。

- **顯示名稱**：此名稱會出現在通訊錄、電子郵件傳送至此群組的 [收件者] 行，以及 [**群組] 清單**中。 顯示名稱是必要的，且應該是方便使用的，讓人員能夠辨識其內容。 在您的網域中也必須是唯一的。

  如果您已實現群組命名原則，則顯示名稱必須符合原則所定義的命名格式。

- **別名**：這是出現在 @ 符號左邊的電子郵件地址部分。 如果您變更別名，群組的主要 SMTP 位址也會變更，而且會包含新的別名。 此外，具有先前別名的電子郵件地址會保留為群組的 proxy 位址。

- **電子郵件地址**：電子郵件地址是由 at （@）符號左側的別名及右側的網域所組成。 預設會**使用 alias 的**值作為別名值，但您可以變更它。 在 [網域] 值中，按一下下拉清單，然後選取組織中的 [已接受的網域]。

- **描述**：此描述會顯示在通訊錄和 EAC 中的 [詳細資料] 窗格中。

#### <a name="ownership"></a>擁有權

使用此索引標籤可指派群組擁有者。 群組擁有者可以管理群組成員資格。 依預設，建立群組的人員為擁有者。 所有群組都必須至少一個擁有者。

若要新增擁有者，請按一下 [**新增** ![ 新增] 圖示 ](../../media/ITPro-EAC-AddIcon.png) 。 在出現的對話方塊中，尋找並選取收件者，然後按一下 [**載入 >**]。 視需要重複此步驟多次。 完成後，按一下 [確定]****。

若要移除擁有者，請選取擁有者，然後按一下 [**移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。

#### <a name="membership"></a>[成員資格]

使用此索引標籤可以新增或移除群組成員。 群組擁有者不需要是群組的成員。

若要新增成員，請按一下 [**新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) 。 在出現的對話方塊中，尋找並選取收件者或群組，然後按一下 [**載入 >**]。 視需要重複此步驟多次。 完成後，按一下 [確定]****。

若要移除成員，請選取成員，然後按一下 [**移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。

### <a name="use-the-eac-to-remove-groups"></a>使用 EAC 移除群組

1. 在 EAC 中，**移至 [** 收件者 \> **群組**]。

2. 在群組清單中，選取您要移除的通訊群組，然後按一下 [**移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-groups"></a>使用 PowerShell 管理群組

### <a name="use-standalone-eop-powershell-to-view-groups"></a>使用獨立 EOP PowerShell 來查看群組

若要在獨立 EOP PowerShell 中傳回所有通訊群組和擁有郵件功能的安全性群組的摘要清單，請執行下列命令：

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

若要傳回群組成員的清單，請 \< \> 使用群組的名稱、別名或電子郵件地址取代 GroupIdentity，並執行下列命令：

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

如需詳細的語法及參數資訊，請參閱[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)和[Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember)。

### <a name="use-standalone-eop-powershell-to-create-groups"></a>使用獨立 EOP PowerShell 建立群組

若要在獨立 EOP PowerShell 中建立通訊群組或擁有郵件功能的安全性群組，請使用下列語法：

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**附註**：

- _Name_參數是必要的，最大長度為64個字元，且必須是唯一的。 如果您未使用 _DisplayName_ 參數，則 _Name_ 參數的值會用於顯示名稱。

- 如果您未使用_alias_參數， _Name_參數會用於別名值。 移除空格，且不支援的字元會轉換成問號（？）。

- 如果您未使用_PrimarySmtpAddress_參數，則會在_PrimarySmtpAddress_參數中使用 alias 值。

- 如果您未使用_Type_參數，則預設值為「分配」。

此範例會使用指定的屬性，建立名為 IT 管理員的通訊群組。

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

如需詳細的語法及參數資訊，請參閱[New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup)。

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>使用獨立 EOP PowerShell 修改群組

若要修改獨立 EOP PowerShell 中的群組，請使用下列語法：

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

這個範例會使用變更西雅圖員工群組的主要 SMTP 位址（也稱為回復位址）來 sea.employees@contoso.com。

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

此範例會將安全小組群組的目前成員取代為 Kitty Petersen and Tyson Fawcett。

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

此範例會將名為 Tyson Fawcett 的新使用者新增至名為 Security Team 的群組，同時保留群組的目前成員。

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

如需詳細的語法及參數資訊，請參閱[Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup)和[EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember)。

### <a name="remove-a-group-using-remote-windows-powershell"></a>使用遠端 Windows PowerShell 移除群組

本範例會使用移除名為 IT 管理員的通訊群組。

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

如需詳細的語法及參數資訊，請參閱[Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何知道這些程序是否正常運作？

若要確認您是否已成功建立、修改或移除通訊群組或已啟用郵件功能的安全性群組，請執行下列任一步驟：

- 在 EAC 中，**移至 [** 收件者 \> **群組**]。 確認群組已列出（或未列出），並確認 [**群組類型**] 值。 選取群組，然後在詳細資料窗格中查看資訊，或按一下 [**編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-AddIcon.png) 以查看設定。

- 在 [獨立 EOP PowerShell] 中，執行下列命令來確認群組已列出（或未列出）：

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- \< \> 以群組的名稱、別名或電子郵件地址取代 GroupIdentity，並執行下列命令來確認設定：

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- 若要查看群組成員，請將 \< GroupIdentity 取代 \> 為群組的名稱、別名或電子郵件地址，並執行下列命令：

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
