---
title: 使用 PowerShell 管理 SharePoint Online 使用者和群組
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: 在本文中，您將瞭解如何使用 PowerShell 進行 Microsoft 365，以管理 SharePoint 線上使用者、群組及網站。
ms.openlocfilehash: 823c5fdc9af178a2e8ea8f0ca4c63fbfa4673dd8
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289052"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>使用 PowerShell 管理 SharePoint Online 使用者和群組

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

如果您是使用大型使用者帳戶或群組清單的 SharePoint Online 系統管理員，而且想要更容易管理，則可以使用 PowerShell Microsoft 365。

在您開始之前，本主題中的程式需要您連線至 SharePoint 線上。 如需相關指示，請參閱[連線以 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="get-a-list-of-sites-groups-and-users"></a>取得網站、群組及使用者的清單

開始管理使用者和群組之前，您必須先取得網站、群組和使用者的清單。 您可以使用這項資訊來執行本文中的範例。

使用此命令，取得您租使用者中的網站清單：

```powershell
Get-SPOSite
```

使用此命令，取得您租使用者中的群組清單：

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

使用此命令，取得您租使用者中的使用者清單：

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>將使用者新增至網站集合管理員群組

您可以使用 `Set-SPOUser` Cmdlet，將使用者新增至網站集合上的網站集合管理員清單。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

若要使用這些命令，請使用正確的名稱取代引號內的所有專案，包括 < 和 > 字元。

例如，這組命令會將 Opal Castillo (使用者名稱 opalc) 新增至 Contoso 租使用者之 ContosoTest 網站集合上的網站集合管理員清單：

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

您可以將這些命令複製並貼到記事本、將 $tenant、$site 及 $user 的變數值變更為您環境中的實際值，然後將它貼到 SharePoint Online 管理命令介面視窗中，以執行這些命令。

## <a name="add-a-user-to-other-site-collection-groups"></a>將使用者新增至其他網站集合群組

在這個工作中，我們將使用 `Add-SPOUser` Cmdlet，將使用者新增至網站集合上的 SharePoint 群組。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

例如，將 Glen Rife (使用者名稱 glenr) 新增至 contoso 租使用者之 ContosoTest 網站集合上的審計員群組：

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>建立網站集合群組

您可以使用 `New-SPOSiteGroup` Cmdlet 來建立新的 SharePoint 群組，並將其新增至網站集合。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

您可以稍後使用 Cmdlet 來更新群組內容，例如許可權層級 `Set-SPOSiteGroup` 。

例如，讓我們將 contoso 租使用者的「只查看」許可權新增至「contosotest 網站集合」的審計員群組：

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>從群組移除使用者

有時候，您必須從網站或所有網站中移除使用者。 員工可能會從一個部門移至另一個部門或離開公司。 您可以在 UI 中輕鬆執行這項作業，但是當您必須將一個網站的完整分割移至另一個網站時，就不會這麼輕鬆。

不過，使用 SharePoint 線上管理命令介面和 CSV 檔案，這是一種快速快捷的方式。 在此工作中，您將使用 Windows PowerShell 從網站集合安全性群組中移除使用者。 然後，您會使用 CSV 檔案，並從不同的網站中移除許多使用者。

我們將使用「Remove-SPOUser ' 指令指令，只從網站集合群組中移除單一 Microsoft 365 使用者，這樣就能看到命令語法。 語法的外觀如下：

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

例如，讓我們從 contoso 租使用者的 contosotest 網站集合的網站集合審計員群組中移除胡繼 Overby：

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

假設我們想要從目前所在的所有群組中移除胡繼。 以下是我們的做法：

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> 這只是一個範例。 除非您確實需要從每個群組中移除使用者，例如，如果使用者離開公司，否則不應該執行此命令。

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>自動管理大型使用者和群組清單

若要將大量帳戶新增至 SharePoint 網站並授與許可權，您可以使用 Microsoft 365 系統管理中心、個別的 PowerShell 命令，或 PowerShell CSV 檔案。 在這些選項中，CSV 檔案是自動化此工作的最快方法。

基本程式是建立 CSV 檔案，該檔案具有對應至 Windows PowerShell 腳本所需參數的標題 (欄) 。 您可以在 Excel 中輕鬆建立這類清單，然後將它匯出為 CSV 檔案。 然後，您可以使用 Windows PowerShell 腳本，逐一查看 CSV 檔案中) 的記錄 (資料列，將使用者新增至群組，並將群組新增至網站。

例如，讓我們建立 CSV 檔案，以定義網站集合、群組和許可權的群組。 接下來，我們會建立 CSV 檔案，以將使用者填入群組。 最後，我們將建立並執行簡單的 Windows PowerShell 腳本，以建立及填入群組。

第一個 CSV 檔案會將一個或多個群組新增至一或多個網站集合，並且會有下列結構：

頭：

```powershell
Site,Group,PermissionLevels
```

專案：

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

以下是範例檔案：

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

第二個 CSV 檔案會將一或多個使用者新增至一或多個群組，並將使用此結構：

頭：

```powershell
Group,LoginName,Site
```

專案：

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

以下是範例檔案：

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

在下一個步驟中，您必須將兩個 CSV 檔案儲存至您的磁片磁碟機。 以下是同時使用 CSV 檔案及新增許可權和群組成員資格的範例命令：

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

腳本會匯入 CSV 檔內容，並使用欄中的值來填入 **SPOSiteGroup** 及 **Add-SPOUser** 命令的參數。 在我們的範例中，我們會將它儲存到 theO365Admin 資料夾的磁碟機 C 上，但您可以隨意將其儲存至您想要的地方。

現在，讓我們使用相同的 CSV 檔案，移除不同網站中多個群組的一群人員。 範例命令如下：

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>產生使用者報告

您可能想要取得少量網站的簡易報表，並顯示這些網站、其許可權層級和其他屬性的使用者。 語法的外觀如下：

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

這會抓取這三個網站的資料，並將它們寫入您的本機磁片磁碟機上的文字檔。 請注意，參數-Append 會將新內容新增至現有的檔案。

例如，讓我們針對 Contoso1 承租人的 ContosoTest、TeamSite01 和 Project01 網站執行報告：

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

請注意，我們只需要變更 **$site** 變數。 **$Tenant** 變數會透過命令的所有三個執行來保持該值。

不過，如果您想要針對每個網站執行這項操作，該怎麼辦？ 您可以執行這項動作，而不必使用下列命令輸入所有網站：

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

這個報告非常簡單，您可以新增更多的程式碼，以建立包含更多詳細資訊的特定報告或報告。 不過，這會讓您瞭解如何使用 SharePoint online 管理命令介面來管理 SharePoint 線上環境中的使用者。

## <a name="see-also"></a>另請參閱

[連線 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[使用 PowerShell 管理 SharePoint Online](create-sharepoint-sites-and-add-users-with-powershell.md)

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)

[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
