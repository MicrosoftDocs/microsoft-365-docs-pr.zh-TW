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
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754103"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="cfa2a-103">為什麼您需要使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="cfa2a-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="cfa2a-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="cfa2a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cfa2a-105">您可以使用 Microsoft 365 系統管理中心，管理您的 Microsoft 365 使用者帳戶和授權。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="cfa2a-106">您也可以管理 Microsoft 365 服務，例如 Exchange Online、小組和 SharePoint 線上。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="cfa2a-107">[！注意] 如果您改為使用 PowerShell 來管理這些服務，您可以並利用命令列及指令碼語言環境，以取得速度、自動化及其他功能。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="cfa2a-108">本文說明如何使用 PowerShell 來管理 Microsoft 365，以進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="cfa2a-109">顯示您在 Microsoft 365 系統管理中心中看不到的其他資訊</span><span class="sxs-lookup"><span data-stu-id="cfa2a-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="cfa2a-110">設定 PowerShell 的功能和設定</span><span class="sxs-lookup"><span data-stu-id="cfa2a-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="cfa2a-111">執行大量作業</span><span class="sxs-lookup"><span data-stu-id="cfa2a-111">Do bulk operations</span></span>
    
- <span data-ttu-id="cfa2a-112">篩選資料</span><span class="sxs-lookup"><span data-stu-id="cfa2a-112">Filter data</span></span>
    
- <span data-ttu-id="cfa2a-113">列印或儲存資料</span><span class="sxs-lookup"><span data-stu-id="cfa2a-113">Print or save data</span></span>
    
- <span data-ttu-id="cfa2a-114">跨服務管理</span><span class="sxs-lookup"><span data-stu-id="cfa2a-114">Manage across services</span></span>
    
