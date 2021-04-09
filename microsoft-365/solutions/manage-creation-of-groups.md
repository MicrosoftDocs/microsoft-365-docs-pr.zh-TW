---
title: 管理能建立 Microsoft 365 群組的使用者
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
ms.openlocfilehash: 092ff821911ef0af2b7867e1b870b68b1b6355b3
ms.sourcegitcommit: dcc6bfd228ca9070975ce9eb14574e084f9ed92c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656982"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>管理能建立 Microsoft 365 群組的使用者

根據預設，所有使用者都可以建立 Microsoft 365 群組。 這是建議的方法，因為它可讓使用者在不需要協助的情況下開始合作。

如果您的公司需要限制誰可以建立群組，您可以將 Microsoft 365 群組建立限制為特定 Microsoft 365 群組或安全性群組的成員。

如果您擔心使用者建立的小組或群組不符合您的商務標準，請考慮要求使用者完成訓練課程，然後將其新增至允許的使用者群組。

當您限制誰可以建立群組時，它會影響依賴群組進行存取的所有服務，包括：

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (傳統) 
- Web/藍圖的專案

本文中的步驟不會防止某些角色的成員建立群組。 Office 365 全域系統管理員可以透過 Microsoft 365 系統管理中心、Planner、Exchange 及 SharePoint 線上建立群組。 其他角色可以透過有限的方式建立群組，如下所列。

- Exchange 管理員： Exchange Admin center，Azure AD
- 合作夥伴第1層支援： Microsoft 365 系統管理中心、Exchange 系統管理中心、Azure AD
- 合作夥伴第2層支援： Microsoft 365 系統管理中心、Exchange 系統管理中心、Azure AD
- 目錄編寫者： Azure AD
- SharePoint 管理員： SharePoint Admin center，Azure AD
- 小組服務管理員：小組系統管理中心，Azure AD
- 使用者管理員： Microsoft 365 Admin center，Azure AD

如果您是其中一個角色的成員，您可以為受限制的使用者建立 Microsoft 365 群組，然後將該使用者指派為群組的擁有者。

## <a name="licensing-requirements"></a>授權需求

若要管理群組的建立者，下列人員必須已指派 Azure AD Premium 授權或 Azure AD 基本 EDU 授權：

- 設定這些群組建立設定的系統管理員
- 允許建立群組的群組成員

> [!NOTE]
> 如需如何指派 Azure 授權的詳細資訊，請參閱 [在 Azure Active Directory 入口網站中指派或移除授權](/azure/active-directory/fundamentals/license-users-groups) 。

下列人員不需要有指派給它們的 Azure AD Premium 或 Azure AD 基本 EDU 授權：

- 屬於 Microsoft 365 群組成員的人員，以及沒有建立其他群組的能力。

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>步驟1：為需要建立 Microsoft 365 群組的使用者建立群組

您組織中只有一個群組可以用來控制誰可以建立群組。 不過，您可以將其他群組嵌套為此群組的成員。

以上所列角色中的系統管理員不需要是此群組的成員：他們保留其建立群組的能力。

1. 在系統管理中心中，移至 [ [群組] 頁面](https://admin.microsoft.com/adminportal/home#/groups)。

2. 按一下 [ **新增群組**]。

3. 選擇您想要的群組類型。 請記下群組名稱！ 以便後續步驟使用。

4. 完成設定群組，新增您想要在您的組織中建立群組的人員或其他群組。

如需詳細指示，請參閱 [建立、編輯或刪除 Microsoft 365 admin center 中的安全性群組](../admin/email/create-edit-or-delete-a-security-group.md)。

## <a name="step-2-run-powershell-commands"></a>步驟 2：執行 PowerShell 命令

您必須使用預覽版本的 [ [Azure Active Directory PowerShell For Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) (模組名稱 **AzureADPreview**) ，以變更群組層級來賓存取設定：

- 如果您之前尚未安裝任何版本的 Azure AD PowerShell 模組，請參閱[安裝 Azure AD 模組](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)，並遵循指示來安裝公開預覽版本。

- 如果您已安裝 Azure AD PowerShell 模組(AzureAD) 的通用版本 2.0，您必須先在 PowerShell 工作階段中執行 `Uninstall-Module AzureAD` 將其解除安裝，然後執行 `Install-Module AzureADPreview` 來安裝預覽版本。

- 如果您已安裝預覽版本，請執行 `Install-Module AzureADPreview` 以確定這是本模組的最新版本。

將下列腳本複製到文字編輯器（例如記事本）或 [Windows POWERSHELL ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)。

*\<GroupName\>* 以您建立的群組名稱取代。 例如：

`$GroupName = "Group Creators"`

將檔案儲存為 GroupCreators.ps1。

在 [PowerShell] 視窗中，流覽至您儲存檔案的位置， (輸入 "CD <FileLocation> " ) 。

輸入下列命令以執行腳本：

`.\GroupCreators.ps1`

系統提示時，請 [使用系統管理員帳戶登入](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) 。

```PowerShell
$GroupName = "<GroupName>"
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

![PowerShell 腳本輸出的螢幕擷取畫面。](../media/952cd982-5139-4080-9add-24bafca0830c.png)

如果您想要變更所使用的群組，您可以使用新群組的名稱重新執行腳本。

如果您想關閉群組建立限制，並再次允許所有使用者建立群組，請將 $GroupName 設定為 ""，並 $AllowGroupCreation 為 "True"，然後重新執行腳本。

## <a name="step-3-verify-that-it-works"></a>步驟 3：驗證命令能正常運作

變更可能需要30分鐘以上的時間才會生效。 您可以執行下列動作來驗證新的設定：

1. 使用不具備建立群組功能之人員的使用者帳戶登入 Microsoft 365。 也就是說，它們不是您所建立之群組的成員，或是管理員的成員。

2. 選取 [ **Planner** ] 磚。

3. 在 Planner 中，選取左側導覽中的 [ **新增方案** ]，以建立計畫。

4. 您應該會收到一則停用計畫和群組建立的訊息。

請使用群組的成員重新嘗試相同的程式。

> [!NOTE]
> [！注意] 如果群組的成員無法建立群組，請檢查未透過 [OWA 信箱原則](/powershell/module/exchange/set-owamailboxpolicy)封鎖這些群組。

## <a name="related-topics"></a>相關主題

[共同作業管理規劃逐步](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[建立共同作業管理計畫](collaboration-governance-first.md)

[開始使用 Office 365 PowerShell](../enterprise/getting-started-with-microsoft-365-powershell.md)

[在 Azure Active Directory 中設定自助群組管理](/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[用於設定群組設定的 Azure Active Directory Cmdlet](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
