---
title: 管理獨立的 SharePoint Online 小組網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 摘要： 管理隔離的 SharePoint Online 小組網站與這些程序。
ms.openlocfilehash: e6ed86421ec199ce785e2daff5e9c5447939e69b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077764"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>管理獨立的 SharePoint Online 小組網站

 **摘要：** 管理隔離的 SharePoint Online 小組網站與這些程序。
  
本文說明用於隔離 SharePoint Online 小組網站的一般管理作業。
  
## <a name="add-a-new-user"></a>新增使用者

當新的人員加入網站時，您必須決定其程度站台中的參與：
  
- 管理： 將新的使用者帳戶新增至網站系統管理員存取群組
    
- 作用中的共同作業： 將使用者帳戶新增至網站成員存取群組
    
- 檢視： 將使用者帳戶新增至網站檢視者存取群組
    
如果您要管理使用者帳戶和群組透過 Active Directory 網域服務 (AD DS)，將適當的使用者新增至適當的存取群組使用一般的 AD DS 使用者和群組管理程序，並等候與您的 Office 365 同步處理訂用帳戶。
  
如果您要管理使用者帳戶和群組透過 Office 365，您可以使用 Microsoft 365 系統管理中心或 Microsoft PowerShell:
  
- 針對 Microsoft 365 系統管理中心中，使用已被指派的使用者帳戶系統管理員或公司系統管理員角色的使用者帳戶登入並使用群組，將適當的使用者新增至適當的存取群組。
    
