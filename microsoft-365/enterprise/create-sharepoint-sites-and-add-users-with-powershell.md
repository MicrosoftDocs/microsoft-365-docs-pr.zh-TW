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
ms.openlocfilehash: 4c4edbd68343f0eaf3a25a8c60a2af1e83b058b6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688409"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="59cf8-103">使用 PowerShell 建立 SharePoint Online 網站並新增使用者</span><span class="sxs-lookup"><span data-stu-id="59cf8-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="59cf8-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="59cf8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="59cf8-105">當您使用 Microsoft 365 的 PowerShell 建立 SharePoint 的線上網站和新增使用者時，您可以快速且重複執行工作，其速度會比您在 Microsoft 365 系統管理中心中更快。</span><span class="sxs-lookup"><span data-stu-id="59cf8-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="59cf8-106">您也可以執行不可能在 Microsoft 365 系統管理中心中執行的工作。</span><span class="sxs-lookup"><span data-stu-id="59cf8-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="59cf8-107">連線至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="59cf8-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="59cf8-108">本主題中的程式需要您連線至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="59cf8-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="59cf8-109">如需相關指示，請參閱 [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="59cf8-109">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="59cf8-110">步驟1：使用 PowerShell 建立新的網站集合</span><span class="sxs-lookup"><span data-stu-id="59cf8-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="59cf8-111">使用所提供的範例程式碼和記事本，建立多個網站，使用 PowerShell 和 .csv 檔案建立。</span><span class="sxs-lookup"><span data-stu-id="59cf8-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="59cf8-112">在此程式中，您將會以您自己的網站與租使用者特有的資訊，取代方括弧中所顯示的預留位置資訊。</span><span class="sxs-lookup"><span data-stu-id="59cf8-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="59cf8-113">此程式可讓您建立單一檔，並執行使用該檔案的單一 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="59cf8-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="59cf8-114">這會使得同時採取可重複和可遷移的動作，並避免在 SharePoint 線上管理命令介面中輸入長命令的錯誤。</span><span class="sxs-lookup"><span data-stu-id="59cf8-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="59cf8-115">此程式有兩個部分。</span><span class="sxs-lookup"><span data-stu-id="59cf8-115">There are two parts to this procedure.</span></span> <span data-ttu-id="59cf8-116">首先，您會建立 .csv 檔案，然後您將使用 PowerShell 參照該 .csv 檔案，該檔案會使用其內容來建立網站。</span><span class="sxs-lookup"><span data-stu-id="59cf8-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="59cf8-117">PowerShell Cmdlet 會匯入 .csv 檔案，並將其管線傳遞到大括弧中的迴圈，將檔案的第一行讀取為欄標頭。</span><span class="sxs-lookup"><span data-stu-id="59cf8-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="59cf8-118">PowerShell 指令程式會逐一查看餘下的記錄，為每個記錄建立新的網站集合，並根據欄標題指派網站集合的屬性。</span><span class="sxs-lookup"><span data-stu-id="59cf8-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="59cf8-119">建立 .csv 檔案</span><span class="sxs-lookup"><span data-stu-id="59cf8-119">Create a .csv file</span></span>

1. <span data-ttu-id="59cf8-120">開啟 [記事本]，並在其中貼上下列文字區塊：</span><span class="sxs-lookup"><span data-stu-id="59cf8-120">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="59cf8-121">其中 *租* 使用者是您租使用者的名稱，而 *擁有* 者是您想要授與主要網站集合管理員角色的承租人使用者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="59cf8-121">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="59cf8-122"> (您可以在使用 [記事本] 以更快的速度大量取代時，按 Ctrl + H。 ) </span><span class="sxs-lookup"><span data-stu-id="59cf8-122">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="59cf8-123">將檔案儲存在您的桌面機 **SiteCollections.csv**。</span><span class="sxs-lookup"><span data-stu-id="59cf8-123">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="59cf8-124">在使用此或任何其他 .csv 或 Windows PowerShell 腳本檔案之前，請務必確定沒有多餘或非列印字元。</span><span class="sxs-lookup"><span data-stu-id="59cf8-124">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="59cf8-125">在 Word 中開啟檔案，然後在功能區中，按一下段落圖示以顯示非列印字元。</span><span class="sxs-lookup"><span data-stu-id="59cf8-125">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="59cf8-126">不應有多餘的非列印字元。</span><span class="sxs-lookup"><span data-stu-id="59cf8-126">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="59cf8-127">例如，在檔案結尾的最後一個段落旁邊不應有任何段落標記。</span><span class="sxs-lookup"><span data-stu-id="59cf8-127">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="59cf8-128">執行 Windows PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="59cf8-128">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="59cf8-129">在 [Windows PowerShell 提示字元處，輸入或複製並貼上下列命令，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="59cf8-129">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="59cf8-130">其中 *MyAlias* 等於您的使用者別名。</span><span class="sxs-lookup"><span data-stu-id="59cf8-130">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="59cf8-131">等候 Windows PowerShell 提示重新顯示。</span><span class="sxs-lookup"><span data-stu-id="59cf8-131">Wait for the Windows PowerShell prompt to reappear.</span></span> <span data-ttu-id="59cf8-132">可能需要一兩分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="59cf8-132">It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="59cf8-133">在 [Windows PowerShell 提示字元處，輸入或複製並貼上下列 Cmdlet，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="59cf8-133">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="59cf8-134">請注意清單中的新網站集合。</span><span class="sxs-lookup"><span data-stu-id="59cf8-134">Note the new site collections in the list.</span></span> <span data-ttu-id="59cf8-135">使用我們的範例 CSV 檔案，您會看到下列網站集合： **TeamSite01**、 **Blog01**、 **Project01**及 **Community01**</span><span class="sxs-lookup"><span data-stu-id="59cf8-135">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="59cf8-136">這樣就完成了。</span><span class="sxs-lookup"><span data-stu-id="59cf8-136">That’s it.</span></span> <span data-ttu-id="59cf8-137">您已使用所建立的 .csv 檔和單一 Windows PowerShell 命令，建立多個網站集合。</span><span class="sxs-lookup"><span data-stu-id="59cf8-137">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="59cf8-138">您現在已準備好建立及指派使用者至這些網站。</span><span class="sxs-lookup"><span data-stu-id="59cf8-138">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="59cf8-139">步驟2：新增使用者和群組</span><span class="sxs-lookup"><span data-stu-id="59cf8-139">Step 2: Add users and groups</span></span>

<span data-ttu-id="59cf8-140">現在您會建立使用者，並將其新增至網站集合群組。</span><span class="sxs-lookup"><span data-stu-id="59cf8-140">Now you’re going to create users and add them to a site collection group.</span></span> <span data-ttu-id="59cf8-141">然後，您會使用 .csv 檔案大量上傳新的群組和使用者。</span><span class="sxs-lookup"><span data-stu-id="59cf8-141">You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="59cf8-142">下列程式會繼續使用範例網站 TeamSite01、Blog01、Project01 及 Community01。</span><span class="sxs-lookup"><span data-stu-id="59cf8-142">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="59cf8-143">建立 .csv 和 ps1 檔</span><span class="sxs-lookup"><span data-stu-id="59cf8-143">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="59cf8-144">開啟 [記事本]，並在其中貼上下列文字區塊：</span><span class="sxs-lookup"><span data-stu-id="59cf8-144">Open Notepad, and paste the following text block into it:</span></span><br/>

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
<br/><span data-ttu-id="59cf8-145">*承租人*會等於您的租使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="59cf8-145">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="59cf8-146">將檔案儲存至您的桌面 **GroupsAndPermissions.csv**。</span><span class="sxs-lookup"><span data-stu-id="59cf8-146">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="59cf8-147">開啟 [記事本] 的新實例，並將下列文字區塊貼到其中：</span><span class="sxs-lookup"><span data-stu-id="59cf8-147">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

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
<br/><span data-ttu-id="59cf8-148">*租*使用者等於您租使用者名稱，而使用者*名稱等於現有*使用者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="59cf8-148">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="59cf8-149">將檔案儲存至您的桌面 **Users.csv**。</span><span class="sxs-lookup"><span data-stu-id="59cf8-149">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="59cf8-150">開啟 [記事本] 的新實例，並將下列文字區塊貼到其中：</span><span class="sxs-lookup"><span data-stu-id="59cf8-150">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="59cf8-151">其中 MyAlias 等於目前登入之使用者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="59cf8-151">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="59cf8-152">將檔案儲存至您的桌面 **UsersAndGroups.ps1**。</span><span class="sxs-lookup"><span data-stu-id="59cf8-152">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="59cf8-153">這是簡單的 Windows PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="59cf8-153">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="59cf8-154">您現在已經準備好執行 UsersAndGroup.ps1 腳本，將使用者和群組新增至多個網站集合。</span><span class="sxs-lookup"><span data-stu-id="59cf8-154">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="59cf8-155">Run UsersAndGroups.ps1 script</span><span class="sxs-lookup"><span data-stu-id="59cf8-155">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="59cf8-156">回到 SharePoint 線上管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="59cf8-156">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="59cf8-157">在 [Windows PowerShell 提示字元處，輸入或複製並貼上下列命令列，然後按 Enter 鍵：</span><span class="sxs-lookup"><span data-stu-id="59cf8-157">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="59cf8-158">在確認提示字元處，按 **Y**。</span><span class="sxs-lookup"><span data-stu-id="59cf8-158">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="59cf8-159">在 [Windows PowerShell 提示字元處，輸入或複製並貼上下列命令，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="59cf8-159">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="59cf8-160">其中 *MyAlias* 等於您的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="59cf8-160">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="59cf8-161">等待提示傳回後，再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="59cf8-161">Wait for the prompt to return before moving on.</span></span> <span data-ttu-id="59cf8-162">您會先看到群組出現在建立時。</span><span class="sxs-lookup"><span data-stu-id="59cf8-162">You will first see the groups appear as they are created.</span></span> <span data-ttu-id="59cf8-163">接著，當使用者新增時，您會看到 [群組] 清單重複。</span><span class="sxs-lookup"><span data-stu-id="59cf8-163">Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="59cf8-164">請參閱</span><span class="sxs-lookup"><span data-stu-id="59cf8-164">See also</span></span>

[<span data-ttu-id="59cf8-165">連線至 SharePoint 線上 PowerShell</span><span class="sxs-lookup"><span data-stu-id="59cf8-165">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="59cf8-166">使用 PowerShell 管理 SharePoint Online 網站群組</span><span class="sxs-lookup"><span data-stu-id="59cf8-166">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="59cf8-167">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59cf8-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="59cf8-168">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="59cf8-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
