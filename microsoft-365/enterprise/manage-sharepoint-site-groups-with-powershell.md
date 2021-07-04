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
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="d578e-103">使用 PowerShell 管理 SharePoint Online 網站群組</span><span class="sxs-lookup"><span data-stu-id="d578e-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="d578e-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="d578e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d578e-105">雖然您可以使用 Microsoft 365 系統管理中心，但您也可以使用 PowerShell 進行 Microsoft 365 管理 SharePoint 的線上網站群組。</span><span class="sxs-lookup"><span data-stu-id="d578e-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d578e-106">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="d578e-106">Before you begin</span></span>

<span data-ttu-id="d578e-107">本文中的程式需要您連線至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="d578e-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="d578e-108">如需相關指示，請參閱[連線以 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="d578e-108">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="d578e-109">View PowerShell Microsoft 365 的 SharePoint 線上模式</span><span class="sxs-lookup"><span data-stu-id="d578e-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="d578e-110">SharePoint Online 系統管理中心具有一些用於管理網站群組的便於使用的方法。</span><span class="sxs-lookup"><span data-stu-id="d578e-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="d578e-111">例如，假設您想要查看網站的群組和群組成員 `https://litwareinc.sharepoint.com/sites/finance` 。</span><span class="sxs-lookup"><span data-stu-id="d578e-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="d578e-112">以下是您必須執行的動作：</span><span class="sxs-lookup"><span data-stu-id="d578e-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="d578e-113">從 SharePoint 系統管理中心，按一下 [作用中的 **網站**]，然後按一下網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="d578e-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="d578e-114">在 [網站] 頁面上，按一下位於頁面右上角的 **設定** 圖示 () ，然後按一下 [**網站許可權**]。</span><span class="sxs-lookup"><span data-stu-id="d578e-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="d578e-115">然後針對您想要查看的下一個網站重複此程式。</span><span class="sxs-lookup"><span data-stu-id="d578e-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="d578e-116">若要使用 Microsoft 365 的 PowerShell 取得群組的清單，您可以使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="d578e-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

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

<span data-ttu-id="d578e-117">在 SharePoint 線上管理命令介面命令提示字元中，有兩種方式可以執行這個命令集：</span><span class="sxs-lookup"><span data-stu-id="d578e-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="d578e-118">將命令複製到記事本 (或其他文字編輯器) 中，修改 **$siteURL** 變數的值，然後選取命令，再將其貼到 SharePoint Online 管理命令介面命令提示字元中。</span><span class="sxs-lookup"><span data-stu-id="d578e-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="d578e-119">當您這麼做時，PowerShell 會在 **>>** 提示時停止。</span><span class="sxs-lookup"><span data-stu-id="d578e-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="d578e-120">按 Enter 鍵以執行 `foreach` 命令。</span><span class="sxs-lookup"><span data-stu-id="d578e-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="d578e-121">將命令複製到記事本 (或其他文字編輯器) 中，修改 **$siteURL** 變數的值，然後在適當的資料夾中，以名稱及 .ps1 副檔名儲存此文字檔。</span><span class="sxs-lookup"><span data-stu-id="d578e-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="d578e-122">接下來，指定 SharePoint 線上管理命令介面命令提示字元，並指定其路徑和檔案名以執行腳本。</span><span class="sxs-lookup"><span data-stu-id="d578e-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="d578e-123">範例命令如下：</span><span class="sxs-lookup"><span data-stu-id="d578e-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="d578e-124">在這兩種情況下，您應該會看到類似以下的內容：</span><span class="sxs-lookup"><span data-stu-id="d578e-124">In both cases, you should see something similar to this:</span></span>

![SharePoint線上網站群組](../media/SPO-site-groups.png)

<span data-ttu-id="d578e-126">這些是已為網站建立的所有群組 `https://litwareinc.sharepoint.com/sites/finance` ，以及指派給這些群組的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="d578e-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="d578e-127">組名為黃色，可協助您將群組名稱與其成員分開。</span><span class="sxs-lookup"><span data-stu-id="d578e-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="d578e-128">在另一個範例中，這裡是列出所有 SharePoint Online 網站之群組和所有群組成員資格的命令集。</span><span class="sxs-lookup"><span data-stu-id="d578e-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d578e-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d578e-129">See also</span></span>

[<span data-ttu-id="d578e-130">連線 SharePoint 線上 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d578e-130">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[<span data-ttu-id="d578e-131">使用 PowerShell 建立 SharePoint Online 網站並新增使用者</span><span class="sxs-lookup"><span data-stu-id="d578e-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="d578e-132">使用 PowerShell 管理 SharePoint Online 使用者和群組</span><span class="sxs-lookup"><span data-stu-id="d578e-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="d578e-133">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d578e-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="d578e-134">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d578e-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
