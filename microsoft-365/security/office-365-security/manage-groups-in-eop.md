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
description: 在本文中，您將瞭解如何在 Exchange Online Protection （EOP）中建立及管理 Exchange 組織的擁有郵件功能的群組。
ms.openlocfilehash: 37825175e3332e975065a3807c6ed9d5096b1a7f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034399"
---
# <a name="manage-groups-in-eop"></a>管理 EOP 中的群組

 您可以使用 Exchange Online Protection （EOP）為 Exchange 組織建立擁有郵件功能的群組。 您也可以使用 EOP 來定義或更新組屬性，以指定成員資格、電子郵件地址及其他群組的群組內容。 您可以根據您的需求，建立通訊群組和安全性群組。 您可以使用 Exchange 系統管理中心（EAC）或透過遠端 Windows PowerShell 建立這些群組。

## <a name="types-of-mail-enabled-groups"></a>擁有郵件功能的群組類型

您可以為您的 Exchange 組織建立兩種類型的群組：

- 通訊群組是電子郵件使用者的集合（如小組或其他的特別小組），其需要接收或傳送有關感興趣之共同領域的電子郵件。 通訊群組專用於散佈電子郵件訊息。 在 EOP 中，通訊群組是指任何擁有郵件功能的群組，不論其是否有安全性內容。

- 安全性群組是需要系統管理員角色存取許可權之電子郵件使用者的集合。 例如，您可能想要授與特定群組的使用者系統管理員角色許可權，讓他們可以設定反垃圾郵件和反惡意程式碼設定。

    > [!NOTE]
    > 根據預設，所有擁有郵件功能的新安全性群組都需要驗證所有寄件者。 這可防止外部寄件者傳送郵件給擁有郵件功能的安全性群組。

## <a name="before-you-begin"></a>開始之前

- 您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的許可權，請參閱[EOP 中的功能許可權](feature-permissions-in-eop.md)主題中的「通訊群組和安全性群組」專案。

- 若要開啟 Exchange 系統管理中心，請參閱 exchange [Online Protection 中的 exchange 系統管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 請注意，使用 Exchange Online Protection PowerShell Cmdlet 來建立及管理群組時，您可能會遇到節流。

- 本主題中的 PowerShell 程式使用批次處理方法，可導致幾分鐘的傳播延遲，然後才會顯示命令的結果。

- 若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 有問題嗎？ 在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。

## <a name="create-a-group-in-the-eac"></a>在 EAC 中建立群組

1. 在 EAC 中，**移至** \> [收件者**群組**]。

2. 依您的需求](../../media/ITPro-EAC-AddIcon.gif)而定，按一下 [**新增新增** ![圖示]，然後按一下 [**通訊群組**或**安全性群組**]。

3. 在 [**新增通訊群組**] 或 [**新增安全性群組**] 頁面上，設定下列設定：

   - **顯示名稱**：輸入貴組織獨有的顯示名稱，並有意義的 EOP 使用者。 顯示名稱是必要項目。

   - **別名**：輸入最多64個字元的群組別名，您的組織是唯一的。 EOP 使用者在 [To：] （電子郵件）行中輸入別名，別名會解析為群組的顯示名稱。 如果您變更別名，群組的主要 SMTP 位址也會變更，並會包含新的別名。 別名為必要項目。

   - **描述**：輸入群組的描述，以供人員瞭解群組的用途。

   - **擁有**者：根據預設，建立群組的人員是擁有者。 您**可以選擇 [新增** ![加入圖示](../../media/ITPro-EAC-AddIcon.gif)] 來新增擁有者。 所有群組都必須至少一個擁有者。

     > [!NOTE]
     > 擁有者不一定必須是群組的成員。

   - [**成員**]：使用此區段可新增群組成員，並指定使用者加入或離開群組時是否需要核准。 若要將成員新增至群組， **Add** ![請按一下 [](../../media/ITPro-EAC-AddIcon.gif)新增新增] 圖示。

4. 按一下 **[確定]** 回到原始頁面。

5. 完成後，按一下 [**儲存**] 以建立群組。 新的群組應該出現在群組清單中。

## <a name="edit-or-remove-a-group-in-the-eac"></a>編輯或移除 EAC 中的群組

1. In the EAC, navigate to **Recipients** \> **Groups**.

2. 請執行下列其中一個步驟：

   - 若要編輯群組：在群組清單中，按一下您要查看或變更的群組，然後按一下 [**編輯** ![編輯圖示](../../media/ITPro-EAC-EditIcon.gif)]。 您可以更新一般設定、新增或移除群組擁有者，並視需要新增或移除群組成員。

   - 若要移除群組：選取群組，然後按一下 [**移除** ![移除](../../media/ITPro-EAC-RemoveIcon.gif)圖示]。

3. 完成變更之後，請按一下 [**儲存**]。

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>使用遠端 Windows PowerShell 建立、編輯或移除群組

本節提供在 Exchange Online Protection PowerShell 中建立群組和變更其屬性的相關資訊。 它也顯示如何移除現有的群組。

### <a name="create-a-group-using-remote-windows-powershell"></a>使用遠端 Windows PowerShell 建立群組

這個範例會使用[New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) Cmdlet 來建立具有 itadmin 別名的通訊群組，以及名稱為 IT 系統管理員的名稱。 它也會將使用者新增為群組的成員。

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

**附注**：若要建立安全性群組而不是通訊群組，請使用`Security` *Type*參數的值。

若要確認您是否已成功建立 IT 管理員群組，請執行下列命令以顯示新群組的相關資訊：

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

如需詳細的語法及參數資訊，請參閱[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient)。

若要取得群組中的成員清單，請執行下列命令：

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

如需詳細的語法及參數資訊，請參閱[Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember)。

若要取得所有群組的完整清單，請執行下列命令：

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a>使用遠端 Windows PowerShell 變更群組的屬性

使用 PowerShell （而非 EAC）的優點是能夠變更多個群組的屬性。

以下是一些使用 Exchange Online Protection PowerShell 變更群組屬性的範例。

這個範例會使用變更西雅圖員工群組的主要 SMTP 位址（也稱為回復位址）來 sea.employees@contoso.com。

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

如需詳細的語法及參數資訊，請參閱[Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup)。

若要確認您是否已成功變更群組的屬性，請執行下列命令來確認新的值：

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

本範例會更新西雅圖 Employees 群組的所有成員。 請使用逗點分隔所有成員。

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

如需詳細的語法及參數資訊，請參閱[EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember)。

若要取得群組西雅圖員工中所有成員的清單，請執行下列命令：

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a>使用遠端 Windows PowerShell 移除群組

本範例會使用移除名為 IT 管理員的通訊群組。

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

如需詳細的語法及參數資訊，請參閱[Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup)。

若要確認群組已移除，請執行下列命令，並確認已刪除群組（在此例中為「It 系統管理員」）。

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