<span data-ttu-id="cfa2a-115">請注意，Microsoft 365 的 PowerShell 是一組 Windows PowerShell 模組，也就是 Windows 服務和平臺的命令列環境。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="cfa2a-116">此環境會建立命令介面語言，該語言可與其他模組擴充。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="cfa2a-117">它提供執行簡易或複雜命令或腳本的方式。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="cfa2a-118">例如，在您安裝 Microsoft 365 模組的 PowerShell 並聯機至您的 Microsoft 365 訂閱後，您可以執行下列命令來列出 Microsoft Exchange Online 的所有使用者信箱：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="cfa2a-119">您也可以使用 Microsoft 365 系統管理中心取得信箱清單，但為所有 web 應用程式的所有網站計算所有清單中的專案，並不容易。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="cfa2a-120">Microsoft 365 的 PowerShell 設計用來協助您管理 Microsoft 365，而不是取代 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="cfa2a-121">系統管理員必須能夠對 Microsoft 365 使用 PowerShell，因為某些設定程式只能透過 PowerShell Microsoft 365 命令進行。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="cfa2a-122">在這些情況下，您必須瞭解如何進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="cfa2a-123">安裝 Microsoft 365 模組的 PowerShell (每個系統管理員電腦) 只執行一次。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="cfa2a-124">在每個 PowerShell 會話) 上，連線至您的 Microsoft 365 訂閱 (一次。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="cfa2a-125">收集為 Microsoft 365 命令執行必要 PowerShell 所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="cfa2a-126">針對 Microsoft 365 命令執行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="cfa2a-127">瞭解這些基本技能之後，您不需要使用 **Get-Mailbox** 命令列出信箱使用者。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="cfa2a-128">您也不需要瞭解如何建立新的命令，如先前提及的命令，用來統計所有 web 應用程式之所有網站的所有清單中的所有專案。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="cfa2a-129">Microsoft 和系統管理員群組可以視需要協助您進行這類工作。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="cfa2a-130">Microsoft 365 的 PowerShell 會顯示您無法使用 Microsoft 365 系統管理中心所看到的資訊</span><span class="sxs-lookup"><span data-stu-id="cfa2a-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="cfa2a-131">Microsoft 365 系統管理中心會顯示許多有用資訊。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="cfa2a-132">但不會顯示 Microsoft 365 儲存的使用者、授權、信箱和網站的所有可能資訊。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="cfa2a-133">以下是 Microsoft 365 系統管理中心中 *使用者和群組* 的範例：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Microsoft 365 系統管理中心中使用者和群組的顯示範例。](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="cfa2a-135">此視圖提供您在許多情況下所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="cfa2a-136">不過，您有時需要更多的資訊。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-136">However, there are times when you need more.</span></span> <span data-ttu-id="cfa2a-137">例如，Microsoft 365 授權 (和 Microsoft 365 功能可供使用者) 中的部分取決於使用者的地理位置。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="cfa2a-138">您可以延伸至位於美國地區之使用者的原則和功能，與您可以擴充到印度或比利時之使用者的原則和功能可能並不相同。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="cfa2a-139">請遵循 Microsoft 365 系統管理中心的下列步驟，判斷使用者的地理位置：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="cfa2a-140">連按兩下使用者的 **[顯示名稱]** 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="cfa2a-141">在 [使用者屬性] 顯示窗格中，選取 [ **詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="cfa2a-142">在詳細資料顯示中，選取 [ **其他詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="cfa2a-143">向中滾動直到您找到該標題的 **國家或地區**：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Microsoft 365 系統管理中心中使用者之地區資訊的範例。](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="cfa2a-145">在一張紙上寫下使用者的顯示名稱和位置，或複製並貼到 [記事本]。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="cfa2a-146">您必須為每位使用者重複此程序。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="cfa2a-147">如果您有許多使用者，此程式可能是單調乏味的。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="cfa2a-148">使用 Microsoft 365 的 PowerShell，您可以使用下列命令，為所有使用者顯示此資訊：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="cfa2a-149">PowerShell 核心不支援 Windows PowerShell 模組的 Microsoft Azure Active Directory 模組，以及其名稱中具有 *Msol* 的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="cfa2a-150">您必須從 [Windows PowerShell 執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="cfa2a-151">以下是結果的範例：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-151">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="cfa2a-152">此 PowerShell 命令的轉譯如下： (**AzureADUser**) 中取得目前 Microsoft 365 訂閱中的所有使用者，但只顯示每位使用者的名稱和位置 (**選取 DisplayName，UsageLocation**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="cfa2a-153">因為 Microsoft 365 PowerShell 支援命令介面語言，所以您可以進一步操縱 **AzureADUser** 命令取得的資訊。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="cfa2a-154">例如，您可能想要依其位置排序使用者、將所有巴西使用者組合在一起，將美國所有使用者組合在一起，等等。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="cfa2a-155">命令如下：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="cfa2a-156">以下是結果的範例：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-156">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="cfa2a-157">此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的所有使用者，但只顯示每位使用者的名稱和位置，並依其位置排序，然後再依其名稱 (**sort UsageLocation DisplayName**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="cfa2a-158">您也可以使用其他篩選。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-158">You can also use additional filtering.</span></span> <span data-ttu-id="cfa2a-159">例如，如果您只想看到巴西使用者的資訊，請使用這個命令：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="cfa2a-160">以下是結果的範例：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="cfa2a-161">此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的所有使用者，其位置是巴西 (**其中 {$ \_ 。UsageLocation-eq "BR"}**) 然後顯示每位使用者的名稱和位置。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="cfa2a-162">**有關大型網域的附注**</span><span class="sxs-lookup"><span data-stu-id="cfa2a-162">**A note about large domains**</span></span>
  
<span data-ttu-id="cfa2a-163">如果您有成千上萬位使用者的大型網域，請嘗試我們在本文中顯示的部分範例，以進行節流。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="cfa2a-164">根據計算能力和可用網路頻寬等因素，您可能嘗試一次執行太多動作。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="cfa2a-165">大型組織可能會想要將一些 PowerShell 作業分割成兩個命令。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="cfa2a-166">例如，下列命令會傳回所有使用者帳戶，並顯示每個使用者帳戶的名稱和位置：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="cfa2a-167">該命令非常適合較小型的網域。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-167">That works great for smaller domains.</span></span> <span data-ttu-id="cfa2a-168">但在大型組織中，您可能會想要將該作業分割成兩個命令：一個命令，可將使用者帳戶資訊儲存在變數中，另一個則顯示必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="cfa2a-169">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="cfa2a-170">這組 PowerShell 命令的轉譯如下：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="cfa2a-171">取得目前 Microsoft 365 訂閱中的所有使用者，並將資訊儲存在名為 $x 的變數中 (**$x = AzureADUser**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="cfa2a-172">顯示變數 *$x*的內容，但只包含每個使用者 (的名稱和位置 **$x |選取 [DisplayName]，UsageLocation**) ]。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="cfa2a-173">Microsoft 365 具有您只能使用 Microsoft 365 PowerShell 所設定的功能</span><span class="sxs-lookup"><span data-stu-id="cfa2a-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="cfa2a-174">Microsoft 365 系統管理中心的設計是要提供適用于大部分環境的一般管理工作的存取。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="cfa2a-175">換句話說，已設計 Microsoft 365 系統管理中心，讓一般管理員可以執行最常見的管理工作。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="cfa2a-176">但有一些工作無法在系統管理中心執行。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="cfa2a-177">例如，商務用 Skype Online 系統管理中心提供一些選項來建立自訂會議邀請：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![在商務用 Skype Online 系統管理中心內，自訂會議邀請顯示方式的範例。](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="cfa2a-179">使用這些設定，您可以新增會議邀請的一些個人化和專門技術。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="cfa2a-180">不過，會議配置設定更多，只是建立自訂會議邀請。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="cfa2a-181">例如，會議預設允許：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="cfa2a-182">匿名使用者自動進入每個會議。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="cfa2a-183">出席者記錄會議。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="cfa2a-184">您組織的所有使用者在加入會議時都會指定為主持人。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="cfa2a-185">您無法從商務用 Skype Online 系統管理中心取得這些設定。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="cfa2a-186">您可以從 Microsoft 365 的 PowerShell 控制它們。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="cfa2a-187">以下是停用這三個設定的命令：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="cfa2a-188">若要執行此命令，您必須安裝 [商務用 Skype Online PowerShell 模組 ](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="cfa2a-189">此 PowerShell 命令的轉譯如下：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="cfa2a-190">在 [新的商務用 Skype Online 會議設定] 中 (**Set-CsMeetingConfiguration**) ]，停用 [允許匿名使用者自動進入會議 (**-AdmitAnonymousUsersByDefault $False**) ]。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="cfa2a-191">停用出席者記錄會議 (**AllowConferenceRecording $False**) 的功能。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="cfa2a-192">請勿將組織中的所有使用者指定為簡報者 (**-DesignateAsPresenter "None"**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="cfa2a-193">若要還原這些預設設定 (啟用選項) ，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="cfa2a-194">另外還有其他類似案例，也就是管理員應該知道如何針對 Microsoft 365 命令執行 PowerShell 的原因。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="cfa2a-195">Microsoft 365 的 PowerShell 非常適合大量作業</span><span class="sxs-lookup"><span data-stu-id="cfa2a-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="cfa2a-196">當您有單一作業時，像是 Microsoft 365 系統管理中心的視覺介面最有價值。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="cfa2a-197">例如，如果您需要停用一個使用者帳戶，您可以使用系統管理中心，快速找出並清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="cfa2a-198">這可能會比在 PowerShell 中執行類似的作業更為容易。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="cfa2a-199">不過，如果您必須在大量的其他專案中變更許多專案或某些選取的專案，則 Microsoft 365 系統管理中心可能不是最佳工具。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="cfa2a-200">例如，假設您必須在數以千計的電話號碼上變更前置詞，或是移除所有 SharePoint Online 網站的特定使用者 *Ken Myer* 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="cfa2a-201">如何在 Microsoft 365 系統管理中心中執行該動作？</span><span class="sxs-lookup"><span data-stu-id="cfa2a-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="cfa2a-202">在最後一個範例中，假設您有數個 SharePoint 線上網站，而且您不知道哪些 Ken Meyer 是的成員。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="cfa2a-203">您必須從 Microsoft 365 系統管理中心開始，然後針對每個網站執行此程式：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="cfa2a-204">選取網站的 **URL** 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="cfa2a-205">在 [ **網站集合屬性** ] 方塊中，選取 [網站 **位址** ] 連結以開啟網站。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="cfa2a-206">在網站上，選取 [ **共用**]。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="cfa2a-207">在 [ **共用** ] 對話方塊中，選取顯示所有具有網站許可權的使用者的連結：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![在 SharePoint Online 系統管理中心內，檢視 SharePoint Online 網站成員的範例。](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="cfa2a-209">在 [ **共用物件** ] 對話方塊中，選取 [ **高級**]。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="cfa2a-210">向下滾動使用者清單，尋找並選取 Ken Myer (假設他具有網站) 的許可權，然後選取 [ **移除使用者**權力]。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="cfa2a-211">這會花費 *很長* 的時間進行數百個網站。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="cfa2a-212">另一種方法是在 Microsoft 365 PowerShell 中執行下列命令，以從所有網站中移除 Ken Myer：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="cfa2a-213">這個命令需要您安裝 [SharePoint 線上 PowerShell 模組](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-213">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="cfa2a-214">此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的所有 SharePoint 網站 (**Get-SPOSite**) ，並針對每個網站，從可以存取它的使用者清單中移除 Ken Meyer (**ForEach {Remove-SPOUser-site $ \_ 。Url-LoginName "kenmyer \@ litwareinc.com"}**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="cfa2a-215">我們告訴 Microsoft 365 從每個網站（包括他沒有存取權）中移除 Ken Meyer。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="cfa2a-216">因此，結果會顯示其沒有存取權之網站的錯誤。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="cfa2a-217">我們可以在這個命令上使用另一個條件，只從其登入清單的網站中移除 Ken Meyer。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="cfa2a-218">但是傳回的錯誤，對網站本身不會造成任何損害。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="cfa2a-219">這個命令可能需要幾分鐘的時間來執行數百個網站，而不是透過 Microsoft 365 系統管理中心的工作時間。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="cfa2a-220">以下是另一個大量的操作範例。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-220">Here's another bulk operation example.</span></span> <span data-ttu-id="cfa2a-221">使用此命令將 *Bonnie Kearney*（新 SharePoint 管理員）新增至組織中的所有網站：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="cfa2a-222">此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的所有 SharePoint 網站，並針對每個網站，將其登入名稱新增至網站的 Members 群組，以允許 Bonnie Kearney 存取 (**ForEach {Add-SPOUser-site $ \_ 。Url-LoginName "bkearney \@ litwareinc.com"-Group "Members"}**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="cfa2a-223">Microsoft 365 的 PowerShell 非常適合篩選資料</span><span class="sxs-lookup"><span data-stu-id="cfa2a-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="cfa2a-224">Microsoft 365 系統管理中心提供數種方式來篩選您的資料，以輕鬆找到目標的資訊子集。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="cfa2a-225">例如，Exchange 可輕鬆篩選使用者信箱的任何內容。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="cfa2a-226">例如，以下是居住在 Bloomington 城市中之所有使用者的信箱清單：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![在 Microsoft 365 系統管理中心中執行高級搜尋的範例，針對居住于 Bloomington 城市中之所有使用者的信箱清單。](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="cfa2a-228">Exchange 系統管理中心也可讓您合併篩選準則。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="cfa2a-229">例如，您可以尋找居住在 Bloomington 中，且在財務部門中運作之所有人員的信箱。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="cfa2a-230">不過，您可以在 Exchange 系統管理中心中做什麼限制。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="cfa2a-231">例如，您無法輕鬆尋找居住于 Bloomington *或* 聖地牙哥的人員信箱，或是未在 Bloomington 中生活之所有人員的信箱。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="cfa2a-232">您可以使用下列 Microsoft 365 命令 PowerShell，以取得居住在 Bloomington 或聖地牙哥之所有人員的信箱清單：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="cfa2a-233">以下是結果的範例：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="cfa2a-234">此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的所有使用者，該訂閱具有位於聖地牙哥或 Bloomington (中的信箱 **，其中 {$ \_ 。RecipientTypeDetails-eq "UserMailbox" 和 ($ \_ 。城市-eq "聖地牙哥"-或 $ \_ 。City-eq "Bloomington" ) }**) ，然後顯示每個 (**選取 DisplayName，城市**) 的名稱和城市。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="cfa2a-235">以下命令可以列出除 Bloomington 之外任何地方生活的人員的所有信箱：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="cfa2a-236">以下是結果的範例：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-236">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="cfa2a-237">此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的信箱未位於 Bloomington 的城市中的所有使用者 (**其中 {$ \_ 。RecipientTypeDetails-eq "UserMailbox"-和 $ \_ 。City-ne "Bloomington"}**) ，然後顯示每個的名稱和城市。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="cfa2a-238">使用萬用字元</span><span class="sxs-lookup"><span data-stu-id="cfa2a-238">Use wildcards</span></span>

<span data-ttu-id="cfa2a-239">您也可以在 PowerShell 篩選中使用萬用字元，以符合部分名稱。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="cfa2a-240">例如，假設您正在尋找使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="cfa2a-241">您可以記得，使用者的姓氏是 *Anderson* 或可能是 *Henderson* 或 *Jorgenson*。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="cfa2a-242">您可以使用搜尋工具並執行三種不同的搜尋，以在 Microsoft 365 系統管理中心中追蹤該使用者：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="cfa2a-243">一個用於  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="cfa2a-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="cfa2a-244">一個用於  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="cfa2a-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="cfa2a-245">一個用於  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="cfa2a-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="cfa2a-246">因為這些名稱中的三個都以 "兒子" 結尾，您可以告訴 PowerShell 顯示名稱以 "兒子" 結尾的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="cfa2a-247">命令如下：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="cfa2a-248">此 PowerShell 命令的轉譯如下：取得目前 Microsoft 365 訂閱中的所有使用者，但使用僅列出姓氏結尾為 "兒子" (**篩選器 "{LastName-like" 子系 \* "}"**) 的使用者。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="cfa2a-249">\*代表任何一組字元，也就是使用者的姓氏中的字母。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="cfa2a-250">Microsoft 365 的 PowerShell 可讓您輕鬆地列印或儲存資料</span><span class="sxs-lookup"><span data-stu-id="cfa2a-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="cfa2a-251">Microsoft 365 系統管理中心可讓您查看資料清單。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="cfa2a-252">以下是商務用 Skype Online 系統管理中心的範例，顯示已啟用商務用 Skype Online 的使用者清單：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![商務用 Skype Online 系統管理中心，顯示商務用 Skype Online 已啟用的使用者清單的範例。](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="cfa2a-254">若要將該資訊儲存至檔案，您必須將其貼到檔或 Microsoft Excel 工作表中。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="cfa2a-255">這兩種情況可能需要其他格式。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-255">Either case might require additional formatting.</span></span> <span data-ttu-id="cfa2a-256">此外，Microsoft 365 系統管理中心不會提供直接列印所顯示清單的方式。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="cfa2a-257">幸運的是，您可以使用 PowerShell，而不只顯示清單，但可將其儲存至可輕鬆匯入 Excel 的檔案。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="cfa2a-258">以下是範例命令，可將商務用 Skype Online 使用者資料儲存到以逗號分隔的值 (CSV) 檔中，然後就可以輕鬆地匯入為 Excel 工作表中的資料表：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="cfa2a-259">以下是結果的範例：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-259">Here's an example of the results:</span></span>
  
![為商務用 Skype Online 使用者資料（儲存于逗號分隔值檔案）匯入 Excel 工作表中的資料表範例。](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="cfa2a-261">此 PowerShell 命令的轉譯如下：在目前的 Microsoft 365 訂閱中取得所有商務用 Skype Online 使用者 (**Get-CsOnlineUser**) ;只取得「使用者名稱」、「UPN」和「位置」 (**選取 DisplayName、UserPrincipalName、UsageLocation**) ;然後將此資訊儲存在名為 C： logsSfBUsers.csv 的 CSV 檔案中 \\ \\ (**匯出 Csv 路徑 "c： \\ Logs \\SfBUsers.csv"-NoTypeInformation**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="cfa2a-262">您也可以使用選項將此清單儲存為 XML 檔或 HTML 頁面。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="cfa2a-263">實際上，使用其他的 PowerShell 命令，您可以將它直接儲存為 Excel 檔案，並以您想要的任何自訂格式設定。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="cfa2a-264">您也可以傳送 PowerShell 命令的輸出，將清單直接顯示在 Windows 中的預設印表機。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="cfa2a-265">以下是範例命令：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="cfa2a-266">以下是您將列印出的文件樣貌：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-266">Here's what your printed document will look like:</span></span>
  
![已列印的檔的範例是直接傳送至 Windows 中預設印表機的 PowerShell 命令輸出。](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="cfa2a-268">此 PowerShell 命令的轉譯如下：在目前的 Microsoft 365 訂閱中取得所有商務用 Skype Online 使用者;只取得使用者名稱、UPN 和位置;，然後將該資訊傳送至預設 Windows 印表機 (**Out-Printer**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="cfa2a-269">列印的檔與 PowerShell 命令視窗中的顯示具有相同的簡易格式。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="cfa2a-270">若要取得硬拷貝，只要新增 **|Out-Printer** 至命令的結尾。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="cfa2a-271">Microsoft 365 的 PowerShell 可讓您跨伺服器產品進行管理</span><span class="sxs-lookup"><span data-stu-id="cfa2a-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="cfa2a-272">組成 Microsoft 365 的元件是設計成共同運作。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="cfa2a-273">例如，假設您將新使用者新增至 Microsoft 365，並指定使用者的部門和電話號碼等資訊。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="cfa2a-274">當您在任何 Microsoft 365 服務中存取使用者的資訊時，就可以使用該資訊：商務用 Skype Online、Exchange 或 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="cfa2a-275">不過，這是對跨越產品系列的一般資訊而言。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="cfa2a-276">產品特有的資訊，例如使用者的 Exchange 信箱的相關資訊，通常無法用於整個套件。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="cfa2a-277">例如，有關使用者信箱是否已啟用的資訊，只適用于 Exchange 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="cfa2a-278">假設您想要製作一份報告，顯示所有使用者的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="cfa2a-279">使用者的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="cfa2a-279">The user's display name</span></span>
    
- <span data-ttu-id="cfa2a-280">使用者是否已取得 Microsoft 365 的授權</span><span class="sxs-lookup"><span data-stu-id="cfa2a-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="cfa2a-281">使用者的 Exchange 信箱是否已啟用</span><span class="sxs-lookup"><span data-stu-id="cfa2a-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="cfa2a-282">是否已對使用者啟用商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="cfa2a-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="cfa2a-283">您無法在 Microsoft 365 系統管理中心中輕鬆產生這類報表。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cfa2a-284">相反地，您必須建立個別的檔來儲存資訊，例如 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="cfa2a-285">然後，從 Microsoft 365 系統管理中心取得所有的使用者名稱和授權資訊、從 Exchange 系統管理中心取得信箱資訊、從商務用 Skype Online 系統管理中心取得商務用 Skype Online 資訊，然後再將該資訊結合在一起。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="cfa2a-286">另一種方法是使用 PowerShell 腳本為您編譯報告。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="cfa2a-287">下列範例腳本比您在本文中所看到的命令複雜。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="cfa2a-288">不過，它會顯示使用 PowerShell 建立很難取得的資訊視圖的可能性。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="cfa2a-289">以下是腳本，用來編譯及顯示您需要的清單：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-289">Here's the script to compile and display the list you need:</span></span>
  
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

<span data-ttu-id="cfa2a-290">以下是結果的範例：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-290">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="cfa2a-291">此 PowerShell 腳本的轉譯如下：</span><span class="sxs-lookup"><span data-stu-id="cfa2a-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="cfa2a-292">取得目前 Microsoft 365 訂閱中的所有使用者，並將資訊儲存在名為 *$x* 的變數中 (**$x = AzureADUser**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="cfa2a-293">啟動迴圈，以執行 (\*\*foreach ($i 中 \*\* 的所有使用者 $x foreach $x) ) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="cfa2a-294">定義名為 *$y* 的變數，並將使用者的信箱資訊儲存 (**$y = Get-Mailbox 身分 $i.UserPrincipalName**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="cfa2a-295">將新屬性新增至名為 *IsMailBoxEnabled*的使用者資訊中。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="cfa2a-296">將它設定為使用者信箱的 IsMailBoxEnabled 屬性值 (**$i | Add-Member-MemberType NoteProperty 名稱 IsMailBoxEnabled-value $Y IsMailBoxEnabled**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="cfa2a-297">定義名為 *$y*的變數，然後將該使用者的商務用 Skype Online 資訊儲存 (**$Y = Get-CsOnlineUser 識別碼 $i.UserPrincipalName**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="cfa2a-298">將新屬性新增至名為 *EnabledForSfB*的使用者資訊中。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="cfa2a-299">將它設定為使用者商務用 Skype Online 資訊 (**$i | Add-Member-MemberType NoteProperty-Name EnabledForSfB-value $y** 的 enabled 屬性值。已啟用) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="cfa2a-300">顯示使用者清單，但不論其是否已授權，都只包含他們的名稱，以及是否啟用其信箱的兩個新屬性，以及是否為商務用 Skype Online (**$x |選取 [DisplayName]、Islicensed 內容、IsMailboxEnabled、EnabledforSfB**) 。</span><span class="sxs-lookup"><span data-stu-id="cfa2a-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cfa2a-301">請參閱</span><span class="sxs-lookup"><span data-stu-id="cfa2a-301">See also</span></span>

[<span data-ttu-id="cfa2a-302">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="cfa2a-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="cfa2a-303">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="cfa2a-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="cfa2a-304">在 Microsoft 365 中使用 Windows PowerShell 建立報告</span><span class="sxs-lookup"><span data-stu-id="cfa2a-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
