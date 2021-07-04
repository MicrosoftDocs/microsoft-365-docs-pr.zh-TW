---
title: 使用 PowerShell 建立 SharePoint Online 網站並新增使用者
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: 摘要：使用 PowerShell 建立新的 SharePoint Online 網站，然後將使用者和群組新增至這些網站。
ms.openlocfilehash: 0c363df3edd40d810a0d8ca63090c0fec4c1c155
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288656"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>使用 PowerShell 建立 SharePoint Online 網站並新增使用者

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

當您使用 PowerShell 來 Microsoft 365 建立 SharePoint 的線上網站及新增使用者時，您可以快速和重複執行工作，其速度會比您在 Microsoft 365 系統管理中心中更快。 您也可以執行不可能在 Microsoft 365 系統管理中心中執行的工作。

## <a name="connect-to-sharepoint-online"></a>連線至 SharePoint Online

本主題中的程式需要您連線至 SharePoint。 如需相關指示，請參閱[連線以 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="step-1-create-new-site-collections-using-powershell"></a>步驟1：使用 PowerShell 建立新的網站集合

使用 PowerShell 和您使用提供之範例程式碼和記事本所建立的 .csv 檔案，建立多個網站。 在此程式中，您將會以您自己的網站與租使用者特有的資訊，取代方括弧中所顯示的預留位置資訊。 此程式可讓您建立單一檔，並執行使用該檔案的單一 PowerShell 命令。 這會使得同時採取可重複和可遷移的動作，並避免在 SharePoint 線上管理命令介面中輸入長命令的錯誤。 此程式有兩個部分。 首先，您會建立 .csv 檔案，然後使用 PowerShell 參照該 .csv 檔案，該檔案會使用其內容來建立網站。

PowerShell Cmdlet 會匯入 .csv 檔案，並將其管線傳遞到大括弧中的迴圈，該括弧會將檔案的第一行讀取為欄標頭。 PowerShell 指令程式會逐一查看餘下的記錄，為每個記錄建立新的網站集合，並根據欄標題指派網站集合的屬性。

### <a name="create-a-csv-file"></a>建立 .csv 檔

> [!NOTE]
> 資源配額參數只能在傳統網站上運作。 如果您在新式網站上使用此參數，則可能會收到警告訊息，告知它已被取代。

1. 開啟記事本，並將下列文字區塊貼入其中：

   ```powershell
   Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
   ```

   其中 *租* 使用者是您租使用者的名稱，而 *擁有* 者是您想要授與主要網站集合管理員角色的承租人使用者的使用者名稱。

    (您可以在使用記事本大量取代時，按 Ctrl + H。 ) 

2. 將檔案儲存在您的桌面機 **SiteCollections.csv**。

> [!TIP]
> 使用此或任何其他 .csv 或 Windows PowerShell 腳本檔案之前，請務必確定沒有多餘或非列印字元。 在 Word 中開啟檔案，然後在功能區中，按一下段落圖示以顯示非列印字元。 不應有多餘的非列印字元。 例如，在檔案結尾的最後一個段落旁邊不應有任何段落標記。

### <a name="run-the-windows-powershell-command"></a>執行 Windows PowerShell 命令

1. 在 Windows PowerShell 提示字元處，輸入或複製並貼上下列命令，然後按 enter：

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
   ```

   其中 *MyAlias* 等於您的使用者別名。

2. 等候 Windows PowerShell 提示重新顯示。 可能需要一兩分鐘的時間。

3. 在 Windows PowerShell 提示字元處，輸入或複製並貼上下列 Cmdlet，然後按 enter：

   ```powershell
   Get-SPOSite -Detailed | Format-Table -AutoSize
   ```

4. 請注意清單中的新網站集合。 使用我們的範例 CSV 檔案，您會看到下列網站集合： **TeamSite01**、 **Blog01**、 **Project01** 及 **Community01**

這樣就完成了。 您已經使用您建立的 .csv 檔及單一 Windows PowerShell 命令建立多個網站集合。 您現在已準備好建立及指派使用者至這些網站。

## <a name="step-2-add-users-and-groups"></a>步驟2：新增使用者和群組

現在您會建立使用者，並將其新增至網站集合群組。 然後您會使用 .csv 檔案大量上傳新的群組和使用者。

下列程式會繼續使用範例網站 TeamSite01、Blog01、Project01 及 Community01。

### <a name="create-csv-and-ps1-files"></a>建立 .csv 和 .ps1 檔

1. 開啟記事本，並將下列文字區塊貼入其中：

   ```powershell
   Site,Group,PermissionLevels
   https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
   https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
   https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
   https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
   https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
   https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
   https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
   https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
   ```

   *承租人* 會等於您的租使用者名稱。

2. 將檔案儲存至您的桌面 **GroupsAndPermissions.csv**。

3. 開啟記事本的新實例，並將下列文字區塊貼入其中：

   ```powershell
   Group,LoginName,Site
   Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
   Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
   Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
   XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
   XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
   Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
   Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
   Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
   ```

   *租* 使用者等於您租使用者名稱，而使用者 *名稱等於現有* 使用者的使用者名稱。

4. 將檔案儲存至您的桌面 **Users.csv**。

5. 開啟記事本的新實例，並將下列文字區塊貼入其中：

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
   Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
   ```

   其中 MyAlias 等於目前登入之使用者的使用者名稱。

6. 將檔案儲存至您的桌面 **UsersAndGroups.ps1**。 這是簡單的 Windows PowerShell 腳本。

您現在已經準備好執行 UsersAndGroup.ps1 腳本，將使用者和群組新增至多個網站集合。

### <a name="run-usersandgroupsps1-script"></a>Run UsersAndGroups.ps1 script

1. 回到 SharePoint 線上管理命令介面。

2. 在 Windows PowerShell 提示字元處，輸入或複製並貼上下列命令列，然後按 enter 鍵：

   ```powershell
   Set-ExecutionPolicy Bypass
   ```

3. 在確認提示字元處，按 **Y**。

4. 在 Windows PowerShell 提示字元處，輸入或複製並貼上下列命令，然後按 enter：

   ```powershell
   c:\users\MyAlias\desktop\UsersAndGroups.ps1
   ```

   其中 *MyAlias* 等於您的使用者名稱。

5. 等待提示傳回後，再繼續進行。 您會先看到群組出現在建立時。 接著，當使用者新增時，您會看到 [群組] 清單重複。

## <a name="see-also"></a>另請參閱

[連線 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[使用 PowerShell 管理 SharePoint Online 網站群組](manage-sharepoint-site-groups-with-powershell.md)

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)

[開始使用適用於 Microsoft 365 的 PowerShell](getting-started-with-microsoft-365-powershell.md)
