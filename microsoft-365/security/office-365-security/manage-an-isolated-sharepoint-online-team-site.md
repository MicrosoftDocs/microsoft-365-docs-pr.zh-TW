---
title: 管理獨立的 SharePoint Online 小組網站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 管理隔離的 SharePoint 線上小組網站、新增使用者和群組、移除使用者和群組，以及使用自訂許可權建立 documents 子資料夾。
ms.openlocfilehash: 05e3cf742482d34c158e14253eed9d1b99c82995
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036629"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>管理獨立的 SharePoint Online 小組網站

 **摘要：** 使用這些程式來管理您的隔離 SharePoint Online 小組網站。
  
本文說明隔離 SharePoint Online 小組網站的一般管理作業。
  
## <a name="add-a-new-user"></a>新增使用者

當有人新加入網站時，您必須決定其在網站中的參與層級：
  
- 管理：將新的使用者帳戶新增至網站管理員存取群組
    
- 主動共同作業：將使用者帳戶新增至網站成員存取群組
    
- 查看：將使用者帳戶新增至網站檢視器存取群組
    
如果您是透過 Active Directory 網域服務（AD DS）來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式將適當的使用者新增至適當的訪問群組，並等待與您的訂閱同步處理。
  
如果您是透過 Microsoft 365 管理使用者帳戶和群組，您可以使用 Microsoft 365 系統管理中心或 Microsoft PowerShell:
  
- 針對 Microsoft 365 系統管理中心，使用指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組將適當的使用者新增至適當的訪問群組。
    
- 在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。 若要使用使用者主要名稱（UPN）將使用者帳戶新增至 access 群組，請使用下列 PowerShell 命令區塊：
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

若要將使用者帳戶新增至具有其顯示名稱的 access 群組，請使用下列 PowerShell 命令區塊：

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>新增群組

若要將存取權新增至整個群組，您必須決定網站中群組的所有成員的參與層級：
  
- 管理：將群組新增至網站管理員存取群組
    
- 主動共同作業：將群組新增至網站成員存取群組
    
- 查看：將群組新增至網站檢視器訪問群組
    
如果您是透過 AD DS 來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式將適當的群組新增至適當的群組，並等待與您的訂閱同步處理。
  
如果您是透過 Office 365 管理使用者帳戶和群組，您可以使用 Microsoft 365 系統管理中心或 PowerShell:
  
- 針對 Microsoft 365 系統管理中心，使用指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組將適當的群組新增至適當的訪問群組。
    
- 在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。
 然後，使用下列 PowerShell 命令：
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>移除使用者

當某人的存取權必須從網站中移除時，您可以從存取權組中移除他們目前是其成員的存取權，而不是根據其在網站中的參與權：
  
- 管理：從網站管理員存取群組中移除使用者帳戶
    
- 主動共同作業：從網站成員存取群組中移除使用者帳戶
    
- 查看：從網站檢視器存取群組中移除使用者帳戶
    
如果您是透過 AD DS 來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式從適當的訪問群組中移除適當的使用者，並等待與您的訂閱同步處理。
  
如果您是透過 Office 365 管理使用者帳戶和群組，您可以使用 Microsoft 365 系統管理中心或 PowerShell:
  
- 針對 Microsoft 365 系統管理中心，使用指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組從適當的訪問群組中移除適當的使用者。
    
- 在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。
若要使用 UPN 從存取群組中移除使用者帳戶，請使用下列 PowerShell 命令區塊：
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

若要從具有顯示名稱的 access 群組中移除使用者帳戶，請使用下列 PowerShell 命令區塊：
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>移除群組

若要移除整個群組的存取權，您可以從存取權群組中移除群組，而其目前是根據其在網站中參與的成員：
  
- 管理：從網站管理員存取群組中移除群組
    
- 使用中共同作業：從網站成員存取群組中移除群組
    
- 查看：從網站檢視器存取群組中移除群組
    
如果您是透過 Windows Server Active Directory 來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式從適當的訪問群組中移除適當的群組，並等待與您的訂閱同步處理。
  
如果您是透過 Office 365 管理使用者帳戶和群組，您可以使用 Microsoft 365 系統管理中心或 PowerShell:
  
- 針對 Microsoft 365 系統管理中心，使用指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組從適當的訪問群組中移除適當的群組。
    
- 在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。    
若要使用使用者的顯示名稱從存取群組中移除群組，請使用下列 PowerShell 命令區塊：
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>使用自訂許可權建立 documents 子資料夾

在某些情況下，隔離網站中的人員子集需要更多私人位置才能進行共同作業。 針對 SharePoint 線上網站，您可以在網站的 [檔] 資料夾中建立子資料夾，並指派自訂許可權。 沒有許可權的人員將不會看到子資料夾。
  
若要建立具有自訂許可權的 documents 子資料夾，請執行下列操作：
  
1. 登入屬於網站管理員存取群組成員的帳戶。 如需說明，請參閱[在何處登入 Microsoft 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 移至隔離的小組網站，然後按一下 [**檔**]。
    
3. 流覽至 documents 資料夾中的資料夾，該資料夾將包含具有自訂許可權的子資料夾、建立資料夾，然後開啟該資料夾。
    
4. 按一下 [共用]****。
    
5. 按一下 [**與 > Advanced**] [共用]。
    
6. 按一下 [**停止繼承許可權**]，然後按一下 **[確定]**。
    
7. 按一下 [共用]****。
    
8. 按一下 [**與 > Advanced**] [共用]。
    
9. 按一下 **[授與許可權] > 與 > 高級] 共用**。
    
10. 在 [許可權] 頁面上，按一下** \<清單中的 [網站名稱> 成員**]。
    
11. 在 [ ** \<網站名稱> 成員**] 頁面上，選取 [網站成員存取] 群組旁的核取記號，按一下 [**動作**]，按一下 [**從群組移除使用者**]，然後按一下 **[確定]**。
    
12. 若要將特定成員新增至這個子資料夾，請按一下 [**新增 > 新增使用者**]。
    
13. 在 [**共用**] 對話方塊中，輸入可共同處理子資料夾中檔案之使用者帳戶的名稱，然後按一下 [**共用**]。
    
14. 請重新整理網頁以查看新的結果。
    
15. 在左側導覽中的 [**群組**] 底下，按一下 [ ** \<網站名稱> 訪客**] 群組，然後使用步驟11-14 指定可在子資料夾中查看檔案的使用者帳戶集（視需要）。
    
16. 在左側導覽中的 [**群組**] 底下，按一下 [ ** \<網站名稱> 擁有**者] 群組，然後使用步驟11-14 指定一組可在子資料夾中管理許可權的使用者帳戶（視需要）。
    
17. 關閉瀏覽器中的 [**人員與群組**] 索引標籤。
    
## <a name="see-also"></a>另請參閱

[獨立的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)
  
[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)

[部署獨立的 SharePoint Online 小組網站](deploy-an-isolated-sharepoint-online-team-site.md)



