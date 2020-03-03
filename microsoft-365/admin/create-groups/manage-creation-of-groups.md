---
title: 管理能建立 Office 365 群組的使用者
f1.keywords:
- NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: 了解如何控制哪些使用者可以建立 Office 365 群組。
ms.openlocfilehash: a6016f6406b211aae216702910a696be50e1b82c
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352634"
---
# <a name="manage-who-can-create-office-365-groups"></a>管理能建立 Office 365 群組的使用者

  
因為它是很容易建立 Office 365 群組的使用者，您不許多與其建立代表其他人的要求。 根據您的業務，不過，您可能想要控制誰可以建立群組的能力。
  
本文說明如何停用建立群組 **，使用群組的所有 Office 365 服務中**的功能： 
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream
    
- StaffHub
    
- Planner
    
- PowerBI

- 藍圖
    
您可以限制 Office 365 群組建立特定的安全性群組的成員。 若要設定此，您可以使用 Windows PowerShell。 本文會引導您所需的步驟。
  
本文中的步驟，將不會阻止特定角色的成員建立群組。 Office 365 全域系統管理員可以透過任何方法，例如 Microsoft 365 系統管理中心、 規劃、 microsoft Teams、 Exchange 和 SharePoint Online 中建立群組。 其他角色可以建立透過有限表示，以下列出的群組。
        
  - Exchange 系統管理員： Exchange 系統管理中心，Azure AD
    
  - 合作夥伴第 1 層支援： Microsoft 365 系統管理中心、 Exchange 系統管理中心中，Azure AD
    
  - 合作夥伴第 2 層支援： Microsoft 365 系統管理中心、 Exchange 系統管理中心中，Azure AD
    
  - 目錄作者： Azure AD

  - SharePoint 系統管理員： SharePoint 系統管理中心內，Azure AD
  
  - Teams 服務系統管理員： Teams 系統管理中心，Azure AD
  
  - 使用者管理系統管理員： Microsoft 365 系統管理中心，Yammer，Azure AD
     
如果您是上述角色成員，即可為受限的使用者建立 Office 365 群組，然後將指派使用者為群組的擁有者。 將此角色的使用者都能建立連線的群組中 Yammer，不論可能會禁止建立任何 PowerShell 設定。

## <a name="licensing-requirements"></a>授權需求

若要管理誰能建立群組，下列人員會需要 Azure AD Premium 授權或指派給他們的 Azure AD 基本教育授權：

- 系統管理員設定這些群組建立設定
- 可以建立群組的 [安全性] 群組成員

下列人員不需要指派給他們的 Azure AD Premium 或 Azure AD 基本教育授權：

- 人員誰是 Office 365 群組的成員，以及沒有建立其他群組的能力。

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a>步驟 1：為需要建立 Office 365 群組的使用者建立安全性群組

在您的組織中只能有一個安全性群組可用來控制誰是能夠建立群組。 不過，您可以以巢狀方式內嵌其他安全性群組，做為此群組的成員。 例如，名為「Allow Group Creation」的群組即為指定的安全性群組，而名為「Microsoft Planner Users and Exchange Online Users」的群組則屬於該群組成員。

在上面所列的角色的系統管理員不需要是此群組的成員： 它們會保留其能夠建立群組。

> [!IMPORTANT]
> 請務必使用**安全性群組**來限制誰可以建立群組。 如果您嘗試使用 Office 365 群組，則成員將因 SharePoint 的安全性群組檢查而無法在當中建立群組。 
    
1. 在系統管理中心，移至 [**群組** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。

2. 按一下 [**新增群組**]。

3. 做為群組類型，請選擇 [**安全性**]。 請記下群組名稱！ 以便後續步驟使用。
  
4. 完成 [安全性] 群組中，新增人員或其他安全性群組您想要能夠貴組織中建立群組的設定
    
如需詳細指示，請參閱[建立、 編輯或刪除安全性群組在 Microsoft 365 系統管理中心](../email/create-edit-or-delete-a-security-group.md)。
  
## <a name="step-2-install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a>步驟 2： 安裝預覽版的 Azure Active Directory PowerShell 的圖表

這些程序需要 Azure Active Directory PowerShell 的預覽版本的圖表。 GA 版本將無法運作。


> [!IMPORTANT]
> 您無法在同一部電腦上安裝預覽版和 GA 版本，在同一時間。 您可以在 Windows 10、 Windows Server 2016 上安裝此模組。

  
As a best practice, we recommend  *always*  staying current: uninstall the old AzureADPreview or old AzureAD version and get the latest one. 
  
1. 在搜尋列中，輸入 Windows PowerShell。
    
2. 在**Windows PowerShell**上按一下滑鼠右鍵，然後選取 [**以管理員身分執行**。
    
    ![以「以系統管理員身分執行」方式開啟 PowerShell。](../../media/52517af8-c7b0-4c8f-b2f3-0f82f9d5ace1.png)
    
3. 使用[Set-executionpolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)RemoteSigned 之中設定原則。
    
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
  
4. 檢查已安裝的模組：
    
    ```
    Get-InstalledModule -Name "AzureAD*"
    ```

5. 若要解除安裝舊版 AzureADPreview 或 AzureAD，請執行此命令：
  
    ```
    Uninstall-Module AzureADPreview
    ```

    或
  
    ```
    Uninstall-Module AzureAD
    ```

6. To install the latest version of AzureADPreview, run this command:
  
    ```
    Install-Module AzureADPreview
    ```

    At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. 

離開的 PowerShell 中的步驟 3 中，開啟下方的視窗。
  
## <a name="step-3-run-powershell-commands"></a>步驟 3： 執行 PowerShell 命令

將下列指令碼複製到文字編輯器，例如 [記事本] 或[Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)。

取代*\<SecurityGroupName\>* 您建立的 [安全性] 群組的名稱。 例如：

`$GroupName = "Group Creators"`

將檔案儲存為 GroupCreators.ps1。 

在 PowerShell 視窗中，瀏覽至您儲存檔案的所在位置 (型別 」 CD <FileLocation>")。

執行指令碼中輸入：

`.\GroupCreators.ps1`

並[使用您系統管理員帳戶登入](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription)提示時。

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

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

指令碼的最後一行會顯示更新的設定：

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

如果在未來您想要變更所用的 [安全性] 群組，您可以重新執行指令碼以新的 [安全性] 群組的名稱。

如果您想要關閉群組建立限制，並再次允許建立群組的所有使用者，將 $GroupName 設定為 「 」 為"True"$AllowGroupCreation 並重新執行指令碼。
    
## <a name="step-4-verify-that-it-works"></a>步驟 4： 確認其運作方式

1. 請使用不具備群組建立能力的使用者帳戶登入 Office 365。 也就是說，它們不為您建立的 [安全性] 群組的成員或系統管理員。
    
2. 選取 [ **planner]** 磚。 
    
3. 在 Planner 中，選取 [建立計劃的左方導覽中的**新方案**。 
  
4. 您應該取得規劃及群組建立已停用郵件。

重試相同的程序的 [安全性] 群組的成員。

> [!NOTE]
> 如果 [安全性] 群組的成員不能建立群組，請檢查它們不在透過其[OWA 信箱原則](https://go.microsoft.com/fwlink/?linkid=852135)遭到封鎖。
    
## <a name="related-articles"></a>相關文章

[開始使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[設定 Azure Active Directory 中的自助群組管理](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[設定群組設定 azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
