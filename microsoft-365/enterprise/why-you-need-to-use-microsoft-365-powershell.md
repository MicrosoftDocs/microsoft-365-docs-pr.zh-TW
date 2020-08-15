---
title: 為什麼您需要使用適用於 Microsoft 365 的 PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 摘要：瞭解為何您必須使用 PowerShell 來管理 Microsoft 365，在某些情況下更有效率，在其他情況下也是必要的。
ms.openlocfilehash: 7220356cd79b03674661ace386fd1d38a7e39587
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688276"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="5b019-103">為什麼您需要使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b019-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="5b019-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="5b019-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5b019-105">使用 Microsoft 365 系統管理中心，您不僅可以管理您的 Microsoft 365 使用者帳戶和授權，還可以管理 Microsoft 365 服務，例如 Exchange Online、小組和 SharePoint 線上。</span><span class="sxs-lookup"><span data-stu-id="5b019-105">With the Microsoft 365 admin center, you can not only manage your Microsoft 365 user accounts and licenses, but you can also manage your Microsoft 365 services such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="5b019-106">不過，您也可以使用 PowerShell 命令管理這些元素，充分運用命令列及指令碼語言環境，以取得速度、自動化和其他功能。</span><span class="sxs-lookup"><span data-stu-id="5b019-106">However, you can also manage these elements with PowerShell commands, taking advantage of a command-line and scripting language environment for speed, automation, and additional capability.</span></span>
  
<span data-ttu-id="5b019-107">在本文中，我們將顯示您可以使用 PowerShell 來管理 Microsoft 365 的方式：</span><span class="sxs-lookup"><span data-stu-id="5b019-107">In this article, we'll show you these ways in which you can use PowerShell to manage Microsoft 365:</span></span>
  
- <span data-ttu-id="5b019-108">顯示您使用 Microsoft 365 系統管理中心看不到的其他資訊</span><span class="sxs-lookup"><span data-stu-id="5b019-108">Reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="5b019-109">設定 PowerShell 的功能和設定</span><span class="sxs-lookup"><span data-stu-id="5b019-109">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="5b019-110">執行大量作業</span><span class="sxs-lookup"><span data-stu-id="5b019-110">Perform bulk operations</span></span>
    
- <span data-ttu-id="5b019-111">篩選資料</span><span class="sxs-lookup"><span data-stu-id="5b019-111">Filtering data</span></span>
    
- <span data-ttu-id="5b019-112">列印或儲存資料</span><span class="sxs-lookup"><span data-stu-id="5b019-112">Print or save data</span></span>
    
- <span data-ttu-id="5b019-113">跨服務管理</span><span class="sxs-lookup"><span data-stu-id="5b019-113">Manage across services</span></span>
    
<span data-ttu-id="5b019-114">開始之前，請先瞭解 Microsoft 365 的 PowerShell 是一組 Windows PowerShell 模組，也就是 Windows 服務和平臺的命令列環境。</span><span class="sxs-lookup"><span data-stu-id="5b019-114">Before you begin, understand that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="5b019-115">此環境會建立命令介面語言，可使用其他模組擴充，並提供執行簡易或複雜命令或腳本的方式。</span><span class="sxs-lookup"><span data-stu-id="5b019-115">This environment creates a command shell language that can be extended with additional modules and provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="5b019-116">例如，在您安裝 Microsoft 365 模組的 PowerShell 並聯機至您的 Microsoft 365 訂閱後，您可以執行此命令來列出 Microsoft Exchange Online 的所有使用者信箱：</span><span class="sxs-lookup"><span data-stu-id="5b019-116">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run this command to list all of the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="5b019-117">您也可以使用 Microsoft 365 系統管理中心輕鬆完成信箱清單，但是計算所有 web 應用程式之所有網站的所有清單中的專案數，無法輕易完成。</span><span class="sxs-lookup"><span data-stu-id="5b019-117">Getting the list of mailboxes can also be easily done using the Microsoft 365 admin center, but counting the number of items in all of the lists for all of the sites for all of your web apps cannot be easily done.</span></span>
  
<span data-ttu-id="5b019-118">請注意，Microsoft 365 的 PowerShell 設計為增強和增強您管理 Microsoft 365 的能力，而不是取代 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="5b019-118">Please note that PowerShell for Microsoft 365 is designed to augment and enhance your ability to manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="5b019-119">身為系統管理員，您必須至少使用 Microsoft 365 的 PowerShell，因為某些設定程式只能使用 Microsoft 365 命令的 PowerShell 進行。</span><span class="sxs-lookup"><span data-stu-id="5b019-119">As an administrator, you must become at least comfortable with using PowerShell for Microsoft 365 because there are some configuration procedures that can only be done with PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="5b019-120">在這些情況下，您必須了解如何：</span><span class="sxs-lookup"><span data-stu-id="5b019-120">In these cases, you will be required to understand how to:</span></span>
  
- <span data-ttu-id="5b019-121">安裝 Microsoft 365 模組的 PowerShell (每個系統管理員電腦) 都只會執行一次。</span><span class="sxs-lookup"><span data-stu-id="5b019-121">Install the PowerShell for Microsoft 365 modules (done only once for each administrator computer).</span></span>
    
- <span data-ttu-id="5b019-122">連線至您的 Microsoft 365 訂閱 (每個 PowerShell 會話) 都會執行一次。</span><span class="sxs-lookup"><span data-stu-id="5b019-122">Connect to your Microsoft 365 subscription (done once for each PowerShell session).</span></span>
    
- <span data-ttu-id="5b019-123">收集為 Microsoft 365 命令執行必要 PowerShell 所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="5b019-123">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="5b019-124">成功執行 Microsoft 365 命令的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5b019-124">Run the PowerShell for Microsoft 365 commands successfully.</span></span>
    
