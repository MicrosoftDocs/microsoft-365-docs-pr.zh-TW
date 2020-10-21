---
title: 防止來賓使用者新增至特定群組
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 瞭解如何防止來賓使用者新增至特定群組
ms.openlocfilehash: 91c7560186fb0b954075e9ff9c997b34121951cd
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651347"
---
# <a name="prevent-guest-users-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>防止來賓使用者新增至特定的 Microsoft 365 群組或 Microsoft 團隊小組

如果您想要允許來賓存取大多數群組和小組，但要讓某些地方禁止來賓存取，您可以封鎖個別群組和小組的「來賓存取」。  (封鎖來賓存取權，可透過封鎖關聯群組的 guest 存取來完成。 ) 這會防止新增來賓，但不會移除群組或小組中已存在的客人。

如果您在組織中使用敏感度標籤，我們建議您在每個群組的基礎上使用敏感度標籤來控制訪客存取。 如需如何執行此動作的詳細資訊，請 [使用敏感度標籤來保護 Microsoft 團隊、microsoft 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。 這是建議方式。

## <a name="change-group-settings-using-microsoft-powershell"></a>使用 Microsoft PowerShell 變更群組設定

您也可以使用 PowerShell，避免將新的客人加入個別群組。

您必須使用預覽版本的 [Azure Active Directory PowerShell，以](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (模組名稱 **AzureADPreview**) 才能變更群組層級來賓存取設定：

- 如果您之前尚未安裝任何版本的 Azure AD PowerShell 模組，請參閱[安裝 Azure AD 模組](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)，並遵循指示來安裝公開預覽版本。

- 如果您已安裝 Azure AD PowerShell 模組(AzureAD) 的通用版本 2.0，您必須先在 PowerShell 工作階段中執行 `Uninstall-Module AzureAD` 將其解除安裝，然後執行 `Install-Module AzureADPreview` 來安裝預覽版本。

- 如果您已安裝預覽版本，請執行 `Install-Module AzureADPreview` 以確定這是本模組的最新版本。

> [!NOTE]
> 您必須具有全域系統管理員許可權，才可執行這些命令。 

執行下列腳本，將 */<GroupName/>* 其變更為您要封鎖來賓存取的群組名稱。

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

若要驗證您的設定，請執行下列命令：

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

驗證看起來像這樣：
    
![顯示「來賓群組存取」已設定為 false PowerShell 視窗的螢幕擷取畫面。](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>根據網域允許或封鎖來賓存取

您可以允許或封鎖使用特定網域的來賓使用者。 例如，如果您的 business (Contoso) 與其他商務 (Fabrikam) 有合作關係，您可以將 Fabrikam 新增至您的允許清單，讓您的使用者可以將這些來賓新增至他們的群組。

如需詳細資訊，請參閱 [允許或封鎖從特定組織 B2B 使用者的邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。

## <a name="add-guests-to-the-global-address-list"></a>將客人新增至全域通訊清單

根據預設，來賓在 Exchange 全域通訊清單中不會顯示。 使用下列步驟，讓來賓在全域通訊清單中可見。

執行下列動作，尋找來賓使用者的 ObjectID：

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

然後，使用 ObjectID、GivenName、姓、DisplayName 和 TelephoneNumber 的適當值來執行下列各項。

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>相關文章

[管理 Microsoft 365 系統管理中心中的群組成員資格](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Azure Active Directory 存取評論](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
