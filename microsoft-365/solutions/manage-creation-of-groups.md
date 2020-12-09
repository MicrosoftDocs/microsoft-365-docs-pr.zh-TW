---
title: 管理可建立 Microsoft 365 群組的人員
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: 瞭解如何控制可建立 Microsoft 365 群組的使用者。
ms.openlocfilehash: 3a0ac5ef48eabfd06e0df3f509c7d8e4be3cff10
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602016"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>管理可建立 Microsoft 365 群組的人員

根據預設，所有使用者都可以建立 Microsoft 365 群組。 這是建議的方法，因為它可讓使用者在不需要協助的情況下開始合作。

如果您的公司需要限制誰可以建立群組，您可以遵循本文所述的程式來執行。 當您限制誰可以建立群組時，它會影響依賴群組進行存取的所有服務，包括：

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- PowerBI (古典) 
- Web/藍圖的專案

您可以將 Microsoft 365 群組建立限制在特定安全性群組的成員。 若要設定此，您可以使用 Windows PowerShell。 本文將引導您完成必要的步驟。

本文中的步驟不會防止某些角色的成員建立群組。 Office 365 全域系統管理員可以透過任何方式建立群組，例如 Microsoft 365 系統管理中心、Planner、小組、Exchange 及 SharePoint 線上。 其他角色可以透過有限的方式建立群組，如下所列。

- Exchange 管理員： Exchange Admin center，Azure AD
- 合作夥伴第1層支援： Microsoft 365 系統管理中心、Exchange 系統管理中心、Azure AD
- 合作夥伴第2層支援： Microsoft 365 系統管理中心、Exchange 系統管理中心、Azure AD
- 目錄編寫者： Azure AD
- SharePoint 管理員： SharePoint Admin center，Azure AD
- 小組服務管理員：小組系統管理中心，Azure AD
- 使用者管理系統管理員： Microsoft 365 Admin center、Yammer、Azure AD

如果您是其中一個角色的成員，您可以為受限制的使用者建立 Microsoft 365 群組，然後將該使用者指派為群組的擁有者。

## <a name="licensing-requirements"></a>授權需求

若要管理群組的建立者，下列人員必須已指派 Azure AD Premium 授權或 Azure AD 基本 EDU 授權：

- 設定這些群組建立設定的系統管理員
- 允許建立群組的安全性群組成員

> [!NOTE]
> 如需如何指派 Azure 授權的詳細資訊，請參閱 [在 Azure Active Directory 入口網站中指派或移除授權](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) 。

下列人員不需要有指派給它們的 Azure AD Premium 或 Azure AD 基本 EDU 授權：

- 屬於 Microsoft 365 群組成員的人員，以及沒有建立其他群組的能力。

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>步驟1：為需要建立 Microsoft 365 群組的使用者建立安全性群組

您組織中只有一個安全性群組可用於控制誰可以建立群組。 不過，您可以以巢狀方式內嵌其他安全性群組，做為此群組的成員。

以上所列角色中的系統管理員不需要是此群組的成員：他們保留其建立群組的能力。

> [!IMPORTANT]
> 請務必使用 **安全性群組** 來限制誰可以建立群組。 不支援使用 Microsoft 365 群組。

1. 在系統管理中心中，移至 [ [群組] 頁面](https://admin.microsoft.com/adminportal/home#/groups)。

2. 按一下 [ **新增群組**]。

3. 選擇 [ **安全性** ] 做為「群組類型」。 請記下群組名稱！ 以便後續步驟使用。

4. 完成設定安全性群組，新增您想要在您的組織中建立群組的人員或其他安全性群組。

如需詳細指示，請參閱 [建立、編輯或刪除 Microsoft 365 admin center 中的安全性群組](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)。

## <a name="step-2-run-powershell-commands"></a>步驟 2：執行 PowerShell 命令

您必須使用預覽版本的 [ [Azure Active Directory PowerShell For Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (模組名稱 **AzureADPreview**) ，以變更群組層級來賓存取設定：

- 如果您之前尚未安裝任何版本的 Azure AD PowerShell 模組，請參閱[安裝 Azure AD 模組](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)，並遵循指示來安裝公開預覽版本。

- 如果您已安裝 Azure AD PowerShell 模組(AzureAD) 的通用版本 2.0，您必須先在 PowerShell 工作階段中執行 `Uninstall-Module AzureAD` 將其解除安裝，然後執行 `Install-Module AzureADPreview` 來安裝預覽版本。

- 如果您已安裝預覽版本，請執行 `Install-Module AzureADPreview` 以確定這是本模組的最新版本。

將下列腳本複製到文字編輯器（例如記事本）或 [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)。

取代 *\<SecurityGroupName\>* 為您建立的安全性群組名稱。 例如：

`$GroupName = "Group Creators"`

將檔案儲存為 GroupCreators.ps1。

在 [PowerShell] 視窗中，流覽至您儲存檔案的位置， (輸入 "CD <FileLocation> " ) 。

輸入下列命令以執行腳本：

`.\GroupCreators.ps1`

系統提示時，請 [使用系統管理員帳戶登入](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) 。

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = $False

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
    $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
  $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

腳本的最後一行會顯示更新的設定：

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

如果您想要變更使用的安全性群組，您可以使用新安全性群組的名稱重新執行腳本。

如果您想關閉群組建立限制，並再次允許所有使用者建立群組，請將 $GroupName 設定為 ""，並 $AllowGroupCreation 為 "True"，然後重新執行腳本。

## <a name="step-3-verify-that-it-works"></a>步驟 3：驗證命令能正常運作

變更可能需要30分鐘以上的時間才會生效。 您可以執行下列動作來驗證新的設定：

1. 使用不具備建立群組功能之人員的使用者帳戶登入 Microsoft 365。 也就是說，它們不是您所建立之安全性群組的成員，或是管理員的成員。

2. 選取 [ **Planner** ] 磚。

3. 在 Planner 中，選取左側導覽中的 [ **新增方案** ]，以建立計畫。

4. 您應該會收到一則停用計畫和群組建立的訊息。

請使用安全性群組的成員嘗試相同的程式。

> [!NOTE]
> 如果安全性群組的成員無法建立群組，請檢查他們未透過 [OWA 信箱原則](https://go.microsoft.com/fwlink/?linkid=852135)封鎖。

## <a name="related-articles"></a>相關文章

[開始使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[在 Azure Active Directory 中設定自助群組管理](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[用於設定群組設定的 Azure Active Directory Cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