- Powershell 中，第一個[與 PowerShell 的 Azure Active Directory 針對 Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。 若要將使用者帳戶新增至其使用者主體名稱 (UPN) 存取群組，使用下列 PowerShell 命令區塊：
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> 文字檔案，其中包含所有 PowerShell 命令和 Excel PowerShell 命令將會產生的組態工作表的群組和使用者帳戶名稱，請下載[隔離 SharePoint Online 小組網站部署套件](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。 

若要新增的使用者帳戶來存取群組，其顯示名稱，請使用下列 PowerShell 命令區塊：

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>新增新群組

若要存取整個群組，您必須決定在站台中的所有群組的成員參與的層級：
  
- 管理： 將群組新增至網站系統管理員存取群組
    
- 作用中的共同作業： 將群組新增至網站成員存取群組
    
- 檢視： 將群組新增至網站檢視者存取群組
    
如果您要管理使用者帳戶和透過 AD DS 群組，將適當的群組新增至適當的群組使用一般的 AD DS 使用者和群組管理程序，並等待同步處理您的 Office 365 訂閱。
  
如果您要管理使用者帳戶和群組透過 Office 365，您可以使用 Microsoft 365 系統管理中心或 PowerShell:
  
- 針對 Microsoft 365 系統管理中心中，使用已被指派的使用者帳戶系統管理員或公司系統管理員角色的使用者帳戶登入並使用群組，將適當的群組新增至適當的存取群組。
    
- Powershell 中，第一個[與 PowerShell 的 Azure Active Directory 針對 Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。
 然後，使用下列 PowerShell 命令：
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>移除使用者

必須從網站移除某個人的存取，當您移除這些，他們正在根據他們參與網站成員存取群組：
  
- 管理： 移除從網站系統管理員存取群組的使用者帳戶
    
- 作用中的共同作業： 移除從網站成員存取群組的使用者帳戶
    
- 檢視： 移除從網站檢視者存取群組的使用者帳戶
    
如果您要管理使用者帳戶和透過 AD DS 群組，從使用一般的 AD DS 使用者和群組管理程序適當的存取群組中移除適當的使用者，並等待同步處理您的 Office 365 訂閱。
  
如果您要管理使用者帳戶和群組透過 Office 365，您可以使用 Microsoft 365 系統管理中心或 PowerShell:
  
- 針對 Microsoft 365 系統管理中心中，使用已被指派的使用者帳戶系統管理員或公司系統管理員角色的使用者帳戶登入並使用群組，從適當的存取群組中移除適當的使用者。
    
- Powershell 中，第一個[與 PowerShell 的 Azure Active Directory 針對 Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。
若要移除其 upn 存取群組的使用者帳戶，請使用下列 PowerShell 命令區塊：
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

若要移除其顯示名稱為存取群組的使用者帳戶，請使用下列 PowerShell 命令區塊：
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>移除群組

若要移除整個群組存取，您移除群組，他們正在根據他們參與網站成員存取群組：
  
- 管理： 移除從網站系統管理員存取群組的群組
    
- 作用中的共同作業： 移除從網站成員存取群組的群組
    
- 檢視： 移除從網站檢視者存取群組的群組
    
如果您要管理使用者帳戶和透過 Windows Server Active Directory 群組，從使用一般的 AD DS 使用者和群組管理程序的適當的存取群組中移除適當的群組，並等候與您的 Office 365 進行同步處理訂用帳戶。
  
如果您要管理使用者帳戶和群組透過 Office 365，您可以使用 Microsoft 365 系統管理中心或 PowerShell:
  
- 針對 Microsoft 365 系統管理中心中，使用已被指派的使用者帳戶系統管理員或公司系統管理員角色的使用者帳戶登入並使用群組，從適當的存取群組中移除適當的群組。
    
- Powershell 中，第一個[與 PowerShell 的 Azure Active Directory 針對 Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。    
若要使用他們的顯示名稱存取群組中移除群組，請使用下列 PowerShell 命令區塊：
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>建立文件的子資料夾有自訂權限

在某些情況下，使用獨立的站台內的人員子集需要更多私人理想的共同作業。 SharePoint Online 網站，您可以在網站的文件資料夾中建立子資料夾，並指派自訂權限。 這些權限而不會看到子資料夾。
  
若要建立自訂的權限文件的子資料夾，請執行下列動作：
  
1. 是網站的系統管理員存取群組的成員帳戶登入 Office 365。 如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 移至隔離的小組網站，然後按一下 [**文件**。
    
3. 瀏覽至資料夾中的文件資料夾，將會包含子資料夾中使用的自訂權限、 建立資料夾，然後再開啟它。
    
4. 按一下 [共用]****。
    
5. 按一下 [**與 > 進階共用**]。
    
6. 按一下 [**停止繼承權限**]，然後按一下 [**確定]**。
    
7. 按一下 [共用]****。
    
8. 按一下 [**與 > 進階共用**]。
    
9. 按一下 [**授與權限 > 與 > 進階共用**]。
    
10. 在 [權限] 頁面上，按一下 [**\<網站清單中的名稱> 成員**。
    
11. 在**\<網站名稱> 成員**] 頁面上，選取之網站成員存取群組旁的核取記號、 按一下 [**動作]**、 按一下 [**移除使用者群組**]，然後按一下 [ **[確定]**。
    
12. 若要將特定成員新增至這個子資料夾，按一下 [**新 > 新增使用者**]。
    
13. 在 [**共用**] 對話方塊中，輸入使用者帳戶，可以在子資料夾中的檔案上共同作業，然後按一下 [**共用**的名稱。
    
14. 重新整理 [web] 頁面上，以查看新的結果。
    
15. 在左導覽中的**群組**] 底下按一下 [**\<網站名稱> 訪客**群組，並使用步驟 11-14 指定 （視需要），可以檢視檔案的子資料夾中的使用者帳戶的集合。
    
16. 在左導覽中的**群組**] 底下按一下 [**\<網站名稱> 擁有者**群組，並使用步驟 11-14 指定 （視需要） 可以管理的子資料夾中的權限的使用者帳戶的集合。
    
17. 關閉瀏覽器中的 [**人員與群組**] 索引標籤。
    
## <a name="see-also"></a>另請參閱

[獨立的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)。
  
[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)

[部署獨立的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)



