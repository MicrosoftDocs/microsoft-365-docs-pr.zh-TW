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
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a><span data-ttu-id="f919b-103">使用 PowerShell 管理 SharePoint Online 使用者和群組</span><span class="sxs-lookup"><span data-stu-id="f919b-103">Manage SharePoint Online users and groups with PowerShell</span></span>

<span data-ttu-id="f919b-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="f919b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f919b-105">如果您是使用大型使用者帳戶或群組清單的 SharePoint Online 系統管理員，而且想要更容易管理，則可以使用 PowerShell Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="f919b-105">If you are a SharePoint Online administrator who works with large lists of user accounts or groups and wants an easier way to manage them, you can use PowerShell for Microsoft 365.</span></span>

<span data-ttu-id="f919b-106">在您開始之前，本主題中的程式需要您連線至 SharePoint 線上。</span><span class="sxs-lookup"><span data-stu-id="f919b-106">Before you begin, the procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="f919b-107">如需相關指示，請參閱[連線以 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="f919b-107">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span></span>

## <a name="get-a-list-of-sites-groups-and-users"></a><span data-ttu-id="f919b-108">取得網站、群組及使用者的清單</span><span class="sxs-lookup"><span data-stu-id="f919b-108">Get a list of sites, groups, and users</span></span>

<span data-ttu-id="f919b-109">開始管理使用者和群組之前，您必須先取得網站、群組和使用者的清單。</span><span class="sxs-lookup"><span data-stu-id="f919b-109">Before we start to manage users and groups, you need to get lists of your sites, groups, and users.</span></span> <span data-ttu-id="f919b-110">您可以使用這項資訊來執行本文中的範例。</span><span class="sxs-lookup"><span data-stu-id="f919b-110">You can then use this information to work through the example in this article.</span></span>

<span data-ttu-id="f919b-111">使用此命令，取得您租使用者中的網站清單：</span><span class="sxs-lookup"><span data-stu-id="f919b-111">Get a list of the sites in your tenant with this command:</span></span>

```powershell
Get-SPOSite
```

<span data-ttu-id="f919b-112">使用此命令，取得您租使用者中的群組清單：</span><span class="sxs-lookup"><span data-stu-id="f919b-112">Get a list of the groups in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

<span data-ttu-id="f919b-113">使用此命令，取得您租使用者中的使用者清單：</span><span class="sxs-lookup"><span data-stu-id="f919b-113">Get a list of the users in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a><span data-ttu-id="f919b-114">將使用者新增至網站集合管理員群組</span><span class="sxs-lookup"><span data-stu-id="f919b-114">Add a user to the Site Collection Administrators group</span></span>

<span data-ttu-id="f919b-115">您可以使用 `Set-SPOUser` Cmdlet，將使用者新增至網站集合上的網站集合管理員清單。</span><span class="sxs-lookup"><span data-stu-id="f919b-115">You use the `Set-SPOUser` cmdlet to add a user to the list of Site Collection Administrators on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

<span data-ttu-id="f919b-116">若要使用這些命令，請使用正確的名稱取代引號內的所有專案，包括 < 和 > 字元。</span><span class="sxs-lookup"><span data-stu-id="f919b-116">To use these commands, replace everything within the quotes, including the < and > characters, with the correct names.</span></span>

<span data-ttu-id="f919b-117">例如，這組命令會將 Opal Castillo (使用者名稱 opalc) 新增至 Contoso 租使用者之 ContosoTest 網站集合上的網站集合管理員清單：</span><span class="sxs-lookup"><span data-stu-id="f919b-117">For example, this set of commands adds Opal Castillo (user name opalc) to the list of Site Collection Administrators on the ContosoTest site collection in the Contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

<span data-ttu-id="f919b-118">您可以將這些命令複製並貼到記事本、將 $tenant、$site 及 $user 的變數值變更為您環境中的實際值，然後將它貼到 SharePoint Online 管理命令介面視窗中，以執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="f919b-118">You can copy and paste these commands into Notepad, change the variable values for $tenant, $site, and $user to actual values from your environment, and then paste this into your SharePoint Online Management Shell window to run them.</span></span>

## <a name="add-a-user-to-other-site-collection-groups"></a><span data-ttu-id="f919b-119">將使用者新增至其他網站集合群組</span><span class="sxs-lookup"><span data-stu-id="f919b-119">Add a user to other site collection groups</span></span>

<span data-ttu-id="f919b-120">在這個工作中，我們將使用 `Add-SPOUser` Cmdlet，將使用者新增至網站集合上的 SharePoint 群組。</span><span class="sxs-lookup"><span data-stu-id="f919b-120">In this task, we'll use the `Add-SPOUser` cmdlet to add a user to a SharePoint group on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

<span data-ttu-id="f919b-121">例如，將 Glen Rife (使用者名稱 glenr) 新增至 contoso 租使用者之 ContosoTest 網站集合上的審計員群組：</span><span class="sxs-lookup"><span data-stu-id="f919b-121">For example, let's add Glen Rife (user name glenr) to the Auditors group on the ContosoTest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a><span data-ttu-id="f919b-122">建立網站集合群組</span><span class="sxs-lookup"><span data-stu-id="f919b-122">Create a site collection group</span></span>

<span data-ttu-id="f919b-123">您可以使用 `New-SPOSiteGroup` Cmdlet 來建立新的 SharePoint 群組，並將其新增至網站集合。</span><span class="sxs-lookup"><span data-stu-id="f919b-123">You use the `New-SPOSiteGroup` cmdlet to create a new SharePoint group and add it to a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

<span data-ttu-id="f919b-124">您可以稍後使用 Cmdlet 來更新群組內容，例如許可權層級 `Set-SPOSiteGroup` 。</span><span class="sxs-lookup"><span data-stu-id="f919b-124">Group properties, such as permission levels, can be updated later by using the `Set-SPOSiteGroup` cmdlet.</span></span>

<span data-ttu-id="f919b-125">例如，讓我們將 contoso 租使用者的「只查看」許可權新增至「contosotest 網站集合」的審計員群組：</span><span class="sxs-lookup"><span data-stu-id="f919b-125">For example, let's add the Auditors group with View Only permissions to the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a><span data-ttu-id="f919b-126">從群組移除使用者</span><span class="sxs-lookup"><span data-stu-id="f919b-126">Remove users from a group</span></span>

<span data-ttu-id="f919b-127">有時候，您必須從網站或所有網站中移除使用者。</span><span class="sxs-lookup"><span data-stu-id="f919b-127">Sometimes you have to remove a user from a site or even all sites.</span></span> <span data-ttu-id="f919b-128">員工可能會從一個部門移至另一個部門或離開公司。</span><span class="sxs-lookup"><span data-stu-id="f919b-128">Perhaps the employee moves from one division to another or leaves the company.</span></span> <span data-ttu-id="f919b-129">您可以在 UI 中輕鬆執行這項作業，但是當您必須將一個網站的完整分割移至另一個網站時，就不會這麼輕鬆。</span><span class="sxs-lookup"><span data-stu-id="f919b-129">You can do this for one employee easily in the UI, but this is not easily done when you have to move a complete division from one site to another.</span></span>

<span data-ttu-id="f919b-130">不過，使用 SharePoint 線上管理命令介面和 CSV 檔案，這是一種快速快捷的方式。</span><span class="sxs-lookup"><span data-stu-id="f919b-130">However by using the SharePoint Online Management Shell and CSV files, this is fast and easy.</span></span> <span data-ttu-id="f919b-131">在此工作中，您將使用 Windows PowerShell 從網站集合安全性群組中移除使用者。</span><span class="sxs-lookup"><span data-stu-id="f919b-131">In this task, you'll use Windows PowerShell to remove a user from a site collection security group.</span></span> <span data-ttu-id="f919b-132">然後，您會使用 CSV 檔案，並從不同的網站中移除許多使用者。</span><span class="sxs-lookup"><span data-stu-id="f919b-132">Then you'll use a CSV file and remove lots of users from different sites.</span></span>

<span data-ttu-id="f919b-133">我們將使用「Remove-SPOUser ' 指令指令，只從網站集合群組中移除單一 Microsoft 365 使用者，這樣就能看到命令語法。</span><span class="sxs-lookup"><span data-stu-id="f919b-133">We'll be using the 'Remove-SPOUser' cmdlet to remove a single Microsoft 365 user from a site collection group just so we can see the command syntax.</span></span> <span data-ttu-id="f919b-134">語法的外觀如下：</span><span class="sxs-lookup"><span data-stu-id="f919b-134">Here is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

<span data-ttu-id="f919b-135">例如，讓我們從 contoso 租使用者的 contosotest 網站集合的網站集合審計員群組中移除胡繼 Overby：</span><span class="sxs-lookup"><span data-stu-id="f919b-135">For example, let's remove Bobby Overby from the site collection Auditors group in the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

<span data-ttu-id="f919b-136">假設我們想要從目前所在的所有群組中移除胡繼。</span><span class="sxs-lookup"><span data-stu-id="f919b-136">Suppose we wanted to remove Bobby from all the groups he is currently in.</span></span> <span data-ttu-id="f919b-137">以下是我們的做法：</span><span class="sxs-lookup"><span data-stu-id="f919b-137">Here is how we would do that:</span></span>

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> <span data-ttu-id="f919b-138">這只是一個範例。</span><span class="sxs-lookup"><span data-stu-id="f919b-138">This is just an example.</span></span> <span data-ttu-id="f919b-139">除非您確實需要從每個群組中移除使用者，例如，如果使用者離開公司，否則不應該執行此命令。</span><span class="sxs-lookup"><span data-stu-id="f919b-139">You should not run this command unless you really have to remove a user from every group, for example if the user leaves the company.</span></span>

## <a name="automate-management-of-large-lists-of-users-and-groups"></a><span data-ttu-id="f919b-140">自動管理大型使用者和群組清單</span><span class="sxs-lookup"><span data-stu-id="f919b-140">Automate management of large lists of users and groups</span></span>

<span data-ttu-id="f919b-141">若要將大量帳戶新增至 SharePoint 網站並授與許可權，您可以使用 Microsoft 365 系統管理中心、個別的 PowerShell 命令，或 PowerShell CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="f919b-141">To add a large number of accounts to SharePoint sites and give them permissions, you can use the Microsoft 365 admin center, individual PowerShell commands, or PowerShell an a CSV file.</span></span> <span data-ttu-id="f919b-142">在這些選項中，CSV 檔案是自動化此工作的最快方法。</span><span class="sxs-lookup"><span data-stu-id="f919b-142">Of these choices, the CSV file is the fastest way to automate this task.</span></span>

<span data-ttu-id="f919b-143">基本程式是建立 CSV 檔案，該檔案具有對應至 Windows PowerShell 腳本所需參數的標題 (欄) 。</span><span class="sxs-lookup"><span data-stu-id="f919b-143">The basic process is to create a CSV file that has headers (columns) that correspond to the parameters that the Windows PowerShell script needs.</span></span> <span data-ttu-id="f919b-144">您可以在 Excel 中輕鬆建立這類清單，然後將它匯出為 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="f919b-144">You can easily create such a list in Excel and then export it as a CSV file.</span></span> <span data-ttu-id="f919b-145">然後，您可以使用 Windows PowerShell 腳本，逐一查看 CSV 檔案中) 的記錄 (資料列，將使用者新增至群組，並將群組新增至網站。</span><span class="sxs-lookup"><span data-stu-id="f919b-145">Then, you use a Windows PowerShell script to iterate through records (rows) in the CSV file, adding the users to groups and the groups to sites.</span></span>

<span data-ttu-id="f919b-146">例如，讓我們建立 CSV 檔案，以定義網站集合、群組和許可權的群組。</span><span class="sxs-lookup"><span data-stu-id="f919b-146">For example, let's create a CSV file to define a group of site collections, groups, and permissions.</span></span> <span data-ttu-id="f919b-147">接下來，我們會建立 CSV 檔案，以將使用者填入群組。</span><span class="sxs-lookup"><span data-stu-id="f919b-147">Next, we will create a CSV file to populate the groups with users.</span></span> <span data-ttu-id="f919b-148">最後，我們將建立並執行簡單的 Windows PowerShell 腳本，以建立及填入群組。</span><span class="sxs-lookup"><span data-stu-id="f919b-148">Finally, we will create and run a simple Windows PowerShell script that creates and populates the groups.</span></span>

<span data-ttu-id="f919b-149">第一個 CSV 檔案會將一個或多個群組新增至一或多個網站集合，並且會有下列結構：</span><span class="sxs-lookup"><span data-stu-id="f919b-149">The first CSV file will add one or more groups to one or more site collections and will have this structure:</span></span>

<span data-ttu-id="f919b-150">頭：</span><span class="sxs-lookup"><span data-stu-id="f919b-150">Header:</span></span>

```powershell
Site,Group,PermissionLevels
```

<span data-ttu-id="f919b-151">專案：</span><span class="sxs-lookup"><span data-stu-id="f919b-151">Item:</span></span>

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

<span data-ttu-id="f919b-152">以下是範例檔案：</span><span class="sxs-lookup"><span data-stu-id="f919b-152">Here is an example file:</span></span>

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

<span data-ttu-id="f919b-153">第二個 CSV 檔案會將一或多個使用者新增至一或多個群組，並將使用此結構：</span><span class="sxs-lookup"><span data-stu-id="f919b-153">The second CSV file will add one or more users to one or more groups and will have this structure:</span></span>

<span data-ttu-id="f919b-154">頭：</span><span class="sxs-lookup"><span data-stu-id="f919b-154">Header:</span></span>

```powershell
Group,LoginName,Site
```

<span data-ttu-id="f919b-155">專案：</span><span class="sxs-lookup"><span data-stu-id="f919b-155">Item:</span></span>

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

<span data-ttu-id="f919b-156">以下是範例檔案：</span><span class="sxs-lookup"><span data-stu-id="f919b-156">Here is an example file:</span></span>

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

<span data-ttu-id="f919b-157">在下一個步驟中，您必須將兩個 CSV 檔案儲存至您的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="f919b-157">For the next step, you must have the two CSV files saved to your drive.</span></span> <span data-ttu-id="f919b-158">以下是同時使用 CSV 檔案及新增許可權和群組成員資格的範例命令：</span><span class="sxs-lookup"><span data-stu-id="f919b-158">Here are example commands that use both CSV files and to add permissions and group membership:</span></span>

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

<span data-ttu-id="f919b-159">腳本會匯入 CSV 檔內容，並使用欄中的值來填入 **SPOSiteGroup** 及 **Add-SPOUser** 命令的參數。</span><span class="sxs-lookup"><span data-stu-id="f919b-159">The script imports the CSV file contents and uses the values in the columns to populate the parameters of the **New-SPOSiteGroup** and **Add-SPOUser** commands.</span></span> <span data-ttu-id="f919b-160">在我們的範例中，我們會將它儲存到 theO365Admin 資料夾的磁碟機 C 上，但您可以隨意將其儲存至您想要的地方。</span><span class="sxs-lookup"><span data-stu-id="f919b-160">In our example, we are saving this to theO365Admin folder on drive C, but you can save it wherever you want.</span></span>

<span data-ttu-id="f919b-161">現在，讓我們使用相同的 CSV 檔案，移除不同網站中多個群組的一群人員。</span><span class="sxs-lookup"><span data-stu-id="f919b-161">Now, let's remove a bunch of people for several groups in different sites using the same CSV file.</span></span> <span data-ttu-id="f919b-162">範例命令如下：</span><span class="sxs-lookup"><span data-stu-id="f919b-162">Here is an example command:</span></span>

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a><span data-ttu-id="f919b-163">產生使用者報告</span><span class="sxs-lookup"><span data-stu-id="f919b-163">Generate user reports</span></span>

<span data-ttu-id="f919b-164">您可能想要取得少量網站的簡易報表，並顯示這些網站、其許可權層級和其他屬性的使用者。</span><span class="sxs-lookup"><span data-stu-id="f919b-164">You might want to get a simple report for a few sites and display the users for those sites, their permission level, and other properties.</span></span> <span data-ttu-id="f919b-165">語法的外觀如下：</span><span class="sxs-lookup"><span data-stu-id="f919b-165">This is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="f919b-166">這會抓取這三個網站的資料，並將它們寫入您的本機磁片磁碟機上的文字檔。</span><span class="sxs-lookup"><span data-stu-id="f919b-166">This will grab the data for these three sites and write them to a text file on your local drive.</span></span> <span data-ttu-id="f919b-167">請注意，參數-Append 會將新內容新增至現有的檔案。</span><span class="sxs-lookup"><span data-stu-id="f919b-167">Note that the parameter –Append will add new content to an existing file.</span></span>

<span data-ttu-id="f919b-168">例如，讓我們針對 Contoso1 承租人的 ContosoTest、TeamSite01 和 Project01 網站執行報告：</span><span class="sxs-lookup"><span data-stu-id="f919b-168">For example, let's run a report on the ContosoTest, TeamSite01, and Project01 sites for the Contoso1 tenant:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="f919b-169">請注意，我們只需要變更 **$site** 變數。</span><span class="sxs-lookup"><span data-stu-id="f919b-169">Note that we had to change only the **$site** variable.</span></span> <span data-ttu-id="f919b-170">**$Tenant** 變數會透過命令的所有三個執行來保持該值。</span><span class="sxs-lookup"><span data-stu-id="f919b-170">The **$tenant** variable keeps its value through all three runs of the command.</span></span>

<span data-ttu-id="f919b-171">不過，如果您想要針對每個網站執行這項操作，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="f919b-171">However, what if you wanted to do this for every site?</span></span> <span data-ttu-id="f919b-172">您可以執行這項動作，而不必使用下列命令輸入所有網站：</span><span class="sxs-lookup"><span data-stu-id="f919b-172">You can do this without having to type all those websites by using this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="f919b-173">這個報告非常簡單，您可以新增更多的程式碼，以建立包含更多詳細資訊的特定報告或報告。</span><span class="sxs-lookup"><span data-stu-id="f919b-173">This report is fairly simple, and you can add more code to create more specific reports or reports that include more detailed information.</span></span> <span data-ttu-id="f919b-174">不過，這會讓您瞭解如何使用 SharePoint online 管理命令介面來管理 SharePoint 線上環境中的使用者。</span><span class="sxs-lookup"><span data-stu-id="f919b-174">But this should give you an idea of how to use the SharePoint Online Management Shell to manage users in the SharePoint Online environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f919b-175">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f919b-175">See also</span></span>

[<span data-ttu-id="f919b-176">連線 SharePoint 線上 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f919b-176">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[<span data-ttu-id="f919b-177">使用 PowerShell 管理 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f919b-177">Manage SharePoint Online with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="f919b-178">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f919b-178">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="f919b-179">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f919b-179">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