<span data-ttu-id="5b019-125">了解這些基本技術之後，您不需要使用 **Get-mailbox** 命令列出信箱使用者，也不需要了解如何建立新命令 (例如前一個命令來計算所有 Web 應用程式之所有網站的所有清單中的所有項目)。</span><span class="sxs-lookup"><span data-stu-id="5b019-125">After learning these basic skills, you are not required to list your mailbox users with **Get-Mailbox** command, nor are you required to understand how to create a new command like the previous one to count all the items in all the lists for all of the sites for all of your web apps.</span></span> <span data-ttu-id="5b019-126">Microsoft 和系統管理員群組可以視需要協助您。</span><span class="sxs-lookup"><span data-stu-id="5b019-126">Microsoft and the community of administrators can help you with that as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="5b019-127">Microsoft 365 PowerShell 會顯示您無法使用 Microsoft 365 系統管理中心所看到的其他資訊</span><span class="sxs-lookup"><span data-stu-id="5b019-127">PowerShell for Microsoft 365 can reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="5b019-128">Microsoft 365 系統管理中心會顯示許多有用的資訊，但這不意味著它會顯示 Microsoft 365 儲存在使用者、授權、信箱和網站上的所有可能資訊。</span><span class="sxs-lookup"><span data-stu-id="5b019-128">The Microsoft 365 admin center displays a lot of useful information, but that doesn't mean that it displays all the possible information that Microsoft 365 stores on users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="5b019-129">以下是 Microsoft 365 系統管理中心中 **使用者和群組** 的範例：</span><span class="sxs-lookup"><span data-stu-id="5b019-129">Here is an example for **users and groups** in the Microsoft 365 admin center:</span></span>
  
