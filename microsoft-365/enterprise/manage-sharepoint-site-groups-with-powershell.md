---
title: 使用 PowerShell 管理 SharePoint Online 網站群組
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
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
description: 在本文中，尋找使用 PowerShell Microsoft 365 管理 SharePoint Online 網站群組的程式。
ms.openlocfilehash: 383536a6ad5ac5742cf1e38081a9be984ce4806b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289076"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>使用 PowerShell 管理 SharePoint Online 網站群組

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

雖然您可以使用 Microsoft 365 系統管理中心，但您也可以使用 PowerShell 進行 Microsoft 365 管理 SharePoint 的線上網站群組。

## <a name="before-you-begin"></a>在您開始之前

本文中的程式需要您連線至 SharePoint。 如需相關指示，請參閱[連線以 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>View PowerShell Microsoft 365 的 SharePoint 線上模式

SharePoint Online 系統管理中心具有一些用於管理網站群組的便於使用的方法。 例如，假設您想要查看網站的群組和群組成員 `https://litwareinc.sharepoint.com/sites/finance` 。 以下是您必須執行的動作：

1. 從 SharePoint 系統管理中心，按一下 [作用中的 **網站**]，然後按一下網站的 URL。
2. 在 [網站] 頁面上，按一下位於頁面右上角的 **設定** 圖示 () ，然後按一下 [**網站許可權**]。

然後針對您想要查看的下一個網站重複此程式。

若要使用 Microsoft 365 的 PowerShell 取得群組的清單，您可以使用下列命令：

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

在 SharePoint 線上管理命令介面命令提示字元中，有兩種方式可以執行這個命令集：

- 將命令複製到記事本 (或其他文字編輯器) 中，修改 **$siteURL** 變數的值，然後選取命令，再將其貼到 SharePoint Online 管理命令介面命令提示字元中。 當您這麼做時，PowerShell 會在 **>>** 提示時停止。 按 Enter 鍵以執行 `foreach` 命令。<br/>
- 將命令複製到記事本 (或其他文字編輯器) 中，修改 **$siteURL** 變數的值，然後在適當的資料夾中，以名稱及 .ps1 副檔名儲存此文字檔。 接下來，指定 SharePoint 線上管理命令介面命令提示字元，並指定其路徑和檔案名以執行腳本。 範例命令如下：

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

在這兩種情況下，您應該會看到類似以下的內容：

![SharePoint線上網站群組](../media/SPO-site-groups.png)

這些是已為網站建立的所有群組 `https://litwareinc.sharepoint.com/sites/finance` ，以及指派給這些群組的所有使用者。 組名為黃色，可協助您將群組名稱與其成員分開。

在另一個範例中，這裡是列出所有 SharePoint Online 網站之群組和所有群組成員資格的命令集。

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```

## <a name="see-also"></a>另請參閱

[連線 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[使用 PowerShell 建立 SharePoint Online 網站並新增使用者](create-sharepoint-sites-and-add-users-with-powershell.md)

[使用 PowerShell 管理 SharePoint Online 使用者和群組](manage-sharepoint-users-and-groups-with-powershell.md)

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)

[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
