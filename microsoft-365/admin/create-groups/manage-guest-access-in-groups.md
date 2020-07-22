---
title: 在 Microsoft 365 群組中管理來賓存取
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: 瞭解如何將來賓新增至 Microsoft 365 群組、查看來賓使用者，以及使用 PowerShell 來控制來賓存取。
ms.openlocfilehash: a56d9599824ac1436c6f875661bcd573c1f6b1ca
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204740"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>在 Microsoft 365 群組中管理來賓存取

根據預設，針對您的組織開啟來賓存取權 Microsoft 365 群組。 系統管理員可以控制是否允許來賓存取整個組織或個別群組的群組。

當其開啟時，群組成員可以透過網頁上的 Outlook 邀請來賓使用者加入 Microsoft 365 群組。 邀請會傳送給群組擁有者以供核准。

一旦核准，就會將來賓使用者新增至目錄和群組。

> [!Note]
> 處於原生模式或[歐盟地理](https://go.microsoft.com/fwlink/?linkid=2107357)位置的 Yammer Enterprise 網路不支援網路來賓。
> Microsoft 365 連線的 Yammer 群組目前不支援來賓存取，但您可以在 Yammer 網路中建立未連線的外部群組。 如需相關指示，請參閱[建立及管理 Yammer 中的外部群組](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups)。

群組中的來賓存取通常是用來包括 SharePoint 或小組的更廣泛案例的一部分。 這些服務有自己的來賓共用設定。 如需設定各群組、SharePoint 及小組之來賓共用的完整指示，請參閱：

- [在網站中與來賓共同作業](../../solutions/collaborate-in-site.md)
- [在小組中與來賓共同作業](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>管理群組來賓存取

如果您想要啟用或停用群組中的「來賓存取」，您可以在 Microsoft 365 系統管理中心進行。

1. 在系統管理中心中，移至 [**顯示所有** \> **設定** \> 的**組織設定**]，然後在 [**服務**] 索引標籤上，選取 [ **Microsoft 365 群組**]。
  
2. 在 [ **Microsoft 365 群組**] 頁面上，選擇您是否要讓組織外部人員存取群組資源，或讓群組擁有者將組織外部人員新增至群組。

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>從系統管理中心新增來賓至 Microsoft 365 群組

如果您的目錄中已存在來賓，您可以從 Microsoft 365 系統管理中心將其新增至您的群組。
  
1. 在系統管理中心中，移至 [**群組**  >  **群組**] 頁面。
  
2. 按一下您要新增來賓的群組，然後選取 [**成員**] 索引標籤上的 [**全部查看] 和 [管理成員**]。 
  
4. 選取 [**新增成員**]，然後選擇您要新增的客人名稱。
    
5. 選取 **[儲存]**。

如果您想要直接將來賓新增至目錄，您可以[在 azure 入口網站中新增 Azure Active directory B2B 協同作業使用者](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)。

如果您想要編輯來賓的任何資訊，可以[使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。
  
## <a name="block-guest-users-from-a-specific-group"></a>從特定群組封鎖來賓使用者

如果您想要允許來賓存取大多數群組，但要讓某些地方禁止來賓存取，您可以使用 Microsoft PowerShell 封鎖個別群組的 guest 存取。

您必須使用預覽版本的 [ [Azure Active Directory PowerShell For Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （模組名稱**AzureADPreview**）來變更群組層級來賓存取設定：

- 如果您之前尚未安裝任何版本的 Azure AD PowerShell 模組，請參閱[安裝 Azure AD 模組](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)，並遵循指示來安裝公開預覽版本。

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
    
![顯示「來賓群組存取」已設定為 false PowerShell 視窗的螢幕擷取畫面。](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>根據網域允許或封鎖來賓存取

您可以允許或封鎖使用特定網域的來賓使用者。 例如，如果您的企業（Contoso）與另一部業務（Fabrikam）有合作關係，您可以將 Fabrikam 新增至您的允許清單，讓您的使用者可以將這些來賓新增至他們的群組。

如需詳細資訊，請參閱[允許或封鎖從特定組織 B2B 使用者的邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。

## <a name="add-guests-to-the-global-address-list"></a>將客人新增至全域通訊清單

根據預設，來賓在 Exchange 全域通訊清單中不會顯示。 使用下列步驟，讓來賓在全域通訊清單中可見。 請確定來賓在 Exchange Online 系統管理中心中是可見的。 新增來賓後，可能需要較短的時間顯示出來。

執行下列動作，尋找來賓使用者的 ObjectID：

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

然後，使用 ObjectID、GivenName、姓、DisplayName 和 TelephoneNumber 的適當值來執行下列各項。

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>相關文章

[管理 Microsoft 365 系統管理中心中的群組成員資格](add-or-remove-members-from-groups.md)
  
[Azure Active Directory 存取評論](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