![Microsoft 365 系統管理中心中使用者和群組的顯示範例。](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="5b019-131">在許多用途中，這會顯示您需要知道的資訊。</span><span class="sxs-lookup"><span data-stu-id="5b019-131">For many purposes, this displays the information you need to know.</span></span> <span data-ttu-id="5b019-132">不過，您有時需要更多的資訊。</span><span class="sxs-lookup"><span data-stu-id="5b019-132">However, there are times when you need more.</span></span> <span data-ttu-id="5b019-133">例如，Microsoft 365 授權 (和 Microsoft 365 功能可供使用者) 因使用者的地理位置而異。</span><span class="sxs-lookup"><span data-stu-id="5b019-133">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depend in part on that user's geographic location.</span></span> <span data-ttu-id="5b019-134">您可延伸到美國使用者的原則和功能，與您可延伸到印度或比利時使用者的原則和功能可能不大一樣。</span><span class="sxs-lookup"><span data-stu-id="5b019-134">The policies and features you can extend to a user who lives in the United States might not be the same as the policies and features you can extend to a user who lives in India or in Belgium.</span></span> <span data-ttu-id="5b019-135">您可以使用 Microsoft 365 系統管理中心，使用下列步驟來判斷使用者的地理位置：</span><span class="sxs-lookup"><span data-stu-id="5b019-135">You can use the Microsoft 365 admin center to determine a user's geographic location with these steps:</span></span>
  
1. <span data-ttu-id="5b019-136">連按兩下使用者的 **[顯示名稱]** 。</span><span class="sxs-lookup"><span data-stu-id="5b019-136">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="5b019-137">在使用者內容顯示窗格中，按一下 **[詳細資料]** 。</span><span class="sxs-lookup"><span data-stu-id="5b019-137">In the user properties display pane, click **details**.</span></span>
    
3. <span data-ttu-id="5b019-138">在詳細資料顯示中，按一下 **[其他詳細資料]** 。</span><span class="sxs-lookup"><span data-stu-id="5b019-138">In the details display, click **additional details**.</span></span>
    
4. <span data-ttu-id="5b019-139">向下捲動，直到您看到 **[國家或地區]** 標題為止。</span><span class="sxs-lookup"><span data-stu-id="5b019-139">Scroll down until you see the heading **Country or region**:</span></span>
    
     ![Microsoft 365 系統管理中心中使用者之地區資訊的範例。](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="5b019-141">在一張紙上寫下使用者的顯示名稱和位置，或複製並貼到 [記事本]。</span><span class="sxs-lookup"><span data-stu-id="5b019-141">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span> 
    
<span data-ttu-id="5b019-142">您必須為每位使用者重複此程序。</span><span class="sxs-lookup"><span data-stu-id="5b019-142">You must repeat this procedure for each user.</span></span> <span data-ttu-id="5b019-143">對於許多使用者，這可能是冗長乏味的工作。</span><span class="sxs-lookup"><span data-stu-id="5b019-143">For many users, this can be a tedious task.</span></span> <span data-ttu-id="5b019-144">使用 Microsoft 365 的 PowerShell，您可以使用下列命令，為所有使用者顯示此資訊：</span><span class="sxs-lookup"><span data-stu-id="5b019-144">With PowerShell for Microsoft 365, you can display this information for all of your users with the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="5b019-145">PowerShell Core 不支援適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組和名稱有 **Msol** 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5b019-145">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="5b019-146">若要繼續使用這些 Cmdlet，您必須從 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="5b019-146">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="5b019-147">以下是顯示範例：</span><span class="sxs-lookup"><span data-stu-id="5b019-147">Here is an example of the display:</span></span>
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

> [!TIP]
>  <span data-ttu-id="5b019-148">此 PowerShell 命令的轉譯如下： ( **AzureADUser** ) 中取得目前 Microsoft 365 訂閱中的所有使用者，但只顯示每位使用者的名稱和位置 ( **選取 DisplayName，UsageLocation** ) 。</span><span class="sxs-lookup"><span data-stu-id="5b019-148">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription ( **Get-AzureADUser** ), but only display the name and location for each user ( **Select DisplayName, UsageLocation** ).</span></span>
  
<span data-ttu-id="5b019-149">因為 Microsoft 365 PowerShell 支援命令介面語言，所以您可以進一步操縱 **AzureADUser** 命令中取得的資訊。</span><span class="sxs-lookup"><span data-stu-id="5b019-149">Because PowerShell for Microsoft 365 supports a command shell language, you can further manipulate the information obtained from the **Get-AzureADUser** command.</span></span> <span data-ttu-id="5b019-150">例如，您可能想要依其位置排序使用者、將所有巴西使用者組合在一起，將美國所有使用者組合在一起，等等。命令如下：</span><span class="sxs-lookup"><span data-stu-id="5b019-150">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, etc. Here is the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="5b019-151">以下是顯示範例：</span><span class="sxs-lookup"><span data-stu-id="5b019-151">Here is an example of the display:</span></span>
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

> [!TIP]
>  <span data-ttu-id="5b019-152">此 PowerShell 命令的轉譯為：取得目前 Microsoft 365 訂閱中的所有使用者，但是只會顯示每位使用者的名稱和位置，並依其位置排序，然後再以其名稱 ( **sort UsageLocation，DisplayName** ) 。</span><span class="sxs-lookup"><span data-stu-id="5b019-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location, and then their names ( **Sort UsageLocation, DisplayName** ).</span></span>
  
<span data-ttu-id="5b019-p110">您也可以使用其他篩選。例如，如果您只想看到巴西使用者的資訊，請使用這個命令：</span><span class="sxs-lookup"><span data-stu-id="5b019-p110">You can also employ additional filtering. For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="5b019-155">以下是顯示範例：</span><span class="sxs-lookup"><span data-stu-id="5b019-155">Here is an example of the display:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  <span data-ttu-id="5b019-156">此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的所有使用者，其位置是巴西 ( **其中 {$ \_ 。UsageLocation-eq "BR"}** ) ，然後顯示每位使用者的名稱和位置。</span><span class="sxs-lookup"><span data-stu-id="5b019-156">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription whose location is Brazil ( **Where {$\_.UsageLocation -eq "BR"}** ), then display the name and location for each user.</span></span>
  
 <span data-ttu-id="5b019-157">**與較大型網域相關的備註**</span><span class="sxs-lookup"><span data-stu-id="5b019-157">**A Quick Note Regarding Larger Domains**</span></span>
  
<span data-ttu-id="5b019-158">如果您有超大型的網域 (擁有數萬名的使用者)，嘗試我們在本文中所示範的部分範例可能會走向「節流」。</span><span class="sxs-lookup"><span data-stu-id="5b019-158">If you have a very large domain with tens of thousands of users, trying some of the examples we show in this article could lead to "throttling."</span></span> <span data-ttu-id="5b019-159">這表示根據如運算能力和可用網路頻寬等項目，您可能一次做太多事情。</span><span class="sxs-lookup"><span data-stu-id="5b019-159">That means that, based on things like computing power and available network bandwidth, you're trying to do a little too much at one time.</span></span> <span data-ttu-id="5b019-160">因此，較大的組織可能會想要將某些 Microsoft 365 命令的 PowerShell 分割成兩個命令。</span><span class="sxs-lookup"><span data-stu-id="5b019-160">Because of that, larger organizations might want to split some of these PowerShell for Microsoft 365 commands into two commands.</span></span> <span data-ttu-id="5b019-161">例如，此命令會傳回所有使用者帳戶，並顯示每位使用者的名稱和位置：</span><span class="sxs-lookup"><span data-stu-id="5b019-161">For example, this one command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="5b019-p112">該命令非常適合較小型的網域。然而，在大型組織中，您可能需要將它分割成兩個命令：一個命令用來將使用者帳戶資訊儲存至變數中，而另一個命令用來顯示所需的資訊。範例如下：</span><span class="sxs-lookup"><span data-stu-id="5b019-p112">That works great for smaller domains. In a large organization, however, you might need to split that into two commands: one command to store the user account information in a variable and another command to display the needed information. Here is an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="5b019-165">這組 PowerShell 命令的轉譯如下：</span><span class="sxs-lookup"><span data-stu-id="5b019-165">The interpretation of this set of PowerShell commands is:</span></span>
- <span data-ttu-id="5b019-166">取得目前 Microsoft 365 訂閱中的所有使用者，並將資訊儲存在名為 $x 的變數中 ( **$x = AzureADUser** ) 。</span><span class="sxs-lookup"><span data-stu-id="5b019-166">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="5b019-167">顯示變數 $x 的內容，但只會包括每位使用者的名稱和位置 ( **$x | Select DisplayName, UsageLocation** )。</span><span class="sxs-lookup"><span data-stu-id="5b019-167">Display the contents of the variable $x, but only include the name and location for each user ( **$x | Select DisplayName, UsageLocation** ).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="5b019-168">Microsoft 365 具有您只能使用 Microsoft 365 PowerShell 所設定的功能</span><span class="sxs-lookup"><span data-stu-id="5b019-168">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="5b019-169">Microsoft 365 系統管理中心主要是用來存取大多數使用者適用的最常見或有意義的管理工作。</span><span class="sxs-lookup"><span data-stu-id="5b019-169">The Microsoft 365 admin center is intended to provide access to the most common or meaningful administrative tasks that apply to most people.</span></span> <span data-ttu-id="5b019-170">換句話說，已設計 Microsoft 365 系統管理中心，讓一般管理員可以使用工具來執行最常見的管理工作。</span><span class="sxs-lookup"><span data-stu-id="5b019-170">In other words, the Microsoft 365 admin center was designed so that the typical administrator could use the tool to carry out the most common management tasks.</span></span> <span data-ttu-id="5b019-171">根據此定義，這表示有一些工作無法使用 Microsoft 365 系統管理中心完成。</span><span class="sxs-lookup"><span data-stu-id="5b019-171">By this definition, that means that there are some tasks that can't be completed by using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="5b019-172">例如，商務用 Skype Online 系統管理中心提供一些選項來建立自訂會議邀請：</span><span class="sxs-lookup"><span data-stu-id="5b019-172">For example, the Skype for Business Online Admin center provides a few options for creating custom meeting invitations:</span></span>
  
![在商務用 Skype Online 系統管理中心內，自訂會議邀請顯示方式的範例。](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="5b019-p114">使用這些設定，您可以新增會議邀請的一些個人化和專門技術。不過，這不只是建立自訂會議邀請，還會進行其他會議組態設定。例如，會議預設允許：</span><span class="sxs-lookup"><span data-stu-id="5b019-p114">With these settings, you can add a touch of personalization and professionalism to meeting invitations. However, there's more to meeting configuration settings than simply creating custom meeting invitations. For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="5b019-177">匿名使用者自動進入每個會議。</span><span class="sxs-lookup"><span data-stu-id="5b019-177">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="5b019-178">出席者記錄會議。</span><span class="sxs-lookup"><span data-stu-id="5b019-178">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="5b019-179">您組織的所有使用者在加入會議時都會指定為主持人。</span><span class="sxs-lookup"><span data-stu-id="5b019-179">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="5b019-180">這些設定無法從 商務用 Skype Online 系統管理中心取得。</span><span class="sxs-lookup"><span data-stu-id="5b019-180">These settings are not available from the Skype for Business Online Admin center.</span></span> <span data-ttu-id="5b019-181">不過，您可以從 PowerShell 對 Microsoft 365 進行控制。</span><span class="sxs-lookup"><span data-stu-id="5b019-181">However, you can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="5b019-182">以下是停用這三項設定的命令：</span><span class="sxs-lookup"><span data-stu-id="5b019-182">Here is a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="5b019-183">這個命令需要您安裝 [商務用 Skype Online PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="5b019-183">This command requires that you install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="5b019-184">此 PowerShell 命令的轉譯：針對新的商務用 Skype Online 會議設定 ( **Set-CsMeetingConfiguration** ) 、停用讓匿名使用者能夠自動進入會議 (- **AdmitAnonymousUsersByDefault $False** ) 、停用出席者記錄 \*\*會議 ( AllowConferenceRecording $False ) \*\* ，但不要將組織中的所有使用者指定為簡報者 ( **-DesignateAsPresenter "None"** ) 。</span><span class="sxs-lookup"><span data-stu-id="5b019-184">The interpretation of this PowerShell command is: For the settings for new Skype for Business Online meetings ( **Set-CsMeetingConfiguration** ), disable allowing anonymous users to gain automatic entrance to meetings ( **-AdmitAnonymousUsersByDefault $False** ), disable the ability for attendees to record meetings ( **-AllowConferenceRecording $False** ), and do not designate all users from your organization as presenters ( **-DesignateAsPresenter "None"** ).</span></span>
  
<span data-ttu-id="5b019-185">如果您改變主意想要還原這些預設設定 (全部都已啟用)，請執行這個命令：</span><span class="sxs-lookup"><span data-stu-id="5b019-185">If you change your mind and want to restore these default settings (all of them enabled), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="5b019-186">這只是其中一個範例。</span><span class="sxs-lookup"><span data-stu-id="5b019-186">This is just one example.</span></span> <span data-ttu-id="5b019-187">還有其他一些原因，您在系統管理員的情況下，您必須熟悉 Microsoft 365 命令的執行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5b019-187">There are others, which is why you, as an administrator, need to be comfortable with running PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a><span data-ttu-id="5b019-188">Microsoft 365 的 PowerShell 非常適合執行大量作業</span><span class="sxs-lookup"><span data-stu-id="5b019-188">PowerShell for Microsoft 365 is great at carrying out bulk operations</span></span>

<span data-ttu-id="5b019-189">從過去的角度來看，當您執行單一作業時，像是 Microsoft 365 系統管理中心的視覺介面最有價值。</span><span class="sxs-lookup"><span data-stu-id="5b019-189">Historically, visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to perform.</span></span> <span data-ttu-id="5b019-190">例如，如果您需要停用一個使用者帳戶，您可以使用 Microsoft 365 系統管理中心，快速找出並清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5b019-190">For example, if you need to disable one user account, you can use the Microsoft 365 admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="5b019-191">這可以比在 PowerShell 中執行類似的作業更簡單。</span><span class="sxs-lookup"><span data-stu-id="5b019-191">This can be simpler than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="5b019-192">不過，如果您必須在大量的其他專案中變更許多專案或某些選取的專案，Microsoft 365 系統管理中心可能無法充分利用您的時間。</span><span class="sxs-lookup"><span data-stu-id="5b019-192">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best use of your time.</span></span> <span data-ttu-id="5b019-193">例如，如果您必須變更數千個電話號碼的前置詞，或者您需要移除所有 SharePoint 線上網站上的特定使用者（Ken Myer），您會如何在 Microsoft 365 系統管理中心中執行此動作？</span><span class="sxs-lookup"><span data-stu-id="5b019-193">For example, if you had to change the prefix on thousands of phone numbers or you needed to remove a specific user, Ken Myer, from all of your SharePoint Online sites, how would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="5b019-194">對於後面的範例，您有數百個 SharePoint Online 網站，而且甚至不知道 Ken Meyer 所屬的網站。</span><span class="sxs-lookup"><span data-stu-id="5b019-194">For the latter example, you have several hundred SharePoint Online sites and you don't know even know which ones of which Ken Meyer is a member.</span></span> <span data-ttu-id="5b019-195">這表示您必須從 Microsoft 365 系統管理中心開始，然後針對每個網站執行此程式：</span><span class="sxs-lookup"><span data-stu-id="5b019-195">That means you'll have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="5b019-196">按一下網站的 **URL** 。</span><span class="sxs-lookup"><span data-stu-id="5b019-196">Click the **URL** of the site.</span></span>
    
2. <span data-ttu-id="5b019-197">在 [網站集合內容] 方塊中，按一下 [網站位址] 連結以開啟網站。</span><span class="sxs-lookup"><span data-stu-id="5b019-197">In the **site collection properties** box, click the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="5b019-198">在網站上，按一下 [共用]。</span><span class="sxs-lookup"><span data-stu-id="5b019-198">On the site, click **Share**.</span></span>
    
4. <span data-ttu-id="5b019-199">在 [共用] 對話方塊中，按一下連結，以顯示所有具有網站權限的使用者：</span><span class="sxs-lookup"><span data-stu-id="5b019-199">In the **Share** dialog box click the link that shows you all the users who have permissions to the site:</span></span>
    
     ![在 SharePoint Online 系統管理中心內，檢視 SharePoint Online 網站成員的範例。](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="5b019-201">在 [共用對象] 對話方塊中，按一下 [進階]。</span><span class="sxs-lookup"><span data-stu-id="5b019-201">In the **Shared With** dialog box, click **Advanced**.</span></span>
    
6. <span data-ttu-id="5b019-202">捲動使用者清單，並尋找和選取 Ken Myer (假設他具有網站權限)，然後按一下 [移除使用者權限]。</span><span class="sxs-lookup"><span data-stu-id="5b019-202">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then click **Remove User Permissions**.</span></span>
    
<span data-ttu-id="5b019-203">因為有數百個網站，所以這可能需要很長的時間。</span><span class="sxs-lookup"><span data-stu-id="5b019-203">This can take a long time for several hundred sites.</span></span>
  
<span data-ttu-id="5b019-204">另一種方法是使用 Microsoft 365 的 PowerShell，並使用下列命令，從所有網站中移除 Ken Myer：</span><span class="sxs-lookup"><span data-stu-id="5b019-204">The alternative is to use PowerShell for Microsoft 365 and the following command to remove Ken Myer from all of your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="5b019-205">這個命令需要您安裝 [SharePoint 線上 PowerShell 模組](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="5b019-205">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="5b019-206">此 PowerShell 命令的轉譯為：取得目前 Microsoft 365 訂閱中的所有 SharePoint 網站 ( **Get-SPOSite** ) 以及每個網站，從可以存取它的使用者清單中移除 Ken Meyer ( **ForEach {Remove-SPOUser 網站 $ \_ 。Url-LoginName "kenmyer@litwareinc.com"}** ) 。</span><span class="sxs-lookup"><span data-stu-id="5b019-206">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription ( **Get-SPOSite** ) and for each site, remove Ken Meyer from the list of users who can access it ( **ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer@litwareinc.com"}** ).</span></span>
  
<span data-ttu-id="5b019-207">因為我們會告訴 Microsoft 365 從每個網站中移除 Ken Meyer，包括其沒有存取權的網站，所以此命令的顯示將會顯示其目前沒有存取權之網站的錯誤。</span><span class="sxs-lookup"><span data-stu-id="5b019-207">Because we are telling Microsoft 365 to remove Ken Meyer from every site, including those in which he does not have access, the display of this command will show errors for those sites in which he does not currently have access.</span></span> <span data-ttu-id="5b019-208">我們可以在此命令上使用其他條件，只從登入清單中有 Key Meyer 的網站中移除 Key Meyer，但列出的錯誤不會傷害網站本身。</span><span class="sxs-lookup"><span data-stu-id="5b019-208">We can use an additional condition on this command to remove Key Meyer only from the sites that have him in their login list, but the listed errors cause no harm to the sites themselves.</span></span> <span data-ttu-id="5b019-209">這個命令可能需要幾分鐘的時間來執行數百個網站，而不是透過 Microsoft 365 系統管理中心的工作時間。</span><span class="sxs-lookup"><span data-stu-id="5b019-209">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="5b019-p121">以下是另一個大量作業範例。使用此命令將 Bonnie Kearney (新的 SharePoint 系統管理員) 新增至組織中的所有網站：</span><span class="sxs-lookup"><span data-stu-id="5b019-p121">Here is another bulk operation example. Use this command to add Bonnie Kearney, a new SharePoint administrator, to all of the sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  <span data-ttu-id="5b019-212">此 PowerShell 命令的轉譯為：取得目前 Microsoft 365 訂閱中的所有 SharePoint 網站，並針對每個網站，將其登入名稱新增至網站的 Members 群組，以允許 Bonnie Kearney 存取 ( **ForEach {Add-SPOUser-site $ \_ 。Url-LoginName "bkearney@litwareinc.com"-Group 「Members」}** ) 。</span><span class="sxs-lookup"><span data-stu-id="5b019-212">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription and for each site, allow Bonnie Kearney access by adding her login name to the Members group of the site ( **ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}** ).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="5b019-213">Microsoft 365 的 PowerShell 非常適合篩選資料</span><span class="sxs-lookup"><span data-stu-id="5b019-213">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="5b019-214">Microsoft 365 系統管理中心提供數種不同的方式來篩選您的資料，以快速輕鬆地找出目標的資訊子集。</span><span class="sxs-lookup"><span data-stu-id="5b019-214">The Microsoft 365 admin center provides several different ways to filter your data to quickly and easily locate a targeted subset of information.</span></span> <span data-ttu-id="5b019-215">例如，Exchange 可輕鬆篩選使用者信箱的任何內容。</span><span class="sxs-lookup"><span data-stu-id="5b019-215">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="5b019-216">例如，以下是住在布魯民頓市中所有使用者的信箱清單：</span><span class="sxs-lookup"><span data-stu-id="5b019-216">For example, here is the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![在 Microsoft 365 系統管理中心中執行高級搜尋的範例，針對居住于 Bloomington 城市中之所有使用者的信箱清單。](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="5b019-p123">Exchange 系統管理中心也可讓您合併篩選準則。例如，您可以找到住在布魯民頓市並且在財務部門工作之所有人的信箱。</span><span class="sxs-lookup"><span data-stu-id="5b019-p123">The Exchange Admin center also lets you combine filter criteria. For example, you can find the mailboxes for all the people who live in Bloomington and who work in the Finance department.</span></span> 
  
<span data-ttu-id="5b019-p124">不過，在 Exchange 系統管理中心內有一些限制。例如，您可能想要找到住在布魯民頓市或聖地牙哥市之人員的信箱，或不住在布魯民頓市之所有人員的信箱。</span><span class="sxs-lookup"><span data-stu-id="5b019-p124">However, there are limitations to what you can do in the Exchange Admin center. For example, maybe you'd like to find the mailboxes of people who live in Bloomington or San Diego, or the mailboxes for all the people who don't live in Bloomington.</span></span> 
  
<span data-ttu-id="5b019-222">使用 Microsoft 365 的 PowerShell，您可以使用此命令來取得居住在 Bloomington 或聖地牙哥市之所有人員的信箱清單：</span><span class="sxs-lookup"><span data-stu-id="5b019-222">With PowerShell for Microsoft 365, you can get a list of mailboxes for all the people who live in the cities of Bloomington or San Diego with this command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="5b019-223">以下是顯示範例：</span><span class="sxs-lookup"><span data-stu-id="5b019-223">Here is an example of the display:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  <span data-ttu-id="5b019-224">此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的所有使用者，這些使用者在聖地牙哥或 ( Bloomington 的城市中擁有信箱 **，其是 {$ \_ 。RecipientTypeDetails-eq "UserMailbox" 和 ($ \_ 。城市-eq "聖地牙哥"-或 $ \_ 。City-eq "Bloomington" ) }** ) ，然後顯示每個 ( **選取 DisplayName，城市** ) 的名稱和城市。</span><span class="sxs-lookup"><span data-stu-id="5b019-224">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox in the cities of either San Diego or Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}** ), then display the name and city for each ( **Select DisplayName, City** ).</span></span>
  
<span data-ttu-id="5b019-225">若要列出不住在布魯民頓市之人員的所有信箱，則命令如下：</span><span class="sxs-lookup"><span data-stu-id="5b019-225">To list all the mailboxes for people who live anywhere except Bloomington, here is the command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="5b019-226">以下是顯示範例：</span><span class="sxs-lookup"><span data-stu-id="5b019-226">Here is an example of the display:</span></span>
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

> [!TIP]
>  <span data-ttu-id="5b019-227">此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的信箱未位於 Bloomington 的城市中的所有使用者 ( **其中 {$ \_ 。RecipientTypeDetails-eq "UserMailbox"-和 $ \_ 。City-ne "Bloomington"}** ) ，然後顯示每一個的名稱和城市。</span><span class="sxs-lookup"><span data-stu-id="5b019-227">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}** ), then display the name and city for each.</span></span>
  
<span data-ttu-id="5b019-228">您也可以在 PowerShell 篩選中使用萬用字元，以符合部分名稱。</span><span class="sxs-lookup"><span data-stu-id="5b019-228">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="5b019-229">例如，假設您正在尋找一個使用者帳戶，而且您只記得姓氏是 Anderson 或 Henderson，也可能是 Jorgenson。</span><span class="sxs-lookup"><span data-stu-id="5b019-229">For example, suppose you're looking for a user account, and all you can remember is that their last name was Anderson, or maybe Henderson, or maybe it was Jorgenson.</span></span>
  
<span data-ttu-id="5b019-230">您可以使用搜尋工具並執行三種不同的搜尋，以在 Microsoft 365 系統管理中心中追蹤該使用者：</span><span class="sxs-lookup"><span data-stu-id="5b019-230">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="5b019-231">一個用於  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="5b019-231">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="5b019-232">一個用於  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="5b019-232">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="5b019-233">一個用於  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="5b019-233">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="5b019-234">因為這些名稱中的三個都以 "兒子" 結尾，您可以告訴 PowerShell 顯示名稱以 "兒子" 結尾的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="5b019-234">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="5b019-235">命令如下：</span><span class="sxs-lookup"><span data-stu-id="5b019-235">Here is the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  <span data-ttu-id="5b019-236">此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的所有使用者，但是使用篩選器，該篩選只會列出姓氏結尾為 "兒子" ( **-filter "{LastName-like" \* 兒子 "}"** ) 的使用者。</span><span class="sxs-lookup"><span data-stu-id="5b019-236">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" ( **-Filter '{LastName -like "\*son"}'** ).</span></span> <span data-ttu-id="5b019-237">\*代表任何一組字元，也就是使用者的姓氏的情況下的字母。</span><span class="sxs-lookup"><span data-stu-id="5b019-237">The \* stands for any set of characters, which are letters in the case of the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="5b019-238">Microsoft 365 的 PowerShell 可讓您輕鬆地列印或儲存資料</span><span class="sxs-lookup"><span data-stu-id="5b019-238">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="5b019-239">Microsoft 365 系統管理中心可讓您查看資料清單。</span><span class="sxs-lookup"><span data-stu-id="5b019-239">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="5b019-240">以下是商務用 Skype Online 系統管理中心範例，其中顯示已啟用商務用 Skype Online 的使用者清單：</span><span class="sxs-lookup"><span data-stu-id="5b019-240">Here is an example of the Skype for Business Online Admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![商務用 Skype Online 系統管理中心，顯示商務用 Skype Online 已啟用的使用者清單的範例。](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="5b019-242">若要將該資訊儲存至檔案，您必須複製該資訊，並將它貼到文件或 Excel。</span><span class="sxs-lookup"><span data-stu-id="5b019-242">To save that information to a file, you must copy and paste it into a document or Excel.</span></span> <span data-ttu-id="5b019-243">在任一情況下，複本可能都需要進行其他格式設定。</span><span class="sxs-lookup"><span data-stu-id="5b019-243">In either case, the copy might require additional formatting.</span></span> <span data-ttu-id="5b019-244">此外，Microsoft 365 系統管理中心不會提供直接列印所顯示清單的方式。</span><span class="sxs-lookup"><span data-stu-id="5b019-244">Additionally, the Microsoft 365 admin center does not provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="5b019-245">幸運的是，您可以使用 PowerShell，而不只顯示清單，但將它儲存到可輕鬆匯入 Excel 的檔案。</span><span class="sxs-lookup"><span data-stu-id="5b019-245">Fortunately, you can use PowerShell to not only display the list, but save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="5b019-246">以下範例命令可將 商務用 Skype Online 使用者資料儲存為逗點分隔值 (CSV) 檔案，而這是可輕鬆地匯入為 Excel 工作表中的資料表的檔案：</span><span class="sxs-lookup"><span data-stu-id="5b019-246">Here is an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, a file that can be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="5b019-247">以下是顯示範例：</span><span class="sxs-lookup"><span data-stu-id="5b019-247">Here is an example of the display:</span></span>
  
![儲存成逗點分隔值 (CSV) 檔案的商務用 Skype Online 使用者資料表，匯入到 Excel 工作表中的範例。](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  <span data-ttu-id="5b019-249">此 PowerShell 命令的轉譯如下：在目前的 Microsoft 365 訂閱中取得所有商務用 Skype Online 使用者 ( **Get-CsOnlineUser** ) 、只取得使用者名稱、UPN 和位置 ( **選取 DisplayName，UserPrincipalName，UsageLocation** ) ，然後將該資訊儲存在名為 C：記錄檔的 CSV 檔案 \\ 中 \\SfBUsers.csv ( **匯出-CSV 路徑 "c： \\ logs \\SfBUsers.csv"-NoTypeInformation** ) 。</span><span class="sxs-lookup"><span data-stu-id="5b019-249">The interpretation of this PowerShell command is: Get all of the Skype for Business Online users in the current Microsoft 365 subscription ( **Get-CsOnlineUser** ), obtain only the user name, UPN, and location ( **Select DisplayName, UserPrincipalName, UsageLocation** ), and then save that information in CSV file named C:\\Logs\\SfBUsers.csv ( **Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation** ).</span></span>
  
<span data-ttu-id="5b019-p131">您也可以使用選項，將此清單儲存為 XML 檔案或 HTML 頁面。事實上，使用其他 PowerShell 命令，您可以直接將它儲存為 Excel 檔 (內含任何您想要的自訂格式)。</span><span class="sxs-lookup"><span data-stu-id="5b019-p131">You can also use options to save this list as an XML file or as an HTML page. In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you desire.</span></span> 
  
<span data-ttu-id="5b019-252">您也可以傳送 PowerShell 命令的輸出，將清單直接顯示在 Windows 中的預設印表機。</span><span class="sxs-lookup"><span data-stu-id="5b019-252">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="5b019-253">範例命令如下：</span><span class="sxs-lookup"><span data-stu-id="5b019-253">Here is an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="5b019-254">以下是您將列印出的文件樣貌：</span><span class="sxs-lookup"><span data-stu-id="5b019-254">Here's what your printed document will look like:</span></span>
  
![列印的檔的範例是直接列于 Windows 的預設印表機的 PowerShell 命令輸出。](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  <span data-ttu-id="5b019-256">此 PowerShell 命令的轉譯如下：在目前的 Microsoft 365 訂閱中取得所有商務用 Skype Online 使用者、只取得使用者名稱、UPN 和位置，然後將該資訊傳送至預設 Windows printer ( **Out-Printer** ) 。</span><span class="sxs-lookup"><span data-stu-id="5b019-256">The interpretation of this PowerShell command is:  Get all of the Skype for Business Online users in the current Microsoft 365 subscription, obtain only the user name, UPN, and location, and then send that information to the default Windows printer ( **Out-Printer** ).</span></span>
  
<span data-ttu-id="5b019-257">列印的檔具有與 PowerShell 命令視窗中的顯示相同的簡易格式設定，但是一旦您建立 PowerShell 命令以列出您需要的專案，您只需新增 **|Out-Printer** 至命令的結尾，以取得可供使用的硬拷貝。</span><span class="sxs-lookup"><span data-stu-id="5b019-257">The printed document has the same simple formatting as the display within the PowerShell command window, but once you have created a PowerShell command to list what you need, you just add **| Out-Printer** to the end of the command to get a hard copy to work from.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="5b019-258">Microsoft 365 的 PowerShell 可讓您跨伺服器產品進行管理</span><span class="sxs-lookup"><span data-stu-id="5b019-258">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="5b019-259">組成 Microsoft 365 的不同元件是設計成共同運作。</span><span class="sxs-lookup"><span data-stu-id="5b019-259">The different components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="5b019-260">例如，假設您將新使用者新增至 Microsoft 365，當您這樣做時，您會指定使用者的部門和電話號碼等資訊。</span><span class="sxs-lookup"><span data-stu-id="5b019-260">For example, suppose you add a new user to Microsoft 365 and, when you do, you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="5b019-261">當您使用 Microsoft 365 服務（商務用 Skype Online、Exchange 或 SharePoint 線上）存取使用者的資訊時，該資訊將可供使用。</span><span class="sxs-lookup"><span data-stu-id="5b019-261">That information will then be available if you access the user's information using any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint Online.</span></span>
  
<span data-ttu-id="5b019-p134">不過，這是對跨越產品系列的一般資訊而言。產品特定資訊 (例如，使用者的 Exchange 信箱相關資訊) 通常不會跨系列提供。例如，如果您想要知道是否已啟用使用者的信箱，則只能在 Exchange 系統管理中心內取得該資訊。</span><span class="sxs-lookup"><span data-stu-id="5b019-p134">But that's for common information that spans the suite of products. Product-specific information-for example, information about a user's Exchange mailbox-is typically not available across the suite. For example, if you want to know if a user's mailbox is enabled or not, that information is available only in the Exchange Admin center.</span></span> 
  
<span data-ttu-id="5b019-265">假設您想要製作一份報告，顯示所有使用者的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5b019-265">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="5b019-266">使用者的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="5b019-266">The user's display name</span></span>
    
- <span data-ttu-id="5b019-267">使用者是否已取得 Microsoft 365 的授權</span><span class="sxs-lookup"><span data-stu-id="5b019-267">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="5b019-268">使用者的 Exchange 信箱是否已啟用</span><span class="sxs-lookup"><span data-stu-id="5b019-268">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="5b019-269">是否已對使用者啟用商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="5b019-269">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="5b019-270">您目前無法使用 Microsoft 365 管理中心來輕鬆產生這類報告。</span><span class="sxs-lookup"><span data-stu-id="5b019-270">You currently cannot use the Microsoft 365 admin center to easily produce such a report.</span></span> <span data-ttu-id="5b019-271">相反地，您必須建立個別的檔來儲存資訊，例如 Excel 工作表，並從 Microsoft 365 系統管理中心取得所有的使用者名稱和授權資訊、取得來自 Exchange 系統管理中心的信箱資訊、從商務用 Skype Online 系統管理中心取得商務用 Skype Online 資訊，然後再進行 collate 及合併該資訊。</span><span class="sxs-lookup"><span data-stu-id="5b019-271">Instead, you'll have to create a separate document to store the information, like an Excel worksheet, and get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then collate and combine that information.</span></span>
  
<span data-ttu-id="5b019-272">另一種方法是使用 PowerShell 腳本為您編譯該報告。</span><span class="sxs-lookup"><span data-stu-id="5b019-272">The alternative is to use a PowerShell script to compile that report for you.</span></span>
  
<span data-ttu-id="5b019-273">下列範例指令碼會比目前為止在本文中看過的命令還要複雜。</span><span class="sxs-lookup"><span data-stu-id="5b019-273">The following example script is more complicated than the commands you have seen so far in this article.</span></span> <span data-ttu-id="5b019-274">不過，它會顯示可能使用 PowerShell 來建立非常困難的資訊視圖。</span><span class="sxs-lookup"><span data-stu-id="5b019-274">But, it shows the potential of using PowerShell to create views of information that are very difficult to do otherwise.</span></span> <span data-ttu-id="5b019-275">以下指令碼可以編譯並顯示所需的清單：</span><span class="sxs-lookup"><span data-stu-id="5b019-275">Here is the script that can compile and display the needed list:</span></span>
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

<span data-ttu-id="5b019-276">以下是顯示範例：</span><span class="sxs-lookup"><span data-stu-id="5b019-276">Here is an example of the display:</span></span>
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

<span data-ttu-id="5b019-277">此 PowerShell 腳本的轉譯如下：</span><span class="sxs-lookup"><span data-stu-id="5b019-277">The interpretation of this PowerShell script is:</span></span>  

- <span data-ttu-id="5b019-278">取得目前 Microsoft 365 訂閱中的所有使用者，並將資訊儲存在名為 $x 的變數中 ( **$x = AzureADUser** ) 。</span><span class="sxs-lookup"><span data-stu-id="5b019-278">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="5b019-279">開始迴圈，而迴圈會對名稱為 $x 之變數中的所有使用者執行 ( **foreach ($i in $x)** )。</span><span class="sxs-lookup"><span data-stu-id="5b019-279">Start a loop that runs over all the users in the variable named $x ( **foreach ($i in $x)** ).</span></span>  
- <span data-ttu-id="5b019-280">定義名稱為 $y 的變數，並在其中儲存使用者的信箱資訊 ( **$y = Get-Mailbox -Identity $i.UserPrincipalName** )。</span><span class="sxs-lookup"><span data-stu-id="5b019-280">Define a variable named $y and store the user's mailbox information in it ( **$y = Get-Mailbox -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="5b019-281">將新的屬性新增至名稱為 IsMailBoxEnabled 的使用者資訊，並將它設定為使用者信箱的 IsMailBoxEnabled 屬性值 ( **$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled** )。</span><span class="sxs-lookup"><span data-stu-id="5b019-281">Add a new property to the user information named IsMailBoxEnabled and set it to the value of the IsMailBoxEnabled property of the user's mailbox ( **$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled** ).</span></span>
- <span data-ttu-id="5b019-282">定義名稱為 $y 的變數，並在其中儲存使用者的商務用 Skype Online 資訊 ( **$y = Get-CsOnlineUser -Identity $i.UserPrincipalName** )。</span><span class="sxs-lookup"><span data-stu-id="5b019-282">Define a variable named $y and store the user's Skype for Business Online information in it ( **$y = Get-CsOnlineUser -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="5b019-283">將新的屬性新增至名稱為 EnabledForSfB 的使用者資訊，並將它設定為使用者之商務用 Skype Online 資訊的 Enabled 屬性值 ( **$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled** )。</span><span class="sxs-lookup"><span data-stu-id="5b019-283">Add a new property to the user information named EnabledForSfB and set it to the value of the Enabled property of the user's Skype for Business Online information ( **$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled** ).</span></span>
- <span data-ttu-id="5b019-284">顯示使用者清單，但只包括其名稱、是否獲得授權，以及指出是否已啟用其信箱以及其是否已啟用商務用 Skype Online 的兩個新屬性 ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** )。</span><span class="sxs-lookup"><span data-stu-id="5b019-284">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b019-285">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5b019-285">See also</span></span>

[<span data-ttu-id="5b019-286">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b019-286">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5b019-287">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="5b019-287">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5b019-288">在 Microsoft 365 中使用 Windows PowerShell 建立報告</span><span class="sxs-lookup"><span data-stu-id="5b019-288">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)

